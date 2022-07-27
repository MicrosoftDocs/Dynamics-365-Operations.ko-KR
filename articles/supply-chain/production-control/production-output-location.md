---
title: 생산 출력 위치
description: 이 항목에서는 생산 출력 위치를 식별하는 데 사용되는 계층 구조에 대해 설명합니다.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f4c8086e9179ff51f62ce77620af96360c6123060372dfd1c0e06dad79998b75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446689"
---
# <a name="production-output-location"></a>생산 출력 위치

[!include [banner](../includes/banner.md)]

이 항목에서는 생산 출력 위치를 식별하는 데 사용되는 계층 구조에 대해 설명합니다.

생산 출력 위치는 완제품이 생산된 후 처음으로 저장되는 위치입니다. 일반적으로 이 위치는 완제품을 생산하는 생산 공정과 가깝습니다. 생산 출력 위치는 선적 영역, 저장 위치, 다운스트림 생산 프로세스의 생산 입력 위치 등으로 이동하기 전에 자재의 중간 저장으로 사용됩니다. 

기본 생산 출력 위치는 완제품이 생산 주문 또는 배치 주문에 보고될 때 설정됩니다. 다음 계층은 이 출력 위치를 식별하는 데 사용됩니다.

1. 생산 주문 또는 배치 주문 헤더에 정의된 출력 위치를 사용하세요.
2. 위치를 찾을 수 없는 경우 생산 경로에 정의된 마지막 작업에서 사용하는 리소스에 정의된 출력 위치를 사용하세요.
3. 위치를 찾을 수 없는 경우 생산 경로에 정의된 마지막 작업에 대해 리소스에서 사용하는 리소스 그룹에 정의된 출력 위치를 사용합니다.
4. 위치가 없으면 생산 주문에 대해 정의된 창고에 정의된 출력 위치를 사용하세요.

기본 생산 출력 위치는 고급 창고 프로세스를 사용하여 설정한 제품에 대해서만 설정됩니다. 이러한 유형의 품목이 완제품으로 보고되면 **완제품 보관** 또는 **연산품 및 부산물 보관** 유형의 창고 작업이 생성됩니다. 이 유형의 작업은 생산 출력 위치를 선택 위치로 사용합니다. 보관 위치는 위치 지시문에 의해 결정됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]