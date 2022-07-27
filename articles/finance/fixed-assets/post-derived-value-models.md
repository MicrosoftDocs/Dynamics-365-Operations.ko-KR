---
title: 파생된 장부로 게시
description: 이 문서에서는 파생된 장부를 사용하는 방법을 설명합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef0c7b2ad93f4a9c4ff24052c749f7891f9e915d
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451102"
---
# <a name="post-with-derived-books"></a>파생된 장부로 게시

[!include [banner](../includes/banner.md)]

이 문서에서는 파생된 장부를 사용하는 방법을 설명합니다.

파생된 장부가 포함된 장부에 대한 트랜잭션을 게시하면 파생된 장부 트랜잭션이 저널, 구매 주문 또는 자유 텍스트 송장에 자동으로 게시됩니다. 그러나 고정 자산 저널에서 기본 장부 트랜잭션을 준비하는 경우 게시하기 전에 파생 트랜잭션의 금액을 보고 수정할 수 있습니다.
-   판매세, 고객 또는 공급업체 계정과 같은 특정 계정은 주 장부의 게시에 의해 한 번만 업데이트됩니다. 파생된 장부 트랜잭션은 고정 자산 게시 프로필 페이지에서 파생 장부에 대해 정의된 계정에 게시됩니다.
-   종종 파생된 장부의 거래 유형으로는 취득이 종종 사용됩니다. 이는 고정 자산 취득 시점부터 장부 및 파생 장부를 고정 자산에 적용해야 할 때 사용합니다.
-   트랜잭션 유형에 다른 값도 적용할 수 있습니다. 예를 들어, 판매나 처분과 관련하여 주 장부와 파생 장부의 간격이 동일하다면, 모든 고정 자산 트랜잭션 유형을 파생된 장부의 설정에 사용할 수 있습니다.

> [!WARNING]
> 파생된 장부에 게시된 감가상각액은 기본 장부에 게시된 금액과 동일합니다. 장부마다 감가상각 방법이 다를 경우 파생된 프로세스를 사용하여 감가상각 트랜잭션을 생성해서는 안 됩니다. |

## <a name="example"></a>예 
다음 항목에서는 파생된 장부 기능을 사용하여 취득 트랜잭션을 설정하는 방법에 대해 설명합니다.

1.  장부 페이지에서 장부를 만듭니다.
    -   회계 장부: VM 1, 현재 기장 계층
    -   세금 관련 장부: VM2, 세금 기장 계층

2.  VM 1에서 파생된 장부 탭을 클릭합니다. 장부 필드에서 VM 2를 선택하고 트랜잭션 유형 필드에서 취득을 선택합니다.

그러면 장부를 특정 고정 자산에 연결할 수 있습니다. 

장부 VM 1이 있는 고정 자산에 대한 취득이 게시되면 VM 1뿐만 아니라 파생된 장부 VM 2에도 취득이 게시됩니다. 두 고정 자산 장부 상태가 모두 열림으로 업데이트됩니다.

> [!NOTE]                                                                                                         
> 파생된 장부를 사용하지 않는 경우 예약 VM1과 예약 VM2 모두에 대해 고정 자산 취득을 게시해야 합니다.

자세한 내용은 [파생된 장부](derived-books.md)를 참조하십시오.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
