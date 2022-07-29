---
title: 중앙 집중식 지불 설정
description: 다음 단계에 따라 조직의 다른 법인을 대신하여 한 법인에서 지불을 처리할 준비를 할 수 있습니다.
author: kweekley
ms.date: 05/09/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 524d4e59e9fad38bd9104ee7e7a3e9d5311b735340bcd03376fc0ebc48eb7174
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450325"
---
# <a name="set-up-centralized-payments"></a>중앙 집중식 지불 설정

[!include [banner](../includes/banner.md)]

다음 단계에 따라 조직의 다른 법인을 대신하여 한 법인에서 지불을 처리할 준비를 할 수 있습니다. 시작하기 전에 다음 설정을 완료해야 합니다.

-   법인을 만듭니다.
-   총계정원장 매개 변수 및 계정 차트를 설정합니다.
-   지급 계정 매개 변수 및 수취 계정 매개 변수를 설정합니다(중앙 집중식 지불을 사용하는 모듈에 따라 다름).
-   회사 간 회계를 설정합니다.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>중앙 집중식 지불을 위한 조직 계층 구조 설정
중앙 집중식 지불을 위한 조직 계층 구조를 설정해야 합니다. 중앙 집중식 공급업체 지불 및 중앙 집중식 고객 지불을 처리하는 데 같은 조직 계층이 사용됩니다. **참고:** 중앙 집중식 지불의 경우 계층 구조는 중요하지 않습니다. 계층 구조에 있는 모든 법인이 계층 구조의 다른 법인을 대신하여 지불을 처리할 수 있습니다. **조직 계층** 페이지에서 새 조직 계층 구조를 만들 수 있습니다. **목적** 필드에서 **중앙 집중식 지불** 을 선택해야 합니다. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>중앙 집중식 지불을 위한 회사 간 계정 설정
현재 법인의 지불 거래가 다른 법인의 송장에 대해 정산되는 경우 각 법인에 대해 적절한 외상매입금 및 외상매출금 거래가 생성됩니다. 적용 가능한 현금 할인 및 실현 손익 금액이 게시되는 법인을 지정해야 합니다. 시작하기 전에 공급업체 및 고객 지불을 처리하는 데 사용할 법인을 결정하세요. 한 법인이 공급업체 지불을 처리하고 다른 법인이 고객 지불을 처리하는 경우 각 법인으로 전환해야 합니다. **회사 간 회계** 페이지에서 대신 지불을 처리할 법인에 대한 회사 간 관계 레코드를 선택할 수 있습니다. 

**중앙 집중식 지불** 탭에서 지불 법인(또는 공급업체 계정의 잔액을 감소시키는 기타 거래) 또는 송장 법인(또는 공급업체 계정의 잔액을 증가시키는 기타 거래)에 현금 할인을 게시할지 선택할 수 있습니다. 이 선택은 **지급 계정 매개 변수** 및 **수취 계정 매개 변수** 페이지의 **현금 할인 관리** 필드와 함께 작동합니다. 초과 지불 및 페니 차이 허용 오차의 경우 지불 법인의 설정이 사용됩니다. 과소 지불 및 페니 차이 허용 오차의 경우 송장 법인의 설정이 사용됩니다.

## <a name="map-vendor-accounts-across-legal-entities"></a>법인 전체에 공급업체 계정 매핑
한 법인의 공급업체에서 비용을 지불하고 다른 법인의 해당 공급업체에 대한 송장을 선택하려는 경우 각 법인의 모든 해당 공급업체 계정이 동일한 주소록 ID를 사용하는지 확인해야 합니다. 둘 이상의 법인에서 송장을 지불하는 고객으로부터 지불을 받는 경우 각 법인의 모든 해당 고객 계정이 동일한 주소록 ID를 사용하는지 확인해야 합니다.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>중앙 집중식 지불을 위한 게시 프로필 설정
다른 법인의 송장을 정산하는 지불을 한 법인에서 만드는 경우 두 법인에서 게시 프로필 ID가 동일해야 합니다. 지불이 올바르게 생성되도록 하려면 송장의 각 법인에서 지불의 법인에서 사용되는 게시 프로필에 해당하는 게시 프로필을 설정하세요. 송장의 첫 번째 법인으로 전환한 다음 **공급업체 게시 프로필** 페이지에서 새 게시 프로필을 만들거나 기존 게시 프로필을 편집할 수 있습니다. 송장의 법인에 있는 게시 프로필에 대해 선택한 항목이 지불의 법인에 있는 게시 프로필 설정과 일치하지 않아도 됩니다.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>중앙 집중식 지불을 위한 지불 방법 설정
다른 법인의 송장을 정산하는 지불을 한 법인에서 만드는 경우 두 법인에서 지불 방법 ID가 동일해야 합니다. 지불이 올바르게 생성되도록 하려면 송장의 각 법인에서 지불의 법인에서 사용되는 지불 방법에 해당하는 지불 방법을 설정하세요. 송장의 첫 번째 법인으로 전환한 다음 **지불 방법** 페이지에서 새 지불 방법을 만들거나 기존 지불 방법을 편집할 수 있습니다. 송장의 법인에 있는 지불 방법에 대해 선택한 항목이 지불의 법인에 있는 지불 방법 설정과 일치하지 않아도 됩니다.

## <a name="set-up-default-descriptions"></a>기본 설명 설정
회사 간 정산 전표에 대한 기본 설명을 정의할 수 있습니다. 기본 설명은 회사 간 정산 절차 중 외상매입금 및 외상매출금 거래에 포함됩니다. **기본 설명** 페이지에서 언어를 선택한 다음 텍스트를 입력하여 **회사 간 고객 정산** 및 **회사 간 공급업체 정산** 에 대한 새 설명을 생성할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]