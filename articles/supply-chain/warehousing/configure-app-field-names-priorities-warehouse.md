---
title: Warehouse Management 모바일 앱의 필드 구성
description: 이 주제에서는 Warehouse Management 모바일 앱에 표시되는 필드의 이름과 우선순위를 정의하고 구성하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8c9c1d921f68538d5b84db16b1e88e28147e6b41
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449551"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱의 필드 구성

[!include [banner](../includes/banner.md)]

이 주제에서는 Warehouse Management 모바일 앱에 표시되는 필드의 이름과 우선순위를 정의하고 구성하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 주제는 창고 관리의 기능에 적용됩니다. 인벤토리 관리의 기능에는 적용되지 않습니다. Warehouse Management 모바일 앱은 창고 작업을 수행하는 데 사용할 수 있는 애플리케이션입니다. 앱에서 사용되는 필드 이름을 정의 및 구성하고 필드 이름을 할당해야 하는 우선 순위를 구성할 수 있습니다. 이 주제에서는 이러한 Warehouse Management 모바일 앱 필드 이름과 우선순위를 정의하고 구성하는 방법 및 사용되는 방법에 대해 설명합니다.

## <a name="configure-warehouse-app-field-names"></a>창고 앱 필드 이름 구성

모바일 디바이스에서 웨어하우징을 사용할 때 메타데이터가 **창고 앱 필드 이름** 페이지의 장치에 표시되는 방식을 구성할 수 있습니다. 새 회사에서 **기본 설정 만들기** 를 선택하여 창고 모바일 디바이스 워크플로에서 사용할 모든 필드 이름을 생성한 다음 선호하는 입력 모드와 입력 유형을 할당합니다. 모든 필드 이름을 생성한 후 다음 입력 옵션을 선택할 수 있습니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>옵션</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>기본 입력 모드</td>
<td>이 옵션은 선택한 필드 이름에 대해 스캐닝 필드 또는 수동 입력 입력 필드를 표시할지 여부를 정의합니다. 이는 필드에 바코드를 사용하는지 여부에 따라 필드를 구분하는 데 유용합니다. <strong>메모:</strong> 기본 입력 모드가 <strong>스캔 중</strong>으로 설정된 필드 이름의 경우 바코드를 읽을 수 없거나 손상된 경우 수동으로 정보를 입력할 수 있습니다.</td>
</tr>
<tr class="even">
<td>입력 유형</td>
<td>이 옵션은 선택한 필드 이름에 사용해야 하는 입력 유형을 정의합니다. 네 가지 옵션을 사용할 수 있습니다.
<ul>
<li><strong>선택</strong> - 선택할 수 있는 옵션 목록이 포함되어 있습니다. 이 옵션이 있는 필드 이름은 편집할 수 없습니다.</li>
<li><strong>날짜</strong> - 날짜로 지정된 필드 이름은 레이블과 함께 날짜 형식을 표시합니다. 이것은 창고 작업자가 날짜를 입력할 형식을 보는 데 도움이 됩니다. 이 옵션이 있는 필드 이름은 편집할 수 없습니다.</li>
<li><strong>알파</strong> - 선택하면 앱에서 수동으로 정보를 입력할 때 장치 키보드가 사용됩니다. 키보드 경험은 사용하는 장치에 따라 변경될 수 있습니다.</li>
<li><strong>숫자</strong> - 숫자 입력만 사용하는 필드 이름의 경우 이 옵션을 선택하여 장치 키보드 대신 입력 필드가 있는 사용자 정의 숫자 키패드를 표시할 수 있습니다.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>창고 앱 필드 우선순위 구성

**창고 앱 필드 우선순위** 페이지에서 필드 이름을 다른 우선 순위 그룹에 넣을 수 있습니다. 이를 통해 창고 작업자가 앱을 사용하여 작업을 수행할 때 기본 작업 페이지에 표시할 정보를 결정할 수 있습니다. **기본 설정 만들기** 를 클릭하면 기본 우선순위 그룹 집합이 생성됩니다. 필요한 만큼 우선순위 그룹을 생성할 수 있지만 작업 페이지에는 세 개의 우선 순위 그룹만 표시됩니다. 시스템이 메타데이터를 앱에 보낼 때 우선순위 그룹에 따라 각 필드에 상대적 우선순위를 할당하고 앱은 작업 페이지의 메타데이터에 포함된 처음 세 개의 우선 순위 그룹을 표시합니다. 나머지 오버플로 메타데이터는 보조 세부정보 페이지에 표시됩니다. 다음 표는 5가지 우선 순위 그룹의 예를 보여줍니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>우선순위 그룹</th>
<th>할당된 필드</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> 우선순위 10</td>
<td><ul>
<li>항목</li>
<li>수량</li>
<li>측정 단위</li>
</ul></td>
</tr>
<tr class="even">
<td> 우선순위 20</td>
<td><ul>
<li>클러스터 위치</li>
<li>클러스터</li>
</ul></td>
</tr>
<tr class="odd">
<td> 우선순위 30</td>
<td><ul>
<li>항목 설명</li>
</ul></td>
</tr>
<tr class="even">
<td> 우선순위 40</td>
<td><ul>
<li>구성</li>
<li>색</li>
<li>크기</li>
<li>스타일</li>
</ul></td>
</tr>
<tr class="odd">
<td> 우선순위 50</td>
<td><ul>
<li>위치</li>
<li>번호판</li>
</ul></td>
</tr>
</tbody>
</table>

예를 들어 창고 작업자가 모바일 디바이스에서 작업을 수행할 때 앱에 표시될 메타데이터가 다음 필드로 구성된 경우:

-   항목
-   수량
-   측정 단위
-   항목 설명
-   크기 및 위치

위 표에 설정된 창고 앱 필드 우선순위에 따라 작업 페이지에 다음 3행의 정보가 표시됩니다.

-   행 1: 항목, 수량, 측정 단위
-   행 2: 항목 설명
-   행 3: 크기

나머지 메타데이터(예: 위치)는 작업 페이지에 표시되지 않고 세부 정보 페이지에 표시됩니다. 자세한 내용을 알아보고 사용자 인터페이스의 예를 보려면 블로그 게시물 [재무 및 운영 발표 - 창고](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/)를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

[Warehouse Management 모바일 앱 설치 및 연결](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]