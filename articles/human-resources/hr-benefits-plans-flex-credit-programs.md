---
title: 플렉스 크레딧 프로그램 설정
description: Microsoft Dynamics 365 Human Resources의 플렉스 크레딧 프로그램을 사용하여 미리 결정된 플렉스 크레딧 수에 따라 복리후생에 직원을 등록할 수 있습니다.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f28e3fb603fde2c19669e9936ea0bdcfc866d0e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452176"
---
# <a name="set-up-flex-credit-programs"></a>플렉스 크레딧 프로그램 설정


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources의 플렉스 크레딧 프로그램을 사용하여 미리 결정된 플렉스 크레딧 수에 따라 복리후생에 직원을 등록할 수 있습니다. 직원은 플렉스 크레딧을 할당하는 방법을 선택할 수 있습니다. 예를 들어 직원이 배우자의 건강 보험에 가입되어 있는 경우 다른 혜택을 받기 위해 건강 보험에 사용했을 크레딧을 사용할 수 있습니다. 

1. **복리후생 관리** 작업 영역의 **계획** 에서 **플렉스 크레딧 프로그램** 을 선택합니다.

2. **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **복리후생 크레딧 ID** | 플렉스 크레딧 프로그램의 고유 식별자. |
   | **설명** | 플렉스 크레딧 프로그램에 대한 설명. | 
   | **시작 날짜** | 플렉스 크레딧 프로그램이 활성화된 날짜. |
   | **종료 날짜** | 플렉스 크레딧 프로그램의 종료 날짜. 플렉스 크레딧 프로그램에 예정된 만료 날짜가 없음을 나타내기 위해 기본값(2154-12-31)을 그대로 둘 수 있습니다. |
   | **총 크레딧 값** | 각 직원이 복리후생을 위해 사용해야 하는 크레딧 수. |
   | **비례 배분 규칙** | 플렉스 크레딧 기간 중간에 직원이 채용된 경우 플렉스 크레딧을 비례 배분하는 데 사용할 규칙. </br></br><ul><li>**없음** – 직원이 플렉스 크레딧 프로그램 기간이 시작된 후에 채용된 경우 플렉스 크레딧을 받지 않습니다.</li><li>**전체 크레딧** – 직원은 고용된 시기에 관계없이 전체 플렉스 크레딧을 받습니다.</li><li>**비례 배분** – 직원은 시작 날짜를 기준으로 비례 배분된 플렉스 크레딧을 받습니다.</li></ul> |
   | **플렉스 크레딧 비례 배분 공식** | 플렉스 크레딧 프로그램의 복리후생 기간 중간에 채용된 직원에게 플렉스 크레딧을 비례 배분하는 데 사용할 규칙. 비례 배분은 고용 시작 날짜를 기준으로 합니다. 이 필드는 **비례 배분 규칙** 필드에서 **비례 배분** 을 선택한 경우에만 사용됩니다. </br></br><ul><li>**일별** – 직원이 받는 플렉스 크레딧 수를 일별로 비례 배분합니다. 총 플렉스 크레딧 수는 해당 기간의 일수로 나뉩니다. 예를 들어 복리후생 기간이 400일인 경우 시스템은 총 플렉스 크레딧 수를 400으로 나누어 직원이 하루에 받는 플렉스 크레딧 수를 계산합니다.</li><li>**이번 달** – 직원이 받는 플렉스 크레딧 수를 월 수준으로 비례 배분하여 이번 달로 반올림합니다. 총 플렉스 크레딧 수는 해당 기간의 개월 수로 나뉩니다. 예를 들어 복리후생 기간이 15개월인 경우 시스템은 총 플렉스 크레딧 수를 15로 나누어 직원이 매월 받는 플렉스 크레딧 수를 계산합니다.</li><li>**다음 달** – 직원이 받는 플렉스 크레딧 수를 월 수준으로 비례 배분하여 다음 달로 반올림합니다. 총 플렉스 크레딧 수는 해당 기간의 개월 수로 나뉩니다. 예를 들어 복리후생 기간이 15개월인 경우 시스템은 총 플렉스 크레딧 수를 15로 나누어 직원이 매월 받는 플렉스 크레딧 수를 계산합니다.</li></ul> |
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
