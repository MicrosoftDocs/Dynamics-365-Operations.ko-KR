---
title: Power Apps 및 Power Automate를 이용한 Talent 확장
description: 이 문서에서는 Microsoft Power Apps 및 Microsoft Power Automate를 사용하는 Microsoft Dynamics 365 Human Resources에 대한 확장성 시나리오의 몇 가지 예를 설명합니다.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fedf9b35e5dc8372fd82c6308ec5b1452eab7e8f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452620"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Power Apps 및 Power Automate를 이용한 확장


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Microsoft Power Apps 및 Microsoft Power Automate를 사용하는 Microsoft Dynamics 365 Human Resources에 대한 확장성 시나리오의 몇 가지 예를 설명합니다. 각 예제와 연결된 솔루션 패키지를 Power Apps 환경으로 가져올 수 있습니다. 그런 다음 패키지를 지침이나 시작점으로 사용하여 조직에 적용할 시나리오를 구현할 수 있습니다.

> [!IMPORTANT]
> 이 항목에 설명된 템플릿과 앱을 "있는 그대로" 사용하려면 구현에 관한 모든 시나리오가 지원되는지 테스트해야 합니다.

## <a name="prerequisites"></a>전제 조건

- 패키지를 가져오려면 사용자에게 **환경 결정자** 권한이 있어야 합니다.
- 앱을 내보내거나 가져오려면 사용자에게 Power Apps 플랜 2 라이선스 또는 Power Apps 플랜 2 평가판 라이선스가 있어야 합니다.

## <a name="integration-with-microsoft-365-power-automate"></a>Microsoft 365, Power Automate와 통합

**Microsoft 365와 통합 앱** 을 사용하여 Microsoft 365에서 로그인한 사용자의 팀 정보를 추출할 수 있습니다. Human Resources의 작업자를 참조하여 직원 식별 유형을 추출합니다. 관리자는 사원 ID 유형의 만료 날짜를 확인할 수 있습니다. 직원 ID 유형이 만료되는 경우 이메일 알림을 보낼 수도 있습니다. Power Automate는 이 알림을 보내기 위해 Power Apps와 통합합니다. 알림이 전송되면 확인이 Power Automate에서 Power Apps로 다시 전송됩니다. 식별 유형에는 운전 면허증, 여권 및 기타 허용되는 신분증이 포함됩니다.

다른 시나리오에 대해 이 앱을 확장할 수 있습니다. 예를 들어 팀 휴가 정보, 일정 이벤트 및 팀별 이벤트를 표시하는 데 사용할 수 있습니다.

**Microsoft 365, Power Automate와 통합** 탭을 다운로드하려면 Microsoft 다운로드 센터에서 [Microsoft 365와 통합](https://go.microsoft.com/fwlink/?linkid=2081787)으로 이동하세요.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – SQL 연결 및 실행

**Power Automate – SQL 연결 및 실행** 템플릿은 Microsoft SQL Server와 연결하여 SQL 쿼리를 실행할 수 있습니다.

이 템플릿은 SQL 테이블을 읽고 업데이트하지만 확장하여 다른 시나리오에 사용할 수 있습니다. 예를 들어 Dataverse의 준비 테이블을 SQL Server의 레코드로 채우고 SQL Server의 증분 푸시를 사용하여 준비 테이블을 주기적으로 동기화하는 데 사용할 수 있습니다.

고급 쿼리가 흐름과 통합되어 데이터 변환 및 증분 푸시가 가능합니다.

**Power Automate – SQL 연결 및 실행** 템플릿을 다운로드하려면 Microsoft 다운로드 센터의 [Power Automate – SQL 연결 및 실행](https://go.microsoft.com/fwlink/?linkid=2081789)으로 이동하세요.

## <a name="additional-resources"></a>추가 리소스

[Microsoft Power Platform](/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
