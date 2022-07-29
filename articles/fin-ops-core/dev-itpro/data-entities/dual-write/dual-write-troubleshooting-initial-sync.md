---
title: 초기 동기화 중 문제 해결
description: 이번에는 초기 동기화 중에 발생할 수 있는 문제를 해결하는 데 도움이 되는 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 030e565ffff561f6c1efbdd0de9928f70c7c46c0
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460651"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>초기 동기화 중 문제 해결

[!include [banner](../../includes/banner.md)]



이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 초기 동기화 중에 발생할 수 있는 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>재무 및 운영 앱에서 초기 동기화 오류 확인

매핑 템플릿을 활성화한 후 맵의 상태는 **실행 중** 이어야 합니다. 상태가 **Not running** 이면 초기 동기화 중에 오류가 발생한 것입니다. 오류를 보려면 **이중 쓰기** 페이지에서 **초기 동기화 세부 정보** 탭을 선택합니다.

![초기 동기화 세부 정보 탭에 오류가 있습니다.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>초기 동기화를 완료할 수 없습니다. 400 잘못된 요청

**문제를 해결하는 데 필요한 역할:** 시스템 관리자

매핑 및 초기 동기화를 실행하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*(\[잘못된 요청\], 원격 서버에서 오류를 반환했습니다. (400) 잘못된 요청입니다.) AX 내보내기에 오류가 발생했습니다.*

다음은 전체 오류 메시지의 예입니다.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

이 오류가 지속적으로 발생하고 초기 동기화를 완료할 수 없는 경우 다음 단계에 따라 문제를 해결하십시오.

1. 재무 및 운영 앱용 가상 머신(VM)에 로그인합니다.
2. Microsoft 관리 콘솔을 엽니다.
3. **서비스** 창에서 Microsoft Dynamics 365 데이터 가져오기 내보내기 프레임워크 서비스가 실행 중인지 확인합니다. 초기 동기화에 필요하므로 중지된 경우 다시 시작하십시오.

## <a name="initial-synchronization-error-403-forbidden"></a>초기 동기화 오류: 403 금지

초기 동기화 중에 다음과 같은 오류 메시지가 나타날 수 있습니다.

*(\[금지\], 원격 서버가 오류를 반환했습니다: (403) 금지됨), AX 내보내기에 오류가 발생했습니다.*

문제를 해결하려면 다음 단계를 따르십시오.

1. 재무 및 운영 앱에 로그인합니다.
2. **Azure Active Directory 애플리케이션** 페이지에서 **DtAppID** 클라이언트를 삭제한 다음 다시 추가합니다.

![Azure AD 애플리케이션 목록의 DtAppID 클라이언트.](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>초기 동기화 중 자체 참조 또는 순환 참조 실패

매핑에 자체 참조 또는 순환 참조가 있는 경우 오류 메시지가 표시될 수 있습니다. 오류는 다음 범주에 속합니다.

- [Vendors V2-to-msdyn_vendors 테이블 매핑 오류](#error-vendor-map)
- [Customers V3-to-Accounts 테이블 매핑 오류](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>V2에서 msdyn_vendors로의 Vendors 테이블 매핑 오류 해결

**PrimaryContactPersonId** 및 **InvoiceVendorAccountNumber** 열에 값이 있는 기존 행이 테이블에 있는 경우 **Vendors V2** 를 **msdyn\_vendors** 로 매핑하는 데 초기 동기화 오류가 발생할 수 있습니다. 이러한 오류는 **InvoiceVendorAccountNumber가** 자체 참조 열이고 **PrimaryContactPersonId** 가 공급 업체 매핑의 순환 참조이기 때문에 발생합니다.

수신되는 오류 메시지는 다음과 같은 형식을 갖습니다.

*필드에 대한 guid를 확인할 수 없습니다. \<field\>. 조회를 찾을 수 없습니다. \<value\>. 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

여기 예시들이 있습니다 :

- *msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid 필드에 대한 guid를 확인할 수 없습니다. 조회를 찾을 수 없습니다. 000056. 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid 필드에 대한 guid를 확인할 수 없습니다. 조회를 찾을 수 없습니다. V24-1 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

공급 업체 테이블의 행에 **PrimaryContactPersonId** 및 **InvoiceVendorAccountNumber** 열의 값이 있는 경우 다음 단계에 따라 초기 동기화를 완료합니다.

1. 재무 및 운영 앱의 매핑에서 **PrimaryContactPersonId** 및 **InvoiceVendorAccountNumber** 열을 삭제한 다음 매핑을 저장합니다.

    1. **공급 업체 V2(msdyn\_vendors)** 에 대한 이중 쓰기 매핑 페이지의 **테이블 매핑** 탭에 있는 왼쪽 필터에서 **재무 및 운영 앱** 을 선택합니다. 공급 업체 V2. 오른쪽 필터에서 **Sales.Vendor** 를 선택합니다.
    2. **PrimaryContactPersonId** 소스 열을 찾으려면 **primarycontactperson** 을 검색하십시오.
    3. **작업** 을 선택한 다음 **삭제** 를 선택합니다.

        ![PrimaryContactPersonId 열을 삭제합니다.](media/vend_selfref3.png)

    4. **InvoiceVendorAccountNumber** 열을 삭제하려면 이 단계를 반복합니다.

        ![InvoiceVendorAccountNumber 열을 삭제합니다.](media/vend-selfref4.png)

    5. 매핑에 대한 변경 사항을 저장합니다.

2. **Vendors V2** 테이블에 대한 변경 내용 추적을 끕니다.

    1. **데이터 관리** 작업 영역에서 **데이터 테이블** 타일을 선택합니다.
    2. **Vendors V2** 테이블을 선택하십시오.
    3. 작업 창에서 **옵션** 을 선택한 다음 **변경 내용 추적** 을 선택합니다.

        ![변경 추적 옵션을 선택합니다.](media/selfref_options.png)

    4. **변경 내용 추적 비활성화** 를 선택합니다.

        ![변경 내용 추적 비활성화를 선택합니다.](media/selfref_tracking.png)

3. **Vendors V2(msdyn\_vendors)** 매핑에 대한 초기 동기화를 실행합니다. 초기 동기화는 오류 없이 성공적으로 실행되어야 합니다.
4. **CDS 연락처 V2(연락처)** 매핑에 대한 초기 동기화를 실행합니다. 연락처 행에 대해서도 초기 동기화를 수행해야 하므로 공급 업체 테이블의 기본 연락처 열을 동기화하려면 이 매핑을 동기화해야 합니다.
5. **PrimaryContactPersonId** 및 **InvoiceVendorAccountNumber** 열을 **Vendors V2(msdyn\_vendors)** 매핑에 다시 추가한 다음 매핑을 저장합니다.
6. **Vendors V2(msdyn\_vendors)** 매핑에 대해 초기 동기화를 다시 실행합니다. 변경 추적이 꺼져 있으므로 모든 행이 동기화됩니다.
7. **Vendors V2** 테이블에 대해 변경 내용 추적을 다시 켭니다.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Customers V3-to-Accounts 테이블 매핑의 오류 해결

테이블에 **ContactPersonID** 및 **InvoiceAccount** 열에 값이 있는 기존 행이 있는 경우 **고객 V3** 을 **계정** 에 매핑할 때 초기 동기화 오류가 발생할 수 있습니다. 이러한 오류는 **InvoiceAccount** 가 자체 참조 열이고 **ContactPersonID** 가 공급 업체 매핑의 순환 참조이기 때문에 발생합니다.

수신되는 오류 메시지는 다음과 같은 형식을 갖습니다.

*필드에 대한 guid를 확인할 수 없습니다. \<field\>. 조회를 찾을 수 없습니다. \<value\>. 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

여기 예시들이 있습니다 :

- *msdyn\_vendorprimarycontactperson.msdyncontactpersonid 필드에 대한 guid를 확인할 수 없습니다. 조회를 찾을 수 없습니다. 000056. 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *msdyn\_billingaccount.accountnumber 필드에 대한 guid를 확인할 수 없습니다. 조회를 찾을 수 없습니다. 1206-1. 참조 데이터가 있는지 확인하려면 다음 URL을 시도하십시오. `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

고객 테이블의 행에 **ContactPersonID** 및 **InvoiceAccount** 열의 값이 있는 경우 다음 단계에 따라 초기 동기화를 완료합니다. **계정** 및 **연락처** 와 같은 기본 테이블에 대해 이 접근 방식을 사용할 수 있습니다.

1. 재무 및 운영 앱의 **고객 V3(계정) 매핑** 에서 **ContactPersonID** 및 **InvoiceAccount** 열을 삭제한 다음 매핑을 저장합니다.

    1. **고객 V3(계정)** 에 대한 이중 쓰기 매핑 페이지의 **테이블 매핑** 탭에 있는 왼쪽 필터에서 **재무 및 운영 앱을 선택합니다.고객 V3**. 오른쪽 필터에서 **Dataverse.Account** 를 선택합니다.
    2. **ContactPersonID** 소스 열을 찾으려면 **담당자** 를 검색하십시오.
    3. **작업** 을 선택한 다음 **삭제** 를 선택합니다.

        ![ContactPersonID 열을 삭제합니다.](media/cust_selfref3.png)

    4. **InvoiceAccount** 열을 삭제하려면 이 단계를 반복합니다.

        ![InvoiceAccount 열을 삭제합니다.](media/cust_selfref4.png)

    5. 매핑에 대한 변경 사항을 저장합니다.

2. **고객 V3** 테이블에 대한 변경 내용 추적을 끕니다.

    1. **데이터 관리** 작업 영역에서 **데이터 테이블** 타일을 선택합니다.
    2. **고객 V3** 테이블을 선택하십시오.
    3. 작업 창에서 **옵션** 을 선택한 다음 **변경 내용 추적** 을 선택합니다.

        ![변경 추적 옵션을 선택합니다.](media/selfref_options.png)

    4. **변경 내용 추적 비활성화** 를 선택합니다.

        ![변경 내용 추적 비활성화를 선택합니다.](media/selfref_tracking.png)

3. **고객 V3(계정)** 매핑에 대한 초기 동기화를 실행합니다. 초기 동기화는 오류 없이 성공적으로 실행되어야 합니다.
4. **CDS 연락처 V2(연락처)** 매핑에 대한 초기 동기화를 실행합니다.

    > [!NOTE]
    > 이름이 같은 맵이 2개 있습니다. **세부 정보** 탭에서 다음 설명이 있는 지도를 선택해야 합니다. **FO.CDS Vendor Contacts V2와 CDS.Contacts 간의 동기화를 위한 이중 쓰기 템플릿. 새 패키지 \[Dynamics365SupplyChainExtended\]가 필요합니다.**

5. **InvoiceAccount** 및 **ContactPersonId** 열을 다시 **Customers V3(계정)** 매핑에 추가한 다음 매핑을 저장합니다. **InvoiceAccount** 열과 **ContactPersonId** 열은 이제 다시 라이브 동기화 모드의 일부입니다. 다음 단계에서는 이러한 열에 대한 초기 동기화를 수행합니다.
6. **고객 V3(계정) 매핑** 에 대해 초기 동기화를 다시 실행합니다. 변경 내용 추적이 꺼져 있기 때문에 **InvoiceAccount** 및 **ContactPersonId** 에 대한 데이터는 Finance and Operations 앱에서 Dataverse로 동기화됩니다.
7. **InvoiceAccount** 및 **ContactPersonId** 의 데이터를 Dataverse 재무 및 운영 앱과 동기화하려면 데이터 통합 프로젝트를 사용해야 합니다.

    1. Power Apps에서 **Sales.Account** 와 **Finance and Operations apps.Customers V3** 테이블 간에 데이터 통합 프로젝트를 만듭니다. 데이터 방향은 재무 및 운영 앱에서 Dataverse 시작되어야 합니다. **InvoiceAccount** 는 이중 쓰기의 새로운 속성이므로 초기 동기화를 건너뛸 수 있습니다. 자세한 내용은 [Dataverse에 데이터 통합](/power-platform/admin/data-integrator)을 참조하십시오.

        다음 그림은 **CustomerAccount** 및 **ContactPersonId** 를 업데이트하는 프로젝트를 보여줍니다.

        ![CustomerAccount 및 ContactPersonId를 업데이트하기 위한 데이터 통합 프로젝트.](media/cust_selfref6.png)

    2. 필터 기준과 일치하는 행만 재무 및 운영 앱에서 업데이트되도록 Dataverse 측면의 필터에 회사 기준을 추가합니다. 필터를 추가하려면 필터 버튼을 선택하십시오. 이후 **쿼리 편집** 대화 상자에서 **\_msdyn\_company\_value eq '\<guid\>'** 와 같은 필터 쿼리를 추가할 수 있습니다.

        > [참고] 필터 버튼이 없으면 지원 티켓을 만들어 데이터 통합 팀에 테넌트에서 필터 기능을 활성화하도록 요청하십시오.

        **\_msdyn\_company\_value** 에 대한 필터 쿼리를 입력하지 않으면 모든 행이 동기화됩니다.

        ![필터 쿼리를 추가합니다.](media/cust_selfref7.png)

    이제 행의 초기 동기화가 완료되었습니다.

8. 재무 및 운영 앱에서 **고객 V3** 테이블에 대해 변경 내용 추적을 다시 켭니다.

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>10개 이상의 조회 필드가 있는 지도에서 초기 동기화 실패

**고객 V3 - 계정**, **판매 주문 매핑** 또는 조회 필드가 10개가 넘는 맵에서 초기 동기화 실패를 실행하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*CRM수출: 패키지 실행이 완료되었습니다. 오류 설명 5 $select=accountnumber, address2_city, address2_country, ...https://xxxxx//datasets/yyyyy/tables/accounts/items?에서 데이터 가져오기 시도 (msdyn_company/cdm_companyid eq 'id')&$orderby=계정 번호 오름차순 실패.*

쿼리에 대한 조회 제한으로 인해 엔터티 매핑에 조회가 10개를 초과하면 초기 동기화가 실패합니다. 자세한 내용은 [쿼리로 관련 테이블 기록 검색](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query)을 참조하십시오.

이 문제를 해결하려면 다음 단계를 따르십시오.

1. 조회 수가 10개 이하가 되도록 이중 쓰기 엔티티 맵에서 선택적 조회 필드를 제거하십시오.
2. 지도를 저장하고 초기 동기화를 수행합니다.
3. 첫 번째 단계의 초기 동기화가 성공하면 나머지 조회 필드를 추가하고 첫 번째 단계에서 동기화한 조회 필드를 제거합니다. 조회 필드 수가 10개 이하인지 확인하십시오. 지도를 저장하고 초기 동기화를 실행합니다.
4. 모든 조회 필드가 동기화될 때까지 이 단계를 반복합니다.
5. 모든 조회 필드를 맵에 다시 추가하고 맵을 저장하고 **초기 동기화 건너뛰기** 로 맵을 실행합니다.

이 프로세스는 지도에서 라이브 동기화 모드를 활성화합니다.

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>당사자 우편 주소 및 당사자 전자 주소의 초기 동기화 중 알려진 문제

당사자 우편 주소와 당사자 전자 주소의 초기 합성을 실행하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*Dataverse에서 파티 번호를 찾을 수 없습니다.*

**사람** 및 **조직** 유형의 당사자를 필터링하는 재무 및 운영 앱의 **DirPartyCDSEntity** 에 범위가 설정되어 있습니다. 결과적으로 **CDS 당사자 – msdyn_parties** 매핑의 초기 동기화는 **법인** 및 **운영 단위** 를 포함한 다른 유형의 당사자를 동기화하지 않습니다. **CDS 당사자 우편 주소(msdyn_partypostaladdresses)** 또는 **당사자 연락처 V3(msdyn_partyelectronicaddresses)** 에 대해 초기 동기화가 실행되면 오류가 수신될 수 있습니다.

모든 유형의 당사자가 성공적으로 동기화할 수 있도록 재무 및 운영 엔터티에서 Dataverse 당사자 유형 범위를 제거하기 위한 수정 작업을 진행 중입니다.

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>고객 또는 연락처 데이터에 대한 초기 동기화를 실행하는 동안 성능 문제가 있습니까?

**고객** 데이터에 대한 초기 동기화를 실행하고 **고객** 맵을 실행한 다음 **연락처** 데이터에 대한 초기 동기화를 실행하는 경우 **연락처** 주소에 대한 **LogisticsPostalAddress** 및 **LogisticsElectronicAddress** 테이블에 대한 삽입 및 업데이트 중에 성능 문제가 있을 수 있습니다. **CustCustomerV3Entity** 및 **VendVendorV2Entity** 에 대해 동일한 전역 우편 주소 및 전자 주소 테이블이 추적되고 이중 쓰기는 다른 쪽에 데이터를 쓰기 위해 더 많은 쿼리를 작성하려고 합니다. **고객** 에 대한 초기 동기화를 이미 실행한 경우 **연락처** 데이터에 대한 초기 동기화를 실행하는 동안 해당 맵을 중지합니다. **공급 업체** 데이터에 대해서도 동일한 작업을 수행합니다. 초기 동기화가 완료되면 초기 동기화를 건너뛰어 모든 맵을 실행할 수 있습니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
