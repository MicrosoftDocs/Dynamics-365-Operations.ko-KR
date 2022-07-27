---
title: 사유 코드 설정
description: Dynamics 365 Human Resources는 직원의 복리후생이 변경되는 이유를 설명하기 위해 사유 코드를 사용합니다.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a30a59a648d54eda771845b8bee52df43987d3d1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452434"
---
# <a name="set-up-reason-codes"></a>사유 코드 설정


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources는 직원의 복리후생이 변경되는 이유를 설명하기 위해 사유 코드를 사용합니다.

> [!NOTE]
> 2021년 1월부터 사유 코드가 **혜택 관리** 작업 영역 대신 **인사 관리** 작업 영역으로 마이그레이션되었습니다. 자세한 내용은 [수동으로 사유 코드를 인사 관리로 마이그레이션](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management)을 참조하세요.

## <a name="create-reason-codes"></a>사유 코드 만들기

1. **인사 관리** 작업 영역(또는 사유 코드가 마이그레이션되지 않은 경우 **혜택 관리** 작업 영역)에서 **연결** 을 선택한 다음 **사유 코드** 를 선택합니다.

2. **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **사유 코드** | 직원이 복리후생 계획 등록을 변경하는 이유를 식별하는 고유한 이름. |
   | **설명** | 사유 코드에 대한 설명. |

4. **적용 가능한 시나리오** 에서 **혜택 관리** 를 **예** 로 설정합니다. (이유 코드가 **인사 관리** 작업 영역으로 마이그레이션되지 않은 경우 적용되지 않습니다.)

5. **저장** 을 선택합니다.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>수동으로 사유 코드를 인사 관리로 마이그레이션

2021년 1월부터 사유 코드가 **혜택 관리** 작업 영역 대신 **인사 관리** 작업 영역으로 마이그레이션되었습니다. 대부분의 사유 코드 데이터는 사용자 환경에서 자동으로 마이그레이션됩니다. 일부 사유 코드 데이터가 마이그레이션되지 않을 수 있습니다. 예를 들어, 사유 코드는 이제 최대 15자이므로 15자를 초과하는 사유 코드는 자동으로 마이그레이션되지 않습니다.

**혜택 관리** 작업 영역의 **연결** 페이지에 마이그레이션에 대해 알려주고 마이그레이션되지 않은 사유 코드가 있는지 알려주는 배너가 표시됩니다.

1. 마이그레이션 상태에 대한 자세한 내용을 보려면 **사유 코드** 를 클릭합니다.

   [![사유 코드.](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. 마이그레이션이 실패한 사유 코드를 선택합니다.

   [![사유 코드 마이그레이션 상태.](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. **마이그레이션 사유 코드** 를 선택하세요.

   [![마이그레이션 사유 코드.](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. **복리후생 사유 코드 마이그레이션** 창에는 인사 관리 사유 코드에 매핑하는 두 가지 옵션이 있습니다.

   - 인사 관리에서 기존 사유 코드를 사용하려면 **기존 사유 코드 사용** 드롭다운에서 하나를 선택합니다.
     > [!NOTE]
     > 다른 복리후생 관리 사유 코드가 아직 마이그레이션되지 않은 경우 인사 관리에서 기존 사유 코드만 사용할 수 있습니다.
   - 인사 관리에서 새 사유 코드를 만들려면 **새 사유 코드** 에 새 사유 코드를 입력한 다음 **새 설명** 에 설명을 입력합니다.

   [![인사 관리 사유 코드에 매핑.](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

사유 코드가 인사 관리로 마이그레이션된 후 복리후생 관리에서 사용하는 옵션이 자동으로 **예** 로 설정됩니다.

[![복리후생 관리에서 사유 코드 사용.](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
