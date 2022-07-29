---
title: Dataverse의 조직 계층 구조
description: 이 항목에서는 재무 및 운영 앱과 Dataverse 간의 조직 데이터 통합에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9174612743c68595d12dd223f0932ace1857c0fb
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8460970"
---
# <a name="organization-hierarchy-in-dataverse"></a>Dataverse의 조직 계층 구조

[!include [banner](../../includes/banner.md)]



Dynamics 365 Finance는 금융 시스템이므로 *조직* 은 핵심 개념이며 시스템 설정은 조직 계층의 구성으로 시작됩니다. 그런 다음 조직 수준 및 조직 계층 구조의 모든 수준에서 비즈니스 재무를 추적할 수 있습니다.

Dataverse에 조직 계층의 개념이 없더라도 총 판매 수익과 같은 몇 가지 느슨한 개념이 있습니다. Dataverse 통합의 일부로 조직 계층 데이터 구조가 Dataverse에 추가됩니다.

## <a name="data-flow"></a>데이터 흐름

재무 및 운영 앱과 Dataverse를 구성하는 비즈니스 에코시스템에 조직 계층이 계속 유지됩니다. 이 조직 계층은 재무 및 운영 앱을 기반으로 하지만 정보 제공 및 확장 목적으로 Dataverse에 공개됩니다. 다음 그림은 금융 및 운영 앱에서 Dataverse로 일반향 데이터 흐름으로 Dataverse에 노출된 조직 계층 정보를 보여줍니다.

![아키텍처 이미지.](media/dual-write-data-flow.png)

조직 계층 테이블 맵은 재무 및 운영 앱에서 Dataverse로 데이터의 단방향 동기화에 사용할 수 있습니다.

## <a name="templates"></a>템플릿

조직은 비즈니스 프로세스를 수행하거나 목표를 달성하기 위해 함께 일하는 사람들의 그룹입니다. 조직 계층은 비즈니스를 구성하는 조직 간의 관계를 나타냅니다. 법인, 운영 단위 및 팀과 같은 내부 조직 유형을 정의할 수 있습니다. 다음 표에서 볼 수 있듯이 법인, 운영 단위, 관련 조직 계층 정보를 동기화하기 위해 테이블 맵 모음이 생성됩니다.

금융 및 운영 앱 | Customer Engagement 앱     | 설명
-----------------------|--------------------------------|---
[법인](mapping-reference.md#102) | cdm_companies | 
[법인](mapping-reference.md#142) | msdyn_internalorganizations |
[운영 단위](mapping-reference.md#143) | msdyn_internalorganizations |
[조직 계층 구조 - 게시됨](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | 이 템플릿은 조직 계층 게시 테이블의 단방향 동기화를 제공합니다.
[조직 계층 구조 목적](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | 이 템플릿은 조직 계층 목적 테이블의 단방향 동기화를 제공합니다.
[조직 계층 구조 유형](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | 이 템플릿은 조직 계층 유형 테이블의 단방향 동기화를 제공합니다.

## <a name="internal-organization"></a>내부 조직

Dataverse의 내부 조직 정보는 **운영 단위** 및 **법인** 의 두 테이블에서 가져옵니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
