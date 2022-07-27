---
title: 기준 계획에서 제품을 제외하는 제품 수명 주기 상태 생성
description: 이 절차에서는 기준 계획 및 BOM 수준 계산에서 제품을 제외하는 새 제품 수명 주기 상태를 생성하는 방법을 보여줍니다.
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
ms.openlocfilehash: c7f72be341b81515b7c5540d66f61647df93af41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447976"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>기준 계획에서 제품을 제외하는 제품 수명 주기 상태 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 기준 계획 및 BOM 수준 계산에서 제품을 제외하는 새 제품 수명 주기 상태를 생성하는 방법을 보여줍니다.


## <a name="create-an-obsolete-state"></a>사용되지 않는 상태 만들기
1. 제품 정보 관리 > 설정 > 제품 수명 주기 상태로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 상태 필드에 값을 입력합니다.
4. 계획에 대해 활성 상태임 필드에서 아니요를 선택합니다.
5. 설명 필드에 값을 입력합니다.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>더 이상 사용되지 않는 상태를 출시된 제품에 연결
1. 페이지를 닫습니다.
2. 제품 정보 관리 > 제품 > 출시 제품으로 이동합니다.
3. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 'M00'인 검색 이름 필드를 필터링합니다.
4. 편집을 클릭합니다.
5. 목록에서 선택한 행을 표시합니다.
6. 제품 수명 주기 상태 필드에서 값을 입력하거나 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]