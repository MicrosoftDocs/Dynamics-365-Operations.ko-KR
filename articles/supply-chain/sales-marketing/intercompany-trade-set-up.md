---
title: 회사 간 무역 설정
description: 이 토픽에서는 회사 간 무역을 설정하는 방법에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7288cc8f336b6b1f5174fe2bef38017e0c96e560
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "8449419"
---
# <a name="set-up-intercompany-trade"></a>회사 간 무역 설정

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에서 회사 간 거래를 실행할 수 있도록 하려면 회사 간 거래를 실행하도록 고객과 공급업체를 설정해야 합니다. 또한 지급 계정, 수취 계정, 조달 및 소싱, 영업 및 마케팅도 설정해야 합니다.

## <a name="before-you-set-up-intercompany-trade"></a>회사 간 무역을 설정하기 전에

회사 간 무역을 설정하기 전에 회사 간 고객인 고객과 회사 간 공급업체인 공급업체를 결정해야 합니다. Microsoft Dynamics 365 Supply Chain Management의 각 법인에 대해 특정 회사 간 고객 또는 공급업체와의 회사 간 거래 관계에 적용할 거래 정책을 결정해야 합니다.

특히 귀하와 귀하의 조직은 회사 간 매개 변수에 익숙해지는 것이 좋습니다.

- 각 법인에서 회사 간 거래를 담당하는 관리자와 설정의 의미에 대해 논의합니다.
- 각 법인에 적절한 값을 설정합니다.

## <a name="set-up-trading-relations"></a>무역 관계 설정

고객 및 공급업체에 대한 회사 간 거래를 설정하려면 다음 단계를 따르십시오.

1. **수취 계정 \> 고객 \> 모든 고객** 으로 이동합니다.
1. 고객 계정을 선택합니다.
1. 작업 창의 **일반** 탭에서 **회사 간** 을 선택합니다.
1. 고객 계정에 대한 회사 간 설정 매개 변수를 지정합니다. 이러한 매개 변수에는 해당 공급업체와 공급업체 계정이 포함된 법인이 포함됩니다. 매개 변수에는 구매 주문 정책, 판매 주문 정책, 값 매핑, 판매 계약 및 구매 계약에 대한 정책도 포함됩니다. 또한 고객 계정 또는 다른 법인의 공급업체 계정에서 기본 데이터 값을 사용할지 여부를 지정합니다.
1. 법인의 나머지 회사 간 고객에 대해 1-4단계를 반복합니다.
1. **미지불금 \> 공급 업체 \> 모든 공급 업체** 로 이동합니다.
1. 공급업체 계정을 선택합니다.
1. 작업 창의 **일반** 탭에서 **회사 간** 을 선택합니다.
1. 공급업체 계정에 대한 회사 간 설정 매개 변수를 지정합니다. 이러한 매개 변수에는 해당 고객과 고객 계정이 포함된 법인이 포함됩니다. 매개 변수에는 판매 주문 정책, 구매 주문 정책, 가치 매핑, 구매 계약 및 판매 계약에 대한 정책도 포함됩니다. 또한 공급업체 계정 또는 다른 법인의 고객 계정에서 기본 데이터 값을 사용할지 여부를 지정합니다.
1. 법인의 나머지 회사 간 공급업체에 대해 6-9단계를 반복합니다.

## <a name="set-up-products"></a>제품 설정

고객 및 공급업체에 대한 회사 간 거래를 설정하려면 다음 단계를 따르십시오.

1. **제품 정보 관리 \> 제품 \> 모든 제품 및 제품 마스터** 로 이동합니다.
1. 회사 간 무역을 수행하려는 법인에 출고되는 제품을 정의합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
