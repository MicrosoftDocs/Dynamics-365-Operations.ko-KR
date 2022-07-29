---
title: 전자 보고에서 다국어 보고서 디자인
description: 이번에는 전자 보고(ER) 레이블을 사용하여 다국어 보고서를 디자인하고 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 11/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eab17635494657740fe46364bde0773dae5b9e4b
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460861"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>전자 보고에서 다국어 보고서 디자인

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>개요

비즈니스 사용자는 [전자 보고(ER)](general-electronic-reporting.md) 프레임워크를 사용하여 다양한 국가 또는 지역의 법적 요구 사항에 따라 생성해야 하는 아웃바운드 문서의 형식을 구성할 수 있습니다. 이러한 요구 사항에 따라 아웃바운드 문서를 다른 국가 또는 지역에 대해 다른 언어로 생성해야 하는 경우 언어 종속 리소스가 포함된 단일 ER 형식을 구성할 수 있습니다. 이러한 방식으로 형식을 재사용하여 다양한 국가 또는 지역에 대한 아웃바운드 문서를 생성할 수 있습니다. 또한 단일 ER 형식을 사용하여 해당 고객, 공급 업체, 자회사 또는 기타 당사자에 대해 다른 언어로 아웃바운드 문서를 생성할 수 있습니다.

ER 데이터 모델 및 모델 매핑을 구성된 ER 형식의 데이터 소스로 구성하여 생성된 문서에 넣을 애플리케이션 데이터를 지정하는 데이터 흐름을 정의할 수 있습니다. ER 구성 [공급자는](general-electronic-reporting.md#Provider) 구성된 데이터 모델, 모델 매핑 및 형식을 ER 솔루션의 구성 요소로 [게시하여](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) 특정 아웃바운드 문서를 생성할 수 있습니다. 또한 고객이 게시된 ER 솔루션을 [업로드](general-electronic-reporting-manage-configuration-lifecycle.md)하여 사용하고 사용자 지정할 수 있도록 허용할 수 있습니다. 고객이 다른 언어를 사용할 수 있을 것으로 예상되는 경우 언어 종속 리소스를 포함하도록 ER 구성 요소를 구성할 수 있습니다. 이러한 방식으로 편집 가능한 ER 구성 요소의 내용은 디자인 타임에 고객이 선호하는 언어로 표시될 수 있습니다.

언어 종속 리소스를 ER 레이블로 구성할 수 있습니다. 이후 해당 레이블을 사용하여 다음 목적을 위해 ER 구성 요소를 구성할 수 있습니다.

- 디자인 타임:

    - 구성된 ER 구성 요소의 내용을 사용자가 선호하는 언어로 표시합니다.

- 런타임 시:

    - 아웃바운드 문서에 대한 언어 종속 콘텐츠를 생성합니다.
    - 사용자가 선호하는 언어로 경고 및 오류 메시지를 제공합니다.
    - 사용자가 선호하는 언어로 필수 필드를 입력하라는 메시지를 표시합니다.

ER 레이블은 다른 구성 요소를 포함하는 모든 ER [구성](general-electronic-reporting.md#Configuration)에서 구성할 수 있습니다. 레이블은 ER 데이터 모델, ER 모델 매핑 및 ER 형식 구성 요소의 구성된 논리와 독립적으로 유지 관리할 수 있습니다.

모든 ER 레이블은 해당 레이블이 포함된 ER 구성 범위에서 고유한 ID로 식별됩니다. 모든 레이블에는 현재 Microsoft Dynamics 365 Finance 인스턴스에서 지원되는 모든 언어에 대한 레이블 텍스트가 포함될 수 있습니다. 이러한 지원 언어에는 배포된 사용자 지정 언어가 포함됩니다.

## <a name="entry"></a>기입

ER 데이터 모델, ER 모델 매핑 또는 ER 형식을 디자인할 때 번역 가능한 컨텍스트를 포함할 수 있는 필드를 선택할 때마다 **번역** 옵션이 표시됩니다. 이 옵션을 선택하면 선택한 필드를 **텍스트 번역** <a name="TextTranslationPane">창</a>의 ER 레이블에 연결할 수 있습니다. 기존 ER 레이블을 선택하거나 아직 사용할 수 없는 경우 새 ER 레이블을 추가할 수 있습니다. ER 레이블을 선택하거나 추가할 때 현재 Finance 인스턴스에서 지원되는 모든 언어에 대한 관련 텍스트를 추가할 수 있습니다.

다음 그림은 편집 가능한 ER 데이터 모델에서 이 변환이 수행되는 방법을 보여줍니다. 이 예시에서 편집 가능한 **송장 모델** 에 대한 **PurchaseOrder** 필드의 **설명** 속성은 오스트리아 독일어(DE-AT) 및 일본어(JA) 언어로 번역됩니다.

![ER 데이터 모델 디자이너에서 ER 레이블 번역을 제공합니다.](./media/er-multilingual-labels-refer.png)

편집 가능한 ER 구성 요소에 있는 레이블의 레이블 텍스트만 번역할 수 있습니다. 예를 들어 ER 모델 매핑 데이터 소스의 레이블 속성에 대해 **번역** 을 선택한 다음 상위 ER 데이터 모델에 있는 ER 레이블을 선택하면 레이블의 내용이 표시되지만 변경할 수는 없습니다. 그것. 이러한 경우 다음 그림과 같이 **번역된 텍스트** 필드를 사용할 수 없습니다.

![ER 모델 매핑 디자이너에서 제공된 ER 레이블 번역을 검토합니다.](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> 디자이너를 사용하여 편집 가능한 ER 구성 요소에 입력된 레이블을 삭제할 수 없습니다.

## <a name="scope"></a>범위

ER 레이블은 ER 구성 요소의 여러 번역 가능한 속성에서 참조할 수 있습니다.

### <a name="data-model-component"></a>데이터 모델 구성 요소

ER 데이터 모델을 구성할 때 ER 레이블을 추가할 수 있습니다. 모델 항목의 **레이블** 및 **설명** 속성, 모든 <a id="LinkModelEnum"></a>모델의 필드 및 모든 모델 열거 값은 ER 데이터 모델에 추가되는 ER 레이블에 연결할 수 있습니다.

![ER 데이터 모델 디자이너에서 설명 속성에 대한 번역을 제공합니다.](./media/er-multilingual-labels-refer.png)

ER 데이터 모델이 이러한 방식으로 구성되면 해당 콘텐츠는 각 사용자가 선호하는 언어로 ER 데이터 모델 디자이너의 사용자에게 표시됩니다. 따라서 모델 유지 관리가 간소화됩니다. 다음 그림은 DE-AT 및 JA가 기본 언어로 설정된 사용자에게 이 함수가 작동하는 방식을 보여줍니다.

![DE-AT가 기본 언어로 설정된 사용자를 위한 ER 데이터 모델 디자이너의 레이아웃입니다.](./media/er-multilingual-labels-refer-de.png)

![JA를 기본 언어로 설정한 사용자를 위한 ER 데이터 모델 디자이너의 레이아웃입니다.](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>모델 매핑 구성 요소

ER 모델 매핑은 ER 데이터 모델을 기반으로 하기 때문에 참조되는 데이터 모델 요소의 레이블은 모델 매핑 디자이너에서 사용자가 선호하는 언어로 나타납니다. 다음 그림은 구성된 데이터 모델에 추가된 **설명** 속성의 레이블을 사용하여 편집 가능한 모델 매핑에서 **PurchaseOrder** 필드의 의미를 설명하는 방법을 보여줍니다. 이 레이블은 사용자가 선호하는 언어(이 예시에서는 DE-AT)로 표시됩니다.

![DE-AT가 기본 언어로 설정된 사용자를 위한 ER 모델 매핑 디자이너의 레이아웃입니다.](./media/er-multilingual-labels-show-mapping.png)

**사용자 입력 매개 변수** 데이터 소스의 **레이블** 속성이 ER 레이블에 연결된 것으로 구성되면 이 데이터 소스에 해당하는 매개 변수 필드가 런타임 시 사용자 대화 상자에 사용자가 선호하는 언어로 표시됩니다.

### <a name="format-component"></a>형식 구성 요소

ER 형식을 구성할 때 ER 레이블을 추가할 수 있습니다. 구성된 모든 데이터 소스의 **레이블** 및 **도움말 텍스트** 속성은 ER 형식에 추가되는 ER 레이블에 연결할 수 있습니다. 모든 <a id="LinkFormatEnum"></a>형식 열거 값의 **레이블** 및 **설명** 속성은 편집 가능한 ER 형식에서 액세스할 수 있는 ER 레이블에도 연결할 수 있습니다.

> [!NOTE]
> 이 ER 데이터 모델에 대해 구성된 모든 ER 형식에서 모델의 레이블을 재사용하는 상위 ER 데이터 모델의 ER 레이블에 이러한 속성을 연결할 수도 있습니다.

ER 형식이 이러한 방식으로 구성되면 형식의 내용은 각 사용자가 선호하는 언어로 ER Operation 디자이너의 사용자에게 표시됩니다. 따라서 구성된 로직의 형식 유지 및 분석이 단순화됩니다.

ER 형식은 ER 데이터 모델을 기반으로 하기 때문에 데이터 모델 요소에서 참조하는 레이블은 사용자가 선호하는 언어로 ER 형식 디자이너에 표시됩니다.

**사용자 입력 매개 변수** 데이터 소스의 **레이블** 속성이 ER 레이블에 연결되면 런타임 시 사용자 대화 상자의 매개 변수에 해당하는 필드가 프롬프트로 사용자에게 표시됩니다. 다음 그림은 디자인 타임에 **사용자 입력 매개 변수** 데이터 소스의 **레이블** 속성을 ER 레이블에 연결하여 사용자가 다른 사용자 기본 설정 언어로 매개 변수를 묻는 메시지를 표시하도록 하는 방법을 보여줍니다(미국 영어(EN-US) 및 DE-AT 언어) 런타임 시.

![ER Operation Designer에서 사용자 입력 매개 변수의 속성 변환을 제공합니다.](./media/er-multilingual-labels-refer-format.png)

![EN-US 사용자 기본 언어에 대한 런타임 시 ER 공급 업체 지급 처리.](./media/er-multilingual-labels-show-runtime-en.png)

![DE-AT 사용자 기본 언어에 대한 런타임 시 ER 공급 업체 지급 처리.](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>식

ER [표현식](er-formula-language.md)에서 레이블을 사용하려면 **@'GER\_LABEL:X**' 구문을 사용해야 합니다. 여기서 **@** 접두사는 피연산자가 레이블을 참조함을 나타내고, **GER\_LABEL** 은 ER 레이블이 포함됨을 나타내며, **X** 는 ER 레이블 ID입니다.

![ER 공식 디자이너에서 ER 레이블에 대한 참조를 포함하는 ER 표현식 구성.](./media/er-multilingual-labels-expression1.png)

시스템(애플리케이션) 레이블을 참조하려면 **@'X'** 구문을 사용하십시오. 여기서 **@** 접두사는 피연산자가 레이블을 참조하고 **X** 는 시스템 레이블 ID임을 나타냅니다.

![ER 공식 디자이너에서 애플리케이션 레이블에 대한 참조를 포함하는 ER 표현식 구성.](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>모델 매핑

레이블을 사용하여 ER 모델 매핑의 표현식을 구성할 수 있습니다. 아웃바운드 문서를 생성하기 위해 실행되는 ER 형식에서 이 매핑을 호출하면 실행 컨텍스트에 언어 코드가 포함됩니다. 구성된 표현식 레이블은 해당 컨텍스트의 언어에 대해 구성된 레이블 텍스트로 채워집니다.

참조된 레이블에 모델 매핑을 호출하는 형식 실행 컨텍스트의 언어에 대한 번역이 없으면 대신 EN-US 언어의 레이블 텍스트가 사용됩니다.

#### <a name="format"></a>포맷

ER 형식의 ER 표현식은 레이블을 사용하여 구성할 수 있습니다. 아웃바운드 문서를 생성하기 위해 이 형식을 실행하면 실행 컨텍스트에 언어 코드가 포함됩니다. 구성된 표현식 레이블은 해당 컨텍스트의 언어에 대해 구성된 레이블 텍스트로 채워집니다.

![ER 공식 디자이너에서 편집 가능한 ER 표현식의 ER 레이블 번역을 제공합니다.](./media/er-multilingual-labels-refer-in-expression.png)

![ER Operation Designer에서 ER 레이블을 참조하는 데이터 바인딩 샘플입니다.](./media/er-multilingual-labels-refer-in-binding.png)

ER 형식의 **FILE** 구성 요소를 구성하여 사용자가 선호하는 언어로 보고서를 생성할 수 있습니다.

![ER Operation Designer에서 FILE 구성 요소를 설정하여 사용자가 선호하는 언어로 보고서를 생성합니다.](./media/er-multilingual-labels-language-context-user.png)

이러한 방식으로 ER 형식을 구성하면 ER 레이블의 해당 텍스트를 사용하여 보고서가 생성됩니다. 다음 그림은 EN-US 및 DE-AT 사용자 언어에 대한 보고서의 예를 보여줍니다.

![EN-US 사용자가 선호하는 언어로 생성된 보고서의 미리보기입니다.](./media/er-multilingual-labels-report-preview-en.png)

![DE-AT 사용자가 선호하는 언어로 생성된 보고서의 미리보기입니다.](./media/er-multilingual-labels-report-preview-de.png)

참조된 레이블에 형식 실행 컨텍스트의 언어에 대한 번역이 없으면 EN-US 언어의 레이블 텍스트가 대신 사용됩니다.

## <a name="language"></a>언어

ER은 생성된 보고서의 언어를 지정하는 다양한 방법을 지원합니다. **형식** 탭의 **언어 기본 설정** 필드에서 다음 값을 선택할 수 있습니다.

- **회사 기본 설정** – 회사에서 지정한 언어로 보고서를 생성합니다.

    ![ER Operation Designer에서 회사가 선호하는 언어를 생성된 보고서의 언어로 지정합니다.](./media/er-multilingual-labels-language-context-company.png)

- **사용자 기본 설정** – 사용자가 선호하는 언어로 보고서를 생성합니다.
- **명시적으로 정의됨** – 디자인 타임에 지정된 언어로 보고서를 생성합니다.

    ![ER 작업 디자이너에서 생성된 보고서의 언어로 디자인 타임 정의 언어를 지정합니다.](./media/er-multilingual-labels-language-context-fixed.png)

- **런타임 시 정의** – 런타임 시 지정된 언어로 보고서를 생성합니다. 이 값을 선택하는 경우 **언어** 필드에서 해당 고객의 언어와 같은 언어에 대한 언어 코드를 반환하는 ER 표현식을 구성하십시오.

    ![ER 작업 디자이너에서 런타임 정의 언어를 생성된 보고서의 언어로 지정합니다.](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="culture-specific-formatting"></a>문화별 서식

ER은 생성된 보고서의 문화권을 지정하는 다양한 방법을 지원합니다. 따라서 날짜, 시간 및 숫자 값에 올바른 문화권별 서식을 사용할 수 있습니다. ER 형식을 디자인할 때 **형식** 탭의 **문화권 기본 설정** 필드에서 **Common\\File**, **Excel\\File**, **PDF\\File** 또는 **PDF\\Merger** 유형의 모든 형식 구성 요소에 대해 다음 값 중 하나를 선택할 수 있습니다.

- **사용자 기본 설정** – 사용자가 선호하는 문화권에 따라 값의 형식을 지정합니다. 해당 문화권은 **사용자 옵션** 페이지의 **기본 설정** 탭에 있는 **날짜, 시간 및 숫자 형식** 필드에 정의되어 있습니다.

    ![ER Operation Designer에서 생성된 보고서의 문화로 사용자의 선호 문화를 정의합니다.](./media/er-multilingual-labels-culture-context-user-preferred.png)

- **명시적으로 정의됨** – 디자인 타임에 지정된 문화권에 따라 값의 형식을 지정합니다.

    ![ER Operation 디자이너에서 생성된 보고서의 culture로 디자인 타임에 지정된 culture를 정의합니다.](./media/er-multilingual-labels-culture-context-fixed.png)

- **런타임에 정의됨** – 런타임에 지정된 문화권에 따라 값의 형식을 지정합니다. 이 값을 선택하는 경우 **매핑** 탭의 **날짜, 시간 및 숫자 형식** 필드에서 해당 고객의 문화권과 같은 문화권에 대한 문화권 코드를 반환하는 ER 식을 구성합니다.

    ![런타임에 ER Operation Designer에서 생성된 보고서의 문화권으로 정의된 문화권을 정의합니다.](./media/er-multilingual-labels-culture-context-runtime.png)

> [!NOTE]
> 특정 문화권을 정의하는 ER 구성 요소에는 텍스트 값을 채우도록 구성된 하위 ER 구성 요소가 포함될 수 있습니다. 기본적으로 부모 구성 요소의 문화권은 해당 구성 요소의 값 형식을 지정하는 데 사용됩니다. 다음 기본 제공 ER 함수를 사용하여 해당 구성 요소에 대한 바인딩을 구성하고 값 형식 지정을 위한 대체 문화권을 적용할 수 있습니다.
>
> - [날짜 형식](er-functions-datetime-dateformat.md#syntax-2)
> - [날짜시간형식](er-functions-datetime-datetimeformat.md#syntax-2)
> - [숫자 형식](er-functions-text-numberformat.md#syntax-2)
>
> 버전 10.0.20 이상에서 **Common\\File** 및 **Excel\\File** 유형의 형식 구성 요소 로케일은 생성된 문서의 [PDF 변환](electronic-reporting-destinations.md#OutputConversionToPDF) 중에 값의 형식을 지정하는 데 사용됩니다.

## <a name="translation"></a>번역

편집 가능한 ER 구성 요소에 필요한 ER 레이블을 추가할 수 있습니다. ER 레이블이 추가되면 수동 및 자동의 두 가지 방법으로 번역될 수 있습니다.

### <a name="manual-translation"></a>수동 번역

**텍스트 번역** [창](#TextTranslationPane)에 ER 레이블을 추가하면 현재 Finance 인스턴스에서 지원되는 모든 언어로 수동으로 번역할 수 있습니다. **시스템 언어** 또는 **사용자 언어** 섹션의 **언어** 필드에서 기본 언어를 선택하고 해당 **번역된 텍스트** 필드에 적절한 텍스트를 입력한 다음 **번역** 을 선택할 수 있습니다. 이 프로세스는 필요한 모든 언어와 추가하는 모든 레이블에 대해 반복되어야 합니다.

### <a name="automatic-translation"></a>자동 번역

ER 구성 요소의 구성은 편집 가능한 ER 구성 요소가 있는 ER 구성의 초안 버전에서 수행됩니다.

![초안 상태의 구성 버전에 대한 액세스를 제공하는 ER 구성 페이지.](./media/er-multilingual-labels-configurations.png)

이 항목의 앞부분에서 설명한 대로 편집 가능한 ER 구성 요소에 필요한 ER 레이블을 추가할 수 있습니다. 이러한 방식으로 EN-US 언어로 ER 레이블 텍스트를 지정할 수 있습니다. 이후 내장 ER 함수를 사용하여 ER 구성 요소의 레이블을 내보낼 수 있습니다. 편집 가능한 ER 구성 요소가 포함된 ER 구성의 초안 버전을 선택한 다음 **Exchange \> 내보내기 레이블** 을 선택합니다.

![ER 구성 페이지에서 선택한 구성 버전에서 ER 레이블을 내보낼 수 있습니다.](./media/er-multilingual-labels-export.png)

내보내기 시작 시 지정한 단일 언어에 대한 레이블 또는 모든 레이블을 내보낼 수 있습니다. 레이블은 XML 파일이 포함된 zip 파일로 내보내집니다. 모든 XML 파일에는 단일 언어에 대한 레이블이 포함되어 있습니다.

![DE-AT 언어에 대한 ER 레이블이 포함된 내보낸 파일의 샘플입니다.](./media/er-multilingual-labels-in-xml.png)

이 형식은 [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md)와 같은 외부 번역 서비스에서 레이블을 자동으로 번역하는 데 사용됩니다. 번역된 레이블을 받으면 해당 레이블을 소유한 ER 구성 요소가 포함된 ER 구성의 초안 버전으로 다시 가져올 수 있습니다. 편집 가능한 ER 구성 요소가 포함된 ER 구성의 초안 버전을 선택하고 레이블 **로드 \> 교환** 을 선택합니다.

![ER 구성 페이지에서 선택한 구성 버전으로 ER 레이블을 가져올 수 있습니다.](./media/er-multilingual-labels-load.png)

번역된 레이블을 선택한 ER 구성으로 가져옵니다. 이 ER 구성에 있는 번역된 레이블이 대체됩니다. 번역된 레이블이 ER 구성에서 누락된 경우 추가됩니다.

## <a name="lifecycle"></a>고객의 요구와 목표에 부합합니다.

편집할 수 있는 ER 구성 요소의 레이블은 구성 요소에 대한 다른 내용과 함께 적절한 버전의 ER 구성에 보관됩니다.

기본 ER 구성 요소의 레이블은 수정 사항을 도입하기 위해 생성하는 ER 구성 요소의 파생 버전에서 참조할 수 있습니다.

ER 버전 관리는 ER 구성 요소의 모든 속성에 대한 레이블 할당을 제어합니다. 레이블 할당에 대한 변경 사항은 제공된 ER 구성 요소의 파생 버전으로 생성된 편집 가능한 ER 구성 요소의 변경 사항(델타) 목록에 기록됩니다. 이러한 변경 사항은 파생 버전이 새 기본 버전으로 재기반될 때 검증됩니다.

## <a name="functions"></a>직렬

내장된 [LISTOFFIELDS](er-functions-list-listoffields.md) ER 함수은 ER 구성 요소의 일부 항목에 대해 구성된 ER 레이블에 액세스할 수 있습니다.

이 항목의 앞부분에서 설명한 대로 모든 [모델](#LinkModelEnum) 또는 [형식](#LinkFormatEnum) ER 열거 값의 **레이블** 및 **설명** 속성은 적절한 ER 구성 요소에서 액세스할 수 있는 ER 레이블에 연결할 수 있습니다. ER 열거형을 인수로 사용하여 **LISTOFFIELDS** 함수를 호출하는 ER 식을 구성할 수 있습니다. 이 표현식은 이 함수의 인수로 정의된 ER 열거의 모든 값에 대한 기록을 포함하는 목록을 반환합니다. 모든 기록에는 ER 열거 값에 연결된 ER 레이블 값이 포함됩니다.

- **레이블** 속성에 연결된 ER **레이블** 값은 반환된 기록의 레이블 필드에 저장됩니다.
- **설명** 속성에 연결된 ER 레이블 값은 반환된 기록의 **설명** 필드에 저장됩니다.

## <a name="performance"></a><a name=performance></a>성능

기본 [언어](#language)로 보고서를 생성하도록 ER 형식 구성 요소를 구성하거나 기본 언어로 콘텐츠가 구문 분석되는 인바운드 문서를 가져오는 경우 ER 실행을 위해 **현재 사용자의 기본 언어 캐시** 기능을 활성화하는 것이 좋습니다. [기능 관리](../../fin-ops/get-started/feature-management/feature-management-overview.md) 작업 공간에서. 이 기능은 특히 ER 공식 및 바인딩의 레이블에 대한 여러 참조를 포함하는 ER 형식 구성 요소와 선호하는 언어로 사용자 메시지를 생성하기 위한 많은 [유효성 검사](general-electronic-reporting-formula-designer.md#TestFormula) 규칙을 포함하는 ER 형식 구성 요소의 성능을 개선하는 데 도움이 됩니다.

ER 구성 버전의 상태를 **초안** 에서 **완료** 로 변경할 때 구성 버전에 ER 레이블이 포함되어 있으면 해당 레이블이 애플리케이션 데이터베이스에 저장됩니다. 스토리지 스키마는 **Accelerate the ER 레이블 스토리지** 기능의 상태에 따라 다릅니다.

- 기능이 활성화되지 않은 경우 모든 레이블은 **ERSOLUTIONVERSIONTABLE** 테이블의 **LABELXML** 필드에 단일 XML 조각으로 저장됩니다.
- 기능이 활성화된 경우 **ERSOLUTIONVERSIONLABELSTABLE** 테이블의 각 언어에 대해 별도의 기록이 생성됩니다. 이 테이블의 **CONTENTS** 필드는 언어별 레이블을 압축된 XML 조각으로 저장합니다.

**기능 관리** 작업 영역에서 **ER 레이블 저장 가속화** 기능을 활성화하는 것이 좋습니다. 대부분의 경우 단일 ER 구성으로 작업할 때 단일 언어의 ER 레이블이 사용되기 때문에 이 기능은 네트워크 대역폭 활용도와 전체 시스템 성능을 개선하는 데 도움이 됩니다.

currenet Finance 인스턴스에서 모든 ER 구성의 레이블을 유지하기 위해 선택한 스토리지 스키마를 적용하려면 다음 단계를 완료하십시오.

1. **조직** >  **관리** 로 >  **이동하여 모든 ER 구성에 대한 스키마를 저장하는 선택한 레이블을 주기적으로 적용** 합니다.
2. **확인** 을 선택합니다.


## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 함수](er-formula-language.md#Functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
