---
title: Report Designer에서 보고서 구성 요소 구성
description: 이 항목에서는 Report Designer에서 기존 보고서, 빌딩 블록 및 개체를 구성하는 방법에 대해 설명합니다.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6b30e7e480edb50bb9509e270806224755f98e38111cda0c1cae86a0f56eb193
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460831"
---
# <a name="organize-report-components-in-report-designer"></a>Report Designer에서 보고서 구성 요소 구성

[!include [banner](../includes/banner.md)]

구성 요소를 디자인하고 보고서를 생성한 후에는 사용자가 더 쉽게 찾을 수 있도록 이러한 개체를 구성하는 것이 좋습니다. 이 도움말에서는 Report Designer에서 기존 보고서, 빌딩 블록 및 개체를 구성하는 방법에 대해 설명합니다.

Report Designer에서 폴더, 보고서, 빌딩 블록 및 기타 개체의 이름을 바꾸어 파일을 구성할 수 있습니다. 이름을 바꾸는 개체 유형에 따라 해당 개체와의 연결을 업데이트해야 할 수 있습니다.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Report Designer에서 폴더 또는 빌딩 블록 이름 바꾸기
Report Designer에서 폴더, 보고서 정의, 행 정의, 열 정의 및 보고 트리 정의의 이름을 바꿀 수 있습니다.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Report Designer에서 폴더 또는 빌딩 블록 이름 바꾸기

1. Report Designer에서 탐색 창을 사용하여 이름을 바꿀 폴더나 개체를 찾습니다.
2. 폴더 또는 개체를 마우스 오른쪽 버튼으로 클릭한 다음 **이름 바꾸기** 를 클릭합니다. 탐색 창의 **이름** 필드를 사용할 수 있게 됩니다.
3. 새 이름을 입력한 다음 Enter 키를 누릅니다.
4. 빌딩 블록이 행 정의, 열 정의 또는 보고 트리 정의인 경우 연관된 다른 빌딩 블록을 업데이트해야 합니다. 3단계에서 이름을 바꾼 빌딩 블록을 마우스 오른쪽 버튼으로 클릭하고 **연결** 을 누른 다음 목록에서 항목을 선택하여 업데이트합니다.
5. 연결된 모든 항목이 업데이트될 때까지 4단계를 반복합니다.

## <a name="create-and-manage-report-groups"></a>보고서 그룹 생성 및 관리
보고서 정의를 그룹화하여 동시에 여러 보고서를 생성할 수 있습니다. 보고서 그룹을 생성, 수정, 삭제하려면 디자이너 또는 관리자의 역할이 있어야 합니다. 생성자 역할이 있는 사용자는 보고서 그룹을 생성할 수 있으며 보고서 그룹에 대한 사용자 보고서 정의 설정을 수정할 수도 있습니다.

### <a name="create-a-report-group"></a>보고서 그룹 만들기

1. Report Designer에서 탐색 창의 **보고서 그룹** 을 클릭합니다.
2. **파일** 메뉴에서 **새로 만들기** &gt; **보고서 그룹 정의** 를 클릭하여 뷰어 창에서 새 보고서 그룹을 엽니다. 또는 **보고서 그룹** 단추 ![보고서 그룹](media/report-group.gif "보고서 그룹")를 클릭합니다. 도구 모음에서.
3. **보고서 그룹** 탭을 클릭합니다. 이 보고서 생성을 위한 개별 보고서 정의에 대한 정보를 무시하려면 **개별 보고서 정의에서 회사, 세부 정보 및 날짜 설정 재정의** 체크박스를 선택합니다. 회사명, 상세수준, 잠정설정, 날짜 정보는 자동으로 입력되지만 업데이트는 가능합니다.
4. 보고 통화를 표시하는 여러 보고서를 생성하려면 **모든 보고 통화 포함** 체크박스를 선택합니다. 그런 다음 보고서를 볼 때 웹 뷰어에서 **통화** 버튼을 클릭하여 여러 보기에 액세스할 수 있습니다.
5. **그룹의 보고서** 필드에서 **추가** 를 클릭하여 보고서 그룹에 포함할 보고서를 선택합니다. 여러 보고서를 선택하려면 **추가** 대화 상자에서 Ctrl 키를 누른 상태에서 보고서를 선택합니다. 보고서 선택을 마쳤으면 **확인** 을 클릭합니다.
6. **파일** &gt; **저장** 을 클릭하여 새 보고서 그룹을 저장합니다.

### <a name="modify-a-report-group"></a>보고서 그룹 수정

1. Report Designer에서 탐색 창의 **보고서 그룹** 을 클릭합니다.
2. 수정할 보고서 그룹을 두 번 클릭합니다.
3. **보고서 그룹** 탭에서 원하는 대로 변경합니다.
4. **파일** 메뉴에서 **저장** 을 클릭하여 수정된 보고서 그룹을 저장합니다. 또는 **저장** 단추 ![저장](media/save.gif "저장")를 클릭합니다. 도구 모음에서.

> [참고] 보고서가 설정된 간격으로 생성되도록 예약한 경우 해당 설정을 무시하고 보고서를 즉시 생성할 수 있습니다.

### <a name="generate-a-report-group-report"></a>보고서 그룹 보고서 생성

1. Report Designer에서 탐색 창의 **보고서 그룹** 을 클릭합니다.
2. 생성할 보고서 그룹을 엽니다.
3. **보고서 생성** 단추 ![보고서 생성](media/generate-report.gif "보고서 생성")를 클릭하여 보고서를 생성합니다.

### <a name="delete-a-report-group"></a>보고서 그룹 삭제

1. Report Designer에서 탐색 창의 **보고서 그룹** 을 클릭합니다.
2. 삭제할 보고서 그룹을 마우스 오른쪽 버튼으로 클릭한 다음 **삭제** 를 선택합니다.
3. 확인 메시지가 나타나면 **네** 를 클릭합니다.

## <a name="report-group-tab-controls"></a>보고서 그룹 탭 컨트롤
다음 표에서는 **보고서 그룹** 탭의 컨트롤에 대해 설명합니다.

<table>
<thead>
<tr>
<th>컨트롤</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>개별 보고서 정의에서 회사, 세부 정보 및 날짜 설정 재정의</td>
<td>이 보고서 생성에 대해서만 이 보고서 그룹에 있는 보고서의 개별 보고서 정의를 무시하려면 이 확인란을 선택합니다.</td>
</tr>
<tr>
<td>회사 이름</td>
<td>보고서에 사용할 회사를 선택합니다.</td>
</tr>
<tr>
<td>상세 수준</td>
<td>보고서에 포함되는 세부 정보 수준을 지정합니다.
<ul>
<li><strong>재무</strong> − 높은 수준의 요약 보고서. &#39;보고 트리를 통해 추가된 계정 및 차원을 제외하고 계정 및 차원으로 드릴다운할 수 없습니다.</li>
<li><strong>재무 &amp; 계정</strong> − 높은 수준의 요약 및 계정 세부 정보가 포함된 보고서.</li>
<li><strong>재무, 계정 &amp; 트랜잭션</strong> − 높은 수준의 요약 및 트랜잭션 세부 정보가 포함된 보고서.</li>
</ul></td>
</tr>
<tr>
<td>공급</td>
<td>보고서에 포함되는 활동의 유형을 지정합니다.
<ul>
<li><strong>게시된 활동만</strong> − 재무 데이터에 게시된 거래 및 잔액만 포함합니다.</li>
<li><strong>게시 및 게시되지 않은 활동</strong> − 재무 데이터에 입력 및 게시된 모든 거래 및 잔액을 포함합니다.</li>
<li><strong>게시되지 않은 활동만</strong> − 재무 데이터에 입력되었지만 아직 게시되지 않은 거래 및 잔액만 포함합니다.</li>
</ul></td>
</tr>
<tr>
<td>모든 보고 통화 포함</td>
<td>Microsoft Dynamics ERP 시스템에 구성된 추가 보고 통화가 여기에 나열됩니다. 표시된 통화로 추가 보고서를 생성하려면 이 확인란을 선택합니다. 웹 뷰어에서 이러한 보고서를 보려면 <strong>통화</strong> 버튼을 누른 다음 통화를 선택합니다.</td>
</tr>
<tr>
<td>보고서 정의와 함께 저장되지 않은 날짜 정보</td>
<td><ul>
<li>기준 기간</li>
<li>기준 연도</li>
<li>적용 기간</li>
</ul>
기본 기준 기간 설정만 보고서 정의와 함께 저장됩니다.</td>
</tr>
<tr>
<td>보고서 정의와 함께 저장되는 날짜 정보</td>
<td><ul>
<li>보고서 날짜</li>
<li>기본 기준 기간</li>
</ul></td>
</tr>
<tr>
<td>그룹의 보고서</td>
<td>보고서 그룹에서 보고서를 추가, 제거 및 재정렬합니다.
<ul>
<li>보고서 그룹에 보고서 정의를 추가하려면 보고서 그룹을 두 번 클릭하여 연 다음 <strong>추가</strong>를 클릭합니다. 보고서 그룹에 포함할 보고서를 선택한 다음 <strong>확인</strong>을 클릭합니다.</li>
<li>보고서 그룹에서 보고서를 제거하려면 보고서를 선택한 다음 <strong>제거</strong>를 클릭합니다.</li>
<li>보고서가 생성되는 순서를 수정하려면 목록에서 보고서를 선택한 다음 <strong>위로 이동</strong> 또는 <strong>아래로 이동</strong>을 클릭합니다.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>추가 리소스

[재무 보고](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]