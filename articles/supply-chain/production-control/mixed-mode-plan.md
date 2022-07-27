---
title: 혼합 모드 계획 - 이산, 프로세스 및 린 소싱 결합
description: 이 항목에서는 혼합 모드 계획에 대한 정보를 제공합니다.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a199d5ac7633aba894ffbc17db015100ae93d895
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447946"
---
# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>혼합 모드 계획 - 이산, 프로세스 및 린 소싱 결합

[!include [banner](../includes/banner.md)]

이 항목에서는 혼합 모드 계획에 대한 정보를 제공합니다. 혼합 모드 계획에서는 자재 흐름을 기반으로 공급망을 모델링할 수 있습니다. Dynamics 365 Supply Chain Management는 선택한 공급 정책(간판, 생산 주문, 구매 주문, 배치 주문 또는 이전 주문)에 관계없이 자재 흐름이 모델을 따르도록 합니다. 

제품 구조에 관계없이 제품 공급에 대한 전반적인 전략을 선택할 수 있습니다.  

예를 들어 어셈블리에서 칸반 제어를 할 수 있습니다. 여기서 자재는 생산 주문, 칸반, 전송, 배치 주문 또는 공급망 특성에 적합한 조합에 의해 어셈블리 영역에 공급됩니다. 단, 공급망 전체에 대한 완전한 가시성은 유지할 수 있습니다. 이 기능을 통해 공급망 프로세스가 최적화되고 공급망에 대한 가시성이 향상됩니다.  

마스터 예약에 사용되는 공급 정책의 세분성은 적용 차원으로 활성화된 스토리지 차원에 따라 다릅니다. 마스터 예약이 다양한 위치 유형의 보충 및 공급을 제어할 수 있도록 하려면(예: 다른 생산 단위에 대해 생산 현장을 분리하거나 다른 유형의 자재 및 완제품 창고를 분리하여) 지점 및 창고를 범위 차원으로 활성화하는 것이 좋습니다. 또는 적용 범위 차원으로 창고를 생략할 수 있습니다. 이 경우 고급 창고 관리를 사용할 때 창고 내부의 모든 이동은 창고 작업으로 제어되는 반면 창고 간의 모든 이동은 철회 칸반으로 제어할 수 있습니다.

## <a name="supply-policies"></a>공급 정책
혼합 모드 계획은 제품이 공급되는 방식과 공급에 따라 파생 소요량(자재 명세서 \[BOM\]의 항목 소비)이 발행되는 방식을 제어합니다. 주문 유형에 따라 시스템은 요구 사항에 맞는 자재를 자동으로 소싱합니다.  

공급 정책은 제품 수준에서 또는 요구 사항을 지원하는 모든 세부 수준에서 정의할 수 있습니다. **기본 주문 설정** 페이지에서 공급 정책의 세분성을 정의합니다.  

공급 정책은 제품, 항목 치수(구성, 색상 및 크기), 사이트 및 창고별로 제어할 수 있습니다. 이 설정은 **항목 적용 범위** 페이지에서 완료됩니다.  

기본 주문 유형은 기준 계획에서 생성하는 주문을 제어합니다.  

공급망이 어떻게 모델링되는지에 관계없이 Supply Chain Management는 공급 정책의 조합을 지원합니다. 칸반에서 소싱되는 생산 주문을 가질 수 있습니다. 또는 이전 또는 칸반에 의해 공급되는 제품이 필요한 배치 주문을 가질 수 있습니다.  

Supply Chain Management는 자재 흐름이 모델을 따르도록 합니다.  

자재 피킹을 위한 창고는 공급 정책이 정의된 후 런타임에 동적으로 지정됩니다.  

일반적으로 칸반은 수명 주기가 짧기 때문에 미래 날짜에 대해 생성되지 않습니다. 공급망에 대한 완전한 가시성을 유지하기 위해 파생된 요구 사항을 계산하는 데 사용되는 "계획된 칸반"이라는 새로운 계획 개념을 도입했으며 실제 칸반을 만들 때 사용되는 것과 동일한 논리를 기반으로 요구 사항이 소싱되도록 보장합니다.  

다른 모든 공급 정책 유형에도 동일한 논리가 있습니다. 따라서 장기 자재 계획은 생산 및 공급이 승인된 후 실제 주문과 함께 실행될 것으로 예상하는 것과 동일한 논리를 기반으로 합니다.

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>자재 할당 교차 공급 정책 – BOM의 리소스 소비
리소스 소비는 중요한 기능입니다. 자원 소비를 통해 공급 정책(주문 유형)에 따라 자재 피킹 창고를 동적으로 선택할 수 있으며 기본 데이터의 유지 관리가 더 쉬워집니다.  

리소스 소비를 위해서는 자재가 피킹되는 창고가 제품 공급 방식에 따라 지정되어야 합니다. 즉, 런타임에 시스템이 제조에 사용해야 하는 리소스를 찾습니다. 그런 다음 시스템은 이러한 리소스를 기반으로 피킹 창고를 찾습니다.  

공급 정책과 무관한 작업의 경우 공급이 변경되더라도 BOM의 정보를 변경할 필요가 없습니다. 임시 변경의 경우 Supply Chain Management는 자재가 올바른 창고에서 공급되는지 확인합니다.

## <a name="process-manufacturing--the-production-type"></a>공정 제조 – 생산 유형
혼합 모드의 완전한 유연성을 위해 모든 제품에 대해 생산 유형 BOM을 사용하는 것이 좋습니다. 그런 다음 생산 주문, 칸반, 이전 주문 또는 구매 주문을 사용하여 제품을 공급할 수 있습니다. 공정 제조의 경우 **수식**, **연산품**, **부산물**, 또는 **계획 항목** 의 생산 유형을 사용해야 합니다. 칸반 및 생산 주문은 이러한 생산 유형에 사용할 수 없습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]