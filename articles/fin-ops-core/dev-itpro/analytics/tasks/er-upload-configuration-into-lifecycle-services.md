---
title: Lifecycle Services에 구성 업로드
description: 이 항목에서는 새 전자 보고(ER) 구성을 생성하고 이를 Microsoft Dynamics Lifecycle Services(LCS)에 업로드하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b480351875c7d300db790a68d61a402218f8ee36d8247188b912762f21d035b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460964"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Lifecycle Services에 구성 업로드

[!include [banner](../../includes/banner.md)]

이 항목에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 새 [전자 보고(ER) 구성](../general-electronic-reporting.md#Configuration)을 만들고 Microsoft Dynamics Lifecycle Services(LCS)에 [프로젝트 수준 자산 라이브러리](../../lifecycle-services/asset-library.md)를 업로드하는 방법을 설명합니다.

> [!IMPORTANT]
> ER 구성을 위한 저장소 리포지토리로 LCS를 사용하는 것은 [더 이상 사용되지 않습니다](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). 자세한 내용은 [Regulatory Configuration Service(RCS) – Lifecycle Services(LCS) 스토리지 사용 중단](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)을 참조하십시오.

이 예에서는 구성을 만들어 Litware, Inc.라는 샘플 회사의 LCS에 업로드합니다. ER 구성은 회사 간에 공유되므로 모든 회사에서 이 단계를 완료할 수 있습니다. 이러한 단계를 완료하려면 RCS에서 [구성 공급자를 만들고 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md) 절차를 완료해야 합니다. LCS에 대한 액세스도 필요합니다.

1. 다음 역할 중 하나를 사용하여 애플리케이션에 로그인합니다.

    - 전자 보고 개발자
    - 시스템 관리자

2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **Litware, Inc.** 를 선택하고 **활성** 으로 표시합니다.
4. **구성** 을 선택합니다.

<a name="accessconditions"></a>
> [!NOTE]
> 현재 Dynamics 365 Finance 사용자는 ER 구성을 가져오는 데 사용되는 [자산 라이브러리](../../lifecycle-services/asset-library.md#asset-library-support)에 포함된 LCS 프로젝트의 구성원입니다.
>
> Finance에서 사용되는 도메인과 다른 도메인을 나타내는 ER 리포지토리에서 LCS 프로젝트에 액세스할 수 없습니다. 시도하면 LCS 프로젝트의 빈 목록이 표시되고 LCS의 프로젝트 수준 자산 라이브러리에서 ER 구성을 가져올 수 없습니다. ER 구성을 가져오는 데 사용되는 ER 리포지토리에서 프로젝트 수준 자산 라이브러리에 액세스하려면 현재 Finance 인스턴스가 프로비저닝된 테넌트(도메인)에 속한 사용자의 자격 증명을 사용하여 Finance에 로그인합니다.

## <a name="create-a-new-data-model-configuration"></a>새 데이터 모델 구성 만들기

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **구성** 페이지에서 **구성 만들기** 를 선택하여 드롭다운 대화 상자를 엽니다.

    이 예에서는 전자 문서에 대한 샘플 데이터 모델이 포함된 구성을 생성합니다. 이 데이터 모델 구성은 나중에 LCS에 업로드됩니다.

3. **이름** 필드에 **샘플 모델 구성** 을 입력합니다.
4. **설명** 필드에 **샘플 모델 구성** 을 입력합니다.
5. **구성 만들기** 를 선택합니다.
6. **모델 디자이너** 를 선택합니다.
7. **새로 만들기** 를 선택합니다.
8. **이름** 필드에 **진입점** 을 입력합니다.
9. **추가** 를 선택합니다.
10. **저장** 을 선택합니다.
11. 페이지를 닫습니다.
12. **상태 변경** 을 선택합니다.
13. **완료** 를 선택합니다.
14. **확인** 을 선택합니다.
15. 페이지를 닫습니다.

## <a name="register-a-new-repository"></a>새 리포지토리 등록

1. **조직 관리 \> 작업 영역 \> 전자 보고** 로 이동합니다.

2. **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택합니다.

3. **Litware, Inc.** 타일에서 **리포지토리** 를 선택합니다.

    이제 Litware, Inc. 구성 제공자의 리포지토리 목록을 열 수 있습니다.

4. **추가** 를 선택하여 드롭다운 대화 상자를 엽니다.

    이제 새 리포지토리를 추가할 수 있습니다.

5. **구성 리포지토리 입력** 필드에서 **LCS** 를 선택합니다.
6. **리포지토리 생성** 을 선택합니다.
7. **프로젝트** 필드에서 값을 입력하거나 선택합니다.

    이 예에서는 원하는 LCS 프로젝트를 선택합니다. 프로젝트에 대한 [액세스](#accessconditions) 권한이 있어야 합니다.

8. **확인** 을 선택합니다.

    새 리포지토리 항목을 완료합니다.

9. 목록에서 선택한 행을 표시합니다.

    이 예에서는 **LCS** 리포지토리 레코드를 선택합니다.

    등록된 저장소는 현재 공급자에 의해 표시됩니다. 즉, 해당 공급자가 소유한 구성만 이 저장소에 넣을 수 있으므로 선택한 LCS 프로젝트에 업로드할 수 있습니다.

10. **열기** 를 선택합니다.

    저장소를 열어 ER 구성 목록을 봅니다. 선택한 프로젝트가 아직 ER 구성 공유에 사용되지 않은 경우 목록이 비어 있습니다.

11. 페이지를 닫습니다.
12. 페이지를 닫습니다.

## <a name="upload-a-configuration-into-lcs"></a>LCS에 구성 업로드

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **샘플 모델 구성** 을 선택합니다.

    이미 완료된 생성된 구성을 선택해야 합니다.

3. 목록에서 원하는 기록을 찾아 선택합니다.

    이 예에서는 상태가 **완료됨** 인 선택한 구성의 버전을 선택합니다.

4. **상태 변경** 을 선택합니다.
5. **공유** 를 선택합니다.

    구성이 LCS에 게시되면 구성 상태가 **완료됨** 에서 **공유됨** 으로 변경됩니다.

6. **확인** 을 선택합니다.
7. 목록에서 원하는 기록을 찾아 선택합니다.

    이 예에서는 상태가 **공유됨** 인 선택한 구성 버전을 선택합니다.

    선택한 버전의 상태가 **완료됨** 에서 **공유됨** 으로 변경되었습니다.

8. 페이지를 닫습니다.
9. **리포지토리** 를 선택합니다.

    이제 Litware, Inc. 구성 제공자의 리포지토리 목록을 열 수 있습니다.

10. **열기** 를 선택합니다.

    이 예시에서는 **LCS** 리포지토리를 선택하고 엽니다.

    선택한 구성이 선택한 LCS 프로젝트의 자산으로 표시됩니다.

11. <https://lcs.dynamics.com>으로 이동하여 LCS를 엽니다.
12. 이전에 리포지토리 등록에 사용한 프로젝트를 엽니다.
13. 프로젝트의 자산 라이브러리를 엽니다.
14. **GER 구성** 자산 유형을 선택합니다.

    업로드한 ER 구성이 나열되어야 합니다.

    공급자가 이 LCS 프로젝트에 액세스할 수 있는 경우 업로드된 LCS 구성을 다른 인스턴스로 가져올 수 있습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
