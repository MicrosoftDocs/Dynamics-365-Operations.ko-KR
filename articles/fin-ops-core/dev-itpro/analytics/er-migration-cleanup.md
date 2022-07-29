---
title: ER 마이그레이션 정리
description: 이번에는 ER 마이그레이션 정리 함수를 사용하여 ER 템플릿 문제를 해결하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: d437bed9b9873f82bcd047e85245bd2a8c66fb3572c06660f29fc19f66aebae1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460972"
---
# <a name="er-migration-cleanup"></a>ER 마이그레이션 정리 

[!include[banner](../includes/banner.md)]

Finance 인스턴스를 관리할 때 현재 인스턴스를 다른 위치로 마이그레이션하기로 결정할 수 있습니다. 예를 들어 프로덕션 인스턴스를 새 샌드박스 환경으로 마이그레이션할 수 있습니다. 템플릿을 Microsoft Azure Blob 저장소에 저장하도록 전자 보고(ER) 프레임워크를 구성한 경우 새 샌드박스 환경의 **DocuValue** 테이블은 프로덕션 환경의 Blob 저장소 인스턴스를 참조합니다. 그러나 마이그레이션 프로세스가 Blob Storage의 아티팩트 마이그레이션을 지원하지 않기 때문에 이 인스턴스는 샌드박스 환경에서 액세스할 수 없습니다. 오히려 새 샌드박스 환경에서는 아직 ER 템플릿을 얻지 못한 샌드박스 환경의 Blob 저장소 인스턴스를 참조해야 합니다.

템플릿을 사용하여 비즈니스 문서를 생성하는 ER 형식을 실행하려고 하면 예외가 발생하고 누락된 템플릿에 대한 알림을 받습니다. 또한 ER 마이그레이션 정리 옵션을 사용하여 템플릿이 포함된 ER 형식 구성을 삭제한 다음 다시 가져오도록 안내합니다.

[![ER 형식을 실행합니다.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

**구성** 페이지(**조직 관리** \> **전자 보고** \> **구성**)로 이동하고 구성 트리에서 템플릿을 사용하는 ER 형식 구성을 삭제하려고 하면 유사한 오류가 표시됩니다.

[![ER 형식을 삭제합니다.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

액세스할 수 없는 ER 템플릿 문제를 해결하려면 다음 단계를 완료하십시오.

1.  **조직 관리** \> **정기** \> **마이그레이션 정리** 페이지로 이동합니다.
2.  실행하거나 삭제할 수 없는 ER 형식 구성을 선택하십시오.
3.  **삭제** 를 선택합니다.
4.  선택한 ER 형식 구성의 삭제를 확인합니다.
5.  삭제된 ER 형식 구성을 현재 Finance 인스턴스로 [가져옵니다](download-electronic-reporting-configuration-lcs.md).

## <a name="applicability"></a>적용 가능성

> [중요] **마이그레이션 정리** 옵션은 액세스할 수 없는 ER 템플릿이 포함된 ER 형식 구성에만 적용됩니다. **마이그레이션 정리** 옵션을 사용하여 ER 형식 구성을 삭제하면 ER은 유일한 애플리케이션 데이터베이스의 구성 아티팩트와 관련된 템플릿을 삭제합니다. Blob Storage에 적절한 실제 파일이 있는지 확인되지 않습니다. 대신 아무 것도 없다고 가정합니다. 따라서 **구성** 페이지에서 ER 구성 삭제 옵션의 대안으로 **마이그레이션 정리** 옵션을 사용하지 마십시오. **구성** 페이지의 ER 구성 삭제 옵션이 실패한 경우에만 **마이그레이션 정리** 옵션을 사용하십시오.
>
> 참조된 템플릿을 Blob 저장소에서 사용할 수 있을 때 **마이그레이션 정리** 옵션을 사용하여 ER 형식 구성을 삭제하는 경우 애플리케이션 데이터베이스에서 관련 구성 아티팩트만 삭제합니다. Blob Storage에 있는 템플릿의 실제 파일은 그대로 유지됩니다. Blob Storage의 파일 덮어쓰기는 더 이상 허용되지 않습니다. 자세한 내용은 [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217)을 참조하십시오. 또한 이 환경에서 마이그레이션 정리를 사용하여 삭제된 구성을 더 이상 다시 가져올 수 없습니다. 이 문제를 해결하려면 Blob Storage에서 해당 파일을 찾아 수동으로 삭제해야 합니다.

[![ER 형식 가져오기.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

애플리케이션 인스턴스를 마이그레이션 대상으로 두 번 이상 사용하고 Blob 저장소에 이미 ER 템플릿 파일이 포함된 다른 위치로 마이그레이션하는 경우 유사한 문제가 발생할 수 있습니다.

여러 ER 형식 구성을 가질 수 있기 때문에 이 프로세스는 시간이 많이 걸릴 수 있습니다. 따라서 [ER 템플릿의 백업 저장소](er-backup-storage-templates.md) 기능을 사용하여 참조가 끊어진 템플릿을 자동으로 복구하는 것이 좋습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]