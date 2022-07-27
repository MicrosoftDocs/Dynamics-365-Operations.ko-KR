---
title: 서비스 주문 결합
description: 서비스 주문을 결합할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5df9571cb1330489651a28462b747cacd7ac7e46
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449311"
---
# <a name="combine-service-orders"></a>서비스 주문 결합   

[!include [banner](../includes/banner.md)]


**서비스 계약** 양식에서 서비스 주문 라인을 자동으로 생성하는 경우 다음 옵션 중 하나를 선택하여 그룹화 방법을 지정할 수 있습니다.

  - **서비스 계약별**

  - **서비스 작업별**

  - **직원별**

  - **서비스 개체별**

## <a name="example"></a>예

시작 날짜가 03-31-2007인 서비스 계약을 생성합니다. **서비스 주문 결합** 필드에서 **서비스 개체별** 을 지정합니다. 그런 다음 서비스 계약 라인을 만듭니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>계약 라인 번호</p></th>
<th><p>트랜잭션 유형</p></th>
<th><p>설명</p></th>
<th><p>간격</p></th>
<th><p>서비스 개체</p></th>
<th><p>시작일</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>시간</strong></p></td>
<td><p>SAL1</p></td>
<td><p>매주</p></td>
<td><p>X-1</p></td>
<td><p>04-01-2007</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>시간</strong></p></td>
<td><p>SAL2</p></td>
<td><p>격주</p></td>
<td><p>X-2</p></td>
<td><p>04-01-2007</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>시간</strong></p></td>
<td><p>SAL3</p></td>
<td><p>매주</p></td>
<td><p>X-2</p></td>
<td><p>04-01-2007</p></td>
</tr>
</tbody>
</table>


서비스 계약 라인에 대해 기간을 지정하지 않습니다. 따라서 서비스 오더 라인은 해당 라인이 속하는 계산된 날부터 이동하지 않습니다.

다음으로 04-01-2007에서 04-30-2007까지 **서비스 주문 생성** 양식에서 서비스 주문 라인을 생성합니다.

총 10개의 서비스 주문이 만들어집니다. 선택한 결합 설정이 **서비스 게체별** 인 경우, 생성된 모든 서비스 주문에는 하나의 특정 서비스 개체가 있는 서비스 주문 라인만 있습니다. 서비스 계약에서 생성되고 서비스 일자 및 객체가 동일한 서비스 주문 라인은 동일한 서비스 주문에 결합됩니다.


> [!NOTE]
> <P>이 예에서는 <STRONG>서비스 관리 매개 변수</STRONG> 양식에 지정된 일정에 휴무일이 없습니다.</P>



서비스 주문 라인을 서비스 주문으로 추가 그룹화하는 것은 서비스 계약 라인에 지정한 시간 창에 따라 발생합니다.

## <a name="see-also"></a>참고 항목

[자동으로 서비스 주문 생성하기](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]