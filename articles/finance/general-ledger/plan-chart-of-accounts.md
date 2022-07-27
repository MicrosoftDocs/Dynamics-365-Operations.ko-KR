---
title: 계정 차트 계획
description: 이 항목에서는 조직의 차트를 계획하는 데 도움이 되는 정보를 제공합니다.
author: aprilolson
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4a5c0d758ecacce6433b13a2b2044d2417d018
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "8450949"
---
# <a name="plan-your-chart-of-accounts"></a>계정 차트 계획

[!include [banner](../includes/banner.md)]

이 항목에서는 조직의 차트를 계획하는 데 도움이 되는 정보를 제공합니다.

조직의 재무 정보를 추적하고 유지 관리하기 위해 계정 차트를 설정할 수 있습니다. 계정 차트는 재무 프레임워크를 정의하는 계정 모음입니다. 이러한 계정의 거래를 추가로 추적하기 위해 세그먼트를 추가할 수 있습니다. 이러한 세그먼트를 재무 차원이라고 합니다. 예를 들어 비용 계정에 부서, 비용 센터 및 목적이라는 재무 차원이 포함될 수 있습니다. 사용자 정의 규칙은 재무 차원이 기본 계정 및 기타 재무 차원에 연결되는 방식과 거래가 입력되는 방식을 결정합니다. 이러한 사용자 정의 규칙을 계정 구조 및 고급 규칙이라고 합니다.

계정 차트는 법인의 총계정원장 계정의 구조화된 목록입니다. 이 목록은 당국과 소유주를 위한 재무 보고서를 준비하는 데 사용됩니다. 계정은 먼저 계정 유형으로 그룹화된 다음 더 큰 범주로 집계됩니다. 가장 일반적인 수준에서 계정은 수익 및 비용(운영 계정)과 자산 및 부채(잔액 계정)로 그룹화됩니다.

계정 차트는 조직의 모든 법인에서 공유하고 사용할 수 있습니다. 법인에서 사용하는 계정 차트는 **원장** 페이지에서 정의됩니다.

다음은 조직의 계정 차트 구조를 계획할 때 고려해야 하는 몇 가지 요소입니다.

- 조직이 위치한 국가 또는 지역의 보고 요구 사항
- 법인의 보고 요건
- 외부 조직과 조직 모두에 필요한 사양의 정도

**계정 차트** 페이지에서 계정 차트를 작성합니다. **계정 차트** 페이지 또는 **주 계정** 페이지에서 주 계정을 만들 수 있습니다. 주 계정에는 계정 차트의 구분 기호로 사용되는 특수 문자를 사용하면 안 됩니다. 그렇지 않으면 계정과 차원의 조합을 입력할 때 불안정하거나 항상 조회나 대화 상자를 사용해야 할 수 있습니다. 자세한 내용은 [주 계정 만들기](tasks/create-main-account.md)를 참조하세요.

> [!NOTE]
> Dynamics 365 for Finance and Operations 버전 8.0(2018년 4월)의 **총계정원장 매개 변수** 페이지에서 계정 차트 구분 기호를 수정할 수 있습니다.

수정하지 않고도 기본 재무 보고서를 활용할 수 있도록 주 계정을 주 계정 범주에 연결하는 것이 좋습니다. 따라서 보고서를 더 빠르고 쉽게 디자인하고 유지 관리할 수 있습니다.

계정 구조는 **계정 구조 구성** 페이지에서 만듭니다. 계정 구조는 유효한 조합을 정의합니다. 이러한 조합은 주 계정과 함께 계정 차트를 형성합니다. 자세한 내용은 [계정 구조 만들기](tasks/create-account-structures.md)를 참조하세요.

**법인 재정의**

모든 주 계정이 모든 법인에 유효한 것은 아니며 일부 주 계정은 특정 기간에만 관련이 있을 수 있습니다. 이 시나리오에서는 **법인 재정의** 섹션을 사용하여 주 계정을 일시 중지해야 하는 회사, 소유자 및 차원이 활성화된 기간을 식별할 수 있습니다. 공유 수준의 재정의는 법인 수준의 재정의보다 더 제한적일 수 없습니다.

자세한 내용은 다음 항목을 참조하세요.

- [재무 차원](financial-dimensions.md)
- [고급 규칙 구조 만들기 및 할당](tasks/create-assign-advanced-rule-structures.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
