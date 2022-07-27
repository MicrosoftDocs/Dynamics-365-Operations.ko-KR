---
title: 프로젝트 예산 워크플로 생성 및 제출
description: 이 절차는 프로젝트에 대한 예산을 생성하고 제출하는 방법을 보여줍니다.
author: Henrikan
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f410d824be717537e6dfb5dbd8b71ff7d992e0a
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2021
ms.locfileid: "8449494"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>프로젝트 예산 워크플로 생성 및 제출

[!include [banner](../../includes/banner.md)]

프로젝트 예산을 생성할 때 프로젝트의 예상 수익 및 비용을 입력하고 값을 사용하여 실제 프로젝트 트랜잭션을 제어할 수 있습니다. 프로젝트 예산 책정에는 승인을 위해 프로젝트 워크플로를 통과하기 위해 모든 원래 예산과 수정이 필요합니다. 워크플로는 예산 편성에 대한 통제력을 높이고 변경 내역 레코드를 생성합니다. [프로젝트를 생성](/dynamicsax-2012/appuser-itpro/create-a-project)한 후 이 절차를 사용하여 예산을 생성하고 제출합니다.

1. **모듈** > **프로젝트 관리 및 회계** > **프로젝트** > **모든 프로젝트** 로 이동합니다.
1. 프로젝트 목록에서 프로젝트를 선택합니다.
1. 프로젝트의 세부 정보 페이지에서 **계획** 탭을 선택합니다.
1. **예산** 그룹에서 **프로젝트 예산** 을 선택합니다.
1. **일반** 빠른 탭에서 다음 정보를 입력합니다.
   - **설명** 상자에 값을 입력합니다.
   - **원래 예산** 에 대한 옵션을 선택합니다.
   - **남은 예산** 에 대한 옵션을 선택합니다.
1. **비용** 빠른 탭을 확장하고 **새로 만들기** 를 선택합니다. 그런 다음 아래 설정을 지정합니다.
   - **트랜잭션 유형** 에 대한 옵션을 선택합니다.
   - 적절한 **범주** 를 선택합니다.
   - **원래 예산** 에 값을 입력합니다.
1. **수익** 빠른 탭을 확장하고 **새로 만들기** 를 선택합니다. 그런 다음 아래 설정을 지정합니다.
   - **트랜잭션 유형** 에 대한 옵션을 선택합니다.
   - **범주** 를 선택합니다.
   - **원래 예산** 의 값을 입력합니다.
1. **저장** 을 선택합니다.
1. **워크플로 \> 제출** 을 선택합니다.
1. **원래 예산 워크플로 검토 - 제출** 페이지에서 **설명** 을 입력하고 **제출** 을 선택합니다.
