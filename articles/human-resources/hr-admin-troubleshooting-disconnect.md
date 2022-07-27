---
title: 클라이언트 연결 끊김
description: 이 항목에서는 고객의 환경 연결이 끊긴 경우 수행할 작업에 대해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
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
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452674"
---
# <a name="client-disconnects"></a>클라이언트 연결 끊김


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**환경 세부 정보** 

이 문제는 모든 환경에서 발생할 수 있습니다.
 
**징후** 

고객이 환경과 연결이 끊겼으며 그 이유를 알지 못합니다. 고객에게 다음 오류 메시지 중 하나가 표시됩니다.

- 연결이 끊어졌습니다. 작업을 계속하려면 닫기를 클릭하십시오.
- 네트워크 연결이 끊긴 것 같습니다. 다시 시도하려면 다시 시도를 클릭하십시오.

**적신호**

이 문제는 사용자가 구현 단계에 있고 운영 및 테스트 환경에서 정보를 비교하며 세션 간에 이동하는 것을 잊어버릴 때 종종 발생합니다. 사용자가 이 단계에 있으면 이 문제가 발생할 가능성이 높습니다.

**문제** 

**브라우저 종류:** Google Chrome, Internet Explorer, Microsoft Edge

Microsoft Dynamics 365 Human Resources는 동일한 사용자 및 브라우저 유형에 대해 두 개의 서로 다른 세션을 동시에 열면 사용자의 연결을 끊습니다. (예를 들어 사용자 A는 환경 1과 환경 2를 모두 Chrome에서 보고 있습니다.) 사용자가 다른 브라우저 창을 열든 다른 탭을 열든 상관 없습니다. 환경 1과 환경 2에 동시에 동일한 브라우저 유형으로 로그인하는 데 동일한 사용자 자격 증명이 사용되는 경우 Human Resources원은 세션 중 하나를 끊습니다.

**해결 방법**

한 브라우저 종류에서 한 번에 하나의 환경만 열려 있어야 합니다. 사용자는 동일한 환경(즉, 동일한 브라우저의 여러 탭)에 대해 여러 세션을 열 수 있습니다.

두 환경 사이를 동시에 이동하려는 사용자는 각 환경을 다른 브라우저 종류로 열어야 합니다. (예를 들어 사용자 A는 Chrome에서 환경 1, Microsoft Edge에서 환경 2를 볼 수 있습니다.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
