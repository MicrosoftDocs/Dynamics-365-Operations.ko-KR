---
title: 솔루션 인식과 관련된 문제 해결
description: 이번에는 솔루션 인식과 관련된 문제를 해결하는 데 도움이 되는 문제 해결 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f83a064bfc8896bdf76bcd38f9187ed0e1ea56cf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460650"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>솔루션 인식과 관련된 문제 해결

[!include [banner](../../includes/banner.md)]





이번에는 Finance 및 Operations 앱 Dataverse 간의 이중 쓰기 통합에 대한 문제 해결 정보를 제공하고 . 특히 솔루션 인식과 관련된 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

> [!IMPORTANT]
> 이 항목에서 해결하는 일부 문제에는 시스템 관리자 역할 또는 Microsoft Azure Active Directory(Azure AD) 테넌트 관리자 자격 증명이 필요할 수 있습니다. 각 문제에 대한 섹션에서는 특정 역할 또는 자격 증명이 필요한지 여부를 설명합니다.

## <a name="error-on-the-dual-write-page"></a>이중 쓰기 페이지 오류

**이중 쓰기** 페이지에서 다음 예시와 유사한 오류 메시지가 나타날 수 있습니다.

*이름이 'msdyn\_dualwriteentitymap'이고 namemapping='Logical'인 엔터티를 MetadataCache에서 찾을 수 없습니다.*

문제를 해결하려면 이중 쓰기 코어 솔루션이 Dataverse에 설치되어 있는지 확인하십시오. 이중 쓰기 코어 솔루션은 솔루션 인식을 위한 전제 조건입니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]