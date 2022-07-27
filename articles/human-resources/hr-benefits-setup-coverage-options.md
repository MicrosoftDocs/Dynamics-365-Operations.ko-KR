---
title: 보장 옵션 만들기
description: 이 항목에서는 복리후생 계획 또는 프로그램에서 참가자의 선택에 대한 Microsoft Dynamics 365 Human Resources의 보장 옵션에 대해 설명합니다.
author: twheeloc
ms.date: 08/24/2021
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
ms.openlocfilehash: 01eb0c56578cf6f6b070c4a05768ec5361993555
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452170"
---
# <a name="create-coverage-options"></a>보장 옵션 만들기


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

보장 옵션은 누가 보장해야 하는지 또는 보험 계획에서 얼마나 많은 보장을 받을 수 있는지를 결정합니다. 예를 들어 의료 계획의 경우 **직원만** 옵션, **직원 + 1** 옵션 및 **가족** 옵션이 있을 수 있습니다. 생명 보험의 경우 **1 x 급여** 또는 **2 x 급여** 로 보장을 제공할 수 있습니다.

복리후생 보장 옵션을 정의한 후에는 다시 사용할 수 있습니다. 옵션을 하나 이상의 계획과 연결할 수 있습니다.

> [!IMPORTANT]
> 보장 옵션을 정의한 후 복리후생 계획 유형에 첨부하세요. 그러면 계획 유형이 복리후생 계획 또는 프로그램과 연결됩니다. 계획 유형과 연결된 보장 옵션은 생성된 해당 유형의 모든 계획에서 사용할 수 있습니다.

## <a name="create-coverage-options"></a>보장 옵션 만들기
1. **복리후생 관리** 작업 영역의 **설정** 에서 **보장 옵션** 을 선택합니다.

2. **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **적용 범위 옵션** | 고유한 보장 옵션 이름. |
   | **설명** | 보장 옵션에 대한 설명. |
   | **보장 코드** | 보장 코드는 각 적격 보장 대상 유형에 대한 최소 및 최대 금액을 할당합니다. 보장 코드는 보장 대상 또는 계획 유형에 대해 허용되는 보장 금액을 나타냅니다. 보장 금액은 달러 금액 또는 백분율로 표현할 수 있습니다. 예:<ul><li>**직원+1** – 자격을 갖추려면 직원이 피부양자 한 명을 선택해야 합니다(둘 이상 선택되면 더는 자격이 없음).</li><li>**직원+가족** – 자격을 갖추려면 직원이 최소 두 명의 피부양자를 선택해야 합니다.</li></ul> |
   | **최대 수** | 최대 피부양자 수. |
   | **상태** | 보장 옵션의 상태. 보장 옵션 상태가 **비활성** 으로 설정된 경우 보장 옵션을 계획 유형에서 선택할 수 없습니다. |
   | **백분율** | 금액 백분율. 이 필드는 보장 코드 필드에서 % x 급여가 선택된 경우에만 활성화됩니다. |
   | **제수** | 보장 코드 % x 급여를 선택할 때 계산에 사용할 제수. |
   | **최소 백분율** | 백분율 보장 코드를 선택할 때의 최소 백분율. |
   | **최대 백분율** | 백분율 보장 코드를 선택할 때의 최대 백분율. |

4. **개인 연락처 자격 옵션** 에서 각 보장 옵션에 적절한 개인 연락처 자격 옵션을 연결합니다.

5. **셀프 서비스** 에서 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **직원 기여 금액 허용** | 직원이 복리후생을 선택할 때 복리후생 셀프 서비스에서 기여 금액을 수정할 수 있도록 허용할지 지정합니다. 이 확인란을 선택하면 직원이 복리후생 셀프 서비스에 입력한 기여 금액을 기준으로 복리후생 계획 매개 변수가 계산됩니다. |
   | **직원 보장 금액 허용** | 직원이 복리후생을 선택할 때 복리후생 셀프 서비스에서 보장 금액을 수정할 수 있도록 허용할지 지정합니다. 이 확인란을 선택하면 직원이 직원 셀프 서비스에 입력한 보장 금액을 기준으로 복리후생 계획 매개 변수가 계산됩니다. |

6. **저장** 을 선택합니다. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
