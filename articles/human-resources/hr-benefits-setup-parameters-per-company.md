---
title: 회사별 복리후생 관리 매개 변수 구성
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 회사별 복리후생 관리를 위한 매개 변수를 구성하는 방법을 설명합니다.
author: twheeloc
ms.date: 8/24/2021
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
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f6b3f068c9d3198afa8cd10aaa14bbc7ec9ef3c4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452161"
---
# <a name="configure-benefits-management-parameters-per-company"></a>회사별 복리후생 관리 매개 변수 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

복리후생을 제공하는 각 조직에 대해 복리후생 확인 이메일에 대한 설정을 구성해야 합니다.

## <a name="configure-confirmation-email-settings"></a>확인 이메일 설정 구성

1. **복리후생 관리** 작업 영역의 **설정** 에서 **인적 자원 매개 변수** 를 선택합니다.

2. **복리후생 관리** 탭에서 다음 필드에 값을 지정합니다. 

   | 필드 | 설명 |
   | --- | --- |
   | **확인 이메일 보내기** | 이 기능이 켜져 있으면 직원이 **직원 셀프 서비스** 의 복리후생 등록 환경에서 체크아웃할 때 확인 이메일이 직원에게 전송됩니다. |
   | **확인 이메일 템플릿** | 등록 확인을 보낼 때 사용할 조직 이메일 템플릿을 선택합니다. 템플릿을 선택하지 않으면 다음과 같은 일반 이메일이 전송됩니다.<br><br>%EmployeeFirstName% 님.<br><br>축하합니다! 복리후생 등록을 완료했습니다.<br><br>감사합니다.<br><Company/Org name> 복리후생. |
   | **기본 이메일 보낸 사람 주소** | 확인 이메일을 보낼 때 사용할 이메일 주소. |

3. **저장** 을 선택합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
