---
title: 프랑스 Intrastat
description: 이 항목에는 프랑스의 Intrastat 신고에 대한 정보가 포함되어 있습니다.
author: anasyash
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4d38576e1c6b40242d5c6313fb06f08e170b4466
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "8450976"
---
# <a name="french-intrastat"></a>프랑스 Intrastat

[!include[banner](../includes/banner.md)]

부가가치세(VAT)에 등록되어 있고 다른 유럽 연합(EU) 국가와 거래하는 프랑스의 회사는 프랑스와의 상품 및 서비스 교환을 신고해야 합니다. DEB(Declaration d'exchanges de biens, 상품 교환 신고)는 EU의 판매 목록과 Intrastat 보고서를 결합한 것입니다. 지역 내 모든 상품 판매에 대해 매달 이 보고서를 제출해야 합니다.

DEB 보고서는 SAISUNIC 330 또는 INTRACOM 형식의 두 가지 전자 텍스트 파일 형식 중 하나로 생성할 수 있습니다.

다음 표에는 SAISUNIC 330 형식의 프랑스 Intrastat 신고에 포함된 필드가 나와 있습니다. 표는 또한 필드의 보고서 수준을 나타냅니다. 필드는 **4**(간소화), **1**(전체) 또는 둘 다일 수 있습니다.

| **필드**                   | **보고서 수준** |
|-----------------------------|------------------|
| 참고 기간         | 4, 1              | 
| 신고 건수       | 4, 1              |
| 줄 번호                 | 4, 1              |
| 국가 ISO 코드(FR)       | 4, 1              | 
| 보완 코드          | 4, 1              | 
| 사이렌 번호                | 4, 1              | 
| 고객의 VAT 코드        | 4, 1              | 
| 방향 코드              | 4, 1              |
| 거래 유형            | 4, 1              | 
| 의무 수준            | 4, 1              |
| 상품 코드              | 1                | 
| 국가 NGP                | 1                | 
| 카운티(부서)         | 1                |
| 거래의 성격       | 1                | 
| 원산지      | 1                | 
| 원산지 - 수입 | 1                | 
| 최종 목적지 - 수출 | 1                | 
| 송장 가치               | 4, 1              | 
| 통계적 가치           | 1                |
| 순 무게                  | 1                | 
| 추가 단위            | 1                |
| 운송 코드              | 1                | 

다음 표에는 INTRACOM 형식의 프랑스 Intrastat 신고에 포함된 필드가 나와 있습니다.
표는 또한 필드의 보고서 수준을 나타냅니다. 필드는 **4**(간소화), **1**(전체) 또는 둘 다일 수 있습니다.

| **필드**                   | **보고서 수준**   | 
|-----------------------------|--------------------|
| 코드                        | 4, 1               | 
| 신고 건수       | 4, 1               |
| 라인 수              | 4, 1               | 
| Siren                       | 4, 1               |
| 카운티(부서)         | 1                  |          
| 운송 코드              | 1                  |          
| 원산지           | 1                  |            
| 거래의 성격       | 1                  |             
| 송장 가치               | 4, 1               |             
| 배송 모드           | 1                  |           
| 거래 유형            | 4, 1               |            
| 의무 수준            | 4, 1               |           
| 상품 코드              | 1                  |            
| 국가 NGP                | 1                  |            
| 순 무게                  | 1                  |            
| 통계적 가치           | 1                  |            
| 추가 단위            | 1                  |            
| 원산지 - 수입 | 1                  |            
| 최종 목적지 - 수출 | 1                  |            
| 고객의 VAT 코드        | 4, 1               |            
| 보완 코드          | 4, 1               |           
| 참고 기간         | 4, 1               |         

### <a name="set-up-intrastat"></a>Intrastat 설정

1.  [Microsoft Dynamics LCS(Lifecycle Services)](https://lcs.dynamics.com/Logon/Index)의 공유 자산 라이브러리에서 Intrastat 선언에 대한 다음 전자 보고(ER) 구성의 최신 버전을 다운로드하십시오.

    - Intrastat 모델
    - Intrastat 보고서
    - Intrastat INTRACOM(FR)
    - Intrastat SAISUNIC(FR)

    자세한 내용은 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하십시오.

2.  Dynamics 365 Finance에서 **세금** > **설정** >  **대외 무역** > **대외 무역 매개 변수** 로 이동하여 다음 단계를 따릅니다.

    1. **Intrastat** 탭의 **전자 보고** 빠른 탭의 **파일 형식 매핑** 필드에서 **Intrastat INTRACOM (FR)** 또는 **Intrastat SAISUNIC (FR)** 을 선택합니다.
    2. **보고서 형식 매핑** 필드에서 **Intrastat 보고서** 를 선택합니다.
    3. **상품 코드 계층** 빠른 탭의 **범주 계층** 필드에서 **Intrastat** 을 선택합니다.
    4. **일반** 빠른 탭의 **트랜잭션 코드** 필드에서 상품 전송에 사용할 코드를 선택합니다.
    5. **신용 노트** 필드에서 상품의 반품을 위해 사용되는 코드를 선택합니다.
    6. **수출 의무 수준** 필드에 내보내기 보고서의 상세 수준을 입력합니다. 선택한 수준은 보고서에 표시되는 행에 영향을 줍니다. 자세한 내용은 이 항목의 시작 부분에 있는 표를 참조하십시오.

3. **조직 관리** > **조직** > **법인** 으로 이동하여 회사를 선택한 후 다음 단계를 수행하십시오.

    1. **등록 번호** 빠른 탭의 **NAF 코드** 필드에 NAF 코드를 입력합니다. 자세한 내용은 [FR-00003 NAF 코드 및 Siret 번호](tasks/fr-00003-naf-codes-siret-numbers.md)를 참조하십시오.
    2. **대외 무역 및 물류** 빠른 탭의 **Intrastat** 섹션에서 **VAT 면제 번호 내보내기** **및 VAT 면제 번호 가져오기** 필드를 설정합니다.
    3. **세금 등록** 빠른 탭의 **세금 등록 번호** 필드에 회사의 세금 등록 번호를 입력합니다.

4. 고객에 대한 NAF 코드 및 면세 번호를 지정하려면 **수취 계정** > **고객** > **모든 고객** 으로 이동한 후 다음 단계를 수행하십시오.

    1. 고객을 선택합니다.
    2. **송장 및 배송** 빠른 탭의 **판매 세금** 섹션의 **면세 번호** 필드에 고객의 면세 번호를 입력합니다.
    3. **판매 인구 통계** 빠른 탭의 **프랑스 Siret** 필드에 회사의 Siret 번호를 입력합니다.
    4. **NAF 코드** 필드에 회사의 NAF 코드를 입력합니다.
    5. 다른 고객에 대해 이 단계를 반복합니다.

5. 공급업체에 대한 NAF 코드 및 면세 번호를 지정하려면 **지급 계정** > **공급업체** > **모든 공급업체** 로 이동한 후 다음 단계를 수행하십시오.

    1. 공급업체를 선택하십시오.
    2. **송장 및 배송** 빠른 탭의 **판매 세금** 섹션의 **면세 번호** 필드에 공급업체의 면세 번호를 입력합니다.
    3. **구매 인구 통계** 빠른 탭의 **프랑스 Siret** 필드에 회사의 Siret 번호를 입력합니다.
    4. **NAF 코드** 필드에 회사의 NAF 코드를 입력합니다.
    5. 다른 공급업체에 대해 이 단계를 반복합니다.

6. **세금** > **설정** > **대외 무역** > **Intrastat의 압축** 으로 이동하여 정보를 요약할 때 비교해야 하는 필드를 선택합니다. 프랑스 Intrastat의 경우 **통계 절차**, **원산지**, **원산지 국가/지역**, **배송 조건**, **운송**, **수정**, **국가/지역**, **원산지/목적지**, **방향**, **발송인 국가/지역**, **발송인 주**, **주**, **거래 코드**, **상품** 을 선택합니다.

7. **창고 관리** > **설정** > **창고** > **창고** 로 이동하여 창고를 선택한 후 다음 단계를 수행하십시오.

    1. **주소** 빠른 탭에서 **추가** 또는 **편집** 을 선택합니다.
    2. 대화 상자의 **도시** 필드에서 창고의 도시를 선택합니다. 도시의 주는 DEB 보고서에 카운티로 사용됩니다.

### <a name="ngp-codes"></a>NGP 코드

DEB 보고서에서 제품의 코드는 다음과 같은 요소로 구성됩니다.

  - EU의 관세 및 통계 명칭을 나타내는 8자리 CN8 코드.
  - 해당되는 경우, 한 자리 NGP(Nomenclature Générale des Produits) 국가 품목 코드.

2021년 NGP는 세 가지 유형의 제품에만 적용됩니다.

  - 소, 양, 염소의 일부 제품
  - 군용 장비
  - 프랑스 와인

 NGP 코드를 설정하고 관련 제품에 할당해야 합니다. 그러면 **NGP** 필드가 **Intrastat 저널** 페이지에서 자동으로 설정됩니다.

#### <a name="set-up-an-ngp-code"></a>NGP 코드 설정

1. **세금** > **설정** > **해외 무역** > **NGP 코드** 로 이동합니다
2. 작업 창에서 **새로 만들기** 를 선택하여 NGP 코드를 생성합니다.
3. **NGP** 필드에 한 자리 코드를 입력합니다.
4. **설명** 필드에 코드에 대한 설명을 입력합니다.

#### <a name="assign-an-ngp-code-to-a-product"></a>제품에 NGP 코드 할당

1. **제품 정보 관리** > **제품** > **출시 제품** 으로 이동합니다.
2. 그리드에서 제품을 선택합니다.
3. **대외 무역** 빠른 탭의 **Interstat** 섹션의 **NGP** 필드에서 적절한 NGP 코드를 선택합니다.

## <a name="intrastat-journal"></a>Intrastat 저널

**세금** > **신고** > **해외** **무역** > **Intrastat** 로 이동하여 EU 국가와의 해외 무역에 적용되는 거래를 관리합니다. 자세한 내용은 [Intrastat 개요](emea-intrastat.md)를 참조하십시오.

**NGP** 열은 프랑스에만 해당됩니다. 이는 제품의 NGP 코드를 보여줍니다. NGP가 제품에 적용되지 않는 경우 **0**(영)이 표시됩니다. NGP 코드를 조정할 수 있습니다. 트랜잭션을 선택한 다음 **일반** 탭의 **코드** 섹션의 **NGP** 필드에서 필요한 NGP 코드를 선택합니다.

### <a name="intrastat-transfer"></a>Intrastat 전송

**Intrastat** 페이지의 작업 창에서 **전송** 을 선택하여 판매 주문, 무료 텍스트 송장, 구매 주문, 공급업체 송장, 공급업체 제품 영수증, 프로젝트 송장 및 이전 주문에서 지역 내 거래에 대한 정보를 자동으로 전송합니다. EU 국가가 도착지 국가 또는 지역(출발용) 또는 위탁(도착용)으로 되어 있는 문서만 전송됩니다.

DEB 보고서는 EU 판매 목록과 Intrastat 보고서를 합친 것이기 때문에, 한 EU 국가(당사자 A)에서 다른 EU 국가(당사자 C)로 직접 전달되고, 프랑스 법인(당사자 B)이 삼각 거래의 중간에 있는 *삼각* 거래도 포함됩니다.

### <a name="generate-a-deb-intrastat-report"></a>DEB(Intrastat) 보고서 생성

1. **세금** > **신고** > **해외 무역** > **Intrastat** 으로 이동합니다.
2. 작업 창에서 **출력** > **보고서** 를 선택합니다.
3. **Intrastat 보고서** 대화 상자에서 다음 필드를 설정하십시오.

    | 필드            | 설명                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | 시작일        | 보고서의 시작 날짜를 선택합니다.                                                                                               |
    | 종료일          | 보고서의 끝 날짜를 선택합니다.                                                                                                 |
    | 파일 생성    | .txt 파일을 생성하려면 이 옵션을 **예** 로 설정합니다.                                                                                 |
    | 파일 이름        | Intrastat 보고서의 .txt 파일 이름을 입력합니다.                                                                          |
    | 보고서 생성  | .xml 파일을 생성하려면 이 옵션을 **예** 로 설정합니다.                                                                                |
    | 보고서 파일 이름 | 필요한 이름을 입력합니다.                                                                                                            |
    | 수정만 | 수정만 보고하려면 이 옵션을 **예** 로 설정합니다. 정상 트랜잭션과 수정을 모두 보고하려면 **아니요** 로 설정합니다.         |
    | 방향        | 지역 내 도착에 대한 보고서를 보려면 **도착** 을 선택합니다. 지역 내 발송에 대해 보고하려면 **발송** 을 선택합니다. |

## <a name="example"></a>예:

다음 예는 프랑스 Intrastat을 설정하고 DEB 보고서를 생성하는 방법을 보여 줍니다. **DEMF** 법인을 사용합니다.

1. [LCS(Microsoft Dynamics Lifecycle Services)](https://lcs.dynamics.com/Logon/Index)의 공유 자산 라이브러리에서 Intrastat 신고 형식에 대한 다음 구성의 최신 버전을 다운로드하십시오.

    - Intrastat 모델
    - Intrastat 보고서
    - Intrastat INTRACOM(FR)

2. Finance에서 거래 코드를 설정:

    1. **세금** > **설정** > **해외 무역** > **거래 코드** 로 이동합니다.
    2. 작업 창에서 **새로 만들기** 를 선택합니다.
    3. **거래 코드** 필드에 **11** 을 입력합니다.
    4. **이름** 필드에 **구매 또는 판매** 를 입력합니다.
    5. 작업 창에서 **저장** 을 선택합니다.

3.  제품 계층 설정:

    1. **제품 정보 관리** > **설정** > **카테고리 및 속성** > **카테고리 계층** 으로 이동합니다.
    2. 그리드에서 **Intrastat** 을 선택합니다. 그런 다음 작업 창의 **범주 계층** 탭에 있는 **유지** 그룹에서 **편집** 을 선택합니다.
    3. 작업 창에서 **새 범주 노드** 를 선택합니다.
    4. **이름** 필드에 **Autres Libournais** 를 입력합니다.
    5. **코드** 필드에 **2204 21 42** 를 입력합니다.
    6. 작업 창에서 **저장** 을 선택합니다.

4. **세금** > **설정** > **해외 무역** > **해외 무역 매개 변수** 로 이동하여 다음 단계를 수행합니다.

    1. **Intrastat** 탭의 **일반** 빠른 탭에 있는 **트랜잭션 코드** 필드에서 **11** 을 선택합니다.
    2. **전자 보고** 빠른 탭의 **파일 형식 매핑** 필드에서 **Intrastat INTRACOM(FR)** 을 선택합니다.
    3. **보고서 형식 매핑** 필드에서 **Intrastat 보고서** 를 선택합니다.
    4. **상품 코드 계층** 빠른 탭의 **범주 계층** 필드에서 **Intrastat** 을 선택합니다.

5. NGP 코드 설정:

    1. **세금** > **설정** > **해외 무역** > **NGP 코드** 로 이동합니다
    2. 작업 창에서 **새로 만들기** 를 선택합니다.
    3. **NGP** 필드에 **8** 을 입력합니다.
    4. **설명 이름** 필드에 **NGP 8** 을 입력합니다.
    5. 작업 창에서 **저장** 을 선택합니다.

6. 제품에 NGP 코드 할당:

    1. **제품 정보 관리** > **제품** > **출시 제품** 으로 이동합니다.
    2. 그리드에서 **0001** 을 선택합니다.
    3. **대외 무역** 빠른 탭의 **NGP** 필드에서 **8** 을 선택합니다.
    4. **상품** 필드에서 **2204 21 42** 를 선택합니다.
    5. 작업 창에서 **저장** 을 선택합니다.

7. 새 제품이 포함된 판매 주문 작성:

    1. **수취 계정** > **주문** > **모든 판매 주문** 으로 이동합니다.
    2. 작업 창에서 **새로 만들기** 를 선택합니다.
    3. **판매** **주문** **생성** 대화 상자의 **고객** 섹션의 **고객** **계정** 필드에서 **100001** 을 선택합니다.
    4. **주소** 섹션의 **배달 주소** 필드에서 더하기 기호(**+**)를 선택하여 주소를 만듭니다.
    5. **새 주소** 대화 상자의 **설명 이름** 필드에 **독일** 을 입력합니다.
    6. **국가/지역** 필드에서 **DEU** 를 선택합니다.
    7. **확인** 을 선택합니다.
    8. **판매 주문 생성** 대화 상자에서 **확인** 을 선택합니다.
    9. **판매** **주문 라인** 빠른 탭의 **항목 번호** 필드에서 **0001** 을 선택합니다.
    10. 작업 창에서 **저장** 을 선택합니다.
    11. 작업 창의 **송장** 탭에 있는 **생성** 그룹에서 **송장** 을 선택합니다.
    12. **송장 게시** 대화 상자의 **매개 변수** 빠른 탭에 있는 **매개 변수** 섹션의 **수량** 필드에서 **모두** 를 선택합니다. 그런 다음 **확인** 을 선택하여 송장을 게시합니다.

8.  DEB 보고서 생성:

    1. **세금** > **신고** > **해외 무역** > **Intrastat** 으로 이동합니다.
    2. 작업 창에서. **전송** 을 선택합니다.
    3. **Intrastat(전송)** 대화 상자의 **매개 변수** 섹션에서 **고객 송장** 옵션을 **예** 로 설정합니다. 그런 다음 **확인** 을 선택합니다.
    4. **날짜** 필드를 기준으로 트랜잭션을 정렬합니다. 최상위 트랜잭션은 결과 트랜잭션입니다. **NGP** 필드는 자동으로 설정됩니다.
    5. 작업 창에서 **출력** &gt; **보고서** 를 선택하십시오.
    6. **Intrastat 보고서** 대화 상자의 **매개 변수** 빠른 탭의 **날짜** 섹션에서 생성한 판매 주문의 달을 선택하십시오.
    7. **내보내기 옵션** 섹션에서 **파일 생성** 옵션을 **예** 로 설정합니다.
    8. **파일 이름** 필드에 필요한 이름을 입력합니다.
    9. **확인** 을 선택하고 보고서를 검토합니다.
