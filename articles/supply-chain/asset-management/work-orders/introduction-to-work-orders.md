---
title: 작업 주문 소개
description: 이 토픽에서는 자산 관리의 작업 주문에 대한 개요를 제공합니다.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3891ea08a484950d8fef57d6229117e90ed93a92ab800f9de3ad82db3aff956d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447052"
---
# <a name="introduction-to-work-orders"></a>작업 주문 소개

[!include [banner](../../includes/banner.md)]



작업 주문은 유지 관리 작업을 관리하고, 필요한 정보를 제공하고, 소비를 등록하는 데 사용됩니다. 각 작업 주문에는 하나 이상의 작업 주문 작업이 포함될 수 있으며 하나 이상의 자산을 각 작업 주문에 연결할 수 있습니다. 각 작업 주문 작업은 자산에 예약된 유지 관리 작업을 정의합니다.

작업 주문은 다음과 같은 방법으로 생성할 수 있습니다.

- "자동 생성" 설정이 켜져 있는 달력 기반 유지 관리 계획의 경우 자동으로 [일정 관리 계획](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md)을 사용.

- "자동 생성" 설정이 켜져 있는 유지 관리 라운드의 경우 [유지 관리 라운드](../preventive-and-reactive-maintenance/maintenance-rounds.md) 예약을 사용하여 자동으로.

- 예방 유지 관리 작업 또는 유지 관리 요청의 경우 [유지 관리 일정](../preventive-and-reactive-maintenance/maintenance-schedule.md)에서.

- 수동으로

- **모든 유지 관리 요청**, **활성 유지 관리 요청** 또는 **내 기능 위치 유지 관리 요청** 페이지에서.

>[!NOTE]
>동일한 자산과 관련된 작업 주문 작업은 동일한 프로젝트 ID와 관련됩니다.

## <a name="all-work-orders"></a>모든 작업 주문

**자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** 을 선택하여 **모든 작업 주문** 목록 페이지를 엽니다. 이 페이지에는 모든 작업 주문과 각 작업 주문과 관련된 일부 정보가 표시됩니다.

아래 그림은 **모든 작업 주문** 목록 페이지의 예를 보여줍니다.

![자료 1.](media/01-work-orders.png)

활성 작업 주문 목록만 보려면 **자산 관리** > **공통** > **작업 주문** > **활성 작업 주문** 을 선택합니다. 

작업자와 관련된 기능 위치에 설치된 자산이 포함된 작업 주문 작업 목록을 보려면 **자산 관리** > **공통** > **작업 주문** > **내 기능 위치 작업 주문 유지 관리 작업** 을 선택합니다. (**작업자** 와 기능 위치 간의 관계는 작업자 페이지에서 설정됩니다. 자세한 내용은 [유지 관리 작업자 및 작업자 그룹](../setup-for-objects/workers-and-worker-groups.md)을 참조하세요.)

다음은 **모든 작업 주문** 페이지를 사용할 수 있는 몇 가지 방법입니다.

- 그리드 보기에서 **작업 주문** 열의 링크를 선택하여 선택한 레코드에 대한 세부 정보 보기를 표시합니다. 그런 다음 **편집** 을 선택하여 편집할 레코드를 열 수 있습니다.

- 세부 정보 보기에서는 작업 주문과 관련된 세부 정보를 봅니다.  

- 세부 정보 보기에서 **라인** 탭을 선택하여 작업 주문 작업의 세부 정보를 보거나 **헤더** 탭을 선택하여 작업 주문의 세부 정보를 봅니다.  

- 페이지 오른쪽에 있는 **관련 정보** 창을 확장하여 선택한 작업 주문과 관련된 추가 정보를 봅니다.

아래 그림은 **모든 작업 주문** 세부 정보 보기의 예를 보여줍니다.

![자료 2.](media/02-work-orders.png)


작업 창의 버튼은 탭으로 구성되어 있습니다. 다음 테이블에서는 자산 관리와 관련된 버튼에 대해 간략하게 설명합니다.



| 버튼 이름                     | 설명                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 편집                            | 선택한 작업 주문을 편집합니다.                                                                                                                                                                                                                                           |
| 신규                             | 새 작업 주문을 만듭니다.                                                                                                                                                                                                                                                  |
| 삭제                          | 선택한 작업 주문을 삭제합니다.                                                                                                                                                                                                                                         |
| 작업 주문 풀                 | 선택한 작업 주문을 작업 주문 풀에 추가하거나 작업 주문 풀에서 제거합니다.                                                                                                                                                                                           |
| 조정                          | 선택한 작업 주문의 예상 시작 및 종료, 서비스 수준, 책임 유지 보수 작업자 또는 책임 유지 보수 작업자 그룹에 대한 정보를 조정합니다.                                                                                                                                     |
| 관련 작업 주문              | 선택한 작업 주문 작업과 관련된 새 작업 주문을 만듭니다. 1차 및 2차 작업 주문을 등록하고자 할 때 유용합니다.                                                                                                                              |
| 작업 주문 복사                 | 기존 작업 주문을 기반으로 새 작업 주문을 만듭니다.                                                                                                                                                                                                               |
| 이벤트 기록                   | 작업 주문에 대한 등록 기록을 봅니다.                                                                                                                                                                                                                |
| 작업 주문 유지 관리 작업 참고 사항                           | 작업 주문에 대한 설명을 작성하거나 메모 또는 비고를 삽입합니다. 먼저 **타임스탬프 추가** 를 선택하여 메모에 사용자 이름과 타임스탬프를 추가합니다. 메모는 **작업 주문** 페이지의 **라인 세부 정보** 빠른 탭에 있는 **설명** 탭에 표시됩니다.         |
| 도구                           | 작업 주문에 필요한 도구 목록을 만듭니다. 도구는 **조직 관리** > **리소스** > **리소스** 에서 리소스로 설정됩니다.                                                                                                      |
| 유지 관리 검사 목록           | 작업 주문에 연결된 자산에 대한 체크리스트를 봅니다.                                                                                                                                                                                                              |
| 자산 결함                     | 자산에 대한 결함 정보를 보거나 등록합니다. 이 정보는 장애 관리에 사용됩니다.                                                                                                                                                                                      |
| 유지 관리 가동 중지 시간            | 작업 주문에 대한 유지 관리 중단 시간을 지정합니다.                                                                                                                                                                                                                               |
| 상태 평가            | 작업 주문에 상태 평가 측정을 등록합니다.                                                                                                                                                                                                             |
| 자산 카운터                 | 자산에 대한 카운터 등록을 생성하거나 봅니다.                                                                                                                                                                                                                     |
| 예측                        | 작업 주문에 대한 예측을 보거나 생성합니다.                                                                                                                                                                                                                               |
| 분개장                        | 작업 주문 분개장을 보거나 생성합니다. 분개 라인은 예측에서 복사할 수 있습니다.                                                                                                                                                                                         |
| 프로젝트 거래            | 자산에 대해 생성된 작업 주문과 관련된 모든 게시된 트랜잭션을 봅니다.                                                                                                                                                                                             |
| 작업 주문 상태 업데이트           | 작업 주문의 수명 주기 상태를 업데이트합니다.                                                                                                                                                                                                                                                |
| 수명 주기 상태 로그                      | 선택한 작업 주문의 수명 주기 상태를 보여주는 로그를 봅니다.                                                                                                                                                                                                                   |
| 자산 문서                | 작업 주문과 관련된 자산에 첨부된 문서 목록을 봅니다. 이러한 문서는 **자산 관리** > **설정** > **자산 문서** 에서 설정됩니다.                                                                                                 |
| 일정                        | 선택한 작업 주문을 예약합니다.                                                                                                                                                                                                                                      |
| 디스패치            | 한 작업자에 대해 선택한 작업 주문을 예약합니다.                                                                                                                                                                                                                        |
| 일정 삭제                 | 선택한 작업 주문에 대한 일정을 삭제합니다.                                                                                                                                                                                                                          |
| 예약된 작업 주문 유지 관리 작업             | **예약된 작업 주문 유지 관리 작업** 목록 페이지를 엽니다.                                                                                                                                                                                                                             |
| 작업 주문 구매 요청 | **작업 주문 구매 요청** 목록 페이지를 엽니다.                                                                                                                                                                                                                 |
| 작업 주문 구매             | **작업 주문 구매** 목록 페이지를 엽니다.                                                                                                                                                                                                                             |
| 비용 관리                    | 작업 주문의 예산 비용과 실제 비용을 비교합니다.                                                                                                                                                                                                                |
| 시간 제어                    | 작업 주문의 예상 시간과 실제 시간을 비교합니다.                                                                                                                                                                                                                |
| 작업 주문 보고서               | 작업 주문 보고서를 인쇄합니다.                                                                                                                                                                                                                                                |
| 작업 주문 소비          | 소비 보고서를 인쇄합니다.                                                                                                                                                                                                                                               |


작업 창의 **작업 주문** 탭에 있는 **프로젝트** 그룹에 있는 버튼은 **프로젝트 관리 및 회계** 모듈의 예측, 분개 및 송장 발행 기능과 관련이 있습니다.

>[!NOTE]
>마스터 스케줄링을 실행할 때 작업 주문에 생성된 예측을 포함하려면 **자산 관리 매개 변수** 페이지에서 선택된 예측 모델을 사용합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]