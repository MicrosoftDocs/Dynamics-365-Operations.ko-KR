---
title: 공급업체 송장에 대한 판매세 계산 및 조정
description: 이 토픽에서는 Dynamics 365 Finance에서 공급업체 송장의 판매세를 조정하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 648d94e895a4941f5f3148134130b3ffa693a9d57e0bb4e236f5d5fb33aca48f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450871"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>공급업체 송장에 대한 판매세 계산 및 조정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 공급업체 송장의 판매세를 조정하는 방법에 대해 설명합니다. 원래 원본 문서에 계산된 세액이 다르게 표시되는 경우 전기하기 전에 해당 금액을 조정할 수 있습니다. 이 작업에는 DEMF 데모 회사를 사용합니다.

1. 탐색 창에서 **모듈 > 지급 계정 > 송장 > 송장 분개장** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 새 행의 **이름** 필드의 드롭다운 메뉴에서 옵션을 선택합니다.
4. 작업 창에서 **라인** 을 선택합니다.
5. **계정** 필드에서 원하는 값을 지정합니다.
6. **송장** 필드에 값을 입력합니다.
7. **대변** 필드에 숫자를 입력합니다.
8. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
9. **판매세** 를 선택합니다.
10. **총 실제 판매 세액** 필드에 숫자를 입력합니다.
11. **조정** 탭에서 판매세 코드별로 판매세 금액을 조정할 수 있습니다.
12. **계산된 금액에서 실제 금액 재설정** 을 선택합니다.
13. **확인** 을 선택합니다.
14. **저장** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]