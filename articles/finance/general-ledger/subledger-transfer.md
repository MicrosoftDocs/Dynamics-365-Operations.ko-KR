---
title: 하위 원장을 총계정원장으로 전송
description: 이 항목에서는 하위 원장을 총계정원장으로 전송하는 프로세스와 관련된 기능에 대해 설명합니다.
author: rcarlson
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 213bbc2541c614aa26b0c830431818fb99c7682d
ms.sourcegitcommit: f5885999e008a49fe072d95f15e239905c24918a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2021
ms.locfileid: "8451297"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>하위 원장을 총계정원장으로 전송

[!include [banner](../includes/banner.md)]

이 항목에서는 하위 원장 분개장 항목의 묶음을 전송하는 규칙과 관련된 기능에 대해 설명합니다.

버전 8.1에서는 규칙 전송을 허용하도록 변경되었으며 **동기화** 옵션은 사용되지 않습니다. 자세한 내용은 [Finance and Operations의 제거되거나 사용되지 않는 기능](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20)을 참조하십시오.

하위 원장 묶음을 전송하는 데 사용할 수 있는 옵션은 다음과 같습니다.

- **비동기** – 총계정원장으로 하위 원장 회계 항목 전송이 즉시 예약됩니다. 서버에서 요청을 처리할 수 있는 리소스가 확보되는 즉시 총계정원장 바우처가 기록됩니다.
- **예약된 배치** – 이전되어야 하는 하위 원장 회계 항목은 총계정원장의 처리 대기열에 추가됩니다. 대기열의 항목은 수신된 순서대로 처리됩니다. 자원이 서버에서 일괄 작업을 처리할 수 있는 경우 각 총계정원장 바우처는 예약된 시간에 계정을 업데이트합니다.

버전 10.0.8은 **비동기** 옵션의 성능을 향상시키기 위해 개선되었습니다. 이 기능은 **하위 원장을 총계정원장으로 이전하는 성능 최적화** 라는 이름의 기능으로 지원됩니다.

보조원장 묶음의 비동기 전송 기능은 보조원장에서 총계정원장으로의 데이터 전송을 개선하는 데 도움이 됩니다. 더 작은 트랜잭션 집합을 그룹화하고 트랜잭션을 그룹으로 전송함으로써 이 기능은 트랜잭션을 보다 효율적으로 처리합니다. 트랜잭션을 그룹화하면 일괄 처리 서버의 리소스가 더 효율적으로 사용됩니다.

보조원장 배치를 비동기식으로 전송하려면 배치 서버에서 즉시 실행하기 위해 배치 작업이 생성되기 때문에 배치 서버가 설정되고 온라인이며 작동해야 합니다. **하위 원장을 총계정원장으로 전송하는 기능의 성능을 최적화** 기능을 활성화하면 **프로세스 자동화 폴링 시스템 작업** 이라는 **프로세스 자동화** 시스템 배치 작업도 활성화되어야 합니다. 자세한 내용은 [프로세스 자동화](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)를 참조하세요.

일괄 처리 수준의 효율성 변경으로 시스템의 모든 법인에 대해 단일 반복 배치 작업을 사용합니다. 런타임에 아직 전송되지 않은 필수 레코드를 처리하기 위한 새 일괄 처리 작업이 생성됩니다. 시스템 관리의 **프로세스 자동화** 페이지에서 더 많은 설정을 제어할 수 있습니다. 이 페이지에서 백그라운드 프로세스를 수정하고 빈도를 변경하고 수면 기간을 정의할 수 있습니다.

프로세스 자동화 설정에 대한 자세한 내용은 [프로세스 자동화](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md)를 참조하십시오.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
