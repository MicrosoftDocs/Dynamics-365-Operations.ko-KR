---
title: 거래 계정 및 총 계정에서 예산 생성
description: 이 문서에서는 총 계정을 기반으로 예산을 생성하는 프로세스에 대한 개요를 제공합니다. 또한 예산 통제가 필요한 경우 전체 계정에 대해 예산 통제를 켜는 방법에 대해서도 설명합니다.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09c9fc38360dcf82ceb317edc7195d826f56d86f
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451006"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>거래 계정 및 총 계정에서 예산 생성

[!include [banner](../includes/banner.md)]

이 문서에서는 총 계정을 기반으로 예산을 생성하는 프로세스에 대한 개요를 제공합니다. 또한 예산 통제가 필요한 경우 전체 계정에 대해 예산 통제를 켜는 방법에 대해서도 설명합니다.

예산 계획 및 예산 등록 입력 문서 모두 **총계** 의 주 계정 유형이 있는 주 계정에 대한 예산 책정을 허용합니다. 실제는 거래 주 계정에만 전기될 수 있습니다. 

**총계정원장에서 예산 계획 생성** 정기 프로세스의 경우 **소스** 탭에서 **총계** 주 계정 유형을 기준으로 지정할 수 있습니다. 이 경우 각 주 계정 총계는 목표 예산 계획에 포함되며, 그 금액은 선택된 주 계정 범위의 총계와 동일하게 됩니다. 

**총계** 유형의 주 계정에 대해 예산 통제를 활성화할 수 있습니다. 이 기능은 예산 그룹을 통해 지원됩니다. 총계 주 계정별로 **예산 통제 구성**페이지에서 예산 그룹에 대해 통제해야 하는 예산을 생성해야 합니다. 지정하는 기준에는 총계 주 계정과 계정 범위가 포함되어야 합니다. 예산 그룹 생성 프로세스의 속도를 높이려면 예산 통제 그룹 데이터 엔터티를 활용할 수 있습니다. 

재무제표와 같이 보고에 예산이 사용되는 경우 총계 계정의 예산 합계는 다음 금액으로 구성됩니다.

-   총계 계정의 간격으로 각 거래 원장 계정에서 생성된 예산입니다.
-   총계 계정에 직접 입력되는 예산 금액입니다.

따라서 총계 계정의 간격에서 가장 중요한 거래 계정에 대해 별도의 예산을 만든 다음 사용 가능한 예산 금액을 총계 계정에 추가할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
