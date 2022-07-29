---
title: 클라이언트 FAQ
description: 이 문서에서는 재무 및 운영 클라이언트에 대해 자주 묻는 질문에 대한 답변을 제공합니다.
author: jasongre
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e64fb2453f17760b17ca2a7d3f593ac34cde0cc9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460691"
---
# <a name="client-faq"></a>클라이언트 FAQ

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 문서에서는 재무 및 운영 클라이언트에 대해 자주 묻는 질문에 대한 답변을 제공합니다.

## <a name="why-arent-symbols-loaded"></a>기호가 로드되지 않는 이유는 무엇입니까?

브라우저의 보안 설정으로 인해 기호가 올바르게 로드되지 않을 수 있습니다. 이 문제를 해결하려면 다음 단계를 시도하십시오.

- Internet Explorer에서 이 문제가 발생하면 **도구** 를 클릭한 다음 **인터넷 옵션** 을 클릭합니다. 인터넷 옵션 대화 상자의 **개인 정보** 탭에서 **사용자 지정 수준** 을 클릭하고 **글꼴 다운로드** 옵션이 선택되어 있는지 확인합니다.
- 그렇지 않으면 앱 사이트를 신뢰할 수 있는 사이트 목록에 추가해야 할 수 있습니다.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Dynamics AX 2012의 리본이 그리워요. 작업 창 탭을 항상 열어 둘 수 있습니까?

이 기능을 곧 구현할 계획입니다. 그러면 사용자는 작업 창의 탭을 항상 열어 두도록 선택할 수 있습니다. 그렇지 않으면 탭이 사용되지 않을 때 축소되어 페이지에 더 많은 화면 공간을 확보할 수 있습니다.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>마우스 오른쪽 버튼을 클릭할 때 때때로 다른 바로 가기 메뉴가 표시되는 이유는 무엇입니까?

편집 가능한 필드를 마우스 오른쪽 버튼으로 클릭하면(또는 텍스트가 선택된 경우) 브라우저의 바로 가기 메뉴가 표시됩니다. 이 메뉴를 사용하면 **잘라내기**, **복사** 및 **붙여넣기** 명령에 액세스할 수 있습니다. 보안상의 이유로 브라우저에서 시스템 클립보드에 프로그래밍 방식으로 액세스할 수 없기 때문에 이러한 명령을 바로 가기 메뉴에 포함할 수 없습니다.

필드 레이블이나 읽기 전용 컨트롤의 값을 마우스 오른쪽 버튼으로 클릭하면 바로 가기 메뉴가 표시됩니다.

키보드 접근을 보다 쉽게 하기 위해 단축키 메뉴를 여는 단축키를 차후에 구현할 예정입니다.

## <a name="where-is-the-view-details-functionality"></a>세부정보 보기 함수은 어디에 있습니까?

**세부정보 보기** 옵션은 다음 두 가지 방법으로 사용할 수 있습니다.

- 컨트롤에 **세부 정보 보기** 기능이 있고 컨트롤에 값이 있는 경우 해당 값은 하이퍼링크로 표시됩니다. 하이퍼링크를 클릭하여 추가 세부 정보가 포함된 페이지를 열 수 있습니다.
- **세부 정보 보기** 는 바로 가기 메뉴의 옵션이기도 합니다. 마우스 오른쪽 버튼을 클릭할 때 바로 가기 메뉴가 표시되는 경우에 대한 자세한 내용은 이전 섹션을 참조하십시오.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]