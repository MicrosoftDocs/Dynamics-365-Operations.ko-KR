---
title: Dynamics 365 Finance에서 제거되거나 사용되지 않는 기능
description: 이 항목에서는 Dynamics 365 Finance에서 제거되었거나 지원 중단 예정인 기능에 대해 설명합니다.
author: roschlom
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ad3df2ee9c10972dac8258b6ee41ae0a6eabfbea
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451285"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Dynamics 365 Finance에서 제거되거나 사용되지 않는 기능

[!include [banner](../includes/banner.md)]

이 항목에서는 Dynamics 365 Finance에서 제거되었거나 지원 중단 예정인 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

이 목록은 자체 계획을 위해 이러한 제거 및 사용 중단을 고려하는 데 도움을 주기 위한 것입니다. 

> [!NOTE]
> 재무 및 운영 앱의 개체에 대한 자세한 정보는 [기술 참조 보고서](/dynamics/s-e/global/axtechrefrep_61)에서 찾을 수 있습니다. 이러한 보고서의 여러 버전을 비교하여 각 버전의 재무 및 작동 앱에서 변경되거나 제거된 개체에 대해 알아볼 수 있습니다.

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Finance 10.0.24 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>스웨덴 판매세 보고서(보고 코드에 기반한 디자인)

[스웨덴 판매세 보고서](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새로운 VAT 신고 설계로 교체, [스웨덴 VAT 신고](../localizations/emea-swe-vat-declaration-sweden.md) |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 12월 1일까지 스웨덴에 대한 판매세 보고서(스웨덴 보고서 레이아웃)를 더 이상 지원하지 않을 계획입니다. 새로운 **VAT 신고 XML(SE)** 및 **VAT 신고 Excel(SE)** 전자 신고(ER) 형식이 **세금 신고** 모델에 도입되었습니다. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>오스트리아 VAT 내역서(보고 코드에 기반한 디자인)

[오스트리아 VAT 내역서 세부 정보](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새로운 VAT 신고 설계로 교체, [오스트리아 VAT 신고](../localizations/emea-aut-vat-declaration-austria.md) |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 12월 1일부터 **VAT 신고 모델** 에서 **VAT 신고(AT)** 전자 신고(ER) 형식을 지원하지 않을 계획입니다. 새로운 **VAT 신고 XML(AT)** 및 **VAT 신고 Excel(AT)** 형식이 **세금 신고** 모델에 도입되었습니다. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>독일 ELSTER 선언(보고 코드 기반 설계)

[VAT 내역서](../localizations/emea-de-vat-declaration.md)</br>
[독일 전자 세금 신고 설정](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[VAT 신고의 전자 전송(ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새 VAT 신고 설계로 대체, [독일 VAT 신고](../localizations/emea-deu-vat-declaration-germany.md) |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 12월 1일부터 **Elster(DE)** 및 **Elster 모델** ER(전자 신고) 형식을 더 이상 지원하지 않을 계획입니다. 새로운 **VAT 신고 XML(DE)** 및 **VAT 신고 Excel(DE)** 형식이 **세금 신고** 모델에 도입되었습니다. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>네덜란드에 대한 OB 신고(보고 코드에 기반한 설계)

[OB 신고](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새 VAT 신고 설계로 대체, [네덜란드 VAT 신고](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 12월 1일부터 **OB 신고(NL)** 및 **OB 신고 모델** 전자 보고(ER) 형식을 더 이상 지원하지 않을 계획입니다. 새로운 **VAT 신고 XML(NL)** 및 **VAT 신고 Excel(NL)** 형식이 **세금 신고** 모델에 도입되었습니다. |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Finance 10.0.20 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>"RTIR Query Invoice Data Request(HU)" 전자 보고(ER) 형식 구성

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 헝가리 온라인 청구 시스템과의 상호 운용을 위한 전자 메시징 처리에서 제외됨 |
| **다른 기능으로 대체되었습니까?**   | 아니요 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 4월 15일부터 "RTIR Query Invoice Data Request(HU)" 형식 구성을 더 이상 지원하지 않을 계획입니다. |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>"프랑스 FEC 감사 파일" "독일 감사 파일 출력" 형식 아래의 프랑스용 전자 보고(ER) 형식

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새로운 "FEC 감사 파일(FR)" 형식으로 대체됨 |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 5월 1일부터 "독일 감사 파일 출력" 형식에서 프랑스를 대상으로 "프랑스 FEC 감사 파일" 전자 보고(ER) 형식을 더 이상 지원하지 않을 계획입니다. 대신 "데이터 내보내기 모델" 아래에 새로운 FEC 감사 파일(FR) 형식이 도입되었습니다. |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Finance 10.0.17 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>전자 보고 구성을 위한 스토리지 옵션인 LCS 리포지토리

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새 RCS(Regulatory Configuration Service) 전역 리포지토리로 대체됨 |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | Dynamics 365 Finance, Supply Chain Management 및 Project Operations 제품|
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 4월 1일부터 ER(전자 보고) 구성을 위한 스토리지 옵션으로 LCS(Microsoft Dynamics Lifecycle Services) 리포지토리를 더 이상 지원하지 않을 계획입니다. 새로운 Microsoft ER 구성은 전역 리포지토리에서만 다운로드할 수 있도록 게시됩니다. 전역 리포지토리는 Dynamics 365 제품 및 RCS에서 액세스할 수 있습니다. 자세한 내용은 [RCS에서 ER 구성 가져오기](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) 및 [Regulatory Configuration Service - Lifecycle Services 스토리지 사용원 중단](../localizations/rcs-lcs-repo-dep-faq.md)을 참조하십시오. |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Finance 10.0.16 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>체코 공화국의 "VAT 신고(CZ)" 및 "통제 명세 보고서(CZ)" 전자 보고 형식

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새로운 형식으로 대체됨 |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2022년 1월 22일부터 "VAT 신고(CZ)", "제어문 내보내기(CZ)" 전자 보고(ER) 형식을 더 이상 지원하지 않을 계획입니다. 새로운 VAT 신고 XML(CZ), VAT 신고 Excel(CZ), VAT 통제 명세서 XML(CZ) 형식이 "세금 신고" 모델에서 대신 도입되었습니다. |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>벨기에 "장부 트랜잭션 내보내기 형식(BE)" 전자 보고 형식 및 해당 "장부 트랜잭션 내보내기(BE)" 모델

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | "표준 감사 파일(SAF-T)" 모델에서 새로운 ER 형식으로 대체되었습니다.  |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2021년 12월 1일부터 "원장 트랜잭션 내보내기 형식(BE)" 전자 신고(ER) 형식과 해당 "원장 트랜잭션 내보내기 형식(BE)" 모델을 더 이상 지원하지 않을 계획입니다. 대신 "표준 감사 파일(SAF-T)" 모델에서 "총계정원장 데이터 모델 매핑"과 함께 새로운 "총계정원장 데이터 내보내기(BE)" 형식이 도입되었습니다. |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>SSRS 형식의 영국 "VAT 100" 보고서

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 새로운 ER 형식 - "세금 신고 모델" 아래의 "VAT Declaration Excel(UK)" 형식으로 대체되었습니다.  |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2021년 12월 1일브터 SSRS 형식의 "VAT 100 보고서"를 더 이상 지원하지 않을 계획입니다. [MTD VAT 기능](../localizations/emea-gbr-mtd-vat-integration.md)의 "세금 신고 모델" 아래의 새로운 "VAT 신고 엑셀(UK)" 형식이 도입되었습니다. |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Finance 10.0.15 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Dynamics 365에 대한 Internet Explorer 11 지원 중단

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 2020년 12월부터 모든 Dynamics 365 제품에 대한 Microsoft Internet Explorer 11 지원은 더 이상 사용되지 않으며 Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.<br><br>이는 Internet Explorer 11 인터페이스를 통해 사용하도록 설계된 Dynamics 365 제품을 사용하는 고객에게 영향을 미칩니다. 2021년 8월 이후에는 이러한 Dynamics 365 제품에 대해 Internet Explorer 11이 지원되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 고객은 Microsoft Edge(으)로 전환하는 것이 좋습니다.|
| **영향을 받는 제품 영역**         | 모든 Dynamics 365 제품 |
| **배포 옵션**              | 모두|
| **상태**                         | 사용되지 않음. Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Finance 10.0.12 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>사용되지 않음: 폴란드 SSRS 보고서: 판매 VAT 레지스터, 구매 VAT 레지스터, EU 요약 VAT 레지스터 – 기능 참조 PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 법적으로 필요하지 않습니다.  |
| **다른 기능으로 대체되었습니까?**   | 예(VAT 신고가 가능한 표준 감사 파일의 Excel 형식 - JPK_VDEK) |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2021년 4월 27일 현재, **판매 VAT 레지스터, 구매 VAT 레지스터, EU 요약 VAT 레지스터 – 특징 참조 PL-00014** 와 같은 SSRS 보고서는 계속 지원할 계획입니다. VAT 신고 표준 감사 파일(JPK_VDEK)의 Excel 형식 예도 도입되었습니다. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Finance 10.0.11 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="norwegian-standard-main-accounts"></a>노르웨이 표준 주 계정

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 재설계  |
| **다른 기능으로 대체되었습니까?**   | 예(ER 형식 애플리케이션별 매개 변수로 대체됨) |
| **영향을 받는 제품 영역**         | 응용 프로그램 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2021년 4월 1일부터 표준 주 계정인 참조 필드, 관련 테이블, 데이터 엔터티와 관련된 기능을 더 이상 지원하지 않을 계획입니다. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Finance 10.0.7 릴리스에서 지원 중단되거나 사용되지 않는 기능

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>워크플로 요청 변경 대화 상자에 더 이상 사용자 선택 드롭다운 목록이 포함되지 않습니다.

| &nbsp; | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 계정 그룹 선택 기능으로 변경되었습니다.  |
| **다른 기능으로 대체되었습니까?**   | 예 |
| **영향을 받는 제품 영역**         | 워크플로 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 2020년 12월 1일부터 계정 그룹 선택이 없는 중국어 바우처 유형 설정을 더 이상 지원하지 않을 계획입니다. 새로운 디자인에 대한 자세한 내용은 [10.0.7의 새로운 기능](whats-new-changed-10-0-7.md)을 참조하십시오. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>제거되거나 더 이상 사용되지 않는 기능에 대한 이전 공지
이전 릴리스에서 제거되거나 더 이상 사용되지 않는 기능에 대한 자세한 내용은 [이전 릴리스에서 제거되거나 사용되지 않는 기능](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md)을 참조하십시오.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
