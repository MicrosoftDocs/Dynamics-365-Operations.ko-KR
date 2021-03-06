---
title: 기능적 위치 생성
description: 이 토픽에서는 자산 관리에서 기능적 위치를 만드는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5dd5ea59b27c594752ff82428723f3afe555b5f2426a812c70e10b968c920a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447187"
---
# <a name="create-functional-locations"></a>기능적 위치 생성

[!include [banner](../../includes/banner.md)]

 

이 토픽에서는 자산 관리에서 기능적 위치를 만드는 방법에 대해 설명합니다.

기능적 위치 구조를 생성할 때 기능적 위치를 생성한 후에는 원래 위치에서 이동할 수 없습니다. 이는 자산 관리에서 생성을 시작하기 전에 기능 위치의 구조를 신중하게 고려해야 함을 의미합니다. 기능적 위치가 마음에 들지 않으면 아직 사용되지 않은 위치에 한하여 삭제할 수 있습니다.

기능적 위치로 작업하려면 먼저 기능적 위치의 두 "카테고리"를 생성해야 합니다.

- 하위 위치가 없는 *하나의* 기본 기능 위치를 만듭니다. 이 기능적 위치는 새 자산을 생성할 때 자산의 표준 위치로만 사용됩니다.  
- 회사에서 유지 관리 작업을 관리하는 데 필요한 기능적 위치 구조를 만듭니다.

## <a name="create-a-default-functional-location"></a>기본 기능 위치 만들기

기능적 위치를 사용하는 경우 새 자산을 생성할 때 사용할 하나의 기본 위치를 생성하여 시작합니다. 이 기능적 위치는 **자산 관리** > **설정** > **자산 관리 매개변수** > **자산** 링크 > **기본 기능 위치** 필드에서 선택하는 위치입니다. 새 자산을 생성할 때 기본 기능 위치를 사용할 수 있으며 해당 자산에 대한 기능 위치 구조를 아직 설정하지 않았습니다.

1. **자산 관리** > **공통** > **기능적 위치** > **모든 기능 위치** 를 선택합니다.  
2. **모든 기능 위치** 에서 **새로 만들기** 를 선택합니다.
3. **기능적 위치** 필드에 ID(예: "0000" 또는 "기본값")를 입력하여 이것이 특수 기능 위치임을 나타냅니다.
4. **이름** 필드에 기본 기능적 위치의 이름을 삽입합니다.
5. **부모** 필드에서 부모를 선택하지 *마세요*. 이 필드를 비워 둡니다.
6. **기능적 위치 유형** 필드에서 기본 기능 위치에 사용할 기능 위치 유형을 선택합니다. [기능적 위치 유형](../setup-for-functional-locations/functional-location-types.md)에서 기능적 위치 유형을 설정하는 방법에 대한 자세한 내용을 보세요.
7. **확인** 을 선택합니다. 회사에서 사용하는 기능 위치에 자산을 설치할 때까지 새 자산의 임시 위치로만 사용되므로 이 기능 위치에 데이터를 더 추가해서는 안 됩니다.

## <a name="create-functional-locations"></a>기능적 위치 생성

다음 절차에서는 회사에서 유지 관리 관리에 필요한 기능 위치를 만드는 방법에 대해 설명합니다.

1. **자산 관리** > **공통** > **기능적 위치** > **모든 기능 위치** 를 선택합니다. 그리드 보기 또는 세부 정보 보기에서 기능적 위치를 생성할 수 있습니다.
2. **새로 만들기** 단추를 선택합니다.
3. **기능적 위치** 필드에 ID를 입력합니다.
4. **이름** 필드에 기능적 위치의 이름을 삽입합니다.
5. 기능 위치가 구조의 하위 위치인 경우 **부모** 필드에서 상위 위치를 선택합니다.
6. **기능 위치 유형** 필드에서 유형을 선택합니다.
7. **확인** 을 선택합니다.
8. 기능 위치를 선택하고 **편집** 버튼을 클릭하여 추가 정보를 추가합니다.

>[!NOTE]
>기능 위치 수명 주기 상태 설정에 따라 기능 위치에 대한 모든 하위 위치를 만든 다음 자산 설치를 시작하기 전에 기능 위치 수명 주기 상태를 변경해야 할 수 있습니다. [기능 위치에 자산 설치](../functional-locations/install-objects-on-functional-locations.md)에서 자산 설치에 대한 자세한 내용을 보세요. [기능적 위치 수명 주기 상태](../setup-for-functional-locations/functional-location-stages.md)에서 기능적 위치 수명 주기 상태 설정에 대해 자세히 알아보세요.

세부 정보 보기에는 기능 위치에 대한 정보를 추가하고 편집할 수 있는 빠른 탭이 표시됩니다.

## <a name="general-information"></a>일반 정보

이 섹션에서는 기능적 위치 구조의 상위 및 하위 정보에 대한 개요를 제공합니다. **세부 정보** 섹션에서 기능 위치와 관련된 자산 속성, 유지 관리 계획 및 자산의 수를 볼 수 있습니다. **재고** 섹션에서 기능 위치와 관련된 사이트 및 창고를 선택할 수 있습니다. 사이트 및 창고는 작업 주문 항목 예측과 관련하여 사용됩니다. 품목 예측을 생성할 때 자산의 기능적 위치에서 사이트 및 창고 정보가 자동으로 사용됩니다. **수명 주기 상태** 섹션에 기능 위치 수명 주기 상태에 대한 정보가 표시됩니다.

## <a name="installed-assets"></a>설치된 자산

[기능 위치에 자산 설치](../functional-locations/install-objects-on-functional-locations.md)를 참조하여 자산 설치에 대한 자세한 내용을 보세요. 빠른 탭의 **보기** 버튼을 사용하여 빠른 탭에서 더 많은 필드를 볼 수 있습니다. **유효 시작 날짜** 및 **하위 자산** 필드가 그리드에 표시될 수 있습니다.

## <a name="asset-attribute-requirements"></a>자산 특성 요구 사항

이 빠른 탭에서 기능 위치에 설치하는 자산에 대한 특정 속성 요구 사항을 추가할 수 있습니다. 이러한 요구 사항은 정보 제공용입니다. 다른 속성 요구 사항이 있는 자산을 설치하는 것을 막지는 않습니다. **라인 추가** 를 선택하고 특성 유형을 선택합니다. 그런 다음 관련 **값** 을 삽입하고 **임계값 기준** 필드에서 임계값을 선택한 후 레코드를 저장합니다.

## <a name="maintenance-plans-and-maintenance-rounds"></a>유지 관리 계획 및 유지 관리 라운드

여기에서 시작 날짜를 포함하여 기능 위치에 유지 관리 계획 및 유지 관리 라운드를 추가할 수 있습니다. 기능 위치에 설치된 자산에는 다른 유지 관리 계획이 설정되어 있을 수 있습니다. 모든 유지 관리 계획 및 유지 관리 라운드는 기능 위치 및 현재 설치된 자산에 대한 자산 일정 항목을 예약하는 데 사용할 수 있습니다.

>[!NOTE]
>**모든 기능 위치** 세부 정보 보기 > **유지 관리 계획** 빠른 탭에서 유지 관리 계획에 대한 자산 유형, 자산 브랜드 및 자산 모델 설정을 업데이트하면 유지 관리 계획을 예약한 후 해당 기능 위치와 관련된 기존 유지 관리 일정 항목이 자동으로 삭제됩니다. 기능 위치에서 업데이트된 유지 관리 계획 설정에 해당하는 새 일정 항목을 생성하려면 해당 기능 위치에 대해 새 유지 관리 계획 일정을 실행해야 합니다. 

## <a name="address"></a>주소

**주소** 빠른 탭에 기능 위치 주소를 입력합니다. 기능 위치의 주소는 상속됩니다. 즉, 하위 위치에 주소가 정의되지 않은 경우 상위 위치의 주소가 사용됩니다.

## <a name="workers"></a>작업자

이 빠른 탭에서 기능 위치와 관련된 작업자를 추가할 수 있으며 작업자의 기본 위치로 기능 위치를 선택할 수 있습니다. 

## <a name="attributes"></a>특성

이 빠른 탭에서 기능적 위치 특성의 값을 설정할 수 있습니다. 이러한 속성은 기능적 위치와 관련된 속성 또는 특성을 설명하는 데 사용할 수 있습니다(예: 구조적 속성, 건물 유형, 지역 설명 또는 지하 위 또는 아래 위치).

**라인 추가** 를 선택하고 특성 유형을 선택합니다. 다음으로 속성 유형과 관련된 **값** 을 입력하고 레코드를 저장합니다.

## <a name="financial-dimensions"></a>재무 차원

기능 위치에 대한 재무 차원을 선택할 수 있습니다. [기능적 위치 유형](../setup-for-functional-locations/functional-location-types.md)은 기능 위치에서 재무 차원의 자동 업데이트를 허용하도록 설정할 수 있습니다. 즉, 재무 차원에 설치된 자산은 기능 위치에 대한 재무 차원을 자동으로 가져옵니다. 위치에 따라 다른 비용 센터를 원할 때 유용합니다.

**대지**, **창고**, **주소** 및 **재무 차원** 에 관한 데이터가 상위 기능 위치에서 업데이트되는 경우 업데이트 중에 해당 항목을 선택하면 관련 하위 기능 위치가 그에 따라 업데이트될 수 있습니다. 업데이트 옵션을 제공하는 대화 상자가 열립니다.

## <a name="copy-a-functional-location-structure"></a>기능적 위치 구조 복사

회사에 유사한 위치 구조를 가진 여러 기능 위치가 있는 경우 자산 관리의 복사 기능을 사용하여 유사한 위치 계층을 여러 개 빠르게 생성할 수 있습니다. 특정 기능 위치 또는 전체 구조를 복사할 때 새 위치 또는 구조는 복사한 것과 동일한 이름을 갖습니다. 복사 절차가 완료된 후 새 기능 위치에 대해 선택된 기능 위치 수명 주기 상태에서 허용하는 경우 새 기능 위치에서 이름이나 기타 설정을 쉽게 변경할 수 있습니다.

1. **모든 기능 위치** 에서 복사할 기능 위치를 선택합니다. 예를 들어, 하위 위치를 포함한 전체 기능 위치 구조를 복사하려면 상위 위치(상위)를 선택합니다.
2. **기능적 위치 구조 복사** 단추를 선택합니다. 목록 페이지에서 선택한 위치는 **다음에서 복사** 필드에 표시됩니다.
3. **새로운 기능적 위치** 필드에서 새 위치의 이름을 입력합니다.
4. **아래에 붙여넣을 상위** 필드에서 생성하는 위치가 기존 기능 위치 구조의 일부여야 하는 경우에만 상위 ID를 삽입해야 합니다.
5. **확인** 을 클릭합니다. 새로운 기능적 위치 구조는 **모든 기능 위치** 에 표시됩니다.

>[!NOTE]
>기능 위치 구조를 복사하면 새 구조의 기능 위치 수명 주기 상태가 기능 위치에 대해 생성한 "첫 번째 상태"로 설정됩니다. **모든 기능적 위치** 에서 **이름 바꾸기** 및 **삭제** 버튼을 사용하여 기능 위치의 이름을 바꾸거나 삭제할 수 있는지 여부는 기능 위치의 현재 수명 주기 상태에 따라 다릅니다.

## <a name="delete-a-functional-location"></a>기능적 위치 삭제

삭제하려는 기능 위치에 자산이 설치되어 있지 않고 현재 기능 위치 수명 주기 상태에서 허용하는 경우 관련 하위 위치가 있는 기능 위치를 삭제할 수 있습니다.

1. **모든 기능 위치** 에서 삭제할 기능 위치를 선택합니다.
2. 필요한 경우 기능 위치를 기능 위치 삭제를 허용하는 기능 위치 수명 주기 상태로 업데이트합니다.
3. **삭제** 를 선택합니다.

>[!NOTE]
>기능 위치를 삭제할 수 없는 경우 대신 이 목적을 위해 기능 위치 수명 주기 상태를 설정하여 삭제를 처리할 수 있습니다. 예를 들어 활성 단계가 아니어야 하는 "스크랩됨" 또는 "삭제됨" 단계를 **기능적 위치 수명 주기 상태** 양식에서 설정할 수 있습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]