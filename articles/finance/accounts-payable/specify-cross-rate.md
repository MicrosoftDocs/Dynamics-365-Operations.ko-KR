---
title: 교차율 지정
description: 이 항목에서는 Microsoft Dynamics 365 Finance의 교차율에 대한 정보를 설명합니다.
author: abruer
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c46ac3324a985810ede61072190014538d0b7ed36f7eedfc387468619cc88cb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450364"
---
# <a name="specify-the-cross-rate"></a>교차율 지정

[!include [banner](../includes/banner.md)]

이 항목에서는 교차율의 목적과 송장으로 결제를 결제할 때 교차율을 지정하는 방법에 대해 설명합니다. 다음 조건이 모두 적용되는 경우 교차율을 사용하십시오. 
-   송장으로 결제를 결제하고 있습니다. 
-   결제 라인과 송장 라인이 다른 통화를 사용합니다. 
-   두 통화 모두 회계 통화가 아닙니다. 

교차율은 결제 회계 통화에 대한 결제 트랜잭션 통화 환산을 계산하는 데 사용되지 않습니다. 대신, 환율표에서 환율을 검색하여 결제 트랜잭션 통화 금액과 결제 회계 통화 금액의 가치를 계산합니다. 

예를 들어 회계 통화는 USD, 송장 통화는 CAD, 결제 통화는 EUR입니다. 교차 환율을 사용하면 CAD와 EUR 간에 직접 환산할 환율을 입력할 수 있으며, USD를 통해 환산할 필요가 없습니다. 송장, 기본 결제를 선택할 때 송장 라인에 대한 교차율을 입력할 수 있습니다. 교차율은 결제일 현재 해당 트랜잭션에 대한 통화 간의 환율입니다.

1.  다음 페이지 중 하나로 이동합니다.
- **수취 계정 > 공통 > 고객 > 모든 고객** 
- **지급 계정 > 공통 > 공급업체 > 모든 공급업체** 
- **조달 및 소싱 > 공통 > 공급업체 > 모든 공급업체**
2.  미결 트랜잭션을 결제할 고객 또는 공급업체를 선택합니다. 
3.  고객의 경우 **모든 고객** 목록 페이지에서 **수집 > 미결 트랜잭션 정산** 으로 이동합니다. 공급업체의 경우 **모든 공급업체** 목록 페이지에서 **송장 > 미결 트랜잭션 정산** 으로 이동합니다. 
4.  기본 결제인 트랜잭션을 선택한 다음 **결제 표시** 를 클릭합니다. **표시** 열의 확인란이 선택되고 **기본 결제** 열에 정보 아이콘이 표시됩니다. 
5.  **교차율** 필드에 결제일 현재 송장 통화와 결제 통화 간의 환율을 입력합니다. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]