---
title: RCS(Regulatory Configuration Service) - RCS 환경 삭제
description: 이 항목에서는 RCS(Regulatory Configuration Service) 시스템 관리자가 RCS 환경 및 관련 데이터를 삭제하는 방법에 대해 설명합니다.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: f9073a14143423676f23f9bf8dc9c17dbae18a6c3ad0d2f6d1e33919fd9162bf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450625"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>RCS(Regulatory Configuration Service) - RCS 환경 삭제

[!include [banner](../includes/banner.md)]

이 항목에서는 RCS(Regulatory Configuration Service) 시스템 관리자가 RCS 환경 및 관련 데이터를 삭제하는 방법에 대해 설명합니다.

이 항목의 절차를 완료하려면 다음 사전 요건을 충족해야 합니다.

- RCS 환경에 대한 **시스템 관리자** 역할이 할당되어 있어야 합니다.
- **시스템 관리자** 역할에는 **RCSDeleteEnvironmentDuty** 역할이 할당되어 있어야 합니다.

## <a name="delete-an-rcs-environment"></a>RCS 환경 삭제

1. RCS를 열고 **전자 보고** 작업 영역 타일을 선택합니다.
2. **관련 링크** 섹션에서 **RCS 환경 삭제** 를 선택합니다.

    ![관련 링크 섹션에서 RCS 환경 링크를 삭제합니다.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. 표시되는 대화 상자에서 환경 삭제 범위에 대한 메시지를 검토합니다.

    ![RCS 환경 삭제 대화 상자의 메시지.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > RCS 환경의 삭제는 되돌릴 수 없습니다.
    >
    > 이 작업은 선택한 RCS 환경과 글로벌 리포지토리에 저장된 기능 및 구성을 포함한 모든 관련 데이터를 삭제합니다. 다른 조직과 공유되는 기능 및 구성은 종속성이 없는 경우 공유되지 않고 삭제됩니다. 종속성이 있는 기능 및 구성은 중단됨으로 표시됩니다.

4. 제공된 필드에 RCS 환경의 GUID(Global Unique Identifier)를 입력하여 삭제할지 확인합니다. 삭제 메시지에 환경의 GUID가 포함됩니다.
5. **환경 삭제** 를 선택합니다.
    
이제 RCS 환경 및 관련 데이터가 삭제됩니다.

> [!IMPORTANT]
> RCS 환경을 삭제한 후에는 데이터를 복구할 방법이 없습니다. 사용 가능한 모든 RCS 영역에서 새로운 RCS 환경을 생성할 수 있습니다.
