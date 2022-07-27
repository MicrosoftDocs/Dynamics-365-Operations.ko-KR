---
title: Human Resources 라이브 전환 준비
description: 이 페이지에서는 Dynamics 365 Human Resources로 라이브 전환을 준비하는 방법에 대한 안내를 제공합니다.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ff7d689129a4015b6085685f4b19ae61bdd549d2
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452233"
---
# <a name="prepare-for-human-resources-go-live"></a>Human Resources 라이브 전환 준비

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../includes/peap-2.md)]

이 항목에서는 Microsoft Dynamics Lifecycle Services(LCS)를 사용하여 Dynamics 365 Human Resources 프로젝트의 라이브 전환을 준비하는 방법을 설명합니다. 

이 그래픽은 라이브 전환 프로세스의 단계를 보여줍니다. 

![라이브 전환 프로세스.](./media/hr-admin-go-live-prepare-process.png)

다음 표에는 프로세스의 모든 단계, 예상 기간 및 작업 담당자가 나옵니다.

| 단계 | 작업 | 기간/시기 | 담당자 | 메모 |
| --- | --- | --- | --- |--- |
| 1 | LCS에서 라이브 전환 날짜 업데이트 | 최소한 2~3개월 전 | 파트너/고객 | 이정표 날짜는 지속적으로 최신 상태로 유지되어야 합니다. |
| 2 | 체크리스트 완료 및 보내기 | UAT(User Acceptance Test)가 완료된 후 | 파트너/고객 | [FastTrack 라이브 전환 평가](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment)에 나오는 지침을 따르세요. |
| 3 | 프로젝트 평가(FastTrack) | FastTrack 설계자* | 설계자는 체크리스트를 받은 후 평가를 제공하고 의문이 해결되고 해당되는 경우 완화 조치가 마련될 때까지 검토를 계속합니다. |
| 4 | 프로젝트 워크샵(FastTrack) | FastTrack 설계자* | |
| 5 | 데이터 패키지 가져오기 | 프로젝트에 따라 다름 | 파트너/고객 | [데이터 관리 개요](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)의 지침을 따르세요.|
| 6 | 프로덕션 준비 완료 | 이전 단계가 모두 완료된 후 | 파트너/고객 | 파트너/고객이 프로덕션 환경을 통제할 수 있습니다.|
| 7 | 전환 활동 | 프로젝트에 따라 다름 | 파트너/고객 | |
| 8 | 라이브 전환 | 프로젝트에 따라 다름 | 고객 | |

> [!IMPORTANT]
> *3단계와 4단계는 FastTrack 자격이 있는 고객만 완료하면 됩니다.

## <a name="completing-the-lcs-methodology"></a>LCS 방법론 완료

각 구현 프로젝트의 주요 이정표는 프로덕션 환경으로의 전환입니다. 단계를 완료하는 프로세스는 두 부분으로 구성됩니다. 

- Fit-Gap 분석 또는 UAT(User Acceptance Test)와 같은 실제 작업을 수행합니다. 
- LCS 방법론의 해당 단계를 완료된 것으로 표시합니다. 

구현을 진행하면서 방법론의 단계를 완료하는 것이 좋습니다. 마지막 순간까지 기다리지 마세요. 견고하게 구현하는 것이 고객에게 가장 유리합니다. 

## <a name="uat-for-your-solution"></a>솔루션을 위한 UAT

UAT 단계 중에는 구현 프로젝트의 샌드박스 환경에서 구현한 모든 비즈니스 프로세스와 사용자 지정을 테스트해야 합니다. 성공적인 라이브 전환을 보장하려면 UAT 단계를 완료할 때 다음을 고려해야 합니다. 

- UAT 프로세스를 시작하기 전에 골드 구성의 데이터가 환경으로 복사되는 깨끗하고 새로운 환경에서 UAT 프로세스를 시작하는 것이 좋습니다. 실제 환경이 프로덕션이 되는 라이브 전환 시점까지 프로덕션 환경을 골드 환경으로 사용하는 것이 좋습니다.
- 테스트 케이스는 요구 사항의 전체 범위를 다룹니다. 
- 마이그레이션된 데이터로 테스트합니다. 여기에는 근로자, 업무 및 직위와 같은 데이터가 포함되어야 합니다. 휴가 및 휴무 적립과 같은 개시 잔액도 포함합니다. 마지막으로 현재 혜택 등록과 같은 미결 거래를 포함합니다. 데이터 세트가 확정되지 않은 경우에도 모든 유형의 데이터로 테스트를 완료합니다. 
- 사용자에게 할당된 올바른 보안 역할(기본 역할 및 사용자 지정 역할)을 사용하여 테스트합니다. 
- 솔루션이 회사 및 산업별 규정 요구 사항을 준수하는지 확인합니다. 
- 모든 기능을 문서화하고 고객의 승인과 인정을 받습니다. 

## <a name="mock-go-live"></a>모의 라이브 전환

라이브 전환 전에 레거시 시스템에서 새 시스템으로 전환하는 데 필요한 단계를 테스트하는 모의 라이브 전환을 수행해야 합니다. 샌드박스 환경에서 모의 라이브 전환을 수행하고 전환 계획에 모든 단계를 포함해야 합니다.

- 라이브 전환 전까지 프로덕션 환경을 골드 구성 환경으로 사용하는 것이 좋습니다.
- 라이브 전환 전에 우발적인 트랜잭션이나 업데이트로부터 프로덕션 환경을 보호할 수 있는 견고한 거버넌스 프로세스를 마련하세요.
- UAT 또는 모의 라이브 전환을 수행할 준비가 되면 프로덕션 환경에서 샌드박스 환경을 새로 고칩니다. 자세한 내용은 [인스턴스 복사](hr-admin-setup-copy-instance.md)를 참조하세요.
- 샌드박스 환경에서 전환 계획의 각 단계를 테스트한 다음 해당 환경의 UAT 스크립트에서 스폿 검사나 테스트를 수행하여 샌드박스 환경을 검증합니다.
  - 테스트에는 라이브 전환에 필요한 변환을 포함한 모든 데이터 마이그레이션이 포함되어야 합니다.
  - 이 프로세스에는 모든 레거시 시스템의 관행 중단이 포함되어야 합니다.
  - 모의 전환은 통합 전환 단계 또는 외부 시스템 단계를 포함해야 합니다.
- 모의 전환 중에 문제가 발견되면 두 번째 모의 전환이 필요할 수 있습니다. 따라서 프로젝트 계획에서 두 번의 모의 전환을 계획하는 것이 좋습니다.

## <a name="fasttrack-go-live-assessment"></a>FastTrack 라이브 전환 평가

FastTrack 자격이 있고 FastTrack Solution Architect에 참여하는 고객은 Microsoft FastTrack으로 라이브 전환 검토를 완료합니다. 자세한 내용은 [Microsoft FastTrack](/dynamics365/fasttrack/)을 참조하세요. 

라이브 전환 약 8주 전에 FastTrack 팀에서 [라이브 전환 체크리스트](https://go.microsoft.com/fwlink/?linkid=2146013) 작성을 요청합니다.

프로젝트 관리자 또는 주요 프로젝트 구성원은 프로젝트의 라이브 전환 전 단계에서 라이브 전환 체크리스트를 작성해야 합니다. 일반적으로 체크리스트는 UAT가 완료되거나 거의 완료되는 제안된 라이브 전환 날짜보다 4~6주 전에 작성합니다. 

라이브 전환 체크리스트를 완료하면 FastTrack Solution Architect에게 이메일로 보내주세요. 항상 이메일에 고객과 구현 파트너의 주요 이해 관계자를 포함해야 합니다. 

체크리스트를 제출하면 FastTrack Solution Architect가 프로젝트를 검토하고 프로젝트의 성공적인 라이브 전환을 위한 잠재적 위험, 모범 사례 및 권장 사항을 설명하는 평가를 제공합니다. 때에 따라 Solution Architect가 위험 요소를 지적하고 완화 계획을 요청할 수 있습니다. 

## <a name="see-also"></a>참고 항목

[라이브 전환 FAQ](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
