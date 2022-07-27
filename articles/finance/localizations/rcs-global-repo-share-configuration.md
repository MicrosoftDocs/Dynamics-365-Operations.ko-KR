---
title: RCS/전역 리포지토리의 ER 구성을 외부 조직과 공유
description: 이 항목에서는 Microsoft RCS(Regulatory Configuration Services)/전역 리포지토리의 ER(전자 보고) 구성을 외부 조직과 직접 공유하는 방법에 대해 설명합니다.
author: JaneA07
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ee7feef83ffa458e7cbd238d37a0f343d1a202f48002da67823df024bb609d02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450175"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>RCS(Regulatory Configuration Services) 전역 리포지토리의 ER(전자 보고) 구성을 외부 조직과 공유

[!include [banner](../includes/banner.md)]

Microsoft RCS(Regulatory Configuration Services)를 사용하여 ER(전자 보고) 구성을 공유한 다음 외부 조직에 게시할 수 있습니다.

다음 절차에서는 RCS 사용자가 RCS 인스턴스에 구성된 ER 구성 버전을 외부 조직과 공유하는 방법을 설명합니다. 이러한 절차를 완료하려면 먼저 다음 필수 요건을 완료해야 합니다.

- RCS 인스턴스에 액세스합니다.
- 활성 구성 공급자를 생성합니다. 자세한 내용은 [구성 공급자 생성 및 활성으로 표시](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.
- 새 버전의 ER 구성을 만들고 업로드합니다. 자세한 내용은 [ER(전자 보고) 구성의 새 버전 만들기 및 업로드](rcs-global-repo-upload.md)를 참조하십시오.

또한 RCS 환경이 귀사에 맞게 프로비저닝되었는지 확인해야 합니다.

1. 재무 및 운영 앱에서 **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. 회사에 맞게 프로비저닝된 RCS 환경이 없는 경우 **Regulatory services - 외부 구성** 을 선택한 다음 지침에 따라 환경을 프로비저닝합니다.

회사용으로 RCS 환경이 이미 프로비저닝된 경우 로그인 옵션을 선택하여 페이지 URL을 사용하여 액세스합니다.

## <a name="verify-the-configuration-that-you-want-to-share"></a>공유할 구성 확인

다음 단계에 따라 공유하려는 구성이 전역 리포지토리에 이미 업로드되었는지 확인합니다.

1. **전자 보고** 작업 영역에서 구성 공급자의 **리포지토리** 를 선택합니다.

    ![구성 공급자.](media/1_RCS_Repo_for_config_provider.JPG)

2. **전역 리포지토리** \> **열기** 를 선택합니다.
3. 공유할 구성을 검색합니다. 필터 필드를 사용하여 검색 범위를 좁힐 수 있습니다. 전역 리포지토리에서 구성을 찾을 수 없는 경우 [ER(전자 보고) 구성의 새 버전 만들기 및 업로드](rcs-global-repo-upload.md)의 단계를 따르십시오.

## <a name="share-er-configurations-with-external-organizations"></a>외부 조직과 ER 구성 공유

구성 공급자에 구성을 생성한 후에는 **전역 구성 리포지토리** 페이지의 **공유 대상** FastTab을 사용하여 외부 조직과 직접 공유할 수 있습니다.

1. **전자 보고** 작업 영역에서 구성 공급자의 **리포지토리** 를 선택합니다.
2. **전역 리포지토리** \> **열기** 를 선택합니다. 
3. 공유할 구성을 선택합니다.
4. **공유 대상** FastTab에서 **조직** 을 선택합니다.

    ![FastTab으로 공유.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. 대화 상자에서 외부 조직의 도메인 이름을 입력한 후 **확인** 을 선택합니다.

    ![외부 조직과 구성 버전 공유 대화 상자.](media/1_RCS_Repo_for_Share_with_form.JPG)

구성은 외부 조직과 공유되며 전역 리포지토리의 해당 조직에서 사용할 수 있습니다. 여기서 조직의 RCS 인스턴스 또는 재무 및 운영 애플리케이션 인스턴스로 가져올 수 있습니다.

6. 이전에 외부 조직과 공유한 구성을 공유 해제하려면 구성을 선택하고 **공유 해제** 를 클릭한 다음 **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]