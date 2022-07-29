---
title: 재무 Report Designer의 행 정의
description: 행 정의는 재무 보고서의 각 행 내용을 지정하는 보고서 구성 요소 또는 빌딩 블록입니다.
author: aprilolson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e175d1e3de1f5db31de9c4600c8a5935f0cb11a9d39bc0f4e142edf5fc00ce86
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460728"
---
# <a name="row-definitions-in-financial-report-designer"></a>재무 Report Designer의 행 정의

[!include [banner](../includes/banner.md)]

행 정의는 재무 보고서의 각 행 내용을 지정하는 보고서 구성 요소 또는 빌딩 블록입니다. 행 정의를 열 정의, 보고 트리 정의 및 보고서 정의와 결합하여 여러 회사에서 사용할 수 있는 빌딩 블록 그룹을 생성할 수 있습니다.

## <a name="create-a-row-definition"></a>행 정의 만들기

1. Report Designer에서 탐색 창의 **행 정의** 를 클릭합니다.
2. **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **행 정의** 를 클릭합니다. 각 셀의 내용에 대한 자세한 내용은 [행 정의 셀 수정](modify-row-definition-cells-financial-reporting.md)을 참조하세요.

## <a name="open-a-row-definition"></a>행 정의 열기
1. Report Designer에서 탐색 창의 **행 정의** 를 클릭합니다.
2. 열려는 행 정의의 이름을 두 번 클릭합니다.
3. 행 정의와 연결된 빌딩 블록을 보려면 행 정의를 마우스 오른쪽 버튼으로 클릭한 다음 **연결** 을 선택합니다.

## <a name="contents-of-a-row-definition"></a>행 정의의 내용
행 정의는 최대 20,000개의 재무 차원 행을 포함할 수 있으며 다음 정보를 포함할 수 있습니다.

- **현금** 또는 **총 수익** 과 같은 섹션 머리글, 줄 및 공백을 만들어 보고서에 의미를 추가하는 설명 텍스트
- Microsoft Dynamics 365 Finance의 차원 값을 포함할 수 있는 재무 데이터에 대한 링크

    > [!NOTE]
    > 보고서가 생성될 때마다 재무 차원 시스템에서 데이터를 가져오도록 행 정의를 설정할 수 있습니다.

- 연결된 재무 데이터를 기반으로 하는 행 합계 및 공식

일반적으로 행 정의의 각 행에는 다음 유형의 정보 중 하나가 포함됩니다.

- 재무 차원 시스템에 대한 참조
- 데이터를 기반으로 하는 합계 또는 계산
- 서식 지정

행 정의에 정보를 입력하는 방법에는 두 가지가 있습니다.

- 새 행 정의에 행 정보를 수동으로 입력합니다. 자세한 내용은 [행 정의 셀 수정](modify-row-definition-cells-financial-reporting.md)을 참조하세요.
- Report Designer를 사용하여 재무 차원에서 직접 행 정보를 가져옵니다. 자세한 내용은 [행 정의 셀 수정](modify-row-definition-cells-financial-reporting.md)의 "관련 수식/행/단위" 섹션을 참조하세요.

## <a name="add-dimensions-in-a-row-definition"></a>행 정의에 차원 추가
차원은 데이터와 값의 교차점입니다. Report Designer에서 데이터와 값을 그룹화할 수 있습니다. 그런 다음 트랜잭션을 더 자세히 분류하고 분석할 수 있습니다. **차원에서 행 삽입** 대화 상자를 사용하여 행 정의에 동시에 여러 행을 추가할 수 있습니다. 대화 상자에는 각 차원에 대해 하나의 열이 표시됩니다. 다음 표에서는 각 차원에 대해 지정할 수 있는 정보를 설명합니다.

| 옵션                | 설명 |
|-----------------------|-------------|
| 차원             | 행 정의에 추가할 차원을 식별하는 패턴입니다. 이 패턴에는 차원의 각 위치에 대해 하나의 앰퍼샌드(&) 또는 숫자 기호(\#)가 있습니다. 일반적으로 기본 계정 차원에는 모든 앰퍼샌드를 사용하고 다른 차원에는 모든 숫자 기호를 사용합니다. |
| 차원 범위 시작 | 행 정의에 추가할 이 차원의 첫 번째 값입니다. |
| 차원 범위 끝   | 행 정의에 추가할 이 차원의 마지막 값입니다. |

행 정의에 차원을 추가하려면 다음 단계를 따르세요.

1. Report Designer에서 행 정의를 클릭한 다음 수정할 **행 정의** 를 엽니다.
2. **편집** 메뉴에서 **차원에서 행 삽입** 을 클릭합니다.
3. **차원에서 행 삽입** 대화 상자의 **차원** 행에서 정의로 전송할 차원의 셀을 선택한 다음 **모두 &&&** 를 클릭합니다.
4. 행 정의를 차원 값의 특정 범위로 제한하려면 시작 차원 값을 **차원 범위 시작** 셀에 입력한 다음 끝 치수 값을 **치수 범위 끝** 셀에 입력합니다. 선택한 차원의 모든 값을 포함하려면 이 셀을 비워 둡니다.

    > [!NOTE]
    > 차원 범위에서 와일드카드 문자(\* 또는 ?)는 ERP 데이터베이스가 데이터를 조합하는 방식에 따라 원하는 모든 결과를 반환하지 않을 수 있습니다.

5. **시작 행 코드** 필드에서 행 정의에 추가할 첫 번째 차원 값에 대한 행 코드를 지정합니다.
6. **각 행 증분** 필드에서 연속 행 코드 사이의 간격을 지정합니다. 예를 들어 첫 번째 행 코드가 100이고 증분 값이 30이면 첫 번째 새 행의 코드는 100, 130, 160, 190, 220입니다. 새 형식 및 공식 행을 삽입하기에 충분한 공간을 제공하는 증분 값을 사용합니다.
7. **확인** 을 클릭합니다. 선택한 각 차원 값에 대해 행 정의에 하나의 행이 추가됩니다.

## <a name="adjust-rounding-in-a-row-definition"></a>행 정의에서 반올림 조정
금액이 반올림된 대차대조표가 있는 경우 합계가 균형을 이루지 않을 수 있습니다. 예를 들어 대차 대조표 보고서에서 반올림 옵션을 사용하고 보고서 정의에서 반올림을 지정하는 경우 이 문제가 발생할 수 있습니다. 행 정의에서 **반올림 조정** 옵션을 사용하여 대차대조표 금액의 균형을 맞출 수 있습니다. 보고서 정의의 **설정** 탭에서 반올림을 끄거나 수정할 수 있습니다. 다음 표는 금액이 반올림되는 방법을 보여줍니다. 이 테이블에서 100행과 200행의 합계는 반올림이 켜져 있을 때 다릅니다.

| 행 코드 | 반올림하지 않은 금액 | 천 단위로 반올림한 금액 |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| 합계    | 7,300                    | 8                                       |

대차 대조표에서 반올림을 조정하려면 다음 단계를 따르세요.

1. Report Designer에서 행 정의를 클릭한 다음 수정할 **행 정의** 를 엽니다.
2. **편집** 메뉴에서 **반올림 조정** 을 클릭합니다.
3. **반올림 조정** 대화 상자에서 다음 값을 입력합니다.

    - **반올림 조정 행** – 대차 대조표의 균형을 맞추기 위해 조정해야 하는 행의 행 코드입니다.
    - **총 자산 행** – 총 자산이 포함된 대차대조표의 행에 대한 행 코드.
    - **총 부채 및 지분 행** – 총 부채 및 지분이 포함된 대차대조표의 행에 대한 행 코드.
    - **조정 금액 한도** – 자동 조정의 한계를 지정하는 양의 정수입니다. 이 금액은 실제 반올림 차이의 절대값과 비교됩니다.

    > [!NOTE]
    > 이러한 행 코드는 재무 데이터에 연결되어야 합니다. 즉, 행에는 **재무 차원 링크** 셀의 차원 값이 있어야 합니다. 설명(**DESC**), 계산됨(**CALC**) 또는 합계(**TOT**) 행을 참조하지 **마세요**.

이제 반올림이 켜져 있을 때 대차 대조표의 금액이 균등하게 균형을 이룹니다.

> [!NOTE]
> 보고서 정의에 대해 지정된 **반올림 자릿수** 에 따라 조정 한도가 적용됩니다. 예를 들어 보고서를 천 단위로 반올림하고 **2** 를 **조정 금액 한도** 필드에 입력하면 **반올림 조정 행** 필드의 값이가 2,000 이상 증가하거나 감소할 때 경고 메시지를 받습니다.

## <a name="format-row-and-column-text"></a>행 및 열 텍스트 서식 지정
글꼴을 변경하고 텍스트 서식을 지정하여 보고서 모양을 사용자 정의할 수 있습니다. 다음 섹션에서는 보고서에서 행과 열의 모양을 지정하는 방법에 대해 설명합니다.

### <a name="manage-font-styles"></a>글꼴 스타일 관리

보고서의 글꼴 스타일을 만들고 수정할 수 있습니다. 그런 다음 해당 스타일을 문서나 보고서의 특정 행이나 열에 적용할 수 있습니다.

<table>
<tbody>
<tr>
<td><strong>글꼴 스타일 만들기</strong></td>
<td>
<ol>
<li>Report Designer의 <strong>서식</strong> 메뉴에서 <strong>스타일 및 서식</strong>을 클릭합니다.</li>
<li><strong>스타일 및 서식</strong> 대화 상자에서 <strong>새로 만들기</strong>를 클릭한 다음 새 스타일의 고유한 이름을 입력합니다.</li>
<li>글꼴을 선택한 다음 <strong>확인</strong>을 클릭합니다.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>글꼴 스타일 수정</strong></td>
<td>
<ol>
<li>Report Designer의 <strong>서식</strong> 메뉴에서 <strong>스타일 및 서식</strong>을 클릭합니다.</li>
<li><strong>스타일 및 서식</strong> 대화 상자에서 수정할 스타일을 선택한 다음 <strong>수정</strong>을 클릭합니다.</li>
<li>글꼴을 선택한 다음 <strong>확인</strong>을 클릭합니다.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>글꼴 스타일 적용</strong></td>
<td>
<ol>
<li>Report Designer의 정의 또는 열 정의 또는 머리글과 바닥글에서 하나 이상의 셀을 선택합니다.</li>
<li>도구 모음의 <strong>스타일</strong> 목록에서 글꼴 스타일을 선택합니다.</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>행 텍스트 서식 지정

행 정의에 지정된 형식은 열 정의 및 보고서 정의에 지정된 형식을 재정의합니다. 서식 도구 모음의 컨트롤을 사용하여 텍스트 서식을 수정할 수 있습니다. 이러한 컨트롤은 표준 Microsoft Windows 컨트롤입니다.

1. Report Designer에서 수정할 행 정의를 엽니다.
2. 서식을 지정할 셀을 선택합니다. 여러 셀을 선택하려면 Ctrl 키를 누른 상태에서 셀을 선택합니다.
3. 적용할 형식의 도구 모음 버튼을 클릭합니다. 예를 들어 행을 들여쓰려면 행을 선택한 다음 도구 모음에서 **들여쓰기** ![들여쓰기.](media/indent.gif "들여쓰기") 를 클릭합니다.

### <a name="adjust-columns-while-you-design-reports"></a>보고서를 디자인하는 동안 열 조정

행 정의에서 작업 중인 열을 더 쉽게 볼 수 있도록 열 너비를 조정할 수 있으며 보기 창에서 열을 숨기거나(최소화) 표시할 수도 있습니다. 수정한 내용은 열의 화면 모양에만 영향을 줍니다. 보고서의 열 형식에는 영향을 주지 않습니다.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>보기 창에서 열 너비 변경

1. Report Designer에서 수정할 행 정의를 엽니다.
2. **서식** 메뉴에서 **열 너비** 를 선택합니다.
3. **열 너비** 대화 상자에서 값을 입력한 다음 **확인** 을 클릭합니다. 또는 열 머리글 셀의 오른쪽 경계를 끌어 열 너비를 변경할 수 있습니다.

### <a name="hide-columns-in-the-view-pane"></a>보기 창에서 열 숨기기

1. Report Designer에서 수정할 행 정의를 엽니다.
2. 최소화할 열을 선택합니다.
3. 마우스 오른쪽 버튼을 클릭한 다음 **숨기기** 를 클릭합니다.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>보기 창에 모든 숨겨진 열 표시

1. Report Designer에서 수정할 행 정의를 엽니다.
2. 표시할 최소화된 열을 마우스 오른쪽 버튼으로 클릭한 다음 **숨기기 해제** 를 클릭합니다.


## <a name="additional-resources"></a>추가 리소스

[재무 보고](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]