---
title: 이메일로 클라이언트 경고 알림
description: 이 주제에서는 사전 정의된 이벤트가 발생하는 이메일 알림을 보내는 규칙을 설정하는 방법에 대한 정보를 제공합니다.
author: RichdiMSFT
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 4e2205ba3bdf5ec2a4e6d9390007eaf1098293c3dd2a5b2ff1b3c73c7de5a83f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460606"
---
# <a name="client-alert-notifications-by-email"></a>이메일로 클라이언트 경고 알림

[!include [banner](../includes/banner.md)]

필터링된 데이터 보기를 모니터링하고 사전 정의된 이벤트가 발생할 때 자동으로 이메일 알림을 보내는 사용자 지정 경고 규칙을 정의할 수 있습니다. 이메일 알림을 보내는 옵션은 지원되는 모든 알림 유형에 사용할 수 있으며 기존 알림 규칙에 대해 설정할 수도 있습니다.

기본 제공 컨트롤을 사용하여 시스템 일괄 작업의 필터링된 보기를 모니터링하는 경고 규칙을 만들 수 있습니다. **상태** 필드의 값을 모니터링하여 일괄 작업이 실패할 때 이메일을 보내는 경고 규칙을 구성할 수도 있습니다. 이러한 경고 규칙을 만든 후에는 더 이상 보고서에서 비즈니스 데이터 변경 사항을 확인할 필요가 없습니다. 대신 지능형 변경 감지 서비스가 모니터링을 수행하도록 할 수 있습니다.

클라이언트 경고는 Microsoft Office과의 통합을 통해 제공되는 이메일 하위 시스템에 따라 다릅니다. 전자 메일 배포가 로컬 메일 클라이언트에 의존하지 않도록 단순 메일 전송 프로토콜(SMTP) 공급자를 사용하는 것이 좋습니다.

이메일로 알림을 보내려면 고객이 통합 이메일 서비스를 구성해야 합니다. 이메일 알림은 경보 소유자를 대신하여 수신자에게 전송됩니다.

이메일 구성 방법에 대한 자세한 내용은 [이메일 구성 및 보내기](../organization-administration/configure-email.md)를 참조하십시오.

다음 이미지는 이제 **전자 메일 보내기** 옵션이 포함된 **경고 규칙 만들기** 대화 상자를 보여줍니다.

[![이메일 보내기 옵션이 예로 설정된 경고 규칙 대화 상자를 생성합니다.](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> **이메일 보내기** 옵션이 **예** 로 설정되어 있으면 알림 센터에서 경고 알림이 계속 전달됩니다.

## <a name="alert-notification-email-templates"></a>경고 알림 이메일 템플릿

이 서비스는 경고 알림의 기본 세부 정보를 전달하는 미리 정의된 이메일 템플릿을 사용하여 이메일 알림을 보냅니다.

다음 이미지는 이메일로 수신된 경고 알림의 구조를 보여줍니다.

[![기록 생성, 필드 변경 및 템플릿 삭제에 대한 템플릿 기반 경고 알림.](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]