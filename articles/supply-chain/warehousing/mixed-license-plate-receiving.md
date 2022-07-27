---
title: 혼합 번호판 수신
description: 이 항목에서는 혼합 번호판 수신을 사용하여 모바일 디바이스로 여러 항목에 대한 작업을 등록하고 생성하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84b01e9c6ad041fe95b46c97d89b90e85422d170399754062a6422319fc23a63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447208"
---
# <a name="mixed-license-plate-receiving"></a>혼합 번호판 수신

[!include [banner](../includes/banner.md)]

혼합 번호판 수신을 사용하면 풋 어웨이 작업을 만들고 등록하기 전에 여러 항목으로 구성된 번호판을 만들 수 있습니다. 

여러 항목으로 구성된 번호판은 각 항목을 등록하기 위해 수령 도크에서 분할할 필요가 없습니다. 

항목 관련 흐름을 사용하여 소스 문서 행을 식별할 때 항목 제어에서 바코드를 스캔할 수 있습니다. 바코드에 수량과 측정 단위(UOM)가 구성되어 있는 경우 항목 및 수량은 혼합 번호판에 자동으로 추가되고 다른 항목을 스캔하기 위해 화면으로 돌아갑니다. 이를 통해 각 단계에서 확인하지 않고도 모든 항목을 빠르게 스캔할 수 있습니다. 

혼합 번호판 수령 흐름에서는 이미 번호판에 스캔된 항목 목록을 표시할 수 있으며 여기에서 항목 수량을 수정하거나 정정할 수 있습니다.

## <a name="where-it-applies"></a>적용되는 곳

혼합 번호판 수신은 동시에 여러 라인/항목에 대한 작업을 등록하고 생성하는 모바일 디바이스 수신 흐름입니다. 여러 항목이 포함된 인바운드 번호판을 받을 때 유용합니다. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>혼합 번호판 수신을 설정하는 방법
혼합 번호판 수신은 모바일 디바이스 메뉴 항목으로 설정됩니다.

기존 작업을 사용하지 않는 모드 작업으로 새 메뉴 항목을 생성하고 다음 방법 중 하나를 사용해야 합니다.

- 혼합 번호판 수신
- 혼합 번호판 수신 및 처리

소스 문서 라인을 식별하는 옵션은 구매 발주 항목, 구매 발주 라인, 반품 주문, 이전 주문 항목 및 이전 주문 라인입니다. 이러한 옵션은 단일 번호판의 수신 순서를 변경할 수 있습니다. 마지막 옵션은 로드 항목별입니다. 번호판에 여러 항목을 추가할 수 있지만 여러 로드 간에 전환할 수는 없습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]