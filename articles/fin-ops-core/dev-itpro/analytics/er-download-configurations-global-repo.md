---
title: 구성 서비스의 글로벌 저장소에서 ER 구성 다운로드
description: 이번에는 구성 서비스의 글로벌 리포지토리에서 전자 보고(ER) 구성을 다운로드하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 32eb5206fadefbd024f2dd2af888d166c81b950f
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460948"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a>구성 서비스의 글로벌 저장소에서 ER 구성 다운로드

[!include [banner](../includes/banner.md)]

이번에는 구성 서비스의 글로벌 리포지토리에서 [전자 보고(ER) 구성](general-electronic-reporting.md#Configuration)을 다운로드하는 방법에 대해 설명합니다. 자세한 내용은 [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, 구성 서비스](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration)를 참조하십시오.

## <a name="open-configurations-repository"></a>구성 저장소 열기

1. 다음 역할 중 하나를 사용하여 Dynamics 365 Finance 애플리케이션에 로그인합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

2. **조직 관리 > 작업 영역 > 전자 보고** 로 이동합니다.
3. **구성 공급자** 섹션에서 **Microsoft** 타일을 선택합니다.
3. **Microsoft** 타일에서 **리포지토리** 를 선택합니다.

    ![전자 보고 작업 공간.](./media/er-download-configurations-global-repo-er-workspace.png)

4. **구성 리포지토리** 페이지의 그리드에서 **글로벌** 유형의 기존 리포지토리를 선택합니다. 이 리포지토리가 그리드에 표시되지 않으면 다음 단계를 따르십시오.

    1. **추가** 를 선택하여 새 리포지토리를 추가합니다.
    2. 리포지토리 유형으로 **전역** 을 선택한 다음 **리포지토리 만들기** 를 선택합니다.
    3. 메시지가 표시되면 인증 지침을 따릅니다.
    4. 리포지토리의 이름과 설명을 입력한 다음 **확인** 을 선택하여 새 리포지토리 항목을 확인합니다.
    5. 그리드에서 **글로벌** 유형의 새 리포지토리를 선택합니다.

5. **열기** 를 선택하여 선택한 리포지토리에 대한 ER 구성 목록을 봅니다.

    ![구성 리포지토리 페이지.](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a>단일 구성 가져오기

1. **구성 리포지토리** 페이지의 구성 트리에서 원하는 ER 구성을 선택합니다.
2. **버전** FastTab에서 선택한 ER 구성의 필수 버전을 선택합니다.
3. 글로벌 리포지토리에서 현재 Finance 인스턴스로 선택한 버전을 다운로드하려면 **가져오기** 를 선택합니다.

    > [!NOTE]
    > 현재 Finance 인스턴스에 이미 있는 ER 구성 버전에는 **가져오기** 버튼을 사용할 수 없습니다.

    ![구성 저장소 페이지, 구성 FastTab.](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a>필터링된 구성 가져오기

1. **구성 리포지토리** 페이지의 구성 트리에서 FastTab **필터** 를 확장합니다.
2. **태그** 그리드에서 필요한 태그를 추가합니다.
3. **국가/지역 적용 가능성** 필드에서 적절한 국가/지역 코드를 선택한 다음 **필터 적용** 을 선택합니다.

    > [!NOTE]
    > **구성** FastTab은 지정된 선택 조건을 충족하는 모든 구성을 표시합니다.

4. **구성** FastTab에서 **가져오기** 를 선택하여 글로벌 리포지토리에서 현재 인스턴스로 필터링된 구성을 다운로드합니다.
5. **구성** FastTab에서 **필터 재설정** 을 선택하여 지정된 선택 조건을 정리합니다.

    ![구성 리포지토리 페이지, 버전 FastTab, 가져오기 버튼.](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> ER 설정에 따라 구성을 가져온 후 유효성을 검사합니다. 발견된 불일치 문제에 대해 알림을 받을 수 있습니다. 가져온 구성 버전을 사용하려면 먼저 문제를 해결해야 합니다. 자세한 내용은 이 항목에 대한 관련 리소스 목록을 참조하십시오.

> [!NOTE]
> ER 구성은 다른 구성에 종속되도록 구성할 수 있습니다. 따라서 선택한 구성과 함께 다른 구성을 자동으로 가져올 수 있습니다. 구성 종속성에 대한 자세한 내용은 [다른 구성 요소에 대한 ER 구성의 종속성 정의](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)를 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
