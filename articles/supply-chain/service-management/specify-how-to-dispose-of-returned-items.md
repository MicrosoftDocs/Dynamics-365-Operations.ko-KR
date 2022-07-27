---
title: 반품 처리 방법 지정
description: 반품 처리 방법을 지정합니다.
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
ms.openlocfilehash: e609c1c285b34a5416a2058809b2fc4fafb73fca
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448405"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>반품 처리 방법 지정

[!include [banner](../includes/banner.md)]

반품 주문을 처리할 때 제품이 반품되는 이유를 식별하기 위해 반품 이유 코드를 지정해야 합니다. 또한 처리 코드와 처리 작업을 지정하여 반품된 제품 자체로 수행해야 할 작업을 결정해야 합니다.

반품 주문을 생성하고, 도착 항목을 등록하거나 포장 전표를 업데이트하고 항목 도착을 검역 주문을 종료할 때 처분 코드를 적용할 수 있습니다.

비즈니스 프로세스를 지원하는 데 필요한 모든 처리 코드를 정의할 수 있습니다. 다음 테이블은 반품 항목 처분을 지정하기 위해 일반적으로 사용되는 코드 세트를 제공합니다.

<table>
<colgroup>
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>처분 유형</p></th>
<th><p>공통 코드</p></th>
<th><p>설명</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>처분</p></td>
<td><p>SC</p></td>
<td><p>스크랩/파기</p></td>
</tr>
<tr class="even">
<td><p>처분</p></td>
<td><p>DC</p></td>
<td><p>자선단체에 기부</p></td>
</tr>
<tr class="odd">
<td><p>처분</p></td>
<td><p>TD</p></td>
<td><p>타사 처분</p></td>
</tr>
<tr class="even">
<td><p>처분</p></td>
<td><p>SL</p></td>
<td><p>구제</p></td>
</tr>
<tr class="odd">
<td><p>처분</p></td>
<td><p>TS</p></td>
<td><p>제3자 판매(2차 시장)</p></td>
</tr>
<tr class="even">
<td><p>수리/수정</p></td>
<td><p>RW</p></td>
<td><p>재작업</p></td>
</tr>
<tr class="odd">
<td><p>수리/수정</p></td>
<td><p>RF</p></td>
<td><p>재생산/개조</p></td>
</tr>
<tr class="even">
<td><p>수리/수정</p></td>
<td><p>MD</p></td>
<td><p>수정</p></td>
</tr>
<tr class="odd">
<td><p>수리/수정</p></td>
<td><p>RP</p></td>
<td><p>수리</p></td>
</tr>
<tr class="even">
<td><p>수리/수정</p></td>
<td><p>RV</p></td>
<td><p>공급업체에 반품</p></td>
</tr>
<tr class="odd">
<td><p>기타</p></td>
<td><p>AI</p></td>
<td><p>그대로 사용</p></td>
</tr>
<tr class="even">
<td><p>기타</p></td>
<td><p>RS</p></td>
<td><p>재판매</p></td>
</tr>
<tr class="odd">
<td><p>기타</p></td>
<td><p>전</p></td>
<td><p>교환</p></td>
</tr>
<tr class="even">
<td><p>기타</p></td>
<td><p>MS</p></td>
<td><p>기타</p></td>
</tr>
</tbody>
</table>


정의하는 각 처분 코드에 대해 처분 작업을 선택해야 합니다. 처분 조치는 처분 코드의 물리적 및 재정적 의미를 결정합니다. 예를 들어, 처분 작업은 반품된 항목의 물리적 처분, 반품된 항목의 재정적 영향 및 교체 항목을 고객에게 보내야 하는지 여부를 결정합니다. 비즈니스 요구 사항에 따라 처분 코드를 무제한으로 정의할 수 있지만 선택할 수 있는 미리 정의된 처분 작업은 6개뿐입니다. 다음 테이블에서는 처분 작업 및 해당 정의를 제공합니다.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>처분 작업</p></th>
<th><p>설명</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>입금</strong></p></td>
<td><p>항목을 인벤토리로 반환하고 고객에게 크레딧을 제공합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>입금만</strong></p></td>
<td><p>반품을 요구하거나 기대하지 않고 고객에게 크레딧을 제공합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>폐기</strong></p></td>
<td><p>항목을 폐기하고 고객에게 크레딧을 제공합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>교체 및 입금</strong></p></td>
<td><p>항목을 인벤토리로 반환하고 교체 주문을 생성한 다음 고객에게 크레딧을 제공합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>교체 및 폐기</strong></p></td>
<td><p>항목을 폐기하고 교체 주문을 생성한 다음 고객에게 크레딧을 제공합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고객에게 반품</strong></p></td>
<td><p>반품된 상품을 거부하고 고객에게 반품합니다.</p></td>
</tr>
</tbody>
</table>

## <a name="select-a-disposition-code-for-a-quarantine-order"></a>검역 명령에 대한 처리 코드 선택

1. **인벤토리 관리** \> **정기** \> **품질 관리** \> **검역 주문** 으로 이동합니다.
1. 기존 검역 명령의 경우 **개요** 탭의 **처분 코드** 필드에서 작업을 선택합니다.

## <a name="see-also"></a>참고 항목

[격리 주문(양식)](/dynamicsax-2012//quarantine-order-form)

[처분 코드(양식)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
