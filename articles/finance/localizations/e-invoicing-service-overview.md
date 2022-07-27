---
title: 전자 송장 발행 개요
description: 이 항목에서는 Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management의 전자 송장 발행에 대한 개요를 제공합니다.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
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
ms.openlocfilehash: 23a98706bc2ab0abc2c72e9f20d8e8fbff56b2b9
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451705"
---
# <a name="electronic-invoicing-overview"></a>전자 송장 발행 개요

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management용 전자 송장 발행은 전자 송장의 구성 가능한 처리 및 구성 가능한 전자 문서 교환을 가능하게 하는 확장 가능한 다중 테넌트 서비스입니다. 처리 및 통합 규칙은 완전히 구성할 수 있으며 논리는 Finance 및 Supply Chain Management 외부에서 실행됩니다. 이 서비스는 주로 기업 대 정부 시나리오에서 전자 송장 문서 처리를 대상으로 합니다. 그러나 다양한 유형의 문서에 대한 B2B 시나리오와 같은 다른 목적을 위해 사용자 지정 구성할 수 있습니다.

전자 송장 발행은 다음 목표를 달성하는 데 도움이 될 수 있습니다.

- 국가/지역별 요구 사항을 빠르고 쉽게 채택
- 전자 송장 발행 솔루션 구현 표준화
- 문서 기록의 추적성 향상
- 구현 주기 단축
- 총 소유 비용(TCO) 감소
- 코드 변경이 필요 없는 쉽게 조정 가능한 구성
- 단순화된 구성 패키징
- 내장된 내보내기, 가져오기 및 통합 기능과 전자 송장 문서 처리의 간편한 확장성
- 회사 전체에서 동일한 내보내기, 가져오기 및 통합 구성을 쉽게 재사용

## <a name="service-availability"></a>서비스 가용성

현재 전자 송장 발행 기능은 Finance 및 Supply Chain Management 고객이 사용할 수 있습니다. 자세한 내용은 애플리케이션의 라이선스 계약조건을 검토하십시오.

국가/지역별 요구 사항을 해결하는 기능은 릴리스의 여러 단계에서 제한될 수 있으므로 지원되는 국가/지역별 솔루션의 적용 범위와 범위를 설명하는 최신 문서를 항상 검토해야 합니다.

전자 송장 발행은 다음 Azure 지리에 배포됩니다.

- 미국
- 유럽
- 아시아

> [!NOTE]
> 전자 송장 발행은 온-프레미스 배포를 지원하지 않습니다.

## <a name="feature-highlights"></a>기능 하이라이트

- Finance 및 Supply Chain Management와 즉시 통합
- 모든 국가 및 지역에 대한 전자 송장 프로세스의 구성 및 모니터링을 위한 일관된 사용자 환경
- 새로운 국가 또는 지역에서 전자 송장 발행 솔루션을 더 빠르고 쉽고 저렴하게 채택
- RCS(Regulatory Configuration Service) 및 세계화 기능 설정을 통한 서비스 구성
- RCS에 정의된 구성을 사용하여 비즈니스 데이터를 여러 전자 송장 형식(XML, JSON\[JavaScript Object Notation\], TXT 및 CSV\[Comma-Separated Value\])으로 변환:

    - 전자 송장 변환에 대한 구성 가능성을 사용할 수 없는 국가 및 지역에서 사용할 수 있는 전자 보고(ER) 형식

- 디지털 서명을 통한 인증 처리를 포함하여 외부 웹 서비스에 구성 가능한 전자 송장 제출:

    - 여러 국가 및 지역의 추가 콘텐츠와 내장, 쉽게 확장 및 구성 가능한 통합

- 구성 가능한 예외 메시지 처리를 포함하여 웹 서비스의 응답 처리
- 전자 서명 지원(예: XMLDSig 서명 알고리즘을 사용하는 전자 서명)
- 문서를 이메일로 보내고 SharePoint에 저장하는 기능
- 전자 송장 메시지 일괄 처리
- 수신 문서의 구성 가능한 변환 및 Finance 및 Supply Chain Management에서 해당 문서 처리
- 이메일 및 SharePoint와 같은 채널에서 들어오는 문서를 수신하는 기능

## <a name="privacy-notice"></a>개인정보보호 통지

전자 송장 발행을 활성화하고 사용하려면 제한된 데이터를 보내야 할 수 있습니다. 이 데이터에는 조직의 납세자 등록 ID가 포함됩니다. 이 데이터는 정부 웹 서비스와의 통합에 필요한 사전 정의된 형식으로 전자 송장을 보낼 목적으로 세무 당국이 승인한 타사 기관으로 전송됩니다. 이러한 외부 시스템에서 Dynamics 365 온라인 서비스로 가져온 데이터에는 당사의 [개인 정보 처리 방침](https://go.microsoft.com/fwlink/?LinkId=512132)이 적용됩니다. 자세한 내용은 국가/지역별 기능 설명서의 "개인 정보 보호 고지" 섹션을 참조하십시오.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
