---
title: 전역 원천징수세
description: 이 항목에서는 전역 원천징수세 기능 및 설정 방법에 관한 정보를 제공합니다. 원천징수세가 품목 수준에서 계산되도록 공급업체 및 고객 거래에 대한 전역 원천징수세 기능이 향상되었습니다.
author: roschlom
ms.date: 01/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 7a3bb3c8766c7dd591f66a663d8be17769bb7d53
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451462"
---
# <a name="global-withholding-tax"></a>전역 원천징수세

[!include [banner](../includes/banner.md)]

이 항목에서는 전역 원천징수세 기능 및 설정 방법을 설명합니다. 새 기능은 버전 10.0.17 이상에서 사용할 수 있습니다.

원천징수세가 품목 수준에서 계산되도록 공급업체 및 고객 거래에 대한 전역 원천징수세 기능이 향상되었습니다. 구매 거래의 원천징수세 계정 잔액은 원천징수세 정산 계정에 대해 원천징수세 납부 작업을 실행하여 정산할 수 있습니다.

> [!NOTE]
> 전역 원천징수세는 구매 주문, 공급업체 송장 및 판매 주문 페이지에서 **요금 유지** 기능을 지원하지 않습니다.

## <a name="turn-on-global-withholding-tax"></a>전역 원천징수세 켜기

1. **기능 관리** 작업 영역에서 **전역 원천징수세** 를 선택하고 **지금 활성화** 를 선택합니다.
2. **세금 \> 설정 \> 매개 변수 \> 총계정원장 매개 변수** 로 이동하고 **원천징수세** 탭에서 **전역 원천징수세 활성화** 옵션을 **예** 로 설정합니다.
3. **저장** 을 선택합니다.
4. 웹 브라우저에서 페이지를 새로 고칩니다.

> [!NOTE]
> 현지화된 원천징수세 솔루션이 이미 존재하는 국가/지역에서는 전역 원천징수세 기능을 켤 수 없습니다. 이러한 지역에는 인도, 브라질, 태국, 사우디아라비아, 아일랜드, 영국, 미국이 포함되며 이에 제한되지 않습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
