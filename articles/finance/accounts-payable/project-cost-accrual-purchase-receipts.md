---
title: 구매 영수증에 대한 프로젝트 비용 발생
description: 이 항목에서는 Microsoft Dynamics 365 Finance에서 구매 영수증에서 발생한 프로젝트 비용을 추적하는 방법에 대해 설명합니다.
author: sunfzam
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ae2f57e0104a30492363f1576962d36a2a1b04b
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451024"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>구매 영수증에 대한 프로젝트 비용 발생

[!include [banner](../includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Finance에서 구매 영수증에서 발생한 프로젝트 비용을 추적하는 방법에 대해 설명합니다. 

프로젝트에 대한 송장은 종종 상품 및 서비스가 전달되는 시간보다 늦게 도착하며, 이는 프로젝트 KPI(핵심 성과 지표)에 상당한 영향을 미칠 수 있습니다. 재무 보고서와 프로젝트 보고서 모두에서 이러한 트랜잭션을 추적할 수 있는 것이 중요합니다.

다음 예제 시나리오에서는 이를 보여 줍니다. 

Contoso Consulting이 새로운 클라우드 구축 프로젝트를 시작했습니다. 프로젝트용 컴퓨터를 구입하기 위한 구매 주문이 생성됩니다. 컴퓨터는 1,500달러이고 설치 서비스는 150달러입니다. 공급업체가 컴퓨터를 납품하고 설치했지만, 송장은 아직 Contoso Consulting에 도착하지 않았습니다. 프로젝트 관리자는 송장이 도착하기 전에 프로젝트 비용이 1,650달러 발생하기를 원합니다. 이 비용은 회사의 월말 재무제표에 반영되어야 합니다. 

발생 비용은 재무 수준과 프로젝트 수준 모두에서 보고 목적으로 기록되어야 합니다. 제품 영수증의 재무 업데이트는 품목 및 조달 범주에 대해 추적할 수 있습니다. 

항목의 경우 **지급 계정 매개 변수** 페이지에서 **제품 영수증을 원장에 게시** 옵션을 선택합니다.
[![지급 계정 매개 변수 페이지.](./media/accruals1-1024x409.png)](./media/accruals1.png) 

조달 카테고리의 경우 **범주 정책 규칙** 페이지에서 **구매** 정책을 선택한 다음 각 조달 카테고리에 대해 **수령 시 구매 비용 발생** 을 선택합니다.
[![범주 정책 규칙 페이지.](./media/accruals2-1024x569.png)](./media/accruals2.png) 

**게시 설정** 의 **청구되지 않은 구매 지출** 및 **구매 발생** 계정은 상품 수령과 관련된 바우처가 게시될 때 사용됩니다.

이와 동일한 시나리오를 사용하여 제품 영수증을 게시하는 것이 총계정원장과 프로젝트 정보에 어떤 영향을 미치는지 살펴보겠습니다. 

**1단계:** 1,500달러에 컴퓨터 구입, 150달러에 설치 서비스 구입을 기록하는 프로젝트의 새 구매 주문을 생성하고 확인합니다.
[![새로운 구매 주문 만들기.](./media/accruals4-1024x497.png)](./media/accruals4.png) 

구매 주문이 확정되면 프로젝트에 대한 커밋된 비용의 트랜잭션이 생성됩니다. 
[![생성된 트랜잭션.](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> 커밋된 비용에 대한 트랜잭션은 **트랜잭션 원본** 필드가 **구매 주문** 으로 설정됩니다. 구매 주문을 만들고 확인해도 프로젝트에 대한 트랜잭션은 생성되지 않습니다. 

**2단계:** 상품과 서비스가 배송되고 제품 영수증이 등록됩니다. 

제품 영수증을 게시하면 바우처가 생성되어 원장에 게시됩니다. 바우처는 구매 지출, 청구되지 않은 계정, 크레딧 구매 발생 계정에 차변할 것입니다. 
[![바우처 트랜잭션.](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> 제품 영수증을 게시하면 프로젝트 범주에 대한 게시 설정이 아닌 조달 범주 및 제품에 대한 게시 설정이 사용됩니다. 구매 발생의 재정적 영향을 올바르게 반영하려면 이 설정을 조정해야 합니다. 

**조달 범주** 페이지에서 조달 범주를 프로젝트 범주에 매핑할 수 있습니다.
[![조달 범주 페이지.](./media/accruals7-1024x390.png)](./media/accruals7.png)

**3단계:** 공급업체 송장 초안을 생성합니다. 

제품 영수증을 게시해도 프로젝트 정보에 영향을 주지 않습니다. 이 문제를 해결하기 위해 구매 영수증을 게시한 후 즉시 공급업체 송장 초안을 생성할 수 있습니다. **구매 주문** 페이지 &gt; **송장 탭** &gt; **생성** &gt; **송장** 으로 이동합니다. 이렇게 하면 프로젝트 정보를 업데이트하는 보류 중인 송장 문서가 만들어집니다. 

공급업체 송장 초안을 생성하면 보류 중인 프로젝트 트랜잭션이 생성됩니다. 
[![보류 중인 프로젝트 트랜잭션.](./media/accruals8-1024x225.png)](./media/accruals8.png) 

**커밋된 비용** 페이지에서 1단계에서 만든 레코드가 닫히고 보류 중인 공급업체 송장에서 나오는 비용 약정을 반영하기 위해 새 레코드가 생성됩니다. 커밋된 비용에 대한 **트랜잭션 원본** 필드가 **공급업체 송장** 으로 설정됩니다.
[![확정된 비용 페이지.](./media/accruals9-1024x200.png)](./media/accruals9.png)

공급업체 송장은 실제 공급업체 송장이 도착할 때까지 보류 상태로 유지됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
