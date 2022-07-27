---
title: Warehouse Management 모바일 앱에 대한 단계 아이콘 및 제목 할당
description: 이 토픽에서는 Warehouse Management 모바일 앱에 대한 신규 또는 사용자 정의 작업 플로우에 대한 단계 아이콘 및 제목을 지정하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a687c26cacc0dbdaf0091b2d26277864553ca1bf
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449977"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱에 대한 단계 아이콘 및 제목 할당

[!include [banner](../includes/banner.md)]

이 토픽에서는 Warehouse Management 모바일 앱에 대한 신규 또는 사용자 정의 작업 플로우에 대한 단계 아이콘 및 단계 제목을 지정하는 방법에 대해 설명합니다.

다음 그림은 Warehouse Management 모바일 앱에서 단계 아이콘과 제목이 어떻게 표시되는지 보여줍니다.

![Warehouse Management 모바일 앱의 단계 아이콘 및 단계 제목 예.](media/step-icon-example.png "Warehouse Management 모바일 앱의 단계 아이콘 및 단계 제목 예.")

## <a name="turn-this-feature-on-or-off"></a>이 기능 켜기 또는 끄기

이 토픽에 설명된 기능을 사용하려면 *새 창고 앱에 대한 사용자 설정, 아이콘 및 단계 제목* 기능이 시스템에 켜져 있어야 합니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 공간에서 *새 창고 앱에 대한 사용자 설정, 아이콘 및 단계 제목* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="standard-step-ids-classes-and-icons"></a>표준 단계 ID, 클래스 및 아이콘

작업 흐름의 각 단계는 단계 ID로 식별되며 각 단계 ID에는 해당하는 단계 클래스가 있습니다. 단계 아이콘과 제목은 각 단계 클래스에 지정됩니다.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>단계 ID 및 단계 클래스

다음 표에는 현재 사용 가능한 모든 단계 ID와 해당 단계 클래스가 나열되어 있습니다. 기본 입력 필드의 제어 이름은 단계 ID로 사용됩니다.

이러한 단계 ID 및 클래스가 사용되는 방법을 보여주는 예는 이 토픽 뒷부분의 [예: 사용자 지정 흐름에 대한 단계 아이콘 및 제목 할당](#example) 섹션에서 `WHSMobileAppStepInfoBuilder.stepId()` 메서드 구현을 참조하세요.

| 단계 ID | 단계 클래스 |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Carrier | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Confirmation | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| PONum | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Potency | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Put | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Qty | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| 중량 | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>사용 가능한 단계 아이콘

시스템에는 사용자 정의 단계에도 사용할 수 있는 표준 단계 아이콘 모음이 포함되어 있습니다. 현재 맞춤 단계 아이콘을 업로드할 수 없습니다. 따라서 항상 표준 단계 아이콘 중 하나를 선택해야 합니다.

다음 표에는 현재 사용 가능한 모든 표준 단계 아이콘과 해당 이름이 나와 있습니다.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="단계 아이콘 정보"><br>정보</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="번호판 또는 항목 단계 아이콘 추가"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="배치 처리 단계 아이콘"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Carrier 단계 아이콘"><br>Carrier</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="공칭 무게 태그 단계 아이콘"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="공칭 무게 태그 무게 단계 아이콘"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="숫자 확인 단계 아이콘"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="체크인 또는 체크아웃 ID 단계 아이콘"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="하위 번호판 단계 아이콘"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="클러스터 ID 단계 아이콘"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="클러스터 위치 단계 아이콘"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="구성 ID 단계 아이콘"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="구성된 필드 단계 아이콘"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="구성 또는 LP 단계 아이콘"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="번호판 ID 단계에서 통합 아이콘"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="번호판 ID 단계로 통합 아이콘"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="컨테이너 유형 단계 아이콘"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="계산 단계 아이콘"><br>Counting</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="계산 이유 코드 단계 아이콘"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="원산지 코드 단계 아이콘"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="처리 단계 아이콘"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="완료 단계 아이콘"><br>완료</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="드라이버 체크인 확인 단계 아이콘"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="드라이버 체크인 ID 단계 아이콘"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="드라이버 체크아웃 ID 단계 아이콘"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="만료 날짜 단계 아이콘"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="필드 단계 아이콘"><br>필드</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="시작 배치 처리 단계 아이콘"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="시작 인벤토리 상태 단계 아이콘"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="ID 특성 단계 아이콘"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="인벤토리 배치 ID 단계 아이콘"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="인벤토리 색상 ID 단계 아이콘"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="인벤토리 위치 단계 아이콘"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="인벤토리 일련 번호 ID 단계 아이콘"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="인벤토리 크기 ID 단계 아이콘"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="인벤토리 상태 ID 단계 아이콘"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="인벤토리 스타일 ID 단계 아이콘"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="인벤토리 버전 ID 단계 아이콘"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="항목 ID 단계 아이콘"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="ITM 컨테이너 ID 단계 아이콘"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="ITM 배송 ID 단계 아이콘"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="칸반 카드 ID 단계 아이콘"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="칸반 또는 카드 ID 단계 아이콘"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="번호판 ID 단계 아이콘"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="로드 ID 단계 아이콘"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="위치 번호판 위치 단계 아이콘"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="위치 또는 번호판 단계 아이콘"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="위치 또는 번호판 확인 단계 아이콘"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="위치 또는 번호판 시작 단계 아이콘"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="위치 또는 번호판 종료 단계 아이콘"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="긴 프로세스 완료 단계 아이콘"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="LP 중단 상위 LP 단계 아이콘"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="병합 컨테이너 ID 단계 아이콘"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="혼합 번호판 라인 번호 단계 아이콘"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="아웃바운드 가중치 단계 아이콘"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="소유자 단계 아이콘"><br>담당자</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="상위 번호판 단계 아이콘"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="단계 아이콘을 확인하세요."><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="구매 주문 라인 번호 단계 아이콘"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="구매 주문 번호 단계 아이콘"><br>PONum</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="위치 전체 단계 아이콘"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="효능 단계 아이콘"><br>Potency</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="프린터 이름 단계 아이콘"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="생산 ID 단계 아이콘"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="제품 확인 단계 아이콘"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="배치 아이콘 정보"><br>Put</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="보관 클러스터 ID 단계 아이콘"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="수량 단계 아이콘"><br>Qty</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="수량 조정 단계 아이콘"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="수량 부족 단계 아이콘"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="소비할 수량 단계 아이콘"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="보관할 수량 단계 아이콘"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="폐기할 수량 단계 아이콘"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="수량 확인 단계 아이콘"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="완료됨으로 보고 최종 작업 단계 아이콘"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="수신 위치 ID 단계 아이콘"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="컨테이너 ID 단계 제거 아이콘"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="RMA 번호 단계 아이콘"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="주문 단계 선택 아이콘"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="단기 선택 이유 단계 아이콘"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="정렬 취이 ID 단계 아이콘"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="대상 번호판 ID 단계 아이콘"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="대상 라인 번호 단계 아이콘"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="대상 위치 단계 아이콘"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="대상 번호 단계 아이콘"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="대상 창고 단계 아이콘"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="운송 로드 ID 단계 아이콘"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="공급업체 배치 ID 단계 아이콘"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="웨이브 레이블 ID 단계 아이콘"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="웨이브 레이블 수량 단계 아이콘"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="무게 단계 아이콘"><br>중량</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="소비할 무게 단계 아이콘"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="WHS 조정 유형 단계 아이콘"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="WHS 수신 예외 단계 아이콘"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="WMS 위치 ID 단계 아이콘"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="작업 ID 단계 아이콘"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="취소할 작업 ID 단계 아이콘"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="작업 번호판 ID 단계 아이콘"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="작업 번호판 ID 보관 클러스터 단계 아이콘"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="작업 풀 ID 단계 아이콘"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="지역 ID 단계 아이콘"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>예: 사용자 정의 흐름에 대한 단계 아이콘 및 제목 할당

이 예에서는 사용자 정의 작업 흐름에 대한 단계 아이콘 및 제목을 설정하는 방법을 설명합니다. 이 시나리오는 [창고 모바일 앱 사용자 지정](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app) 블로그 게시물에서 더 자세히 설명하고 탐색하는 사용자 지정 작업 흐름의 예를 기반으로 합니다. 작업 흐름은 다음과 같은 방식으로 작동합니다.

1. 앱은 작업자에게 컨테이너 ID를 제공하라는 메시지를 표시하는 페이지를 표시합니다(예: 바코드 스캔).
1. 컨테이너 ID가 유효한 경우 앱은 작업자에게 무게를 묻는 새 페이지를 엽니다. (컨테이너 ID가 유효하지 않은 경우 작업자는 첫 페이지로 돌아갑니다.)
1. 작업자가 유효한 무게를 입력하면 시스템은 무게를 저장하고 작업자를 첫 번째 페이지로 되돌립니다.

다음 그림은 이 작업 흐름을 보여줍니다.

![작업 흐름도.](media/step-icons-example-task-flow.png "작업 흐름도")

### <a name="create-a-step-class-for-the-container-input-page"></a>컨테이너 입력 페이지에 대한 단계 클래스 생성

컨테이너 입력 페이지에서는 작업자가 컨테이너 ID를 스캔하거나 입력할 수 있습니다.

![컨테이너 입력 페이지.](media/step-icons-example-container-input.png "컨테이너 입력 페이지")

컨테이너 입력 페이지에서 입력 필드의 컨트롤 이름은 `ContainerId`입니다. 이 컨트롤 이름은 [단계 ID 목록](#step-ids-classes)에 없기 때문에 이를 기반으로 하는 기존 단계를 찾을 수 없습니다. 따라서 단계를 나타내는 단계 클래스를 작성해야 합니다. 다음은 예입니다.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

단계 아이콘의 식별자는 `defaultStepIcon` 클래스 멤버에 저장되고 단계 제목은 `defaultStepTitle` 클래스 멤버에 저장됩니다.

단계 아이콘을 할당하려면 `defaultStepIcon`을 이 토픽 앞부분의 [사용 가능한 단계 아이콘](#step-icons) 섹션에 나열된 아이콘 ID 중 하나로 설정합니다.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>무게 입력에 표준 또는 사용자 정의 단계 아이콘 및 제목 사용

무게 입력 페이지에서는 작업자가 무게를 입력할 수 있습니다.

![무게 입력 페이지.](media/step-icons-example-weight-input.png "무게 입력 페이지")

가중치 입력 페이지에서 입력 필드의 컨트롤 이름은 `Weight`이며, 이는 [단계 ID 목록](#step-ids-classes)에 있습니다. 따라서 `WHSMobileAppStepWeight` 클래스에 정의된 단계 아이콘과 제목이 허용되는 경우 이 단계에 대해 아무 것도 변경할 필요가 없습니다.

그러나 이 단계에서 다른 아이콘이나 제목을 사용하려는 경우 빌더 클래스에서 `stepId()` 메서드나 `stepInfo()` 메서드를 재정의할 수 있습니다. 각 작업 흐름에는 고유한 단계 정보 작성기가 있습니다.

#### <a name="override-the-stepid-method"></a>stepId() 메서드 재정의

다음 예제에서는 `stepId()` 메서드를 재정의하여 빌더 클래스를 수정할 수 있는 한 가지 방법을 보여 줍니다.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

그런 다음 `NewWeight` 단계에 대한 단계 클래스를 만듭니다. 코드는 이 항목의 앞부분에 표시된 `ContainerId` 예제의 코드와 유사해야 합니다.

#### <a name="override-the-stepinfo-method"></a>stepInfo() 메서드 재정의

다음 예제에서는 `stepInfo()` 메서드를 재정의하여 빌더 클래스를 수정할 수 있는 한 가지 방법을 보여 줍니다.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

그런 다음 `WHSMobileAppStepInfo` 개체를 만들고 아이콘 및/또는 제목을 직접 설정합니다.

## <a name="additional-resources"></a>추가 리소스

- [Warehouse Management 모바일 앱 설치 및 연결](install-configure-warehouse-management-app.md)
- [모바일 디바이스 사용자 설정](mobile-device-user-settings.md)
