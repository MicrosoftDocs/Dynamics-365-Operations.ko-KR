---
title: RCS 글로벌 리포지토리의 구성 중단
description: 이 항목에서는 RCS 글로벌 리포지토리의 구성을 중단하는 방법을 설명합니다.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 340fc96e7dfe56da9ee8d4831a5980e3e96ec3ee0f2f5a8fb2ab72f713de9737
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450133"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>RCS 글로벌 리포지토리의 구성 중단

[!include [banner](../includes/banner.md)]

이 항목에서는 RCS 글로벌 리포지토리의 구성을 중단하는 방법을 설명합니다. 이전에는 더는 필요하지 않은 구성을 삭제만 할 수 있었습니다. 이제 릴리스된 구성을 RCS 글로벌 리포지토리에서 **중단됨** 으로 표시할 수 있습니다. 이 기능을 다음과 같이 사용할 수도 있습니다. 
 
 - 구성이 중단될 예정이면 미리 알림을 제공합니다.
 - 교체 구성에 관한 적절한 세부 정보를 포함합니다.
 - 특정 구성의 **지원 종료일** 날짜를 설정하여 중단될 시기를 사용자에게 알립니다.

구성 버전을 중단할 때는 다음과 같은 선택적 정보를 지정할 수 있습니다.

  - **교체 구성**
  - **교체 구성 버전**
  - **자유 텍스트 메모**: 이 필드를 사용하여 설명서 링크나 참조를 제공합니다.
  - **지원 종료일** : 이 필드는 현재 구성/버전의 지원이 종료될 날짜를 제공합니다. 이 날짜는 수동으로 업데이트해야 합니다.
  
구성을 중단하려면 다음 단계를 완료합니다. 

1. **모든 버전** 을 **예** 로 설정하여 한 작업으로 같은 설정의 모든 버전을 중단할지 또는 단일 버전을 중단할지 선택합니다. 
2. **중단** 매개 변수를 **예** 로 설정합니다.
3. 구성을 중단하려면 **확인** 을 선택합니다. 변경 내용을 저장할 때 **중단 날짜** 필드가 자동으로 채워집니다.

![구성 정보를 중단합니다.](media/Discontinue-details-2.png)
  
언제든지 구성을 **공유** 로 되돌리거나 중단 정보를 조정할 수 있습니다. 구성을 공유하는 경우 **지원 종료일** 및 중단과 관련한 기타 모든 정보를 지정하여 향후 중단 계획을 전달하십시오.

실제로 구성을 중단하기 전에 계획된 중단에 관한 정보를 공유하려면 교체에 관한 모든 필드를 미리 입력하고 **중단** 매개 변수를 **아니요** 로 설정하면 됩니다.

> [!NOTE]
> 중단해도 구성 작업은 제한되지 않습니다. 계속해서 구성을 가져오기, 실행 또는 파생할 수 있습니다. 이러한 필드는 정보용입니다.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Finance는 버전 10.0.14부터 이 정보 표시를 지원합니다.

Dynamics 365 Finance는 버전 10.0.14부터 중단 정보 표시를 지원합니다. **글로벌 리포지토리** 페이지에서 중단에 관한 최신 정보를 볼 수 있습니다. 기본적으로 중단된 구성은 필터링됩니다.
  
**가져온 구성**(ERSolutionTable) 페이지에는 가져올 때 이미 중단된 구성이 표시됩니다. 가져온 후 중단된 구성의 경우 **구성 업데이트 가져오기** 작업을 실행하여 중단 정보를 동기화할 수 있습니다.


