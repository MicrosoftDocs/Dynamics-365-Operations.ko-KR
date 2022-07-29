---
title: Lifecycle Services에서 전자 보고 구성 다운로드
description: 이번에는 Microsoft Dynamics LCS(Lifecycle Services)에서 전자 보고(ER) 구성을 다운로드하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ea603d01d05e98ac69d5a0d12802b5f23ee34793bf4c9b4f885f0e4303f77d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460676"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Lifecycle Services에서 전자 보고 구성 다운로드

[!include [banner](../includes/banner.md)]

이번에는 Microsoft Dynamics LCS(Lifecycle Services)의 [공유 자산 라이브러리](../lifecycle-services/asset-library.md)에서 최신 버전의 [전자 보고(ER) 구성](general-electronic-reporting.md#Configuration)을 다운로드하는 방법에 대해 설명합니다.

> [!IMPORTANT]
> ER 구성을 위한 저장소 리포지토리로 LCS를 사용하는 것은 더 이상 [사용되지 않습니다](../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). 자세한 내용은 [Regulatory Configuration Service(RCS) – Lifecycle Services(LCS) 스토리지 사용 중단](../../../finance/localizations/rcs-lcs-repo-dep-faq.md)을 참조하십시오.

1. 다음 역할 중 하나를 사용하여 애플리케이션에 로그인합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

2. **조직 관리** &gt; **작업 영역** &gt; **전자 보고** 로 이동합니다.
3. **구성 공급자** 섹션에서 **Microsoft** 타일을 선택합니다.
4. **Microsoft** 타일에서 **리포지토리** 를 선택합니다.

    [![현지화 구성 페이지의 Microsoft 타일.](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)

5. **구성 리포지토리** 페이지의 그리드에서 **LCS** 유형의 기존 리포지토리를 선택합니다. 이 리포지토리가 그리드에 표시되지 않으면 다음 단계를 따르십시오.

    1. **추가** 를 선택하여 리포지토리를 추가합니다.
    2. 리포지토리 유형으로 **LCS** 를 선택합니다.
    3. **리포지토리 만들기** 를 선택합니다.
    4. 인증에 대한 메시지가 표시되면 화면의 지시를 따릅니다.
    5. 리포지토리의 이름과 설명을 입력합니다.
    6. **확인** 을 선택하여 새 리포지토리 항목을 확인합니다.
    7. 그리드에서 **LCS** 유형의 새 리포지토리를 선택합니다.

6. **열기** 를 선택하여 선택한 리포지토리에 대한 ER 구성 목록을 봅니다.

    [![구성 리포지토리 페이지.](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)

    > [!TIP]
    > LCS의 공유 자산 라이브러리에서 구성을 다운로드하기 위해 LCS 리포지토리에 액세스하는 데 문제가 있는 경우 대신 [글로벌 리포지토리](er-download-configurations-global-repo.md)에서 구성을 다운로드할 수 있습니다.

7. 왼쪽 창의 구성 트리에서 필요한 ER 구성을 선택합니다.
8. **버전** FastTab에서 선택한 ER 구성의 필수 버전을 선택합니다.
9. **가져오기** 를 선택하여 선택한 버전을 LCS에서 현재 인스턴스로 다운로드합니다.

    > [!NOTE]
    > 현재 인스턴스에 이미 있는 ER 구성 버전에는 **가져오기** 버튼을 사용할 수 없습니다.

    [![구성 리포지토리 페이지입니다.](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)

> [!NOTE]
> ER 설정에 따라 구성을 가져온 후 유효성을 검사합니다. 발견된 불일치 문제에 대해 알림을 받을 수 있습니다. 가져온 구성 버전을 사용하려면 먼저 이러한 문제를 해결해야 합니다. 자세한 내용은 이 항목에 대한 관련 항목 목록을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[구성 서비스의 글로벌 저장소에서 ER 구성 다운로드](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
