---
title: 파티 및 전체 주소록 모델로 업그레이드
description: 이 항목에서는 이중 쓰기 데이터를 당사자 및 전체 주소록 모델로 업그레이드하는 방법에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95d272d9076f1ab25230e4efa98e321bdd618062
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8461023"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>파티 및 전체 주소록 모델로 업그레이드

[!include [banner](../../includes/banner.md)]



[Microsoft Azure Data Factory 템플릿](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)은 파티 및 전체 주소록 모델에 이중 쓰기로 다음 기존 데이터를 업그레이드하는 데 도움이 됩니다. **계정**, **연락처**, **공급업체** 테이블, 우편 및 전자 주소의 데이터.

다음 세 가지 Data Factory 템플릿이 제공됩니다. 재무 및 운영 앱과 고객 참여 앱의 데이터를 조정하는 데 도움이 됩니다.

- **[파티 템플릿](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json)(이중 쓰기 Party-GAB schema/arm_template.json으로 데이터 업그레이드)** – 이 템플릿은 **계정**, **연락처**, **공급업체** 데이터와 연결된 **파티** 및 **연락처** 데이터를 업그레이드하는 데 도움이 됩니다.
- **[파티 우편 주소 템플릿](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json)(이중 쓰기 Party-GAB 스키마로 데이터 업그레이드/당사자 우편 주소로 업그레이드 - GAB/arm_template.json)** – 이 템플릿은 **계정**, **연락처**, **공급업체** 데이터와 관련된 우편 주소를 업그레이드하는 데 도움이 됩니다.
- **[파티 전자 주소 템플릿](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json)(이중 쓰기 Party-GAB 스키마로 데이터 업그레이드/당사자 전자 주소로 업그레이드 - GAB/arm_template.json)** – 이 템플릿은 **계정**, **연락처**, **공급업체** 데이터와 관련된 전자 주소를 업그레이드하는 데 도움이 됩니다.

프로세스가 끝나면 다음과 같은 쉼표로 구분된 값(.csv) 파일이 생성됩니다.

| 파일 이름 | 목적 |
|---|---|
| FONewParty.csv | 이 파일은 재무 및 운영 앱 내에 새로운 **파티** 레코드를 만듭니다. |
| ImportFONewPostalAddressLocation.csv | 이 파일은 재무 및 운영 앱에 새로운 **우편 주소 위치** 레코드를 만듭니다. |
| ImportFONewPartyPostalAddress.csv | 이 파일은 재무 및 운영 앱에 새로운 **파티 우편 주소** 레코드를 만듭니다. |
| ImportFONewPostalAddress.csv | 이 파일은 재무 및 운영 앱에 새로운 **우편 주소** 레코드를 만듭니다. |
| ImportFONewElectronicAddress.csv | 이 파일은 재무 및 운영 앱에 새로운 **전자 주소** 레코드를 만듭니다. |

이 항목에서는 Data Factory 템플릿을 사용하고 데이터를 업그레이드하는 방법에 대해 설명합니다. 사용자 정의가 없는 경우 템플릿을 있는 그대로 사용할 수 있습니다. 그러나 **계정**, **연락처**, **공급업체** 데이터에 대한 사용자 정의가 있는 경우 이 항목에 설명된 대로 템플릿을 수정해야 합니다.

> [!IMPORTANT]
> 당사자 우편 주소 및 당사자 전자 주소 템플릿을 실행하기 위한 특별 지침이 있습니다. 먼저 당사자 템플릿을 실행한 다음 당사자 우편 주소 템플릿을 실행한 다음 당사자 전자 주소 템플릿을 실행해야 합니다. 각 템플릿은 별도의 데이터 팩터리에서 가져오도록 설계되었습니다.

## <a name="prerequisites"></a>전제 조건

파티 및 전체 주소록 모델로 업그레이드하려면 다음 전제 조건이 충족되어야 합니다.

+ [Azure 구독](https://portal.azure.com/)이 있어야 합니다.
+ [템플릿](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)에 액세스할 수 있어야 합니다.
+ 기존 이중 쓰기 고객이어야 합니다.

## <a name="prepare-for-the-upgrade"></a>업그레이드 준비

업그레이드에는 다음 준비가 필요합니다.

+ **전체 동기화:** 재무 및 운영 환경과 고객 참여 환경은 **계정(고객)**, **연락처** 및 **공급업체** 테이블의 완전히 동기화된 상태입니다.
+ **통합 키:** Customer Engagement 앱의 **계정(고객)**, **연락처** 및 **공급업체** 테이블은 기본 통합 키를 사용합니다. 통합 키를 사용자 정의한 경우 템플릿을 사용자 정의해야 합니다.
+ **파티 번호:** 업그레이드될 모든 **계정(고객)**, **연락처** 및 **공급업체** 레코드에는 파티 번호가 있습니다. 파티 번호가 없는 레코드는 무시됩니다. 해당 레코드를 업그레이드하려면 업그레이드 프로세스를 시작하기 전에 당사자 번호를 추가하세요.
+ **시스템 중단:** 업그레이드 프로세스 중에 재무 및 운영 환경과 고객 참여 환경을 모두 오프라인으로 전환해야 합니다.
+ **스냅샷:** 재무 및 운영 앱과 고객 참여 앱의 스냅샷을 만듭니다. 그런 다음 필요한 경우 스냅샷을 사용하여 이전 상태를 복원할 수 있습니다.

## <a name="deployment"></a>배포

1. [Dynamics-365-FastTrack-구현-자산](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema)에서 템플릿 다운로드.
2. [Azure Portal](https://portal.azure.com/)에 로그인합니다.
3. [리소스 그룹](/azure/azure-resource-manager/management/manage-resource-groups-portal)을 만듭니다.
4. 생성한 리소스 그룹에서 [스토리지 계정](/azure/storage/common/storage-account-create?tabs=azure-portal)을 만듭니다.
5. 생성한 리소스 그룹에서 [데이터 팩터리](/azure/data-factory/quickstart-create-data-factory-portal)를 만듭니다.
6. 데이터 팩터리를 열고 **작성자 및 모니터** 타일을 선택합니다.
7. **관리** 탭에서 **ARM 템플릿** 을 선택합니다.
8. **ARM 템플릿 가져오기** 를 선택하여 **파티** 템플릿을 가져옵니다.
9. 템플릿을 데이터 팩터리로 가져옵니다. **프로젝트 세부정보** 및 **인스턴스 세부정보** 에 대해 다음 값을 입력합니다.

    | 필드 | 값 |
    |---|---|
    | 구독 | Azure 구독 |
    | 리소스 그룹 | 스토리지 계정이 생성된 것과 동일한 리소스를 제공합니다. |
    | 지역 | 지역 |
    | 팩토리 이름 | 팩토리 이름 |
    | FO 연결된 서비스_서비스 주체 키 | 애플리케이션의 키 |
    | Azure Blob Storage 연결 문자열 | Azure Blob Storage 연결 문자열 |
    | Dynamics CRM 연결된 서비스_암호 | 사용자 이름으로 지정한 사용자 계정의 암호 |
    | FO 연결된 서비스_속성_유형 속성_url | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | FO 연결된 서비스_속성_유형 속성_테넌트 | 애플리케이션이 있는 테넌트에 대한 정보(도메인 이름 또는 테넌트 ID) |
    | FO 연결된 서비스_속성_유형 속성_aad 리소스 Id | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | FO 연결된 서비스_속성_유형 속성_서비스 주체 Id | 애플리케이션의 클라이언트 ID |
    | Dynamics Crm 연결된 서비스_속성_유형 속성_사용자 이름 | Dynamics 365에 연결하는 데 사용되는 사용자 이름 |

    자세한 내용은 다음 항목을 참조하세요.

    - [각 환경에 대한 Resource Manager 템플릿을 수동으로 승격](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [연결된 서비스 속성](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Azure Data Factory를 사용하여 데이터 복사](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. 배포 후 데이터 팩터리의 데이터 세트, 데이터 흐름 및 연결된 서비스의 유효성을 검사합니다.

    ![데이터 세트, 데이터 흐름 및 연결된 서비스.](media/data-factory-validate.png)

11. **관리** 로 이동합니다. **연결** 에서 **연결된 서비스** 를 선택합니다. 그런 다음 **DynamicsCrmLinkedService** 를 선택합니다. **연결된 서비스 편집(Dynamics CRM)** 대화 상자에서 다음 값을 입력합니다.

    | 필드 | 값 |
    |---|---|
    | 이름 | DynamicsCrmLinkedService |
    | 설명 | 엔터티 데이터를 가져오기 위해 CRM 인스턴스와 연결하는 연결된 서비스 |
    | 통합 런타임을 통해 연결 | 자동 해결 통합 런타임 |
    | 배포 유형 | 온라인 |
    | 서비스 Uri | `https://<organization-name>.crm[x].dynamics.com` |
    | 인증 유형 | Office365 |
    | 사용자 이름 | |
    | 암호 또는 Azure Key Vault | 암호 |
    | 암호 | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Data Factory 템플릿 실행 준비

이 섹션에서는 당사자 우편 주소 및 당사자 전자 주소 Data Factory 템플릿을 실행하기 전에 필요한 설정에 대해 설명합니다.

### <a name="setup-to-run-the-party-postal-address-template"></a>당사자 우편 주소 템플릿을 실행하기 위한 설정

1. Customer Engagement 앱에 로그인하고 **설정** \> **개인화 설정** 으로 이동합니다. 그런 다음 **일반** 탭에서 시스템 관리자 계정의 시간대 설정을 구성합니다. 금융 및 운영 앱에서 우편 주소의 "유효한 시작" 및 "유효한" 날짜를 업데이트하려면 시간대가 협정 세계시(UTC)여야 합니다.

    ![시스템 관리자 계정에 대한 시간대 설정.](media/ADF-1.png)

2. Data Factory에서 **관리** 탭의 **전역 매개 변수** 아래에서 다음 전역 매개 변수를 작성합니다.

    | 번호 | 이름 | 형식 | 값 |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | 문자열 | 이 매개변수는 새로 생성된 우편 주소에 일련 번호를 접두사로 추가합니다. 재무 및 운영 앱 및 고객 참여 앱의 우편 주소와 충돌하지 않는 문자열을 제공해야 합니다. 예를 들어 **ADF-PAD-** 를 사용합니다. |

    ![관리 탭에서 생성된 PostalAddressIdPrefix 전역 매개변수입니다.](media/ADF-2.png)

3. 완료되면 **모두 게시** 를 선택합니다.

    ![모두 게시 버튼.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>파티 전자 주소 템플릿을 실행하기 위한 설정

1. Data Factory에서 **관리** 탭의 **전역 매개 변수** 아래에서 다음 전역 매개 변수를 작성합니다.

    | 번호 | 이름 | 형식 | 값 |
    |---|---|---|---|
    | 1 | IsFOSource | 부울 | 이 매개변수는 충돌 시 대체되는 기본 시스템 주소를 결정합니다. 값이 **진실** 이면 재무 및 운영 앱의 기본 주소가 Customer Engagement 앱의 기본 주소를 대체합니다. 값이 **false진실** 이면 Customer Engagement 앱의 기본 주소가 금융 및 운영 앱의 기본 주소를 대체합니다. |
    | 2 | ElectronicAddressIdPrefix | 문자열 | 이 매개변수는 새로 생성된 전자 주소에 일련 번호를 접두사로 추가합니다. 재무 및 운영 앱 및 Customer Engagement 앱의 전자 주소와 충돌하지 않는 문자열을 제공해야 합니다. 예를 들어 **ADF-EAD-** 를 사용합니다. |

    ![관리 탭에서 생성된 IsFOSource 및 ElectronicAddressIdPrefix 전역 매개변수.](media/ADF-4.png)

2. 완료되면 **모두 게시** 를 선택합니다.

## <a name="run-the-templates"></a>템플릿 실행

1. 금융 및 운영 앱을 사용하는 다음 **파티**, **계정**, **연락처** 및 **공급업체** 이중 쓰기 맵을 중지합니다.

    + CDS 당사자(msdyn_parties) 
    + 고객 V3(계정)
    + 고객 V3(연락처)
    + CDS 연락처 V2(연락처)
    + CDS 연락처 V2(연락처)
    + 공급업체 V2(msdyn_vendor)
    + 연락처 V2(msdyn_contactforparties)
    + CDS 당사자 우편 주소 위치(msdyn_partypostaladdresses)
    + CDS 우편 주소 기록 V2(msdyn_postaladdresses)
    + CDS 우편 주소 위치(msdyn_postaladdresscollections)
    + 당사자 연락처 V3(msdyn_partyelectronicaddresses)

2. Dataverse의 **msdy_dualwriteruntimeconfig** 테이블에서 지도가 제거되었는지 확인합니다.
3. AppSource에서 [이중 쓰기 파티 및 전체 주소록 솔루션](https://aka.ms/dual-write-gab)을 설치합니다.
4. 다음 테이블에 데이터가 포함된 경우 금융 및 운영 앱에서 **초기 동기화** 를 실행합니다.

    + 인사말
    + 개인 문자 유형
    + 결구
    + 담당자 직함
    + 의사결정 역할
    + 충성도 수준

5. Customer Engagement 앱에서 다음 플러그인 단계를 비활성화합니다.

    + 계정 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: 계정 업데이트
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: 계정 업데이트

    + 연락처 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: 연락처 업데이트
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: 연락처 업데이트

    + msdyn_party 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party 업데이트

    + msdyn_vendor 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor 업데이트

    + Customeraddress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: 고객 주소 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: customeraddress 업데이트

        + 삭제

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: customeraddress 삭제

    + msdyn_partypostaladdress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: msdyn_partypostaladdress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress 업데이트
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: msdyn_partypostaladdress 업데이트

    + msdyn_postaladdress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: msdyn_postaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: msdyn_postaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: msdyn_postaladdress 업데이트
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress 업데이트

    + msdyn_partyelectronicaddress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress 업데이트

        + 삭제

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: msdyn_partyelectronicaddress 삭제

6. Customer Engagement 앱에서 다음 워크플로를 비활성화합니다.

    + 계정 테이블에 공급업체 생성
    + 계정 테이블에 공급업체 생성
    + 연락처 테이블에 사람 유형의 공급업체 만들기
    + 공급업체 테이블에 사람 유형의 공급업체 만들기
    + 계정 테이블에 공급업체 업데이트
    + 공급업체 테이블에 공급업체 업데이트
    + 연락처 테이블에 사람 유형의 공급업체 업데이트
    + 공급업체 테이블에 사람 유형의 공급업체 업데이트

7. 다음 그림과 같이 데이터 팩터리에서 **지금 트리거** 를 선택하여 템플릿을 실행합니다. 데이터 볼륨에 따라 이 프로세스를 완료하는 데 몇 시간이 걸릴 수 있습니다.

    ![템플릿 실행.](media/data-factory-trigger.png)

    > [!NOTE]
    > **계정**, **연락처**, **공급업체** 에 대한 사용자 정의가 있는 경우 템플릿을 수정해야 합니다.

8. 새 **파티** 레코드를 금융 및 운영 앱에 가져옵니다.

    1. Azure Blob Storage에서 **FONewParty.csv** 파일을 다운로드합니다. 경로는 **partybootstrapping/output/FONewParty.csv** 입니다.
    2. **FONewParty.csv** 파일을 Excel 파일로 변환하고 Excel 파일을 재무 및 운영 앱으로 가져옵니다. 또는 CSV 가져오기가 작동하는 경우 .csv 파일을 직접 가져올 수 있습니다. 데이터 볼륨에 따라 이 단계를 완료하는 데 몇 시간이 걸릴 수 있습니다. 자세한 내용은 [데이터 가져오기 및 내보내기 작업 개요](../data-import-export-job.md)를 참조하세요.

    ![Dataverse 파티 레코드 가져오기.](media/data-factory-import-party.png)

9. 데이터 공장에서 당사자 우편 주소 및 당사자 전자 주소 템플릿을 차례로 실행합니다.

    + 당사자 우편 주소 템플릿은 Customer Engagement 앱의 모든 우편 주소 레코드를 업데이트하고 해당 **계정**, **연락처** 및 **공급업체** 레코드와 연결합니다. 또한 ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv 및 ImportFONewPostalAddress.csv라는 3개의 .csv 파일도 생성합니다.
    + 당사자 전자 주소 템플릿은 Customer Engagement 앱의 모든 전자 주소를 업데이트하고 해당 **계정**, **연락처** 및 **공급업체** 레코드와 연결합니다. 또한 하나의 .csv 파일인 ImportFONewElectronicAddress.csv를 생성합니다.

    ![당사자 우편 주소 및 당사자 전자 주소 템플릿을 실행합니다.](media/ADF-7.png)

10. 이 데이터로 재무 및 운영 앱을 업데이트하려면 .csv 파일을 Excel 통합 문서로 변환하고 [재무 및 운영 앱으로 가져오기](/data-entities/data-import-export-job)를 수행합니다. 또는 CSV 가져오기가 작동하는 경우 .csv 파일을 직접 가져올 수 있습니다. 볼륨에 따라 이 단계를 완료하는 데 몇 시간이 걸릴 수 있습니다.

    ![가져오기 성공.](media/ADF-8.png)

11. Customer Engagement 앱에서 다음 플러그인 단계를 활성화합니다.

    + 계정 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: 계정 업데이트
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: 계정 업데이트

    + 연락처 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: 연락처 업데이트
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: 연락처 업데이트

    + msdyn_party 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: msdyn_party 업데이트

    + msdyn_vendor 업데이트

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: msdyn_vendor 업데이트

    + msdyn_partypostaladdress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: msdyn_partypostaladdress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: msdyn_partypostaladdress 업데이트
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: msdyn_partypostaladdress 업데이트

    + msdyn_postaladdress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: msdyn_postaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: msdyn_postaladdress 생성
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: msdyn_postaladdress 업데이트
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: msdyn_postaladdress 업데이트
 
    + msdyn_partyelectronicaddress

        + 만들기

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress 생성

        + 업데이트

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: msdyn_partyelectronicaddress 업데이트

        + 삭제

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: msdyn_partyelectronicaddress 삭제

12. 이전에 비활성화한 경우 고객 참여 앱에서 다음 워크플로를 활성화합니다.

    + 계정 테이블에 공급업체 생성
    + 계정 테이블에 공급업체 생성
    + 연락처 테이블에 사람 유형의 공급업체 만들기
    + 공급업체 테이블에 사람 유형의 공급업체 만들기
    + 계정 테이블에 공급업체 업데이트
    + 공급업체 테이블에 공급업체 업데이트
    + 연락처 테이블에 사람 유형의 공급업체 업데이트
    + 공급업체 테이블에 사람 유형의 공급업체 업데이트

13. [파티 및 전체 주소록](party-gab.md)에 설명된 대로 **파티** 레코드 관련 맵을 실행합니다.

## <a name="explanation-of-the-data-factory-templates"></a>Data Factory 템플릿에 대한 설명

이 섹션에서는 각 Data Factory 템플릿의 단계를 안내합니다.

### <a name="steps-in-the-party-template"></a>파티 템플릿의 단계

1. 1~6단계에서는 이중 쓰기가 가능한 회사를 식별하고 해당 회사에 대한 필터 절을 작성합니다.
2. 7-1~7-9단계에서는 재무 및 운영 앱과 고객 참여 앱 모두에서 데이터를 검색하고 업그레이드를 위해 해당 데이터를 준비합니다.
3. 8~9단계는 재무 및 운영 앱과 고객 참여 앱 간에 **계정**, **연락처** 및 **공급업체** 레코드에 대한 파티 번호를 비교합니다. 파티 번호가 없는 레코드는 건너뜁니다.
4. 10단계에서는 고객 참여 앱과 재무 및 운영 앱에서 생성해야 하는 당사자 기록에 대해 두 개의 .csv 파일을 생성합니다.

    - **FOCDSParty.csv** – 이 파일에는 회사에서 이중 쓰기가 활성화되었는지 여부에 관계없이 두 시스템의 모든 당사자 레코드가 포함됩니다.
    - **FONewParty.csv** – 이 파일에는 Dataverse에서 알고 있는 당사자 기록의 하위 집합이 포함되어 있습니다(예: **잠재 고객** 유형의 계정).

5. 11단계에서는 고객 참여 앱에서 당사자를 만듭니다.
6. 12단계는 Customer Engagement 앱에서 당사자의 GUID(Globally Unique Identifier)를 검색하여 이후 단계에서 **계정**, **연락처**, **공급업체** 레코드를 연결할 수 있도록 합니다.
7. 13단계는 **계정**, **연락처**, **공급업체** 레코드를 파티 GUID와 연결합니다.
8. 14-1~14-3단계는 Customer Engagement 앱의 **계정**, **연락처**, **공급업체** 레코드를 파티 GUID와 연결합니다.
9. 15-1~15-3단계는 **파티 연락처** 레코드를 **계정**, **연락처**, **공급업체** 레코드와 비교합니다.
10. 16-1단계부터 16-7단계까지 인사말 및 개인 문자 유형과 같은 참조 데이터를 검색하고 **파티 연락처** 레코드와 연결합니다.
11. 17단계는 **파티 연락처** 레코드를 **계정**, **연락처**, **공급업체** 레코드와 통합합니다.
12. 18단계는 **파티 문의** 레코드를 Customer Engagement 앱으로 가져옵니다.

### <a name="steps-in-the-party-postal-address-template"></a>파티 우편 주소 템플릿의 단계

1. 1-1~1-10단계에서는 재무 및 운영 앱과 Customer Engagement 앱 모두에서 데이터를 검색하고 업그레이드를 위해 해당 데이터를 준비합니다.
2. 2단계에서는 우편 주소와 당사자 우편 주소를 결합하여 재무 및 운영 앱의 우편 주소 데이터를 비정규화합니다.
3. 3단계에서는 Customer Engagement 앱에서 계정, 연락처 및 공급업체 주소 데이터의 중복을 제거하고 병합합니다.
4. 4단계에서는 재무 및 운영 앱용 .csv 파일을 만들어 계정, 연락처 및 공급업체 주소를 기반으로 하는 새 주소 데이터를 만듭니다.
5. 5-1단계에서는 재무 및 운영 앱과 Customer Engagement 앱을 기반으로 모든 주소 데이터를 생성하기 위해 고객 참여 앱에 대한 .csv 파일을 생성합니다.
6. 5-2단계에서는 .csv 파일을 수동 가져오기를 위한 재무 및 운영 가져오기 형식으로 변환합니다.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. 6단계에서는 우편 주소 수집 데이터를 Customer Engagement 앱으로 가져옵니다.
8. 7단계에서는 우편 주소 수집 데이터를 Customer Engagement 앱에서 검색합니다.
9. 8단계에서는 고객 주소 데이터를 생성하고 우편 주소 수집 ID를 연결합니다.
10. 9-1~9-2단계는 당사자 및 우편 주소 수집 ID를 우편 주소 및 당사자 우편 주소와 연결합니다.
11. 10-1~10-3단계에서는 고객 주소, 우편 주소 및 당사자 우편 주소를 Customer Engagement 앱으로 가져옵니다.

### <a name="steps-in-the-party-electronic-address-template"></a>파티 전자 주소 템플릿의 단계

1. 1-1~1-5단계에서는 재무 및 운영 앱과 Customer Engagement 앱 모두에서 데이터를 검색하고 업그레이드를 위해 해당 데이터를 준비합니다.
2. 2단계에서는 Customer Engagement 앱의 계정, 연락처 및 공급업체 엔터티의 전자 주소를 통합합니다.
3. 3단계에서는 Customer Engagement 앱과 재무 및 운영 앱의 기본 전자 주소 데이터를 병합합니다.
4. 4단계에서는 .csv 파일을 만듭니다.

    - 계정, 연락처 및 공급업체 주소를 기반으로 재무 및 운영 앱용 전자 주소 데이터를 만듭니다.
    - 재무 및 운영 앱의 전자 주소, 계정, 연락처 및 공급업체 주소를 기반으로 Customer Engagement 앱에 대한 새 전자 주소 데이터를 만듭니다.

5. 5-1단계에서는 전자 주소를 Customer Engagement 앱으로 가져옵니다.
6. 5-2단계에서는 .csv 파일을 만들어 Customer Engagement 앱의 계정 및 연락처에 대한 기본 주소를 업데이트합니다.
7. 6-1~6-2단계에서는 계정을 가져오고 기본 주소를 Customer Engagement 앱으로 연결합니다.

## <a name="troubleshooting"></a>문제 해결

1. 프로세스가 실패하면 데이터 팩터리를 다시 실행합니다. 실패한 활동에서 시작합니다.
2. 데이터 팩터리에서 생성된 일부 파일은 데이터 유효성 검사에 사용할 수 있습니다.
3. 데이터 팩터리는 .csv 파일을 기반으로 실행됩니다. 따라서 필드 값에 쉼표가 포함되면 결과에 영향을 줄 수 있습니다. 필드 값에서 모든 쉼표를 제거해야 합니다.
4. **모니터링** 탭은 처리된 모든 단계 및 데이터에 대한 정보를 제공합니다. 디버그할 특정 단계를 선택합니다.

    ![모니터링 탭.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>템플릿에 대해 자세히 알아보기

템플릿에 대한 자세한 내용은 [Azure Data Factory 템플릿 추가 정보에 대한 설명](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md)을 참조하세요.
