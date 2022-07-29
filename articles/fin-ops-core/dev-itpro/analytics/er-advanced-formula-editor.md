---
title: 전자 보고 고급 수식 편집기
description: 이번에는 고급 수식 편집기를 사용하여 전자 보고(ER) 모델 매핑 및 형식 구성 요소에서 식을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58d7a936f94e1cd453c904ef6404e0db65083c54235c8420b9cfa561bcde1584
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460757"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>전자 보고 고급 수식 편집기

[!include [banner](../includes/banner.md)]

[전자 보고](general-electronic-reporting.md) [공식 편집기](general-electronic-reporting-formula-designer.md) 외에도 고급 전자 보고 공식 편집기를 사용하여 전자 보고(ER) 표현식 구성 환경을 개선할 수 있습니다. 고급 편집기는 브라우저 기반이며 [Monaco 편집기](https://microsoft.github.io/monaco-editor)로 구동됩니다. 이번에는 가장 일반적으로 사용되는 고급 편집기 기능에 대해 설명합니다.

- [코드 자동 서식 지정](#Autoformatting)
- [인텔리센스](#IntelliSense)
- [코드 완성](#CodeCompletion)
- [코드 탐색](#CodeNavigation)
- [코드 구조화](#CodeStructuring)
- [찾기 및 바꾸기](#FindAndReplace)
- [데이터 붙여넣기](#DataPasting)
- [구문 색상화](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">고급 수식 편집기 활성화</a>

Microsoft Dynamics 365 Finance 인스턴스에서 고급 수식 편집기를 사용하려면 다음 단계를 완료하십시오.

1.  **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2.  **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3.  **사용자 매개 변수** 대화 상자의 **실행 추적** 섹션에서 **고급 수식 편집기 사용** 매개 변수를 **예** 로 설정합니다.

[![사용자 매개 변수 대화 상자, 고급 수식 편집기 매개 변수 활성화가 강조표시되었습니다.](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> 이 매개 변수는 사용자와 회사에 따라 다릅니다.

Microsoft Dynamics 365 Finance 버전 10.0.19부터 기본적으로 제공되는 ER 수식 편집기를 제어할 수 있습니다. 현재 Finance 인스턴스의 모든 사용자 및 회사에 대해 고급 수식 편집기를 활성화하려면 다음 단계를 완료하십시오.

1.  **기능 관리** 작업 영역을 엽니다.
2.  ER 고급 수식 편집기를 **목록의 모든 사용자에 대한 기본 편집기로 설정** 기능을 찾아 선택한 다음 **지금 사용** 을 선택합니다.
3.  **조직 관리**  >  **전자 보고**  >  **구성** 으로 이동합니다.
4.  **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
5.  **사용자 매개 변수** 대화 상자에서 **고급 수식 편집기 비활성화** 매개 변수를 찾아 **아니요** 로 설정되어 있는지 확인합니다.

[![사용자 매개 변수 대화 상자, 고급 수식 편집기 매개 변수 비활성화가 강조표시되었습니다.](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> **고급 수식 편집기 사용** 및 **고급 수식 편집기 사용 안 함** 매개 변수의 값은 각 사용자에 대해 별도로 유지되며 **ER 고급 수식 편집기를 모든 사용자의 기본 수식 편집기로 설정** 기능의 상태에 따라 **사용자 매개 변수** 대화 상자에서 제공됩니다.

## <a name=""></a><a name="Autoformatting">코드 자동 서식 지정</a>

여러 행의 코드로 구성된 복잡한 표현식을 작성할 때 새로 입력된 행의 들여쓰기는 이전 행의 들여쓰기를 기반으로 자동으로 수행됩니다. **Tab** 또는 **Shift+Tab** 을 입력하여 줄을 선택하고 들여쓰기를 변경할 수 있습니다.

[![줄 선택 및 들여쓰기 변경을 보여주는 ER 공식 편집기 gif.](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

자동 형식 지정을 사용하면 전체 표현식의 형식을 잘 유지하여 추가 유지 관리를 더 쉽게 만들고 구성된 논리에 대한 이해를 단순화할 수 있습니다.

## <a name=""></a><a name="IntelliSense">인텔리센스</a>

편집기는 표현을 더 빨리 작성하고 오타를 방지하는 데 도움이 되는 단어 완성 기능을 제공합니다. 새 텍스트를 추가하기 시작하면 편집기는 입력한 문자를 포함하는 ER 함수에서 지원되는 함수 목록을 자동으로 제공합니다. **Ctrl+Space** 를 입력하여 구성된 식의 모든 위치에서 IntelliSense를 트리거할 수도 있습니다.

[![IntelliSense 트리거를 보여주는 ER 수식 편집기 gif.](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">코드 완성</a>

편집기는 다음을 통해 자동으로 코드 완성을 제공합니다.

- 여는 대괄호를 입력할 때 닫는 대괄호를 삽입하고 대괄호 안에 커서를 유지합니다.
- 첫 번째 따옴표를 입력할 때 두 번째 따옴표를 삽입하고 커서를 따옴표 안에 유지합니다.
- 첫 번째 큰따옴표를 입력할 때 두 번째 큰따옴표를 삽입하고 커서를 따옴표 안에 유지합니다.

[![코드 완성을 자동으로 제공하는 편집기를 보여주는 ER 공식 편집기 gif.](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

입력된 브래킷을 가리키면 이 쌍의 두 번째 브래킷이 지원하는 구성을 표시하기 위해 자동으로 강조 표시됩니다.

## <a name=""></a><a name="CodeNavigation">코드 탐색</a>

명령 팔레트나 상황에 맞는 메뉴를 사용하여 **이동** 명령을 입력하여 표현식에서 필요한 기호나 선을 찾을 수 있습니다.

예를 들어, **8** 행으로 이동하려면 다음을 수행하십시오.

- **Ctrl+G** 를 누르고 값 **8** 을 입력한 다음 **Enter** 키를 누릅니다.

  또는

- **F1** 키를 누르고 **G** 를 입력하고 **줄로 이동** 을 선택하고 값 **8** 을 입력하고 **Enter** 키를 누릅니다.

[![명령 팔레트를 사용하여 표현식의 일부를 찾는 방법을 보여주는 ER 공식 편집기 gif.](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">코드 구조화</a>

[IF](er-functions-logical-if.md) 또는 [CASE](er-functions-logical-case.md)와 같은 일부 함수의 코드는 자동으로 구조화됩니다. 주의가 필요한 코드 부분에만 집중하기 위해 표현식의 편집 가능한 부분을 줄이기 위해 이 코드의 접는 영역의 일부 또는 전체를 확장 및 축소할 수 있습니다. 이를 위해 접기/펼치기 토글 명령을 사용할 수 있습니다.

예를 들어 모든 영역을 접으려면 다음을 수행하십시오.

- **Ctrl+K** 누르기

  또는

- **F1** 키를 누르고 **FO** 를 누르고 **모두 접기** 를 선택한 다음 **Enter** 키를 누릅니다.

모든 영역을 펼치려면 다음을 수행하십시오.

- **Ctrl+J** 누르기

  또는
  
- **F1** 키를 누르고 **UN** 을 입력하고 **모두 펼치기** 를 선택한 다음 **Enter** 키를 누릅니다.

[![펼쳐진 코드를 보여주는 ER 공식 편집기 gif.](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">찾기 및 바꾸기</a>

특정 텍스트의 발생을 찾으려면 표현식에서 텍스트를 선택하고 다음을 수행하십시오.

- **Ctrl+F** 를 누른 다음 **F3** 을 눌러 선택한 텍스트의 다음 항목을 찾거나 **Shift+F3** 을 눌러 이전 항목을 찾습니다.

  또는
  
- **F1** 키를 누르고 **F** 를 입력한 다음 필요한 옵션을 선택하여 선택한 텍스트를 찾습니다.

특정 텍스트의 발생을 바꾸려면 표현식에서 텍스트를 선택하고 다음을 수행하십시오.

- **Ctrl+H** 를 누릅니다. 현재 표현식에서 선택한 텍스트 또는 이 텍스트의 모든 항목을 바꾸려면 대체 텍스트를 입력하고 바꾸기 옵션을 선택합니다.

  또는
  
- **F1** 키를 누르고 **R** 을 입력한 다음 필요한 옵션을 선택하여 선택한 텍스트를 바꿉니다. 현재 표현식에서 선택한 텍스트 또는 이 텍스트의 모든 항목을 바꾸려면 대체 텍스트를 입력하고 바꾸기 옵션을 선택합니다.

특정 텍스트의 모든 발생을 변경하려면 표현식에서 텍스트를 선택하고 다음을 수행하십시오.

- **Ctrl+F2** 를 누른 다음 대체 텍스트를 입력합니다.

  또는
  
- **F1** 키를 누르고 **C** 를 입력한 다음 필요한 옵션을 선택하여 선택한 텍스트를 변경합니다. 대체 텍스트를 입력합니다.

[![찾기 및 바꾸기를 보여주는 ER 공식 편집기 gif.](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">데이터 소스 및 함수 붙여넣기</a>

데이터 소스 왼쪽 패널에서 현재 선택된 **데이터 소스** 를 현재 표현식에 붙여넣는 **데이터 소스 추가** 를 선택할 수 있습니다. 마찬가지로, **함수** 오른쪽 패널에서 현재 선택된 함수를 현재 표현식에 붙여넣는 **함수 추가** 를 선택할 수 있습니다. ER 수식 편집기를 사용하는 경우 선택한 함수 또는 선택한 데이터 소스는 항상 구성된 표현식의 끝에 붙여넣습니다. 고급 ER 공식 편집기를 사용하면 선택한 함수 또는 선택한 데이터 소스를 구성된 표현식의 어느 부분에나 붙여넣을 수 있습니다. 커서를 사용하여 데이터를 붙여넣을 위치를 지정해야 합니다.

[![데이터 소스 추가 및 함수 붙여넣기를 보여주는 ER 수식 편집기 gif.](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">구문 색상화</a>

현재 다양한 색상이 표현의 다음 부분을 강조 표시하는 데 사용됩니다.

- 텍스트 상수의 레이블 ID를 나타낼 수 있는 이중 괄호 안의 텍스트입니다.

[![ER 공식 편집기.](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>한계

편집기는 현재 다음 웹 브라우저에서 지원됩니다.

- Chrome
- 가장자리
- Firefox
- 오페라
- 원정 여행

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)
- [모나코 에디터](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
