---
title: 분석 보고서 문제 해결
description: 이 항목에서는 고객의 데이터 변경 사항이 고객의 작업 영역에 나타나지 않는 경우 문제를 해결하고 진단하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6ea04c06858cc98b0e233b9133d9dfbebfe59fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452389"
---
# <a name="troubleshoot-analytic-reports"></a>분석 보고서 문제 해결


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**문제**

고객의 데이터 변경 내용이 고객 작업 영역의 **분석** 탭에 표시되지 않습니다.

**원인**

기본적으로 Microsoft Power BI 보고서는 배포 측정 일괄 작업 일정에 따라 4시간마다 새로 고쳐집니다.

**해결**

이 문제는 단지 타이밍의 문제일 수 있습니다. 다음 단계에 따라 일괄 작업을 시작하고 분석 작업 영역을 업데이트하세요.

1. **시스템 관리 \> 연결 \> 일괄 작업 \> 일괄 작업** 에서 **일괄 작업** 페이지를 엽니다. 또는 검색을 사용하고 **일괄 작업** 을 입력합니다.
1. 목록에서 **배포 측정** 작업을 찾습니다.
1. 페이지 상단에서 **편집** 을 선택하고 분석을 새로 고치는 예약 시작 날짜/시간을 현재 시간에 더 가까운 값으로 설정합니다.

![일괄 작업.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
