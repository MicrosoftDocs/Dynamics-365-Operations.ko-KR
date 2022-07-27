---
title: 검수를 통한 반품 접수
description: 검수를 통한 반품을 접수합니다.
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c800c18bbef17baa4b114c960da5ee0faec8a359
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449281"
---
# <a name="take-returned-items-through-inspection"></a>검수를 통한 반품 접수 

[!include [banner](../includes/banner.md)]


1.  **재고 관리** \> **정기** \> **품질 관리** \> **검역 주문** 을 클릭합니다.

2.  검사 중인 반품 품목에 해당하는 주문 라인을 찾습니다.

    > [!NOTE]
    > <P>검역 명령은 단일 품목 번호와 연관될 수 있습니다. 품목 번호가 다른 10개의 품목이 단일 배송으로 반품되어 검역소로 보내지면 10개의 개별 검역 명령이 생성됩니다.</P>

3.  항목을 검사한 후 **처리 코드** 필드에서 항목을 선택하여 해당 항목으로 수행해야 하는 작업과 관련 금융 거래를 처리하는 방법을 나타냅니다. 예를 들면 품목을 재고로 반품하고 고객에게 환불하거나 품목을 폐기하고 고객에게 교체품을 보내거나 신용 없이 고객에게 품목을 반품하는 경우가 있습니다.
    
    > [!NOTE]
    > <P>단일 품목 번호 배치의 여러 반품 품목에 동일한 처분 코드를 할당할 수 없는 경우 검역 명령(<STRONG>기능</STRONG> &gt; <STRONG>분할</STRONG>)을 분할하여 각 하위 배치에 다른 처분 코드를 할당해야 합니다.</P>


4.  검사가 끝나면 **완료로 보고** 를 클릭하여 반품된 품목을 릴리스하고 상품 도착 분개장을 생성합니다. 그런 다음 항목을 받는 사람이나 부서는 재고로 반환될 항목에 대한 분개장을 처리합니다.
    
    –또는–
    
    검역 명령을 종료하고 **인벤토리** 기능 중 하나를 사용하여 항목을 인벤토리로 직접 다시 이동합니다.

5.  변경 내용을 저장하려면 양식을 닫으세요.

## <a name="see-also"></a>참고 항목

[반품 처리 방법 지정](specify-how-to-dispose-of-returned-items.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]