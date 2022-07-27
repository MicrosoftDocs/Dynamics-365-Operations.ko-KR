---
title: 출시된 제품 마스터에 제품 수명 주기 상태 할당
description: 이 절차는 출시된 제품 마스터 및 해당 변형에 제품 수명 주기 상태를 할당하는 방법을 보여줍니다.
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
ms.openlocfilehash: 217bab38544c2794d2e57410f8c2a979605106b0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447973"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>출시된 제품 마스터에 제품 수명 주기 상태 할당

[!include [banner](../../includes/banner.md)]

이 절차는 출시된 제품 마스터 및 해당 변형에 제품 수명 주기 상태를 할당하는 방법을 보여줍니다. 전제 조건: 이 작업 가이드를 재생하려면 먼저 "새 제품 수명 주기 상태 만들기" 작업 가이드를 재생하여 하나 이상의 제품 수명 주기 상태가 생성되었는지 확인해야 합니다.


## <a name="find-a-released-product-master"></a>릴리스된 제품 마스터 찾기
1. 제품 정보 관리 > 제품 > 출시 제품으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.

> [!NOTE]
> 제품 마스터에는 제품 하위 유형 제품 마스터가 있습니다.  

## <a name="update-the-lifecycle-state"></a>수명 주기 상태를 업데이트
1. 편집을 클릭합니다.
2. 제품 수명 주기 상태 필드에서 값을 입력하거나 선택합니다.
3. 저장을 클릭합니다.
4. 예를 클릭합니다.

> [!NOTE]
> 예를 선택하면 출시된 제품 마스터와 원래 상태가 동일한 모든 관련 출시된 제품 변형도 새 제품 수명 주기 상태로 업데이트됩니다. 아니요를 선택하면 모든 변형이 실제 상태를 유지합니다. 릴리스된 제품 마스터와 제품 수명 주기 상태가 다른 변형은 업데이트되지 않습니다.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>변형의 수명 주기 상태 확인
1. 출시된 제품 변형을 클릭합니다.

> [!NOTE]
> 모든 변형은 출시된 제품 마스터에서 선택한 수명 주기 상태를 상속받았습니다.  

2. 목록에서 선택한 행을 표시합니다.
3. 제품 수명 주기 상태 필드에서 값을 입력하거나 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]