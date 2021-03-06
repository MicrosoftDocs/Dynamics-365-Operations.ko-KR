---
title: 제품 구성 모델 설정
description: 이 문서에서는 제품 구성 모델을 설정하고 생성하는 단계를 설명합니다.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dc9f46d91dc298a5c8babee2b370fea09f61741
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449089"
---
# <a name="set-up-a-product-configuration-model"></a>제품 구성 모델 설정

[!include [banner](../includes/banner.md)]

이 문서에서는 제품 구성 모델을 설정하고 생성하는 단계를 설명합니다.

| 작업                                                        | 설명                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 제품 마스터를 만듭니다.                                    | **제품 마스터** 목록에서 제품 마스터를 작성합니다. 모든 관련 회사에 제품 마스터를 릴리스합니다. 제품 구성 모델의 버전 또는 하위 구성 요소로 사용되는 제품 마스터의 경우 구성 기술로 **제약 기반 구성** 을 선택해야 하며 구성 차원은 제품 크기 그룹에 대해서만 선택해야 합니다. |
| 구성 요소를 만듭니다.                                          | **구성 요소** 페이지에서 구성 요소를 생성합니다. 구성 요소는 제품 구성 모델의 빌딩 블록이며 여러 제품 구성 모델에서 재사용할 수 있습니다.                                                                                                                                                                                                                      |
| 특성 유형을 생성합니다.                                     | **특성 유형** 페이지에서 특성 유형을 생성합니다. 특성 유형은 제품 구성 모델에 사용되는 모든 특성에 대한 데이터 형식 세트를 지정합니다. **부울** 특성, 고정 목록이 있는 **텍스트** 및 범위 유형이 있는 **정수** 는 제품 구성 모델을 기반으로 제품 변형을 구성할 때 사용할 수 있는 값 집합을 나열합니다.       |
| 제품 구성 모델을 만듭니다.                       | **새 제품 구성 모델** 페이지에서 제품 구성 모델을 작성합니다.                                                                                                                                                                                                                                                                                                              |
| 제품 구성 모델에 특성을 추가합니다.            | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지의 **특성** 빠른 탭에서 특성을 생성합니다. 특성은 제품 구성 모델의 기능을 설명합니다.                                                                                                                                                                                                       |
| 제품 구성 모델에 제약 조건을 추가합니다.           | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지의 **제약 조건** 빠른 탭에서 제약 조건을 생성합니다. 제약 조건은 제품 구성이 충족해야 하는 제한 사항입니다. 제약 조건은 표현식 제약 조건 또는 테이블 제약 조건입니다.                                                                                                                                 |
| 제품 구성 모델에 하위 구성 요소를 추가합니다.         | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지의 **하위 구성 요소** 빠른 탭에서 하위 구성 요소를 생성합니다. 하위 구성 요소는 구성 요소와 관련이 있으며 하위 구성 요소를 나타내는 항목에 연결됩니다.                                                                                                                                                                       |
| 제품 구성 모델에 사용자 요구 사항을 추가합니다.     | 사용자 요구 사항은 하위 구성 요소와 유사하지만 항목을 참조하지 않습니다. 사용자 요구 사항을 팬텀 BOM으로 생각할 수 있습니다. 사용자 요구 사항 바로 아래에 있는 모든 BOM 라인 또는 경로 작업은 상위 구성요소로 축소됩니다.                                                                                                                       |
| 제품 구성 모델에 BOM 라인을 추가합니다.             | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지의 **BOM 라인** 빠른 탭에서 BOM 라인을 생성합니다. BOM 라인은 제품의 변형을 만드는 데 필요한 부품을 나타냅니다.                                                                                                                                                                                                 |
| 제품 구성 모델에 경로 작업을 추가합니다.      | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지의 **경로 작업** 빠른 탭에서 경로 작업을 생성합니다. 경로 작업은 제품의 변형을 만들기 위해 수행되는 일련의 단계 중 한 단계를 나타냅니다.                                                                                                                                                    |
| 제품 구성 모델에 대한 활성 버전을 만듭니다. | **버전** 페이지에서 제품 구성 모델의 활성 버전을 작성합니다. 버전은 제품 구성 모델과 제품 마스터 간의 관계입니다. 활성 버전이 있는 제품 구성 모델은 판매 주문, 판매 견적, 구매 주문 또는 생산 주문에서 구성할 수 있습니다.                                                               |
| 제품 구성 모델을 테스트합니다.                         | **제약 조건 기반 제품 구성 모델 세부 정보** 페이지 또는 **제품 구성 모델 목록** 페이지에서 제품 구성 모델을 테스트합니다. 제품 구성 모델 테스트는 주문 처리 중에 발생하는 제품 모델 구성 프로세스를 시뮬레이션합니다.                                                                                                |
| 제품 구성 모델 템플릿을 만듭니다.                | **구성 템플릿** 페이지에서 제품 구성 모델 템플릿을 작성합니다. 구성 템플릿에는 제품 구성 모델의 특성 값이 포함됩니다. **라인 구성** 페이지에서 특성 값을 선택합니다. 제품 모델 구성 중에 제품 모델 구성 템플릿을 로드하도록 선택할 수 있습니다.                                                   |
| 항목을 구성합니다.                                          | 제품 구성 모델은 판매 주문, 판매 견적, 구매 주문 또는 생산 주문에서 구성할 수 있습니다.                                                                                                                                                                                                                                                                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]