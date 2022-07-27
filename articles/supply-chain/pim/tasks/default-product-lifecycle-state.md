---
title: 기본 제품 수명 주기 상태 생성
description: 이 절차에서는 기본 제품 수명 주기 상태를 생성하는 방법과 기본 상태를 출시된 제품과 연결하는 방법을 보여줍니다.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a628ed2b609f48c22076f409889c212e4d9463ac
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449083"
---
# <a name="create-a-default-product-lifecycle-state"></a>기본 제품 수명 주기 상태 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 기본 제품 수명 주기 상태를 생성하는 방법과 기본 상태를 출시된 제품과 연결하는 방법을 보여줍니다.


## <a name="create-a-default-lifecycle-state"></a>기본 수명 주기 상태 생성
1. 제품 정보 관리 > 설정 > 제품 수명 주기 상태로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 상태 필드에 값을 입력합니다.
4. 법인으로 출시될 때 기본값 필드에서 예를 선택합니다.
5. 설명 필드에 값을 입력합니다.
6. 계획에 대해 활성 상태임 필드에서 아니요를 선택합니다.

> [!NOTE]
> 신규 출시 제품이 기준 계획에 포함되지 않아야 하는 경우 아니요를 선택합니다. 기준 계획에 포함해야 하는 경우 컨트롤을 기본값인 예로 둡니다.  

## <a name="create-a-new-released-product"></a>새로 출시된 제품 생성
1. 페이지를 닫습니다.
2. 제품 정보 관리 > 제품 > 출시 제품으로 이동합니다.
3. 새로 만들기를 클릭합니다.
4. 제품 번호 필드에 값을 입력합니다.
5. 제품 이름 필드에 값을 입력합니다.
6. 검색 이름 필드에 값을 입력합니다.
7. 항목 모델 그룹 필드에서 값을 입력하거나 선택합니다.
8. 항목 그룹 필드에 값을 입력하거나 선택합니다.
9. 재고 규모 그룹 필드에서 값을 입력하거나 선택합니다.
10. 추적 규모 그룹 필드에서 값을 입력하거나 선택합니다.
11. 확인을 클릭합니다.

> [!NOTE]
> 기본 제품 수명 주기 상태는 전역 정의입니다.  

## <a name="change-the-product-to-an-active-state"></a>제품을 활성 상태로 변경
1. 제품 수명 주기 상태 필드에서 값을 입력하거나 선택합니다.

> [!NOTE]
> 활성 상태를 설정했다고 가정하고 이제 활성 상태를 선택하여 제품을 기준 계획 및 BOM 수준 계산에 사용할 수 있습니다. 분명히 이것은 일관된 계획에 필요한 모든 제품 세부 정보가 지정된 경우에만 의미가 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]