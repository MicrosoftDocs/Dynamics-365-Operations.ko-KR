---
title: 임대 사용자 역할 할당
description: 이 항목에서는 자산 임대에 사용되는 보안 역할에 관해 설명합니다. 또한 이러한 역할에 사용자를 할당하는 방법도 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7a3443cf9fa5b14ac0b3c4560ed45874939aa50cd665f4db46290f5af04bf6ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450775"
---
# <a name="assign-lease-user-roles"></a>임대 사용자 역할 할당

[!include [banner](../includes/banner.md)]

이 항목에서는 자산 임대에 사용되는 보안 역할에 관해 설명합니다. 또한 이러한 역할에 사용자를 할당하는 방법도 설명합니다.

자산 임대에서 액세스를 구분하는 세 가지 사용자 역할이 있습니다. 한 역할은 임대를 유지하는 데 적합하고, 다른 하나는 임대를 조회하는 데 적합하며, 다른 하나는 임대 사무원 임무를 수행하는 데 적합합니다. 각 역할에는 모든 임대 페이지에 특정 권한이 있으며 각 역할은 사용자가 직무에 따라 임대를 조회, 생성, 편집 또는 삭제할 수 있게 해줍니다.

| 역할           | 설명 |
|----------------|-------------|
| 임대 유지 | 이 역할의 사용자는 임대를 추가, 편집, 삭제 및 조회할 수 있습니다. 이 역할은 월별 분개장 항목 작성 및 게시, 새 임대 추가 등의 작업을 수행하는 일일 사용자를 위해 설계되었습니다. 이 역할은 모든 자산 임대 기능에 대한 액세스 권한을 부여합니다. |
| 임대 보기     | 이 역할의 사용자는 임대 기록, 일정을 조회하고 보고서를 실행할 수만 있습니다. 새 임대를 만들거나 기존 임대를 편집하거나 임대에 대한 분개장 항목을 만들 수는 없습니다. 이 역할은 임대, 임대 일정 및 해당 임대에 관해 발생하는 거래를 보기만 하면 되는 사용자를 위해 설계되었습니다. |
| 임대 사무원    | 이 역할의 사용자는 새 임대를 만들기만 수 있습니다. 기존 임대를 편집 또는 삭제하거나 임대 일정을 보거나 임대 분개장 항목을 게시할 수는 없습니다. 이 역할은 데이터 입력 작업을 하는 사용자를 위해 설계되었습니다. |

자산 임대에 사용되는 역할에 사용자를 할당하려면 다음 단계를 따르세요.

1. **시스템 관리 \> 보안 \> 역할에 사용자 할당** 으로 이동합니다.
2. **임대 유지**, **임대 사무원** 또는 **임대 보기** 역할을 선택한 다음 **수동으로 사용자 할당/제외** 를 선택합니다.
3. 역할에 할당할 사용자를 선택한 다음 **역할에 할당** 을 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
