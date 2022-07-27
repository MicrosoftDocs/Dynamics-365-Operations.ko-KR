---
title: 기준 계획 작업 취소
description: 이 항목에서는 기본 제공 계획 기능을 사용하는 활성 계획 작업을 취소하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 27a48473a934e0db9986d6e588fc769ba9d2f605d72b2465976cb20a1ad93d16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446671"
---
# <a name="cancel-a-master-planning-job"></a>기준 계획 작업 취소

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에는 기준 계획 작업을 취소하기 위한 여러 옵션이 있습니다. 예를 들어, 기준 계획 작업이 실수로 시작되었거나 예상보다 오래 실행되어 종료하려는 경우 취소할 수 있습니다. 계획 작업을 취소하는 가장 좋은 방법은 **완료되지 않은 계획 프로세스** 페이지에서 수행하는 것입니다. **일괄 작업** 및 **향상된 일괄 작업** 페이지의 대체 옵션은 **완료되지 않은 계획 프로세스** 페이지에서 기준 계획 작업 취소가 몇 분 내에 완료되지 않은 경우에만 사용해야 합니다.

## <a name="preferred-cancel-option"></a>선호하는 취소 옵션
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>**완료되지 않은 계획 프로세스** 페이지에서 기준 계획 작업 취소
1. **마스터 플랜 > 문의 및 보고 > 마스터플랜 > 미완성 기획과정** 으로 이동합니다.
2. 취소할 계획 프로세스가 있는 라인을 선택합니다.
3. **취소** 를 클릭합니다.

## <a name="additional-cancel-options"></a>추가 취소 옵션
이는 **완료되지 않은 계획 프로세스** 페이지의 기준 계획 작업 취소가 몇 분 안에 완료되지 않은 경우에만 사용해야 합니다.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>**일괄 작업** 페이지에서 기준 계획 작업 삭제
1. **시스템 관리 > 문의 > 일괄 작업** 으로 이동합니다.
2. 삭제할 계획 작업이 있는 라인을 선택합니다.
3. **삭제** 를 클릭합니다.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>**향상된 일괄 작업** 페이지에서 기준 계획 작업 중단
1. **시스템 관리 > 문의 > 일괄 작업** 으로 이동합니다.
2. 작업 ID가 목록에 표시되지 않으면 **향상된 양식으로 전환** 을 클릭하세요. 그렇지 않으면 다음 단계로 진행합니다.
3. 일괄 작업을 엽니다. 종료하려는 작업이 있는 일괄 작업의 **작업 ID** 를 클릭합니다.
4. **일괄 작업** 에서 종료할 작업을 선택합니다.
5. **상태 변경** 을 클릭하고 **취소** 를 선택한 다음 **확인** 을 클릭합니다.
6. **일괄 작업** 빠른 탭에서 **중단** 을 클릭합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]