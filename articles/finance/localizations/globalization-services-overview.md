---
title: Dynamics 365 세계화 서비스
description: 이 항목에서는 Microsoft Dynamics 365 세계화 서비스에 대한 개요를 제공합니다.
author: JaneA07
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1dfe88bf6eb0cf479f8febd8a599b165b71d932d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451456"
---
# <a name="dynamics-365-globalization-services"></a>Dynamics 365 세계화 서비스

[!include [banner](../includes/banner.md)]

다음 세계화 서비스는 일부 Microsoft Dynamics 365 Online 서비스에 있는 기능을 확장하도록 구성할 수 있습니다.

- **RCS(Regulatory Configuration Service)** 는 다양한 유형의 전자 문서 및 보고서 구성을 지원합니다. RCS는 구성 리포지토리가 독립형 서비스인 전자 보고(ER) 디자이너의 향상된 버전을 제공합니다. 자세한 내용은 [Regulatory Configuration Service](rcs-overview.md)를 참조하세요.
- **전자 송장 발행** 은 인증 및 응답 처리를 포함하여 외부 웹 서비스와의 연결을 위해 변환, 디지털 서명 및 구성 가능한 통합을 위한 구성 가능한 형식을 함께 제공합니다. 자세한 내용은 [전자 송장 발행](e-invoicing-service-overview.md)을 참조하세요.
- **세금 계산** 은 다중 세금 ID, 세금 코드 결정, 세금 계산 디자이너 및 런타임 엔진을 지원하여 전 세계의 복잡한 세금 규정을 준수할 수 있는 향상된 유연성을 제공합니다. 자세한 내용은 [세금 계산](global-tax-calcuation-service-overview.md)을 참조하세요.

이러한 세계화 서비스는 다음 Dynamics 365 온라인 서비스와의 기본 통합을 제공합니다.

| 온라인 서비스 | RCS | 전자 송장 발행 | 세금 계산(프리뷰) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | 예 | 예 | 예 | 
| Dynamics 365 Supply Chain Management | 예 | 예 | 예 | 
| Dynamics 365 Project Operations | 예 | 예 | 해당 없음 | 
| Dynamics 365 Commerce | 예 | 해당 없음 | 해당 없음 | 

> [!NOTE]
> RCS에 대한 Azure 지리적 위치(지역)의 가용성 차이로 인해 이 서비스를 구성하면 해당 Dynamics 365 온라인 서비스에 선택된 지역 외부로 고객 데이터가 전송될 수 있습니다. 자세한 내용은 [Dynamics 365 및 Power Platform: 가용성, 데이터 위치, 언어, 현지화](https://aka.ms/rcs/D365Productavailabilityguide)를 참조하세요.