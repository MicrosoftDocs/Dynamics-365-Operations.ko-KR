---
title: 예약된 실행
description: 이 토픽에서는 자산 관리의 예약된 실행에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4ace2da2c4bc3d5cc404301fc4ecef5ceeef240dae6569a4d28f621b02637930
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447313"
---
# <a name="scheduled-execution"></a>예약된 실행

[!include [banner](../../includes/banner.md)]

 

작업 주문 서비스 수준을 사용하여 예약된 실행을 설정할 수 있습니다. (작업 주문 서비스 수준에 대한 자세한 내용은 [서비스 수준 및 설명](service-level-and-description.md)을 참조하세요.) 예약된 실행은 작업 주문이 완료되어야 하는 간격에 대해 보다 상세하거나 덜 상세한 요구 사항을 설정할 수 있기 때문에 유지 관리 작업자를 위한 작업 계획의 유연성을 제공합니다. 예를 들어, 생산 시설에서 예상보다 빨리 작업을 완료하는 유지 관리 작업자는 이번 주에 계획되었지만 반드시 당일은 아닌 다른 인근 작업으로 이동할 수 있습니다. 이 접근 방식을 통해 작업자 계획 및 작업 완료를 최적화할 수 있습니다.

작업 주문과 관련된 예약 실행 설정은 일반적이거나 특정적일 수 있습니다. 특정 작업 주문 유형, 자산 유형 등에 국한되지 않는 일반 라인을 설정할 수 있습니다. 또는 특정 작업 주문 유형, 자산 유형, 유지 관리 작업 유형 등에 적용되는 예약된 실행 라인을 생성할 수 있습니다.

1. **자산 관리** \> **설정** \> **작업 주문** \> **예약된 실행** 을 선택합니다.
2. **새로 만들기** 를 선택하여 예약된 실행 라인을 생성합니다.
3. **기능 위치**, **작업 주문 유형**, **자산 유형**, **제조업체**, **모델**, **유지 관리 작업 유형 범주**, **유지 관리 작업 유형**, **유지 관리 작업 유형 변형** 및 **거래** 필드에서 필요에 따라 값을 선택합니다.
4. **서비스 수준** 필드에서 작업 주문 서비스 수준을 선택합니다. 이 필드를 비워 두면 가장 일반적인 유형의 예약된 실행 라인이 됩니다. 일반 라인의 예는 다음 그림의 첫 번째 레코드를 참조하세요. 이 라인을 사용하면 작업 주문 서비스 수준이 없는 모든 작업 주문을 특정 날짜 및 시간에 예약할 수 있습니다.
5. **예약된 실행** 필드에서 시간 간격을 선택합니다.
6. **저장** 을 선택합니다.

![예약된 실행.](media/20-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]