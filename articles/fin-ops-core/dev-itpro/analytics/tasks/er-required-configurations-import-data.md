---
title: ER 외부 파일에서 데이터를 가져오기 위해 필요한 구성 생성
description: 이 항목에서는 외부 파일에서 Microsoft Dynamics 365 Finance 앱으로 데이터를 가져오기 위해 전자 보고 구성을 설계하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eaa35baae8e030d8a8b7ce903554c4876c874b48cfd72d6ac278cf4c0e8a6e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460842"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER 외부 파일에서 데이터를 가져오기 위해 필요한 구성 생성

[!include [banner](../../includes/banner.md)]

다음 단계는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 외부 파일에서 애플리케이션으로 데이터를 가져오기 위해 전자 보고(ER) 구성을 설계할 수 있는 방법을 설명합니다. 이 예에서는 샘플 회사인 Litware, Inc.에 필요한 ER 구성을 생성합니다. 이 단계를 완료하려면 먼저 작업 가이드 "ER 구성 공급자 생성 및 활성으로 표시"의 단계를 완료해야 합니다. 이러한 단계는 USMF 데이터 세트를 사용하여 완료할 수 있습니다. 다음 파일을 다운로드하여 로컬에 저장합니다. 

| 콘텐츠 설명                       | 파일 이름                                     |
|-------------------------------------------|-----------------------------------------------|
| ER 데이터 모델 구성 - 1099 | [1099model,xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)                  |
| ER 형식 구성 - 1099    | [1099format.xml](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)                  |
| XML 형식의 수신 문서 샘플                          | [1099entries.xml](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)        |
| 들어오는 문서의 데이터를 관리하기 위한 통합 문서 샘플                          | [1099entries.xlsx](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx) |

ER은 비즈니스 사용자에게 외부 데이터 파일을 .XML 또는 .TXT 형식의 테이블로 가져오는 프로세스를 구성할 수 있는 기능을 제공합니다. 먼저 추상 데이터 모델 및 ER 데이터 모델 구성은 가져오는 데이터를 나타내도록 설계되어야 합니다. 다음으로 가져올 파일의 구조와 파일에서 추상 데이터 모델로 데이터를 이식하는 데 사용할 방법을 정의해야 합니다. 설계된 데이터 모델에 매핑되는 ER 형식 구성은 해당 추상 데이터 모델에 대해 생성되어야 합니다. 그런 다음 가져온 데이터가 추상 데이터 모델 데이터로 지속되는 방법과 테이블 업데이트에 사용되는 방법을 설명하는 매핑으로 데이터 모델 구성을 확장해야 합니다.  ER 데이터 모델 구성에는 애플리케이션의 대상에 대한 데이터 모델의 바인딩을 설명하는 새 모델 매핑이 추가되어야 합니다.  

다음 시나리오는 ER 데이터 가져오기 기능을 보여줍니다. 여기에는 외부에서 추적한 다음 나중에 1099에 대한 공급업체의 결제로 보고되도록 가져온 공급업체 거래가 포함됩니다.   

## <a name="add-a-new-er-model-configuration"></a>새 ER 모델 구성 추가
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.

    샘플 회사 'Litware, Inc.'의 구성 공급자를 확인합니다. 사용 가능하고 활성으로 표시됩니다. 이 구성 공급자가 보이지 않으면 "구성 공급자를 만들고 활성으로 표시" 절차의 단계를 완료해야 합니다.   

2. 보고 구성을 클릭합니다.

    데이터 가져오기를 지원하기 위해 새 모델을 만드는 대신 이전에 다운로드한 1099model.xml 파일을 로드합니다. 이 파일에는 공급 업체 트랜잭션의 사용자 지정 데이터 모델이 포함되어 있습니다. 이 데이터 모델은 AOT 데이터 엔티티에 있는 데이터 구성 요소에 매핑됩니다.   

3. 교환을 클릭합니다.
4. XML 파일에서 로드를 클릭합니다.

    찾아보기를 클릭하고 이전에 다운로드한 1099model.xml 파일로 이동합니다.  

5. 확인을 클릭합니다.
6. 트리에서 '1099 결제 모델'을 선택합니다.

## <a name="review-data-model-settings"></a>데이터 모델 설정 검토
1. 디자이너를 클릭합니다.

    이 모델은 비즈니스 관점에서 공급업체의 트랜잭션을 나타내도록 설계되었으며 구현과 별개입니다.   

2. 트리에서 '1099-MISC'를 확장합니다.
3. 트리에서 '1099-MISC\Transactions'를 선택합니다.
4. 트리에서 '1099-MISC\Transactions'를 확장합니다.

    이 모델의 트랜잭션 요소는 개별 트랜잭션을 나타냅니다. 하위 요소는 각 거래에 대해 공급업체 계정 및 거래 날짜와 같은 필수 세부 정보를 지정하는 데 사용됩니다.   

5. 페이지를 닫습니다.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>데이터 가져오기를 지원하는 새 ER 형식 구성 추가
이 하위 작업의 단계는 외부 파일에서 데이터 가져오기를 관리하기 위해 새 형식 구성을 만드는 방법을 보여줍니다.   
1. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.
2. 새로 만들기 필드에 '데이터 모델 1099 지급 모델 기반 형식'을 입력합니다.
3. 데이터 가져오기 지원 필드에서 예를 선택합니다.
4. 이 페이지를 닫으려면 ESC 키를 누르십시오.

    데이터 가져오기를 지원하기 위해 새 형식을 만드는 대신 이전에 다운로드한 1099format.xml 파일을 로드합니다. 이 파일에는 가져오는 파일의 정의된 구조와 공급업체 트랜잭션의 사용자 정의 데이터 모델에 대한 구조 매핑이 포함되어 있습니다.   
5. 교환을 클릭합니다.
6. XML 파일에서 로드를 클릭합니다.
    찾아보기를 클릭하고 이전에 다운로드한 1099format.xml 파일로 이동합니다.  
7. 확인을 클릭합니다.
8. 트리에서 '1099 결제 모델'을 확장합니다.
9. 트리에서 '1099 지불 모델\공급업체 트랜잭션 가져오기 형식'을 선택합니다.

## <a name="review-format-settings"></a>형식 설정 검토
1. 디자이너를 클릭합니다.
2. '세부정보 표시'를 켭니다.
3. 펼치기/접기를 클릭합니다.
4. 펼치기/접기를 클릭합니다.

    설계된 형식은 외부 파일의 예상 구조를 나타냅니다. 이 파일은 XML 형식이어야 하며 결제 루트 요소가 있어야 합니다. 각 공급업체의 트랜잭션은 0대다 다중성을 갖는 것으로 정의된 트랜잭션 요소로 표시됩니다. 이것은 들어오는 파일이 0에서 여러 트랜잭션을 포함할 수 있음을 의미합니다. 'transaction' 요소의 중첩 요소는 단일 트랜잭션의 속성을 나타냅니다. 국가를 제외한 모든 속성은 필수로 표시되어 가져오기 파일에 포함해야 함을 의미합니다.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>데이터 모델에 대한 형식 매핑 설정 검토
1. 모델링할 형식 매핑을 클릭합니다.

    '가져오기 공급업체' 트랜잭션' 매핑에는 들어오는 XML 파일에서 1099-MISC 정의를 선택하여 정의된 사용자 지정 데이터 모델의 선택된 부분으로의 데이터 전송 규칙이 포함됩니다.  

2. 디자이너를 클릭합니다.
3. '세부정보 표시'를 켭니다.
4. 트리에서 '형식: 레코드'를 확장합니다.
5. 트리에서 '형식: 레코드'를 선택합니다.

    디자인된 형식은 데이터 소스 구성 요소로 여기에 표시됩니다.  

6. 트리에서 `format: Record\*settlement: XML Element 1..1 (settlement): Record`를 확장합니다.
7. 트리에서 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list`를 확장합니다.
8. 트리에서 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`를 확장합니다.
9. 트리에서 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record`를 확장합니다.
10. 트리에서 `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`를 선택합니다.

    필수 및 선택적 형식 요소의 표시는 미리 정의된 '형식' 데이터 소스 구성요소에서 다릅니다.  
11. 트리에서 '트랜잭션: 레코드 목록= format.settlement.'$enumerated''를 확장합니다.

    가져온 파일의 구조를 정의하는 형식의 요소는 사용자 지정 데이터 모델의 요소에 바인딩됩니다. 이러한 바인딩을 기반으로 가져온 XML 파일의 내용은 런타임 시 기존 데이터 모델에 저장됩니다. 국가 요소의 바인딩에 주의하세요. 이러한 요소가 없는 수신 파일의 모든 트랜잭션 요소의 경우 기본 국가 코드 'USA'가 데이터 모델에 채워집니다.  

12. 유효성 검사 탭을 클릭합니다.

    이 형식 매핑에는 비즈니스 관점에서 가져온 데이터의 정확성을 검증하기 위한 사용자 지정 논리가 포함될 수 있습니다. 예를 들어, 설정에 따라 정의된 국가 코드가 없는 가져오기 파일의 모든 트랜잭션에 대해 사용자에게 해당 사례를 알리고 트랜잭션의 시퀀스 번호를 나타내는 경고 메시지가 Infolog에 생성됩니다.  

13. 페이지를 닫습니다.

## <a name="run-the-format-mapping-to-the-data-model"></a>데이터 모델에 대한 형식 매핑 실행
테스트 목적으로 이 형식 매핑을 실행합니다. 이전에 다운로드한 1099entries.xml 파일을 사용합니다. 공급업체 트랜잭션을 관리하는 데 사용되는 1099entries.xlsx 통합 문서에서 이 파일을 내보낼 수 있습니다. 생성된 출력은 선택한 XML 파일에서 가져오고 실제 가져오기 시 사용자 지정 데이터 모델을 채웁니다.  

1. 실행을 클릭합니다.

    찾아보기를 클릭하고 이전에 다운로드한 1099entries.xml 파일로 이동합니다.  

2. 확인을 클릭합니다.

    가져온 파일에서 거래에 대한 국가 코드 누락에 대한 경고 메시지를 확인합니다.  
    
    선택한 파일에서 가져와 데이터 모델로 이식된 데이터를 나타내는 XML 형식의 출력을 검토합니다.   

3. 페이지를 닫습니다.
4. 페이지를 닫습니다.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>대상에 대한 모델 매핑 설정 검토
1. 트리에서 '1099 결제 모델'을 선택합니다.
2. 디자이너를 클릭합니다.
3. 데이터 소스에 모델 매핑을 클릭합니다.

    1099 수동 트랜잭션 가져오기 매핑이 대상 방향 유형으로 정의되었습니다. 이는 데이터 가져오기를 지원하기 위해 입력되었으며 가져온 외부 파일과 추상 데이터 모델 데이터로 지속되는 방법을 정의하는 규칙 설정을 포함하여 애플리케이션에서 테이블을 업데이트하는 데 사용됨을 의미합니다.  

4. 디자이너를 클릭합니다.
5. 트리에서 '모델: 데이터 모델 1099 지불 모델'을 확장합니다.
6. 트리에서 '모델: 데이터 모델 1099 지불 모델\트랜잭션: 레코드 목록'을 확장합니다.

    디자인된 모델은 여기에 데이터 소스 요소로 표시됩니다. 런타임 시 외부 파일에서 가져온 데이터가 포함됩니다. 수입 거래 벤더 계정이 시스템에서 사용 가능한지 여부, 수입 국가 및 주 코드의 조합이 존재하는지 여부 등을 포함하여 가져온 데이터가 현재 애플리케이션의 데이터와 호환되는지 확인하기 위해 여러 테이블이 데이터 소스 요소로 추가되었습니다. .  

7. 트리에서 'model: Data model 1099 Payments model\Transactions: Record list\$failed: Calculated field = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean'을 선택합니다.
8. 편집을 클릭합니다.
9. 수식 편집을 클릭합니다.

    가져온 단일 트랜잭션에 대해 하나 이상의 유효성 검사가 실패하면 이 트랜잭션은 데이터 소스 속성 '$failed'에 의해 실패한 것으로 표시됩니다.  

10. 페이지를 닫습니다.
11. 취소를 클릭합니다.
12. 트리에서 'tax1099trans: Table 'VendSettlementTax1099' records= model.Validated'를 선택합니다.
13. 대상 편집을 클릭합니다.

    가져온 데이터가 응용 프로그램 테이블을 업데이트하는 방법을 지정하기 위해 이 ER 대상이 추가되었습니다. 이 경우 데이터 테이블 VendSettlementTax1099가 선택되었습니다. 레코드 작업 삽입이 선택되었으므로 가져온 트랜잭션이 VendSettlementTax1099 테이블에 삽입됩니다. 단일 모델 매핑에는 여러 대상이 포함될 수 있습니다. 즉, 가져온 데이터를 사용하여 여러 애플리케이션의 테이블을 한 번에 업데이트할 수 있습니다. 테이블, 보기 및 데이터 엔터티를 ER 대상으로 사용할 수 있습니다.   

    매핑이 이 작업을 위해 특별히 설계된 응용 프로그램의 한 지점(예: 버튼 또는 메뉴 항목)에서 호출되는 경우 ER 대상이 통합 지점으로 표시되어야 합니다. 이 예에서 이것은 ERTableDestination#VendSettlementTax1099 포인트입니다.  

14. 취소를 클릭합니다.
15. 모두 표시를 클릭합니다.
16. 매핑된 항목만 표시를 클릭합니다.
17. 트리에서 'tax1099trans: Table 'VendSettlementTax1099' records= model.Validated'를 확장합니다.

    검증된 트랜잭션만 포함하는 데이터 소스 요소는 생성된 대상에 바인딩됩니다. 가져온 트랜잭션을 필터링하여 애플리케이션 데이터와 호환되지 않는 트랜잭션을 건너뛸 수 있습니다.  

18. 트리에서 'failed: Table 'VendSettlementTax1099Entity' records= model.Failed'를 선택합니다.
19. 유효성 검사 탭을 클릭합니다.

    이 모델 매핑에는 기존 애플리케이션 데이터에서 가져온 데이터의 정확성을 검증하기 위한 사용자 정의 논리가 포함될 수 있습니다. 예를 들어, 현재 설정에 따라 시스템에 없는 공급업체 계정을 사용하는 가져온 파일의 모든 트랜잭션에 대해 사용자에게 알리고 잘못된 공급업체 계정 코드를 나타내는 경고 메시지가 생성됩니다.  

    사후 유효성 검사 작업 옵션을 각 유효성 검사에 사용하여 가져오기 프로세스를 계속 또는 중지해야 하는지 여부와 이미 수행된 삽입/업데이트를 유지하거나 롤백할 수 있는지 여부를 지정할 수 있습니다.  

20. 매핑된 항목만 표시를 클릭합니다.
21. 모두 표시를 클릭합니다.
22. 페이지를 닫습니다.

    이 모델 매핑을 실행하여 설계된 형식 및 모델 매핑을 테스트합니다. 1099entries.xml 파일을 사용합니다. 선택한 파일의 데이터를 시스템으로 가져옵니다.  

23. 실행을 클릭합니다.

    대화 상자에는 가져온 파일을 구문 분석한 다음 데이터를 데이터 모델로 이식하는 데 사용해야 하는 형식 매핑에 대한 추가 질문이 포함되어 있지 않습니다. 이는 현재 데이터 가져오기를 지원하도록 설계된 것으로 표시된 이 모델을 사용하는 형식이 하나만 있기 때문입니다.  
    
    가져온 거래를 이미 수동으로 입력했거나 가져왔을 수 있는 다른 거래와 구별하기 위해 바우처 ID를 정의합니다.  

24. 바우처 ID 입력 필드에 'IMPORT-001'을 입력합니다.

    '1099entries.xml' 파일을 검색합니다.  

25. 확인을 클릭합니다.

    생성된 경고 목록은 잘못된 공급업체 계정, 잘못된 세금 1099 상자 코드, 누락된 국가 코드 등에 대한 정보를 제공합니다. 이 경고 목록을 실행 XML 파일에 포함된 내용과 비교합니다.  

26. 페이지를 닫습니다.
27. 페이지를 닫습니다.
28. 페이지를 닫습니다.
29. 페이지를 닫습니다.
30. 지급 계정 > 정기 작업 > 세금 1099 > 1099에 대한 공급업체 정산으로 이동합니다.

    이 양식은 가져온 거래를 기반으로 생성된 Tax1099Summary 테이블의 누적 거래를 보여줍니다.  

31. 시작 날짜 필드에서 날짜를 '2000-01-01'로 설정합니다.
32. 수동 1099 트랜잭션을 클릭합니다.

    이 양식에는 수동으로 추가한 트랜잭션 목록과 방금 가져온 트랜잭션 목록이 포함되어 있습니다.  

33. 상품권 열 필터를 엽니다.
34. "begins with" 필터 연산자를 사용하여 "Voucher" 필드에 "IMPORT-001"의 필터 값을 입력합니다.

## <a name="review-the-relationship-between-model-and-format-mappings"></a>모델 매핑과 형식 매핑 간의 관계 검토
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
4. 보고 구성을 클릭합니다.
5. 트리에서 '1099 결제 모델'을 선택합니다.

    동일한 데이터를 .TXT 파일 형식으로 가져오는 것을 지원하려고 한다고 가정합니다.   

6. 구성 만들기를 클릭하여 대화 상자를 엽니다. 
7. 새로 만들기 필드에 '데이터 모델 1099 지급 모델 기반 형식'을 입력합니다.
8. 이름 필드에 'TXT 파일에서 데이터 가져오기'를 입력합니다.
9. 데이터 가져오기 지원 필드에서 예를 선택합니다.
10. 구성 만들기를 클릭합니다.
11. 디자이너를 클릭합니다.
12. 모델링할 형식 매핑을 클릭합니다.
13. 새로 만들기를 클릭합니다.
14. 정의 필드에 값을 입력하거나 선택합니다.

    '1099-MISC' 옵션을 선택합니다.  

15. 이름 필드에 'TXT 파일에서 데이터 가져오기'를 입력합니다.
16. 설명 필드에 'TXT 파일에서 데이터 가져오기'를 입력합니다.
17. 저장을 클릭합니다.
18. 페이지를 닫습니다.
19. 페이지를 닫습니다.
20. 편집을 클릭합니다.

    핫픽스 "KB 4012871 다른 버전의 Dynamics 365 Finance에 배포하기 위한 여러 종류의 전제 조건을 지정할 수 있는 별도의 구성에서 GER 모델 매핑 지원"([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871))을 설치한 경우 입력한 형식 구성에 대해 다음 단계 "'모델 매핑에 대한 기본값' 플래그 켜기"를 실행합니다. 그렇지 않으면 다음 단계를 건너뜁니다.  

21. 모델 매핑의 기본값 필드에서 예를 선택합니다.
22. 트리에서 '1099 결제 모델'을 선택합니다.
23. 디자이너를 클릭합니다.
24. 데이터 소스에 모델 매핑을 클릭합니다.
25. 실행을 클릭합니다.

    핫픽스 KB 4012871 다른 버전의 에 배포하기 위한 여러 종류의 전제 조건을 지정할 수 있는 별도의 구성에서 GER 모델 매핑 지원([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871))을 설치한 경우 조회 필드에서 선호하는 모델 매핑을 선택합니다. 아직 핫픽스를 설치하지 않은 경우 기본 형식 구성의 정의에 따라 매핑이 이미 선택되었으므로 다음 단계로 건너뜁니다.  
    
    핫픽스 KB 4012871를 설치하지 않은 경우 대화 상자에 가져오는 파일을 구문 분석하는 데 사용되는 추가 모델 매핑 질문이 포함되어 있습니다. 그런 다음 데이터는 대화 상자에서 데이터 모델로 이식됩니다. 현재 가져오려는 파일 유형에 따라 사용해야 하는 형식 매핑을 선택할 수 있습니다.  
    
    작업을 위해 특별히 설계된 응용 프로그램의 한 지점에서 이 모델 매핑을 호출하려면 ER 대상 및 형식 매핑이 통합의 일부로 표시되어야 합니다.  

26. 취소를 클릭합니다.
27. 페이지를 닫습니다.
28. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
