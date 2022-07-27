---
title: Dataverse 가상 테이블 쿼리 최적화
description: Dataverse 가상 테이블 쿼리의 성능 최적화 및 문제 해결
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1857d2e35e369bcd0c8f02a059a307f31da8b3b9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452356"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Dataverse 가상 테이블 쿼리 최적화


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>문제

### <a name="overview"></a>개요

Dataverse 가상 테이블을 사용하여 Dynamics 365 Human Resources와의 통합과 기타 데이터 연결을 개발할 때 가상 테이블에 대한 쿼리에 성능 문제가 발생할 수 있습니다. 다양한 클라이언트 또는 인터페이스에서 쿼리 실행이 느릴 수 있습니다. 예를 들어 다음과 같은 상황에서 문제가 발생할 수 있습니다.

- Dataverse 웹 API를 통해 가상 테이블을 쿼리할 때
- 가상 테이블에 대해 Power App을 만들 때
- 가상 테이블에서 Power BI 보고서를 구축할 때

이러한 모든 인터페이스는 성능 문제를 드러낼 가능성이 있습니다.

Human Resources용 Dataverse 가상 테이블이 성능이 저하되는 원인 중 하나는 테이블의 [탐색 속성](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties)과 관련된 가상 테이블의 외부 키 열입니다. 가상 테이블에 대한 탐색 속성이 생성되면 관련 가상 테이블의 키 열에 대한 키 값을 나타내는 외래 키 열이 자동으로 테이블에 추가됩니다. 예를 들어 **mshr_fk_person_id_value** 열은 **mshr_dirpersonentity** 엔터티의 외래 키 속성을 가진 **mshr_hcmworkerbaseentity** 엔터티에 추가됩니다. 이러한 외래 키 열의 값이 테이블에서 유지되는 방식 때문에 값을 가져오면 가상 테이블에 대한 쿼리 성능에 부정적인 영향을 미칠 수 있습니다.

### <a name="potential-symptoms"></a>잠재적인 증상

이 영향을 볼 수 있는 예로 작업자(**mshr_hcmworkerentity**) 또는 기본 작업자(**mshr_hcmworkerbaseentity**) 엔터티에 대한 쿼리가 있습니다. 몇 가지 다른 방식으로 성능 문제가 나타나는 것을 볼 수 있습니다.

- **느린 쿼리 실행**: 가상 테이블에 대한 쿼리가 예상한 결과를 반환하지만 쿼리 실행을 완료하는 데 예상보다 오래 걸립니다.
- **쿼리 시간 초과**: 쿼리가 시간 초과되어 "Finance 및 Operations를 호출하기 위해 토큰을 얻었지만 Finance 및 Operations에서 InternalServerError 유형의 오류를 반환했습니다." 오류를 반환할 수 있습니다.
- **예기치 않은 오류**: 쿼리가 "예기치 않은 오류가 발생했습니다."라는 메시지와 함께 오류 유형 400을 반환할 수 있습니다.

  ![HcmWorkerBaseEntity의 오류 유형 400.](./media/HcmWorkerBaseEntityErrorType400.png)

- **제한**: 쿼리가 서버 리소스를 과도하게 사용하여 제한될 수 있습니다. 이 경우 쿼리가 "Finance 및 Operations를 호출하기 위해 토큰을 얻었지만 Finance 및 Operations에서 429 유형의 오류를 반환했습니다." 오류를 반환합니다. Human Resources에서 제한에 대한 자세한 내용은 [제한 FAQ](./hr-admin-integration-throttling-faq.md)를 참조하세요.

  ![HcmWorkerBaseEntity의 오류 유형 429.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>해결

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>데이터 쿼리에 포함된 열 수 제한

가상 테이블의 경우 쿼리 성능을 향상하는 가장 좋은 한 방법은 쿼리에서 선택한 열의 수를 제한하는 것입니다. 쿼리 성능을 최적화하기 위한 일반적인 지침은 쿼리에 반환되는 열을 필요한 속성으로만 제한하는 것입니다. 특히 가상 테이블의 외래 키 열의 경우 더욱 그렇습니다. 통합 또는 보고서에 대한 외래 키 열의 값이 필요하지 않으면 외래 키 열을 제외하고 필요한 열만 선택하도록 쿼리를 구성하세요.

#### <a name="selecting-columns-in-an-odata-query"></a>OData 쿼리에서 열 선택

Dataverse 웹 API를 통해 가상 테이블을 쿼리할 때 **$select** 시스템 쿼리 옵션을 사용하여 쿼리에 포함되는 열의 수를 제한하고 결과가 반환되어야 하는 열을 정의할 수 있습니다. 성능을 최대화하려면 쿼리에서 외래 키 열(**__mshr_FK__** 접두사가 있는 열)을 제외합니다.

예를 들어 **mshr_hcmworkerbaseentity** 엔터티에 대한 다음 쿼리는 외래 키 값을 제외하고 **$select** 쿼리 옵션 절에 포함된 열만 포함합니다. 이렇게 하면 모든 테이블 열을 포함하는 쿼리보다 성능이 크게 향상됩니다.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

선택하는 열 수를 제한하는 권장 사항은 **$expand** 쿼리 옵션을 사용하여 탐색 속성으로 관련 가상 테이블로 쿼리를 확장하는 경우에도 적용됩니다. 예를 들어 다음 쿼리에는 **mshr_dirpersonentity** 엔터티의 확장된 열이 있는 **mshr_hcmworkerbaseentity** 엔터티의 열이 포함됩니다. **$select** 쿼리 옵션은 **$expand** 쿼리 옵션 절에도 포함되어 있습니다.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

**$expand** 쿼리 옵션 절에서 **$select** 쿼리 옵션과 함께 데이터를 검색하는 이 방법을 사용할 때 일반적으로 엔터티 간의 탐색 속성이 다대일 관계일 때 성능이 더 크게 향상됩니다. 일대다 관계를 확장할 때는 쿼리 실행 시간이 동일하게 감소하지 않을 수 있습니다. Dataverse 가상 테이블의 관계 정의에 관한 자세한 내용은 [테이블 관계](/powerapps/maker/data-platform/create-edit-entity-relationships)를 참조하세요.

Dataverse 웹 API에서 **$select** 및 **$expand** 시스템 쿼리 옵션을 사용하는 데 대한 자세한 내용은 [쿼리로 관련 엔터티 레코드 검색](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query)을 참조하세요.

#### <a name="selecting-columns-in-power-bi"></a>Power BI의 열 선택

Dataverse 가상 테이블에 대해 Power BI 보고서를 작성할 때 앞서 언급한 성능 저하 징후가 발생하는 경우 보고서의 테이블에서 선택한 열에서 외래 키 열을 제외하여 성능을 향상할 수 있습니다. 예를 들어 Power BI Desktop을 사용하여 **mshr_hcmworkerbaseentity** 엔터티에 대한 보고서를 만드는 경우 다음 단계를 사용하여 보고서 쿼리에 포함할 열을 선택할 수 있습니다.

1. Power BI Desktop의 작업 리본에 있는 **데이터 가져오기** 드롭다운 목록에서 **더 보기...** 를 선택합니다.
2. **데이터 가져오기** 창에서 검색 상자에 **Common Data Service** 를 입력하고 **Common Data Service** 커넥터를 선택한 다음 **연결** 을 선택합니다.
3. Common Data Service 창의 **서버 Url** 필드에 Dataverse 환경의 조직 URI를 입력하고 **확인** 을 선택합니다.
  
   ![Dataverse 환경의 URI를 입력합니다.](./media/PowerBIDataverseURLSetup.png)
  
4. 탐색 창에서 **엔터티** 노드를 확장합니다.
5. 검색 상자에 **mshr_hcmworkerbaseentity** 를 입력하고 엔터티를 선택합니다.
6. **데이터 변환** 을 선택합니다.
7. Power Query 편집기 창에서 **고급 편집기** 를 선택합니다.
8. **고급 편집기** 창에서 쿼리를 아래와 같이 업데이트하고 필요에 따라 배열에 열을 추가하거나 제거합니다.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Power Query 편집기의 고급 편집기에서 쿼리를 업데이트합니다.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. **완료** 를 선택합니다.

   > [!NOTE]
   > 업데이트하기 전에 이전에 쿼리에서 유형 429 오류를 수신한 경우 쿼리를 완료하려면 쿼리를 새로 고치기 전에 재시도 기간을 기다려야 할 수 있습니다.

10. Power Query 편집기 작업 리본에서 **닫기 및 적용** 을 클릭합니다.

이제 가상 테이블에서 선택한 열에 대해 Power BI 보고서 구축을 시작할 수 있습니다.

#### <a name="selecting-columns-in-power-apps"></a>Power Apps의 열 선택

Dataverse 웹 API 쿼리 및 Power BI와 비슷하게 앱에서 관련 테이블의 열을 제외하여 Dataverse 가상 테이블 기반의 Power Apps 쿼리 성능을 개선할 수 있습니다. 페이지에 관련 테이블의 열이 포함된 경우 데이터를 가져오기 위해 구성된 요청 URL에 관련 테이블의 외래 키 속성이 포함됩니다. 이는 위의 [OData 쿼리에서 열 선택](#selecting-columns-in-power-apps) 예와 같이 추가 데이터 조회를 일으켜 성능을 떨어뜨립니다.

이 문제를 해결하려면 관련 테이블의 데이터 필드가 Power Apps의 데이터 형식에 포함되지 않았는지 확인할 수 있습니다.

1. 트리 보기 창에서 화면의 데이터 양식을 선택합니다.
2. **속성** 창에서 **필드** 속성의 **편집** 을 선택합니다.
3. **데이터** 창에서 선택한 필드가 데이터 원본의 가상 테이블 필드가 아닌지 확인합니다.

예를 들어 앱의 페이지에 포함된 데이터 필드 중 하나가 **ThisItem.Worker.Name** 과 같은 다른 테이블을 참조할 때 **Worker** 가 관련 테이블이면 데이터를 가져올 때 성능이 저하될 가능성이 있습니다.

[Power Apps 모니터](/powerapps/maker/monitor-overview)를 사용하여 Power Apps에 대한 데이터를 가져오는 데 필요한 열만 쿼리에 포함되도록 할 수 있습니다. getRows 작업을 위해 구성된 URL을 보고 앱에 대해 선택된 열이 데이터 검색에 최적인지 확인할 수 있습니다.

![Power Apps 모니터를 사용하여 getData 작업을 분석합니다.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>데이터 쿼리 필터링

쿼리 실행 성능을 향상하는 또 다른 방법은 쿼리 결과에 반환되는 레코드 수를 제한하는 것입니다. 이를 위해 필요한 레코드만 수신하도록 결과를 필터링할 수 있습니다.

쿼리 데이터 필터링에 대한 자세한 내용은 [결과 필터링](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results)을 참조하세요.

### <a name="limiting-the-page-size-of-the-query"></a>쿼리의 페이지 크기 제한

대규모 데이터 세트로 작업하는 경우 데이터 쿼리에 `odata.maxpagesize` 기본 설정 헤더를 추가하여 쿼리 결과를 여러 페이지로 나눌 수 있습니다.

페이징에 대한 자세한 내용은 [페이지에 반환할 엔터티 수 지정](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Dataverse 가상 테이블 구성](hr-admin-integration-common-data-service-virtual-entities.md)
- [Human Resources 가상 테이블 FAQ](hr-admin-virtual-entity-faq.md)
- [제한 FAQ](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
