---
title: 금융 및 운영 앱에 대한 도움말 환경 구성
description: 이 항목에서는 일부 Microsoft Dynamics 365 앱의 도움말 시스템 구성 요소에 대한 정보를 제공합니다.
author: margoc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bac06e258a96bb50bb6de7957e3e5ed07e966127
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460751"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>금융 및 운영 앱에 대한 도움말 환경 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 항목에서는 Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce 및 Dynamics 365 Human Resources와 같은 금융 및 운영 앱용 도움말 시스템의 구성 요소에 대한 개요를 찾을 수 있습니다. 이 항목에서는 이러한 구성 요소를 연결하는 방법도 설명하고 사용자 지정 도움말을 만드는 프로세스에 대한 요약을 제공합니다.

## <a name="help-architecture"></a>도움말 아키텍처

금융 및 운영 앱에는 [Microsoft Dynamics 365 문서](/dynamics365/) 사이트에 게시된 개념 개요 및 기타 주제가 포함되어 있습니다. 이 콘텐츠는 제품 내 **도움말** 창에서 액세스할 수 있습니다. 다음 그림은 도움말 시스템의 부분을 보여줍니다.

[![도움말 아키텍처.](./media/help-architecture.png)](./media/help-architecture.png)

제품 내 도움말 시스템은 docs.microsoft.com 및 기타 연결된 웹사이트에서 기사를 가져옵니다. 또한 Microsoft Dynamics Lifecycle Services(LCS)의 BPM(비즈니스 프로세스 모델러)에 저장된 작업 가이드를 가져옵니다.

## <a name="adding-task-guides"></a>작업 가이드 추가

> [!NOTE]
> **작업 가이드** 탭은 현재 인사부 또는 상거래에서 사용할 수 없습니다. <!--We are currently working to enable this functionality in a future release.--> 그러나 인적 자원의 시작하기 환경에 있는 작업 가이드는 기본 기능을 다루기 위해 계속 사용할 수 있습니다. 인적 자원 및 상업 분야 모두에 대해 절차상의 도움을 [Microsoft Dynamics 365 문서](/dynamics365/) 사이트에서 받을 수 있습니다.

**시스템 매개 변수** 페이지에서 시스템 관리자는 구현을 위해 관련 작업 가이드 라이브러리에 대한 액세스를 구성할 수 있습니다.

> [!NOTE]
> - 도움말을 구성하려면 앱이 배포된 테넌트와 동일한 테넌트의 계정을 사용하여 로그인해야 합니다.
> - LCS 라이브러리는 로컬 VHD(가상 하드 드라이브)에서 실행 중인 앱 인스턴스에서 연결할 수 없습니다.

[![도움말 설정이 있는 시스템 매개변수 양식.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

솔루션에 대한 작업 가이드를 구성하려면 **시스템 매개 변수** 페이지의 단계를 따르세요.

> [!IMPORTANT]
> **도움말** 탭을 처음 열 때 Lifecycle Services에 연결해야 합니다. 반드시 양식 중간에 있는 링크를 선택하고 연결을 기다린 후 대화 상자를 닫고 **확인** 을 선택하여 **시스템 매개변수** 페이지로 이동합니다.
>
> [![LCS에 연결](./media/connect-to-lcs-crop-1024x365.png "LCS에 연결.")](./media/connect-to-lcs-crop.png)

1. 연결할 Lifecycle Services 프로젝트를 선택합니다.
2. 작업 기록을 검색할 BPM 라이브러리(선택한 프로젝트 내)를 선택합니다.
3. BPM 라이브러리의 표시 순서를 설정합니다. 표시 순서는 라이브러리의 작업 기록이 **도움말** 창에 표시되는 순서를 정의합니다.

이 단계를 완료한 후 **도움말** 창을 열고 **작업 가이드** 탭을 선택할 수 있습니다. 이제 재무 및 운영 앱에서 현재 보고 있는 페이지에 적용되는 작업 가이드가 표시됩니다. 작업 가이드가 없으면 키워드를 입력하여 검색 범위를 좁힐 수 있습니다.

### <a name="showing-translated-task-guides"></a>번역된 작업 가이드 표시

번역된 작업 가이드는 2016년 5월 APQC 통합 라이브러리 및 시작하기 라이브러리에서 처음 릴리스되었습니다. 현지화된 작업 가이드 도움말을 보려면 Dynamics 365 솔루션이 2016년 5월 라이브러리에 연결되어 있는지 확인하세요. 사용자는 **옵션** &gt; **기본 설정** 아래의 언어 설정을 변경하여 작업 가이드가 표시되는 언어를 변경할 수 있습니다.

> [!NOTE]
> 많은 작업 가이드가 번역되었지만 클라이언트는 현재 번역된 작업 가이드 이름을 표시하지 않습니다. 또한 2016년 5월 라이브러리에서는 2016년 2월에 릴리스된 작업 가이드에 대해서만 번역이 제공됩니다. Microsoft는 추가 번역이 포함된 업데이트된 라이브러리를 출시할 예정입니다.
>
> - 작업 가이드가 번역된 경우 해당 작업 가이드를 열면 작업 가이드의 모든 텍스트가 선택한 언어로 표시됩니다.
> - 작업 가이드가 아직 번역되지 않은 경우 해당 작업 가이드를 열면 일부 텍스트만(컨트롤의 텍스트) 선택한 언어로 표시됩니다.

## <a name="adding-custom-help"></a>사용자 정의 도움말 추가

작업 가이드를 사용하여 사용자 정의 도움말을 만들거나 사용자 정의 도움말 웹 사이트를 **도움말** 창에 연결할 수 있습니다.

### <a name="create-custom-help-by-using-task-guides"></a>작업 가이드를 사용하여 사용자 지정 도움말 만들기

구현을 반영하는 작업 기록을 만든 다음 LCS의 비즈니스 프로세스 라이브러리에 저장하여 지원되는 앱에 대한 사용자 지정 도움말을 만들 수 있습니다. 인적 자원에 대한 사용자 지정 작업 가이드를 만들 수 없습니다.

파트너이고 라이브러리를 기업 라이브러리로 승격하고 솔루션에 포함하면 고객이 사용할 수 있습니다. APQC 통합 라이브러리의 복사본을 만든 다음 복사본에서 작업 기록을 열고 편집하고 변경 사항을 저장할 수도 있습니다. 자세한 내용은 [작업 레코더 리소스](../../dev-itpro/user-interface/task-recorder.md)를 참조하세요.

### <a name="connect-a-custom-help-site"></a>사용자 지정 도움말 사이트 연결

재무 및 운영 앱은 즉시 사용 가능한 형태로 거의 사용되지 않습니다. 대신 솔루션이 조직의 요구 사항에 맞게 사용자 지정되고 확장됩니다. 도움말 환경을 사용자 지정하고 확장할 수도 있습니다. 예를 들어, 제품 내 **도움말** 창에 사용자 정의 도움말을 추가할 수 있습니다.

Microsoft는 **도움말** 창에 사용자 지정 도움말을 배포하고 연결하는 데 도움이 되는 도구 키트를 제공했습니다. **도움말** 창에 연결된 사용자 정의 도움말 솔루션을 설정하는 방법에 대한 정보는 [사용자 정의 도움말 개요](../../dev-itpro/help/custom-help-overview.md)를 참조하세요.

도움말 사용자 지정을 위한 도구 및 프로세스에 대해 Microsoft와 협력하려면 [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback)에서 양식을 작성하세요.

## <a name="see-also"></a>또한, 다음을 참조하세요.

[도움말 시스템](help-overview.md)  
[사용자 정의 도움말 개요](../../dev-itpro/help/custom-help-overview.md)  
[작업 레코더 리소스](../../dev-itpro/user-interface/task-recorder.md)  
[작업 레코더로 설명서 또는 교육 만들기](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[사용자 지정 도움말 GitHub 리포지토리](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
