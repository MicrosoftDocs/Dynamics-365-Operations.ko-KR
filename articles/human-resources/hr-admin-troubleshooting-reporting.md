---
title: 보고 옵션
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources 보고서를 사용자 정의하거나 새 보고서를 생성하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3c82f3d4f040f680cab68228f1aa8ab16f548961
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452518"
---
# <a name="reporting-options"></a>보고 옵션


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



**환경 세부 정보**

이 문제는 모든 환경에 적용됩니다.

**징후**

고객이 Microsoft Dynamics 365 Human Resources 보고서를 사용자 지정하거나 새 보고서를 생성하려고 합니다.

**문제**

사용자가 내장된 Microsoft Power BI 보고서를 사용자 지정할 수 없습니다.

**해결 방법**

- Dataverse로 가는 Human Resources 데이터는 Power Apps Dataverse 커넥터를 통해 Power BI Desktop으로 보고될 수 있습니다. Dataverse에는 Human Resources 데이터의 일부가 포함되어 있습니다. Power BI 및 대시보드에 대한 자세한 내용은 [Power Apps Common Data Service로 Power BI 보고서 및 대시보드 만들기](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi)를 참조하십시오.
- 전자 보고(ER)는 Human Resources의 일부 보고서에 사용할 수 있습니다. ER 구성 옵션을 통해 고객 중심 사용자 지정을 할 수 있습니다.
- Microsoft Office 통합을 통해 Human Resources가 제공하는 다양한 데이터 엔터티를 사용하여 데이터를 Microsoft Excel 또는 Microsoft Word로 내보낼 수 있습니다.

**장기적 솔루션**

추가 Power BI 옵션을 사용할 수 있으며 더 많은 데이터와 엔터티가 Dataverse에 포함됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
