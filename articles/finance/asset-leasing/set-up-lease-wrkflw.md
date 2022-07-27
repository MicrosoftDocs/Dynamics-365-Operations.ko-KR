---
title: 임대 승인 워크플로 설정
description: 이 항목에서는 새 임대가 생성될 때 실행할 승인 워크플로를 설정하는 방법에 대해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2f99bb480e6ee2314852965ab9559bae2ad348fb92514d791fca127d91558348
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450337"
---
# <a name="set-up-lease-approval-workflows"></a>임대 승인 워크플로 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 새 임대가 생성될 때 실행할 승인 워크플로를 설정하는 방법에 대해 설명합니다. 워크플로우 사용 방법에 대한 자세한 내용은 [임대 승인 워크플로 사용](use-create-lease-wrkflw.md)을 참조하십시오. 

1. **자산 임대 \> 설정 \> 임대 워크플로** 로 이동합니다.
2. **임대 워크플로** 페이지에서 **새로 만들기** 를 선택합니다.
3. 나타나는 대화 상자의 **워크플로 유형** 에서 **임대 워크플로** 링크를 선택합니다.

    애플리케이션이 열립니다. 실행 후 Azure AD(Azure Active Directory)에 로그인하여 워크플로 애플리케이셔으로 리디렉션합니다.

4. **임대 워크플로 승인** 요소를 워크플로우로 끕니다.
5. **시작** 에서 **임대 워크플로 승인** 으로 노드 하나를 연결합니다. 그런 다음 **임대 워크플로 승인** 을 **종료** 에 연결합니다.
6. **임대 워크플로 승인** 을 두 번 클릭합니다.
7. **속성** 을 선택한 다음 **기본 설정** 에서 워크플로 이름을 입력하십시오.

    이 페이지에서 워크플로에 대한 추가 매개 변수를 설정할 수도 있습니다. **자동 작업** 을 설정한 경우 시스템에서 자동으로 특정 작업을 수행합니다. **알림** 탭에 지정된 경우 알림을 보낼 수 있습니다. **고급 설정** 탭에서 최종 승인자를 지정하고, 시간 제한을 설정하고, 완료해야 하는 특정 작업을 지정할 수 있습니다.

8. 워크플로 매개 변수 설정을 마쳤으면 **닫기** 를 선택합니다.
9. **1단계** 를 선택한 다음 **속성** 을 선택합니다.
10. **기본 설정** 에서 단계 이름을 입력하고 승인에 대한 제목줄을 생성한 다음 승인 지침을 지정합니다.
11. **할당** 페이지에서 할당 유형을 선택합니다.
12. 특정 사용자를 승인에 할당하려면 **사용자** 를 선택하고 임대를 승인하는 사용자를 선택한 다음 **닫기** 를 선택합니다.
13. **저장 후 닫기** 를 선택하여 워크플로를 생성합니다. 메시지가 나타나면 **확인** 을 선택합니다.
14. **워크플로 생성** 페이지에서 **닫기** 를 선택하십시오.
14. 새 워크플로를 선택한 다음 **버전** 을 선택합니다. 그런 다음 **활성화** 를 선택하여 워크플로가 활성 상태인지 확인합니다.
15. **닫기** 를 선택합니다. 새 활성 버전이 나타납니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
