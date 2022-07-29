---
title: 기능 위치 소개
description: 이 토픽에서는 자산 관리의 기능 위치에 대한 개요를 제공합니다.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b0cb76a05f0f19d3e57d1f79751e8bc5870b3c331aa4d1c37ec8dfde0a3c6d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447190"
---
# <a name="introduction-to-functional-locations"></a>기능 위치 소개

[!include [banner](../../includes/banner.md)]

 

이 토픽에서는 자산 관리의 기능 위치에 대한 개요를 제공합니다. 기능 위치는 시스템의 기능 단위와 같은 기술 구조의 요소입니다. 기능 위치는 계층적으로 생성되며 여기에 자산을 설치합니다. 회사의 기능 위치 설정은 회사의 요구 사항에 따라 다릅니다.

다음은 기능적 위치를 사용하는 방법에 대한 몇 가지 예입니다.

- **기능** – 기능 위치는 사용자 지향적일 수 있으며 유사한 동작을 가진 자산을 관리하는 데 사용할 수 있습니다.
- **프로세스 관련** – 기능적 위치는 워크플로 지향적일 수 있습니다.
- **공간** – 기능 위치는 지리 위치 또는 사이트를 나타낼 수 있습니다.

각 기능 위치는 자산 관리에서 독립적으로 관리됩니다. 다음은 기능적 위치의 유용한 기능 중 일부입니다.

- 기능 위치 사양을 설정합니다.
- 자산 사양 요구 사항을 설정합니다.
- 예방 및 사후 유지보수를 위한 유지보수 순서를 설정합니다.
- 설치된 자산을 관리합니다.
- 설치된 자산과 관련된 활성 요청 및 작업 주문을 추적합니다.
- 자산에 등록된 결함을 추적합니다.
- 주어진 시간에 기능 위치와 관련된 자산의 유지 관리 비용을 추적합니다.

기능적 위치는 요청, 작업 주문, 결함 등록, 상태 평가, 생산 중지 등록 및 자산 카운터 등록과 관련하여 자산의 추적성을 제공합니다.

> [!NOTE]
> 자산이 수명 동안 다양한 기능 위치에 설치되더라도 비용은 각 위치와 관련될 수 있습니다. 즉, 자산 비용은 항상 자산이 주어진 시간에 설치된 기능적 위치와 관련됩니다.

기능적 위치는 유연하지 **않습니다**. 따라서 기능적 위치 계층 구조를 설정한 후에는 위치를 이동할 수 없습니다. 

기능적 위치 계층 구조를 만든 후 다음 단계는 여기에 자산을 설치하는 것입니다. 자세한 내용은 [기능 위치에 자산 설치](../functional-locations/install-objects-on-functional-locations.md)를 참조하세요.

## <a name="all-functional-locations"></a>모든 기능 위치

Select **자산 관리** \> **공통** \> **기능 위치** \> **모든 기능 위치** 룰 선택하여 **모든 기능 위치** 목록 페이지를 엽니다. 이 페이지는 모든 기능적 위치와 각각과 관련된 일부 정보를 보여줍니다. 활성 기능 위치만 보려면 **활성 기능 위치** 를 선택합니다. 유지 관리 작업자와 관련된 기능 위치에 설치된 자산만 보려면 **내 활성 기능 위치** 를 선택합니다. (이 관계는 **작업자** 페이지에서 설정됩니다. 자세한 내용은 [유지 관리 작업자 및 작업자 그룹](../setup-for-objects/workers-and-worker-groups.md)을 참조하세요.)

**모든 기능 위치** 목록 페이지에서 **기능 위치** 열의 링크를 선택하여 선택한 레코드의 세부 정보를 봅니다. 기능 위치를 편집하려면 **편집** 버튼을 선택합니다. 세부 정보 보기에는 위치와 관련된 세부 정보가 표시됩니다. 또한 오른쪽에 **관련 정보** 창이 포함되어 있습니다. 이 창에는 기능적 위치 계층이 표시됩니다. **관련 정보** 창을 확장 및 축소할 수 있습니다.

작업 창의 버튼은 탭으로 구성되어 있습니다. 다음 테이블에서는 자산 관리와 관련된 버튼에 대해 간략하게 설명합니다.

| 버튼 이름                         | 설명                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| 편집                                | 페이지의 편집 모드와 보기 모드 간에 전환합니다.                                                                                         |
| 신규                                 | 신규 기능 위치를 만듭니다.                                                                                                            |
| 삭제                              | 선택한 기능 위치를 삭제합니다.                                                                                                     |
| 이름 바꾸기                              | 선택한 기능 위치의 이름을 바꿉니다.                                                                                                     |
| 기능적 위치 구조 복사  | 기능 위치 계층을 복사합니다.                                                                                                      |
| 자산 설치                       | 기능 위치에 하위 자산을 포함한 자산을 설치합니다.                                                                        |
| 자산 교체                       | 자산 계층 구조를 기능 위치의 다른 자산 계층 구조로 바꿉니다.                                                         |
| 비용 관리                        | 선택한 기능 위치에 대한 비용 계산을 수행할 수 있는 **기능 위치 비용 관리** 페이지를 엽니다.                |
| 시간 제어                        | 선택한 기능 위치에 대한 시간 계산을 수행할 수 있는 **기능 위치 시간 관리** 페이지를 엽니다.                |
| 자산                              | 선택한 기능 위치와 관련된 자산 목록을 볼 수 있는 **모든 자산** 페이지를 엽니다.                      |
| 요청                            | 선택한 기능 위치와 관련된 요청 목록을 볼 수 있는 **활성 요청** 페이지를 엽니다.               |
| 작업 주문                         | 선택한 기능 위치와 관련된 작업 주문 목록을 볼 수 있는 **활성 작업 주문** 페이지를 엽니다.         |
| 결함                              | 선택한 기능 위치와 관련된 **자산 결함** 등록 목록을 볼 수 있는 자산 결함 페이지를 엽니다. |
| 기능적 위치 상태 업데이트    | 선택한 기능 위치의 단계를 업데이트합니다.                                                                                        |
| 수명 주기 상태 로그                 | 선택한 기능 위치의 단계를 보여주는 로그를 봅니다.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]