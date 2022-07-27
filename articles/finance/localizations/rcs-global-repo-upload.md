---
title: RCS에서 ER 구성 생성 및 전역 리포지토리에 업로드
description: 이 항목에서는 Microsoft RCS(Regulatory Configuration Services)에서 ER(전자 보고) 구성을 만들고 이를 전역 리포지토리에 업로드하는 방법에 대해 설명합니다.
author: JaneA07
ms.date: 01/11/2021
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
ms.openlocfilehash: eb04362d6d7261af56d2940b085fbc8d43c9d662
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "8451342"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>RCS(Regulatory Configuration Services)에서 ER 구성을 생성하여 전역 리포지토리에 업로드

[!include [banner](../includes/banner.md)]

Microsoft RCS(Regulatory Configuration Services)를 사용하여 ER(전자 보고) 구성을 설계하고 조직에서 사용할 수 있도록 게시할 수 있습니다.

다음 절차에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 RCS 인스턴스에 구성된 ER 구성의 파생 버전을 생성한 다음 파생 구성을 전역 리포지토리에 업로드하는 방법을 설명합니다. 

이러한 절차를 완료하려면 먼저 다음 필수 요건을 완료해야 합니다.

- 조직의 RCS 환경에 액세스할 수 있습니다.
- 활성 구성 공급자를 생성하고 활성화합니다. 자세한 내용은 [구성 공급자 생성 및 활성으로 표시](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.

조직에 맞게 RCS 환경이 프로비저닝되었는지 확인해야 합니다. 조직에 맞게 프로비저닝된 RCS 인스턴스가 없는 경우 다음 단계를 사용하여 프로비저닝할 수 있습니다.

1. 재무 및 운영 앱에서 **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **관련 링크 / 외부 링크** 에서 **Regulatory services – 구성** 을 선택한 다음 지침에 따라 **로그인** 하여 프로비저닝합니다.

조직용으로 RCS 환경이 이미 프로비저닝된 경우 **로그인** 옵션을 선택하여 페이지 URL을 사용하여 액세스합니다.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>RCS에서 구성의 파생 버전 생성

> [!NOTE]
> RCS를 처음 사용하는 경우 파생할 수 있는 원본 구성이 없습니다. 전역 리포지토리에서 구성을 가져와야 합니다. 자세한 내용은 [구성 서비스의 글로벌 리포지토리에서 ER 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)를 참조하십시오.

1. RCS에 **로그인** 하고 **전자 보고** 작업 영역을 선택합니다.
2. 활성으로 설정된 조직의 활성 구성 공급자가 있는지 확인합니다(전제 조건 참조). 
3. **보고 구성** 을 선택합니다.
4. 새 버전을 가져올 구성을 선택합니다. 트리 위의 필터 필드를 사용하여 검색 범위를 좁힐 수 있습니다.
5. **구성 만들기** \> **이름에서 파생** 을 선택합니다.
6. 이름과 설명을 입력한 다음 **구성 만들기** 를 선택하여 '초안' 상태의 새 파생 버전을 생성합니다.
7. 새로 파생된 구성을 선택하고 필요한 경우 구성 형식을 추가로 변경합니다. 
8. 변경이 완료된 후 구성의 **변경 상태** 를 **완료** 로 설정해야 리포지토리에 게시할 수 있습니다. **확인** 을 선택합니다.

![RCS의 새 구성 버전.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> 구성 상태가 변경되면 연결된 애플리케이션과 관련된 유효성 검사 오류 메시지가 표시될 수 있습니다. 유효성 검사를 해제하려면 **구성** 탭의 작업 창에서 **사용자 매개 변수** 를 선택한 다음 구성의 **상태 변경 및 다시 지정 시 유효성 검사 건너뛰기** 옵션을 **예** 로 설정합니다. 

## <a name="upload-a-configuration-to-the-global-repository"></a>전역 리포지토리에 구성 업로드

새 구성 또는 파생 구성을 조직과 공유하려면 다음 단계를 수행하여 구성을 전역 리포지토리에 업로드할 수 있습니다.

1. 완료된 구성 버전을 선택한 다음 **리포지토리로 업로드** 를 선택합니다.
2. **전역(Microsoft)** 옵션을 선택한 다음 **업로드** 를 선택합니다.

    ![리포지토리에 업로드 옵션.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. 확인 메시지 상자에서 **예** 를 선택합니다. 
4. 필요에 따라 버전 설명을 업데이트한 다음 **확인** 을 선택합니다. 또한 선택적으로 연결된 애플리케이션 또는 GIT 리포지토리에 버전을 업로드할 수 있습니다.  

구성 상태가 **공유됨** 으로 업데이트되고 구성이 전역 리포지토리에 업로드됩니다. 업로드한 구성의 임시 버전도 생성되며 이후 변경이 필요한 경우 사용할 수 있습니다.

구성을 전역 리포지토리에 업로드한 후에는 다음과 같은 방법으로 해당 리포지토리에서 작업할 수 있습니다.

- Dynamics 365 인스턴스로 가져옵니다. 자세한 내용은 [(ER) RCS에서 구성 가져오기](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md)를 참조하십시오.
- 타사 또는 외부 조직과 공유하려면 [외부 조직과 ER(전자 보고) RCS 구성 공유(rcs-global-repo-share-configuration.md)](rcs-global-repo-share-configuration.md)를 참조하십시오.

    ![전역 리포지토리에 파생된 Intrastat Contoso 구성 버전.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>전역 리포지토리에서 구성 삭제
조직에서 만든 구성을 삭제하려면 다음 단계를 완료합니다.

1. **전자 보고** 작업 영역에서 구성 공급자가 **활성** 상태인지 확인합니다. 자세한 내용은 [구성 공급자 생성 및 활성으로 표시](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.
2. 활성 구성 공급자에서 **리포지토리** 를 선택합니다.
3. 리포지토리 유형 **전역** 을 선택하고 **열기** 를 선택합니다.
4. **필터** FastTab에서 **필터** 기능을 사용하여 삭제할 구성을 찾습니다.
5. **버전** FastTab에서 삭제할 구성 버전을 선택한 다음 **삭제** 를 선택합니다.

    ![전역 리포지토리에서 구성을 삭제합니다.](media/RCS_Delete_from_GlobalRepo.JPG)

6. 확인 메시지 상자에서 **예** 를 선택합니다.

    ![구성 버전 확인 메시지를 삭제합니다.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
구성 버전이 삭제되고 확인 메시지가 표시됩니다. 

> [!NOTE]
> 구성은 해당 구성을 만든 구성 공급자만 삭제할 수 있습니다. 구성이 다른 조직과 공유된 경우 삭제하기 전에 구성을 공유 해제해야 합니다.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
