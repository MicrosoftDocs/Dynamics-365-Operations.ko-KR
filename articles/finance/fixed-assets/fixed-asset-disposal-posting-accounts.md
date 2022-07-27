---
title: 고정 자산 처분 게시 계정
description: 이 항목에서는 자산 처분을 위해 총계정원장 게시 계정을 설정하는 방법을 설명합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c82cb8b82f2cc8424675f76c68613a2b5aa76745
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451105"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>고정 자산 처분 게시 계정

[!include [banner](../includes/banner.md)]

이 항목에서는 자산을 처분할 때 총계정원장 게시 계정을 설정하는 방법을 설명합니다.

자산을 폐기할 때 사용할 총계정원장 게시 계정을 설정하려면 **고정 자산 게시 프로필** 페이지의 **원장 계정** 빠른 탭에서 **처분 - 판매** 및 **처분 - 폐기** 를 선택합니다.

두 가지 거래 유형(판매 또는 폐기에 의한 자산 처분)의 경우 고정 자산의 처분 가치가 원장 계정에 입금됩니다. 출금은 예를 들어 은행 계좌일 수 있는 상쇄 계정으로 게시됩니다. 고정 자산이 고객에게 판매되는 경우 상쇄 계정 대신 고객 계정이 사용됩니다. 자세한 내용은 [고정 자산 폐기](dispose-of-a-fixed-asset-as-scrap.md)를 참조하세요.

**처분** 을 클릭한 다음 **판매** 또는 **폐기** 를 클릭하고 고정 자산의 순 장부가액을 되돌리기 위한 세부 계정을 설정합니다. **처분 매개 변수** 페이지의 **게시 가치** 및 **판매 가치 유형** 필드에 정보를 입력할 수도 있습니다. 

소액 풀에 있는 자산에 대한 처분 거래는 소액 풀의 순 장부가액을 처분 금액만큼 감소시킵니다. 그러나 자산 매각이 소액 풀의 순 장부가액을 초과하면 순 장부가액이 0으로 감소합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
