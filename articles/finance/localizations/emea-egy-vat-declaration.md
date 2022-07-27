---
title: 이집트 VAT 신고
description: 이 항목에서는 이집트에 대한 VAT 신고 양식을 구성하고 생성하는 방법을 설명합니다.
author: sndray
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a67c6e00b94d49b3eb279416407f603923e53b2e
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450952"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>이집트에 대한 VAT 신고서(EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

이 항목에서는 이집트의 법인을 위한 VAT 환급 양식과 판매 및 구매 장부를 설정 및 생성하는 방법에 대해 설명합니다.

이집트 VAT 환급 양식은 총 매출 VAT 세액, 회수 가능한 총 매입 VAT 세액 및 관련 VAT 세액 부채를 요약한 공식 문서입니다. 이 양식은 모든 유형의 납세자에게 사용되며 세무 당국 포털을 통해 수동으로 작성해야 합니다. 부가가치세 신고 양식은 일반적으로 부가가치세 신고서라고 합니다.

Dynamics 365 Finance의 VAT 신고서에는 다음 보고서가 포함됩니다.

- VAT 환급 양식 번호 10은 법률에 설명된 대로 VAT 환급 양식의 항목당 금액, 조정 및 VAT 금액에 대한 분석을 제공합니다.
- 판매 거래 장부
- 구매 거래 장부

## <a name="prerequisites"></a>전제 조건
법인의 기본 주소는 이집트에 있어야 합니다.
**기능 관리** 작업 공간에서 다음 기능을 실행해야 합니다.

   - (이집트) 판매세 및 구매세 보고서의 카테고리 계층.

기능을 활성화하는 방법에 대한 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하십시오.

**전자 보고** 작업 공간에서 리포지토리에서 다음 전자 보고 형식을 가져옵니다.

- VAT 신고 Excel(EG)

> [!NOTE]
> 위의 형식은 **세금 신고 모델** 을 기반으로 하며 **세금 신고 모델 매핑** 을 사용합니다. 추가 구성을 자동으로 가져옵니다.

전자 보고 구성을 가져오는 방법에 대한 자세한 내용은 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하십시오.

## <a name="download-electronic-reporting-configurations"></a>전자 보고 구성 다운로드

이집트에 대한 부가가치세 신고서의 구현은 전자 보고(ER) 구성을 기반으로 합니다. 구성 가능한 보고의 기능 및 개념에 대한 자세한 내용은 [전자 보고](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)를 참조하십시오.

운영 및 사용자 수용 테스트(UAT) 환경의 경우 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하십시오.

이집트 법인에서 VAT 환급 양식 및 관련 보고서를 생성하려면 다음 구성을 업로드하십시오.

- 세금 신고 model.version.70.xml 이상 버전
- 세금 신고 모델 mapping.version.70.120.xml 이상 버전
- VAT 선언 Excel(EG).version.70.32 이상 버전

LCS(Lifecycle Services) 또는 글로벌 리포지토리에서 ER 구성 다운로드를 완료한 후 다음 단계를 완료하십시오.

1. **전자 보고** 작업 공간으로 이동하고 **보고 구성** 타일을 선택합니다.
1. **구성** 페이지의 작업 창에서 **Exchange** >  **XML 파일에서 로드** 를 선택하십시오.
1. 위에 나열된 순서대로 파일을 업로드합니다. 모든 구성이 업로드되면 구성 트리가 Finance에 있어야 합니다.

## <a name="set-up-application-specific-parameters"></a>애플리케이션별 매개 변수 설정

애플리케이션별 매개변수를 사용하면 보고서가 생성될 때 세금 거래가 각 라인에서 어떻게 분류되고 계산되는지에 대한 기준을 설정할 수 있습니다. 결정은 품목 판매세 그룹, 판매세 그룹, 판매세 코드 및 조회 정의에 설정된 기타 기준의 구성을 기반으로 합니다.

이집트에 대한 판매 및 구매 장부 보고서에는 이집트에 특정한 작업, 제품 및 문서 유형과 같은 특정 거래 분류에 해당하는 일련의 열이 포함됩니다. 트랜잭션이 게시될 때 이러한 새로운 분류를 새로운 항목 데이터로 포함하는 대신, 분류는 이집트에 대한 VAT 보고서 보류 요건을 충족하기 위해 **구성** > **애플리케이션별 매개 변수 설정** > **설정** 에 소개된 다양한 검색에 따라 결정됩니다. 

![애플리케이션별 매개 변수 페이지.](media/egypt-vat-declaration-setup1.png)

다음 조회 구성은 구매 및 판매 VAT 장부 보고서의 거래를 분류하는 데 사용됩니다.

- **PurchaseItemTypeLookup** > O열: 품목 유형
- **VATRateTypeLookup** > B열: 세금 유형
- **VATRateTypeLookup** > C열: 표 항목 유형
- **PurchaseOperationTypeLookup** > A열: 문서 유형
- **CustomerTypeLookup** > A열: 문서 유형
- **SalesOperationTypeLookup** > N열: 작업 유형
- **SalesItemTypeLookup** > O열: 품목 유형

다음 단계를 완료하여 VAT 선언 및 관련 북 보고서를 생성하는 데 사용되는 다양한 조회를 설정합니다. 

1. **전자 보고** 작업 공간에서 **구성** >  **설정** 을 선택하여 부가가치세 신고 양식의 관련 상자에서 세금 거래를 식별하는 규칙을 설정합니다.
2. 현재 버전을 선택하고 **조회** 빠른 탭에서 조회 이름을 선택합니다. 예를 들어 **SalesItemTypeLookup** 입니다. 이 조회는 세무 당국에서 요구하는 판매 VAT 장부의 분류 목록을 식별합니다.
3. **조건** 빠른 탭에서 **추가** 를 선택하고 **조회 결과** 열의 새 줄에서 **열O** 의 분류를 나타내는 관련 줄을 선택합니다.
4. **판매세 그룹** 열에서 분류를 식별하는 데 사용되는 판매세 그룹을 선택합니다. 예를 들어, **국내 판매 송장** 입니다. 구성이 다른 방식으로 정의된 경우 품목 판매세 그룹, 세금 코드 또는 트리 속성 조합을 사용할 수도 있습니다. 
5. **이름** 열에서 세금 거래 분류를 선택합니다.
6. 사용 가능한 모든 조회에 대해 3~5단계를 반복합니다.
7. **추가** 를 선택하여 최종 레코드 줄을 포함시키고 **조회 결과** 열에서 **적용되지 않음** 을 선택합니다. 
8. 나머지 열에서 **비어 있지 않음** 을 선택합니다. 
9. **상태** 필드에서 **완료** 를 선택합니다.
10. **저장** 을 선택한 다음 **애플리케이션별 매개 변수** 페이지를 닫습니다.

> [!NOTE]
> **해당되지 않음** 마지막 레코드를 추가할 때 다음 규칙을 정의합니다. 인수로 전달된 판매세 그룹, 품목 판매세 그룹, 세금 코드 및 이름이 이전 규칙을 충족하지 못할 경우 해당 거래는 판매 부가세 장부에 포함되지 않습니다. 이 규칙은 보고서를 생성할 때 사용되지 않지만 규칙 구성이 누락된 경우 보고서 생성 오류를 방지하는 데 도움이 됩니다.

다음 표는 설명된 조회 구성에 대해 제안된 구성의 예를 나타냅니다. 

**SalesItemTypeLookup**

| 조회 결과         | 줄 | 판매세 그룹    | 품목 판매세 그룹    | 세금 코드(코드) | 이름                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| 국내              | 1    | VAT_LOCAL          | *비어 있지 않음*             | *비어 있지 않음*     | 영업                 |
| 국내              | 2    | VAT_LOCAL          | *비어 있지 않음*             | *비어 있지 않음*     | SalesCreditNote       |
| 국내              | 3    | VAT_FINALC         | *비어 있지 않음*             | *비어 있지 않음*     | 영업                 |
| 국내              | 4    | VAT_FINALC         | *비어 있지 않음*             | *비어 있지 않음*     | SalesCreditNote       |
| 국내              | 5    | VAT_PUBLIO         | *비어 있지 않음*             | *비어 있지 않음*     | 영업                 |
| 국내              | 6    | VAT_PUBLIO         | *비어 있지 않음*             | *비어 있지 않음*     | SalesCreditNote       |
| 내보내기                | 7    | VAT_EXPORT         | *비어 있지 않음*             | *비어 있지 않음*     | 영업                 |
| 내보내기                | 8    | VAT_EXPORT         | *비어 있지 않음*             | *비어 있지 않음*     | SalesCreditNote       |
| 기계 및 장비 | 9    | *비어 있지 않음*        | VAT_M&E                 | *비어 있지 않음*     | 영업                 |
| 기계 및 장비 | 10   | *비어 있지 않음*        | VAT_M&E                 | *비어 있지 않음*     | SalesCreditNote       |
| 부품 기계        | 11   | *비어 있지 않음*        | VAT_PARTS               | *비어 있지 않음*     | 영업                 |
| 부품 기계        | 12   | *비어 있지 않음*        | VAT_PARTS               | *비어 있지 않음*     | SalesCreditNote       |
| 면제            | 13   | VAT_EXE            | *비어 있지 않음*           | *비어 있지 않음*     | SaleExempt            |
| 면제            | 14   | VAT_EXE            | *비어 있지 않음*           | *비어 있지 않음*     | SalesExemptCreditNote |
| 해당 없음        | 15   | *빈 템플릿*            | *빈 템플릿*                 | VAT_ADJ         | *비어 있지 않음*           |
| 해당 없음        | 16   | *비어 있지 않음*        | *비어 있지 않음*             | *비어 있지 않음*     | *비어 있지 않음*           |

 **SalesOperationTypeLookup**

| 조회 결과  | 줄 | 품목 판매세 그룹    | 세금 코드    | 이름                  |
|----------------|------|-------------------------|-------------|-----------------------|
| 상품          | 1    | VAT_GOODS               | *비어 있지 않음* | 영업                 |
| 상품          | 2    | VAT_GOODS               | *비어 있지 않음* | SalesCreditNote       |
| 상품          | 3    | VAT_GOODS               | *비어 있지 않음* | SaleExempt            |
| 상품          | 4    | VAT_GOODS               | *비어 있지 않음* | SalesExemptCreditNote |
| 서비스       | 5    | VAT_SERV                | *비어 있지 않음* | 영업                 |
| 서비스       | 6    | VAT_SERV                | *비어 있지 않음* | SalesCreditNote       |
| 서비스       | 7    | VAT_SERV                | *비어 있지 않음* | SaleExempt            |
| 서비스       | 8    | VAT_SERV                | *비어 있지 않음* | SalesExemptCreditNote |
| 조정    | 9    | *빈 템플릿*                 | VAT_ADJ     | 영업                 |
| 조정    | 10   | *빈 템플릿*                 | VAT_ADJ     | SalesCreditNote       |
| 해당 없음 | 11   | *비어 있지 않음*             | *비어 있지 않음* | *비어 있지 않음*           |

**PurchaseItemTypeLookup**

| 조회 결과          | 줄 | 품목 판매세 그룹    | 세금 코드    | 이름                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| 상품                  | 1    | VAT_GOODS               | *비어 있지 않음* | 구매                 |
| 상품                  | 2    | VAT_GOODS               | *비어 있지 않음* | PurchaseCreditNote       |
| 서비스               | 3    | VAT_SERV                | *비어 있지 않음* | 구매                 |
| 서비스               | 4    | VAT_SERV                | *비어 있지 않음* | PurchaseCreditNote       |
| 기계 및 장비  | 5    | VAT_M&E                 | *비어 있지 않음* | 구매                 |
| 기계 및 장비  | 6    | VAT_M&E                 | *비어 있지 않음* | PurchaseCreditNote       |
| 부품 기계         | 7    | VAT_PARTS               | *비어 있지 않음* | 구매                 |
| 부품 기계         | 8    | VAT_PARTS               | *비어 있지 않음* | PurchaseCreditNote       |
| 면제             | 9    | VAT_EXE                 | *비어 있지 않음*  | PurchaseExempt           |
| 면제             | 10   | VAT_EXE                 | *비어 있지 않음* | PurchaseExemptCreditNote |
| 해당 없음         | 11   | *비어 있지 않음*             | *비어 있지 않음* | *비어 있지 않음*              |

**PurchaseOperationTypeLookup**

| 조회 결과  | 줄 | 판매세 그룹  | 세금 코드    | 이름                     |
|----------------|------|------------------|-------------|--------------------------|
| 국내       | 1    | VAT_LOCAL        | *비어 있지 않음* | 구매                 |
| 국내       | 2    | VAT_LOCAL        | *비어 있지 않음* | PurchaseCreditNote       |
| 국내       | 3    | VAT_LOCAL        | *비어 있지 않음* | PurchaseExempt           |
| 국내       | 4    | VAT_LOCAL        | *비어 있지 않음* | PurchaseExemptCreditNote |
| 가져옴       | 5    | VAT_IMPORT       | *비어 있지 않음* | 구매                 |
| 가져옴       | 6    | VAT_IMPORT       | *비어 있지 않음* | PurchaseCreditNote       |
| 가져옴       | 7    | VAT_IMPORT       | *비어 있지 않음* | PurchaseExempt           |
| 가져옴       | 8    | VAT_IMPORT       | *비어 있지 않음* | PurchaseExemptCreditNote |
| 조정    | 9    | *빈 템플릿*          | VAT_ADJ     | PurchaseCreditNote       |
| 조정    | 10   | *빈 템플릿*          | VAT_ADJ     | 구매                 |
| 해당 없음 | 11   | *비어 있지 않음*      | *비어 있지 않음* | *비어 있지 않음*              |

**CustomerTypeLookup**

|    조회 결과    | 줄 | 판매세 그룹 |
|---------------------|------|-----------------|
| 조직        |  1   | VAT_LOCAL       |
| 조직        |  2   | VAT_EXPORT      |
| 조직        |  3   | VAT_EXE         |
| 최종 소비자      |  4   | VAT_FINALC      |
| 공공 조직 |  5   | VAT_PUBLIO      |
| 해당 없음      |  6   | *비어 있지 않음*     |

**VATRateTypeLookup**

| 조회 결과  | 줄 | 세금 코드(코드) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *비어 있지 않음*     |
| SecondTable    | 4    | *비어 있지 않음*     |
| 해당 없음 | 5    | *비어 있지 않음*     |


## <a name="set-up-general-ledger-parameters"></a>총계정원장 매개 변수 설정

Microsoft Excel 형식으로 VAT 반환 양식 보고서를 생성하려면 **총계정원장 매개 변수** 페이지에서 ER 형식을 정의합니다.

1. **세금** > **설정** > **총계정원장 매개변수** 로 이동합니다.
2. **판매세** 탭의 **세금 옵션** 섹션의 **부가가치세 명세서 형식 매핑** 필드에서 **부가가치세 신고 Excel(EG)** 을 선택합니다. 필드를 비워 두면 표준 판매세 보고서가 SSRS 형식으로 생성됩니다.
3. **범주 계층** 을 선택합니다. 이 카테고리는 사용자가 상품 및 서비스를 선택하고 분류할 수 있도록 대외 무역 탭 거래의 상품 코드를 활성화합니다. 이 분류에 대한 설명은 판매 및 구매 거래 보고서에 자세히 설명되어 있습니다. 이 구성은 선택 사항입니다.

![신고서 양식.](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>VAT 환급 보고서 생성
일정 기간 동안의 VAT 환급 보고서를 준비하고 제출하는 프로세스는 판매세 정산 및 사후 작업 중에 전기된 판매세 납부 거래를 기반으로 합니다. 판매세 정산 및 보고에 대한 자세한 내용은 [판매세 개요](../general-ledger/indirect-taxes-overview.md)를 참조하십시오.

세금 신고 보고서를 생성하려면 다음 단계를 완료하십시오.

1. **세금** >  **신고** >  **판매세** >  **정산기간 판매세 신고** 또는 **정산 후 판매세 신고** 로 이동합니다.
2. **정산 기간** 을 선택합니다.
3. 시작 날짜를 선택한 다음 판매세 납부 버전을 선택합니다.
5. **확인** 을 선택합니다. 
6. 해당되는 경우 이전 기간의 대변 금액을 입력하거나 금액을 0으로 둡니다.
7. **보고서 상세 내역** 필드에서 다음 사용 가능한 옵션 중 하나를 선택하십시오. 
   - **부가가치세 장부 구매**: 구매세 거래 내역 보고서를 생성합니다.
   - **판매 부가세 장부**: 판매세액 거래 내역 보고서를 생성합니다.
   - **부가가치세 신고**: 부가가치세 신고서만 생성합니다.
8. 양식을 할당하기 위해 등록된 사람의 이름을 입력합니다.
9. 언어를 선택합니다. 모든 보고서는 **en-us** 및 **ar-eg** 로 번역됩니다.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


