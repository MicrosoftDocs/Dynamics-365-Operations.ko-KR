---
title: 제품 마스터 만들기
description: 사전 정의된 변형에 대한 제품 마스터를 생성합니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e76c367d4aa6c08332371374a26dd6fdbbdb4eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449002"
---
# <a name="create-a-product-master"></a>제품 마스터 만들기

[!include [banner](../../includes/banner.md)]

사전 정의된 변형에 대한 제품 마스터를 생성합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 제품 디자이너를 위한 것입니다.


## <a name="create-a-new-product-master"></a>새 제품 마스터 만들기
1. **탐색 창 > 모듈 > 제품 정보 관리 > 제품 > 제품 마스터** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **제품 번호** 필드에 값을 입력합니다. 번호는 고유해야 합니다. **제품 번호** 필드에서 번호 시퀀스를 설정할 수 있습니다. 이 경우 사용자는 값을 입력할 필요가 없습니다.
4. **제품 이름** 필드에 값을 입력합니다. 설명이 포함된 제품 이름을 입력합니다. 기본값은 검색 이름이지만 사용자가 변경할 수 있습니다.
5. **제품 크기 그룹** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다. 제품 차원 그룹은 4가지 제품 차원 중 제품 변형을 생성하는 데 사용할 수 있는 제품 차원을 결정합니다. 이 예에서는 색상과 크기가 있는 그룹을 사용합니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다. 기본 **구성 기술** 은 '미리 정의된 변형'입니다. 이것은 이 예에서 사용됩니다.
8. **확인** 을 클릭합니다.

## <a name="select-product-dimension-groups"></a>제품 크기 그룹 선택
1. **색상 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. **크기 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="add-dimension-groups"></a>크기 그룹 추가
1. **작업 창** 에서 **제품** 을 클릭합니다.
2. **차원 그룹** 을 클릭하여 드롭 대화 상자를 엽니다.
3. **재고 규모 그룹** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다. 재고 규모는 항목을 보관하고 인벤토리에서 가져오는 방법을 제어하는 데 도움이 됩니다. 예를 들어 재고 규모는 사이트 및 창고를 포함할 수 있습니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. **추적 규모 그룹** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다. 추적 규모 그룹은 제품에 추가할 수 있는 추적 규모를 결정합니다. 예를 들어 일괄 처리 번호와 일련 번호는 재고 항목을 추적하는 데 사용됩니다.
7. 목록에서 원하는 레코드를 찾아 선택합니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
9. **확인** 을 클릭합니다.
10. **저장** 을 클릭합니다.
11. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]