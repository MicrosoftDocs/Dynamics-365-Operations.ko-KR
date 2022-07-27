---
title: 새 창고 레이아웃 만들기
description: 이 항목에서는 창고 위치에 대한 정보를 설정하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf5c5203aa0a4c8522b8f9d04fc6a8cd306a64a3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449362"
---
# <a name="create-a-new-warehouse-layout"></a>새 창고 레이아웃 만들기

[!include [banner](../../includes/banner.md)]

이 항목에서는 창고 위치에 대한 정보를 설정하는 방법에 대해 설명합니다. 이는 창고 관리 모듈에서 생성된 창고가 아니라 재고 관리 모듈에서 "기본 창고"를 사용하여 생성된 창고에만 적용됩니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 사용할 수 있습니다.


## <a name="set-the-default-location-capacity"></a>기본 위치 용량 설정
1. 탐색 창에서 **모듈 > 재고 관리 > 설정 > 재고 및 창고 관리 매개 변수** 로 이동합니다.
2. **위치** 탭을 선택합니다.
3. **표준 너비** 필드에 숫자를 입력합니다.
4. **표준 깊이** 필드에 숫자를 입력합니다.
5. **표준 높이** 필드에 숫자를 입력합니다.
6. **저장** 을 선택합니다.
7. 페이지를 닫습니다.

## <a name="define-the-location-name-format"></a>위치 이름 형식 정의
1. 탐색 창에서 **모듈 > 재고 관리 > 설정 > 재고 내역 > 창고** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **창고** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **사이트** 필드의 조회에서 원하는 레코드를 선택합니다.
6. **위치 이름** 섹션의 확장을 토글합니다. 이 섹션의 옵션은 위치 이름의 기본 형식을 정의합니다. 이 예에서는 통로 번호, 랙 번호 및 선반 번호를 포함합니다.  
7. **통로 포함** 옵션을 **예** 로 설정합니다.
8. **랙 포함** 옵션을 **예** 로 설정합니다. 
9. **형식** 필드에서 랙에 대한 값을 입력합니다.
10. **선반 포함** 옵션을 **예** 로 설정합니다.
11. **형식** 필드에서 선반에 대한 값을 입력합니다.

## <a name="define-warehouse-locations"></a>창고 위치 정의
1. 작업 창에서 **창고** 를 선택합니다.
2. **위치 마법사** 를 선택합니다.
3. **다음** 을 선택합니다.
4. **아웃바운드 부두** 옵션 선택 취소
5. **대량 위치** 옵션 선택 취소
6. 옵션이 나올 때까지 **다음** 을 선택하고 **완료** 를 선택합니다.
7. 페이지를 닫습니다.
8. 페이지를 새로 고칩니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]