---
title: 생산 기장
description: 이 문서는 생산 과정에서 다양한 유형의 기장에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee3eaf11f5d77861e7abd29bb428f67b57a3e0e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447874"
---
# <a name="production-posting"></a>생산 기장

[!include [banner](../includes/banner.md)]

이 문서는 생산 과정에서 다양한 유형의 기장에 대한 정보를 제공합니다.

생산 기장 활동은 아래 섹션에 설명된 생산 프로세스를 따릅니다.

## <a name="material-consumption"></a>자재 소비
자재는 생산 불출 목록 분개장이 기장될 때 생산 중 소비된 것으로 등록됩니다. 이 프로세스는 현재고를 차감하는 출고 트랜잭션을 생성합니다. 생산 매개 변수에서 진행 중인 원자재 값(재공품\[ WIP\])를 원장에 기장해야 합니다. 진행 중인 원자재 값(WIP)은 전용 불출 목록 계정과 전용 불출 목록 상쇄 계정에 기장됩니다.

## <a name="time-consumption"></a>시간 소비
작업자가 생산 작업에 소요한 시간은 경로 카드 분개장 또는 작업 카드 분개장에 기록됩니다. 이러한 분개장이 기장되면 진행 중인 자원(WIP)에 대한 전용 계정에 대한 원장 기장이 처리됩니다. 이 기장은 생산 주문에 소요된 시간의 가치를 나타냅니다. 생산 주문이 종료된 것으로 등록된 후 WIP 계정이 정산됩니다.

## <a name="reporting-finished-goods-and-error-quantities"></a>완제품 및 오류 수량 보고
생산 주문이 완료로 보고되면 완료 분개장으로 보고서를 통해 재고 관리에서 완료된 완제품의 수량이 업데이트됩니다. 생산 매개 변수에서 설정할 수 있는 WIP 회계를 사용하는 경우 WIP 계정을 줄이고 완제품의 재고를 늘리기 위해 원장 분개장이 만들어집니다. 분개장은 제품에 대해 정의된 표준 비용을 사용합니다.

## <a name="ending-the-production-order"></a>생산 주문 종료
생산 주문이 종료되기 전에 생산된 수량에 대한 실제 비용을 계산합니다. 재료비, 노무비, 간접비의 모든 예상 비용은 취소되고 실제 비용으로 대체됩니다. 완제품의 전체 비용은 재고 영수증 계정에서 차변에 기입되고 재고 발행 계정에 적립됩니다. 원가 계산 실행 시 **작업 종료** 확인란을 선택하면 생산 주문의 상태가 **종료됨** 으로 변경됩니다. 이 상태는 추가 비용이 완료된 생산 주문에 실수로 전기되는 것을 방지합니다. 완료로 보고되는 동안 보고된 오류 수량 값을 완료로 보고된 양호한 수량에 할당하도록 지정할 수 있습니다. 또는 오류 수량 값을 전용 스크랩 계정에 전기하도록 지정할 수 있습니다.

## <a name="controlling-the-level-of-ledger-posting"></a>원장 전기 수준 제어
**생산 제어 매개 변수** 에서 **원장 전기** 필드를 사용하여 생산 프로세스에 대한 원장 전기 수준을 설정할 수 있습니다. 다음 값을 사용할 수 있습니다.

-   **품목 및 리소스** – 원자재 및 완제품의 품목 그룹에 설정된 원장 계정을 사용합니다. 시간 소비를 위한 WIP는 경로 작업의 리소스 또는 리소스 그룹에서 가져옵니다.
-   **품목 및 범주** – 원자재 및 완제품의 품목 그룹에 설정된 원장 계정을 사용합니다. 시간 소비에 대한 WIP는 경로 작업과 관련된 비용 범주에서 가져옵니다.
-   **생산 그룹** – 자재 및 시간 소비 모두에 대해 생산 그룹에 설정된 원장 계정을 사용합니다. 생산 그룹은 릴리스된 제품과 연결되고 해당 주문이 생성될 때 생산 주문에 복사됩니다. 생산 주문에 대한 전기는 생산 주문과 연결된 생산 그룹을 따릅니다.

**참고:** 완제품 원가를 계산하는 표준 방법을 사용했다면 최종 거래에는 이러한 사실이 반영됩니다. 실제 원가와 표준법으로 계산한 원가가 다른 경우에는 그 차액을 당기손익으로 계상합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]