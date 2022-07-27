---
title: BYOD 예약 일괄 작업 최적화
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 BYOD(Bring Your Own Database) 기능을 사용할 때 성능을 최적화하는 방법을 설명합니다.
author: andreabichsel
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: a2f110d105b8c04f07f219f7f11a57d24e00ce4a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452395"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>BYOD 예약 일괄 작업 최적화


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 BYOD(Bring Your Own Database) 기능을 사용할 때 성능을 최적화하는 방법을 설명합니다. BYOD에 대한 자세한 내용은 [BYOD(Bring Your Own Database)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

## <a name="performance-considerations-for-data-export"></a>데이터 내보내기에 대한 성능 고려 사항

엔터티가 대상 데이터베이스에 게시된 후 내보내기 기능을 사용하여 **데이터 관리** 작업 영역에서 데이터를 이동할 수 있습니다. 내보내기 기능을 사용하면 하나 이상의 엔터티가 포함된 데이터 이동 작업을 정의할 수 있습니다. 데이터 가져오기 프로세스에 대한 자세한 내용은 [데이터 가져오기 및 내보내기 작업 개요](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

**내보내기** 페이지를 사용하여 CSV(쉼표로 구분된 값) 파일과 같은 다양한 대상 데이터 형식으로 데이터를 내보낼 수 있습니다. 이 페이지는 또한 다른 대상으로 SQL 데이터베이스를 지원합니다.

여러 엔터티가 있는 데이터 프로젝트를 만들고 일괄 처리를 사용하여 해당 데이터 프로젝트를 실행하도록 예약할 수 있습니다. **일괄 처리로 내보내기** 옵션을 선택하면 데이터 내보내기 작업이 주기적으로 실행되도록 예약할 수 있습니다.

BYOD 내보내기의 전체적인 안정성을 유지하려면 하나의 내보내기 프로젝트에 여러 엔터티를 추가할 때 주의해야 합니다. 동일한 프로젝트에 추가할 엔터티 수를 결정할 때는 다음 매개 변수를 고려하세요.

- 엔터티의 복잡성
- 엔터티당 예상 데이터 볼륨
- 작업 수준에서 내보내기를 완료하는 데 필요한 전체 시간

최상의 성능을 위해 단일 프로젝트에 수백 개의 엔터티를 추가하지 마세요. 더 적은 수의 엔터티가 포함된 여러 작업을 만드는 것이 좋습니다.

## <a name="scheduling-byod-batch-jobs"></a>BYOD 일괄 작업 예약

Microsoft Dynamics 365 Human Resources 사용자에게 미치는 영향을 줄이기 위해 야간 또는 근무 시간 이후에 BYOD 일괄 작업을 실행하세요. 정기적인 일괄 작업의 표준 시간대를 확인하세요. 일부 일괄 작업은 태평양 표준시(PST)를 사용할 수 있습니다.

성능 문제를 방지하기 위해 BYOD 일괄 작업의 예약 빈도를 구성할 때 다음 요소를 고려하세요.

- 각 일괄 작업을 완료하는 데 필요한 시간
- BYOD의 데이터에 대한 비즈니스 요구

각 일괄 작업의 빈도를 다음 예약된 실행 시간 전에 작업을 완료할 수 있는 값으로 설정합니다. Human Resources의 성능에 부정적인 영향을 미칠 수 있으므로 여러 작업을 병렬로 실행하지 마세요.

최상의 성능을 위해 항상 **내보내기** 페이지에서 **일괄 처리로 내보내기** 옵션을 사용하여 BYOD 일괄 작업을 예약하세요. **관리 \> 정기 데이터 작업 관리** 에서 정기 내보내기를 예약하지 마세요.

## <a name="incremental-export"></a>증분 내보내기

데이터 내보내기를 위한 엔터티를 추가할 때 증분 푸시(내보내기) 또는 전체 푸시를 수행할 수 있습니다. 전체 푸시는 BYOD 데이터베이스의 엔터티에서 모든 기존 레코드를 삭제합니다. 그런 다음 Human Resources 엔터티의 현재 레코드 집합을 삽입합니다.

증분 푸시를 수행하려면 **엔터티** 페이지에서 각 엔터티에 대해 변경 내용 추적을 켜야 합니다. 자세한 내용은 [엔터티의 변경 내용 추적 활성화](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

증분 푸시를 선택하면 첫 번째 푸시는 항상 전체 푸시입니다. SQL은 이 첫 번째 전체 푸시부터 변경 사항을 추적합니다. 새 레코드가 삽입되거나 레코드가 업데이트 또는 삭제되면 변경 사항이 대상 엔터티에 반영됩니다.

## <a name="time-outs"></a>시간 제한

BYOD 내보내기의 기본 시간 제한은 다음과 같습니다.

- 자르기 작업의 경우 10분
- 대량 삽입 작업의 경우 1시간

볼륨이 크면 이러한 시간 제한 설정이 충분하지 않을 수 있습니다. 이를 업데이트하려면 **데이터 관리 \> 프레임워크 매개 변수 \> BYOD(Bring Your Own Database)** 로 이동합니다. 이러한 시간 제한은 회사별로 다르며 각 회사에 대해 별도로 설정해야 합니다.

## <a name="known-limitations"></a>알려진 제한

BYOD 기능에는 다음과 같은 제한이 있습니다.

- 동기화하는 동안 데이터베이스에 활성 잠금이 없어야 합니다. 활성 잠금이 있으면 쓰기 속도가 느려지거나 Azure SQL 데이터베이스로 데이터를 내보내지 못할 수 있습니다.
- 복합 엔터티를 자신의 데이터베이스로 내보낼 수 없습니다. 현재 복합 엔터티는 지원되지 않습니다. 복합 엔터티를 구성하는 개별 엔터티를 내보내야 합니다. 같은 데이터 프로젝트에서 두 엔터티를 모두 내보낼 수는 있습니다.
- 고유 키가 없는 엔터티는 증분 푸시를 사용하여 내보낼 수 없습니다. 일부 기성 엔터티에서 레코드를 점진적으로 내보내려고 할 때 특히 이 제한이 적용될 수 있습니다. 이러한 엔터티는 데이터를 가져오기를 지원하도록 설계되었기 때문에 고유 키가 없습니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="incremental-push-doesnt-work-correctly"></a>증분 푸시가 제대로 작동하지 않음

**문제:** 엔터티에 대해 전체 푸시가 수행되면 **Select** 문을 사용할 때 BYOD에 많은 레코드 집합이 표시됩니다. 그러나 증분 푸시를 수행하면 BYOD에 몇 개의 레코드만 표시됩니다. 증분 푸시가 모든 레코드를 삭제하고 BYOD에서 변경된 레코드만 추가한 것처럼 보입니다.

**해결책:** SQL 변경 내용 추적 테이블이 예상되는 상태가 아닐 수 있습니다. 이 유형의 경우 엔터티에 대한 변경 내용 추적을 껐다가 다시 켜는 것이 좋습니다. 자세한 내용은 [엔터티의 변경 내용 추적 활성화](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

### <a name="staging-tables-arent-clearing"></a>준비 테이블이 지워지지 않음

**문제:** 프로젝트에 준비를 사용할 때 준비 테이블이 올바르게 지워지지 않습니다. 그러면 테이블의 데이터가 계속 증가하여 성능 문제가 발생합니다.

**해결책:** 준비 테이블에는 7일 간의 기록이 유지됩니다. 7일이 지난 기록 데이터는 **가져오기 내보내기 준비 정리** 일괄 작업으로 준비 테이블에서 자동으로 지워집니다. 이 작업이 중단되면 테이블이 올바르게 지워지지 않습니다. 이 일괄 작업을 다시 시작하면 준비 테이블을 자동으로 지우는 프로세스가 계속됩니다.

## <a name="see-also"></a>참고 항목

[데이터 관리 개요](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[BYOD(Bring Your Own Database)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[데이터 가져오기 및 내보내기 작업 개요](../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)<br>
[엔터티의 변경 내용 추적 활성화](../fin-ops-core/dev-itpro/data-entities/entity-change-track.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
