---
title: ER 애플리케이션별 매개 변수를 사용하도록 조회 데이터 소스 구성
description: 이번에는 ER 애플리케이션별 매개 변수를 사용하도록 전자 보고(ER) 형식의 조회 데이터 소스를 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: c028b01aa2889a517bee69de46411ada12d6fe25
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "8461022"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>ER 애플리케이션별 매개 변수를 사용하도록 조회 데이터 소스 구성 

[!include[banner](../includes/banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 애플리케이션별 매개 변수 기능을 사용하면 추상 규칙 집합을 기반으로 하도록 ER 형식으로 데이터 필터링을 구성할 수 있습니다. 이 규칙 집합은 ER 형식에서 사용할 수 있는 **조회** 유형의 데이터 원본을 사용하도록 구성할 수 있습니다. 이후 해당 ER 형식의 **조회** 데이터 소스와 현재 법인 데이터의 설정을 기반으로 자동 생성되는 UI(사용자 인터페이스)를 사용하여 ER 구성 요소 디자이너를 넘어 실제 규칙을 지정할 수 있습니다. 결국 이 ER 형식이 실행될 때 ER 형식의 **조회** 데이터 소스에서 지정된 규칙에 액세스합니다.

> [!NOTE]
> 편집 가능한 ER 형식의 구성된 데이터 소스를 사용하여 실제 규칙을 구성하는 데 사용되는 애플리케이션 데이터를 지정합니다.

[ER 작업 디자이너](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base)를 사용하여 **조회** 유형의 데이터 소스를 ER 형식으로 가져옵니다. 다음을 포함하여 추상 규칙이 어떻게 보이는지 설명하도록 데이터 소스를 구성해야 합니다.

   - 단일 규칙을 지정하기 위해 값이 제공되는 특정 데이터 유형의 매개 변수 세트.
   - 이 규칙이 가장 적절한 것으로 간주될 때 단일 규칙에 의해 반환되는 특정 데이터 유형의 값 유형입니다.

구성된 규칙에서 반환되는 값 유형에 따라 다음 유형의 **조회** 데이터 원본을 구성할 수 있습니다.

   - 모델 열거 값을 반환해야 하는 경우 **데이터 모델\조회** 유형을 사용합니다.
   - 애플리케이션 열거형 값 또는 애플리케이션 [확장 데이터 형식 값](../extensibility/extensible-edts.md)을 반환해야 하는 경우 **Dynamics 365 Operations\Lookup** 유형을 사용합니다.
   - 형식 열거 값을 반환해야 하는 경우 **형식 열거\조회** 유형을 사용합니다.

다음 그림은 샘플 ER 형식에서 형식 열거를 구성하는 방법을 보여줍니다.

   ![구성된 조회 데이터 소스의 기반으로 형식 열거를 표시합니다.](./media/er-lookup-data-sources-img1.gif)

다음 그림은 생성된 보고서의 다른 섹션에서 다양한 유형의 세금을 보고하도록 구성된 형식 구성 요소를 보여줍니다.

   ![다른 유형의 세금을 별도로 보고하는 형식 섹션을 표시합니다.](./media/er-lookup-data-sources-img2.png)

다음 그림은 ER Operations 디자이너가 **형식 열거\조회** 유형의 데이터 소스를 추가하는 방법을 보여줍니다.  추가된 데이터 소스는 `List of taxation levels` 형식 열거형 값을 반환하도록 구성됩니다.

   ![형식 열거\조회 유형의 ER 데이터 소스를 추가합니다.](./media/er-lookup-data-sources-img3.gif)

다음 그림은 **모델** 데이터 소스의 **Model.Data.Tax** 기록 목록에 있는 **코드** 필드를 구성된 모든 규칙에 대해 지정해야 하는 매개 변수로 사용하도록 추가된 데이터 소스를 구성하는 방법을 보여줍니다.

![Format enumeration\Lookup 유형의 추가된 데이터 소스의 매개 변수를 구성합니다.](./media/er-lookup-data-sources-img4.gif)

추가된 `Model.Data.Tax` 데이터 소스는 **TaxTable** 애플리케이션 테이블의 기록에 액세스하여 구성된 모든 규칙에 대해 세금 코드를 지정하도록 구성됩니다.

   ![형식 열거\조회 유형의 단일 회사 조회 데이터 원본을 검토합니다.](./media/er-lookup-data-sources-img5.gif)

구성된 데이터 소스의 구조에 자동으로 맞춰지는 UI를 사용하여 선택한 ER 형식에 대한 조회 규칙을 설정할 수 있습니다. 현재 이 UI에서는 각 규칙에 대해 반환된 값을 `List of taxation levels` 형식 열거 값으로 지정하고 세금 코드를 매개 변수로 지정해야 합니다.

   ![구성된 데이터 소스에 대한 규칙을 설정합니다.](./media/er-lookup-data-sources-img6.gif)

다음 그림은 필수 매개 변수를 제공하는 구성된 **조회** 데이터 원본을 호출하도록 **계산된 필드** 유형의 `Model.Data.Summary.LevelByLookup` 데이터 원본을 구성할 수 있는 방법을 보여줍니다. 런타임 시 이 호출을 처리하기 위해 ER은 정의된 순서로 구성된 규칙 목록을 살펴보고 제공된 조건을 충족하는 첫 번째 규칙을 찾습니다. 이 예시에서 제공된 것과 일치하는 세금 코드가 포함된 규칙입니다. 결과적으로 가장 적절한 규칙이 발견되고 발견된 규칙에 대해 구성된 열거 값이 이 데이터 소스에서 반환됩니다.

> [!NOTE]
> 적용 가능한 규칙이 없으면 예외가 발생합니다. 이러한 예외를 방지하려면 구성되지 않은 값 또는 값이 제공되지 않은 경우를 처리하도록 규칙 목록 끝에 추가 규칙을 구성하십시오. **\*비어 있지 않음**\* 및 **\*비어 있음**\* 옵션을 적절히 사용합니다.  
>
> ![구성된 조회 데이터 원본을 호출할 데이터 원본을 추가합니다.](./media/er-lookup-data-sources-img7.png)

편집 가능한 조회 데이터 소스에 대해 **회사 간** 옵션을 **예** 로 설정하면 이 데이터 소스의 매개 변수 세트에 새로운 필수 **회사** 매개 변수를 추가합니다. 조회 데이터 소스가 호출될 때 런타임에 **Company** 매개 변수의 값을 지정해야 합니다. 런타임 시 회사 코드를 지정하면 이 회사에 대해 구성된 규칙을 사용하여 가장 적합한 규칙을 찾고 해당 값을 반환합니다. 다음 그림은 이 작업을 수행하는 방법과 편집 가능한 데이터 소스의 매개 변수 집합이 변경되는 방법을 보여줍니다.

   ![형식 열거\조회 유형의 회사 간 조회 데이터 원본을 검토합니다.](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> 편집 가능한 ER 형식의 이 조회 데이터 소스에 대한 규칙 세트를 구성하려면 모든 회사를 별도로 선택하십시오. 조회 설정이 완료되지 않은 회사의 코드로 회사 간 조회가 호출되면 런타임에 예외가 발생합니다.
>
> 회사 간 **조회** 데이터 원본으로 ER 형식을 실행하는 사용자에게 이 데이터 원본 범위에 있는 모든 회사의 데이터에 액세스할 수 있는 권한을 부여해야 합니다. 그렇지 않으면 런타임에 예외가 발생합니다.

버전 10.0.19부터 **조회** 데이터 원본의 확장된 기능을 사용할 수 있습니다. 편집 가능한 조회 데이터 원본에 대해 **확장** 옵션을 **예** 로 설정하면 구성된 조회 데이터 원본이 구성된 규칙 집합을 분석하기 위한 추가 기능을 제공하는 구조화된 데이터 원본으로 변환됩니다. 다음 그림은 이 변환을 보여줍니다.

   ![형식 열거\조회 유형의 구조적 조회 데이터 원본을 검토합니다.](./media/er-lookup-data-sources-img9.gif)

- **Lookup** 하위 항목은 제공된 매개 변수 집합을 기반으로 구성 가능한 규칙 집합에서 가장 적절한 규칙을 찾는 함수로 설계되었습니다.
- **IsLookupResultSet** 하위 항목은 기본 열거 데이터 소스의 제공된 값을 수락하고 제공된 열거 값이 반환된 값으로 구성된 규칙 집합에 하나 이상의 규칙이 포함된 경우 *부울* 값 **True** 를 반환하는 함수로 설계되었습니다. . 이 함수는 제공된 열거형 값을 반환하도록 구성된 규칙이 없는 경우 **False** 의 *부울* 값을 반환합니다.
- **설정** 하위 항목은 구성된 규칙 집합을 기록 목록의 기록으로 반환하는 함수로 설계되었습니다. 구성된 규칙의 반환된 값과 매개 변수 집합은 반환된 모든 기록에 관련 데이터 유형의 필드로 표시됩니다.

    - 반환된 값은 **조회 결과** 필드로 표시됩니다.
    - 구성된 매개 변수는 매개 변수 이름이 있는 필드로 표시됩니다(이 예시에서는 **코드** 필드).

**조회** 데이터 원본을 구성하는 방법에 대한 자세한 내용은 [법인별로 지정된 매개 변수를 사용하도록 ER 형식 구성](er-app-specific-parameters-configure-format.md)을 참조하십시오. 조회 규칙을 설정하는 방법을 배우려면 [법인당 ER 형식의 매개 변수 설정](er-app-specific-parameters-set-up.md)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[법인별로 지정된 매개 변수를 사용하도록 ER 형식 구성](er-app-specific-parameters-configure-format.md)

[법인별 ER 형식의 매개 변수 설정](er-app-specific-parameters-set-up.md)
