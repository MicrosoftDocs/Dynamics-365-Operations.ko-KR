---
title: 전자 송장 발행 FAQ
description: 이 항목에서는 전자 송장 발행에 관해 자주 묻는 질문에 대한 정보를 제공합니다.
author: gionoder
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 2d4e7c79c83b9d60469c2b87a7b9120e0d4c13a695badfb2254a85cee629c933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450751"
---
# <a name="electronic-invoicing-faq"></a>전자 송장 발행 FAQ

[!include [banner](../includes/banner.md)]

이 항목에서는 전자 송장 서비스에 관해 자주 묻는 질문에 대한 답변을 제공합니다. 전자 송장 발행은 Dynamics 365 Finance, Dynamics 365 Supply Chain Management 및 Dynamics 365 Project Operations에 있는 전자 송장 발행 기능을 확장합니다. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>전자 송장에 관해 중요한 것은 무엇이며 조직에 왜 중요합니까?

조직이 전 세계적으로 성장하고 지역 전반에 걸쳐 입지를 확장함에 따라 운영 복잡성과 위험이 계속 심화되고 있습니다. 규정 준수를 유지하고 자주 변경되는 규정에 적응하는 일은 점점 더 어려워지고 있는 과제이며 송장 발행에 대해 특히 중요합니다. 기업이 종이 문서와 수작업 중심의 프로세스에 의존하기 때문에 송장 발행은 전통적으로 비용이 많이 들고 오류가 발생하기 쉽습니다.  

조직은 비용을 절감하고 엔드투엔드 프로세스의 속도를 높이기 위해 종이 송장에서 벗어나기 시작했습니다. 정부는 세금 디지털화의 핵심 구성 요소로 전자 송장 발행을 점점 더 많이 사용하고 있습니다. 조직이 세무 당국에 실시간 세금 정보를 디지털 방식으로 제출하도록 요구함으로써 정부는 탈세와 조작을 최소화하고 사기를 줄일 수 있습니다. 

세상은 종이를 사용하지 않는 문서 처리로 전환하고 있으며 전자 송장 발행을 구현하지 않으면 고객은 규정 준수 문제, 불필요한 비용, 경쟁자보다 뒤처지는 위험에 처하게 됩니다. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>전자 송장 발행 기능은 이미 Finance, Supply Chain Management 및 Project Operations에 포함되어 있지 않습니까? 이는 고객인 나에게 어떤 가치를 제공합니까? 

전자 송장 발행은 Finance, Supply Chain Management 및 Project Operations에 있는 전자 송장 발행 기능을 확장합니다. 이 기능은 또한 최신 전자 송장 발행 표준 준수를 단순화하고 여러 지역의 전자 송장 처리 및 교환에 일관된 경험을 제공합니다. 전자 송장 발행의 기능에는 다음과 같은 다양한 이점이 있습니다. 

   - 국가/지역별 요구 사항을 더 빠르고 쉽게 채택합니다.
   - 전자 송장 발행 솔루션 구현을 표준화합니다. 
   - 전자 송장 처리 추적 가능성을 향상합니다.  
   - 변화하는 법적 요구 사항 및 현지 비즈니스 관행을 준수하기 위한 유지 관리가 더 쉽습니다. 
   - 솔루션 패키징이 간소합니다.
   - 제출된 문서를 대량으로 처리하는 확장 기능으로 처리 시간이 단축됩니다.
   - 다른 회사와 솔루션을 공유할 수 있습니다.

## <a name="does-electronic-invoicing-service-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>전자 송장 발행 서비스는 Finance, Supply Chain Management 및 Project Operations의 온-프레미스 설치를 지원합니까? 

현재 플랫폼은 온-프레미스 버전 사용을 허용하지 않으며 향후 지원할 계획이 없습니다.

## <a name="does-electronic-invoicing-service-interface-with-the-vendor-import-automation-feature"></a>전자 송장 발행 서비스는 공급업체 가져오기 자동화 기능과 인터페이스를 수행합니까?

아니요. 이 인터페이스에 대한 계획은 있지만 계획된 일정은 없습니다. 계획되면 [릴리스 계획](/dynamics365/release-plans/)에 날짜가 발표됩니다.

## <a name="how-does-electronic-invoicing-service-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>전자 송장 발행 서비스는 전자 송장에 첨부된 파일을 어떻게 처리합니까? PDF 파일을 XML 파일에 포함할 때 SharePoint 서버가 필요합니까?

전자 송장에 첨부된 파일은 XML 요소에 포함된 바이너리 데이터로 처리됩니다. PDF 파일을 포함하기 위해 SharePoint 서버가 필요하지는 않지만 첨부 파일은 Finance, Supply Chain Management 및 Project Operations 문서 관리 시스템에 저장해야 합니다.

## <a name="is-electronic-invoicing-service-available-according-to-the-regulations-of-my-countryregion"></a>내 국가/지역의 규정에 따라 전자 송장 발행 서비스를 사용할 수 있습니까?

전자 송장 발행 서비스는 전 세계적으로 사용할 수 있는 마이크로 서비스 플랫폼입니다.

Microsoft는 Microsoft에서 기능을 현지화한 국가에 대한 전자 송장 형식 및 통합을 게시할 계획입니다. 자세한 내용은 [전자 송장 발행 기능의 가용성](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features)을 참조하십시오.

해당 국가/지역의 전자 송장 형식이 목록에 없는 경우 플랫폼은 향후 이 시나리오를 지원하는 것을 목표로 합니다. 전자 송장 발행의 구성 기능을 계속 활용하고 전자 송장 발행 형식을 직접 구성하거나 파트너/ISV와 협력하여 조직에 맞게 구성할 수 있습니다.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>Dynamics 365 for Regulatory Services는 Finance 또는 Supply Chain Management에 연결된 Human Resources 또는 Project Operations과 같은 새로운 모듈입니까? 이에 대한 추가 비용이 있습니까?

Dynamics 365 for Regulatory Services(RCS)는 세계화 리소스를 구성하기 위한 클라우드 서비스입니다. RCS는 모든 Finance, Supply Chain Management 및 Project Operations 라이선스 보유자에게 무료입니다.

RCS 가입을 위해서는 <https://marketing.configure.global.dynamics.com/>으로 이동하십시오.

자세한 내용은 [RCS(Regulatory Configuration Services) - 세계화 기능](rcs-globalization-feature.md)을 참조하십시오.

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing-service-or-just-turn-it-on-in-feature-management"></a>전자 송장 발행 서비스를 받으려면 등록해야 합니까? 아니면 기능 관리에서 켜야 합니까?

Finance, Supply Chain Management 및 Project Operations 라이선스가 있는 경우 [전자 송장 발행 추가 기능 서비스 관리 시작](e-invoicing-get-started-service-administration.md)을 참조하여 전자 송장 발행에 등록하십시오.

## <a name="does-electronic-invoicing-service-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>전자 송장 발행 서비스는 계층 1 가상 머신에서 작동합니까? 최소 요구 환경은 무엇입니까?

전자 송장 발행 서비스와 통합하려면 Finance 또는 Supply Chain Management를 호스팅할 계층 2 이상의 가상 머신이 필요합니다. 환경 계획에 대한 자세한 내용은 [환경 계획](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)을 참조하십시오.

## <a name="does-electronic-invoicing-service-have-a-test-mode-for-testing-invoice-submission"></a>전자 송장 발행 서비스에 송장 제출 테스트를 위한 테스트 모드가 있습니까?

이는 구성을 통해 달성할 수 있습니다. 송장 제출을 테스트하기 위해 UAT(User Acceptance Test) 환경에서 Finance 또는 Supply Chain Management에 연결하고 테스트 송장을 제출할 수 있습니다. 전자 송장 발행은 테스트 디지털 인증서 구성을 지원하며, 디지털 승인이 필요한 전자 송장의 경우 세무 당국에서 게시한 테스트 웹 서비스의 URL 설정을 지원합니다.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>기본 제공 국가별 전자 송장 발행 기능에 대한 설명서가 있습니까?

예. 전자 송장 발행 기능의 가용성 및 지원하는 형식에 대한 내용은 [전자 송장 발행 기능의 가용성](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features)을 참조하십시오.

## <a name="does-the-electronic-invoicing-service-allow-a-legal-entity-in-finance-or-supply-chain-management-that-is-configured-for-a-specific-country-to-consume-electronic-invoicing-features-from-different-countryregions"></a>특정 국가에 맞게 구성된 Finance 또는 Supply Chain Management에서 법인이 전자 송장 발행 서비스로 다른 국가/지역의 전자 송장 발행 기능을 사용할 수 있습니까?

예. 다음의 경우 법인의 국가와 무관하게 전자 송장 발행 기능으로 비즈니스 문서 제출을 처리할 수 있습니다.

   - 생성되는 비즈니스 문서에 적절한 문서 모델 매핑을 사용합니다.
   - 구성된 비즈니스 문서가 전자 송장 발행 기능에서 구성된 적용 가능성 규칙과 일치합니다.

## <a name="does-the-electronic-invoicing-service-use-the-same-configuration-and-design-experience-provided-by-the-electronic-reporting-module-in-finance-and-supply-chain-management"></a>전자 송장 발행 서비스는 Finance 및 Supply Chain Management의 전자 보고 모듈에서 제공하는 것과 동일한 구성 및 디자인 환경을 사용합니까? 

예. Finance 및 Supply Chain Management의 전자 보고(ER) 모듈에 사용되는 것과 동일한 디자이너 도구로 데이터 모델 매핑 및 파일 형식 구성을 만들고 구성합니다. 이러한 디자이너 도구로 RCS(Regulatory Configuration Services)에서도 전자 송장 발행 기능 구성에 사용되는 데이터 모델 매핑 및 파일 형식 구성을 만들고 구성할 수 있습니다.

## <a name="can-the-applicability-rules-be-extended-and-configured-so-that-they-arent-tied-to-any-specific-parameter-such-as-a-legal-entity"></a>적용 가능성 규칙이 법인과 같은 특정 매개 변수에 연결되지 않도록 확장 및 구성할 수 있습니까?

예. 적용 가능성 규칙은 완전히 구성할 수 있습니다. 조항을 추가 또는 제거하고 논리 연산을 작성하며 조항을 그룹화 및 그룹 해제할 수 있습니다. 자세한 내용은 [적용 가능성 규칙](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#applicability-rules)을 참조하십시오.

## <a name="does-the-electronic-invoicing-service-support-adding-other-er-format-configurations-to-generate-other-types-of-documents-does-it-support-sending-the-documents-electronically-to-customers-such-as-a-delivery-note"></a>전자 송장 발행 서비스로 다른 유형의 문서를 생성하기 위해 다른 ER 형식 구성을 추가할 수 있습니까? 상품 수령증과 같은 문서를 고객에게 전자적으로 보내는 기능을 지원합니까?

다른 ER 형식 구성을 사용하여 원하는 출력 파일을 생성할 수 있습니다. 그러나 ER 형식 구성이 비즈니스 문서를 생성하기 위해 Finance 또는 Supply Chain Management에 구성된 동일한 ER 송장 모델 매핑에서 파생되어야 합니다. 출력 파일을 EDI 트랜잭션으로 고객에게 직접 보내는 기능은 전자 송장 발행에서 기본적으로 지원되지 않습니다.

## <a name="does-the-electronic-invoicing-service-support-exchanging-electronic-invoices-with-customers-does-it-support-configuring-different-invoice-formats-for-the-same-invoice"></a>전자 송장 발행 서비스는 고객과 전자 송장 교환을 지원합니까? 동일한 송장에 대해 다른 송장 형식 구성을 지원합니까?

공급업체 전자 송장을 받고 가져오는 기능은 로드맵에 있지만 전자 송장을 고객에게 자동으로 보내는 기능은 현재 지원되지 않습니다.

## <a name="does-the-electronic-invoicing-service-extend-to-support-exchanging-edi-messages-with-other-companies"></a>전자 송장 발행 서비스는 다른 회사와 EDI 메시지 교환을 지원하도록 확장됩니까?

전자 송장 발행 서비스의 초점은 규정 준수 요구 사항에 따라 구동되는 전자 송장 메시지 유형을 교환하는 것입니다. 공급업체 전자 송장 수신 및 가져오기는 로드맵에 있지만 고객에게 전자 송장을 보내는 기능이 규제 요구 사항인 시나리오를 제외하고 현재 고객에게 전자 송장 파일을 보내는 기능이 기본적으로 지원되지 않습니다.

## <a name="does-the-electronic-invoicing-service-support-importing-or-merging-customizations-made-in-the-er-format-configurations-from-the-legacy-electronic-invoicing-feature"></a>전자 송장 발행 서비스는 레거시 전자 송장 발행 기능에서 ER 형식 구성으로 만든 사용자 정의 가져오기 또는 병합을 지원합니까?

전자 송장 발행 서비스에서 ER 형식 구성을 재사용할 수 있습니다. 그러나 전자 송장 기능에서 사용하도록 설계되고 Finance 또는 Supply Chain Management에서 비즈니스 문서를 생성하기 위해 구성된 동일한 ER 송장 모델에서 ER 형식 구성이 파생되어야 합니다.

## <a name="does-the-electronic-invoicing-service-support-issuing-electronic-invoices-from-custom-made-tables-if-so-how-do-you-create-the-er-data-model-configurations-for-these-new-tables-and-entities"></a>전자 송장 발행 서비스는 고객이 작성한 테이블에서 전자 송장 발행을 지원합니까? 그렇다면 이러한 새 테이블과 엔터티의 ER 데이터 모델 구성은 어떻게 만듭니까?

예. 그러나 송장 모델 매핑을 사용자 지정하고 고객이 작성한 테이블에 필요한 참조를 추가하거나 복잡성에 따라 새 송장 모델 매핑을 만들어야 합니다.

## <a name="does-the-electronic-invoicing-service-support-different-web-service-endpoints"></a>전자 송장 발행 서비스는 다양한 웹 서비스 엔드포인트를 지원합니까?

전자 송장 발행은 다양한 웹 서비스 엔드포인트를 지원합니다. REST 웹 서비스 또는 매개 변수화된 여러 국가별 웹 서비스 통합과 함께 구성 가능한 통합을 사용할 수 있습니다. 서로 다른 버전의 구성을 사용하여 동일한 웹 서비스 및 API에 대해 서로 다른 엔드포인트를 구성할 수 있습니다. 자세한 내용은 [작업별 매개 변수 목록](e-invoicing-setup.md#list-of-parameters-by-action)을 참조하십시오.

## <a name="is-electronic-invoicing-integrated-with-the-various-invoice-operators-apis-from-the-nordic-countries-or-should-that-be-handled-on-a-case-by-case-basis"></a>전자 송장 발행은 북유럽 국가의 다양한 송장 운영자 API와 통합되어 있습니까? 아니면 사례별로 처리해야 합니까?

Microsoft는 전자 송장 발행 기능을 사용하여 즉시 사용 가능한 통합을 제공하기 위해 기능 범위를 지속적으로 확장하고 있습니다. 지원되는 형식 및 통합에 대한 자세한 내용은 [전자 송장 발행 기능의 가용성](e-invoicing-configuration-rcs.md?toc=/dynamics365/finance/toc.json#availability-of-electronic-invoicing-features)을 참조하십시오.

> [!NOTE] 
> 원하는 답변을 찾지 못한 경우 제품 개발 팀(<D365EInvoicePreview@microsoft.com>)에 이메일로 문의해주십시오. 연락을 드리거나 이 FAQ의 내용을 보강하겠습니다.
