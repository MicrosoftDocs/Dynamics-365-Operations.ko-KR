---
title: 스웨덴 Intrastat
description: 이 항목에는 스웨덴의 Intrastat 보고에 대한 정보가 포함되어 있습니다.
author: andosip
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 152bfd24843867685b1d303484ed61ad98ec652a
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2021
ms.locfileid: "8450970"
---
# <a name="swedish-intrastat"></a>스웨덴 Intrastat

[!include[banner](../includes/banner.md)]

**Interstat** 페이지는 유럽연합(EU) 국가 간의 무역에 대한 정보를 생성하고 보고하는 데 사용됩니다. 스웨덴 Intrastat 신고에는 신고를 위한 상품 거래에 대한 정보가 포함되어 있습니다.

스웨덴 Intrastat 신고에는 다음 필드가 포함되어 있습니다.

   - 파트너 국가 ISO 코드
   - 트랜잭션 코드
   - 상품 코드
   - 추가 단위
   - 중량
   - 송장 금액

## <a name="set-up-intrastat"></a>Intrastat 설정

다음 전자 보고(ER) 구성의 최신 버전을 가져옵니다.

   - Intrastat 모델
   - Intrastat 보고서
   - Intrastat(SE)

자세한 내용은 [구성 서비스의 글로벌 리포지토리에서 ER 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)를 참조하십시오.

## <a name="set-up-foreign-trade-parameters"></a>대외 무역 매개 변수 설정

1. Microsoft Dynamics 365 Finance에서 **세금** > **설정** > **대외 무역 매개 변수** 로 이동합니다.
2. **Intrastat** 탭의 **전자 보고** 빠른 탭의 **파일 형식 매핑** 필드에서 **Intrastat (SE)** 를 선택합니다.
3. **보고서 형식 매핑** 필드에서 **Intrastat 보고서** 를 선택합니다.
4. **상품 코드 계층** 빠른 탭의 **범주 계층** 필드에서 **Intrastat** 을 선택합니다.
5. **트랜잭션 코드** 필드에서 속성 전송을 위한 트랜잭션 코드를 선택합니다. 보상(재정 또는 기타)에 대해 실제 또는 계획된 재산 이전을 생성하는 거래에 이 코드를 사용합니다. 수정에도 사용합니다. 스웨덴의 회사는 한 자리 거래 코드를 사용합니다.
6. **신용 노트** 필드에서 물품 반환에 대한 거래 코드를 선택합니다.
7. **국가/지역 속성** 탭의 **국가/지역** 필드에 회사가 거래하는 모든 국가 또는 지역을 나열합니다. EU에 속한 각 국가의 **국가/지역 유형** 필드에서 해당 국가가 Intrastat 보고서에 나타나도록 **EU** 를 선택합니다.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Interstat 신고에 대한 제품 매개 변수 설정

1. **제품 정보 관리** > **제품** > **출시 제품** 으로 이동합니다.
2. 그리드에서 제품을 선택합니다.
3. **대외 무역** 빠른 탭의 **Interstat** 섹션의 **상품** 필드에서 상품 코드를 선택합니다.
4. **재고 관리** 빠른 탭의 **순 무게** 필드에 제품의 무게를 킬로그램으로 입력합니다.
5. **세금** > **설정** > **대외 무역** > **Intrastat의 압축** 으로 이동하여 정보를 요약할 때 비교해야 하는 필드를 선택합니다. 스웨덴 Intrastat의 경우 다음 필드를 선택합니다.

    - 상품
    - 트랜잭션 코드
    - 방향
    - 국가/지역
    - 수정
    - 인보이스

## <a name="intrastat-transfer"></a>Intrastat 전송

**Intrastat** 페이지의 작업 창에서 **전송** 을 선택하여 판매 주문, 무료 텍스트 송장, 구매 주문, 공급업체 송장, 공급업체 제품 영수증, 프로젝트 송장 및 이전 주문에서 지역 내 거래에 대한 정보를 자동으로 전송합니다. EU 국가가 도착지 국가 또는 지역(출발용) 또는 위탁(도착용)으로 되어 있는 문서만 전송됩니다.

또는 작업 창에서 **새로 만들기** 를 선택하여 트랜잭션을 수동으로 입력할 수 있습니다.

### <a name="generate-an-intrastat-report"></a>Intrastat 보고서 생성

1. **세금** > **신고** > **해외 무역** > **Intrastat** 으로 이동합니다.
2. 작업 창에서 **출력** > **보고서** 를 선택합니다.
3. **Intrastat 보고서** 대화 상자에서 다음 필드를 설정하십시오.

    | 필드            | 설명                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | 시작일        | 보고서의 시작 날짜를 선택합니다.                                                                                               |
    | 종료일          | 보고서의 끝 날짜를 선택합니다.                                                                                                 |
    | 파일 생성    | Intrastat 보고서에 대한 .txt 파일을 생성하려면 이 옵션을 **예** 로 설정합니다.                                                       |
    | 파일 이름        | .txt 파일의 이름을 입력합니다.                                                                                                    |
    | 보고서 생성  | Intrastat 보고서에 대한 .xlsx 파일을 생성하려면 이 옵션을 **예** 로 설정합니다.                                                     |
    | 보고서 파일 이름 | .xlsx 파일의 이름을 입력합니다.                                                                                                   |
    | 방향        | 지역 내 도착에 대한 보고서를 보려면 **도착** 을 선택합니다. 지역 내 발송에 대해 보고하려면 **발송** 을 선택합니다. |

4. **확인** 을 선택하고 생성된 보고서를 검토합니다.

## <a name="example"></a>예:

이 예에서는 Intrastat에 대한 도착 및 발송을 게시하는 방법을 보여 줍니다. **DEMF** 법인을 사용합니다.

### <a name="preliminary-setup"></a>예비 설정

1. **조직 관리** > **조직** > **법인** 으로 이동하여 **DEMF** 법인을 선택합니다.
2. **주소** 빠른 탭에서 **편집** 을 선택한 다음 **국가/지역** 필드에서 **SWE(스웨덴)** 를 선택합니다.
3. 다음 ER 구성의 최신 버전을 가져옵니다.

    - Intrastat 모델
    - Intrastat 보고서
    - Intrastat(SE)

### <a name="create-transaction-codes"></a>거래 코드 생성

1. **세금** > **설정** > **해외 무역** > **거래 코드** 로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **거래** **코드** 필드에 **1** 을 입력합니다.
4. **이름** 필드에 **일반 트랜잭션** 입력
5. 작업 창에서 **저장** 을 선택합니다.

### <a name="set-up-foreign-trade-parameters"></a>대외 무역 매개 변수 설정

1. **세금** > **설정** > **대외 무역** > **매개 변수** 로 이동합니다.
2. **Intrastat** 탭의 **일반** 빠른 탭에 있는 **트랜잭션** **코드** 필드에서 **1** 을 선택합니다.
3. **전자 보고** 빠른 탭의 **파일 형식 매핑** 필드에서 **Intrastat(SE)** 을 선택합니다.
4. **보고서 형식 매핑** 필드에서 **Intrastat 보고서** 를 선택합니다.
5. **상품 코드 계층** 빠른 탭의 **범주 계층** 필드에서 **Intrastat** 이 선택되어 있는지 확인합니다.
6. **국가/지역 속성** 탭에서 **새로 만들기** 를 선택합니다.
7. **당사자 파티 국가/지역** 필드에서 **SWE** 를 선택합니다.
8. **국가/지역 유형** 필드에서 **국내** 를 선택합니다.
9. **당사자 국가/지역** 필드에서 **DEU** 를 선택한 다음 **국가/지역 유형** 필드에서 **EU** 를 선택합니다.

### <a name="set-up-product-information"></a>제품 정보 설정

1. **제품 정보 관리** > **제품** > **출시 제품** 으로 이동합니다.
2. 그리드에서 **D0001** 을 선택합니다.
3. **대외 무역** 빠른 탭의 **Intrastat** 섹션의 **상품** 필드에서 **100 200 30** 를 선택합니다.
4. **재고 관리** 빠른 탭의 **중량 측정** 섹션에 **순 중량** 필드에 **5** 를 입력합니다.
5. 작업 창에서 **저장** 을 선택합니다.

### <a name="change-the-site-address"></a>사이트 주소 변경

1. **창고 관리** > **설정** > **창고** > **사이트** 로 이동합니다.
2. 그리드에서 **1** 을 선택합니다.
3. **주소** 빠른 탭에서 **편집** 을 선택합니다.
4. **주소 편집** 대화 상자의 **국가/지역** 필드에서 **SWE** 를 선택합니다.
5. **확인** 을 선택합니다.

### <a name="create-a-sales-order-with-an-eu-customer"></a>EU 고객으로 판매 주문 생성

1. **수취 계정** > **주문** > **모든 판매 주문** 으로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **판매 주문 생성** 대화 상자의 **고객** 빠른 탭에 있는 **고객** 섹션의 **고객 계정** 필드에서 **DE-015** 를 선택합니다.
4. **일반** 빠른 탭의 **저장소 치수** 섹션의 **사이트** 필드에서 **1** 을 선택하십시오.
5. **창고** 필드에서 **11** 를 선택합니다.
6. **확인** 을 선택합니다.
7. **라인** 탭의 **판매 주문 라인** 빠른 탭의 **항목 번호** 필드에서 **D0001** 을 선택하십시오. 그런 다음 **수량** 필드에 **10** 를 입력합니다.
8. **라인 세부 정보** 빠른 탭의 **해외 거래** 탭에서 **트랜잭션 코드** 및 **상품** 필드가 자동으로 설정되었는지 확인하십시오.
9. 작업 창에서 **저장** 을 선택합니다.
10. 작업 창의 **송장** 탭에 있는 **생성** 섹션에서 **송장** 을 선택합니다.
11. **송장 게시** 대화 상자의 **매개 변수** 빠른 탭에 있는 **매개 변수** 섹션의 **수량** 필드에서 **모두** 를 선택합니다.
12. **확인** 을 선택하여 송장을 게시합니다.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>트랜잭션을 Intrastat 저널로 전송하고 결과를 검토합니다.

1. **세금** > **신고** > **해외 무역** > **Intrastat** 으로 이동합니다.
2. 작업 창에서 **전송** 을 선택합니다.
3. **Intrastat(전송)** 대화 상자의 **매개 변수** 섹션에서 **고객 송장** 옵션을 **예** 로 설정합니다.
4. **필터** 를 선택합니다.
5. **Intrastat 필터** 대화 상자의 **범위** 탭에서 첫 번째 줄을 선택하고 **필드** 필드가 **날짜** 로 설정되어 있는지 확인합니다.
6. **기준** 필드에서 현재 날짜를 선택합니다.
7. **확인** 을 선택하여 **Intrastat 필터** 대화 상자를 닫습니다.
8. **확인** 을 선택하여 **Intrastat(전송)** 대화 상자를 닫고 결과를 검토합니다. 선은 이전에 생성한 판매 주문을 나타냅니다.

    ![판매 주문에 대한 Intrastat 분개장](media/swe_intrastat_journal_sales_order.png)

9. 트랜잭션 라인을 선택한 다음 **일반** 탭을 선택하여 자세한 정보를 봅니다.

    ![판매 주문에 대한 분개장 라인 상세 내역](media/swe_intrastat_journal_sales_order_line_details.png)

10. 작업 창에서 **출력** > **보고서** 를 선택합니다.
11. **Intrastat 보고서** 대화 상자의 **매개 변수** 빠른 탭의 **날짜** 섹션에서 생성한 판매 주문의 달을 선택하십시오.
12. **내보내기** **옵션** 섹션에서 **파일 생성** 옵션을 **예** 로 설정합니다. 그런 다음 **파일 이름** 필드에 필요한 이름을 입력합니다.
13. **보고서 생성** 옵션을 **예** 로 설정합니다. 그런 다음 **보고서 파일 이름** 필드에 필요한 이름을 입력하십시오.
14. **방향** 필드에서 **발송** 을 선택합니다.
15. **확인** 을 선택하고 생성된 .txt 형식의 보고서를 검토하십시오. 다음 표에서는 예제 보고서의 값을 보여 줍니다.

    | 파트너 국가 ISO 코드 | 트랜잭션 코드 | 상품 코드 | 추가 단위 | 중량 | 송장 금액 |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. 생성된 Excel 형식의 보고서를 검토합니다.

    ![Intrastat 보고서](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>구매 주문 만들기

1. **지급 계정** > **구매 주문** > **모든 구매 주문** 으로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **구매 주문 생성** 대화 상자의 **공급업체 계정** 필드에서 **DE-001** 을 선택합니다.
4. **확인** 을 선택합니다.
5. **헤더** 탭의 **대외** **무역** 빠른 탭에서 **트랜잭션 코드** 필드가 **1** 로 설정되어 있는지 확인합니다.
6. **라인** 탭의 **구매 주문 라인** 빠른 탭의 **항목 번호** 필드에서 **D0001** 을 선택하십시오. 그런 다음 **수량** 필드에 **6** 를 입력합니다.
7. 작업 창의 **구매** 탭에 있는 **작업** 그룹에서 **확인** 을 선택합니다.
8. 작업 창의 **송장** 탭에 있는 **생성** 그룹에서 **송장** 을 선택합니다.
9. 작업 창에서 **기본 위치** 를 선택합니다. **라인에 대한 기본 수량** 필드에서 **주문한 수량** 을 선택합니다. 그런 다음 **확인** 을 선택합니다.
10. **공급업체 송장 헤더** 빠른 탭에 있는 **송장 식별** 섹션의 **번호** 필드에 **0001** 을 입력합니다.
11. 작업 창에서 **게시** 를 선택하여 송장을 게시합니다.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>도착에 대한 Interstat 신고 작성

1. **세금** > **신고** > **해외 무역** > **Intrastat** 으로 이동합니다.
2. 작업 창에서 **전송** 을 선택합니다.
3. **Intrastat(전송)** 대화 상자에서 **공급업체 송장** 옵션을 **예** 로 설정합니다.
4. **확인** 을 선택하여 트랜잭션을 전송하고 Intrastat 저널을 검토합니다.

    ![구매 주문에 대한 Intrastat 분개장](media/swe_intrastat_journal_purchase_order.png)

5. 구매 주문서의 **일반** 탭을 검토합니다.

    ![구매 주문에 대한 분개장 라인 상세 내역](media/swe_intrastat_journal_purchase_order_line_details.png)

6. 작업 창에서 **출력** > **보고서** 를 선택합니다.
7. **Intrastat 보고서** 대화 상자의 **매개 변수** 빠른 탭의 **날짜** 섹션에서 생성한 판매 주문의 달을 선택하십시오.
8. **내보내기** **옵션** 섹션에서 **파일 생성** 옵션을 **예** 로 설정합니다. 그런 다음 **파일 이름** 필드에 필요한 이름을 입력합니다.
9. **보고서 생성** 옵션을 **예** 로 설정합니다. 그런 다음 **보고서 파일 이름** 필드에 필요한 이름을 입력하십시오.
10. **방향** 필드에서 **도착** 을 선택합니다.
11. **확인** 을 선택하고 생성된 .txt 형식의 보고서를 검토하십시오. 다음 표에서는 예제 보고서의 값을 보여 줍니다.

    | 파트너 국가 ISO 코드 | 트랜잭션 코드 | 상품 코드 | 추가 단위 | 중량 | 송장 금액 |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. 생성된 Excel 형식의 보고서를 검토합니다.

    ![Intrastat 도착 보고서](media/swe_intrastat_arrivals_report.png)
