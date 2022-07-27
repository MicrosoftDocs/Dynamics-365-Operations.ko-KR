---
title: 이집트의 전자 송장 발행
description: 이 항목은 이집트에서 Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management의 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6fe1dd4254db8b390c17558320a6eaff2b0dcd19
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451666"
---
# <a name="electronic-invoicing-for-egypt"></a>이집트의 전자 송장 발행

[!include [banner](../includes/banner.md)]

이 항목은 이집트에서 전자 송장 발행을 시작하는 데 도움이 되는 정보를 제공합니다. RCS(Regulatory Configuration Service)의 국가별 구성 단계를 안내합니다. 이러한 단계는 [전자 송장 발행 설정](e-invoicing-set-up-overview.md)에 설명된 단계를 보완합니다.

## <a name="prerequisites"></a>전제 조건

이 항목의 절차를 시작하기 전에 다음 전제 조건을 완료하십시오.

- [전자 송장 발행 개요](e-invoicing-service-overview.md)에 설명된 전자 송장 발행을 숙지하십시오.
- RCS에 가입하고 전자 송장 발행을 설정합니다. 자세한 내용은 다음 항목을 참조하세요.

    - [전자 송장 발행 서비스 가입 및 설치](e-invoicing-sign-up-install.md)
    - [전자 송장 발행을 위한 Azure 리소스 설정](e-invoicing-set-up-azure-resources.md)
    - [Lifecycle Services에서 마이크로 서비스용 추가 기능 설치](e-invoicing-install-add-in-microservices-lcs.md)
    
- [전자 송장 발행과 통합 활성화 및 설정](e-invoicing-activate-setup-integration.md)에 설명된 대로 Microsoft Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management 애플리케이션과 전자 송장 발행 서비스 간의 통합을 활성화합니다.
- [고객 인증서 및 비밀](e-invoicing-customer-certificates-secrets.md)에 설명된 대로 Azure Key Vault에서 디지털 인증서 비밀을 만듭니다. 이집트 세무국은 테스트 목적을 위해 테스트 및 솔루션 검증 단계에서만 사용해야 하는 특정 테스트 디지털 인증서를 제공합니다. 자세한 내용은 [이집트 전자 송장 발행 SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/)에 제공된 링크를 통해 이집트 세무국 웹 사이트를 방문하십시오.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>이집트 전자 송장(EG) 기능에 대한 국가별 구성

**이집트 전자 송장(EG)** 전자 송장 발행 기능의 일부 매개 변수는 기본값으로 게시됩니다. 전자 송장 발행 기능을 서비스 환경에 배포하기 전에 경영 운영을 더 잘 반영하도록 기본값을 검토하고 필요에 따라 업데이트하십시오.

1. [글로벌 리포지토리에서 기능 가져오기](e-invoicing-import-feature-global-repository.md)에서 설명된 대로 **이집트 전자 송장(EG)** 세계화 기능의 최신 버전을 가져옵니다.
2. [세계화 기능 만들기](e-invoicing-create-new-globalization-feature.md)에 설명된 대로 가져온 세계화 기능의 복사본을 만들고 이를 위한 구성 공급자를 선택합니다.
3. **버전** 탭에 **초안** 버전이 선택되었는지 확인합니다.
4. **설정** 탭의 그리드에서 **파생된 판매 송장** 기능 설정을 선택합니다.
5. **편집** 을 선택합니다.
6. **처리 파이프라인** 탭의 **처리 파이프라인** 섹션에서 **이집트 세무국의 JSON 문서에 서명**.
7. **매개 변수** 섹션에서 **인증서 이름** 을 선택한 다음 생성한 디지털 인증서의 이름을 선택합니다.
8. **처리 파이프라인** 섹션에서 **이집트 ETA 서비스와 통합** 을 선택합니다. 이 작업이 두 번 수행되는 경우 이 단계를 반복합니다.
9. **매개 변수** 섹션에서 **웹 서비스 URL** 및 **로그인 서비스 URL** 을 선택합니다. 그런 다음 URL 매개 변수를 검토합니다. 테스트 및 프로덕션 URL을 받으려면 [이집트 전자 송장 발행 SDK](https://sdk.sit.invoicing.eta.gov.eg/faq/)에 제공된 링크를 통해 이집트 세무국 웹 사이트를 방문하십시오.
10. **저장** 을 선택하고 페이지를 닫습니다.
11. **파생된 프로젝트 송장** 기능 설정에 대해 4~10단계를 반복합니다.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>이집트 전자 송장(EG) 애플리케이션 설정의 국가별 구성

Finance 또는 Supply Chain Management 환경에서 설정해야 하는 매개 변수가 있습니다. 다음 두 위치 중 하나에서 이 설정을 완료할 수 있습니다.

- Finance 또는 Supply Chain Management 환경에서 직접. 자세한 내용은 [전자 송장 발행 매개 변수 설정](e-invoicing-set-up-parameters.md)을 참조하십시오.
- RCS에서. 전자 송장 발행 기능 설정 범위에서 모든 매개 변수를 정의한 다음 전자 송장 발행 기능을 배포할 때 Finance 또는 Supply Chain Management 환경에 직접 배포할 수 있습니다.

두 옵션의 매개 변수는 동일합니다. 전자 송장 서비스에서 첫 번째 기능을 설정하는 경우 다음 단계에 따라 RCS에서 매개 변수를 설정한 다음 연결된 애플리케이션에 배포하는 것이 좋습니다.

> [!NOTE]
> 일부 전자 송장 발행 기능 버전에는 Finance 또는 Supply Chain Management에 대해 사전 정의된 애플리케이션별 매개 변수 집합이 포함될 수 있습니다. 이 경우 데이터가 올바른지 확인해야 합니다. 올바르지 않으면 수동으로 매개 변수를 설정합니다.

1. 만든 **이집트 전자 송장(EG)** 세계화 기능의 사본을 찾습니다.
2. **버전** 탭에 **초안** 버전이 선택되었는지 확인합니다.
3. **설정** 탭에서 **애플리케이션 설정** 을 선택합니다.
4. **연결된 애플리케이션** 필드에서 매개 변수를 배포할 애플리케이션을 선택합니다.
5. **전자 문서 유형** 페이지에서 **추가** 를 선택하여 레코드를 만듭니다.
6. **테이블 이름** 필드에 **CustInvoiceJour** 를 추가합니다.
7. **문맥** 필드에 **고객 송장 컨텍스트** 매핑 이름에 대한 참조를 추가합니다. 구성은 **고객 송장 컨텍스트 모델** 입니다.
8. **전자 문서 매핑** 필드에 **고객 송장** 매핑 이름에 대한 참조를 추가합니다. 구성은 **송장 모델 매핑** 입니다.
9. **저장** 을 선택합니다.
10. **응답 유형** 페이지에서 **추가** 를 선택합니다.
11. **응답 유형** 필드에 **응답** 을 입력합니다.
12. **설명** 필드에 **프로세스 응답** 을 입력합니다.
13. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
14. **모델 매핑** 필드에서 **응답 메시지 가져오기** 를 선택합니다. 구성은 **이집트 응답 메시지 가져오기(EG)** 입니다.
15. **저장** 을 선택합니다.
16. **추가** 를 선택합니다.
17. **응답 유형** 필드에 **응답 데이터** 를 입력합니다.
18. **설명** 필드에 **프로세스 응답 데이터** 를 입력합니다.
19. **제출 상태** 필드에서 **보류 중** 을 선택합니다.
20. **데이터 엔터티 이름** 필드에서 **SalesInvoiceHeaderV2Entity** 를 선택합니다.
21. **모델 매핑** 필드에서 **응답 데이터 가져오기** 를 선택합니다. 구성은 **이집트 응답 데이터 가져오기 형식(EG)** 입니다.
22. **저장** 을 선택하고 페이지를 닫습니다.
23. 페이지를 닫습니다.

서비스 환경에 기능을 배포하고 Finance 또는 Supply Chain Management 연결 애플리케이션에 애플리케이션 설정을 배포하려면 [세계화 기능 완료, 게시 및 배포](e-invoicing-complete-publish-deploy-globalization-feature.md)를 참조하십시오.

## <a name="privacy-notice"></a>개인정보보호 통지

**이집트 전자 송장(EG)** 기능을 활성화하려면 제한된 데이터를 보내야 할 수 있습니다. 이 데이터에는 조직의 납세자 등록 ID가 포함됩니다. 데이터는 정부 웹 서비스와의 통합에 필요한 사전 정의된 형식으로 해당 세무 당국에 전자 송장를 보내기 위해 세무 당국이 승인한 타사 기관으로 전송됩니다. 관리자는 **조직 관리** \> **설정** \> **전자 문서 매개 변수** 로 이동하여 기능을 활성화 및 비활성화할 수 있습니다. **기능** 탭에서 **이집트 전자 송장(EG)** 기능이 포함된 행을 선택한 다음 적절하게 선택합니다. 외부 시스템에서 Dynamics 365 온라인 서비스로 가져온 데이터에는 당사의 [개인 정보 처리 방침](https://go.microsoft.com/fwlink/?LinkId=512132)이 적용됩니다. 자세한 내용은 국가별 기능 설명서의 "개인 정보 보호 고지" 섹션을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 송장 발행 개요](e-invoicing-service-overview.md)
- [전자 송장 발행 서비스 관리 시작](e-invoicing-get-started-service-administration.md)
- [전자 송장 발행 시작](e-invoicing-get-started.md)
- [이집트의 고객 전자 송장](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
