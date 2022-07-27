---
title: 세계화 기능 구성 요소
description: 이 항목에서는 세계화 기능 구성 요소에 대한 개요를 제공합니다.
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
ms.openlocfilehash: 87d7dd231b9ccda7761c91f129659c18039f3299
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451723"
---
# <a name="globalization-feature-components"></a>세계화 기능 구성 요소

[!include [banner](../includes/banner.md)]

세계화 기능은 전자 보고(ER) 구성에서 데이터 변환 규칙을 정의하는 구성 요소 집합입니다. 이러한 구성 요소에는 전자 문서를 처리한 다음 외부 채널로 전송하거나 외부 채널에서 수신하기 위한 지침이 포함됩니다. 여기에는 수신 비즈니스 데이터에 대해 기능을 실행해야 하는 시기를 정의하는 조건도 포함됩니다.

모든 구성 요소는 서로 의존합니다. 세계화 기능을 사용하면 이러한 종속성을 쉽게 만들고 유지 관리하고 구성 요소 집합의 수명 주기 관리 및 버전 관리를 지원할 수 있습니다.

## <a name="access-electronic-invoicing-feature-components"></a>전자 인보이스 기능 구성 요소에 액세스 

1. RCS(Regulatory Configuration Service) 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **기능** 섹션에 있는 **전자 청구서 발행** 타일을 선택합니다.

    세계화 기능에는 여러 구성 요소가 있습니다. **전자 송장 기능** 페이지에는 각 구성 요소에 대한 별도의 탭이 있습니다.

    - **버전** – 이 구성 요소는 기능의 수명 주기 관리를 지원합니다. 이를 사용하여 기능의 다양한 버전에 대한 상태를 관리할 수 있습니다.
    - **구성** – 이 구성 요소를 사용하면 처리 파이프라인에서 사용되는 관련 ER 형식 및 형식 매핑 구성을 관리, 확인 및 편집할 수 있습니다.
    - **설정** – 이 구성 요소를 사용하면 전자 송장 서비스와 같은 세계화 서비스 사용자가 관련 기능 버전 설정을 관리할 수 있습니다. 따라서 통신 및 응답 규칙의 유연한 구성을 지원합니다.
    - **환경** – 전자 송장 서비스와 같은 글로벌화 서비스 사용자는 이 구성 요소를 사용하여 기능 버전 설정이 사용되는 환경을 관리할 수 있습니다. 또한 기능 버전 설정에 액세스할 수 있는 사용자에게 권한을 부여할 수 있습니다.
    - **조직** – 이 구성 요소를 통해 사용자는 기능을 외부 조직과 공유할 수 있습니다.
    - **태그** – 이 구성 요소를 사용하면 참조에 대한 세계화 청사진에서 사용할 수 있는 기능에 태그를 지정할 수 있습니다.
