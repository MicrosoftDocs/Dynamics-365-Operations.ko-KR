---
title: 서비스 상태 및 진행 필드 상호 작용
description: 서비스 주문 양식에서 헤더의 진행률 필드는 전체 서비스 주문의 상태를 반영하고 상태는 개별 서비스 주문 라인의 상태를 보고합니다.
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
ms.openlocfilehash: 0758c370fd1548770d596115b18f133071f3bbc0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447883"
---
# <a name="service-status-and-progress-field-interaction"></a>서비스 상태 및 진행 필드 상호 작용

[!include [banner](../includes/banner.md)]

**서비스 주문** 양식에서 서비스 주문 헤더의 **진행** 필드는 전체 서비스 주문의 상태를 반영하고 **상태** 는 개별 서비스 주문 라인의 상태를 보고합니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>진행률</p></th>
<th><p>라인 1 상태</p></th>
<th><p>라인 2 상태</p></th>
<th><p>라인 3 상태</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>진행 중</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>진행 중</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>진행 중</strong></p></td>
<td><p><strong>생성됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>게시됨</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>게시됨</strong></p></td>
<td><p><strong>게시됨</strong></p></td>
<td><p><strong>게시됨</strong></p></td>
<td><p><strong>게시됨</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>게시됨</strong></p></td>
<td><p><strong>게시됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
<td><p><strong>취소됨</strong></p></td>
</tr>
</tbody>
</table>

모든 라인의 상태가 **생성됨** 인 경우 서비스 주문의 진행이 진행 중입니다. 일부 라인의 상태가 **취소됨** 또는 **전기됨** 인 경우 여전히 처리 중입니다.

서비스 주문의 모든 라인이 **전기됨** 으로 표시된 경우 상태 주문의 진행률은 **전기됨** 입니다. 일부 라인이 **전기됨** 이고 일부가 **취소됨** 인 경우 진행 상황은 여전히 **전기됨** 입니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
