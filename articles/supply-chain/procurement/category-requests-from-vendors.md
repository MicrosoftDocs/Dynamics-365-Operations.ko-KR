---
title: 공급업체의 범주 요청
description: 이 항목에서는 공급업체가 계정에 대한 조달 범주를 요청할 수 있는 방법에 대해 설명합니다. 또한 조달 에이전트가 완료하는 승인 프로세스에 대해서도 설명합니다.
author: Henrikan
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5d06f05ca27ed8fe58a9a24fcde8c0082662b866
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449956"
---
# <a name="category-requests-from-vendors"></a>공급업체의 범주 요청

[!include [banner](../includes/banner.md)]

범주 요청 프로세스를 통해 공급업체는 새 조달 범주가 계정과 연결되도록 요청할 수 있습니다. 그런 다음 이러한 조달 범주는 관련 조달 및 소싱 프로세스에서 사용할 수 있습니다. (자세한 내용은 [조달 범주 개요](procurement-catalogs.md)를 참조하세요.)

범주 요청은 **공급업체 정보** 작업 영역에서 공급업체가 시작합니다. 그런 다음 검토 및 승인을 위해 기관에 제출됩니다. 승인된 범주는 공급업체 계정의 조달 범주 목록에 추가됩니다.

## <a name="turn-the-category-requests-from-vendors-feature-on-or-off"></a>공급업체의 범주 요청 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *공급업체가 공급업체 협업을 통해 조달 범주를 신청할 수 있도록 허용* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

이 기능이 켜져 있는 경우에도 공급업체 계정에 조달 범주를 수동으로 추가할 수 있습니다. 자세한 내용은 [특정 조달 범주에 대한 공급업체 승인](tasks/approve-vendors-specific-procurement-categories.md)을 참조하세요.

## <a name="vendor-collaboration-requirements"></a>공급업체 협업 요구 사항

공급업체가 범주 요청과 상호 작용하려면 먼저 공급업체 협업을 위해 설정해야 합니다.

공급업체에는 하나 이상의 공급업체 협업 사용자가 있어야 합니다. *공급업체 관리자(외부)* 보안 역할이 있는 공급업체 사용자만 범주 요청을 생성하고 제출할 수 있습니다.

자세한 내용은 [공급업체 협업 설정 및 유지 관리](set-up-maintain-vendor-collaboration.md)를 참조하세요.

## <a name="set-up-the-vendor-category-request-workflow"></a>공급업체 범주 요청 워크플로 설정

*공급업체 범주 요청* 워크플로는 조달 및 소싱 워크플로에서 설정해야 합니다. 공급업체는 귀하가 검토하고 승인할 수 있는 새 범주 요청을 제출합니다. 요청된 조달 범주는 범주 요청이 승인된 후 공급업체 계정에 추가됩니다.

다음 예는 단일 승인자가 있는 간단한 *공급업체 범주 요청* 워크플로를 설정하는 방법을 보여줍니다. 기관에 적합한 워크플로 설정을 결정하려면 내부 프로세스를 검토해야 합니다.

1. **조달 및 소싱 \> 설정 \> 조달 및 소싱 워크플로** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 대화 상자에서 **공급업체 범주 요청 워크플로** 를 선택하여 워크플로 편집기를 엽니다.
1. 워크플로 편집기에 로그인합니다.
1. 작업 창에서 **속성** 을 선택합니다.
1. 워크플로의 **속성** 페이지에 있는 **제출 지침** 필드에 지침 텍스트를 입력합니다. 벤더가 범주 요청을 제출할 때 지침을 볼 수 있습니다.
1. **속성** 페이지를 닫습니다.
1. **새 범주 요청 승인** 워크플로 요소를 캔버스로 드래그합니다.
1. **시작** 워크플로 요소의 링크를 **새 범주 요청 승인** 워크플로 요소로 드래그합니다.
1. **새 범주 요청 승인** 워크플로 요소의 링크를 **끝** 워크플로 요소로 드래그합니다.
1. **새 범주 요청** 워크플로 요소를 두 번 탭(또는 두 번 클릭)합니다.
1. **1단계** 워크플로 요소를 길게 선택하고(또는 오른쪽 버튼으로 클릭) **속성** 을 선택합니다.
1. 워크플로 요소의 **속성** 페이지에 있는 **작업 항목 제목** 필드에 제목 텍스트를 입력합니다. 이 텍스트는 **나에게 할당된 작업 항목** 페이지의 **제목** 필드의 값이 표시됩니다.
1. **작업 항목 지침** 필드에 지침 텍스트를 입력합니다. 승인자가 범주 요청의 작업 창에서 **워크플로** 를 선택하면 지침이 표시됩니다.
1. 왼쪽 창에서 **할당** 을 선택합니다.
1. **할당 유형** 탭에서 **이 워크플로 요소에 사용자 할당** 을 *사용자* 로 설정합니다.
1. **사용자** 탭의 **사용 가능한 사용자** 목록에서 승인자를 선택합니다. 예를 들어 조달 부서의 사용자를 선택합니다.
1. 오른쪽 화살표 버튼(**\>**)을 선택하여 승인자를 **선택된 사용자** 목록으로 이동합니다.
1. **속성** 페이지를 닫습니다.
1. **저장 및 닫기** 를 선택합니다.
1. **버전 참고 사항** 필드에 워크플로에 대한 메모를 입력합니다.
1. **확인** 을 선택하여 워크플로를 저장합니다.
1. 워크플로 테스트를 시작할 준비가 되었으면 **새 버전 활성화** 를 선택합니다. 그렇지 않으면 **새 버전을 활성화하지 않음** 을 선택합니다.
1. **확인** 을 선택하여 워크플로 설정을 완료합니다.

> [!TIP]
> 대행사에서 범주 요청 승인을 요구하지 않는 경우 자동 승인을 위한 워크플로를 구성해야 합니다.

워크플로를 설정하는 방법에 대한 자세한 내용은 [워크플로 시스템 개요](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md)를 참조하세요.

## <a name="create-and-submit-a-category-request"></a>범주 요청 생성 및 제출

이 섹션에서는 공급업체가 **공급업체 정보** 작업 영역을 사용하여 범주 요청을 만들고, 편집하고, 보고, 제출하는 방법을 설명합니다.

### <a name="start-a-new-request"></a>새 요청 시작

새 범주 요청을 시작하려면 다음 단계를 따르세요.

1. **공급업체 정보** 작업 영역에서 **범주 요청** 타일을 선택합니다.
1. **범주 요청** 페이지의 작업 창에서 **새 범주 요청** 을 선택합니다.
1. **새 범주 요청** 대화 상자에서 트리를 탐색하거나 목록 상단의 필터를 사용하여 신청하려는 범주를 찾습니다. 각 관련 범주의 확인란을 선택합니다.

    다음 요점을 확인하세요.

    - 현재 공급업체 계정에서 활성화된 범주는 선택된 것으로 표시되며 제거할 수 없습니다.
    - 단일 범주 요청에서 여러 조달 범주를 요청할 수 있습니다.

1. **확인** 을 선택하여 초안 요청을 생성합니다.

    이제 새 초안 요청이 **범주 요청** 페이지에 표시됩니다.

1. 새 초안 요청을 열어 필요에 따라 검토하고 편집합니다.

    - 현재 요청에 포함된 범주 목록을 보려면 **요청된 범주** 빠른 탭을 선택합니다.
    - 활성 범주를 보려면 페이지 오른쪽의 **활성 범주** 팩트 상자를 엽니다.
    - 요청에 범주를 추가하려면 **요청된 범주** 빠른 탭의 도구 모음에서 **추가** 를 선택합니다.
    - 요청에서 범주를 제거하려면 **요청된 범주** 빠른 탭을 선택한 다음 도구 모음에서 **제거** 를 선택합니다.
    - 요청에 문서를 첨부하려면 작업 창에서 **첨부 파일** 을 선택합니다. 첨부 문서는 승인자가 범주 요청을 검토할 때 사용할 수 있습니다.
    - 요청에서 첨부된 문서를 제거하려면 작업 창에서 **첨부 파일** 을 선택합니다. 제거할 문서를 선택한 다음 작업 창에서 **삭제** 를 선택합니다.

1. 요청을 제출할 준비가 되었다면 작업 창에서 **제출** 을 선택합니다. 그렇지 않으면 페이지를 닫고 이 절차의 나머지 단계를 건너뜁니다. 그런 다음 나중에 요청으로 돌아갈 수 있습니다.
1. 표시되는 제출 지침을 읽고 **제출** 을 선택합니다.
1. **댓글** 상자에 필요한 추가 정보를 입력합니다. 그런 다음 **제출** 을 선택하여 요청을 완료합니다.

### <a name="edit-a-draft-or-recalled-request"></a>초안 또는 회수 요청 수정

초안 또는 회수된 범주 요청을 편집하려면 다음 단계를 따르세요.

1. **공급업체 정보** 작업 영역에서 **범주 요청** 타일을 선택합니다.
1. 초안 또는 회수 요청을 선택하여 엽니다.
1. 필요에 따라 요청을 편집한 다음 이전 절차에서 설명한 대로 요청을 닫거나 제출합니다.

### <a name="submit-a-draft-or-recalled-request"></a>초안 또는 회수 요청 제출

초안 또는 회수된 범주 요청을 제출하려면 다음 단계를 따르세요.

1. **공급업체 정보** 작업 영역에서 **범주 요청** 타일을 선택합니다.
1. 제출할 초안 또는 회수 요청을 선택합니다.
1. 작업 창에서 **제출** 을 선택합니다.
1. 표시되는 제출 지침을 읽고 **제출** 을 선택합니다.
1. **댓글** 상자에 필요한 추가 정보를 입력합니다. 그런 다음 **제출** 을 선택하여 요청을 완료합니다.

    범주 요청의 상태가 다음 값 중 하나로 변경됩니다.

    - _검토 보류 중_ – 요청이 워크플로에 있습니다.
    - _승인 대기 중_ – 승인이 필요합니다.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>아직 승인되지 않은 제출된 요청 회수

제출되었지만 아직 승인되지 않은 범주 요청을 회수하려면 다음 단계를 따르세요.

1. **공급업체 정보** 작업 영역에서 **범주 요청** 타일을 선택합니다.
1. 회수하려는 보류 중인 요청을 선택합니다.
1. 작업 창에서 **회수** 를 선택합니다.
1. **댓글 입력** 상자에 필요한 추가 정보를 입력합니다. 그런 다음 **제출** 을 선택하여 요청을 완료합니다.

    범주 요청의 상태가 _취소됨_ 으로 변경됩니다. 요청은 삭제하거나 다시 제출할 때까지 이 상태로 유지됩니다.

### <a name="delete-a-draft-or-recalled-request"></a>초안 또는 회수 요청 삭제

초안 또는 회수된 범주 요청을 삭제하려면 다음 단계를 따르세요.

1. **공급업체 정보** 작업 영역에서 **범주 요청** 타일을 선택합니다.
1. 삭제할 초안 또는 회수 요청을 선택합니다.
1. 작업 창에서 **삭제** 를 선택합니다.
1. **예** 를 선택하여 삭제를 확인합니다.

### <a name="view-completed-requests"></a>완료된 요청 보기

완료된 요청을 보려면 **공급업체 정보** 작업 영역을 열고 **범주 요청** 타일을 선택합니다. 완료된 범주 요청은 다음 상태 중 하나가 됩니다.

- _승인됨_ – 요청이 승인되었습니다. 새로 추가된 범주를 보려면 **공급업체 정보** 작업 영역으로 이동하고 왼쪽 창의 **추가 정보** 드롭다운 목록을 연 다음 **범주** 를 선택합니다.
- _거부됨_ – 요청이 거부되었습니다. 필요에 따라 새 범주 요청을 생성할 수 있습니다.

## <a name="review-category-requests"></a>범주 요청 검토

이 섹션에서는 벤더가 제출한 범주 요청을 승인, 거부 및 위임하는 방법과 완료된 요청을 보는 방법에 대해 설명합니다. 이러한 워크플로 작업은 전체 범주 요청에 대한 것입니다.

### <a name="view-category-requests"></a>범주 요청 보기

범주 요청을 보려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 협업 요청 \> 범주 요청** 으로 이동합니다.

    **범주 요청** 페이지가 나타납니다. 기본 페이지 보기에는 상태가 *보류 중인 작업* 인 범주 요청이 표시됩니다.

1. 모든 요청을 보려면 **요청 표시** 필드에서 *모두* 를 선택합니다.
1. 요청을 열어 필요에 따라 검토하고 편집합니다.

    - 현재 요청에 포함된 범주 목록을 보려면 **요청된 범주** 빠른 탭을 선택합니다.
    - 활성 범주를 보려면 페이지 오른쪽의 **활성 범주** 팩트 상자를 엽니다.
    - 서류를 제출한 경우 작업 창의 **첨부 파일**(종이 클립) 버튼이 첨부 문서의 개수를 보여줍니다. 첨부 문서를 보려면 **첨부 파일** 단추를 선택합니다. 그런 다음 볼 문서를 선택하고 **열기** 를 선택해 봅니다.
    - 요청에 문서를 첨부하려면 작업 창에서 **첨부 파일** 을 선택합니다. 첨부 문서는 승인자가 범주 요청을 검토할 때 사용할 수 있습니다.
    - 요청에서 첨부된 문서를 제거하려면 작업 창에서 **첨부 파일** 을 선택합니다. 제거할 문서를 선택한 다음 작업 창에서 **삭제** 를 선택합니다.
    - 워크플로 기록을 보려면 작업 창에서 **워크플로** 를 선택합니다. 워크플로 옵션에서 **더 보기** 다음 **워크플로 기록** 을 선택합니다. **워크플로 기록** 페이지가 나타납니다.

### <a name="approve-a-pending-category-request"></a>보류 중인 범주 요청 승인

보류 중인 범주 요청을 승인하려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 협업 요청 \> 범주 요청** 으로 이동합니다.
1. 승인할 보류 중인 요청을 선택합니다.
1. 범주 요청을 검토합니다.
1. 옵션: **일반** 빠른 탭의 **이유 코드** 필드에서 이유 코드를 선택합니다. 그런 다음 **이유 코멘트** 필드에 이유 코드에 대한 설명을 입력합니다.
1. 작업 창에서 **워크플로** 를 선택합니다.
1. 워크플로 옵션에서 **승인** 을 선택합니다.
1. **댓글** 필드에 필요한 추가 정보를 입력합니다. 그런 다음 **승인** 을 선택하여 요청을 완료합니다.

    범주 요청 상태가 _승인됨_ 으로 변경되며, 조달 범주가 공급업체 계정에 추가됩니다.

### <a name="reject-a-pending-category-request"></a>보류 중인 범주 요청 거부

보류 중인 범주 요청을 거부하려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 협업 요청 \> 범주 요청** 으로 이동합니다.
1. 거부할 보류 중인 요청을 선택합니다.
1. 범주 요청을 검토합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **일반** 빠른 탭의 **이유 코드** 필드에서 이유 코드를 선택합니다. 그런 다음 **이유 코멘트** 필드에 이유 코드에 대한 설명을 입력합니다.
1. 작업 창에서 **저장** 을 선택합니다.
1. 작업 창에서 **워크플로** 를 선택합니다.
1. 워크플로 옵션에서 **더 보기** 다음 **거부** 를 선택합니다.
1. **댓글** 필드에 필요한 추가 정보를 입력합니다. 그런 다음 **거부** 를 선택하여 요청을 완료합니다.

    범주 요청의 상태가 _거부됨_ 으로 변경됩니다. 이 시점에서 공급업체는 필요에 따라 새 범주 요청을 생성할 수 있습니다.

### <a name="delegate-a-pending-category-request"></a>보류 중인 범주 요청 위임

보류 중인 범주 요청을 다른 사용자에게 위임하려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 협업 요청 \> 범주 요청** 으로 이동합니다.
1. 승인하려는 보류 중인 요청을 선택합니다.
1. 작업 창에서 **워크플로** 를 선택합니다.
1. 워크플로 옵션에서 **더 보기** 다음 **위임** 을 선택합니다.
1. **사용자** 필드에서 검토를 위해 범주 요청을 할당할 사용자를 선택합니다.
1. **댓글** 필드에 필요한 추가 정보를 입력합니다.
1. **대리자** 를 선택하여 위임을 완료합니다. 선택한 사용자는 이제 범주 요청을 검토할 수 있습니다.

### <a name="view-procurement-categories-for-a-vendor"></a>공급업체의 조달 범주 보기

범주 요청이 승인된 후 공급업체의 조달 범주를 보려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 검색** 으로 이동합니다.
1. **모든 공급업체** 페이지에서 조달 범주를 보려는 공급업체를 선택합니다.
1. 작업 창에서 **일반** 탭을 열고 **설정** 그룹에서 **범주** 를 선택합니다.

    **범주** 페이지가 나타납니다. **조달** 빠른 탭은 범주 요청을 통해 추가된 조달 범주를 보여줍니다.

1. **조달** 빠른 탭에서 필요한 경우 변경할 수 있습니다. 예를 들어 **공급업체 범주 상태** 필드를 _기본_ 으로 설정할 수 있습니다.