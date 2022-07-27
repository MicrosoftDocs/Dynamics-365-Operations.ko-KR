---
title: Finance insights 설정 문제 해결
description: 이 항목에는 Finance insights 기능을 사용할 때 발생할 수 있는 문제가 나열되어 있습니다. 또한 이러한 문제를 해결하는 방법도 설명합니다.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: fc616e5fce6bbfeaa3b36ccc35f1b1cf407af4a6
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451552"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Finance insights 설정 문제 해결

[!include [banner](../includes/banner.md)]

이 항목에는 Finance insights 기능을 사용할 때 발생할 수 있는 문제가 나열되어 있습니다. 또한 이러한 문제를 해결하는 방법도 설명합니다.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>증상: 고객 지불 인사이트 데이터 통합 템플릿 대상 열을 매핑할 수 없는 이유는 무엇입니까?

### <a name="resolution"></a>해결

이전 버전의 템플릿을 사용 중일 수 있습니다. 버전 10.0.17 릴리스 전에 프리뷰 고객은 **지불 예측 결과(프리뷰)** 엔터티를 사용하여 **고객 지불 인사이트 결과(CDS에서 Fin 및 Ops로)** 데이터 통합(DI) 템플릿을 구성했습니다. 10.0.17 이상으로 업그레이드한 후 **고객 지불 인사이트 결과(CDS에서 Fin 및 Ops 10.0.17 이상으로)** DI 템플릿을 사용하여 매핑을 완료해야 합니다. 데이터 관리 엔터티 목록을 새로 고치고 **지급 예측 결과** 엔터티가 목록에 나타날 때까지 DI 템플릿 대상 열을 매핑하지 못할 수 있습니다. 엔터티 목록을 새로 고치고 지불 예측 결과를 표시하려면 Microsoft Dynamics 365 Finance 및 Dataverse(이전의 Common Data Service\[CDS\] 관리 포털)에서 단계를 완료해야 합니다.

### <a name="in-finance"></a>Finance에서 수행할 작업

업그레이드 후 Finance에서 다음 단계를 따릅니다.

1. **시스템 관리 \> 작업 영역 \> 데이터 관리** 로 이동합니다.
2. **데이터 관리** 작업 영역에서 **프레임워크 매개 변수** 타일을 선택합니다.
3. **데이터 가져오기/내보내기 프레임워크 매개 변수** 페이지에서 **엔터티 설정** 을 선택한 다음 **엔터티 목록 새로 고침** 을 선택합니다.
4. **데이터 가져오기/내보내기 프레임워크 매개 변수** 페이지를 닫습니다.
5. **데이터 관리** 작업 영역에서 **데이터 엔터티** 타일을 선택합니다.
6. "지불 예측 결과"를 검색합니다. **지불 예측 결과** 엔터티가 미리 보기 버전이 아닌지 확인합니다. 프리뷰 버전의 이름은 "(프리뷰)"로 끝납니다. 엔터티의 프리뷰 버전만 표시되는 경우 Microsoft 지원에 문의하세요.

### <a name="in-dataverse"></a>Dataverse에서 수행할 작업

[Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/environments)의 단계를 따라 데이터 통합 프로젝트를 업데이트합니다.

1. Finance insights의 프리뷰 버전을 사용하는 경우 **고객 지불 인사이트 결과(CDS에서 Fin 및 Ops로)** 템플릿과 연결된 DI 프로젝트를 제거합니다.
2. [데이터 통합자 프로젝트 만들기](create-data-integrate-project.md)의 단계를 따릅니다. **고객 지불 인사이트 결과(CDS에서 Fin 및 Ops 10.0.17 이상으로)** 템플릿을 사용합니다.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>증상: 고객 지불 예측 설정 페이지의 링크를 사용하여 AI Builder를 열려고 하면 "죄송합니다. 연결이 끊어졌습니다"라는 오류 메시지가 표시되는 이유는 무엇입니까?

### <a name="resolution"></a>해결

Dynamics 365 Finance 사용자는 환경에 대한 Microsoft Power Apps 사용자 계정이 있어야 하고 해당 사용자 계정에는 시스템 사용자 지정자 역할이 있어야 합니다. Microsoft Power Apps 시스템 관리자는 사용자 계정을 만들고 역할을 할당할 수 있습니다. 그런 다음 <https://make.preview.powerapps.com/>으로 이동하고 해당 사용자 계정을 사용하여 로그인한 다음 다시 링크를 시도할 수 있습니다.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>증상: 현금 흐름 예측 작업 영역의 현금 예측 탭에 데이터가 표시되지 않는 이유는 무엇입니까?

### <a name="resolution"></a>해결

**현금 흐름 예측** 작업 영역에 데이터를 올바르게 표시하려면 현금 및 은행 관리의 현금 흐름 예측 기능과 Finance insights의 현금 흐름 예측 기능을 설정하고 활성화해야 합니다.

먼저 현금 흐름 예측 및 유동성 계정을 설정하고 활성화합니다. 자세한 내용은 [현금 흐름 예측](../cash-bank-management/cash-flow-forecasting.md)을 참조하세요. 이 설정을 완료해도 예상한 결과가 표시되지 않으면 [현금 흐름 예측 설정 문제 해결](../cash-bank-management/cash-flow-forecasting-tsg.md)에서 자세한 내용을 참조하세요.

다음은 Finance insights의 현금 흐름 예측 기능(**현금 및 은행 관리 \> 설정 \> Finance Insights \> 현금 흐름 예측**)이 활성화되었고 AI 모델의 학습이 완료되었는지 확인합니다. 학습이 완료되지 않은 경우 **지금 예측** 을 선택하여 모델 학습 프로세스를 시작합니다.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>증상: Microsoft Dynamics Lifecycle Services에 새 추가 기능 설치 버튼이 표시되지 않는 이유는 무엇입니까?

### <a name="resolution"></a>해결

Microsoft Dynamics Lifecycle Services(LCS)의 **프로젝트 보안 역할** 필드에서 먼저 **환경 관리자** 또는 **프로젝트 소유자** 역할이 로그인한 사용자에게 할당되었는지 확인합니다. 새 추가 기능을 설치하려면 이러한 프로젝트 보안 역할 중 하나가 필요합니다.

올바른 프로젝트 보안 역할이 할당된 경우 **새 추가 기능 설치** 버튼을 보려면 브라우저 창을 새로 고쳐야 할 수 있습니다.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>증상: Finance Insights 추가 기능이 설치되지 않는 것 같습니다. 무엇이 문제인가요?

### <a name="resolution"></a>해결

다음 단계를 완료해야 합니다.

- Power Portal 관리 센터에서 **시스템 관리자** 및 **시스템 사용자 지정자** 액세스 권한이 있는지 확인합니다.
- 추가 기능을 설치하는 사용자에게 Dynamics 365 Finance 또는 이에 상응하는 라이선스가 적용되었는지 확인합니다.
- 다음 Azure AD 앱이 Azure AD에 등록되었는지 확인합니다. 

  | 응용 프로그램                  | 앱 ID           |
  | ---------------------------- | ---------------- |
  | Microsoft Dynamics ERP 마이크로 서비스 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>증상: "선택한 필터 범위에 대한 데이터를 찾지 못했습니다. 다른 필터 범위를 선택하고 다시 시도하세요."라는 오류가 표시됩니다. 

### <a name="resolution"></a>해결

데이터 통합기 설정을 확인하여 예상대로 작동하는지 확인하고 AI Builder에서 Finance로 데이터를 다시 업로드합니다.  
자세한 내용은 [데이터 통합 프로젝트 만들기](../finance-insights/create-data-integrate-project.md)를 참조하세요.

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>증상: 고객 지불 예측 훈련이 실패하고 AI Builder 오류 "모델을 훈련하려면 예측에는 2개의 고유한 결과 값만 있어야 합니다. 2개의 결과로 매핑하고 다시 학습하세요", "훈련 보고서 문제: IsNotMinRequiredDistinctNonNullValues"가 표시됩니다.

### <a name="resolution"></a>해결

이 오류는 **정시**, **연체** 및 **심한 연체** 범주에 설명된 각 범주를 나타내는 작년의 과거 거래가 충분하지 않음을 의미합니다. 이 오류를 해결하려면 **심한 연체** 거래 기간을 조정하세요. **심한 연체** 거래 기간을 조정해도 오류가 수정되지 않는 경우 **고객 지불 예측** 은 훈련 목적으로 각 범주의 데이터가 필요하므로 사용하기에 가장 적합한 솔루션이 아닙니다.

**정시**, **연체** 및 **심한 연체** 범주를 조정하는 방법에 대한 자세한 내용은 [고객 지불 예측 활성화](../finance-insights/enable-cust-paymnt-prediction.md)를 참조하세요.

## <a name="symptom-model-training-failed"></a>증상: 모델 학습이 실패합니다.

### <a name="resolution"></a>해결

**현금 흐름 예측** 모델 학습에는 1년 이상에 걸쳐 100개 이상의 거래가 포함된 데이터가 필요합니다. 1,000건 이상의 트랜잭션이 있는 데이터를 최소 2년 이상 보유하는 것이 좋습니다.

**고객 지불 예측** 기능을 사용하려면 이전 6개월에서 9개월 동안 100건 이상의 거래가 필요합니다. 거래에는 무료 텍스트 송장, 판매 주문 및 고객 지불이 포함될 수 있습니다. 이 데이터는 **구성** 페이지에 정의된 **정시**, **연체** 및 **심한 연체** 설정에 걸쳐 분산되어야 합니다.    

**예산 제안** 기능에는 최소 3년의 예산 또는 실제 데이터가 필요합니다. 이 솔루션은 예측에 3~10년간의 데이터를 사용합니다. 3년 이상을 사용해야 더 나은 결과를 얻을 수 있습니다. 데이터 자체는 값에 변동이 있을 때 가장 잘 작동합니다. 데이터에 임대 비용과 같은 모든 상수 데이터가 포함된 경우 변동이 없기 때문에 AI가 금액을 예측할 필요가 없기 때문에 훈련이 실패할 수 있습니다.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>증상: "이름이 'msdyn_paypredpredictionresultentities'인 테이블이 존재하지 않습니다. 원격 서버에서 오류: (404) 찾을 수 없음…"이라는 오류가 발생합니다.

### <a name="resolution"></a>해결

환경이 Data Lake 서비스의 최대 테이블 한도에 도달했습니다. 한도에 관한 자세한 내용은 [Azure Data Lake로 내보내기 개요](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md) 항목의 **실시간에 가까운 데이터 변경 활성화** 섹션을 참조하세요.
