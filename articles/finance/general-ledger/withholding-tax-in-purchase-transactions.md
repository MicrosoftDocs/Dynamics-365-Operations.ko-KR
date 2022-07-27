---
title: 구매 거래의 원천징수세
description: 원천징수세 의무가 있는 공급업체의 경우 **모든 공급업체** 페이지에서 기본 **원천징수세 그룹** 을 지정할 수 있습니다.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: a1d1ddf108e5e79ca7684ecc26df1c016a0362bbec43868c7dfed6970a097a76
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450319"
---
# <a name="withholding-tax-in-purchase-transactions"></a>구매 거래의 원천징수세

원천징수세 의무가 있는 공급업체의 경우 **모든 공급업체** 페이지에서 기본 **원천징수세 그룹** 을 지정할 수 있습니다.

1. **탐색 창 > 모듈 > 지급 계정 > 공급업체 > 모든 공급업체** 로 이동합니다.

2. 해당 공급업체 계정을 클릭하고 **편집** 을 클릭합니다.

3. **송장 및 배송** 탭에서 **원천징수세 계산** 필드를 **예** 로 설정합니다.

   > [!NOTE] 
   > 데이터에서 이 공급업체에 대해 **원천징수세 계산** 이 켜져 있지 않으면 원천징수세가 계산되지 않습니다.

4. **원천징수세 그룹** 에서 원천징수세 그룹을 선택합니다.

5. **저장** 을 클릭합니다.

원천징수해야 하는 품목/서비스의 경우 **출시된 제품** 에서 기본 **품목 원천징수세 그룹** 을 지정할 수 있습니다.

1. **탐색 창 > 모듈 > 제품 정보 관리 > 제품 > 출시된 제품** 으로 이동합니다.

2. 품목 번호를 클릭하고 **편집** 을 클릭합니다.

3. **구매** 탭에서 **원천징수세 계산** 을 클릭합니다.

   > [!NOTE] 
   > **출시된 제품** 페이지의 **구매** 탭에 이 품목에 대해 **원천징수세 계산** 이 **예** 로 설정되어 있지 않으면 원천징수세가 계산되지 않습니다.

4. **품목 원천징수세 그룹** 목록에서 품목 원천징수세 그룹을 선택합니다.

5. **저장** 을 클릭합니다.

원천징수세 그룹 및 품목 원천징수세 그룹은 페이지에서 지정할 수 있습니다. 

- **구매 주문**
- **공급업체 송장**
- **송장 분개장**

기본 원천세 그룹 및 항목 원천세 그룹은 **구매 주문** 및/또는 **보류 중인 공급업체 송장** 을 생성할 때 라인으로 전달됩니다. **공급업체 송장 분개장** 의 경우 **원천징수세 계산** 을 켜고 분개장의 **일반** 탭에서 **원천징수세 항목 그룹** 을 선택할 수 있습니다.

임시 원천징수세 금액은 **구매 주문** 페이지의 **합계** 탭에 있는 **조정된 원천징수세** 필드에서 확인할 수 있습니다.

![원천징수세는 구매 주문에 포함됩니다.](media/withholding-tax-adjusted.png)

원천징수세는 **공급업체 지불 분개장** 에서 계산됩니다. **거래 정산** 페이지의 **원천징수세** 탭에서 해당 원천징수세 코드와 실제 원천징수세 금액을 수동으로 조정할 수 있습니다.

![원천징수세는 거래 정산 페이지에서 수동으로 조정할 수 있습니다.](media/withholding-tax-vendor-payment-tab.png)

파생된 원천징수세 금액은 공급업체 지불에서 공제되고 관련 전표의 **원천징수세 계정** 에 게시됩니다.

![관련 전표가 표시된 원천징수세 계정.](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]