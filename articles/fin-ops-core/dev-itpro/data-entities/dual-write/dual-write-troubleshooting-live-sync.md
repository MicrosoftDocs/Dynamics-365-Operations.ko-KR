---
title: 라이브 동기화 문제 해결
description: 이번에는 라이브 동기화 문제를 해결하는 데 도움이 될 수 있는 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: df184decdfa900ccb5c2070575e55052b9dfc547
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460648"
---
# <a name="troubleshoot-live-synchronization-issues"></a>라이브 동기화 문제 해결

[!include [banner](../../includes/banner.md)]



이번에는 Finance 및 Operations 앱 Microsoft Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 라이브 동기화 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 주제에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 섹션에서는 특정 역할 또는 특정 자격 증명이 필요한지 여부를 설명합니다.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>행을 생성할 때 실시간 동기화에 오류가 표시됨

Finance and Operations 앱에서 행을 만들 때 다음 오류 메시지가 나타날 수 있습니다.

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\'사용자가 조직의 구성원이 아닙니다.\\"}}\]', 원격 서버에서 오류를 반환했습니다. (403) 금지."}}".*

문제를 해결하려면 [시스템 요구 사항 및 전제 조건](requirements-and-prerequisites.md)의 단계를 따르십시오. 이러한 단계를 완료하려면 Dataverse에서 생성된 이중 쓰기 애플리케이션 사용자에게 시스템 관리자 역할이 있어야 합니다. 기본 소유 팀에는 시스템 관리자 역할도 있어야 합니다.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>라이브 동기화는 테이블 데이터를 저장하려고 할 때 오류를 표시합니다.

**문제를 해결하는 데 필요한 역할:** 시스템 관리자

Finance and Operations 앱에서 테이블 데이터를 저장하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*데이터베이스에 변경 사항을 저장할 수 없습니다. 작업 단위가 트랜잭션을 커밋할 수 없습니다. 엔티티 uom에 데이터를 쓸 수 없습니다. UnitOfMeasureEntity에 대한 쓰기가 엔터티 uom과 동기화할 수 없다는 오류 메시지와 함께 실패했습니다.*

이 문제를 해결하려면 재무 및 운영 앱과 Dataverse에 전제 조건 참조 데이터가 있는지 확인하십시오. 예를 들어 고객 기록이 특정 고객 그룹에 속하는 경우 고객 그룹 기록이 Dataverse에 있는지 확인합니다.

두 위치에 데이터가 있고 문제가 데이터와 관련이 없음을 확인한 경우 다음 단계를 따르십시오.

1. Excel 추가 기능을 사용하여 **DualWriteProjectConfigurationEntity** 엔터티를 엽니다. 추가 기능을 사용하려면 재무 및 운영 Excel 추가 기능에서 디자인 모드를 활성화하고 **DualWriteProjectConfigurationEntity** 를 워크시트에 추가합니다. 자세한 내용은 [Excel로 엔터티 데이터 보기 및 업데이트](../../office-integration/use-excel-add-in.md)를 참조하십시오.
2. 이중 쓰기 맵 및 프로젝트에서 문제가 있는 기록을 선택하여 삭제합니다. 모든 이중 쓰기 매핑에 대해 두 개의 기록이 있습니다.
3. Excel 추가 기능을 사용하여 변경 사항을 게시합니다. 이 단계는 엔터티 및 기본 테이블에서 기록을 삭제하기 때문에 중요합니다.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>재무 및 운영 앱에서 데이터를 생성할 때 읽기 또는 쓰기 권한 오류 처리

재무 및 운영 앱에서 데이터를 생성할 때 '잘못된 요청' 오류 메시지가 나타날 수 있습니다.

![잘못된 요청 오류 메시지의 예.](media/error_record_id_source.png)

이 문제를 해결하려면 매핑된 Dynamics 365 Sales 또는 Dynamics 365 Customer Service 사업부 팀에 올바른 보안 역할을 할당하여 누락된 권한을 활성화해야 합니다.

1. 재무 및 운영 앱에서 데이터 통합 연결 집합에 매핑된 사업부를 찾습니다.

    ![조직 매핑.](media/mapped_business_unit.png)

2. 고객 참여 앱에서 환경에 로그인하고 **보안 \> 설정** 으로 이동하여 매핑된 사업부의 팀을 찾습니다.

    ![매핑된 사업부의 팀입니다.](media/setting_security_page.png)

3. 편집할 팀의 페이지를 연 다음 **역할 관리** 를 선택합니다.

    ![역할 관리 버튼.](media/manage_team_roles.png)

4. **팀 역할 관리** 대화 상자에서 해당 테이블에 대한 읽기/쓰기 권한이 있는 역할을 할당한 후 **확인** 을 선택합니다.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>최근에 환경이 변경된 Dataverse 환경에서 동기화 문제 수정

**문제를 해결하는 데 필요한 역할:** 시스템 관리자

Finance and Operations 앱에서 데이터를 생성할 때 다음 오류 메시지가 나타날 수 있습니다.

*{entityName:'CustCustomerV3Entity','executionStatus':2,'fieldResponses':\[\],'recordResponses'\[{:'errorMessage':**'CustCustomerV3Entity 엔터티에 대한 페이로드를 생성할 수 없음'**,'logDateTime':'2019-08-27T18:51:52.584312 ','verboseError'}:\]'잘못된 URI 오류로 인해 페이로드 생성 실패: URI가 비어 있습니다.","isErrorCountUpdated":true}*

고객 참여 앱의 오류 메시지는 다음과 같습니다.

> ISV 코드에서 예기치 않은 오류가 발생했습니다. (ErrorType = ClientError) 플러그인의 예기치 않은 예외(실행): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: 엔터티 계정 처리 실패 - (연결된 당사자가 일정 시간 후에 제대로 응답하지 않아 연결 시도가 실패했거나 연결된 호스트가 응답하지 않아 설정된 연결이 실패했습니다.

재무 및 운영 앱에서 데이터를 생성하려고 할 때 Dataverse 환경이 잘못 재설정되면 이 오류가 발생합니다.

> [!IMPORTANT]
> 환경을 다시 연결한 경우 완화 단계를 계속하기 전에 모든 엔터티 맵을 중지해야 합니다.

문제를 해결하려면 Dataverse 재무 및 운영 앱 모두에서 단계를 완료해야 합니다.

1. 재무 및 운영 앱에서 다음 단계를 따르십시오.

    1. Excel 추가 기능을 사용하여 **DualWriteProjectConfigurationEntity** 엔터티를 엽니다. 추가 기능을 사용하려면 재무 및 운영 Excel 추가 기능에서 디자인 모드를 활성화하고 **DualWriteProjectConfigurationEntity** 를 워크시트에 추가합니다. 자세한 내용은 [Excel로 엔터티 데이터 보기 및 업데이트](../../office-integration/use-excel-add-in.md)를 참조하십시오.
    2. 이중 쓰기 맵 및 프로젝트에서 문제가 있는 기록을 선택하여 삭제합니다. 모든 이중 쓰기 매핑에 대해 두 개의 기록이 있습니다.
    3. Excel 추가 기능을 사용하여 변경 사항을 게시합니다. 이 단계는 엔터티 및 기본 테이블에서 기록을 삭제하기 때문에 중요합니다.
    4. 재무 및 운영 또는Dataverse  환경을 다시 연결할 때 오류를 방지하려면 이중 쓰기 구성이 남아 있지 않은지 확인하십시오.

2. Dataverse에서 다음 단계를 따르십시오.

    1. Dataverse 환경에 로그인합니다(예: `https://*****.crm.dynamics.com/`).
    2. **고급 설정** \> **고급 찾기** 로 이동합니다.
    3. **DualWrite 런타임 구성** 을 선택합니다.
    4. 보려는 열을 선택합니다.
    5. **결과** 를 선택하여 구성을 봅니다.
    6. 모든 인스턴스를 삭제합니다.

3. 재무 및 운영 앱에서 다음 단계를 따르십시오.

    1. Excel 추가 기능을 사용하여 **DualWriteProjectConfigurationEntity** 엔터티를 엽니다. 추가 기능을 사용하려면 재무 및 운영 Excel 추가 기능에서 디자인 모드를 활성화하고 **DualWriteProjectConfigurationEntity** 를 워크시트에 추가합니다. 자세한 내용은 [Excel로 엔터티 데이터 보기 및 업데이트](../../office-integration/use-excel-add-in.md)를 참조하십시오.
    2. 이중 쓰기 맵 및 프로젝트에서 문제가 있는 기록을 선택하여 삭제합니다. 모든 이중 쓰기 매핑에 대해 두 개의 기록이 있습니다.
    3. Excel 추가 기능을 사용하여 변경 사항을 게시합니다. 이 단계는 엔터티 및 기본 테이블에서 기록을 삭제하기 때문에 중요합니다.
    4. 재무 및 운영 또는Dataverse  환경을 다시 연결할 때 오류를 방지하려면 이중 쓰기 구성이 남아 있지 않은지 확인하십시오.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>전체 데이터베이스 복사를 수행한 후 라이브 동기화 오류

한 시스템에서 다른 시스템으로 전체 데이터베이스 복사본을 실행한 다음 데이터베이스 작업을 실행하려고 시도하면 다음 오류 메시지가 나타날 수 있습니다.

*SecureConfig 조직(???)이 실제 CRM 조직(???)과 일치하지 않습니다.*

한 시스템에 설정된 이중 쓰기 구성을 다른 시스템에서 사용할 수 없도록 이중 쓰기 런타임 플러그인에서 오류 메시지가 표시됩니다.

이 문제를 해결하려면 데이터베이스를 복원한 후 **msdyn_dualwriteruntimeconfig** 테이블의 모든 기록을 삭제하십시오. 자세한 내용은 [이중 쓰기 환경 연결 해제 및 다시 연결](relink-environments.md)을 참조하십시오.

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>이중 쓰기 맵에서 잘못된 쿼리 필터 구문으로 인해 발생하는 라이브 동기화 문제

이중 쓰기 맵 필터에 대한 쿼리 표현식이 구문적으로 정확하더라도 예상대로 작동하지 않을 수 있습니다. 필터 식은 쿼리 개체의 개별 데이터 원본이 아니라 엔터티에 있습니다. 따라서 생성된 SQL 쿼리는 예상 결과를 반환하지 않습니다.

다음은 예입니다.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

상위 항목이 없는 프로젝트가 필터링될 것으로 예상할 수 있습니다. 그러나 필터는 다음 예시와 유사한 쿼리로 변환되기 때문에 작동하지 않습니다.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

실제 결과는 `parentProject` 필드가 `null`로 평가된다는 것입니다. 그러나 `null` 빈 스트링과 같지 않습니다. 이 불일치 때문에 쿼리 필터는 유효한 결과를 반환하지 않습니다.

문제를 해결하려면 다음 단계를 따르십시오.

1. 확장 모델에 추가할 수 있고 빈 스트링으로 변환하는 논리로 뒷받침되는 계산 열을 `null` 추가합니다.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. 기본 열 대신 새 계산 열에 필터를 사용합니다.

개발 환경에서 필터를 평가하려면 다음 X++ 코드를 사용하여 결과를 검증할 수 있습니다. 이 코드를 독립 실행형 프로그램으로 실행합니다. 이중 쓰기 맵에서 이러한 필터를 사용하기 전에 엔터티에 적용할 수 있는 다양한 종류의 필터를 평가하는 데 사용할 수 있습니다. 데이터베이스에 대해 쿼리를 실행하여 불일치를 평가할 수 있습니다.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>재무 및 운영 앱의 데이터는 다음과 동기화되지 않습니다. Dataverse

라이브 동기화 중에 데이터의 일부만 재무 및 운영 앱에서 Dataverse으로 동기화되거나 데이터가 전혀 동기화되지 않는 문제가 발생할 수 있습니다.

> [!NOTE]
> 개발 중에 이 문제를 수정해야 합니다.

문제 해결을 시작하기 전에 다음 전제 조건을 검토하십시오.

+ 사용자 지정 변경 사항이 단일 트랜잭션 범위에 기록되었는지 확인하십시오.
+ 비즈니스 이벤트 및 이중 쓰기 프레임워크는 `doinsert()`, `doUpdate()`, `recordset()` 및 `skipBusinessEvents(true)`가 표시된 작업 또는 기록을 처리하지 않습니다. 코드가 이러한 함수 안에 있으면 이중 쓰기가 트리거되지 않습니다.
+ 매핑된 데이터 소스에 대해 비즈니스 이벤트를 등록해야 합니다. 일부 데이터 원본은 외부 조인을 사용할 수 있으며 재무 및 운영 앱에서 읽기 전용으로 표시될 수 있습니다. 이러한 데이터 소스는 추적되지 않습니다.
+ 매핑된 필드에 수정 사항이 있는 경우에만 변경 사항이 트리거됩니다. 매핑되지 않은 필드 수정은 이중 쓰기를 트리거하지 않습니다.
+ 필터 평가가 유효한 결과를 제공하는지 확인하십시오.

### <a name="troubleshooting-steps"></a>문제 해결 단계

1. 이중 쓰기 관리 페이지에서 필드 매핑을 검토합니다. 필드가 재무 및 운영 앱에서 Dataverse으로 매핑되지 않으면 추적되지 않습니다. 예를 들어 다음 그림에서 **설명** 필드는 Dataverse에서 추적되지만 재무 및 운영 앱에서는 추적되지 않습니다. 재무 및 운영 앱 내에서 해당 필드에 대한 변경 사항은 추적되지 않습니다.

    ![추적 필드.](media/live-sync-troubleshooting-1.png)

2. 비즈니스 이벤트 정의에서 데이터 소스가 추적되는지 여부를 판별하십시오. 예를 들어 다음 그림에서 **DefaultDimensionDAVs** 테이블 및 기본 테이블의 필드는 변경 사항에 대해 추적되지 않습니다. 외부 조인을 사용하고 읽기 전용으로 표시된 데이터 원본은 추적되지 않습니다.

    ![추적되지 않는 필드입니다.](media/live-sync-troubleshooting-2.png)

3. 다음 그림과 같이 매핑된 테이블 필드가 **BUSINESSEVENTSDEFINITION** 테이블에 나타나는지 여부를 결정합니다. 쿼리 결과에서 원하는 필드를 찾지 못하면 이중 쓰기로 트리거되지 않습니다.

    ![테이블의 추적 필드.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>샘플 시나리오

재무 및 운영 앱에서 연락처 기록에 대한 주소 업데이트가 있지만 주소 변경은 Dataverse에 동기화되지 않습니다. 이 시나리오는 **BusinessEventsDefinition** 테이블의 기록에 영향을 받는 테이블과 엔터티의 조합이 없기 때문에 발생합니다. 특히 **LogisticsPostalAddress** 테이블은 **smmContactpersonCDSV** 2Entity 엔터티에 대한 직접 데이터 원본이 아닙니다. **smmContactpersonCDSV** 2Entity 엔터티에는 데이터 소스로 **smmContactPersonV2Entity** 가 있고, 차례로 **smmContactPersonV2Entity** 에는 **LogisticsPostalAddressBaseEntity** 가 데이터 소스로 있습니다. **LogisticsPostalAddress** 테이블은 **LogisticsPostalAddressBaseEntity** 에 대한 데이터 소스입니다.

재무 및 운영 앱에서 수정 중인 테이블이 테이블을 포함하는 엔터티에 분명히 연결되지 않은 경우와 같은 일부 비표준 패턴에서 유사한 상황이 발생할 수 있습니다. 예를 들어 기본 주소 데이터는 **smmContactPersonCDSV2Entity** 엔터티에서 계산됩니다. 이중 쓰기 프레임워크는 기본 테이블에 대한 변경 사항이 엔터티에 다시 매핑되는 방법을 결정하려고 합니다. 일반적으로 이 접근 방식으로 충분합니다. 그러나 경우에 따라 링크가 너무 복잡하여 구체적이어야 합니다. 엔터티에서 관련 테이블의 **RecId** 를 직접 사용할 수 있는지 확인해야 합니다. 이후 테이블의 변경 사항을 모니터링하는 정적 메서드를 추가합니다.

예를 들어 **smmContactPersonCDSV2::Entity()** 메서드를 검토하십시오. **CustCustomerV3entity** 및 **VendVendorV2Entity** 가 이 상황을 처리하도록 수정되었습니다.

문제를 해결하려면 다음 단계를 따르십시오.

1. **PrimaryPostalAddressRecId** 필드를 **smmContactPersonV2Entity** 엔터티에 추가합니다. 내부로 만드십시오.

    ![smmContactPersonV2Entity 엔터티에 필드가 추가되었습니다.](media/Troubleshoot_live_sync_issue_1.png)

2. **smmContactPersonCDSV2Entity** 엔터티에 동일한 필드를 추가합니다.

    ![smmContactPersonCDSV2Entity 엔터티에 필드가 추가되었습니다.](media/Troubleshoot_live_sync_issue_2.png)

3. **smmContactPersonCDSV2Entity** 클래스에 다음 메서드를 추가합니다.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. 데이터베이스를 동기화하고 애플리케이션을 빌드합니다.
5. **smmContactPersonCDSV2Entity** 엔터티에서 생성된 모든 이중 쓰기 맵을 중지합니다.
6. 지도를 시작합니다. **BusinessEventsDefinition** 테이블에서 **refentityname** 값이 **smmContactPersonCDSV2Entity** 와 동일한 행에 대해 **RefTableName** 열을 사용하여 추적을 시작한 새 테이블(이 예시에서는 **LogisticsPostalAddress**)이 표시되어야 합니다.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>여러 기록이 Finance and Operations 앱에서 Dataverse 동일한 배치로 전송되는 기록을 생성할 때 오류가 발생합니다.

모든 거래에 대해 Dataverse 재무 및 운영 앱은 데이터를 일괄적으로 생성하고 일괄적으로 에 보냅니다. 두 개의 기록이 동일한 트랜잭션의 일부로 생성되고 서로 참조하는 경우 Finance and Operations 앱에서 다음 예와 유사한 오류 메시지가 나타날 수 있습니다.

*엔티티 aaa_fundingsources에 데이터를 쓸 수 없습니다. {PC00...} 값이 있는 ebecsfs_contracts를 조회할 수 없습니다. {PC00...} 값이 있는 aaa_fundingsources를 조회할 수 없습니다. 오류 메시지 예외 메시지와 함께 aaa_fundingsources에 대한 쓰기가 실패했습니다. 원격 서버에서 오류를 반환했습니다. (400) 잘못된 요청.*

이 문제를 해결하려면 재무 및 운영 앱에서 엔터티 관계를 만들어 두 엔터티가 서로 관련되어 있고 관련 기록이 동일한 트랜잭션에서 처리됨을 나타내십시오.

## <a name="enable-verbose-logging-of-error-messages"></a>오류 메시지의 자세한 로깅 활성화

재무 및 운영 앱에서 Dataverse 환경과 관련된 오류가 발생할 수 있습니다. 오류 메시지는 메시지의 전체 텍스트 또는 기타 관련 데이터를 포함하지 않을 수 있습니다. 자세한 정보를 얻으려면 재무 및 운영 앱의 모든 프로젝트 구성에서 **DualWriteProjectConfigurationEntity** 엔터티에 있는 **IsDebugMode** 플래그를 설정하여 자세한 로깅을 활성화할 수 있습니다.

1. Excel 추가 기능을 사용하여 **DualWriteProjectConfigurationEntity** 엔터티를 엽니다. 추가 기능을 사용하려면 재무 및 운영 Excel 추가 기능에서 디자인 모드를 활성화하고 **DualWriteProjectConfigurationEntity** 를 워크시트에 추가합니다. 자세한 내용은 [Excel로 엔터티 데이터 보기 및 업데이트](../../office-integration/use-excel-add-in.md)를 참조하십시오.
2. 프로젝트에서 **IsDebugMode** 플래그를 **예** 로 설정합니다.
3. 시나리오를 실행합니다.
4. 자세한 로그는 **DualWriteErrorLog** 테이블에서 사용할 수 있습니다. 테이블 브라우저를 사용하여 데이터를 조회하려면 다음 URL을 사용하십시오. `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. 디버그 모드에서 더 많은 로그를 캡처하려면 [KB 4595434에서 업데이트를 설치하십시오(이중 쓰기 라이브 동기화에서 전파되는 빈 값 수정)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>고객 또는 연락처의 주소를 추가할 때 오류가 발생했습니다.

재무 및 운영 앱 또는 Dataverse에서 고객 또는 연락처의 주소를 추가하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*엔터티 msdyn_partypostaladdresses에 데이터를 쓸 수 없습니다. DirPartyPostalAddressLocationCDSEntity에 쓰기 실패 오류 메시지와 함께 요청 실패 상태 코드 BadRequest 및 CDS 오류 코드: 0x80040265 응답 메시지: 플러그인에서 오류가 발생했습니다. 속성 값이 위치 ID인 기록이 이미 존재합니다. 엔티티 키 위치 ID 키는 이 속성 세트에 고유한 값을 포함해야 합니다. 고유한 값을 선택하고 다시 시도하십시오.*

이 문제를 해결하려면 이중 쓰기 오케스트레이션 패키지 버전(2.2.2.60)을 설치하여 **주소** 테이블의 키가 다음 표와 같이 정의되도록 합니다.

| 속성, | 값 |
|---|---|
| 표시 이름 | **위치 키** |
| 이름 | **msdyn_locationkey** |
| 필드 | **msdyn_locationid**, **parentid** |
| 상태 | **활성** |
| 시스템 작업 | 빈 템플릿 |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>에 고객을 추가할 때 오류가 발생했습니다. Dataverse

Dataverse에서 고객을 추가하려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*RecordError0:'알 수 없는 예외가 있는 고객 V3 엔터티에 대한 쓰기 실패 - 당사자 유형 '조직'에 대한 당사자 기록을 찾을 수 없습니다.'}.*

Dataverse에서 고객이 생성되면 새로운 당사자 번호가 생성됩니다. 고객 기록이 당사자와 함께 재무 및 운영 앱에 동기화되지만 당사자 번호가 다른 고객 기록이 이미 있는 경우 오류 메시지가 표시됩니다.

문제를 해결하려면 파티 조회를 통해 고객을 찾으십시오. 고객이 없으면 새 고객 기록을 만듭니다. 고객이 존재하는 경우 기존 당사자를 사용하여 새 고객 기록을 생성합니다.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>새 고객, 공급 업체 또는 연락처를 생성할 때 오류가 발생했습니다. Dataverse

Dataverse에서 새 고객, 공급 업체 또는 연락처를 만들려고 하면 다음 오류 메시지가 나타날 수 있습니다.

*당사자 유형을 'DirOrganization'에서 'DirPerson'으로 업데이트할 수 없습니다. 기존 당사자를 삭제한 후 새 유형을 삽입하는 대신 수행해야 합니다.*

Dataverse에는 **msdyn_party** 테이블에 번호 시퀀스가 있습니다. Dataverse에서 계정이 생성되면 새 당사자가 생성됩니다(예: **조직** 유형의 **당사자-001**). 이 데이터는 재무 및 운영 앱으로 전송됩니다. 환경이 재설정되거나 Dataverse 재무 및 운영 환경이 다른 환경에 연결된 경우 Dataverse에서 새 연락처 기록이 생성되면 **Party-001** 로 시작하는 Dataverse 새 당사자 값이 생성됩니다. 이때 생성되는 당사자 기록은 **Person** 유형의 **Party-001** 이 됩니다. 이 데이터가 동기화되면 **조직** 유형의 당사자 기록 **Party-001** 이 이미 존재하기 때문에 재무 및 운영 앱에 앞의 오류 메시지가 표시됩니다.

이 문제를 해결하려면 **msdyn_party** 테이블의 **msdyn_partynumber** 필드에 대한 Dataverse 자동 번호 시퀀스를 다른 자동 번호 시퀀스로 변경합니다.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>고객 또는 연락처 매핑의 성능 문제

**getEntityDataSourceToFieldMapping** 메서드(**CustCustomerV3Entity** 엔터티) 및 **getEntityDataSourceToFieldMapping** 메서드(**smmContactPersonCDSV2Entity** 엔터티)를 사용자 지정하여 고객 및 연락처에 대한 실시간 동기화 성능을 약간 향상시킬 수 있습니다. 이러한 사용자 지정은 **BusinessEventsDefinition** 테이블의 기록 수를 줄입니다. 기록 수의 감소는 차례로 발생하는 이벤트 수를 줄입니다.

**CustCustomerV3Entity** 엔터티의 **getEntityDataSourceToFieldMapping** 메서드는 고객의 전자 주소 또는 우편 주소 업데이트가 비즈니스 이벤트를 트리거하도록 하여 업데이트된 데이터가 Dataverse로 전송되도록 합니다. 모든 필드를 사용하지 않고 이중 쓰기의 정보가 필요하지 않은 경우 메서드에서 적절한 줄을 주석 처리합니다. 이 메서드에 추가된 모든 추적 필드와 테이블은 추적 테이블과 추적 엔터티의 조합에 대해 **BusinessEventsDefinition** 테이블에 기록을 추가합니다.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

유사한 방식으로 **smmContactPersonCDSV2Entity** 엔터티의 **getEntityDataSourceToFieldMapping** 메서드는 연락처의 전자 주소 또는 우편 주소 업데이트가 비즈니스 이벤트를 트리거하도록 하여 업데이트된 데이터가 Dataverse로 전송되도록 합니다. 메서드에서 사용하지 않는 필드에 대한 줄을 주석 처리할 수 있습니다.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

방법을 업데이트한 후 다음 단계를 따르십시오.

1. 데이터베이스를 동기화하고 애플리케이션을 빌드합니다.
2. **smmContactPersonCDSV2Entity** 및 **CustCustomerV3Entity** 엔터티에서 모든 이중 쓰기 맵을 중지합니다.
3. 지도를 시작합니다. **smmContactPersonCDSV2Entity** 및 **CustCustomerV3Entity** 엔터티와 **BusinessEventsDefinition** 테이블에 더 적은 수의 기록이 표시되어야 하며 성능이 약간 향상될 수 있습니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
