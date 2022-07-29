---
title: 전자 보고 형식의 DATA COLLECTION 데이터 소스 사용
description: 이번에는 전자 보고(ER) 형식의 DATA COLLECTION 데이터 소스를 사용하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 185fb9a33cb4cc655dfdf640b4c239d617426c64
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461031"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>전자 보고 형식의 DATA COLLECTION 데이터 소스 사용

[!include [banner](../includes/banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 프레임워크의 작업 디자이너를 사용하여 다양한 형식의 아웃바운드 문서를 생성하는 데 사용되는 ER 솔루션의 형식 구성 요소를 구성할 수 있습니다. 구성된 형식 구성 요소의 계층 구조는 다양한 형식 요소로 구성됩니다. 이러한 형식 요소는 생성된 문서를 런타임에 필요한 정보로 채우는 데 사용됩니다. 기본적으로 ER 형식을 실행할 때 형식 요소는 형식 계층에 표시된 순서대로 위에서 아래로 하나씩 실행됩니다.

ER이 바인딩을 포함하는 형식 요소를 실행할 때 해당 바인딩의 공식이 실행되고 형식 요소가 생성된 문서에 값을 추가합니다. 예를 들어 바인딩은 데이터 모델 필드의 값을 형식 요소에 전달할 수 있습니다. DATA COLLECTION 데이터 소스를 구성하여 런타임에 데이터 모델 필드의 값을 수집하고, 값 합산을 수행하고, 수집된 값으로 생성된 문서를 채울 수 있습니다. 이 접근 방식을 사용하려면 구성된 DATA COLLECTION 데이터 소스가 데이터 모델 필드의 값을 형식 요소에 전달하는 데 사용되도록 초기 바인딩을 변경하십시오. DATA COLLECTION 데이터 소스를 통해 값을 전달하여 추가 사용을 위해 필요한 세부 정보를 수집할 수 있습니다.

DATA COLLECTION 데이터 소스를 구성할 때 데이터 소스에서 관리할 값 유형을 지정하십시오. 현재 값 수집을 위해 다음 [데이터 유형](er-formula-supported-data-types-primitive.md)이 지원됩니다.

- 부울
- 날짜
- 날짜 시간
- GUID
- Int64
- 정수
- 실수
- 스트링
- 시간

DATA COLLECTION 데이터 소스의 메소드를 사용하여 수집을 위해 `Collect(Value)` 데이터 소스에 값을 전달할 수 있습니다. 이 방법에서 `Value` 인수는 상수 또는 관련 데이터 유형의 데이터 소스 필드의 유효한 경로입니다.

DATA COLLECTION 데이터 소스의 `Result` 속성을 사용하여 수집된 값 목록에 액세스합니다. 이 속성은 [기록 목록](er-formula-supported-data-types-composite.md#record-list)을 반환합니다. 기록 목록의 기록에는 수집된 값에 액세스하는 데 사용할 수 있는 `Value` 필드가 포함되어 있습니다.

기본적으로 DATA COLLECTION 데이터 소스는 고유한 값만 수집합니다.

모든 값을 수집하려면 구성된 DATA COLLECTION 데이터 소스의 **모든 값 수집** 필드를 **예** 로 설정하십시오. **모든 값 수집** 필드가 **예** 로 설정되면 `Sum(Flag)` 매개 변수화된 속성을 사용할 수 있습니다. 이 속성을 사용하여 현재 수집된 모든 값의 총액을 가져올 수 있습니다. 이 속성에서 `Flag` 인수는 총 값을 재설정해야 하는지 여부를 나타내는 데 사용되는 [부울](er-formula-supported-data-types-primitive.md#boolean) 값입니다.

- **False** 값이 제공되면 이전에 수집된 금액에서 합산이 계속됩니다.
- **True** 값이 제공되면 새로운 합산이 시작됩니다.

현재 합산에 지원되는 데이터 유형은 다음과 같습니다.

- Int64
- 정수
- 실수

이 기능에 대해 자세히 알아보려면 다음 예시를 완료하십시오.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>예:, DATA COLLECTION 데이터 소스를 사용하여 계산 및 합산을 수행하도록 ER 형식 구성

이 예는 시스템 관리자 또는 전자 보고 함수 컨설턴트 역할의 사용자가 누계를 계산하고 합산된 값을 수집하는 데 사용되는 DATA COLLECTION 데이터 소스가 있는 ER 형식을 구성할 수 있는 방법을 보여줍니다.

이 예의 절차는 Microsoft Dynamics 365 Finance의 USMF 회사에서 완료할 수 있습니다.

### <a name="upload-and-use-the-provided-er-solution"></a>제공된 ER 솔루션 업로드 및 사용

1. [샘플 ER 구성을 가져옵니다](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [구성 공급자를 활성화합니다](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [가져온 모델 매핑을 검토합니다](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [가져온 형식을 검토합니다](er-defer-sequence-element.md#review-the-imported-format).
5. [가져온 형식을 실행합니다](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>제공된 ER 솔루션의 형식 실행

1. **형식 디자이너** 페이지에서 **실행** 을 선택합니다.
2. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택합니다.
3. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![초기 포맷 실행 결과가 포함된 다운로드 파일](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>ER 솔루션의 형식을 수정하여 누적 세액 계산

트랜잭션 볼륨이 현재 예시의 볼륨보다 훨씬 큰 경우 합산에 필요한 시간이 증가하고 성능 문제가 발생할 수 있습니다. 형식 설정을 변경하여 이러한 성능 문제를 방지할 수 있습니다. 생성된 보고서에 포함하기 위해 세금 값에 액세스하기 때문에 해당 정보를 재사용하여 세금 값을 합산할 수 있습니다.

1. **형식 디자이너** 페이지의 **매핑** 탭에서 **루트 추가** 를 선택합니다.
2. **데이터 원본 추가** 대화 상자에서 **함수** \> **데이터 컬렉션** 을 선택합니다.
3. **'데이터 수집' 데이터 원본 속성** 대화 상자에서 다음 단계를 따르십시오.

    1. **이름** 필드에 **CollectedTaxValues** 를 입력합니다.
    2. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    3. **모든 값 수집** 필드에서 **예** 를 선택합니다.
    4. **확인** 을 선택합니다.

4. **Report\\Lines\\Record\\TaxAmount** 숫자 형식 요소를 선택하십시오.

    > [!NOTE]
    > 현재 이 요소에 대한 `@.Value` 바인딩이 구성되어 있습니다. 따라서 `model.Data.List.Value` 필드의 세금 값으로 채워진 경우 문서가 생성됩니다.

5. **수식 편집** 을 선택합니다.
6. **수식 디자이너** 페이지에서 다음 단계를 수행합니다.

    1. **수식** 필드에서 `@.Value`로 `CollectedTaxValues.Collect(@.Value)` 바꿉니다.
    2. 변경 사항을 저장하고 페이지를 닫습니다.

    > [!NOTE]
    > 새 바인딩은 생성된 문서에 동일한 세금 값을 전달합니다. 그러나 이러한 값은 **CollectedTaxValues** 데이터 소스에서도 수집됩니다.

7. **Report\\Lines\\Record\\RunningTotal** 숫자 형식 요소를 선택하십시오.
8. **수식 편집** 을 선택합니다.
9. **수식 디자이너** 페이지에서 다음 단계를 수행합니다.

    1. **수량** 필드에 `CollectedTaxValues.Sum(false)`을(를) 입력합니다.
    2. 변경 사항을 저장하고 페이지를 닫습니다.

    > [!NOTE]
    > 새 바인딩은 이미 입력된 세금 값의 총액을 생성된 문서로 전달합니다.

    ![형식 디자이너 페이지에서 업데이트된 바인딩이 있는 숫자 요소](./media/er-data-collection-data-sources-02.png)

10. **저장** 을 선택한 다음 **실행** 을 선택합니다.
11. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택합니다.
12. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![수정된 포맷 실행 결과가 포함된 다운로드 파일](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>징수된 세금 값 목록을 평가하는 형식 수정

1. **형식 디자이너** 페이지의 **형식** 탭에서 **Report\\Lines\\Record\\RunningTotal** 숫자 형식 요소를 선택한 후 다음 단계를 수행합니다.

    1. **숫자 유형** 필드에서 값을 **실수** 에서 **정수** 로 변경하십시오.
    2. **숫자 형식** 필드에서 값을 **F2** 에서 **F0** 으로 변경합니다.

3. **매핑** 탭에서 **수식 편집** 을 선택합니다.
4. **수식 디자이너** 페이지에서 다음 단계를 수행합니다.

    1. **수량** 필드에 `COUNT(CollectedTaxValues.Result)`을(를) 입력합니다.
    2. 변경 사항을 저장하고 페이지를 닫습니다.

    > [!NOTE]
    > 새 바인딩은 세금 값이 수집되는 목록의 기록 수를 생성된 문서에 전달합니다.

5. **저장** 을 선택한 다음 **실행** 을 선택합니다.
6. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택합니다.
7. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![다른 수정된 형식 실행의 결과가 포함된 다운로드된 파일](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>누계를 계산하고 데이터를 수집해야 하는 경우 DATA COLLECTION 데이터 소스를 사용하는 것과 내장된 DATA COLLECTION 함수를 사용하는 것의 차이점은 무엇입니까?

[DATA COLLECTION](er-functions-category-data-collection.md) 데이터 소스와 기본 제공 DATA COLLECTION 함수는 생성된 아웃바운드 문서에 전달된 정보를 기반으로 데이터 수집, 합산 및 계산에 사용할 수 있습니다. 그러나 어떤 기술을 사용할지 결정할 때 다음 사항을 고려해야 합니다.

| 데이터 소스 | 내장 함수 |
|-------------| ------------------ |
| 값만 수집됩니다. | <p>명명된 값이 수집됩니다. 따라서 개별 값 그룹에 대해 합계를 계산할 수 있습니다.</p><p>또한 그룹을 목록으로 추출할 수 있습니다.</p><p>텍스트 값도 수집할 수 있습니다.</p> |
| 고유 값이 자동으로 수집됩니다. | 수집된 값에서 고유한 값 목록을 추출하려면 추가 설정이 필요합니다. |
| 성능은 수집된 값의 양에 따라 다릅니다. | 실제로 성능은 수집된 값의 양에 의존하지 않습니다. |
| 이 기술은 모든 유형의 아웃바운드 문서에 적용됩니다. | 이 기술은 텍스트 및 XML 문서에만 적용됩니다. |

## <a name="additional-resources"></a>추가 리소스

- [계산 및 합산을 수행하는 형식 구성](./tasks/er-format-counting-summing-1.md)
- [ER 형식의 시퀀스 요소 실행 연기](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
