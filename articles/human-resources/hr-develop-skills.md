---
title: 기술 구성
description: Dynamics 365 Human Resources에서 작업자의 기술을 추적할 수 있습니다. 특정 작업에 필요한 기술을 지정할 수도 있습니다.
author: twheeloc
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 13206bb3c961f001620e8b65a8b1bb39bf95ee49
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452683"
---
# <a name="configure-skills"></a>기술 구성

> [!IMPORTANT]
> 이 항목에서 언급한 기능은 현재 Finance 인프라의 Human Resources 고객이 사용할 수 있습니다.  


Dynamics 365 Human Resources에서 작업자의 기술을 추적할 수 있습니다. 특정 작업에 필요한 기술을 지정할 수도 있습니다.

추적할 수 있는 기술의 예는 다음과 같습니다.

- 감독 – 다른 사람의 작업을 감독하는 능력.
- 리더십 – 직원 및 비즈니스 영역을 이끄는 능력.
- 기획 – 앞을 내다보고, 비전 선언을 작성하고, 완수하는 능력.
- HTML – HTML 코드를 작성하는 능력.

기술 유형 및 평점 모델을 아직 설정하지 않은 경우 기술을 만들기 전에 일부 추가해야 합니다.

다음 사람들이 작업자의 기술을 입력할 수 있습니다.

- 작업자는 직원 셀프 서비스에서 자기 기술을 입력할 수 있습니다. 이러한 기술에는 관리자 승인이 필요합니다.
- 관리자는 직원의 기술을 입력할 수 있습니다. 이러한 기술을 자동 승인하는 워크플로를 만들 수 있습니다.

## <a name="create-a-skill-type"></a>기술 유형 만들기

기술 유형은 관리 또는 영업과 같이 개별 기술이 속하는 범주입니다.

1. **직원 개발** 작업 영역에서 **연결** 을 선택합니다.

2. **역량 설정** 에서 **기술 유형** 을 선택합니다.

3. **새로 만들기** 를 선택합니다.

4. 다음 필드를 입력합니다.

   - **기술 유형**: 기술 유형의 이름을 입력합니다.
   - **설명**: 기술 유형에 대한 설명을 입력합니다.

5. **저장** 을 선택합니다.

## <a name="create-a-rating-model"></a>평점 모델 만들기

평점 모델은 개인의 실제 기술 수준, 달성하기 위해 노력해야 하는 수준 또는 직무에 필요한 기술 수준을 평가하는 데 도움이 됩니다. 평점 모델의 각 수준에는 요소가 할당됩니다.

1. **직원 개발** 작업 영역에서 **연결** 을 선택합니다.

2. **역량 설정** 에서 **평점 모델** 을 선택합니다.

3. **새로 만들기** 를 선택합니다.

4. 다음 필드를 입력합니다.

   - **평점**: 평점 모델의 이름(예: **기술**)을 입력합니다.
   - **설명**: 평가 모델에 대한 설명(예: **기술 평점**)을 입력합니다.

5. **수준** 섹션에서 **새로 만들기** 를 선택합니다. 추가하려는 수준별로 다음 필드를 완료합니다.

   - **수준**: 수준의 이름을 입력합니다.
   - **설명**: 수준에 대한 설명을 입력합니다.
   - **계수** : 0~9 사이의 계수 값을 입력합니다. 계수는 다양한 평점 모델을 사용하는 기술 점수를 정규화하는 데 도움이 됩니다. 각 수준에는 고유한 계수가 있어야 합니다. 계수 값이 더 큰 수준은 평점 모델에서 더 높은 가중치를 가집니다.

   필요에 따라 수준을 계속 추가합니다. 각 평점 모델에 대해 최대 10개의 수준을 입력할 수 있습니다.

6. **저장** 을 선택합니다.

## <a name="create-a-skill"></a>기술 만들기

기술을 할당하거나 기술 매핑 검색 또는 기술 프로필을 만들려면 먼저 **기술** 페이지에서 기술에 관한 정보를 입력해야 합니다. 기술별로 기술 유형과 평점 모델을 선택할 수 있습니다.

1. **직원 개발** 작업 영역에서 **연결** 을 선택합니다.

2. **역량 설정** 에서 **기술** 을 선택합니다.

3. **새로 만들기** 를 선택합니다.

4. 다음 필드를 입력합니다.

   - **기술**: 기술의 이름을 입력합니다.
   - **설명**: 기술에 대한 설명을 입력합니다.
   - **평가**: 이 기술에 사용할 평점 모델을 선택합니다.
   - **기술 유형**: 기술 유형 목록에서 선택합니다.

5. **저장** 을 선택합니다.

## <a name="see-also"></a>참고 항목

[기술 입력](hr-develop-enter-skills.md)<br>
[기술 매핑](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
