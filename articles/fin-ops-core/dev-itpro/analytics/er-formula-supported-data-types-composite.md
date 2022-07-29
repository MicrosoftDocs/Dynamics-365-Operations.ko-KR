---
title: 전자 보고 공식에 지원되는 복합 데이터 유형
description: 이번에는 전자 보고(ER) 수식에서 지원되는 복합 데이터 유형에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf7178888e39a5f26ae92e77df9c996374b76bf3
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461026"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>전자 보고 공식에 지원되는 복합 데이터 유형

[!include [banner](../includes/banner.md)]

이 주제에서는 [전자 보고(ER)](general-electronic-reporting.md) 표현식에서 지원되는 복합 데이터 유형에 대한 정보를 제공합니다. 복합 데이터 유형은 [클래스](#class), [컨테이너](#container), [기록](#record), [기록 목록](#record-list) 및 [개체](#object)입니다.

## <a name="class"></a><a name="class"></a>클래스

*클래스* 데이터 유형은 공용 애플리케이션 클래스를 참조합니다. ER에서는 참조된 클래스의 모든 공용 메서드에 대해 별도의 필드를 포함하는 [*기록*](#record)로 표시됩니다. 메서드 호출이 매개 변수화되면 메서드를 호출하도록 구성된 ER 표현식에서 적절한 형식의 필수 인수도 지정해야 합니다.

ER 매핑 및 형식 구성 요소에서 데이터 원본으로 표시되고 **클래스** 유형 값을 반환하는 *클래스* 데이터 원본을 추가할 수 있습니다. 이 데이터 소스는 런타임에 호출할 수 있는 클래스의 공용 메서드를 노출합니다.

> [!NOTE]
> 값을 반환하는 메서드만 ER 표현식에서 호출할 수 있습니다.
>
> 0에서 8개의 인수 범위가 있는 메서드만 ER 표현식에서 호출할 수 있습니다.

*클래스* 의 기본값은 **null** 입니다.

다음 그림은 **Class** 타입의 **System information(xInfo)** 데이터 소스를 추가하여 **xInfo** 애플리케이션 클래스의 인스턴스를 만들고 해당 **productName()** 메소드를 호출하여 현재 애플리케이션의 이름을 받는 방식을 보여준다. 현재 애플리케이션의 이름은 ER 데이터 모델의 **소프트웨어 이름(SoftwareName)** 필드에 대해 구성된 `xInfo.productName` 바인딩을 실행하여 런타임에 가져옵니다. 이 바인딩은 현재 모델 매핑에 **시스템 정보(xInfo)** 데이터 소스로 표시되는 **xInfo** 애플리케이션 클래스의 `productName()` 메서드를 호출합니다.

[![ER 모델 매핑 디자이너에서 클래스 데이터 소스 구성.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

다음 그림은 생성된 문서에 제공된 애플리케이션 이름을 입력하도록 ER 형식을 구성하는 방법을 보여줍니다. 사용된 데이터 모델의 **소프트웨어 이름(SoftwareName)** 필드는 ER 형식의 **softwareUsed** XML 요소 아래에 중첩된 **스트링** 구성 요소에 바인딩되었습니다. 따라서 현재 애플리케이션의 이름은 런타임 시 XML 형식으로 생성된 문서의 **softwareUsed** XML 요소에 배치됩니다.

[![ER 형식 디자이너에서 전자 아웃바운드 문서의 구조를 구성합니다.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>다음 포함

*컨테이너* 데이터 유형은 이진 콘텐츠를 보유합니다. *컨테이너* 값을 사용하여 저장소에서 생성된 문서로 특정 정보를 전달할 수 있습니다. ER 프레임워크에서 이 데이터 유형은 생성된 문서에 회사 로고와 같은 미디어 콘텐츠를 넣는 데 자주 사용됩니다.

> [!NOTE]
> 모든 미디어 항목이 *컨테이너* 값으로 표시될 수 있지만 모든 *컨테이너* 값이 미디어 항목을 나타내는 것은 아닙니다. 따라서 *컨테이너* 를 사용하여 생성된 문서에 이미지를 넣도록 ER 형식을 구성했지만 참조된 *컨테이너* 가 미디어 콘텐츠를 반환하지 않으면 다음 예시와 유사한 예외가 throw될 수 있습니다. 오류 코드: 이진(객체), 잘못된 매개변수를 사용하여 생성자에서 메서드를 호출했습니다.

*컨테이너* 의 기본값은 **null** 입니다.

다음 그림은 *컨테이너* 유형의 **Bitmap(Image)** 필드가 **판매 송장** 모델 매핑에서 **컨테이너** 유형의 데이터 모델 **로고** 필드에 바인딩되는 방법을 보여줍니다. 이 바인딩을 통해 **SalesInvoice** 루트 정의용으로 디자인되고 런타임 시 이 모델 매핑을 사용하는 모든 ER 형식에서 회사 로고를 사용할 수 있습니다.

[![ER 모델 매핑 디자이너에서 컨테이너 유형의 필드를 바인딩합니다.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>기록

*기록* 는 각각 [기본](er-formula-supported-data-types-primitive.md) 데이터 유형 또는 복합 데이터 유형의 값과 연관된 명명된 필드의 모음입니다. 일반적으로 *기록* 는 기록 목록의 단일 기록을 나타내는 데 사용됩니다. 이 경우 모든 항목은 개별 필드, 메서드 및 관계를 나타냅니다.

*기록* 의 기본값은 **비어** 있습니다.

> [!NOTE]
> 빈 *기록* 의 필드 값을 가져오면 해당 데이터 형식의 기본값이 반환됩니다.

다음 함수를 사용하여 *기록* 를 얻을 수 있습니다.

- [먼저](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [빈 기록](er-functions-record-emptyrecord.md)
- [널컨테이너](er-functions-record-nullcontainer.md)

*기록* 값 변환에 대한 자세한 내용은 [목록 범주의 ER 함수 목록](er-functions-category-list.md)을 참조하십시오.

## <a name="record-list"></a><a name="record-list"></a>기록 목록

*기록 목록* 은 *기록* 유형의 항목 목록입니다. 일반적으로 *기록 목록* 은 데이터베이스 테이블에서 가져온 기록 목록을 나타내는 데 사용됩니다.

기본적으로 *기록 목록* 의 기록은 순차적으로 액세스됩니다. 특정 기록에 액세스하려면 [INDEX](er-functions-list-index.md) 함수를 사용하고 *정수* 색인을 지정할 수 있습니다.

*기록 목록* 의 기본값은 **비어** 있습니다. [ISEMPTY](/er-functions-list-isempty.md) 함수를 사용하여 *기록 목록* 이 비어 있는지 여부를 평가할 수 있습니다.

> [!NOTE]
> *기록 목록* 이 비어 있는 경우 *기록* 에 대한 필드 값을 가져오려고 하면 런타임에 예외가 throw됩니다. 이 유형의 런타임 예외를 방지하는 방법을 알아보려면 [빈 목록 사례 고려](er-components-inspections.md#i9)를 참조하십시오.

다음 함수를 사용하여 *기록 목록* 을 시작할 수 있습니다.

- [모든 아이템](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [빈 목록](er-functions-list-emptylist.md)
- [목록](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

*기록 목록* 값 변환에 대한 자세한 내용은 [목록 범주의 ER 함수 목록](er-functions-category-list.md)을 참조하십시오. *기록 목록* 항목을 도입하고 애플리케이션 데이터로 채운 다음 데이터를 사용하여 비즈니스 문서를 생성하는 방법을 배우려면 [사용자 지정 보고서를 인쇄하는 새 ER 솔루션 디자인](er-quick-start1-new-solution.md)을 참조하십시오.

## <a name="object"></a><a name="object"></a>개체

*객체* 는 *클래스* 의 상태 저장 인스턴스를 참조합니다. 일반적으로 *개체* 는 소스 코드에서 시작됩니다. 이후 ER 모델 매핑으로 전달되고 실행 컨텍스트에 대한 세부 정보를 제공합니다.

*개체* 의 기본값은 **null** 입니다.

다음 그림은 생성된 송장에 대한 정보를 소스 코드에서 **프로젝트 송장** 모델 매핑으로 전달하기 위해 *개체* 유형의 **ReportDataContract** 데이터 원본이 추가되는 방법을 보여줍니다. 예를 들어, 송장 인스턴스 텍스트는 실행 컨텍스트의 일부로 전달됩니다. 이 텍스트는 ER 데이터 모델의 **참고** 필드에 대해 구성된 `ReportDataContract.parmInvoiceInstanceText` 바인딩을 실행하여 런타임 시 소스 코드에서 가져옵니다. 이 바인딩은 현재 모델 매핑에 **ReportDataContract** 데이터 소스로 표시되는 **PSAProjInvoiceContract** 애플리케이션 클래스의 `parmInvoiceInstanceText()` 메서드를 호출합니다.

[![ER 모델 매핑 디자이너에서 개체 데이터 소스를 구성합니다.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

소스 코드에서 실행 중인 ER 솔루션으로 실행 컨텍스트의 세부 정보를 전달하는 방법을 배우려면 [디자인된 보고서를 호출하는 애플리케이션 아티팩트 개발](er-quick-start1-new-solution.md#DevelopCustomCode)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 공식 언어](er-formula-language.md)
- [지원되는 기본 데이터 유형](er-formula-supported-data-types-primitive.md)
