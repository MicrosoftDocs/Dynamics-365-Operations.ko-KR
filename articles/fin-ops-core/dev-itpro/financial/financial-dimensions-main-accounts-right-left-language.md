---
title: 오른쪽에서 왼쪽으로 쓰는 언어의 재무 측정기준 및 기본 계정
description: 이 항목에서는 오른쪽에서 왼쪽으로 쓰는 언어를 사용할 때 결정해야 하는 결정 사항에 대해 설명하고 재무 차원 및 기본 계정을 설정해야 합니다.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0c88b95ba7c596f4e8c1677c475ca92deba1cb71
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460789"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>오른쪽에서 왼쪽으로 쓰는 언어의 재무 측정기준 및 기본 계정

[!include [banner](../includes/banner.md)]

이 항목에서는 오른쪽에서 왼쪽으로 쓰는 언어를 사용할 때 고려해야 하는 일부 구현 사항에 대해 설명하고 재무 차원 및 기본 계정을 설정해야 합니다.

재무 차원과 기본 계정은 구현을 위한 계획 단계의 핵심 구성 요소입니다. 재무 차원 및 기본 계정이 시스템에서 생성된 후 **계정 구조 구성**, **고급 규칙 구조** 및 **애플리케이션 통합을 위한 재무 차원 구성** 페이지에서 사용됩니다. 해당 페이지에 정의된 순서는 데이터 입력 및 소비를 위해 시스템에서 사용됩니다. 시스템의 일부 위치에서는 재무 차원과 기본 계정이 별도의 필드에 나타납니다. 분개와 같은 다른 위치에서는 재무 차원과 기본 계정이 단일 문자열로 나타납니다.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>오른쪽에서 왼쪽으로 쓰는 시스템에서 재무 차원 및 기본 계정을 설정하기 위한 모범 사례

- 계정 코드집에 대한 구분 기호를 선택할 때 이중 구분 기호 옵션 중 하나를 선택합니다. 이중 하이픈(`--`), 이중 막대(`||`), 이중 마침표(`..`) 또는 이중 밑줄(`\\`).
- 재무 차원 및 기본 계정 값을 생성할 때 숫자와 오른쪽에서 왼쪽으로 쓰는 언어 문자만 사용합니다.
- 재무 차원 및 기본 계정 값에서 선택한 계정 코드집 구분 기호를 사용하지 마세요.

이러한 모범 사례를 따르면 시스템 전체에서 사용자 정의 순서의 일관된 표현을 보장하는 데 도움이 됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]