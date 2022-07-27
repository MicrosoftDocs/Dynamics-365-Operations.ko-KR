---
title: 계획 최적화 문제 해결
description: 이 항목에서는 계획 최적화 작업 중에 발생할 수 있는 문제를 해결하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: bbf21abae60d4adee5a23a8405d14907b91724fa2cbf31c901bb46c589b2ea49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447196"
---
# <a name="troubleshoot-planning-optimization"></a>계획 최적화 문제 해결 

[!include [banner](../../includes/banner.md)]

이 항목에서는 계획 최적화 작업 중에 발생할 수 있는 일반적인 문제를 해결하는 방법에 대해 설명합니다.

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a>계획 최적화 추가 기능 설치가 완료되지 않음

계획 최적화에는 LCS(Lifecycle Services)가 활성화된 고가용성 환경, 계층 2 이상(OneBox 환경 아님), Dynamics 365 Supply Chain Management 버전 10.0.7 이상이 필요합니다. OneBox 환경에 추가 기능을 설치하려고 하면 설치가 완료되지 않습니다.

**해결**: 설치를 취소하고 고가용성 환경 Tier 2 이상(OneBox 환경 아님)을 사용합니다.

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a>계획 최적화가 활성화된 경우 일괄 작업 계획이 실패함

계획 최적화를 활성화하면 기본 제공 기준 계획 엔진이 자동으로 비활성화됩니다. 기본 제공 Supply Chain Management 계획 엔진에 대해 생성된 기준 계획 배치 작업은 계획 최적화가 활성화되어 있는 동안 트리거되면 실패합니다. 다음과 같은 오류 메시지가 나타날 수 있습니다. *이 작업은 계획 최적화가 활성화된 경우 지원되지 않는 기준 계획을 트리거했습니다*.

**해결**: 기본 제공 Supply Chain Management 계획 엔진에 대해 생성된 모든 기준 계획 배치 작업을 취소합니다.

## <a name="planning-optimization-results-are-different-from-earlier-results"></a>계획 최적화 결과가 이전 결과와 다릅니다.

계획 최적화는 일부 영역에서 기본 제공되는 기준 계획 설계와 다릅니다. 이는 보류 중인 기능으로 인해 발생할 수도 있습니다.

**해결**: 계획 최적화 적합 분석을 실행한 후 관련 문서를 참조하면서 결과를 분석하여 영향을 파악합니다. 자세한 내용은 [계획 최적화 적합 분석](planning-optimization-fit-analysis.md)을 참조하세요.

## <a name="cant-enable-planning-optimization"></a>계획 최적화를 활성화할 수 없음

**계획 최적화 사용** 을 **예** 로 설정하기 전에 **연결 상태** 는 **연결됨** 이어야 합니다. 자세한 내용은 [계획 최적화 시작하기](get-started.md)를 참조하세요.

**해결**: 계획 최적화 추가 기능이 성공적으로 설치되었는지 확인합니다.

## <a name="error-message-is-shown-during-ctp"></a>CTP 중 오류 메시지가 표시됨

계획 최적화가 활성화된 상태에서 판매 주문에서 CTP(Capable to Promise)를 실행하려고 하면 다음 오류 메시지가 나타납니다. *이 작업은 계획 최적화가 활성화된 경우 지원되지 않는 기준 계획을 트리거했습니다.*.

이것은 생산 주문에 대한 지원의 일부로 계획된 보류 중인 기능과 관련이 있습니다.

**해결:** CTP 지원을 사용할 수 있을 때까지 계획 최적화가 활성화된 경우 CTP 계산을 피하세요.

## <a name="additional-resources"></a>추가 리소스

[계획 최적화 시작하기](get-started.md)

[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]