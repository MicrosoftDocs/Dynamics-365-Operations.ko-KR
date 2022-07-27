---
title: 화물 템플릿
description: 이 토픽에서는 화물 템플릿을 설정하는 방법과 화물 템플릿을 새 로드와 연결하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 694860d1ade74f9fd51a8ac579aa69fe7fb673a8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448255"
---
# <a name="load-templates"></a>화물 템플릿

[!include [banner](../../includes/banner.md)]

새 하중을 생성할 때 화물 템플릿을 할당할 수 있습니다. 화물 템플릿에는 장비에 대한 정보와 하중의 높이, 너비, 깊이 및 부피와 같은 측정값에 대한 정보가 포함되어 있습니다.

이 토픽에서는 화물 템플릿을 설정하는 방법과 화물 템플릿을 새 로드와 연결하는 방법에 대해 설명합니다.

## <a name="set-up-a-load-template"></a>화물 템플릿 설정

1. **운송 관리 \> 설정 \> 로드 빌딩 \> 화물 템플릿** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 새 등급 프로필을 추가하거나 **편집** 을 선택하여 기존 프로필을 편집합니다.
1. 신규 또는 기존 템플릿 행에서 다음 필드를 설정합니다.

    - **화물 템플릿 ID** – 화물 템플릿의 고유 식별자(ID)를 입력합니다.
    - **장비** – 화물을 운송하는 데 사용해야 하는 장비를 선택합니다.
    - **화물 높이**, **화물 너비** 및 **화물 깊이** – 화물의 치수를 입력합니다.
    - **최대 허용 화물 부피** 및 **최대 허용 화물 중량** – 화물의 최대 허용 부피와 중량을 입력합니다.
    - **최대 허용 총 중량** – 화물의 최대 허용 총 중량을 입력합니다. 화물의 총 중량에는 자체 중량과 적재 중량이 모두 포함됩니다.
    - **허용되는 최대 화물 개수** – 화물이 담을 수 있는 최대 화물 개수를 입력합니다.
    - **바닥에 쌓인 하중** – 바닥 하중을 사용하려면 이 확인란을 선택합니다. 바닥 하중 시나리오에서 상자는 수용량을 최대화하기 위해 컨테이너 내부에서 바닥에서 천장으로, 벽에서 벽으로 쌓입니다.

1. 작업 창에서 **저장** 을 선택합니다.

## <a name="associate-a-load-template-with-a-new-load"></a>화물 템플릿을 새 화물에 연결

1. **운송 관리 \> 계획 \> 적재 계획 워크벤치** 로 이동합니다.
1. 페이지 상단에서 화물을 생성하는 소스 문서 유형에 따라 **선적**, **판매 라인**, **이전 라인** 또는 **구매 주문 라인** 탭 중 하나를 선택합니다. 
1. 적재를 계획할 특정 문서를 선택합니다.
1. 작업 창의 **수요 및 공급** 탭에 있는 **추가** 그룹에서 **새 화물로** 를 선택합니다.
1. **화물 탬플릿** 대화 상자의 **화물 템플릿 ID** 필드에서 적용할 템플릿을 선택합니다.
1. **확인** 을 선택하여 템플릿을 적용합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]