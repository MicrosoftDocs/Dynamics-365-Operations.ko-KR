---
title: 바코드 스캐너용 칸반 전송 보드 지원
description: 칸반 전송 보드는 위젯 바코드 스캐너에서 칸반 작업을 선택, 시작, 완료 및 비우기 위한 스캐너 입력을 지원합니다.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b18aad4dcdbf8c2d18960ae306556c3ea679d622
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447949"
---
# <a name="kanban-transfer-board-support-for-bar-code-scanners"></a>바코드 스캐너용 칸반 전송 보드 지원

[!include [banner](../includes/banner.md)]

칸반 전송 보드는 위젯 바코드 스캐너에서 칸반 작업을 선택, 시작, 완료 및 비우기 위한 스캐너 입력을 지원합니다.

## <a name="registration-modes"></a>등록 모드

**스캐너 등록** 빠른 탭에서 칸반 카드 번호를 스캔하거나 칸반 카드 번호 필드에 번호를 수동으로 입력할 때 동작을 제어하는 등록 모드를 선택할 수 있습니다.

| 등록 모드 설정 | 설명                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| 시작                 | 진행 중인 칸반 전송 작업을 등록합니다.                                                 |
| 완료              | 칸반 전송 작업을 완료된 것으로 등록합니다.                                                   |
| 비어 있음                 | 칸반 카드에서 참조하는 자재 취급 단위를 비어 있는 것으로 등록합니다.              |
| 선택                | 칸반 카드 번호를 등록하고 칸반 목록에서 참조 작업을 자동으로 선택합니다. |

 
## <a name="registration-mode-select"></a>등록 모드 선택

바코드 리더기를 사용하여 작업을 선택하면 칸반 보드의 표시 모드가 변경됩니다. 이 모드에서는 다음 조건이 적용됩니다.

-   스캔한 칸반 작업만 표시됩니다.
-   선택한 작업의 세부 정보는 **세부 정보** 빠른 탭에 표시됩니다.
-   **메시지** 빠른 탭은 선택한 작업에 대한 메시지만 표시합니다.
-   작업 창에서 사용할 수 있는 기능을 사용하여 작업 상태를 변경할 수 있습니다. 칸반 전송 보드는 이 시간 동안 단일 작업만 계속 표시합니다.
-   작업 창에서 **새로 고침**(Shift+F5)을 클릭하여 작업 목록의 정보를 수동으로 업데이트할 수 있습니다. 정보를 새로 고치면 작업 필터에 대한 전체 결과가 다시 표시됩니다.

## <a name="job-status-and-possible-actions"></a>작업 상태 및 가능한 조치
선택한 작업의 상태와 이벤트 칸반에 대해 페깅된 작업의 상태에 따라 작업을 추가로 처리할 수 있는지 여부가 결정됩니다. 다음 테이블에는 이러한 상태 및 작업에 대한 정보가 표시됩니다.
-   작업 또는 작업에서 참조하는 처리 단위에 사용할 수 있는 상태입니다.
-   작업에 대해 수행할 수 있는 각 작업.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>작업 유형</th>
<th>작업 상태 또는 취급 단위 상태</th>
<th>불출 목록 업데이트</th>
<th>시작</th>
<th>등록 업데이트</th>
<th>완료</th>
<th>비어 있음</th>
<th>이벤트 칸반 만들기</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>전송</td>
<td><ul>
<li>계획되지 않음</li>
<li>페깅된 작업이 없거나 페깅된 작업이 완료됨</li>
</ul></td>
<td>예</td>
<td>예</td>
<td>예</td>
<td>예</td>
<td>아니요</td>
<td>예</td>
</tr>
<tr class="even">
<td>전송</td>
<td><ul>
<li>계획되지 않음</li>
<li>페깅된 작업이 완료되지 않음</li>
</ul></td>
<td>예</td>
<td>아니요</td>
<td>예</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="odd">
<td>전송</td>
<td>진행 중</td>
<td>예</td>
<td>아니요</td>
<td>예</td>
<td>예</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="even">
<td>전송</td>
<td>완료됨</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>예</td>
<td>아니요</td>
</tr>
<tr class="odd">
<td>전송 또는 처리</td>
<td>비어 있음</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="even">
<td>전송 또는 처리</td>
<td>칸반 카드를 찾을 수 없음</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="odd">
<td>전송 또는 처리</td>
<td>칸반 카드를 찾았지만 칸반에 지정되지 않음</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="even">
<td>프로세스</td>
<td><ul>
<li>계획되지 않음</li>
<li>준비됨</li>
<li>진행 중</li>
</ul></td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
<tr class="odd">
<td>프로세스</td>
<td>완료됨</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
<td>아니요</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]