---
title: 총계정원장에 대한 기본 설명
description: 기본 설명을 사용하여 바우처 전기의 설명 필드를 총계정원장으로 업데이트할 수 있습니다.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 52e048e5a9271dfcd1d7b303d8ae8eae331296a3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449029"
---
# <a name="default-descriptions-for-the-general-ledger"></a>총계정원장에 대한 기본 설명

[!include [banner](../../includes/banner.md)]

기본 설명을 사용하여 바우처 전기의 **설명** 필드를 총계정원장으로 업데이트할 수 있습니다. 이 기능은 상륙 비용과 함께 작동하도록 향상되었습니다.

원장 전기에 대한 기본 설명을 설정하려면 **조직 구성 관리 \> 설정 \> 기본 설명** 으로 이동합니다.

다음 테이블에는 상륙 비용을 지원하기 위해 **기본 설명** 페이지의 **설명** 필드에 추가된 새 값이 나열되어 있습니다.

| 설명 유형 | 메모 |
|---|---|
| 수입원가계산 – 발생원가 | 구매 주문 청구서가 전기되면 예상 항해 비용에 대해 발생 비용이 처리됩니다. 기본 설명을 지정하여 설명에 항해 번호를 추가할 수 있습니다. 배송 번호로 *%4* 을(를) 선택합니다. |
| 수입원가계산 – 운송 주문 상품 | 미착 처리를 사용하는 경우 구매 발주 송장이 전기되고 상품이 미착 상품 계정에 전기됩니다. 기본 설명을 지정하여 설명에 미착 주문 번호를 추가할 수 있습니다. 미착 주문 번호로 *%4* 을(를)을 사용합니다. |
| 재고 – 마감 – 조정 | 항해 비용에 대해 AP(지급 계정) 청구서를 처리할 때 항해 비용을 추정하기 위해 재고 조정이 처리됩니다. 기본 설명을 지정하여 설명에 항해 번호를 추가할 수 있습니다. 배송 번호로 *%4* 을(를) 선택합니다. |

**기본 설명** 페이지를 사용하는 방법에 대한 자세한 내용은 [자동 전기를 위한 기본 설명 설정](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md)을 참조하세요.
