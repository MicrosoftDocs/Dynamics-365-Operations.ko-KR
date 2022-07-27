---
title: 고정 보상 계획에 직원 등록
description: 보상 및 복리후생 관리자는 직원을 고정 보상 계획에 할당하여 기본급을 관리할 수 있습니다.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b7c2423faa4a0c50d9d319a9e6f489e2946c36a7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452557"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a>고정 보상 계획에 직원 등록


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

보상 및 복리후생 관리자는 직원을 고정 보상 계획에 할당하여 기본급을 관리할 수 있습니다. 이 절차에서는 고정 계획이 생성되고 활성 상태이며 해당 계획에 대한 자격 규칙이 설정되었다고 가정합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 절차를 시작하려면 **Human Resources** > **작업자** > **직원** > **보상** > **고정 계획** 으로 이동합니다.

1. **새로 만들기** 를 클릭합니다.
2. **작업** 필드에서 **채용/재고용** 의 고정 보상 작업을 선택하여 직원 보상의 변경 사항을 설명합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. **직위** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
    * 표시되는 수준은 **직위** 에 할당된 **직무** 의 **보상** 빠른 탭 > **수준** 필드에서 가져온 것입니다. 직원에게 보상을 할당하려면 먼저 직무에 수준을 설정해야 합니다.  
6. **계획** 필드에서 직원에 대한 고정 보상 계획을 선택합니다. **계획** 조회는 **자격 규칙** 에 따라 직원이 자격이 있는 계획만 표시하도록 필터링됩니다.
7. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 보상 **적용** 및 **만료** 날짜는 기본적으로 작업자의 직위 할당 시작 및 종료 날짜부터 시작됩니다. 필요에 따라 이러한 날짜를 조정할 수 있습니다.  
    * 고정 보상 계획이 단계적 계획인 경우 직원의 정확한 급여 비율이 포함된 단계를 선택합니다. 고정 보상 계획이 등급 또는 구간 계획인 경우 직원의 급여 비율을 입력합니다. 급여 비율은 계획의 허용 오차 설정과 해당 직무의 보상 수준에 대한 최소 및 최대 기준점에 대해 검증됩니다.  
8. **확인** 을 클릭합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
