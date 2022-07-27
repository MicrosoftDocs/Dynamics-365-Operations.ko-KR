---
title: 모든 회사의 복리후생 관리 및 직원 셀프 서비스 매개 변수 설정
description: Microsoft Dynamics 365 Human Resources에서 복리후생 관리 및 직원 셀프 서비스의 매개 변수를 구성합니다.
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
ms.openlocfilehash: 822e5b37be7b2d5712d61bf7fb00f40d1692f406
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452284"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>모든 회사의 복리후생 관리 및 직원 셀프 서비스 매개 변수 설정


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources에서 복리후생 계획을 설정하려면 먼저 복리후생 관리 매개 변수를 구성해야 합니다. 이러한 매개 변수는 기본값, 사유 코드 및 기타 옵션을 설정합니다. 

## <a name="configure-general-parameters"></a>일반 매개 변수 구성

1. **복리후생 관리** 작업 영역의 **설정** 에서 **인적 자원 공유 매개 변수** 를 선택합니다.

2. **복리후생 관리** 탭에서 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **국가/지역** | **국가/지역** 필드는 우편 번호, 주/도의 표시 순서를 결정합니다. 선택한 국가가 드롭다운 목록에서 먼저 표시됩니다. |
   | **등록 이유 코드** | 공개 등록 처리 중에 직원 계획이 생성될 때 사용할 기본 사유 코드를 선택합니다. |
   | **취소 사유 코드** | 직원 복리후생 계획을 취소할 때 사용할 사유 코드. 취소 프로세스 중에 대화 상자에 표시됩니다. 사용자는 필요한 경우 **취소 사유 코드** 를 변경할 수 있습니다. |
   | **재개 사유 코드** | 직원 복리후생 계획을 재개할 때 사용할 사유 코드. 취소 프로세스 중에 대화 상자에 표시됩니다. 사용자는 필요한 경우 **재개 사유 코드** 를 변경할 수 있습니다. | 
   | **생활 이벤트 사유 코드** | 생활 이벤트가 발생할 때 사용할 사유 코드. |
   | **요율 변경 사유 코드** | 요율 변경 업데이트 프로세스 중 직원 복리후생 계획을 취소하고 재개할 때 사용할 사유 코드. 요율 변경 업데이트 프로세스에 의해 변경된 레코드를 나타냅니다. |
   | **복리후생 연봉** | 직원의 **복리후생 연봉** 금액을 설정할 수 있습니다. Human Resources는 보장 금액을 결정할 때 고정 보상 연간 금액 대신 **복리후생 연봉** 금액을 사용합니다. |
   | **신입사원 자격** | 신입사원이 자격이 있는지를 지정합니다. |
   | **신입사원 등록 기간** | 신입사원 등록이 허용되는 기간.</br></br>**참고** : 이 설정은 계획 자격 규칙에 설정된 신규 고용 등록 기간을 모두 무시합니다. |
   | **기본 지불 빈도** | 새 작업자가 추가될 때 사용할 기본 급여 빈도입니다. |
   | **생활 이벤트 활성화됨** | 생활 이벤트를 활성화합니다. |
   | **기존 복리후생 양식 숨기기** | 기존 복리후생 양식을 숨길 수 있습니다. |
   | **복리후생 확인** | 셀프 서비스 복리후생 체크아웃 시 사용할 인증 텍스트. |
   | **피지명인 자동 선택** | 계획 옵션에 대한 자격을 기준으로 피부양자와 수혜자를 자동으로 선택할지를 지정합니다. |

3. **저장** 을 선택합니다.

## <a name="configure-employee-self-service-parameters"></a>직원 셀프 서비스 매개 변수 구성

1. **복리후생 관리** 작업 영역의 **설정** 에서 **인적 자원 매개 변수** 를 선택합니다.

2. **복리후생 관리** 탭에서 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **복리후생 확인** | 셀프 서비스 복리후생 체크아웃 시 사용할 인증 텍스트. |
   | **피지명인 자동 선택** | 계획 옵션에 대한 자격을 기준으로 피부양자와 수혜자를 자동으로 선택할지를 지정합니다. |

3. **저장** 을 선택합니다.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
