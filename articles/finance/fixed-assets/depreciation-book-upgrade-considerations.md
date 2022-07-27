---
title: 감가상각 장부 업그레이드 개요
description: 이 항목에서는 고정 자산의 현재 장부 기능에 대해 설명합니다. 이 기능은 이전 버전에서 사용 가능했던 가치 모델 기능을 기반으로 하지만 이전에 감가상각 분개장에서만 제공되었던 모든 기능도 가지고 있습니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eaa47b47a93deda24a6c76572881d1e5bba29c52
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451441"
---
# <a name="depreciation-book-upgrade-overview"></a>감가상각 장부 업그레이드 개요

[!include [banner](../includes/banner.md)]

이 항목에서는 고정 자산의 현재 장부 기능에 대해 설명합니다. 이 기능은 이전 버전에서 사용 가능했던 가치 모델 기능을 기반으로 하지만 이전에 감가상각 분개장에서만 제공되었던 모든 기능도 가지고 있습니다. 가치 모델 기능과 감가상각 장부 기능이 하나의 장부라는 개념으로 통합되었습니다. 장부 기능을 사용하면 조직의 모든 고정 자산 프로세스에 하나의 페이지, 조회, 보고서 모음을 사용할 수 있습니다. 이 항목에서는 업그레이드하기 전에 고려해야 할 몇 가지 사항을 설명합니다. 

업그레이드 프로세스는 기존 설정과 모든 기존 트랜잭션을 새 장부 구조로 옮깁니다. 가치 모델은 총계정원장에 게시하는 장부로 현재와 같이 유지됩니다. 감가상각 장부는 총계정원장에 게시 옵션이 아니요로 설정된 분개장으로 이동합니다. 감가상각 장부 분개장 이름은 총계정원장 분개장 이름으로 이동하며 기장 계층은 없음으로 설정됩니다. 감가상각 장부 트랜잭션은 고정 자산 트랜잭션으로 이동합니다.

데이터 업그레이드를 실행하기 전에 감가상각 장부 분개장 라인을 트랜잭션 바우처로 업그레이드하는 데 사용할 수 있는 두 가지 옵션과 바우처 시리즈에 사용되는 숫자 순서를 이해해야 합니다.

옵션 1: **시스템 정의 숫자 순서** - 업그레이드 성능을 최적화하는 기본 옵션입니다. 업그레이드는 숫자 순서 프레임워크를 사용하지 않고 세트 기반 접근 방식으로 바우처를 할당합니다. 업그레이드 후 업그레이드된 트랜잭션에 따라 **다음 숫자 세트** 와 함께 새 번호 순서가 생성됩니다. 기본적으로는 사용되는 숫자 순서는 FADBUpgr\#\#\#\#\#\#\#\#\# 형식입니다. 이 방법을 사용할 때 형식을 조정하는 데 사용할 수 있는 몇 가지 매개 변수가 있습니다.

-   **숫자 순서 코드** - 숫자 순서를 구분하는 코드입니다. 이 숫자 순서 코드는 업그레이드에 의해 생성되므로 존재할 수 없습니다.
    -   상수 이름: **NumberSequenceDefaultCode**
    -   기본값: "FADBUpgr"
-   **접두사** – 바우처 번호의 접두사로 사용할 상수 문자열 값입니다.
    -   상수 이름: **NumberSequenceDefaultParameterPrefix**
    -   기본값: "FADBUpgr"
-   **영숫자 길이** – 숫자 순서의 영숫자 세그먼트 길이입니다.
    -   상수 이름: **NumberSequenceDefaultParameterAlpanumericLength**
    -   기본값: 9
-   **시작 숫자** - 숫자 순서에서 사용할 첫 번째 숫자입니다.
    -   상수 이름: **NumberSequenceDefaultParameterStartNumber**
    -   기본값: 1

옵션 2: **기존 사용자 정의 숫자 순서** - 이 옵션을 사용하면 업그레이드에 사용할 숫자 순서를 정의할 수 있습니다. 고급 숫자 순서 구성이 필요한 경우 이 옵션을 사용하는 것이 좋습니다. 숫자 순서를 사용하려면 다음 정보를 사용하여 업그레이드 클래스 ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans를 수정해야 합니다.

-   **숫자 순서 코드** – 숫자 순서의 코드입니다.
    -   상수 이름: **NumberSequenceExistingCode**
    -   기본값: 기본값 없음, 숫자 순서 코드로 업데이트해야 합니다.
-   **공유 숫자 순서** – 숫자 순서의 범위를 나타내는 부울 값입니다. 모든 회사에 공유 숫자 순서를 사용하면 "true"를, 회사별 범위를 사용하면 "false"를 지정합니다. "false"를 사용하는 경우 감가상각 장부 트랜잭션을 포함하는 모든 회사에 지정된 이름의 숫자 순서가 있어야 합니다. 공유 숫자 순서는 감가상각 장부 트랜잭션이 포함된 모든 파티션에 존재합니다.
    -   상수 이름: **NumberSequenceExistingIsShared**
    -   기본값: true

매개 변수는 ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans 클래스의 시작 부분에 있습니다. 

*// 바우처 할당에 대한 원하는 접근 방식 지정* 
 *// true, 기존 숫자 순서 코드를 사용하려는 경우* 
 *// false, 시스템 정의 번호 순서(기본값)* const boolean NumberSequenceUseExistingCode = false;를 사용하는 경우  

*// 시스템 정의 숫자 순서 방식을 사용하는 경우 숫자 순서의 매개 변수를 지정합니다.*
 *// 이러한 매개 변수를 사용하여 새로운 숫자 순서가 생성됩니다.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// 기존 숫자 순서 방식을 사용하는 경우 기존 숫자 순서 코드를 지정합니다.* 
 *// 기존 숫자 순서에 대한 바우처 할당이 행 단위로 이루어집니다.* const str NumberSequenceExistingCode = ''; *// 기존 숫자 순서 코드의 범위를 지정합니다.* 
 *// true, 지정된 숫자 순서를 공유하는 경우* 
 *// false, 지정한 숫자 순서가 회사별 순서일 경우* 
 *// 지정된 범위의 숫자 순서 코드를 찾을 수 없는 경우 기본 시스템 정의 숫자 순서가 사용됩니다.* const boolean NumberSequenceExistingIsShared = true; 

상수가 수정된 후 클래스가 포함된 프로젝트를 다시 빌드합니다. 

시스템 생성 순자 순서 방식(옵션 1)을 사용하는 경우 업그레이드 스크립트 매개 변수에 지정된 대로 세트 기반 처리를 사용하여 바우처 번호를 할당합니다. 또한 할당 후 지정된 매개 변수를 사용하여 새 숫자 순서를 만듭니다. 

기존 사용자 정의 숫자 순서 방식(옵션 2)을 사용하는 경우 데이터 업그레이드는 감가상각 장부 트랜잭션이 있는 각 파티션 및 회사의 데이터베이스에 지정된 범위의 숫자 순서가 있는지 여부를 확인합니다. 숫자 순서가 없으면 업그레이드 시 행별 처리를 사용하여 숫자 순서 프레임워크를 사용하여 숫자 순서에 지정된 대로 바우처 번호를 할당합니다. 지정된 범위에 숫자 순서가 존재하지 않는 경우 업그레이드는 기본 시스템 정의 숫자 순서 방식을 사용하여 바우처 번호를 할당하고 할당 후 지정된 기본 매개 변수를 사용하여 새로운 숫자 순서를 만듭니다.

어떤 방식이든 데이터 업그레이드 스크립트는 이전 감가상각 장부 분개장 이름을 위해 생성된 새로운 총계정원장 분개장 이름의 **바우처 시리즈** 필드의 숫자 순서를 사용합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
