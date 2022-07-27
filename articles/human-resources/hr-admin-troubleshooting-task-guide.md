---
title: 작업 가이드를 LCS에 저장하고 재생
description: 이 항목에서는 작업 가이드를 LCS(Microsoft Dynamics Lifecycle Services)에 저장한 다음 재생하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 54251aed1a54f626e5cd6cbd983e3eb4589a02e8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452440"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>작업 가이드를 LCS에 저장하고 재생


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**환경 세부 정보** 

Microsoft Dynamics 365 Human Resources는 Microsoft Dynamics Lifecycle Services(LCS)를 통해 배포됩니다.

**문제**

고객이 새 작업 기록을 LCS 프로젝트에 저장한 다음 저장된 작업 가이드를 재생하려고 합니다.

**해결**

다음 단계에 따라 작업 기록을 LCS에 저장합니다.

1. LCS에 로그인하고 프로젝트를 선택합니다.
2. **비즈니스 프로세스 모델러** 타일을 선택합니다.
3. "업데이트된 BPM 환경"에서 페이지를 봅니다.
4. 라이브러리를 선택한 후 **복사** 를 선택합니다.
5. 비즈니스 프로세스 모델러(BPM) 모델의 이름을 입력합니다.
6. LCS에서 Human Resources에 로그인합니다.
7. **검색** 필드에 **도움말** 을 입력합니다. Lifecycle Services 도움말이 열립니다.
8. Lifecycle Services 도움말 구성에서 **새로 고침** 버튼을 선택합니다.

    새 BPM 라이브러리가 나타나고 활성 상태가 됩니다.

9. 페이지를 닫습니다.
10. 작업 기록을 만듭니다.
11. 완료했으면 **Lifecycle Services에 저장** 을 선택합니다.

    ![Lifecycle Services에 저장합니다.](media/task-guides.png)

12. 작업 기록을 저장할 BPM 라이브러리와 노드를 선택합니다.

다음 단계에 따라 LCS에서 작업 가이드를 재생합니다.

1. 작업 레코더를 시작합니다.
2. **LCS에서 열기** 를 선택합니다.
3. 라이브러리와 저장된 작업 가이드가 있는 BPM 노드를 선택합니다.
4. 작업 가이드를 엽니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
