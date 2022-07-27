---
title: 사용 가능한 예산 자금
description: 이 토픽에서는 사용 가능한 예산 자금 기능을 소개하고 조직의 재정 자원 관리를 최적화하기 위해 예산 통제를 구성하는 데 도움이 되는 정보를 제공합니다.
author: rcarlson
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: a8279ae9b08c7537548c1c8b71e6e978fee2b8a1
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451279"
---
# <a name="budget-funds-available"></a>사용 가능한 예산 자금

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 토픽에서는 사용 가능한 예산 자금 기능을 소개하고 조직의 재정 자원 관리를 최적화하기 위해 예산 통제를 구성하는 데 도움이 되는 정보를 제공합니다.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>사용 가능한 예산 자금에 대한 향상된 계산 기능

**사용 가능한 예산 자금 계산의 금액만 추적** 기능을 사용하면 **예산 통제 매개 변수 정의** 페이지의 설정을 기반으로 문서 유형 및 상태에 대한 기본 예산 통제 테이블을 추적할 수 있습니다.

일부 예산 통제 구성 옵션에는 기능이 올바르게 작동하기 위한 특정 설정이 있어야 합니다. 이러한 옵션은 **예산 통제 매개 변수 정의** 페이지의 **사용 가능한 예산 자금** 탭에서 선택되거나 지워집니다. 다음 표는 사용 가능한 예산 자금 기능에 필요한 설정을 보여줍니다.

| 이 옵션을 선택하면 | 이 옵션도 선택해야 합니다 |
| ------------------------- | -------------------------------- |
| 사전 지출원인행위에 대한 예산 예약 | 지출원인행위에 대한 예산 예약 *및* 실제 지출 |
| 지출원인행위에 대한 예산 예약 | 실제 지출 |
| 구매 요청 유형 문서를 통한 지출원인행위에 대한 예산 예약 | 사전 지출원인행위에 대한 예산 예약 |

이 기능은 새 문서에만 영향을 줍니다. 기존 문서의 금액은 사용 가능한 예산 설정이 변경되고 새 예산 관리 구성이 활성화될 때까지 계속해서 추적되고 예산 관리 통계 조회에 표시됩니다. 그 시점에서 사용 가능한 예산 자금 계산에서 제거된 문서에 대한 예산 추적 데이터가 제거됩니다.

**미전기된 실제 지출** 옵션을 선택 취소한 상태로 두는 것이 좋습니다. 선택하면 보류 중인 공급업체 송장과 같은 미전기 문서에 대해 시간 소모적인 예산 통제 계산이 수행됩니다.
