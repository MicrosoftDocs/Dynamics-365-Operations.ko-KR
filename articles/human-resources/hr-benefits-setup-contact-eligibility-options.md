---
title: 개인 연락처 자격 옵션 구성
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 개인 연락처 자격 옵션을 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: ad9dc9d12bcc419c3925b0f78566d9f3eb0a1e35
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452626"
---
# <a name="configure-personal-contact-eligibility-options"></a>개인 연락처 자격 옵션 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources에서 복리후생에 사용할 수 있는 개인 연락처 유형을 구성하는 방법을 설명합니다. 개인 연락처는 계획에 따라 보장될 개인(피부양자) 또는 계획의 혜택을 받을 개인(수혜자)입니다. 피부양자는 일반적으로 배우자 또는 자녀입니다. 수혜자는 배우자, 자녀, 신탁 또는 부모가 될 수 있습니다.

1. **복리후생 관리** 작업 영역의 **설정** 에서 **개인 연락처 자격 옵션** 을 선택합니다.

2. **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **자격 옵션** | 자격 옵션을 식별하기 위한 고유 자격 옵션 이름 또는 코드. |
   | **설명** | 자격 옵션에 대한 간략한 설명. |
   | **연락처 자격 코드** | 개인 자격 옵션을 가장 잘 설명하는 시스템 코드. 다음 중에서 선택할 수 있습니다. <ul><li>관계</li><li>학생</li><li>고령 피부양자</li><li>고령 장애인 피부양자</li></ul> |
   | **상태** | 자격 옵션의 상태. 자격 옵션의 상태가 비활성으로 설정된 경우 해당 개인의 개인 연락처에 대해 연락처 자격 옵션을 선택할 수 없습니다. |
   | **관계** | 개인 연락처와 직원 간의 관계를 지정합니다. 이 필드는 연락처 자격 코드가 관계로 설정된 경우에만 활성화됩니다. |
   | **나이** | 복리후생 계획에 대한 적격 개인 연락처의 최고 나이. 이 필드는 관계를 선택한 경우에만 활성화됩니다. 이 나이는 계산된 개인 연락처 나이와 비교됩니다. 계산된 나이: (보장 날짜 – 개인 연락처 생일 / 365). 이 숫자는 항상 정수입니다. |

4. **저장** 을 선택합니다. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
