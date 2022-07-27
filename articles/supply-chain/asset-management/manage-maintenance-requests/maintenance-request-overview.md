---
title: 유지 관리 요청
description: 이 토픽에서는 자산 관리에서 유지 관리 요청을 관리하는 방법에 대한 개요를 제공합니다.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6d247457b83036dba2fad8fd9f94e04c29a3aa5e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449737"
---
# <a name="maintenance-requests"></a>유지 관리 요청

[!include [banner](../../includes/banner.md)]

유지 관리 요청은 자산에 유지 관리 또는 수리 작업이 필요할 수 있지만 작업 주문을 생성하지 않을 수 있음을 관리자나 계획자에게 알리기 위해 생성되는 메모 또는 선언입니다. 유지 관리 요청의 내용이 유효한 것으로 간주되면 유지 관리 요청을 기반으로 작업 주문을 생성할 수 있습니다.

자산 관리의 모든 자산에 대해 유지 관리 요청을 생성할 수 있습니다. 회사에서 유지 관리 요청을 사용하는 방식에 따라 다양한 유형의 유지 관리 요청을 생성할 수 있습니다. 여기 예시들이 있습니다 :

- 유지 관리 요청
- 메모
- 수정 또는 개선 사항
- 투자
- 디포 수리(이 유형은 유지 관리 또는 수리 작업을 수행 할 수 있도록 다른 위치에서 자산을 수령하고 작업 완료 후 자산을 반환하는 경우 사용합니다.)

## <a name="view-maintenance-requests"></a>유지 관리 요청 보기

유지 관리 요청을 보려면 **자산 관리** \> **공통** \> **유지 관리 요청** \> **모든 유지 관리 요청**, **활성 유지 관리 요청** 또는 **내 기능 위치 유지 관리 요청** 을 선택합니다. 각 목록 페이지에는 유지 관리 요청과 관련된 일부 정보가 표시됩니다.

![유지 관리 요청을 봅니다.](media/01-manage-maintenance-requests.png)

> [!NOTE]
> **내 기능 위치 유지 관리 요청** 목록 페이지를 사용하여 작업자와 관련된 기능 위치 또는 작업자와 관련된 기능 위치에 설치된 자산을 포함하는 유지 관리 요청 목록을 봅니다. (유지 관리 작업자의 기능 위치를 설정하는 방법에 대한 정보는 [유지 관리 작업자 및 작업자 그룹](../setup-for-objects/workers-and-worker-groups.md)을 참조하세요.)
> 
> 고객 계정 정보는 자산 서비스 관리(외부 유지 관리)에서 사용할 수 있지만 자산 관리(내부 유지 관리)에서는 사용할 수 없습니다.

레코드의 세부 정보 보기를 열려면 **모든 유지 관리 요청** 목록 페이지의 그리드 보기에서 **유지 관리 요청** 열의 링크를 선택합니다.

![유지 관리 요청의 세부 정보를 봅니다.](media/02-manage-maintenance-requests.png)

작업 창의 버튼은 탭으로 구성되어 있습니다. 다음 테이블에서는 자산 관리와 관련된 버튼에 대해 간략하게 설명합니다.

| 단추 이름                      | 설명 |
|----------------------------------|-------------|
| 편집                             | 선택한 유지 관리 요청을 편집합니다. |
| 신규                              | 새 유지 관리 요청을 만듭니다. |
| 삭제                           | 선택한 유지 관리 요청을 삭제합니다. |
| 작업 주문 풀                  | 선택한 유지 관리 요청을 작업 주문 풀에 연결합니다. |
| 작업 주문                       | 선택한 유지 관리 요청을 기반으로 작업 주문을 생성합니다. |
| 자산 결함                      | **자산 결함** 을 클릭하면 선택한 유지 관리 요청에 대한 결함 등록을 생성할 수 있습니다. |
| 작업 주문                      | 선택한 유지 관리 요청에 연결된 모든 작업 주문 목록을 표시합니다. |
| 유지 관리 요청 상태 업데이트 | 유지 관리 요청 상태를 업데이트합니다. |
| 수명 주기 상태 로그              | 선택한 유지 관리 요청의 수명 주기 상태를 보여주는 로그를 봅니다. |
| 유지 관리 요청 세부 정보      | 선택한 유지 관리 요청의 세부 정보를 보여주는 보고서를 인쇄합니다. |
| 대출 자산 보내기                  | 선택한 유지 관리 요청에서 선택한 자산에 대한 임시 교체가 되어야 하는 대출 자산을 선택합니다. |
| 대출 자산 반납                | 대출 자산을 반납으로 등록합니다. |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]