---
title: 이중 쓰기 응용 프로그램 오케스트레이션 솔루션 제거
description: 이 항목에서는 이중 쓰기 응용 프로그램 오케스트레이션 솔루션을 제거하는 방법에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: 781b2cb19a563d5712fa65718c93bfdc242f0c4a
ms.sourcegitcommit: abfaef124c8747827d6f297821f01f1f6fbca6b7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8461048"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>이중 쓰기 응용 프로그램 오케스트레이션 솔루션 제거

[!include [banner](../../includes/banner.md)]

이 항목에서는 이중 쓰기 응용 프로그램 오케스트레이션 솔루션을 제거하는 방법에 대해 설명합니다.

일부 고객은 Microsoft Dataverse 환경에 여러 솔루션을 설치하는 이중 쓰기 응용 프로그램 오케스트레이션 패키지를 실수로 설치합니다. 패키지에 관련 없는 솔루션을 설치하면 예상치 못한 바람직하지 않은 문제가 발생할 수 있습니다.

이중 쓰기 응용 프로그램 오케스트레이션 패키지 설치와 관련된 문제를 해결하려면 다음 순서로 원치 않는 이중 쓰기 솔루션을 제거합니다.

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed(있는 경우)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed(이 솔루션을 제거하려면 Microsoft에서 지원 티켓을 열어야 합니다.)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

파티 및 전체 주소록 솔루션이 설치된 경우 다음 순서로 솔루션을 제거합니다.

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. 당사자
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
