---
title: 통합 계정 그룹 및 추가 통합 계정
description: 이 토픽에서는 통합 계정 그룹 및 추가 통합 계정에 대한 정보를 제공하고 사용 방법에 대해 설명합니다.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidateAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 489f5417b6044e02d4711a03a17d6c19031cc2ee
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451219"
---
# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>통합 계정 그룹 및 추가 통합 계정

[!include [banner](../includes/banner.md)]

이 토픽에서는 통합 계정 그룹 및 추가 통합 계정에 대한 정보를 제공하고 사용 방법에 대해 설명합니다.

## <a name="consolidation-account-groups"></a>통합 계정 그룹

통합 계정 그룹을 사용하면 데이터 통합에 사용할 계정 그룹을 만들 수 있습니다. 일반적으로 통합 계정 그룹은 정부에서 지정한 계정 차트를 나타냅니다. 통합 계정 그룹은 계정을 회사 본사에서 정의한 그룹에 매핑할 수도 있습니다. **통합** 모듈의 **설정** 영역에서 통합 계정 그룹을 찾을 수 있습니다. 새 그룹을 추가할 때 계정 그룹의 고유 식별자와 이름을 입력합니다.

## <a name="additional-consolidation-accounts"></a>추가 통합 계정
추가 통합 계정을 사용하면 기존 계정 차트의 계정을 통합 계정 그룹에 지정할 수 있습니다. 그런 다음 통합 계정 값과 이름을 지정할 수 있습니다. 

**통합** 모듈의 **설정** 영역에서 추가 통합 계정을 찾을 수 있습니다. 새 통합 계정을 만들 때 다음 정보를 지정해야 합니다.

-   **주 계정** – 이 필드는 페이지에서 선택한 계정 차트를 기반으로 하는 모든 주 계정을 표시하는 조회입니다. 계정을 선택하면 **주 계정 이름** 필드에 이름이 자동으로 입력됩니다.
-   **통합 계정 그룹** – 이 필드를 사용하여 계정을 할당할 그룹을 지정합니다. 두 가지 다른 방법으로 통합하는 경우 4개의 통합 계정 그룹 모두에 동일한 계정을 추가해야 합니다.
-   **통합 계정** – 통합 계정의 값을 입력합니다. 이 값은 계정 차트의 계정일 필요는 없습니다. 필요한 모든 값이 될 수 있습니다.
-   **통합 계정 이름** – 조회 및 보고서에 표시할 계정 이름을 입력합니다.
-   **SAT 레벨** – 이 필드는 멕시코 세무 당국에 계정 명세서를 보고하는 데 사용됩니다. 

통합 계정 그룹 및 추가 통합 계정 만들기 완료하면 통합 온라인 프로세스에서 그룹을 선택할 수 있습니다.


자세한 내용은 [통합 그룹 및 추가 통합 계정 만들기](../general-ledger/tasks/create-consolidation-groups.md)를 참조하십시오. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
