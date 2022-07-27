---
title: 타사 제조 실행 시스템과 통합
description: 이 항목에서는 타사 MES(제조 실행 시스템)를 사용하여 Microsoft Dynamics 365 Supply Chain Management를 통합하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8917c9b265bc3df19517f052e28fb7644057cb46
ms.sourcegitcommit: 19f0e69a131e9e4ff680eac13efa51b04ad55a38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2022
ms.locfileid: "8450067"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>타사 제조 실행 시스템과 통합

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management를 사용하는 일부 제조 조직은 Dynamics 365의 기본 기능을 사용하여 기계, 장비 및 인력에 대한 제조 활동을 제어합니다. 그러나 다른 제조 조직, 특히 고급 제조 요구 사항이 있는 조직에서는 대신 타사 MES(제조 실행 시스템)를 사용합니다. 조직은 예를 들어 수직 산업에 맞게 특별히 조정된 타사 MES 솔루션을 선택할 수 있습니다.

통합 솔루션에서 데이터 교환은 완전히 자동화되고 거의 실시간으로 발생합니다. 따라서 데이터는 두 시스템 모두에서 최신 상태로 유지되며 수동 데이터 입력이 필요하지 않습니다. 예를 들어 자재 소비가 MES에 등록되면 통합을 통해 동일한 소비가 Dynamics 365에도 등록됩니다. 따라서 계획 및 판매와 같은 다른 중요한 프로세스에서 최신 재고 기록을 사용할 수 있습니다.

이 솔루션은 Supply Chain Management 사용자가 타사 MES와 통합하는 것을 더 빠르고 쉽고 저렴하게 만듭니다. 다음과 같은 기능을 제공합니다.

- [주요 제조 실행 프로세스](#processes-available-for-mes-integration)를 지원하는 비즈니스 이벤트 및 인터페이스
- 이벤트 처리 내역을 추적하고 실패한 프로세스의 문제를 해결하고 수정할 수 있는 중앙 집중식 대시보드

다음 그림은 통합 솔루션에서 교환되는 비즈니스 이벤트, 프로세스 및 메시지의 일반적인 컬렉션을 보여줍니다.

![일반적인 통합 시나리오.](media/3p-mes-scenario.png "일반적인 통합 시나리오.")

## <a name="turn-on-the-mes-integration-feature"></a>MES 통합 기능 켜기

이 기능을 사용하려면 관리자가 다음 절차에 설명된 대로 시스템에서 이 기능을 켜야 합니다.

1. **시스템 관리 \> 설정 \> 라이선스 구성** 으로 이동합니다.
1. **시간 및 참석률** 라이선스 키가 활성화되었는지 확인하세요(확인 표시가 나타남). 이 라이선스 키는 제조 실행 시스템의 기능과 데이터를 제어하기 때문에 필요합니다. 활성화되어 있지 않으면 다음 단계를 수행하세요.
    1. [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 시스템을 유지 관리 모드로 설정합니다.
    1. **라이선스 구성** 페이지에서 **시간 및 참석률** 확인란을 선택합니다.
    1. [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 유지 관리 모드를 끕니다.
1. **시스템 관리 \> 작업 영역 \> 기능 관리** 로 이동합니다.
1. 다음과 같은 방법으로 나열된 기능을 켭니다([기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 참조).
    - **모듈:** *생산 관리*
    - **기능 이름:** *제조 실행 시스템 통합*

## <a name="processes-available-for-mes-integration"></a>MES 통합에 사용 가능한 프로세스

통합을 위해 다음 프로세스 중 일부 또는 전체를 활성화할 수 있습니다.

| 프로세스 이름 | 설명 |
|---|---|
| 생산 주문 릴리스 및 생산 주문 상태 변경 비즈니스 이벤트 | 이 프로세스는 생산되어야 하는 생산 주문에 대한 정보를 얻기 위해 MES가 청취할 수 있는 비즈니스 이벤트를 제공합니다. 생산 주문과 관련된 참조 데이터는 OData(Open Data Protocol) 또는 데이터 개체를 통해 Supply Chain Management에서 MES로 공유될 것으로 예상됩니다. |
| 생산 주문 시작 | 이 프로세스는 MES를 사용하여 시작되는 생산 주문에 대한 정보를 Supply Chain Management에 제공합니다. 이를 통해 두 시스템 모두 모든 제조 활동에 대한 최신 정보를 볼 수 있습니다. |
| 생산 또는 폐기 수량 보고 | 이 프로세스는 MES를 사용하여 생산 작업에 보고된 상품 및 오류 수량에 대한 정보를 Supply Chain Management에 제공합니다. 이를 통해 작업 현장 감독자는 생산 계획 진행 상황에 대한 최신 정보를 얻을 수 있습니다. |
| 자재 소비 보고 | 이 프로세스는 Supply Chain Management에 소비되는 자재의 양에 대한 MES의 정보를 제공합니다. 계획 및 판매와 같은 다른 중요한 프로세스에서 최신 재고 기록을 사용할 수 있습니다. |
| 작업에 소요된 보고 시간 | 이 프로세스는 Supply Chain Management에 특정 작업에 사용된 시간에 대한 정보를 제공합니다. |
| 생산 주문 종료 | 이 프로세스는 MES가 생산 주문을 *종료됨* 의 최종 상태로 업데이트했음을 Supply Chain Management에 알립니다. 이 상태는 생산 주문에서 더 이상 수량이 생산되지 않음을 나타냅니다. |

## <a name="monitor-incoming-messages"></a>들어오는 메시지 모니터링

시스템으로 들어오는 메시지를 모니터링하려면 **제조 실행 시스템 통합** 페이지를 엽니다. 여기에서 문제를 보고, 처리하고, 해결할 수 있습니다.

## <a name="call-the-api"></a>API 호출

MES 통합 API를 호출하려면 다음 엔드포인트 URL에 대한 `POST` 요청을 보냅니다.

`/api/services/SysMessageServices/SysMessageService/SendMessage`

보내는 요청의 본문은 다음 예와 유사해야 합니다. 필요에 따라 `_companyId`, `_messageType` 및 `_messageContent`의 값을 대체합니다. API가 지원하는 다양한 메시지 유형과 해당 콘텐츠를 디자인하는 방법에 대한 정보는 다음 섹션을 참조하세요.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>API 메시지 유형 및 콘텐츠

이 섹션에서는 MES 통합 API를 통해 교환할 수 있는 각 메시지 유형에 대해 설명합니다.

### <a name="start-production-order-message"></a>생산 주문 시작 메시지

*생산 주문 시작* 메시지의 경우 `_messageType` 값은 `ProdProductionOrderStart`입니다. 다음 표는 이 메시지가 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ProductionOrderNumber` | 필수적인 | 문자열 |
| `StartedQuantity` | 옵션 | 실수 |
| `StartedDate` | 옵션 | 날짜 |
| `AutomaticBOMConsumptionRule` | 옵션 | 열거형(FlushingPrincip \| Always \| Never) |

### <a name="report-as-finished-message"></a>완료로 보고 메시지

*완료로 보고* 메시지의 경우 `_messageType` 값은 `ProdProductionOrderReportFinished`입니다. 다음 표는 이 메시지가 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ProductionOrderNumber` | 필수적인 | 문자열 |
| `ReportFinishedLines` | 필수적인 | 다음 표에 설명된 페이로드가 각각 포함된 행 목록(최소 하나) |

다음 표는 `ProdProductionOrderReportFinished` 메시지의 `ReportFinishedLines` 섹션에 있는 각 행이 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `LineNumber` | 옵션 | 실수 |
| `ItemNumber` | 옵션 | 문자열|
| `ProductionType` | 옵션 | 열거형(MainItem \| Formula \| BOM \| Co_Product \| By_Product \| None), 확장 가능 |
| `ReportedErrorQuantity` | 옵션 | 실수|
| `ReportedGoodQuantity` | 옵션 | 실수|
| `ReportedErrorCatchWeightQuantity` | 옵션 | 실수 |
| `ReportedGoodCatchWeightQuantity` | 옵션 | 실수 |
| `AcceptError` | 옵션 |부울 |
| `ErrorCause` | 옵션 | 열거형(None \| Material \| Machine \| OperatingStaff), 확장 가능 |
| `ExecutedDateTime` | 옵션 | 날짜 시간 |
| `ReportAsFinishedDate` | 옵션 | 날짜 |
| `AutomaticBOMConsumptionRule` | 옵션 | 열거형(FlushingPrincip \| Always \| Never) |
| `AutomaticRouteConsumptionRule` | 옵션 |열거형(RouteDependent \| Always \| Never) |
| `RespectFlushingPrincipleDuringOverproduction` | 옵션 | 부울 |
| `ProductionJournalNameId` | 옵션 | 문자열 |
| `PickingListProductionJournalNameId` | 옵션 | 문자열|
| `RouteCardProductionJournalNameId` | 옵션 | 문자열 |
| `FromOperationNumber` | 옵션 | 정수|
| `ToOperationNumber` | 옵션 | 정수|
| `InventoryLotId` | 옵션 | 문자열 |
| `BaseValue` | 옵션 | 문자열 |
| `EndJob` | 옵션 | 부울 |
| `EndPickingList` | 옵션 | 부울 |
| `EndRouteCard` | 옵션 | 부울 |
| `PostNow` | 옵션 | 부울 |
| `AutoUpdate` | 옵션 | 부울 |
| `ProductColorId` | 옵션 | 문자열|
| `ProductConfigurationId` | 옵션 | 문자열 |
| `ProductSizeId` | 옵션 | 문자열 |
| `ProductStyleId` | 옵션 | 문자열 |
| `ProductVersionId` | 옵션 | 문자열 |
| `ItemBatchNumber` | 옵션 | 문자열 |
| `ProductSerialNumber` | 옵션 | 문자열 |
| `LicensePlateNumber` | 옵션 | 문자열 |
| `InventoryStatusId` | 옵션 | 문자열 |
| `ProductionWarehouseId` | 옵션 | 문자열 |
| `ProductionSiteId` | 옵션 | 문자열 |
| `ProductionWarehouseLocationId` | 옵션 | 문자열 |
| `InventoryDimension1`~`InventoryDimension12` | 옵션 | 문자열 |

12개의 확장 가능한 차원(`InventoryDimension1`에서 `InventoryDimension12`까지)은 사용자 지정이 필요하며 항상 사용되는 것은 아닙니다. 이에 대한 자세한 내용은 [확장을 통해 새 인벤토리 차원 추가](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md)를 참조하세요.

### <a name="material-consumption-picking-list-message"></a>재료 소비(불출 목록) 메시지

*재료 소비(불출 목록)* 메시지의 경우 `_messageType` 값은 `ProdProductionOrderPickingList`입니다. 다음 표는 이 메시지가 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ProductionOrderNumber` | 필수적인 | 문자열 |
| `JournalNameId` | 옵션 | 문자열 |
| `PickingListLines` | 필수적인 | 다음 표에 설명된 페이로드가 각각 포함된 행 목록(최소 하나) |

다음 표는 `ProdProductionOrderPickingList` 메시지의 `PickingListLines` 섹션에 있는 각 행이 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ItemNumber` | 필수적인 | 문자열 |
| `ConsumptionBOMQuantity` | 옵션 | 실수 |
| `ProposalBOMQuantity` | 옵션 | 실수 |
| `ScrapBOMQuantity` | 옵션 | 실수 |
| `BOMUnitSymbol` | 옵션 | 문자열 |
| `ConsumptionInventoryQuantity` | 옵션 | 실수 |
| `ProposalInventoryQuantity` | 옵션 | 실수 |
| `ConsumptionCatchWeightQuantity` | 옵션 | 실수 |
| `ProposalCatchWeightQuantity` | 옵션 | 실수 |
| `ConsumptionDate` | 옵션 | 날짜 |
| `OperationNumber` | 옵션 | 정수 |
| `LineNumber` | 옵션 | 실수 |
| `PositionNumber` | 옵션 | 문자열 |
| `IsConsumptionEnded` | 옵션 | 부울 |
| `ErrorCause` | 옵션 | 열거형(None \| Material \| Machine \| OperatingStaff), 확장 가능 |
| `InventoryLotId` | 옵션 | 문자열 |

### <a name="time-used-for-operation-route-card-message"></a>작업 시간(경로카드) 메시지

*작업 시간(경로카드)* 메시지의 경우 `_messageType` 값은 `ProdProductionOrderRouteCard`입니다. 다음 표는 이 메시지가 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ProductionOrderNumber` | 필수적인 | 문자열 |
| `JournalNameId` | 옵션 | 문자열 |
| `RouteCardLines` | 필수적인 | 다음 표에 설명된 페이로드가 각각 포함된 행 목록(최소 하나) |

다음 표는 `ProdProductionOrderRouteCard` 메시지의 `RouteCardLines` 섹션에 있는 각 행이 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `OperationNumber` | 필수적인 | 정수 |
| `OperationPriority` | 옵션 | 열거형(Primary \| Secondary1 \| Secondary2 \| ... \| Secondary20) |
| `OperationId` | 옵션 | 문자열 |
| `OperationsResourceId` | 옵션 | 문자열 |
| `Worker` | 옵션 | 문자열 |
| `HoursRouteCostCategoryId` | 옵션 | 문자열 |
| `QuantityRouteCostCategoryId` | 옵션 | 문자열 |
| `HourlyRate` | 옵션 | 실수 |
| `Hours` | 옵션 | 실수 |
| `GoodQuantity` | 옵션 | 실수 |
| `ErrorQuantity` | 옵션 | 실수 |
| `CatchWeightGoodQuantity` | 옵션 | 실수 |
| `CatchWeightErrorQuantity` | 옵션 | 실수 |
| `QuantityPrice` | 옵션 | 실수 |
| `ProcessingPercentage` | 옵션 | 실수 |
| `ConsumptionDate` | 옵션 | 날짜 |
| `TaskType` | 옵션 | 열거형(QueueBefore \| Setup \| Process \| Overlap \| Transport \| QueueAfter \| Burden) |
| `ErrorCause` | 옵션 | 열거형(None \| Material \| Machine \| OperatingStaff), 확장 가능 |
| `OperationCompleted` | 옵션 | 부울 |
| `BOMConsumption` | 옵션 | 부울 |
| `ReportAsFinished` | 옵션 | 부울 |

### <a name="end-production-order-message"></a>생산 주문 종료 메시지

*생산 주문 종료* 메시지의 경우 `_messageType` 값은 `ProdProductionOrderEnd`입니다. 다음 표는 이 메시지가 지원하는 필드를 보여줍니다.

| 필드 이름 | 상태 | 형식 |
|---|---|---|
| `ProductionOrderNumber` | 필수적인 | 문자열 |
| `ExecutedDateTime` | 옵션 | 날짜 시간 |
| `EndedDate` | 옵션 | 날짜 |
| `UseTimeAndAttendanceCost` | 옵션 | 부울 |
| `AutoReportAsFinished` | 옵션 | 부울 |
| `AutoUpdate` | 옵션 | 부울 |

## <a name="receive-feedback-about-the-state-of-a-message"></a>메시지 상태에 대한 피드백 받기

MES가 Supply Chain Management에 메시지를 보낸 후 Supply Chain Management가 메시지 상태에 대한 피드백을 반환하는 것과 관련이 있을 수 있습니다. 다음은 이 동작이 관련될 수 있는 몇 가지 사례입니다.

- MES 통합을 지속적으로 감독할 책임이 있는 사람은 없습니다.
- MES 통합을 감독할 책임이 있는 사람은 메시지가 실패할 때 이메일로 알림을 받아 조치를 취해야 한다는 것을 알고 싶어합니다.
- MES는 작업 현장 운영자 또는 IT 부서의 누군가에게 조치를 취해야 함을 알리기 위해 오류 메시지를 표시해야 합니다.
- MES는 실패 메시지를 수신한 후 주문 일정을 다시 계산해야 합니다(예: 생산 주문 시작 실패).

이러한 경우 Supply Chain Management의 표준 경고 기능을 활용할 수 있습니다. 표준 경고 작동 방식에 대한 자세한 내용은 다음 리소스를 참조하세요.

- 도움말 주제: [경고 개요](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- 동영상: [Dynamics 365 for Finance and Operations의 경고 규칙 옵션](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

예를 들어 다음 경고를 설정하여 메시지 상태에 대한 피드백을 제공할 수 있습니다.

- 메시지가 *실패* 일 때 사용되는 비즈니스 이벤트("외부로 보내기")를 만듭니다.
- IT 관리자 또는 생산 현장 관리자에게 알림 및 이메일을 보냅니다.
