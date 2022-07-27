---
title: 구독 판매 가격
description: 구독을 만들 때 판매 가격은 판매 가격(구독) 양식에서 만든 판매 가격 설정에서 파생됩니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd63fc290263babafabd6e29441f008d0cf10e13
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448261"
---
# <a name="subscription-sales-prices"></a>구독 판매 가격

[!include [banner](../includes/banner.md)]

구독을 만들 때 판매 가격은 **판매 가격(구독)** 양식에서 만든 판매 가격 설정에서 파생됩니다.

**판매 가격(구독)** 양식에서 특정 구독에 대한 판매 가격을 생성하거나 보다 광범위하게 적용되는 판매 가격을 생성할 수 있습니다. 구독에 적용되는 판매 가격의 경우 구독의 기간 코드 및 통화는 판매 가격의 기간 코드 및 통화와 동일해야 합니다.

구독 및 판매 가격에 대한 기간 코드 및 통화가 동일한 경우 구독 판매 가격은 다음 표에 나열된 우선 순위에 따라 선택됩니다. 테이블의 빈 셀은 빈 필드를 나타내고 X는 트랜잭션이 생성된 구독의 값과 동일한 값을 나타냅니다.

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
<th><p>우선 순위</p></th>
<th><p><strong>카테고리</strong></p></th>
<th><p><strong>프로젝트 ID</strong></p></th>
<th><p><strong>구독</strong></p></th>
<th><p><strong>판매 통화</strong></p></th>
<th><p><strong>기간 코드</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

구독료가 생성되면 위의 표와 같이 가장 세부적인 수준의 판매 가격이 구독 판매 가격으로 선택됩니다.

## <a name="update-and-index-subscription-sales-prices"></a>구독 판매 가격 업데이트 및 색인 생성

기본 가격 또는 인덱스를 업데이트하여 구독 판매 가격을 업데이트할 수 있습니다. 백분율 또는 새 값으로 업데이트할 수 있습니다.

## <a name="subscription-fee-sales-prices"></a>구독 요금 판매 가격

구독료를 생성할 때 판매 가격은 구독의 판매 가격 설정을 기반으로 합니다. 구독 가격 설정의 기본 가격을 사용하거나 색인화된 판매 가격을 생성할 수 있습니다.

## <a name="example"></a>예

새 프로젝트 9030에 대해 EUR 500의 구독 판매 가격을 설정하려고 합니다. **판매 가격(구독)** 양식에서 다음 표에 표시된 대로 구독 판매 가격 라인을 생성합니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>유효 기간 시작</p></th>
<th><p>카테고리</p></th>
<th><p>프로젝트 </p></th>
<th><p>구독</p></th>
<th><p>기간 코드</p></th>
<th><p>판매 통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>개월</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


**범주** 및 **구독** 필드는 비어 있습니다.

그런 다음 아래 구독을 만듭니다.

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
<th><p>서비스 구독</p></th>
<th><p>프로젝트 </p></th>
<th><p>구독 그룹</p></th>
<th><p>카테고리</p></th>
<th><p>통화</p></th>
<th><p>기간 코드</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat1</p></td>
<td><p>EUR</p></td>
<td><p>매월</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>매월</p></td>
</tr>
</tbody>
</table>


이제 구독 그룹 Sub1의 두 구독에 대한 구독 요금을 생성합니다.

1.  **서비스 관리** \> **설정** \> **서비스 구독** \> **구독 그룹** 을 클릭합니다.

2.  **구독 그룹** 양식에서 **기능** \> **구독료 생성** 을 클릭합니다.

3.  **구독료 생성** 양식에 적절한 정보를 입력합니다. 자세한 내용은 [구독료 거래 생성](create-subscription-fee-transactions.md)을 참조하세요.

판매 가격이 EUR 500인 구독료는 다음 표와 같이 두 구독에 대해 생성됩니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>프로젝트 데이터</p></th>
<th><p>서비스 구독</p></th>
<th><p>프로젝트 </p></th>
<th><p>카테고리</p></th>
<th><p>시작일</p></th>
<th><p>종료일</p></th>
<th><p>판매 통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


나중에 프로젝트 9030의 SubCat1 범주에 대한 판매 가격을 지정하기로 결정합니다. 따라서 프로젝트 9030과 수수료 범주 SubCat1의 조합에 대해 판매 가격이 EUR 550인 새 판매 가격 라인을 생성합니다. 이제 다음 표에 표시된 것처럼 프로젝트 9030에 대한 두 개의 구독 판매 가격 라인이 있습니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>유효 기간 시작</p></th>
<th><p>카테고리</p></th>
<th><p>프로젝트 </p></th>
<th><p>구독</p></th>
<th><p>기간 코드</p></th>
<th><p>통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>개월</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2007</p></td>
<td><p>SubCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>개월</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>

위에서 설명한 절차를 반복하여 Sub1 구독 그룹의 두 구독에 대한 구독료를 생성합니다. 다음 표는 구독 그룹에 연결된 각 구독에 대해 생성된 트랜잭션을 보여줍니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>프로젝트 데이터</p></th>
<th><p>구독</p></th>
<th><p>프로젝트 </p></th>
<th><p>카테고리</p></th>
<th><p>시작일</p></th>
<th><p>종료일</p></th>
<th><p>판매 통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-07-2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28-07-2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>

구독 00020\_135에 대한 첫 번째 트랜잭션에서 EUR 550의 판매 가격은 특정 프로젝트와 범주의 조합에 대해 설정된 구독 판매 가격에서 파생됩니다. 구독 00021에 대한 두 번째 트랜잭션에서\_ 135에서 프로젝트 9030과 범주 SubCat2의 조합에 대해 설정된 가격이 없기 때문에 EUR 500의 판매 가격이 프로젝트 구독 판매 가격으로 사용됩니다.

## <a name="see-also"></a>참고 항목

[구독 판매 가격 업데이트 및 색인 생성](update-and-index-subscription-sales-prices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
