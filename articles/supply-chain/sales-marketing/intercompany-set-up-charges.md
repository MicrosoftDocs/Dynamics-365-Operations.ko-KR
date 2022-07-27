---
title: 회사 간 주문에 대한 요금 설정
description: 이 토픽에서는 회사 간 주문에 대한 요금을 설정하는 방법에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3786df5ce185fa8433d7c69bed5bef09b4983b8b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447757"
---
# <a name="set-up-charges-on-intercompany-orders"></a>회사 간 주문에 대한 요금 설정

[!include [banner](../../includes/banner.md)]

회사 간 주문에 추가할 비용을 설정할 수 있습니다. 회사 간 판매 주문에 요금이 추가되면 회사 간 구매 주문에 자동으로 동기화됩니다. 이는 회사 간 판매 주문에서 구매 주문으로, 그리고 그 반대의 두 가지 방식으로 작동합니다.

또한 요금을 회사 간 백분율로 정의하여 요금을 사용하여 회사 간 판매 주문에 이익을 추가할 수 있습니다.

회사 간 주문에 적용할 비용을 설정할 때 원래 판매 주문의 순 금액에서 회사 간 판매 주문에 대한 내부 이익을 계산할 수 있습니다. 회사 간 공급업체가 원가에 판매하는 경우 이 작업을 수행할 수 있습니다. 다음 절차에서는 회사 간 고객에 대해 이 작업을 수행하는 방법에 대해 설명합니다. 공급업체에 대해 동일한 절차를 사용할 수 있습니다.

1. **수취 계정 \> 설정 \> 요금 \> 고객 요금 그룹** 으로 이동합니다.
1. 요금 그룹 만들기
1. **수취 계정 \> 고객 \> 모든 고객** 으로 이동합니다. 고객 계정 링크를 선택합니다. 작업 창에서 **고객** 탭을 선택한 다음 **판매 주문** 빠른 탭을 선택합니다.
1. 작업 창에서 **편집** 을 선택하여 필드 편집을 활성화합니다. **요금 그룹** 필드에서 2단계에서 설정한 회사 간 요금 그룹을 선택합니다.
1. **수취 계정 \> 설정 \> 요금 \> 자동 요금** 으로 이동합니다.
1. 관련 필드를 작성하여 요금을 설정합니다.
1. **고객 관계** 필드에서 2단계에서 설정한 회사 간 요금 그룹을 선택합니다.
1. **라인** 빠른 탭의 **범주** 필드에서 **회사 간 퍼센트** 를 선택합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
