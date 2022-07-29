---
title: 전자 보고(ER) 공식 디자이너
description: 이 항목에서는 전자 보고(ER)의 수식 디자이너를 사용하는 방법에 대한 일반 정보를 제공합니다.
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eec63fb1782c5afed0320eb841b6bfc92af31a691731ef6bac5d00ed442c0dcd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460663"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>전자 보고(ER) 공식 디자이너

[!include [banner](../includes/banner.md)]

이 항목에서는 전자 보고(ER)의 수식 디자이너를 사용하는 방법을 설명합니다. ER에서 특정 전자 문서의 형식을 디자인할 때 수식을 사용하여 문서의 이행 및 형식 요구 사항을 충족하도록 데이터를 변환할 수 있습니다. 이 공식은 Microsoft Excel의 공식과 유사합니다. 수식에서는 텍스트, 날짜 및 시간, 수학, 논리, 정보 및 데이터 유형 변환 함수와 같은 다양한 유형의 함수와 기타 비즈니스 도메인별 함수가 지원됩니다.

## <a name="formula-designer-overview"></a>수식 디자이너 개요

ER은 공식 디자이너를 지원합니다. 따라서 디자인 타임에 런타임에 다음 작업에 사용할 수 있는 식을 구성할 수 있습니다.

- 응용 프로그램 데이터베이스에서 수신되고 ER 형식의 데이터 소스가 되도록 설계된 ER 데이터 모델에 입력해야 하는 데이터를 변환합니다. (예를 들어, 이러한 변환에는 필터링, 그룹화 및 데이터 유형 변환이 포함될 수 있습니다.)
- 특정 ER 형식의 레이아웃 및 조건에 따라 생성 전자 문서로 보내야 하는 형식 데이터입니다. (예를 들어, 요청한 언어나 문화 또는 인코딩에 따라 서식이 지정될 수 있습니다.)
- 전자 문서 작성 프로세스를 제어합니다. (예를 들어, 표현식은 처리 데이터에 따라 형식의 특정 요소 출력을 활성화하거나 비활성화할 수 있습니다. 또한 문서 생성 프로세스를 중단하거나 사용자에게 메시지를 보낼 수 있습니다.)

다음 작업 중 하나를 수행할 때 **수식 디자이너** 페이지를 열 수 있습니다.

- 데이터 소스 항목을 데이터 모델 구성 요소에 바인딩합니다.
- 데이터 소스 항목을 형식 구성 요소에 바인딩합니다.
- 데이터 원본의 일부인 계산된 필드의 완전한 유지 관리.
- 사용자 입력 매개변수에 대한 가시성 조건을 정의합니다.
- 형식의 변형을 디자인합니다.
- 형식의 구성 요소에 대한 활성화 조건을 정의합니다.
- 형식의 FILE 구성 요소에 대한 파일 이름을 정의합니다.
- 공정 제어 검증을 위한 조건을 정의합니다.
- 공정 제어 검증을 위한 메시지 텍스트를 정의합니다.

## <a name="data-binding"></a><a name="Binding"></a>데이터 바인딩

ER 공식 디자이너를 사용하여 데이터 소스에서 받은 데이터를 변환하는 표현식을 정의할 수 있으므로 런타임 시 다음과 같은 방식으로 데이터 소비자에 데이터를 입력할 수 있습니다.

- 애플리케이션 데이터 소스 및 런타임 매개변수에서 ER 데이터 모델로
- ER 데이터 모델에서 ER 형식으로
- 애플리케이션 데이터 소스 및 런타임 매개변수에서 ER 형식으로

다음 그림은 이 유형의 표현식 디자인을 보여줍니다. 이 예에서 표현식은 Intrastat 테이블의 **Intrastat.AmountMST** 값을 반올림하여 소수점 이하 두 자리로 변환한 다음 반올림된 값을 반환합니다.

[![데이터 바인딩 식.](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

다음 그림은 이 유형의 식이 사용되는 방식을 보여줍니다. 이 예에서 설계된 표현식의 결과는 **Transaction.InvoicedAmount** 구성 요소의 **세금 보고 모델** 데이터 모델에 입력됩니다.

[![데이터 바인딩 표현식이 사용 중입니다.](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

런타임 시 설계된 공식 `ROUND (Intrastat.AmountMST, 2)`는 Intrastat 테이블의 각 레코드에 대해 **AmountMST** 필드 값을 소수점 이하 두 자리까지 반올림합니다. 그런 다음 **세금 보고** 데이터 보델의 **Transaction.InvoicedAmount** 구성 요소에서 반올림된 값을 입력합니다.

## <a name="data-formatting"></a><a name="Transformation"></a>데이터 형식 지정

ER 공식 디자이너를 사용하여 데이터 소스에서 받은 데이터를 형식 지정하는 표현식을 정의할 수 있으므로 전자 문서 생성의 일부로 데이터를 전송할 수 있습니다. 형식에 재사용해야 하는 일반적인 규칙으로 적용해야 하는 형식이 있을 수 있습니다. 이 경우 형식 구성에서 형식 지정 표현식이 있는 명명된 변환으로 해당 형식을 한 번 도입할 수 있습니다. 그런 다음 이 명명된 변환을 생성한 형식 지정 표현식에 따라 출력 형식을 지정해야 하는 여러 형식 구성 요소에 연결할 수 있습니다.

다음 그림은 이 유형의 변환 디자인을 보여줍니다. 이 예에서 **트리밍된 문자열** 변환은 선행 및 후행 공백을 제거하여 *문자열* 데이터 유형의 수신 데이터를 자릅니다. 그런 다음 잘린 문자열 값을 반환합니다.

[![변환.](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

다음 그림은 이 유형의 변환이 사용되는 방식을 보여줍니다. 이 예에서 여러 형식 구성 요소는 런타임에 생성하는 전자 문서에 출력으로 텍스트를 보냅니다. 이러한 모든 형식 구성 요소는 이름으로 **TrimmedString** 변환을 참조합니다.

[![변환을 사용 중입니다.](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

앞의 그림에서 **partyName** 구성 요소와 같은 형식 구성 요소가 **TrimmedString** 변환을 참조하면 변환은 생성 전자 문서에 출력으로 텍스트를 보냅니다. 이 텍스트에는 선행 및 후행 공백이 포함되지 않습니다.

개별적으로 적용해야 하는 서식이 있는 경우 해당 서식을 특정 서식 구성 요소 바인딩의 개별 표현식으로 도입할 수 있습니다. 다음 그림은 이 유형의 표현식을 보여줍니다. 이 예에서 **partyType** 형식 구성 요소는 들어오는 데이터를 변환하는 표현식을 통해 데이터 원본의 **Model.Company.RegistrationType** 필드에서 수신 데이터를 대문자 텍스트로 변환합니다. 그런 다음 표현식은 해당 텍스트를 전자 문서의 출력으로 보냅니다.

[![개별 구성 요소에 서식 적용](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>프로세스 흐름 제어

ER 공식 디자이너는 전자 문서 생성의 프로세스 흐름을 제어하는 표현식을 정의하는 데 사용할 수 있습니다. 다음 작업을 수행할 수 있습니다.

- 문서 생성 프로세스를 중지해야 하는 시기를 결정하는 조건을 정의합니다.
- 사용자에게 중지된 프로세스에 대한 메시지를 작성하거나 보고서 생성의 계속되는 프로세스에 대한 실행 로그 메시지를 생성하는 표현식을 지정합니다.
- 전자문서 생성 파일명을 지정하고 생성 조건을 제어합니다.

프로세스 흐름 제어의 각 규칙은 개별 검증으로 설계되었습니다. 다음 그림은 이 유형의 유효성 검사를 보여줍니다. 다음은 이 예의 구성에 대한 설명입니다.

- 유효성 검사는 XML 파일 생성 중에 **INSTAT** 노드가 생성되면 평가됩니다.
- 트랜잭션 목록이 비어 있으면 유효성 검사가 실행 프로세스를 중지하고 **거짓** 을 반환합니다.
- 유효성 검사는 사용자의 기본 언어로 된 레이블 SYS70894의 텍스트를 포함하는 오류 메시지를 반환합니다.

[![유효성 검사.](./media/picture-validation.jpg)](./media/picture-validation.jpg)

ER 공식 디자이너는 전자 문서 생성을 위한 파일 이름을 생성하고 파일 생성 프로세스를 제어하는 데에도 사용할 수 있습니다. 다음 그림은 이 유형의 프로세스 흐름 제어 디자인을 보여줍니다. 다음은 이 예의 구성에 대한 설명입니다.

- **model.Intrastat** 데이터 소스의 레코드 목록은 일괄 처리로 나뉩니다. 각 배치에는 최대 1,000개의 레코드가 포함됩니다.
- 출력은 생성된 모든 배치에 대해 XML 형식의 파일 하나가 포함된 zip 파일을 생성합니다.
- 표현식은 파일 이름과 파일 이름 확장자를 연결하여 전자 문서를 생성하기 위한 파일 이름을 반환합니다. 두 번째 배치 및 모든 후속 배치의 경우 파일 이름에 배치 ID가 접미사로 포함됩니다.
- 표현식은(**진실** 을 반환하여) 하나 이상의 레코드가 포함된 배치에 대한 파일 생성 프로세스를 가능하게 합니다.

[![프로세스 흐름 제어.](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>문서 콘텐츠 제어

ER 공식 디자이너는 런타임에 생성된 전자 문서에 넣을 데이터를 제어하는 표현식을 구성하는 데 사용할 수 있습니다. 표현식은 처리 데이터 및 구성된 로직에 따라 형식의 특정 요소 출력을 활성화하거나 비활성화할 수 있습니다. 이러한 표현식은 **활성화됨** 필드의 **매핑** 탭에서 **운영 디자이너** 페이지의 단일 형식 요소에 대해 입력할 수 있습니다. *부울* 값을 반환하는 논리 조건으로 식을 입력할 수 있습니다.

- 조건이 **진실** 을 반환하면 현재 형식 요소가 실행됩니다.
- 조건이 **거짓** 을 반환하면 현재 형식 요소를 건너뜁니다.

다음 그림은 이 유형의 표현식을 보여줍니다. (Microsoft에서 제공하는 버전 11.12.11의 **ISO20022 신용 양도(NO)** 형식 구성을 예로 사용합니다.) **XML헤더** 형식 구성 요소는 ISO 20022 XML 메시지 표준에 따라 신용 전송 메시지의 구조를 설명하도록 구성됩니다. **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** 형식 구성 요소는 **Ustrd** XML 요소를 생성된 메시지에 추가하고 다음 XML 요소의 텍스트로 비정형 형식의 송금 정보를 넣습니다.

- **PaymentNotes** 구성 요소는 지불 메모 텍스트를 생성하는 데 사용됩니다.
- **DelimitedSequence** 구성 요소는 현재 신용 이체를 정산하는 데 사용되는 쉼표로 구분된 송장 번호를 생성합니다.

[![PaymentNotes 및 DelimitedSequence 구성 요소.](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> **PaymentNotes** 및 **DelimitedSequence** 구성 요소는 물음표를 사용하여 레이블이 지정됩니다. 물음표는 구성 요소의 사용이 조건부임을 나타냅니다. 이 경우 구성 요소의 사용은 다음 기준에 따릅니다.
>
> - **PaymentNotes** 구성 요소에 대해 정의된 `@.PaymentsNotes <> ""` 식을 사용하면(**진실** 을 반환하여) 현재 신용 이체에 대해 해당 텍스트가 비어 있지 않은 경우 **Ustrd** XML 요소가 지불 메모 텍스트로 채워집니다.
>
>    [![PaymentNotes 구성 요소에 대한 표현식입니다.](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - **DelimitedSequence** 구성 요소에 대해 정의된 `@.PaymentsNotes = ""` 식을 사용하면(**진실** 을 반환하여) 해당 신용 이체에 대한 지불 메모 텍스트가 비어 있는 경우 **Ustrd**  XML 요소가 현재 신용 이체를 결제하는 데 사용되는 송장 번호의 쉼표로 구분된 목록으로 채워집니다.
>
>    [![DelimitedSequence 구성 요소에 대한 표현식입니다.](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> 이러한 설정을 기반으로 각 채무자 지불에 대해 생성되는 메시지는 **Ustrd** XML 요소가 지불 메모의 텍스트를 포함하거나 해당 텍스트가 비어 있는 경우 지불을 정산하는 데 사용되는 송장 번호의 쉼표로 구분된 목록을 포함합니다.

## <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>구성된 공식의 검증

**수식 디자이너** 페이지에서 **테스트** 를 선택하여 구성된 수식이 작동하는 방식을 확인합니다.

[![테스트를 선택하여 공식을 확인합니다.](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

수식 인수의 값이 필요한 경우 **수식 디자이너** 페이지의 **테스트 표현식** 대화 상자를 열 수 있습니다. 구성된 바인딩이 디자인 타임에 실행되지 않기 때문에 대부분의 경우 이러한 인수를 수동으로 정의해야 합니다. **수식 디자이너** 의 **검사 결과** 탭은 구성된 수식의 실행 결과를 보여줍니다.

다음 예는 Intrastat 상품 코드에 숫자만 포함되어 있는지 확인하기 위해 대외 무역 도메인에 대해 구성된 공식을 테스트하는 방법을 보여줍니다.

이 공식을 테스트할 때 **테스트 표현식** 대화 상자를 사용하여 테스트를 위한 Intrastat 상품 코드의 값을 지정할 수 있습니다.

[![테스트를 위해 Intrastat 상품 코드를 지정합니다.](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Intrastat 상품 코드를 지정하고 **확인** 을 선택하면 **수식 디자이너** 페이지의 **검사 결과** 탭은 구성된 수식의 실행 결과를 보여줍니다. 그런 다음 결과가 허용 가능한지 여부를 평가할 수 있습니다. 결과가 허용되지 않는 경우 수식을 업데이트하고 다시 테스트할 수 있습니다.

[![검사 결과.](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

일부 수식은 디자인 타임에 테스트할 수 없습니다. 예를 들어, 수식은 **테스트 결과** 탭에 표시할 수 없는 데이터 유형의 결과를 반환할 수 있습니다. 이 경우 수식을 테스트할 수 없다는 오류 메시지가 나타납니다.

[![오류 메시지.](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]