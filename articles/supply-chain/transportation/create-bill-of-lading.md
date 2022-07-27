---
title: 선하 증권 만들기
description: 이 항목에서는 창고 관리 프로세스를 사용할 때 선하증권을 생성하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b79408e21e9acda12617cf35464007e58ae1b5fe
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448591"
---
# <a name="create-a-bill-of-lading"></a>선하 증권 만들기

[!include [banner](../includes/banner.md)]

이 항목에서는 창고 관리 프로세스를 사용할 때 선하증권을 생성하는 방법에 대해 설명합니다.  

선하증권은 물품을 배송하는 회사와 운송업체 간의 법적 문서입니다. 문서는 선적된 품목과 함께 제공되며 품목이 목적지에 배달될 때 선적 영수증 역할을 합니다. 창고 관리를 사용하는 경우 선하 증권을 생성하는 두 가지 방법이 있습니다.

  -   **선하 증권** 페이지를 사용하여 보고서를 수동으로 생성합니다.
  -   **적재 계획 워크벤치** 에서 보고서를 생성합니다.

**적재 계획 워크벤치** 에서 선하 증권을 생성하는 경우 로드 상태는 **배송됨** 이어야 합니다. 화물에 둘 이상의 발송물이 있는 경우 각 발송물에 대해 선하증권이 생성됩니다. 선하 증권이 생성된 후에는 **선하 증권** 페이지에서 변경할 수 있습니다.

## <a name="master-bill-of-lading"></a>마스터 선하 증권
화물에 둘 이상의 발송물이 있는 경우 마스터 선하 증권을 생성할 수 있습니다. 이는 선하 증권과 동일한 레이아웃 및 정보를 갖지만 모든 발송물에 대한 요약된 내용을 포함합니다. **운송 관리 매개 변수** 페이지에 **하나 이상의 화물이 적재된 경우 마스터 선하증권을 생성합니다** 옵션이 **예** 로 설정되어 있으면 **적재 계획 워크벤치** 에서 선하 증권을 만드는 경우 마스터 선하 증권이 자동을 ㅗ생성되며 하나 이상의 배송이 있습니다. **관련 정보** &gt; **선하 증권** 을 클릭하여 선하증권 목록을 얻을 수도 있습니다. 선하 증권을 수동으로 생성하는 경우 **선하 증권** 페이지에서 마스터 선하 증권을 생성할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]