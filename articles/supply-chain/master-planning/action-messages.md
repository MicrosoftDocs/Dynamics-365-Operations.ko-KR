---
title: 작업 메시지
description: 작업 메시지는 기존 계획 또는 확정 주문을 변경하기 위해 시스템에서 생성된 제안입니다.
author: ChristianRytt
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb208d390d3b5d2091f5b0f112532794a4d78d8adcf947291a4183c3b3fd3f9c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447211"
---
# <a name="action-messages"></a>작업 메시지

[!include [banner](../includes/banner.md)]

작업 메시지는 기존 계획 또는 확정 주문을 변경하기 위해 시스템에서 생성된 제안입니다.

## <a name="introduction"></a>소개

작업 메시지는 변경된 요구 사항에 대한 응답으로 기준 계획 계산에 의해 생성됩니다. 예를 들어, 수요를 충족시키기 위해 구매 주문을 이미 생성한 판매 주문에서 배송 날짜 또는 수량을 변경했을 수 있습니다. 이 경우 구매 주문을 업데이트하기 위해 기준 계획 계산에 의해 하나 이상의 작업 메시지가 생성됩니다. 제안된 변경을 수행할지 여부를 결정합니다.

항목에 첨부한 적용 범위 그룹에 대해 작업 메시지가 계산되는 방법을 설정할 수 있습니다.

## <a name="select-action-messages"></a>작업 메시지 선택

**커버리지 그룹** 페이지에서 시스템이 생성할 작업 메시지와 메시지가 적용되는 적용 범위 그룹 또는 항목을 선택할 수 있습니다. 다음 작업 메시지를 선택할 수 있습니다.

| 메시지             | 설명                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **사전**         | 이 메시지를 선택하면 시스템은 필요할 때 더 빠른 날짜로 주문을 이동하기 위한 조치 메시지를 생성합니다. **사전 마진** 필드에서 사전 조치 없이 수령과 발행 사이의 최대 일수를 지정할 수도 있습니다. |
| **연기**        | 이 메시지를 선택하면 시스템은 필요할 때 더 늦은 날짜로 주문을 이동하기 위한 조치 메시지를 생성합니다. **연기 마진** 필드에서 연기 조치 없이 수령과 발행 사이의 최대 일수를 지정할 수 있습니다.       |
| **감소**        | 이 메시지를 선택하면 초과 재고 수준을 방지하기 위해 생산 주문, 구매 주문 및 기타 입고 트랜잭션을 줄여야 합니다.                                                                                                   |
| **증가**        | 이 메시지를 선택하면 재고 부족을 방지하기 위해 생산 주문, 구매 주문 및 기타 입고 트랜잭션을 늘려야 합니다.                                                                                                    |
| **파생 작업** | 이 메시지를 선택하면 파생된 요구 사항에 대한 작업 메시지가 생성됩니다(예: 생산을 이행하는 구성 요소 주문에 대한 작업).                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]