---
title: 작업 주문에 결함 추가
description: 이 항목에서는 자산 관리에서 작업 주문에 오류 등록을 추가하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1090d95d381a047e77bca3e18ef7b99151ea3d5f941f2d6c9e4877a339f1385e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447133"
---
# <a name="add-fault-to-work-order"></a>작업 주문에 결함 추가

[!include [banner](../../includes/banner.md)]



결함 디자이너에서 설정한 결함을 작업 주문에 추가할 수 있습니다. 작업 주문에서 선택한 자산에 사용되는 자산 유형에 하나 이상의 결함 레코드를 연결해야 합니다. 설정에 대한 자세한 내용은 [장애 관리](../setup-for-work-orders/fault-management.md)를 참조하세요.

1. **자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** 또는 **활성 작업 주문** 을 선택합니다.

2. 장애를 등록할 작업 주문을 선택한 다음 작업 창의 **작업 주문** 탭에 있는 **자산** 그룹에서 **자산 결함** 을 선택합니다.

3. **증상** 빠른 탭에서 **라인 추가** 를 선택합니다. 순차적인 오류 번호가 **결함** 필드에 자동으로 입력됩니다.

4. **결함 증상** 필드에서 해당 증상을 선택합니다.

5. **결함 영역** 및 **결함 유형** 필드에서 적절한 값을 선택합니다.

6. **결함 날짜** 필드에 현재 날짜가 자동으로 삽입됩니다. 필요에 따라 다른 날짜를 선택할 수 있습니다.

7. **선택한 증상의 원인** 빠른 탭에서 문제의 원인을 설명하는 줄을 추가합니다.

8. **선택한 증상의 해결** 빠른 탭에서 문제의 가능한 솔루션을 설명하는 줄을 추가합니다.

9. **저장** 을 선택합니다.

아래 그림은 오류 등록의 예를 보여줍니다.

![그림 1.](media/19-work-orders.png)


## <a name="view-asset-faults"></a>자산 결함 보기

**자산 결함** 목록에서 자산에 등록된 모든 결함에 대한 개요를 얻을 수 있습니다.

**자산 결함** 목록 페이지에서 자산에 등록된 모든 결함에 대한 개요를 얻을 수 있습니다. 페이지를 열려면 **자산 관리** > **문의** > **자산 결함** > **자산 결함** 을 선택합니다.


## <a name="print-asset-fault-report"></a>자산 오류 보고서 인쇄

**모든 자산** 목록 페이지에서 모든 오류 등록과 오류 통계의 그래픽 개요를 보여주는 자산 오류 보고서를 인쇄할 수 있습니다.

1. **자산 관리** > **공통** > **자산** > **모든 자산** 을 선택합니다.

2. 오류 보고서를 인쇄할 자산을 선택합니다.

3. 작업 창의 **일반** 탭에서 **보고서** 그룹의 **자산 결함** 을 선택합니다.

4. 특정 기간을 입력하거나 장애 유형을 선택합니다.

5. **확인** 을 선택하여 보고서를 인쇄합니다.

>[!NOTE]
>여러 자산 또는 자산 유형에 대한 오류 보고서를 인쇄하려면 **자산 관리** > **보고서** > **자산** > **자산 결함** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]