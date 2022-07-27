---
title: 연결된 애플리케이션
description: 이 항목에서는 전자 송장 발행에서 연결된 애플리케이션을 설정하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59b67589139c0ce332716acf998825c6a024bded
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451678"
---
# <a name="connected-applications"></a>연결된 애플리케이션

[!include [banner](../includes/banner.md)]

연결된 애플리케이션은 RCS(Regulatory Configuration Service)를 통해 연결할 수 있는 Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management의 인스턴스입니다. 연결된 애플리케이션을 통해 Finance 또는 Supply Chain Management에서 세계화 기능의 일부를 구성하여 전자 송장 발행 시나리오가 작동하도록 할 수 있습니다.

세계화 기능을 배포할 때 Finance 또는 Supply Chain Management 애플리케이션에 적용할 수 있는 설정 정보를 RCS에서 연결된 적절한 애플리케이션으로 직접 게시할 수 있습니다.

UAT(User Acceptance Testing) 및 프로덕션 환경과 같은 여러 애플리케이션 환경이 있고 동일한 매개 변수를 다른 환경에 배포하여 설정을 일관되게 유지하려고 할 때 RCS에서 제공되는 Finance 또는 Supply Chain Management 매개 변수가 유용합니다.

## <a name="create-a-connected-application"></a>연결된 애플리케이션 만들기

1. RCS 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **환경** 섹션에서 **전자 송장 발행** 타일을 선택합니다.
3. **환경 설정** 페이지의 작업 창에서 **연결된 애플리케이션** 을 선택합니다.
4. **새로 만들기** 를 선택하여 연결된 애플리케이션을 만듭니다.
5. **이름** 필드에 연결할 애플리케이션의 이름을 입력합니다.
6. **유형** 필드에서 **Dynamics 365 Finance** 를 선택합니다.
7. **애플리케이션** 필드에서 연결할 환경의 URL을 입력합니다.
8. **테넌트** 필드에서 연결할 환경의 테넌트를 입력합니다.
9. **저장** 을 선택합니다.
10. 작업 창에서 **연결 확인** 을 선택하여 환경과의 연결을 테스트합니다. 페이지를 닫습니다.

## <a name="link-connected-applications-to-environments"></a>연결된 애플리케이션을 환경에 연결

1. **환경 설정** 페이지에서 **새로 만들기** 를 선택하여 연결된 애플리케이션을 환경에 할당합니다.
2. **연결된 애플리케이션** 필드에서 연결된 애플리케이션을 선택합니다.
3. **서비스 환경** 필드에서 서비스 환경을 선택합니다.
4. **저장** 을 선택한 다음 페이지를 닫습니다.
