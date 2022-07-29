---
title: 계정 코드집 구분 기호를 고유하게 설정
description: 이번에는 계정 코드집 및 차원 값에 대해 동일한 구분 기호를 사용할 수 없는 방법에 대해 설명합니다. 업그레이드 후 구분 기호 값을 변경해야 합니다.
author: panolte
ms.date: 09/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: a19dc8926df0efeac242e2e42ac37fdad91df9f8
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "8460786"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>계정 코드집 구분 기호를 고유하게 설정

[!include [banner](../includes/banner.md)]

Microsoft Dynamics AX 2012년에는 계정 코드집 및 차원 값에 동일한 구분 기호를 사용할 수 있습니다. 현재 버전의 Finance and Operations에서는 계정 코드집 및 차원 값에 대해 동일한 구분 기호를 사용할 수 없습니다. 중복 구분자가 있는 경우 업그레이드 후 변경할 수 있습니다. 

## <a name="update-delimiter"></a>구분자 업데이트
계정 코드집과 충돌하는 경우 계정 코드집 구분 기호 및 프로젝트/하위 프로젝트 ID 형식을 변경할 수 있습니다. 다른 차원 구분 기호는 변경할 수 없습니다. 
- 업그레이드 후 계정 코드집 구분 기호를 변경할 수 있습니다. **총계정원장 매개 변수** > **계정과목표 및 차원** > **구분 기호 변경**. 
- 프로젝트/하위 프로젝트 ID 형식과만 충돌하는 경우 **프로젝트 관리 및 회계 매개 변수** > **일반** > **하위 프로젝트 형식 수정** 에서 해당 값을 변경할 수 있습니다. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>환경에 업데이트된 구분 기호가 필요한지 확인하는 방법 
업그레이드된 환경의 구분 기호가 충돌하는 경우 세그먼트 입력 컨트롤 또는 차원 입력 컨트롤에 값을 입력할 때 불안정해질 수 있습니다. 즉, 계정 및 차원 조합을 입력할 때 항상 조회 또는 플라이아웃 메뉴를 사용해야 합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
