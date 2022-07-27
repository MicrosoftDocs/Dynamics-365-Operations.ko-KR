---
title: 고정 자산 감가상각
description: 이 항목에서는 고정 자산의 감가상각에 대한 개요를 제공합니다.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2442830766ef1dccc109db5569bfbbbc8182f027
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451288"
---
# <a name="fixed-asset-depreciation"></a>고정 자산 감가상각

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 항목에서는 고정 자산의 감가상각에 대한 개요를 제공합니다.

감가상각은 일반적으로 대차 대조표의 고정 자산 가치를 감소시키는 정기 거래이며 손익 계정에 지출로 청구됩니다. 따라서 일반적으로 대차 대조표에 정기 감가상각을 입금하는 데 주 계정이 사용됩니다. 상쇄 계정은 계정 차트의 손익 부분에 있는 계정입니다.

버전 10.0.24부터 **장부** 페이지의 **양수 감가상각 계산** 자산 장부 구성 옵션을 사용하면 감가상각이 음수 장부가액(입금)로 취득한 고정 자산을 출금으로 기입할 수 있습니다.

## <a name="depreciation-adjustment"></a>감가상각 조정
일반적으로 게시된 감가상각 거래에 대한 수정만 감가상각 조정으로 게시됩니다. 따라서 주 계정과 상쇄 계정은 모두 감가상각 계정과 같이 설정됩니다. 감가상각 조정은 양수 또는 음수 금액일 수 있지만 주 계정(대차 대조표 계정)의 기능과 상쇄 계정(일반적으로 손익 계정)의 기능은 같게 유지됩니다.

## <a name="extraordinary-depreciation"></a>특별 감가상각
특별 감가상각은 기본 감가상각처럼 작동합니다. 따라서 주 계정은 감가상각액을 대차 대조표에 입금하고 고정 자산의 가치를 줄이는 데 사용됩니다. 상쇄 계정은 회계 기간에 대해 계산된 감가상각액이 비용으로 청구되는 손익 계정입니다. 

특별 감가상각은 기본 감가상각과는 독립적으로 작동합니다. 특별 감가상각을 별도의 거래유형으로 하여 기본 감가상각과 별도로 특별 감가상각을 게시 및 보고할 수 있습니다.

## <a name="special-depreciation-allowance"></a>특수 감가상각 허용값
자산이 사용되기 시작하고 감가상각되는 첫해 동안 특수 감가상각 허용값으로 추가 감가상각액을 받을 수 있습니다. 특수 감가상각 허용값은 다른 감가상각 계산보다 먼저 적용해야 합니다. 특수 감가상각 허용값은 고정 자산의 서비스 수명이 끝날 때까지 알 수 없는 경우가 많으므로 총계정원장에 게시되지 않는 장부에 이러한 유형의 감가상각을 사용하는 것이 가장 좋습니다. 총계정원장에 게시되지 않은 정기 거래 삭제 기능을 사용하여 이러한 장부에 대한 거래 내역을 삭제할 수 있습니다. 그런 다음 고정 자산 장부의 감가상각 내역을 삭제하고 특수 감가상각 허용값이 알려진 경우 게시한 다음 해당 연도의 나머지 감가상각 거래를 게시할 수 있습니다. 

특수 감가상각 허용값 기록은 무제한으로 생성할 수 있습니다. 이러한 기록을 자산 그룹 장부에 할당하면 자산 장부에 적용됩니다. 

특수 감가상각 허용값은 백분율 또는 고정 금액으로 입력됩니다. 감가상각 제안을 게시할 때 특수 감가상각 허용값 거래는 감가상각 거래와 별도의 거래로 장부에 게시됩니다.

## <a name="depreciation-calendars"></a>감가상각 달력
각 장부에는 고정 자산을 감가상각할 때 사용되는 달력이 있습니다. 기본적으로 장부에 달력을 지정하지 않으면 장부는 원장 회계 달력을 사용합니다. 장부와 연결된 감가상각 프로필이 회계 감가상각 연도를 사용하는 경우 장부의 회계 달력을 선택해야 합니다. 

총계정원장의 **회계 달력** 페이지를 사용하여 공유 달력을 만들 수 있습니다.

자세한 내용은 [감가상각 방법 및 관례](depreciation-methods-conventions.md)를 참조하세요.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
