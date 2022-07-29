---
title: 여러 워크시트가 있는 데이터 템플릿
description: 이 항목에서는 Excel 데이터 엔터티 템플릿을 사용하여 재무 및 운영으로 데이터를 가져오는 방법에 대해 설명합니다.
author: peakerbl
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: cf3c423bdf06685a3c4025551927123773ae818a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460896"
---
# <a name="data-templates-with-multiple-worksheets"></a>여러 워크시트가 있는 데이터 템플릿

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

응용 프로그램의 데이터 관리는 데이터 엔터이에 대해 Microsoft Excel 기반 템플릿을 지원합니다. 이러한 템플릿에는 하나 이상의 워크시트가 포함될 수 있습니다. 여러 워크시트가 있는 템플릿은 단일 파일에서 데이터를 관리하고 여러 데이터 엔터티로 가져오는 것이 편리할 때 자주 사용됩니다. 사이트와 창고를 예로 들 수 있습니다.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>파일을 한 번 업로드하고 모든 엔터티에 매핑
**사이트** 및 **창고** 라는 워크시트가 있는 Excel 파일이 하나 있는 예를 들어 보겠습니다. 데이터 가져오기 프로젝트를 설정하려면 첫 번째 데이터 엔터티인 **사이트** 를 추가한 다음 파일을 업로드합니다. 이 엔터티에 사용할 워크시트로 **사이트** 를 사용할 수 있게 됩니다.

**파일 추가** 양식을 나가지 않고 두 번째 엔터티 **창고** 를 추가하는 경우 워크시트 조회를 통해 파일을 다시 업로드하지 않고 **창고** 워크시트를 선택할 수 있습니다. 새 파일을 업로드하는 유일한 이유는 **창고** 데이터가 다른 파일에 있었기 때문입니다.

![여러 워크시트.](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>엔터티 매핑에 워크시트 수정

가져오기 작업의 데이터 엔터티에 대한 워크시트 매핑은 그리드에서 수정할 수 있습니다. 그리드의 **워크시트** 열은 매핑된 파일의 워크시트를 보여줍니다. 드롭다운 메뉴에서 다른 워크시트를 선택할 수 있습니다. 선택한 워크시트가 데이터 프로젝트의 엔터티에 이미 매핑되어 있는 경우 변경 사항을 확인하라는 메시지가 표시됩니다. 그리드의 모든 매핑을 수정하는 것이 좋습니다.

![워크시트 매핑을 업데이트합니다.](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>새 파일로 다시 매핑

데이터 프로젝트의 기존 엔터티에 대해 동일한 파일의 새 버전이나 완전히 새로운 파일을 업로드해야 하는 경우에는 **파일 추가** 환경을 사용하고 엔터티를 처음 추가하는 것처럼 다시 추가합니다. 계속 진행하기 전에 시스템에서 데이터 프로젝트의 기존 엔터티를 덮어쓸 것인지 확인합니다. 다시 추가되지 않은(또는 덮어쓰지 않은) 엔터티는 이전 파일의 이전 매핑을 계속 유지합니다.

## <a name="upload-a-file-using-run-project"></a>프로젝트 실행을 사용하여 파일 업로드

**프로젝트 실행** 옵션을 사용하여 프로젝트 가져오기를 실행하는 동안 Excel 파일을 업로드할 수 있습니다. 데이터 프로젝트의 데이터 엔터티에 대한 기존 매핑과 동일한 워크시트가 있는 파일만 업로드하도록 주의해야 합니다. 새로 업로드된 파일에서 워크시트를 찾을 수 없는 경우 시스템은 오류를 표시하고 가져오기를 중지합니다. 엔터티에 대해 워크시트에 대한 매핑을 변경해야 하는 경우 데이터 프로젝트의 매핑을 먼저 데이터 프로젝트 내에서 업데이트한 다음 **프로젝트 실행** 경험을 사용해야 합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
