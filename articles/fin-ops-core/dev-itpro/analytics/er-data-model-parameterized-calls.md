---
title: ER 데이터 모델의 매개 변수화된 호출 지원
description: 이번에는 전자 보고(ER) 데이터 모델의 매개 변수화된 호출을 구현하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 968b0769607e9fdbed57c25b727ed44988a92913
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "8461047"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>ER 데이터 모델의 매개 변수화된 호출 지원

[!include [banner](../includes/banner.md)]

비즈니스 문서를 생성하려면 다음 ER 구성 요소가 포함된 [전자 보고(ER)](general-electronic-reporting.md) 솔루션을 구성합니다.

- **[형식](er-overview-components.md#format-component)** – 이 구성 요소는 비즈니스 문서의 구조를 지정합니다.
- **형식 매핑** – 이 구성 요소는 런타임에 비즈니스 문서를 채우는 방법을 제어합니다.
- **[모델 매핑](er-overview-components.md#model-mapping-component)** – 이 구성 요소는 데이터가 애플리케이션에서 형식 매핑으로 가져오는 것을 지정합니다.
- **[데이터 모델](er-overview-components.md#data-model-component)** – 이 구성 요소는 개별 구성 요소 간에 정보를 전달합니다.

ER 형식을 실행하면 루트 형식 요소에서 시작하여 모든 형식 요소가 실행됩니다. 실행되는 형식 요소에 [데이터 소스](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents)에 대한 바인딩이 포함될 때마다 데이터 소스가 실행되어 예상 데이터를 전달하고 이를 사용하여 형식 요소를 채웁니다. *모델* 유형의 데이터 소스가 호출되면 모델 매핑 설정을 기반으로 애플리케이션에서 데이터를 가져오기 위해 적절한 모델 매핑이 호출됩니다.

이전에는 이러한 모델 매핑 호출을 매개 변수화하여 실행되는 형식의 논리에 종속시킬 수 없었습니다. 다음 데이터 흐름만 지원되었습니다.

<table>
<tbody>
<tr align="center">
<td>
<b>포맷</b><br>
형식&nbsp;요소<br>
&nbsp;
</td>
<td>
<i>포획</i><br>
&gt;&nbsp;요청&nbsp;&gt;<br>
&lt;&nbsp;값&nbsp;&lt;
</td>
<td><b>형식&nbsp;매핑</b><br>
데이터 소스<br>
&nbsp;
</td>
<td>
<i>데이터&nbsp;모델</i><br>
&gt;&nbsp;요청&nbsp;&gt;<br>
&lt;&nbsp;값&nbsp;&lt;
</td>
<td>
<b>모델&nbsp;매핑</b><br>
데이터&nbsp;소스<br>
&nbsp;
</td>
<td>
<i>포획</i><br>
&gt;&nbsp;요청&nbsp;&gt;<br>
&lt;&nbsp;값&nbsp;&lt;
</td>
<td>
<b>테이블</b><br>
기록<br>
필드
</td>
</tr>
</tbody>
</table>

그러나 버전 10.0.15 이상에서는 구성된 매개 변수의 값이 제공될 때만 호출할 수 있는 데이터 모델 필드를 구성할 수 있습니다. 이러한 필드가 구성되고 형식 구성 요소에서 호출되는 경우 필수 매개 변수는 호출의 인수로 형식 바인딩에 제공되어야 합니다. 이러한 경우 형식별 값을 기반으로 인수 값을 지정할 수 있습니다. 따라서 데이터 모델 호출에 **동적 런타임 매개 변수화** 를 사용하여 다음 데이터 흐름을 지원할 수 있습니다.

<table>
<tbody>
<tr align="center">
<td>
<b>포맷</b><br>
형식&nbsp;요소&nbsp;1<br>
<br>
형식&nbsp;요소&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>포획</i><br>
&gt;&nbsp;요청&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;가치&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;요청&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;가치&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>형식&nbsp;매핑</b><br>
데이터&nbsp;소스&nbsp;1<br>
&nbsp;<br>
<b>값2=함수(값1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>데이터&nbsp;모델</i><br>
&gt;&nbsp;field1&nbsp;&gt;<br>
&lt;&nbsp;가치&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;field2(value2)&nbsp;&gt;</b><br>
&lt;&nbsp;가치&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>모델&nbsp;매핑</b><br>
데이터&nbsp;소스&nbsp;1<br>
<br>
데이터&nbsp;소스&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>포획</i><br>
&gt;&nbsp;요청&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;가치&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;요청&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;가치&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>표&nbsp;1</b><br>
기록&nbsp;1<br>
필드&nbsp;1<br>
<b>표&nbsp;2</b><br>
기록&nbsp;2<br>
필드&nbsp;2
</td>
</tr>
</tbody>
</table>

새 함수를 사용하면 [*기록*](er-formula-supported-data-types-composite.md#record) 또는 [*기록 목록*](er-formula-supported-data-types-composite.md#record-list) 유형의 모든 데이터 모델 필드에 대한 호출을 매개 변수화할 수 있습니다. 데이터 모델 필드의 매개 변수에 대해 다음 데이터 유형이 지원됩니다.

- [부울](er-formula-supported-data-types-primitive.md#boolean)
- [다음 포함](er-formula-supported-data-types-composite.md#container)
- [날짜](er-formula-supported-data-types-primitive.md#date)
- [날짜 시간](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [정수](er-formula-supported-data-types-primitive.md#integer)
- [실수](er-formula-supported-data-types-primitive.md#real)
- [스트링](er-formula-supported-data-types-primitive.md#string)

정의된 데이터 유형의 단일 값과 해당 값 [*목록*](er-formula-supported-data-types-composite.md#record-list)으로 인수를 제공할 수 있는 데이터 모델 필드의 모든 매개 변수를 지정할 수 있습니다.

> [!NOTE]
> 데이터 모델 필드의 매개 변수에 대한 기본값은 지원되지 않습니다. 데이터 모델의 필드에 매개 변수를 추가하고 해당 데이터 모델의 버전이 이미 릴리스 및 게시된 경우 모든 해당 모델 매핑 및 형식을 이 모델의 새 버전으로 [리베이스해야](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) 합니다. 이전 버전과 호환되지 않습니다.

매개 변수화된 데이터 모델 필드를 구성하여 모델 매핑 호출을 형식별로 만들 수 있습니다. 이 접근 방식을 사용하면 단일 데이터 모델의 여러 형식에 대해 구성해야 하는 모델 매핑의 수를 줄일 수 있습니다. 또한 이 접근 방식을 사용하여 형식의 실행 성능을 개선하고 비즈니스 문서를 생성하는 데 필요한 시간을 줄일 수 있습니다. 이 기능에 대해 자세히 알아보려면 이 항목의 예시를 완료하십시오.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>예:, ER 데이터 모델의 매개 변수화된 호출 사용

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 다음을 제공하여 형식에서 모델 매핑을 호출하도록 구성된 데이터 모델, 모델 매핑 및 형식 ER 구성 요소가 포함된 ER 솔루션을 설계하는 방법을 설명합니다. 실행 형식의 공식을 사용하여 런타임에 값이 계산된 호출에 대한 인수입니다. 

이러한 단계는 **DEMF** 회사에서 완료할 수 있습니다. 코드 수정이 필요하지 않습니다. 

이 예시에서는 **Litware, Inc.** 샘플 회사에 필요한 ER [구성](general-electronic-reporting.md#Configuration)을 생성합니다. **Litware, Inc.** (`http://www.litware.com`) 샘플 회사의 구성 공급자가 ER 프레임워크에 대해 나열되어 있고 **활성** 으로 표시되어 있는지 확인합니다. 이 구성 공급자가 나열되지 않거나 **활성** 으로 표시되지 않은 경우 구성 공급자 만들기의 단계를 따라 [활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)합니다.

### <a name="business-scenario"></a>비즈니스 시나리오

감사 목적으로 전자 문서를 생성하기 위해 실행할 수 있는 형식이 포함된 ER 솔루션이 있습니다. 이 형식에는 판매 주문 및 구매 주문과 관련되고 거래 날짜 및 세액과 같은 필수 세부 정보가 있는 세금 거래가 포함됩니다. 새 회계연도부터 이 문서의 구조가 변경되었습니다. 이제 생성된 보고서에 거래가 표시되는 모든 당사자(고객 및 공급 업체)의 추가 세부정보(이름)가 포함된 확장 문서를 제출해야 합니다. 따라서 이 새로운 요구 사항을 준수하는 문서를 생성하도록 ER 솔루션을 수정해야 합니다.

### <a name="configure-the-er-framework"></a>ER 프레임워크 구성

ER 프레임워크 구성의 단계에 따라 [ER 매개 변수의 최소 집합](er-quick-start2-customize-report.md#ConfigureFramework)을 설정합니다. ER 프레임워크를 사용하여 새 ER 솔루션을 설계하기 시작하기 전에 이 설정을 완료해야 합니다.

### <a name="design-a-domain-specific-data-model"></a>도메인별 데이터 모델 설계

필요한 데이터 모델 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 이 데이터 모델은 나중에 감사 보고서를 생성하기 위해 ER 형식을 설계할 때 데이터 소스로 사용됩니다.

Microsoft에서 제공하는 XML 파일에서 필요한 데이터 모델을 가져오려면 다음 단계를 따르십시오.

1. [샘플 감사 model.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 샘플 감사 **model.version.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

    ![구성 페이지에서 가져온 ER 데이터 모델 구성.](./media/er-data-model-parameterized-calls-imported-model.png)

다음 그림은 **데이터 모델 디자이너** 페이지에서 구성된 데이터 모델의 편집 가능한 버전을 보여줍니다.

![데이터 모델 디자이너 페이지의 ER 데이터 모델 구조.](./media/er-data-model-parameterized-calls-model1.png)

현재 이 모델은 필요한 세부 정보가 있는 세금 거래만 노출하도록 설계되었습니다.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>구성된 데이터 모델에 대한 모델 매핑 설계

전자 보고 개발자 역할의 사용자는 샘플 감사 데이터 모델에 대한 모델 매핑 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 이 구성 요소는 Microsoft Dynamics 365 Finance에 대해 구성된 데이터 모델을 구현하며 해당 앱에만 해당됩니다. 런타임 시 구성된 데이터 모델을 애플리케이션 데이터로 채우는 데 사용해야 하는 애플리케이션 개체를 지정하도록 모델 매핑 구성 요소를 구성해야 합니다. 이 작업을 완료하려면 세무 비즈니스 도메인의 데이터 구조가 재무에서 구현되는 방식을 이해해야 합니다.

Microsoft에서 제공하는 XML 파일에서 필요한 모델 매핑을 가져오려면 다음 단계를 따르십시오.

1. [샘플 감사 모델 mapping.version.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **샘플 감사 모델 mapping.version.1.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

    ![구성 페이지에서 가져온 ER 모델 매핑 구성.](./media/er-data-model-parameterized-calls-imported-mapping.png)

다음 그림은 **모델 매핑 디자이너** 페이지에서 구성된 모델 매핑의 편집 가능한 버전을 보여줍니다.

![모델 매핑 디자이너 페이지의 ER 모델 매핑 구조입니다.](./media/er-data-model-parameterized-calls-mapping1.png)

현재 모델 매핑은 필요한 세부 정보가 있는 세금 거래를 노출하도록 설계되었습니다. 구성된 `TaxTrans` `TaxTransFiltered` ER 데이터 소스를 사용하여 `TaxTrans` 애플리케이션 테이블에서 이 정보를 가져옵니다.

### <a name="design-a-new-format"></a>새로운 형식을 디자인하다

전자 보고 함수 컨설턴트 역할의 사용자는 형식 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 모든 필수 세부 정보가 포함된 세금 거래로 생성된 보고서를 채우도록 형식 구성 요소를 구성해야 합니다.

다음 단계에 따라 Microsoft에서 제공하는 XML 파일에서 필요한 형식을 가져옵니다.

1. [샘플 감사 format.version.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. **구성** 페이지의 작업 창에서 XML 파일에서 **Exchange** \> **로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **샘플 감사 format.version.1.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

    ![구성 페이지에서 가져온 ER 형식 구성.](./media/er-data-model-parameterized-calls-imported-format.png)

다음 그림은 **형식 디자이너** 페이지에서 구성된 형식의 편집 가능한 버전을 보여줍니다.

![형식 디자이너 페이지의 ER 형식 구조입니다.](./media/er-data-model-parameterized-calls-format1.png)

ER 형식은 보고서를 CSV(쉼표로 구분된 값) 형식의 텍스트 파일로 생성하도록 구성됩니다.

### <a name="run-the-imported-format"></a>가져온 형식 실행

1. **구성** 페이지에서 **샘플 감사 형식** 구성을 선택한 다음, 작업 창에서 **실행** 을 선택합니다.
2. **전자 보고서 매개 변수** 대화 상자의 **포함할 기록** 탭에서 **필터** 를 선택합니다.
3. **PIV-110000004** 및 **INV-10000001** 바우처의 세금 거래 선택 조건을 지정합니다.
4. **확인** 을 선택합니다.
5. **확인** 을 선택합니다.
6. 선택한 바우처의 세금 거래가 포함된 생성된 문서를 검토합니다.

    ![세금 거래와 함께 생성된 문서의 미리보기.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>가져온 ER 솔루션 조정

새로운 요구 사항에 따라 제출해야 하는 문서에는 거래가 포함된 고객 및 공급 업체의 이름이 포함되어야 합니다. 따라서 가져온 ER 솔루션을 수정하여 이 새로운 요구 사항을 준수하는 문서를 생성해야 합니다.

가져온 ER 구성 요소에 필요한 수정 사항을 구현하는 방법을 결정합니다.

명백한 접근 방식은 다음 수정 사항을 구현하는 것입니다.

- 데이터 모델에서 *스트링* 유형의 새 `Transaction.Party.Name` 데이터 모델 필드를 추가합니다.
- 모델 매핑에서 사용 가능한 테이블 관계를 사용하여 새 데이터 모델 `Name` 필드에 대한 바인딩을 구성하여 `DirPartyTable` 애플리케이션 테이블의 관련 기록에 액세스하고 여기에서 필드 값을 가져옵니다.

이 접근 방식은 효과가 있지만 트랜잭션 `TaxTrans` 테이블이 있고 많은 양의 기록을 포함할 수 있기 때문에 SQL 데이터베이스에서 성능 문제를 일으킬 수 있습니다. 이 경우 `DirPartyTable`에 대한 호출 수는 성능 문제를 일으킬 수 있는 `TaxTrans` 테이블의 기록 수와 같아야 합니다.

또는 다음 수정 사항을 구현할 수 있습니다.

- 데이터 모델에서 새 `Party` 루트와 새 `Party.Name` 필드를 추가합니다.
- 모델 매핑에서 테이블에서 시작하여 `DirPartyTable` 애플리케이션 `TaxTrans` 테이블의 관련 기록에 액세스하기 위해 테이블 관계에 사용되는 테이블의 모든 기록을 조인하는 새 데이터 소스를 추가합니다.

이 접근 방식이 작동하더라도 일부 메모리 소비 문제가 발생할 수 있습니다. 새로운 [JOIN](er-join-data-sources.md) 데이터 소스가 데이터베이스 성능 문제를 방지하기 위해 애플리케이션 데이터베이스에 대한 단일 SQL 요청으로 실행되는 경우에도 결과를 애플리케이션 서버의 메모리로 가져와야 합니다. 기록의 수와 해당 기록의 필드 수가 상당히 많기 때문에 이 접근 방식을 사용하면 메모리가 매우 많이 소모될 수 있습니다. 메모리 부족 런타임 예외가 발생할 수도 있습니다.

실행 형식이 메모리에서 생성된 보고서에 표시될 모든 세금 거래에 대한 고객 및 공급 업체의 고유 식별 코드를 수집할 때 수정 사항을 구현할 수 있습니다. 고유한 코드만 유지해야 하므로 최종 코드 세트는 메모리 소비에 영향을 줄 만큼 크지 않습니다. 이후 코드 집합은 *모델* 유형의 데이터 소스에 대한 다른 호출의 인수로 모델 매핑에 전달됩니다. 해당 호출을 기반으로 모델 매핑은 애플리케이션 데이터베이스에 대한 단일 SQL 요청을 수행하는 새로운 ER 데이터 소스를 실행하여 제공된 코드 세트에 코드가 표시된 당사자에 대한 기록만 `DirPartyTable` 테이블에서 가져옵니다.

### <a name="adjust-the-imported-data-model"></a>가져온 데이터 모델 조정

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **샘플 감사 모델** 을 선택합니다.
3. **버전** FastTab에서 상태가 **[초안](general-electronic-reporting.md#component-versioning)** 인 버전 **2** 를 선택합니다.
4. **구성 구성 요소** FastTab을 선택합니다.
5. **디자이너** 를 선택하여 편집할 데이터 모델을 엽니다.
6. **데이터 모델** 페이지에서 `Root` 필드가 선택되어 있는지 확인한 다음 **새로 만들기** 를 선택합니다.
7. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. 필드 그룹으로 **새 노드** 에서 **활성 노드의 하위** 옵션을 선택합니다.
    2. **이름** 필드에 **당사자** 를 입력합니다.
    3. **항목 유형** 필드에서 **기록 목록** 을 선택하십시오.
    4. **추가** 를 선택하여 새 필드 추가를 완료합니다.

8. `Root.Party` 필드가 선택되어 있는지 확인한 다음 **노드** 탭에서 **매개 변수** 를 선택합니다.
9. **매개 변수** 대화 상자에서 다음 단계를 수행합니다.

    1. **매개 변수** 탭에서 **새로 만들기** 를 선택합니다.
    2. **이름** 필드에 **PartyRefRecId** 를 입력합니다.
    3. **유형** 필드에서 **Int64** 를 선택합니다.
    4. **목록** 확인란을 선택합니다.
    5. **확인** 을 선택하여 매개 변수 입력을 마칩니다.

    > [!NOTE]
    > 방금 `Root.Party` 데이터 모델 필드를 **PartyRefRecId** 매개 변수에 값이 제공될 때 호출되는 필드로 구성했습니다. 이 값은 *Int64* 데이터 형식의 `Value` 필드가 포함된 기록 목록에 있어야 합니다.

    ![매개 변수 대화 상자.](./media/er-data-model-parameterized-calls-model2a.png)

10. `Root.Party` 필드가 여전히 선택되어 있는지 확인한 다음 **새로 만들기** 를 선택합니다.
11. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. 필드 그룹으로 **새 노드** 에서 **활성 노드의 하위** 옵션을 선택합니다.
    2. **이름** 필드에 **이름** 을 입력합니다.
    3. **항목 유형** 필드에서 **스트링** 을 선택하십시오.
    4. **추가** 를 선택하여 새 필드 추가를 완료합니다.

12. **저장** 을 선택하고 **데이터 모델** 페이지를 닫습니다.

    ![데이터 모델 디자이너 페이지에서 조정된 ER 데이터 모델의 구조.](./media/er-data-model-parameterized-calls-model2b.png)

13. **버전** FastTab에서 버전 **2** 의 경우 **상태 변경** \> **완료** 를 선택합니다. 이후 **확인** 을 선택합니다.

    > [!NOTE]
    > 데이터 모델 변경 사항은 **샘플 감사 모델** ER 구성의 두 번째 버전에 있는 **샘플 감사 모델** 데이터 모델 구성 요소의 두 번째 개정에 저장됩니다.

![구성 페이지에서 ER 데이터 모델 구성을 업데이트했습니다.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>가져온 모델 매핑 조정

1. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **샘플 감사 모델** 을 확장합니다.
2. **샘플 감사 모델 매핑** 을 선택한 다음 **버전** FastTab에서 첫 번째 데이터 모델 버전(버전 **1.2**)을 기반으로 하고 상태가 **초안** 인 두 번째 매핑 버전을 선택합니다.
3. **리베이스** 를 선택합니다.
4. **대상 버전** 필드에서 **샘플 감사 모델** 기본 모델의 버전 **2** 를 그대로 둡니다.
5. **확인** 을 선택하여 최근 데이터 모델 변경 사항에 따라 모델 매핑을 리베이스하고 정렬합니다.

    편집 가능한 모델 매핑의 버전 번호가 **1.2** 에서 **2.2** 로 변경되어 두 번째 모델 버전이 현재 기본으로 사용 중임을 나타냅니다.

6. **디자이너** 를 선택합니다.
7. **모델 대 데이터 소스 매핑** 페이지에서 현재 모델 매핑에 대해 **디자이너** 를 선택합니다.
8. `DirPartyTable` 애플리케이션 테이블에 액세스할 새 데이터 소스를 추가하려면 다음 단계를 따르십시오.

    1. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations \> 테이블 기록** 를 선택합니다.
    2. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    3. **이름** 필드에 **PartyTable을** 입력합니다.
    4. **테이블** 필드에 **DirPartyTable을** 입력합니다.
    5. **확인** 을 선택하여 새 데이터 원본 추가를 완료합니다.

9. 제공된 `DirPartyTable` 기록 식별 코드 목록을 기반으로 기록을 요청할 새 데이터 소스를 추가하려면 다음 단계를 따르십시오.

    1. **데이터 원본 유형** 창에서 **일반 \> 빈 컨테이너** 를 선택합니다.
    2. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    3. **이름** 필드에 **데이터** 를 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본 추가를 완료합니다.
    5. **데이터 원본** 창에서 **데이터** 데이터 원본을 선택합니다.
    6. **데이터 원본 유형** 창에서 **계산된 \> 함수** 필드를 선택합니다.
    7. **데이터 원본** 창에서 **추가** 를 선택합니다.
    8. **이름** 필드에 **DirParty를** 입력합니다.
    9. **수식 편집** 을 선택합니다.
    10. **공식 디자이너** 페이지에서 **매개 변수** 를 선택합니다.
    11. **매개 변수** 대화 상자에서 다음 단계를 수행합니다.

        1. **매개 변수** 탭에서 **새로 만들기** 를 선택합니다.
        2. **이름** 필드에 **DirPartyId** 를 입력합니다.
        3. **유형** 필드에서 **Int64** 를 선택합니다.
        4. **목록** 확인란을 선택합니다.
        5. **확인** 을 선택합니다.

        > [!NOTE]
        > *Int64* 유형의 단일 필드가 있는 기록 목록으로 구성된 단일 매개 변수의 인수를 런타임에 수락하도록 이 계산된 `Value` 필드를 방금 구성했습니다.

    12. **수식** 필드에 다음 표현식을 입력합니다.

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > 필드가 호출될 때 `DirParty` 인수로 제공되는 `DirPartyTable` 목록에 기록 식별 코드가 포함된 `DirPartyId` 기록만 가져오도록 계산된 `DirParty` 필드를 구성했습니다.

        ![공식 디자이너 페이지의 애플리케이션 테이블에서 당사자 이름을 가져오는 공식.](./media/er-data-model-parameterized-calls-formula1.png)

    13. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.
    14. **저장** 을 선택한 다음 **확인** 을 선택하여 새 데이터 원본 추가를 마칩니다.

10. 다음 단계에 따라 새 데이터 소스를 새 데이터 모델 필드에 바인딩하여 데이터 모델이 당사자 이름을 노출하는 데 사용되도록 합니다.

    1. **데이터 모델** 창에서 `Root.Party` 데이터 모델 필드를 선택합니다.
    2. **데이터 모델** 창에서 **편집** 을 선택합니다.
    3. **수식 디자이너** 페이지의 **수식** 필드에 `Data.DirParty(PartyRefRecId)` 식을 입력합니다.
    4. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.

        > [!NOTE]
        > 구성된 `Data.DirParty` 데이터 소스를 호출하고 데이터 모델 필드가 호출될 때 형식에 지정될 `Root.Party` 기록 식별 코드 목록을 제공하도록 바인딩을 구성했습니다.

    5. **데이터 모델** 창에서 `Root.Party.Name` 데이터 모델 필드를 선택합니다.
    6. **데이터 모델** 창에서 **편집** 을 선택합니다.
    7. **수식 디자이너** 페이지의 **데이터 원본** 창에서 **Data \> DirParty** 를 확장하고 **이름** 을 선택합니다.
    8. **데이터 원본 추가** 를 선택합니다.
    9. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.

    ![모델 매핑 디자이너 페이지에서 조정된 ER 모델 매핑의 구조입니다.](./media/er-data-model-parameterized-calls-mapping2.png)

11. **저장** 을 선택하고 **모델 매핑 디자이너** 페이지를 닫습니다.
12. **데이터 소스 매핑 모델링** 페이지를 닫습니다.
13. **버전** FastTab에서 버전 **2.2** 의 경우 **상태 변경 \> 완료** 를 선택합니다. 이후 **확인** 을 선택합니다.

### <a name="adjust-the-imported-format"></a>가져온 형식 조정

1. **구성** 페이지에서 **샘플 감사 형식** 을 선택합니다.
2. **버전** FastTab에서 상태가 **초안** 인 버전 **1.2** 를 선택하십시오.
3. **리베이스** 를 선택합니다.
4. **대상 버전** 필드에서 **샘플 감사 모델** 기본 모델의 버전 **2** 를 그대로 둡니다.
5. **확인** 을 선택하여 최근 데이터 모델 변경 사항에 맞게 형식을 리베이스하고 정렬합니다.
6. **디자이너** 를 선택합니다.
7. **형식 디자이너** 페이지의 왼쪽 창에 있는 형식 구조 트리에서 **확장/축소** 를 선택합니다.
8. 생성된 보고서에 거래가 표시되는 당사자의 기록 식별 코드를 수집하기 위해 새 형식 요소를 추가하려면 다음 단계를 따르십시오.

    1. 형식 구조 트리에서 **Report.Row.Trans** 시퀀스 요소를 선택합니다.
    2. **추가** 를 선택합니다.
    3. **추가** 대화 상자에서 **데이터 원본 \> 항목** 을 선택합니다.
    4. **구성 요소 속성** 대화 상자의 **이름** 필드에 **Id** 를 입력합니다.
    5. **데이터 유형** 필드에서 **Int64** 를 선택합니다.
    6. **확인** 을 선택합니다.

    > [!NOTE]
    > **데이터 소스 \> 항목** 요소는 실행 중인 형식의 범위에서만 내부 계산 및 데이터 변환을 수행하는 데 사용할 수 있습니다. 따라서 이 형식 요소를 추가하여 생성된 문서의 내용을 변경하지 않습니다.

9. 생성된 보고서에 당사자 이름을 입력하기 위해 새 형식 요소를 추가하려면 다음 단계를 따르십시오.

    1. **Report.Row** 시퀀스 요소를 선택합니다.
    2. **추가** 를 선택합니다.
    3. **추가** 대화 상자에서 **텍스트 \> 시퀀스** 를 선택합니다.
    4. **구성 요소 속성** 대화 상자의 **이름** 필드에 **당사자** 를 입력합니다.
    5. **확인** 을 선택합니다.
    6. **Report.Row.Party** 시퀀스 요소를 선택하십시오.
    7. **추가** 를 선택합니다.
    8. **추가** 대화 상자에서 **텍스트 \> 스트링** 을 선택합니다.
    9. **구성 요소 속성** 대화 상자의 **이름** 필드에 **이름** 을 입력합니다.
    10. **확인** 을 선택합니다.

10. 생성된 보고서에 거래가 표시되는 당사자의 기록 식별 코드를 수집하기 위해 새 데이터 소스를 추가하려면 다음 단계를 따르십시오.

    1. **매핑** 탭에서 **루트 추가** 를 선택합니다.
    2. **데이터 원본 추가** 대화 상자에서 **함수 \> 데이터 컬렉션** 을 선택합니다.
    3. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **PartyIds를** 입력합니다.
    4. **항목 유형** 필드에서 **Int64** 를 선택합니다.
    5. **확인** 을 선택합니다.

11. 생성된 보고서에 거래가 표시되는 당사자의 기록 식별 코드를 수집하기 위해 새 바인딩을 추가하려면 다음 단계를 따르십시오.

    1. 형식 구조 트리에서 **Report.Row.Trans.Id** 데이터 항목 요소를 선택하십시오.
    2. **수식 편집** 을 선택합니다.
    3. **수식 디자이너** 페이지에서 `PartyIds.Collect(model.Transaction.Party.RecId)` 식을 입력합니다.
    4. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.

12. 생성된 보고서에 당사자 이름을 입력하기 위해 새 바인딩을 추가하려면 다음 단계를 따르십시오.

    1. 형식 구조 트리에서 **Report.Party** 시퀀스 요소를 선택합니다.
    2. **수식 편집** 을 선택합니다.
    3. **수식 디자이너** 페이지에서 `model.Party(PartyIds.Result)` 식을 입력합니다.
    4. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.
    5. 형식 구조 트리에서 **Report.Party.Name** 시퀀스 요소를 선택합니다.
    6. **매핑** 탭에서 `model.Party.Name` 데이터 모델 필드를 선택합니다.
    7. **바인딩** 을 선택합니다.

    ![형식 디자이너 페이지에서 조정된 ER 형식의 구조입니다.](./media/er-data-model-parameterized-calls-format2.png)

13. **저장** 을 선택하고 **형식 디자이너** 페이지를 닫습니다.
14. **데이터 소스 매핑 모델링** 페이지를 닫습니다.
15. **버전** FastTab에서 버전 **2.2** 의 경우 **상태 변경** \> **완료** 를 선택합니다. 이후 **확인** 을 선택합니다.

### <a name="run-the-adjusted-format"></a>조정된 형식 실행

1. **구성** 페이지에서 **샘플 감사 형식** 을 선택한 다음, 작업 창에서 **실행** 을 선택합니다.
2. **전자 보고서 매개 변수** 대화 상자의 **포함할 기록** 탭에서 **필터** 를 선택합니다.
3. **PIV-110000004** 및 **INV-10000001** 바우처의 세금 거래 선택 조건을 지정합니다.
4. **확인** 을 선택합니다.
5. **확인** 을 선택합니다.
6. 선택한 바우처의 세금 거래와 해당 고객 및 공급 업체의 이름이 포함된 생성된 문서를 검토합니다.

    ![세금 거래 및 당사자 이름이 있는 생성된 문서의 미리보기.](./media/er-data-model-parameterized-calls-output2.png)

7. **미지급금** \> **공급 업체** \> **모든 공급 업체** 로 이동하여 공급 업체 이름을 포함하여 선택한 **PIV-110000004** 바우처의 세부 정보를 검토합니다.

    ![모든 공급 업체 및 송장 분개 페이지에서 구매 바우처 세부 정보를 검토합니다.](./media/er-data-model-parameterized-calls-review1.gif)

8. **미수금** \> **고객** \> **모든 고객** 으로 이동하여 고객 이름을 포함하여 선택한 **INV-10000001** 바우처의 세부 정보를 검토합니다.

    ![모든 고객 및 게시된 판매세 페이지에서 판매 쿠폰 세부 정보를 검토합니다.](./media/er-data-model-parameterized-calls-review2.gif)

이 ER 솔루션 실행에 대한 자세한 내용은 ER 내장 [성능 추적](trace-execution-er-troubleshoot-perf.md) 파서를 사용하십시오.

## <a name="additional-resources"></a>추가 리소스

- [계산된 필드 유형의 ER 데이터 소스의 매개 변수화된 호출 지원](er-calculated-field-type.md)
- [ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)
- [전자 보고 형식의 DATA COLLECTION 데이터 소스 사용](er-data-collection-data-sources.md)
- [ValueInLarge ER 함수](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
