---
title: 구독 적립
description: 서비스 구독을 사용하면 수수료 거래를 청구한 날짜 다음 기간에 수동으로 수익이 발생합니다.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d17737c415f6204359dae3ea4b2a0cb4ebb5d65
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449314"
---
# <a name="accruing-subscriptions"></a>구독 적립 

[!include [banner](../includes/banner.md)]


서비스 구독을 사용하면 수수료 거래를 청구한 날짜 다음 기간에 수동으로 수익이 발생합니다.

적립 기간은 구독료에 대해 설정한 송장 기간에 대해 생성되며, 적립 기간은 구독의 기간 코드를 기반으로 합니다.

발생한 수익을 발생 및 취소할 수 있습니다.

## <a name="reverse-accruals-of-credit-amounts"></a>신용 금액의 발생 취소

청구된 구독 금액을 대변에 기입하는 경우 두 가지 방법을 사용하여 발생 금액을 취소할 수 있습니다.

  - 거래에 대한 대변 메모 제안을 생성하기 전에 각 미지급 수익 거래를 개별적으로 취소할 수 있습니다. 수동 방식입니다. (수동)

  - 대변 메모가 전기된 일자 또는 발생의 최초 전기일에 미지급 금액을 취소할 수 있습니다.

자세한 내용은 [구독 매개 변수(양식)](/dynamicsax-2012//subscription-parameters-form)를 참조하세요.

## <a name="setup-requirements"></a>설정 요구 사항

수익을 올리려면 다음 데이터 요구 사항을 충족해야 합니다.

## <a name="account-setup"></a>계정 설정

**WIP - 구독** 및 **미수 수익 - 구독** 계정이 **프로젝트** 모듈에서 설정되어야 합니다.

발생한 수익을 게시할 때 **WIP - 구독** 계정은 발생 금액으로 차변에 기입되며, **미수 수익 - 구독** 계정은 발생 금액으로 적립됩니다.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>구독 수익 발생을 위한 계정 설정

1.  **프로젝트 관리 및 회계** \> **설정** \> **전기** \> **원장 전기 설정** 을 클릭합니다.

2.  **수익 계정** 탭을 클릭하고 **WIP - 구독** 또는 **미수 수익 - 구독** 을 선택하여 계정을 설정합니다.

## <a name="subscription-group-setup"></a>구독 그룹 설정

구독에 대한 수익을 올리려면 **수익 발생** 확인란을 선택해야 합니다. 이는 구독에 연결된 그룹의 **구독 그룹** 양식에 있습니다. **서비스 관리** \> **설정** \> **서비스 구독** \> **구독 그룹** 을 클릭합니다.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>구독 그룹에서 수익 발생 활성화

**서비스 관리** \> **설정** \> **서비스 구독** \> **구독 그룹** 을 클릭합니다.

## <a name="periods"></a>기간

송장 발행 기간 코드를 설정해야 합니다. 송장 발행에 사용하는 것과 동일한 시간 간격으로 수익을 발생시키지 않으려면 발생 기간도 설정해야 합니다.

다음 테이블은 각 송장 발행 기간에 대해 설정할 수 있는 적치휴가 기간에 대한 개요를 제공합니다.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>송장 발행 기간</p></th>
<th><p>적립 기간</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>연도</strong></p></td>
<td><ul>
<li><p><strong>연도</strong></p></li>
<li><p><strong>분기</strong></p></li>
<li><p><strong>개월</strong></p></li>
<li><p><strong>일</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>분기</strong></p></td>
<td><ul>
<li><p><strong>분기</strong></p></li>
<li><p><strong>개월</strong></p></li>
<li><p><strong>일</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>개월</strong></p></td>
<td><ul>
<li><p><strong>개월</strong></p></li>
<li><p><strong>일</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>주</strong></p></td>
<td><ul>
<li><p><strong>일</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>일</strong></p></td>
<td><ul>
<li><p><strong>일</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

송장 발행 기간 설정은 전체 구독 그룹 설정의 필수 부분입니다. 구독 그룹에 대한 적립 기간도 설정할지 여부를 결정할 수 있습니다. 가입 그룹에 대한 적립 기간을 설정한 경우 이 기간은 **기간 코드** 필드에서 추천됩니다. 이 필드는 구독 수익이 발생할 때 **구독 수익 발생** 양식에서 찾을 수 있습니다. 단, 적립 기간은 가입 그룹에 대한 선택적 정보입니다.


> [!NOTE]
> <P>다음 경로를 사용하여 <STRONG>구독 수익 발생</STRONG> 양식을 엽니다. <STRONG>서비스 관리</STRONG> &gt; <STRONG>정기</STRONG> &gt; <STRONG>서비스 구독</STRONG> &gt; <STRONG>구독 수익 발생</STRONG>을 클릭합니다.</P>


## <a name="transactions"></a>트랜잭션

미수 수익을 전기할 때 생성되는 원장 거래의 수를 제어할 수 있습니다. 구독에서 원장 거래를 총계로 생성해야 하는지 라인별로 생성해야 하는지 정의합니다.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>발생한 거래에 대해 표시할 전기 상세 내역 레벨을 지정합니다.

1.  **프로젝트 관리 및 회계** \> **설정** \> **프로젝트 관리 및 회계 매개 변수** 를 클릭합니다.

2.  **재무** 탭의 **청구서** 필드에서 **전체** 또는 **라인** 을 선택합니다.


## <a name="see-also"></a>참고 항목

[구독 수익 발생](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]