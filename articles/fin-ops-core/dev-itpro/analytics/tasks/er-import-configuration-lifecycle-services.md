---
title: Lifecycle Services에서 구성 가져오기
description: 이번에는 Microsoft Dynamics LCS(Lifecycle Services)에서 새 버전의 전자 보고(ER) 구성을 가져오는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05a8ad127df177c54e67ff1f2ddcd8b3a3f51ea12b6e11d087105bd74b6bdb3f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460912"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Lifecycle Services에서 구성 가져오기

[!include [banner](../../includes/banner.md)]

이번에는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 Microsoft Dynamics LCS(Lifecycle Services)의 [프로젝트 수준 자산 라이브러리](../../lifecycle-services/asset-library.md)에서 새 버전의 [전자 보고(ER) 구성](../general-electronic-reporting.md#Configuration)을 가져올 수 있는 방법에 대해 설명합니다.

> [!IMPORTANT]
> ER 구성을 위한 저장소 리포지토리로 LCS를 사용하는 것은 [더 이상 사용되지 않습니다](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). 자세한 내용은 [Regulatory Configuration Service(RCS) – Lifecycle Services(LCS) 스토리지 사용 중단](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md)을 참조하십시오.

이 예시에서는 원하는 버전의 ER 구성을 선택하고 Litware, Inc.라는 샘플 회사에 대해 가져옵니다. ER 구성은 회사 간에 공유되므로 모든 회사에서 이 단계를 완료할 수 있습니다. 이 단계를 완료하려면 먼저 [Lifecycle Services에 구성 업로드](er-upload-configuration-into-lifecycle-services.md)의 단계를 완료해야 합니다. LCS에 대한 액세스도 필요합니다.

1. 다음 역할 중 하나를 사용하여 애플리케이션에 로그인합니다.

    - 전자 보고 개발자
    - 시스템 관리자

2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **구성** 을 선택합니다.

<a name="accessconditions"></a>
> [!NOTE]
> 현재 Dynamics 365 Finance 사용자가 ER 구성을 가져오기 위해 [액세스](../../lifecycle-services/asset-library.md#asset-library-support)하려는 자산 라이브러리가 포함된 LCS 프로젝트의 구성원인지 확인하십시오.
>
> Finance에서 사용되는 도메인과 다른 도메인을 나타내는 ER 리포지토리에서 LCS 프로젝트에 액세스할 수 없습니다. 시도하면 LCS 프로젝트의 빈 목록이 표시되고 LCS의 프로젝트 수준 자산 라이브러리에서 ER 구성을 가져올 수 없습니다. ER 구성을 가져오는 데 사용되는 ER 리포지토리에서 프로젝트 수준 자산 라이브러리에 액세스하려면 현재 Finance 인스턴스가 프로비저닝된 테넌트(도메인)에 속한 사용자의 자격 증명을 사용하여 Finance에 로그인합니다.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>데이터 모델 구성의 공유 버전 삭제

1. **구성** 페이지의 구성 트리에서 **샘플 모델 구성** 을 선택합니다.

    샘플 데이터 모델 구성의 첫 번째 버전을 생성하고 [Lifecycle Services에 구성 업로드](er-upload-configuration-into-lifecycle-services.md)의 단계를 완료했을 때 LCS에 게시했습니다. 이 절차에서는 해당 버전의 ER 구성을 삭제합니다. 이후 이 항목의 뒷부분에 나오는 LCS에서 해당 버전을 가져옵니다.

2. 목록에서 원하는 기록을 찾아 선택합니다.

    이 예시에서는 상태가 **공유** 인 구성 버전을 선택합니다. 이 상태는 구성이 LCS에 게시되었음을 나타냅니다.

3. **상태 변경** 을 선택합니다.
4. **중단** 을 선택합니다.

    선택한 버전의 상태를 **Shared** 에서 **Discontinued** 로 변경하면 해당 버전을 삭제할 수 있습니다.

5. **확인** 을 선택합니다.
6. 목록에서 원하는 기록을 찾아 선택합니다.

    이 예시에서는 **Discontinued** 상태의 구성 버전을 선택합니다.

7. **삭제** 를 선택합니다.
8. **예** 를 선택합니다.

    이제 선택한 데이터 모델 구성의 초안 버전 2만 사용할 수 있습니다.

9. 페이지를 닫습니다.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>LCS에서 데이터 모델 구성의 공유 버전 가져오기

1. **조직 관리 \> 작업 영역 \> 전자 보고** 로 이동합니다.

2. **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택합니다.

3. **Litware, Inc.** 타일에서 **리포지토리** 를 선택합니다.

    이제 Litware, Inc. 구성 제공자의 리포지토리 목록을 열 수 있습니다.

4. **열기** 를 선택합니다.

    이 예시에서는 **LCS** 리포지토리를 선택하고 엽니다. 선택한 ER 리포지토리에서 [액세스](#accessconditions)하는 LCS 프로젝트 및 자산 라이브러리에 대한 액세스 권한이 있어야 합니다.

5. 목록에서 선택한 행을 표시합니다.

    이 예시에서는 버전 목록에서 **샘플 모델 구성** 의 첫 번째 버전을 선택합니다.

6. **가져오기** 를 선택합니다.
7. **예** 를 선택하여 LCS에서 선택한 버전 가져오기를 확인합니다.

    선택한 버전을 성공적으로 가져왔는지 확인하는 정보 메시지가 표시됩니다.

8. 페이지를 닫습니다.
9. 페이지를 닫습니다.
10. **구성** 을 선택합니다.
11. 트리에서 **샘플 모델 구성** 을 선택합니다.
12. 목록에서 원하는 기록을 찾아 선택합니다.

    이 예시에서는 상태가 **공유** 인 구성 버전을 선택합니다.

    선택한 데이터 모델 구성의 공유 버전 1도 이제 사용할 수 있습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
