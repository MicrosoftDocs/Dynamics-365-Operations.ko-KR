---
title: 구성 작업
description: 이 항목에서는 세계화 기능 작업 공간에서 전자 보고(ER) 구성을 사용하기 위한 기본 시나리오에 대한 개요를 제공합니다.
author: dkalyuzh
ms.date: 01/26/2022
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
ms.openlocfilehash: 4318399ee58ed54b29f8d360345b8930238ea9f2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451726"
---
# <a name="work-with-configurations"></a>구성 작업

[!include [banner](../includes/banner.md)]

전자 보고(ER) 구성은 전자 송장 기능의 주요 구성 요소 집합 중 하나입니다. ER 구성에는 파일 구조 설정과 다음 두 가지 방법으로 데이터를 변환하기 위한 변환 규칙 세트가 포함됩니다.

- **ER 형식 구성 내보내기** – 이 구성은 데이터를 통합 내부 구조(ER 모델)에서 전자 파일 형식으로 변환합니다.
- **ER 형식 구성 가져오기** – 이 구성은 데이터를 전자 파일 형식에서 통합 내부 구조(ER 모델)로 변환합니다.

미리 정의된 형식으로 아웃바운드 전자 파일을 생성하는 것 외에도 ER 구성은 외부 웹 서비스에서 들어오는 메시지를 응답으로 구문 분석하는 데 널리 사용됩니다. 이 기능은 외부 채널과의 통신 결과를 가져오고 이러한 결과(코드, 메시지 및 로그)를 사용자가 읽을 수 있는 구조로 변환한 다음 해당 정보를 클라이언트 애플리케이션에 전달하는 구성 가능한 논리를 구축하는 데 도움이 됩니다.

전자 송장 기능에 ER 구성을 사용하려면 해당 구성을 기능에 연결하고 현재 기능 버전의 **구성** 탭에서 ER 구성을 사용할 수 있도록 해야 합니다. **추가**, **삭제**, **편집** 또는 **보기** 를 선택하여 연결된 ER 구성으로 작업할 수 있습니다.

ER 구성에 대한 링크를 추가하려면 먼저 해당 구성이 RCS(Regulatory Configuration Service) 리포지토리에 있어야 합니다. RCS 저장소에서 사용할 수 있는 ER 구성을 검토하려면 다음 단계를 따르십시오.

1. RCS 계정에 로그인합니다.
2. **전자 보고** 작업 공간의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.

새 ER 구성을 생성하거나 글로벌 리포지토리에서 기존 ER 구성을 가져오는 방법에 대한 자세한 내용은 [전자 보고](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)를 참조하십시오.

연결된 ER 구성을 조정하려면 현재 전자 송장 기능에 대한 **구성** 탭에서 **편집** 을 선택합니다. 시스템은 자동으로 ER 구성 버전을 생성합니다. 현재 버전이 활성 구성 공급자에 의해 생성되지 않은 경우 시스템은 구성 공급자를 사용하는 파생 버전을 생성합니다. 현재 버전이 활성 구성 공급자에 의해 생성된 경우 시스템은 새 버전을 생성합니다. 두 경우 모두 생성된 버전을 수정한 다음 필요한 모든 업데이트를 자동으로 수행할 수 있습니다.
