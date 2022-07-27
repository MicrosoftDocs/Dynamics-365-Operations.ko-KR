---
title: 직원 셀프 서비스 구성
description: Microsoft Dynamics 365 Human Resources에서 직원 셀프 서비스의 최상위 탐색용 타일을 구성할 수 있습니다.
author: twheeloc
ms.date: 12/06/2021
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
ms.openlocfilehash: 83718856a864123d7941b21c078bcdb96a62cca8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452371"
---
# <a name="configure-employee-self-service"></a>직원 셀프 서비스 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources에서 **직원 셀프 서비스** 의 최상위 탐색용 타일을 구성할 수 있습니다. 복리후생 계획 타일은 사용자가 자격이 있는 복리후생 계획으로 안내합니다.

## <a name="set-up-a-benefit-plans-tile"></a>복리후생 계획 타일 설정

1. **복리후생 관리** 작업 영역의 **설정** 에서 **직원 셀프 서비스 매개 변수** 를 선택합니다.

2. **복리후생 계획 타일 설정** 탭을 선택하고 **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **계획 유형 코드** | **복리후생 셀프 서비스** 에서 이 타일을 선택했을 때 표시되는 계획 유형. |
   | **타일 ID** | 타일의 고유 식별자 |
   | **타일 레이블 텍스트** | **복리후생 셀프 서비스** 의 타일에 표시될 텍스트. |
   | **설명** | 타일에 대한 설명. |
   | **타일 배경 이미지** | 타일에 사용할 이미지의 URL(선택 사항). |
   | **공개 등록 추적** | 이 계획 유형에 대한 개설 등록 진행률을 추적하려면 이 옵션을 선택합니다. 예를 들어 **계획 유형 = 기타** 로 만든 계획이 있을 수 있습니다. 이러한 계획은 등록 진행률을 추적하지 않으려는 선택적 계획일 수 있습니다. 이 계획 유형을 선택하지 않으면 **공개 등록** 탭에서 등록 진행 또는 등록 완료를 추적할 때 이 유형의 계획이 무시됩니다. 이 설정은 모든 기간 및 법인에 대해 선택된 계획 유형에 적용됩니다. |

4. **저장** 을 선택합니다.

## <a name="set-up-a-flex-credit-plan-tile"></a>플렉스 크레딧 계획 타일 설정

1. **복리후생 관리** 작업 영역의 **설정** 에서 **직원 셀프 서비스 매개 변수** 를 선택합니다.

2. **플렉스 크레딧 타일 설정** 탭을 선택하고 **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **복리후생 크레딧 ID** | **복리후생 셀프 서비스** 에서 이 타일을 선택하면 표시될 플렉스 크레딧 프로그램 계획. |
   | **타일 ID** | 타일의 고유 식별자 |
   | **타일 레이블 텍스트** | **복리후생 셀프 서비스** 의 타일에 표시될 텍스트. |
   | **설명** | 타일에 대한 설명. |
   | **타일 배경 이미지** | 타일에 사용할 이미지의 URL(선택 사항). |
   | **공개 등록 추적** | 이 계획 유형에 대한 개설 등록 진행률을 추적하려면 이 옵션을 선택합니다. 예를 들어 **계획 유형 = 기타** 로 만든 계획이 있을 수 있습니다. 이러한 계획은 등록 진행률을 추적하지 않으려는 선택적 계획일 수 있습니다. 이 계획 유형을 선택하지 않으면 **공개 등록** 탭에서 등록 진행 또는 등록 완료를 추적할 때 이 유형의 계획이 무시됩니다. 이 설정은 모든 기간 및 법인에 대해 선택된 계획 유형에 적용됩니다. |

4. **저장** 을 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
