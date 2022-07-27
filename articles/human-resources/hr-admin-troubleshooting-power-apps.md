---
title: Power Apps 관리 센터에서 환경을 생성할 수 없음
description: 이 항목에서는 관리자가 Microsoft Power Apps 관리 센터에서 환경을 생성할 수 없는 경우 수행할 작업에 대해 설명합니다.
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
ms.openlocfilehash: 937b372fa95c8076666aed14c2b34b12e8029c4d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452386"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Power Apps 관리 센터에서 환경을 생성할 수 없음


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**문제**

- 테넌트/환경 관리자가 Microsoft Power Apps 관리 센터에서 환경을 생성할 수 없습니다.
- 사용자에게 환경을 만들 수 있는 라이선스가 없습니다.

**해결 방법**

테넌트 관리자가 환경을 생성하는 사용자에게 유효한 Power Apps P2 라이선스를 할당했는지 확인합니다. 다음 Microsoft Dynamics 서비스 계획은 환경을 생성할 수 있는 권한을 제공합니다.

| 전체 제품 재고 관리 단위(SKU)       | Power Apps P2 서비스 계획  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps for Dynamics 365 |

다양한 Microsoft Office SKU도 독립 실행형 Power Apps Plan 2 SKU와 함께 권한을 제공합니다. 중요한 점은 이러한 SKU 중 하나가 있어야 한다는 것입니다.

1. [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments)로 이동합니다.
2. [Human Resources 준비](/dynamics365/unified-operations/talent/provisioning-talent)의 지침에 따라 환경을 생성합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
