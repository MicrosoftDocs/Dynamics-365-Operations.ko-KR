---
title: 생산 주문 릴리스
description: 이번에는 생산 주문을 릴리스하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6d0db7f93e113d8f41effd68ce19aa065b031fd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448639"
---
# <a name="release-a-production-order"></a>생산 주문 릴리스

[!include [banner](../../includes/banner.md)]

이번에는 생산 주문을 릴리스하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이는 생산 주문 수명 주기를 설명하는 7가지 절차 중 4번째 절차입니다.

1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
    * 그리드에서 예약됨 상태의 생산 주문을 선택합니다.  
2. 작업 창에서 생산 주문을 클릭합니다.
3. 릴리스를 클릭합니다.
    * 이 페이지에서 선택한 생산 주문 범위의 릴리스를 확인할 수 있습니다. 주문을 추가하려면 선택을 클릭하세요.  
    * 릴리스 단계는 생산 주문이 생산 현장으로 릴리스되어 생산 현장 운영자가 생산 작업의 진행 상황을 보고할 수 있도록 하는 시점을 나타냅니다. 작업 처리에 대한 관련 정보가 포함된 생산 문서를 발행할 수 있습니다. 창고 절차를 위해 설정된 품목에 대해 원자재 피킹을 위한 창고 작업이 생성됩니다.  
4. 일반 탭을 클릭합니다.
    * 인쇄할 생산 보고서를 선택합니다. 작업 카드 보고서는 예약된 각 작업에 대한 페이지를 인쇄하고 작업 수준에서 생산 주문을 예약해야 합니다. 보고서에는 예약된 시작 및 종료 시간, 생산할 수량, 작업을 처리하는 자원에 대한 정보가 포함됩니다. 경로 작업 보고서는 동일한 페이지에서 동일한 정보를 수집하지만 각 작업에 대한 페이지를 인쇄하지는 않습니다. 경로 카드 보고서에는 작업만 표시되고 작업은 표시되지 않습니다. 따라서 이 보고서는 작업 스케줄링이 필요하지 않지만 생산 주문이 작업 수준에서 스케줄링될 때 사용할 수 있습니다.  
5. 경로 카드 인쇄 확인란을 클릭합니다.
6. 확인을 클릭합니다.
7. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]