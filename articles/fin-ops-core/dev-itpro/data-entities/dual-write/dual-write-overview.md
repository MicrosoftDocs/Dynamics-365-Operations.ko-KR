---
title: 이중 쓰기 개요
description: 이번에는 고객 참여 앱과 재무 및 운영 앱 간의 거의 실시간 상호 작용을 제공하는 이중 쓰기 개요를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f39322a0c2ef50ef2bbeb256c80096e0687c4642
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460815"
---
# <a name="dual-write-overview"></a>이중 쓰기 개요

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>이중 쓰기란 무엇입니까?

이중 쓰기는 고객 참여 앱과 재무 및 운영 앱 간의 거의 실시간 상호 작용을 제공하는 즉시 사용 가능한 인프라입니다. 고객, 제품, 사람 및 운영에 대한 데이터가 애플리케이션 경계를 넘어 흐르면 조직의 모든 부서에 권한이 부여됩니다.

이중 쓰기는 재무 및 운영 앱과 Dataverse. 재무 및 운영 앱의 모든 데이터 변경은 Dataverse에 대한 쓰기를 유발하고 모든 데이터 변경은 재무 및 운영 앱의 Dataverse 쓰기를 유발합니다. 이 자동화된 데이터 흐름은 앱 전반에 걸쳐 통합된 사용자 경험을 제공합니다.

![앱 간의 데이터 관계.](media/dual-write-overview.jpg)

이중 쓰기에는 *인프라* 측면과 *애플리케이션* 측면의 두 가지 측면이 있습니다.

### <a name="infrastructure"></a>하부 구조

이중 쓰기 인프라는 확장 가능하고 안정적이며 다음과 같은 주요 기능을 포함합니다.

+ 애플리케이션 간의 동기 및 양방향 데이터 흐름
+ 온라인 및 오프라인/비동기 모드 동안 시스템을 지원하기 위해 재생, 일시 중지 및 따라잡기 모드와 함께 동기화합니다.
+ 애플리케이션 간의 초기 데이터 동기화 기능
+ 데이터 관리자를 위한 활동 및 오류 로그의 결합된 보기
+ 사용자 지정 경고 및 임계값을 구성하고 알림을 구독하는 기능
+ 필터링 및 변환을 위한 직관적인 UI(사용자 인터페이스)
+ 테이블 종속성 및 관계 설정 및 보기 기능
+ 표준 및 사용자 지정 테이블과 맵 모두에 대한 확장성
+ 안정적인 애플리케이션 수명 주기 관리
+ 신규 고객을 위한 즉시 사용 가능한 설정 환경

### <a name="application"></a>응용 프로그램

이중 쓰기는 재무 및 운영 앱의 개념과 고객 참여 앱의 개념 간에 매핑을 만듭니다. 이 통합은 다음 시나리오를 지원합니다.

+ 통합 고객 마스터
+ 고객 충성도 카드 및 보상 포인트에 대한 액세스
+ 통합 제품 마스터링 경험
+ 조직 계층에 대한 인식
+ 통합 공급 업체 마스터
+ 재정 및 세금 참조 데이터에 대한 액세스
+ 주문형 가격 엔진 경험
+ 통합 잠재 고객 대 현금 경험
+ 현장 에이전트를 통해 사내 자산과 고객 자산 모두에 서비스를 제공할 수 있는 능력
+ 통합 조달-지급 경험
+ 고객 데이터 및 문서에 대한 통합 활동 및 메모
+ 보유 재고 가용성 및 세부 정보 조회 기능
+ 프로젝트-캐시 경험
+ 파티 개념을 통해 여러 주소 및 역할을 처리하는 기능


## <a name="top-reasons-to-use-dual-write"></a>이중 쓰기를 사용하는 주요 이유

이중 쓰기는 Microsoft Dynamics 365 애플리케이션에서 데이터 통합을 제공합니다. 이 강력한 프레임워크는 환경을 연결하고 다양한 비즈니스 애플리케이션이 함께 작동할 수 있도록 합니다. 이중 쓰기를 사용해야 하는 주요 이유는 다음과 같습니다.

+ 이중 쓰기는 재무 및 운영 앱과 고객 참여 앱 간에 긴밀하게 결합된 거의 실시간 양방향 통합을 제공합니다. 이러한 통합을 통해 Microsoft Dynamics 365는 모든 비즈니스 솔루션을 위한 원스톱 쇼핑을 할 수 있습니다. Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management를 사용하지만 CRM(고객 관계 관리)에 타사 솔루션을 사용하는 고객은 이중 쓰기 지원을 위해 Dynamics 365로 이동하고 있습니다.
+ 고객, 제품, 운영, 프로젝트 및 사물 인터넷(IoT)의 데이터가 이중 쓰기를 통해 Dataverse 자동으로 흐릅니다. 이 연결은 Power Platform 확장에 관심이 있는 비즈니스에 유용합니다.
+ 이중 쓰기 인프라는 코드 없는/낮은 코드 원칙을 따릅니다. 표준 테이블 간 맵을 확장하고 사용자 지정 맵을 포함하려면 최소한의 엔지니어링 노력이 필요합니다.
+ 이중 쓰기는 온라인 모드와 오프라인 모드를 모두 지원합니다. Microsoft는 온라인 및 오프라인 모드를 지원하는 유일한 회사입니다.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>고객 참여 앱의 개발자와 설계자에게 이중 쓰기는 무엇을 의미합니까?

이중 쓰기는 재무 및 운영 앱과 고객 참여 앱 간의 데이터 흐름을 자동화합니다. 이중 쓰기는 Dataverse에 설치된 두 가지 AppSource 솔루션으로 구성됩니다. 솔루션은 Dataverse 테이블 스키마, 플러그인 및 워크플로를 확장하여 ERP 크기로 확장할 수 있습니다. 성공적인 구현을 위해 고객 참여 앱의 개발자와 설계자는 이러한 변경 사항을 이해하고 재무 및 운영 앱에 대해 해당 상대와 협력해야 합니다.

재무 및 운영 애플리케이션과 패리티를 생성하기 위해 이중 쓰기는 Dataverse 스키마에서 몇 가지 중요한 변경을 수행합니다. 계획을 이해하면 향후 일부 설계 및 개발 재작업을 피할 수 있습니다.

+ 이중 쓰기 AppSource 패키지가 설치되면 Dataverse 회사 및 파티와 같은 새로운 개념이 생깁니다. 이러한 개념은 Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service 및 Dynamics 365 Field Service를 포함하여 구축된 Dataverse 애플리케이션이 재무 및 운영 앱과 원활하게 상호 작용하는 데 도움이 됩니다.

+ 활동과 메모가 통합되고 확장되어 C1(시스템 사용자)과 C2(시스템 고객)를 모두 지원합니다.

+ 재무 및 운영 앱과 Dataverse 간의 통화 전송 중 데이터 손실을 방지하기 위해 고객 참여 앱의 통화 데이터 유형에서 소수점 이하 자릿수를 확장할 수 있습니다. 이 기능은 메타데이터 계층에서 기존 행을 새로운 확장 상태로 자동 번역합니다. 이 과정에서 통화 값은 통화 데이터가 아닌 소수 데이터로 변환되며 통화 값은 소수점 이하 10자리를 지원합니다. 이 기능은 옵트인이며 소수점 이하 4자리 이하의 정밀도가 필요하지 않은 조직은 옵트인할 필요가 없습니다. 자세한 내용은 [이중 쓰기를 위한 통화 데이터 유형 마이그레이션](currrency-decimal-places.md)을 참조하십시오.

+ [날짜 유효성](../../dev-tools/date-effectivity.md)이 Dataverse에 추가됩니다. 동일한 테이블에서 과거, 현재 및 미래 데이터를 지원합니다.

+ 제품 [단위 변환](../../../../supply-chain/pim/tasks/manage-unit-measure.md)은 제품, 견적, 주문 및 송장에 대해 지원됩니다.

예정된 변경 사항에 대한 자세한 내용은 [이중 쓰기의 새로운 기능 또는 변경된 사항](whats-new-dual-write.md)을 참조하십시오.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
