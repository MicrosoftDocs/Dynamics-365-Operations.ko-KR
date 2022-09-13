---
title: 회계 보류 중인 문서
description: 이 문서에서는 회계 보류 중인 문서 페이지의 기능을 사용하는 방법에 대해 설명합니다.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: e915c248abd1c842f8f01490a49db9b824644a29
ms.sourcegitcommit: 07ed6f04dcf92a2154777333651fefe3206a817a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424371"
---
# <a name="documents-pending-accounting"></a>회계 보류 중인 문서

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이 문서에서는 **회계 보류 중인 문서** 페이지의 기능을 사용하는 방법에 대해 설명합니다.

Microsoft Dynamics 365 Finance 10.0.30에서는 **소스 문서 회계 프레임워크의 향상된 성능** 기능을 사용할 수 있습니다. 이 기능은 자유 텍스트 송장에 대한 전기 프로세스부터 시작하여 소스 문서 사용 문서 전기에 대한 전기 프로세스를 개선합니다.

이 기능이 사용되면 보조 원장 문서 전기는 총계정원장으로 이전되는 전체 회계 세부 사항을 생성하는 회계 생성 또는 *분개* 프로세스와 별도로 수행됩니다. 예를 들어, 자유 텍스트 송장 전기 프로세스에서 전체 회계가 생성되기 전에 **수취 계정** 모듈의 고객 송장이 기록됩니다. 이 향상된 성능 기능을 통해 회계 생성이 지연되는 동안 고객 송장을 더 빨리 기록할 수 있습니다.

**회계 보류 중인 문서** 페이지에서는 다음 단추를 사용할 수 있습니다.

- **회계 생성** - 분개를 위해 현재 계정 생성이 보류 중인 문서를 제출합니다.
- **분포 보기** - 목록에서 선택한 문서에 대한 회계 분포를 봅니다.
- **오류 로그 보기** - 회계 상태가 오류를 나타내는 문서에 대해 존재하는 오류 메시지 세부 정보를 봅니다. 문서 행에서 **오류 로그** 링크를 선택하여 동일한 오류 메시지 세부 정보를 볼 수 있습니다.

회계 생성은 **회계 프레임워크 프로세서** 라는 프로세스 자동화 백그라운드 프로세스에 의해 수행됩니다. 모든 프로세스 자동화의 설정 및 구성에 대한 자세한 내용은 [프로세스 자동화](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)를 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
