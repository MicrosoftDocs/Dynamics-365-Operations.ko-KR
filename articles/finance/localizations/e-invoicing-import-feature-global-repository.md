---
title: 글로벌 리포지토리에서 기능 가져오기
description: 이 항목에서는 전역 리포지토리에서 전역화 기능을 가져오는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/11/2022
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
ms.openlocfilehash: ff3019986d089a286f7aef94346398b3d328ad54
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451684"
---
# <a name="import-features-from-the-global-repository"></a>글로벌 리포지토리에서 기능 가져오기

[!include [banner](../includes/banner.md)]

글로벌 리포지토리에는 구성 공급자와 공유되는 전자 송장 발행 기능이 포함되어 있습니다. Microsoft에서 제공하는 모든 전자 송장 발행 기능은 모든 회사와 공유됩니다. Microsoft가 글로벌 리포지토리에 릴리스하고 게시하는 모든 전자 송장 발행 기능에 자동으로 액세스할 수 있습니다.

구성 공급자와 공유되는 전자 송장 발행 기능을 사용하기 시작하려면 글로벌 리포지토리에서 RCS(Regulatory Configuration Service) 인스턴스로 이 기능을 가져옵니다. 그런 다음 전자 보고(ER) 구성 및 처리 파이프라인과 같은 기능의 세부 정보를 검토합니다.

## <a name="import-a-feature-from-the-global-repository"></a>글로벌 리포지토리에서 기능 가져오기

1. RCS 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 청구서 발행** 타일을 선택합니다.
3. **가져오기** 를 선택하여 **글로벌 리포지토리에서 기능 가져오기** 조회를 엽니다.
4. 특정 구성 공급자가 사용할 수 있는 글로벌 리포지토리의 전자 송장 발행 기능을 찾아보려면 **동기화** 를 선택하여 조직의 RCS 인스턴스를 동기화합니다. 동기화가 완료되면 사용 가능한 전자 송장 발행 기능의 목록이 글로벌 리포지토리에서 업데이트됩니다. 이 업데이트는 몇 분 정도 걸릴 수 있습니다.
5. 가져올 기능을 선택한 다음 **가져오기** 를 선택합니다.

가져온 전자 송장 발행 기능을 보려면 올바른 구성 제공자가 선택되었는지 확인합니다. 기본적으로 활성 구성 공급자가 만든 기능은 자동으로 필터링됩니다. 필터를 조정하여 Microsoft 구성 공급자와 같은 다른 공급자가 만든 기능을 볼 수 있습니다.

이제 가져온 기능으로 작업할 수 있습니다. 가져온 기능을 템플릿으로 사용하여 세부 정보를 검토하고 새 기능을 생성할 수 있습니다.

> [!NOTE]
> 현재 활성 상태인 구성 공급자가 만든 경우에만 기능을 수정할 수 있습니다. 원본 기능을 바탕으로 새 기능을 만들 수 있습니다. 그런 다음 필요한 변경을 하거나 매개 변수를 설정할 수 있습니다.

Microsoft 또는 귀사와 세계화 기능을 공유하는 다른 회사가 가져온 기능을 업데이트할 경우 **세계화 기능** 의 작업 영역의 **관련 설정** 섹션에서 **기능 업데이트 확인** 을 선택하여 업데이트 버전을 확인할 수 있습니다.

템플릿으로 사용하는 기능에 대한 업데이트가 있는 경우 글로벌 리포지토리에 게시된 기능 목록을 동기화한 후 새 버전을 가져올 수 있습니다.
