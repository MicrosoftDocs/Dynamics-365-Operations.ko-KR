---
title: Dataverse 통합 구성
description: 이 항목에서는 Microsoft Dataverse 및 Dynamics 365 Human Resources 간의 통합에 관해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4e68142045b72b139bdda8be707a73e21e568fd
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452134"
---
# <a name="configure-dataverse-integration"></a>Dataverse 통합 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dataverse 및 Dynamics 365 Human Resources 간의 통합을 켜고 끌 수 있습니다. 또한 두 환경 간의 데이터 문제를 해결하기 위해 동기화 세부 정보를 보고, 추적 데이터를 지우며, 테이블을 다시 동기화할 수 있습니다.

> [!NOTE]
> Dataverse(이전의 Common Data Service) 및 용어 업데이트에 대한 자세한 내용은 [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)을 참조하세요.

통합을 끄면 사용자가 Human Resources 또는 Dataverse에서 변경할 수 있지만 이러한 변경 사항은 두 환경 간에 동기화되지 않습니다.

기본적으로 Human Resources 및 Dataverse 간의 통합은 꺼져 있습니다.

다음과 같은 상황에서 통합을 끌 수 있습니다.

- 데이터 관리 프레임워크를 통해 데이터를 입력하고 있으며 올바른 상태로 만들려면 데이터를 여러 번 가져와야 합니다.

- Human Resources 또는 Dataverse의 데이터에 문제가 있습니다. 통합을 끄면 한 환경에서 레코드를 삭제하면서 다른 환경에서 삭제하지 않을 수 있습니다. 통합을 다시 켜면 삭제되지 않은 환경의 레코드가 삭제된 환경과 동기화됩니다. 동기화는 다음번 **Dataverse 통합 누락 요청 동기화** 일괄 작업이 실행될 때 시작됩니다.

> [!WARNING]
> 데이터 통합을 끌 때 두 환경에서 동일한 레코드를 편집하지 않도록 하세요. 통합을 다시 켜면 마지막으로 편집한 레코드가 동기화됩니다. 따라서 두 환경에서 레코드를 동일하게 변경하지 않으면 데이터가 손실될 수 있습니다.

## <a name="access-the-dataverse-integration-page"></a>Dataverse 통합 페이지 액세스

1. Dataverse와의 통합을 위한 설정을 보거나 구성하려는 Human Resources 인스턴스에서 **시스템 관리** 타일을 선택합니다.

    [![시스템 관리 타일.](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. **연결** 탭을 선택합니다.

    [![연결 탭.](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. **통합** 탭에서 **Dataverse 구성** 을 선택합니다.

    [![Dataverse 구성 연결.](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Human Resources 및 Dataverse 간의 데이터 통합을 켜거나 끄기

- 통합을 켜려면 **Microsoft Dataverse 통합** 페이지에서 **Dataverse 통합 활성화** 옵션을 **예** 로 설정합니다.

    > [!NOTE]
    > 통합을 켜면 다음번 **Dataverse 통합 누락 요청 동기화** 일괄 작업이 실행될 때 데이터가 동기화됩니다. 일괄 작업이 완료되면 모든 데이터를 사용할 수 있습니다.

- 통합을 끄려면 옵션을 **아니요** 로 설정합니다.

[![Dataverse 통합 켜기 또는 끄기.](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> 데이터 마이그레이션 작업을 수행하는 동안은 Dataverse 통합을 끄는 것이 좋습니다. 대용량 데이터 업로드는 성능에 상당한 영향을 미칠 수 있습니다. 예를 들어 작업자 2,000명을 업로드할 때 통합이 활성화된 경우 몇 시간이 걸릴 수 있지만 비활성화된 경우 1시간 미만이 걸릴 수 있습니다. 이 예에 제시된 수치는 예시용입니다. 레코드를 가져오는 데 걸리는 정확한 시간은 여러 요인에 따라 크게 달라질 수 있습니다.

## <a name="view-data-integration-details"></a>데이터 통합 세부 정보 보기

**Microsoft Dataverse 통합** 페이지의 **관리** 빠른 탭에서 Human Resources와 Dataverse 간에 행이 어떻게 연결되어 있는지 확인할 수 있습니다.

- 테이블의 행을 보려면 **Dataverse 테이블** 필드에서 테이블을 선택합니다. 선택한 테이블에 연결된 모든 행이 그리드에 표시됩니다.

> [!NOTE]
> 현재 모든 Dataverse 테이블이 나열되지는 않습니다. 사용자 지정 필드 사용을 지원하는 테이블만 그리드에 나타납니다. Human Resources의 지속적인 릴리스를 통해 새 테이블을 사용할 수 있습니다.

그리드에는 다음 필드가 포함됩니다.

- **Dataverse 테이블** – Dataverse에 있는 테이블의 이름.
- **Dataverse 테이블 참조** – Dataverse가 레코드를 식별하는 데 사용하는 식별자. 이 값은 Human Resources **RecId** 값과 동일합니다. Microsoft Excel에서 Dataverse 테이블을 열면 식별자를 찾을 수 있습니다.
- **Human Resources 엔터티 이름** – Dataverse에 데이터를 마지막으로 동기화한 Human Resources 엔터티. 엔터티는 Dataverse 접두사 또는 다른 접두사를 가질 수 있습니다.
- **Human Resources 참조** – Human Resources의 레코드와 연결된 **RecId** 값.
- **Dataverse에서 삭제** – Dataverse에서 행이 삭제되었는지 나타내는 값.

> [!NOTE]
> Human Resources의 레코드는 Dataverse의 행에 해당합니다.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Dataverse 행에서 Human Resources 레코드의 연결 제거

Human Resources와 Dataverse 간의 데이터 동기화 중에 문제가 발생할 때 추적을 지우고 추적 테이블을 다시 동기화하면 문제가 해결될 수 있습니다. 연결을 제거한 다음 Dataverse에서 행을 변경하거나 삭제하면 변경 사항이 Human Resources에 동기화되지 않습니다. Human Resources에서 변경 사항을 적용하면 새 추적 레코드가 생성되고 Dataverse에서 행이 업데이트됩니다.

- Human Resources 레코드와 Dataverse 행의 연결을 제거하려면 **Dataverse 테이블** 필드에서 테이블을 선택한 다음 **추적 정보 지우기** 를 선택합니다.

[![추적 정보 지우기.](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

추적을 지운 후 테이블에서 전체 동기화를 실행하려면 다음 절차를 참조하세요.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Human Resources 및 Dataverse 간의 테이블 동기화

다음과 같은 경우 이 절차를 사용하세요.

- Dataverse의 변경 사항이 Human Resources에 나타나는 데 너무 오래 걸립니다.

- 추적을 지운 후에는 추적 테이블을 새로 고쳐야 합니다.

Human Resources 및 Dataverse 간의 테이블을 전체 동기화를 실행하려면 다음을 수행합니다.

1. **Dataverse 테이블** 필드에서 테이블을 선택합니다.

2. **지금 동기화** 를 선택합니다.

[![전체 동기화 실행.](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>참고 항목

[Dataverse 테이블](hr-developer-entities.md)<br>
[Dataverse 가상 테이블 구성](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Human Resources 가상 테이블 FAQ](hr-admin-virtual-entity-faq.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)<br>
[용어 업데이트](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
