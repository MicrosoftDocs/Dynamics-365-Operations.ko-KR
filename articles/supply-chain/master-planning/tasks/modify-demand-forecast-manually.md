---
title: '가이드: 수동으로 수요 예측 수정'
description: 이 항목에서는 항목에 대한 예측을 수정하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f48e1689d21fd0085ec38aab8f5171997fbf432
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447994"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>가이드: 수동으로 수요 예측 수정

[!include [banner](../../includes/banner.md)]

이 절차는 항목에 대한 예측을 수정하는 방법을 보여줍니다. 이 절차는 생산 계획자를 위한 것입니다.

## <a name="modify-the-forecast-for-a-selected-item"></a>선택한 항목에 대한 예측 수정

선택한 항목에 대한 예측을 수정하려면:

1. **모듈 \> 제품 정보 관리 \> 제품 \> 출시 제품** 으로 이동합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다. 예측을 수정할 항목을 선택합니다.
1. 작업 창에서 **계획** 탭을 열고 **수요 예측** 을 선택합니다.
1. 목록에서 행을 선택합니다. 예측 라인이 없는 경우 작업 창에서 **새로 만들기** 를 선택하여 새 라인을 생성합니다.  
1. **판매 수량** 필드에 양수를 입력합니다. 이 숫자는 항목의 예상 수량을 나타냅니다. 음수를 입력하면 오류가 표시됩니다.
1. 필요에 따라 다른 필드를 채웁니다.
1. 작업 창에서 **저장** 을 선택합니다.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Microsoft Excel을 사용하여 하나 이상의 항목에 대한 예측 수정

Microsoft Excel을 사용하여 하나 이상의 항목에 대한 예측을 수정하려면:

1. 다음 중 하나를 수행하세요.
    - 이전 섹션에서 설명한 대로 모든 항목(어느 항목이든 상관 없음)에 대한 **수요 예측** 페이지를 엽니다.
    - **기준 계획 \> 예측 \> 수동 예측 입력 \> 수요 예측 라인** 으로 이동합니다.
1. 작업 창에서 **Microsoft Office에서 열기 \> 수요 예측 항목** 을 선택합니다.
1. 다운로드 위치를 선택하고 저장한 후 다운로드한 파일을 Excel에서 엽니다.
1. 경고가 표시되면 **편집 활성화** 를 선택합니다.
1. Excel에서 Microsoft Dynamics 작업 창을 사용하여 Supply Chain Management에 로그인합니다. **로그인 상태 유지** 옵션이 활성화된 상태로 로그인해야 하며 데이터 연결 앱을 신뢰해야 합니다.
1. 이제 Excel 스프레드시트에 회사의 모든 현재 수요 예측 라인이 표시됩니다.  필요에 따라 수요 예측 라인을 추가, 삭제 및 편집합니다.
1. Microsoft Dynamics 작업 창에서 **게시** 를 선택하여 변경 사항을 다시 Supply Chain Management에 업로드합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
