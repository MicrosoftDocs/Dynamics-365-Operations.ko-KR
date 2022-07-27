---
title: 감가상각 제안 생성
description: 이 토픽에서는 감가상각 일괄 처리 제안이 작동하는 방식과 고정 자산에 대한 감가상각을 제안하는 방법에 대해 설명합니다.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6cf285e8764af8c6525fb3f9cbec7306917e57e832777588e8c2c1d4aeed818
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450178"
---
# <a name="create-a-depreciation-proposal"></a>감가상각 제안 생성

[!include [banner](../../includes/banner.md)]

이 토픽에서는 감가상각 일괄 처리 제안이 작동하는 방식과 고정 자산에 대한 감가상각을 제안하는 방법에 대해 설명합니다. 이 작업은 USMF 데모 회사와 회계사 역할을 사용합니다.


## <a name="create-a-depreciation-proposal"></a>감가상각 제안 생성
1. 탐색 창에서 **모듈 > 고정 자산 > 분개장 기입 > 감가상각 제안 생성** 으로 이동합니다.
2. **분개장 이름** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
3. **종료 날짜** 필드에 날짜를 입력합니다.

    - **감가상각 요약** 옵션을 선택하여 월별 감가상각을 하나의 분개장 라인으로 요약합니다.  
    - 예를 들어 종료 날짜 값이 2015년 3월 31일이면 "2015년 1월 31일 이후 감가상각"이라는 설명이 생성됩니다. 제안된 분개장 라인의 **날짜** 필드는 2015년 3월 31일로 설정됩니다.  
    - 감가상각 제안은 **필터** 옵션을 사용하여 자산, 자산 그룹 또는 기타 기준으로 필터링할 수 있습니다.  
    - **고정 자산에 대한 취득 또는 감가상각 제안 생성** 양식을 사용하면 감가상각을 일괄적으로 제안할 수 있습니다. 더 많은 시스템 리소스를 사용하는 대규모 제안에 권장됩니다. 일괄 처리 옵션을 선택하면 해당 시간 동안 다른 작업을 완료할 수 있습니다. 이러한 방식으로 감가상각을 제안하면 고정 자산의 가치 모델에 대한 감가상각이 계산됩니다.  

4. **분개장 생성** 을 선택합니다.

## <a name="review-depreciation-entries"></a>감가상각 항목 검토
1. 탐색 창에서 **모듈 > 고정 자산 > 분개장 기입 > 고정 자산 분개장** 으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. **라인** 을 선택합니다.
4. **전기** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]