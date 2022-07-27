---
title: 자산 문서
description: 이 항목에서는 자산 관리의 자산 문서에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77b7265b1ba56dbd1cd955f5d90afea02f589ce2eebdd05a2fef3a7ddebc0ee1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446716"
---
# <a name="asset-documents"></a>자산 문서

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리의 자산 문서에 대해 설명합니다.

자산 관리에서 문서가 자동으로 작업 유형, 자산 제조업체, 자산 유형 또는 자산과 관련되도록 설정할 수 있습니다. 이 기능은 업데이트된 문서 버전이 릴리스될 때 유용합니다. 이 경우 업데이트된 문서를 Supply Chain Management 문서에 사용하는 표준 위치에 넣고 생성한 자산 문서 레코드에 문서를 첨부하기만 하면 됩니다. 업데이트된 문서는 **모든 자산**, **활성 자산**, **내 활성 자산**, **모든 작업 주문** 및 **활성 작업 주문 작업** 메뉴 항목에서 액세스할 수 있습니다. 자산 문서 레코드에 문서를 첨부하는 프로세스는 표준 문서 처리 시스템을 사용합니다.

**예시 1:** 작업 유형과 관련된 문서는 해당 작업 유형에 대한 절차를 설명할 수 있습니다.

**예시 2:** 자산 유형, 제조업체 및 모델의 조합과 관련된 문서는 선택한 자산 제조업체 모델에 대한 표준 매뉴얼일 수 있습니다.

## <a name="create-asset-document-relation"></a>자산 문서 관계 생성

1. **자산 관리** \> **설정** \> **자산 문서** 를 선택합니다.
2. **새로 만들기** 를 선택하여 자산 문서 레코드를 생성합니다.
3. 문서 관계의 구체적인 정도에 따라 **자산 유형**, **제조업체**, **모델**, **자산**, **작업 유형 범주**, **작업 유형**, **작업 유형 변형** 및 **작업 요구 사항** 필드 중 하나 이상에서 관련 항목을 선택합니다. **작업 유형 변형** 및 **자격 요구 사항** 필드에서 사용할 수 있는 옵션은 **작업 유형** 필드의 선택 항목에 따라 다릅니다.

    > [!NOTE]
    > 시스템이 자산 또는 작업 주문과 관련되어야 하는 문서를 검색할 때 자산 관리는 가능한 일치를 확인하기 위해 모든 자산 문서 레코드를 검토합니다. 항상 가장 구체적인 조합을 먼저 확인합니다. 즉, 자산 관리는 먼저 **작업 요구 사항** 필드와 일치하는지 확인합니다. 일치하는 항목이 없으면 **작업 유형 변형** 필드의 일치 항목이 있는지 확인합니다. 일치하는 항목이 없으면 **작업 유형** 필드 등의 일치 항목이 있는지 확인합니다. **자산 문서** 페이지 레이아웃에서 볼 수 있듯이 이 동작은 가장 구체적인 조합을 찾기 위해 자산 관리가 각 레코드를 오른쪽에서 왼쪽으로 확인하여 일치하는지를 의미합니다. 여러 문서가 자산 또는 작업 주문과 관련될 수 있습니다. 필요에 따라 유지 관리 요청 또는 작업 주문에 대한 서비스 수준을 편집할 수 있습니다.

4. **첨부 파일** 을 선택합니다. 표준 **문서 처리** 페이지가 나타납니다.
5. 자산 문서 레코드에 첨부해야 하는 문서 또는 메모를 설정합니다. 문서를 첨부한 후, **첨부 파일** 필드는 레코드와 관련된 문서의 수를 보여줍니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]