---
title: GROUPBY 데이터 소스를 사용하여 그룹 기록 및 집계 계산
description: 이번에는 전자 보고(ER)에서 GROUPBY 유형 데이터 소스를 사용하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a6cdc486c5f799bdedafa38e90be989fd328c96
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461044"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>GROUPBY 데이터 소스를 사용하여 그룹 기록 및 집계 계산

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 모델 매핑 또는 형식을 구성할 때 **GroupBy** 유형의 필수 데이터 소스를 [추가](#AddMmDataSource2)할 수 있습니다.

디자인 타임에 **GroupBy** 데이터 원본은 다음 요소를 식별하도록 구성됩니다.

- 런타임에 그룹화될 기록을 포함하는 [기본 데이터 소스](#BaseDataSource)
- 런타임 시 기록 그룹화에 사용되는 기본 데이터 소스의 [그룹화 필드](#GroupingFields)
- 런타임 시 검색된 각 그룹에 대해 수행될 집계 계산을 지정하는 [집계 함수](#AggregateFunctions)

런타임에 구성된 **GroupBy** 데이터 원본은 그룹화 필드에서 동일한 값을 가진 기록을 그룹화한 다음 기록 목록을 반환합니다. 각 기록은 단일 그룹을 나타냅니다. 각 그룹에 대해 데이터 원본은 초기 기록을 그룹화한 필드 값, 계산된 집계 함수의 값 및 그룹에 속한 기본 데이터 원본의 기록 목록을 노출합니다.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>집계 함수

런타임 시 각 기록 그룹에 대해 모든 집계 계산이 수행됩니다. 이 계산은 **GroupBy** 유형의 편집 가능한 데이터 원본에서 그룹화를 위해 선택한 데이터 원본의 기록에 있는 식 또는 단일 필드 값을 사용하여 수행됩니다. 다음 집계 함수가 현재 지원됩니다.

- **AVG** – 이 함수는 그룹에 있는 값의 평균을 반환합니다. 숫자 필드에만 사용할 수 있습니다.
- **COUNT** – 이 함수는 그룹에서 발견된 항목의 수를 반환합니다.
- **Min** – 이 함수는 그룹의 값 중 최소값을 반환합니다.
- **Max** – 이 함수는 그룹의 값 중 최대값을 반환합니다.
- **SUM** – 이 함수는 그룹에 있는 모든 값의 합계를 반환합니다. 숫자 필드에만 사용할 수 있습니다.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>실행 위치

**GroupBy** 데이터 소스를 편집하고 그룹화해야 하는 기록이 포함된 기본 데이터 소스를 지정하면 시스템은 해당 **GroupBy** 데이터 소스를 실행하기 위한 가장 효율적인 [위치](#ExecutionLocation)를 자동으로 감지합니다. 기본 데이터 원본이 [쿼리 가능](er-functions-list-filter.md#usage-notes)한 경우(즉, 데이터베이스 수준에서 실행할 수 있는 경우) 애플리케이션 데이터베이스도 편집 가능한 **GroupBy** 데이터 원본의 실행 위치로 지정됩니다. 그렇지 않으면 애플리케이션 서버 메모리가 실행 위치로 지정됩니다.

구성된 데이터 소스에 적용 가능한 위치를 선택하여 자동으로 감지된 실행 위치를 수동으로 변경할 수 있습니다. 선택한 실행 위치를 적용할 수 없는 경우 디자인 타임에 [유효성 검사 오류](er-components-inspections.md#i5)가 발생합니다.

> [!TIP]
> 많은 수의 기록을 노출하는 데이터 원본을 그룹화하려면 데이터베이스 위치를 사용하는 것이 좋습니다.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>메모리 소비

기본적으로 **GroupBy** 데이터 소스가 메모리에서 실행되는 경우 애플리케이션 서버 메모리는 검색된 각 그룹에 속하는 기본 데이터 소스의 기록을 단일 그룹의 기록으로 저장하는 데 사용됩니다. 메모리 소비를 줄이기 위해 집계된 함수만 계산하도록 구성되고 해당 그룹의 기록이 런타임에 사용되지 않는 경우 **GroupBy** 데이터 원본에 대한 기록 저장소를 억제할 수 있습니다. 이러한 방식으로 메모리 소비를 줄이려면 **기능 관리** 작업 공간에서 **기록 그룹화가 집계 계산에만 사용되는 경우 ER에서 메모리 사용 줄이기** 를 활성화하십시오.

## <a name="alternatives"></a><a name="Alternatives"></a>대안

[다른](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) 유형의 데이터 소스 또는 ER 내장 함수를 사용하여 유사한 집계를 계산할 수 있습니다.

이 기능에 대해 자세히 알아보려면 다음 예시를 완료하십시오.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>예:, 집계 계산 및 기록 그룹화에 GROUPBY 데이터 원본 사용

이 예는 시스템 관리자 또는 전자 보고 함수 컨설턴트 역할의 사용자가 집계 함수 및 그룹 기록을 계산하는 데 사용되는 **GROUPBY** 데이터 소스가 있는 ER 모델 매핑을 구성할 수 있는 방법을 보여줍니다. 이 모델 매핑은 Intrastat 선언이 생성될 때 제어 보고서를 인쇄하는 데 사용됩니다. 해당 보고서를 통해 보고된 통계 내 거래를 검토할 수 있습니다.

이 예의 절차는 Microsoft Dynamics 365 Finance의 **DEMF** 회사에서 완료할 수 있습니다. 

### <a name="prepare-sample-data"></a>샘플 데이터 준비

Intrastat 페이지에 보고할 **Intrastat** 트랜잭션이 있는지 확인하십시오. 이 예시에서는 **전송** 필드를 기준으로 트랜잭션을 그룹화하므로 서로 다른 전송 코드에 대한 트랜잭션이 있어야 합니다.

![Intrastat 페이지에서 Intrastat 트랜잭션을 준비합니다.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>ER 프레임워크 구성

ER 프레임워크 구성의 단계에 따라 [ER 매개 변수의 최소 집합](er-quick-start2-customize-report.md#ConfigureFramework)을 설정합니다. ER 프레임워크를 사용하여 ER 모델 매핑을 설계하기 시작하기 전에 이 설정을 완료해야 합니다.

### <a name="import-the-standard-er-format-configuration"></a>표준 ER 형식 구성 가져오기

[표준 ER 형식 구성 가져오기](er-quick-start2-customize-report.md#ImportERSolution1)의 단계에 따라 Dynamics 365 Finance의 현재 인스턴스에 표준 ER 구성을 추가합니다. 저장소에서 **Intrastat 모델** 구성의 버전 1을 가져옵니다.

### <a name="create-a-custom-data-model-configuration"></a>사용자 지정 데이터 모델 구성 만들기

[사용자 지정 데이터 모델 구성 추가](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration)의 단계에 따라 가져온 **Intrastat 모델** 구성에서 파생된 새 **Intrastat 모델(Litware)** ER 데이터 모델 구성을 수동으로 추가합니다.

### <a name="configure-a-custom-data-model-component"></a>사용자 지정 데이터 모델 구성 요소 구성

다음 단계에 따라 파생된 **Intrastat 모델(Litware)** 데이터 모델에 필요한 변경을 수행하여 필요한 세부 정보가 있는 전송 코드를 노출하는 데 사용할 수 있습니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **Intrastat 모델(Litware)** 을 선택합니다.
3. **디자이너** 를 선택합니다.
4. **데이터 모델 디자이너** 페이지의 모델 트리에서 **Intrastat** 를 선택합니다.
5. **새로 만들기** 를 선택하여 선택한 **Intrastat** 노드에 대해 새 중첩 노드를 추가합니다. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **이름** 필드에 **Transport** 를 입력합니다.
    2. **항목 유형** 필드에서 **기록 목록** 을 선택하십시오.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

6. **새로 추가** 를 선택하여 방금 추가한 **전송** 노드에 대한 새 중첩 노드를 추가합니다. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **이름** 필드에 **코드** 를 입력합니다.
    2. **항목 유형** 필드에서 **스트링** 을 선택하십시오.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

7. **새로 만들기** 를 선택하여 **전송** 노드에 대해 다른 새 중첩 노드를 추가합니다. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **이름** 필드에 **TotalInvoicedAmount** 를 입력합니다.
    2. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

8. **새로 만들기** 를 선택하여 **전송** 노드에 대해 다른 새 중첩 노드를 추가합니다. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **이름** 필드에 **NumberOfTransactions** 를 입력하십시오.
    2. **항목 유형** 필드에서 **정수** 를 선택합니다.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

9. **새로 만들기** 를 선택하여 **전송** 노드에 대해 다른 새 중첩 노드를 추가합니다. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **이름** 필드에 **트랜잭션** 을 입력합니다.
    2. **항목 유형** 필드에서 **기록 목록** 을 선택하십시오.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

10. 방금 추가한 **트랜잭션** 노드의 경우 **노드** FastTab에서 **항목 참조 전환** 을 선택합니다.
11. **항목 참조 전환** 대화 상자의 데이터 모델 트리에서 **CommodityRecord** 를 선택합니다. 이후 **확인** 을 선택합니다.

![ER 데이터 모델 디자이너에서 구성된 데이터 모델.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>맞춤형 데이터 모델 설계 완료

[데이터 모델 디자인 완료](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration)의 단계에 따라 파생된 **Intrastat 모델(Litware)** 데이터 모델의 디자인을 완료합니다.

### <a name="create-a-new-model-mapping-configuration"></a>새 모델 매핑 구성 만들기

[새 모델 매핑 구성 만들기](er-quick-start1-new-solution.md#CreateModelMapping)의 단계에 따라 파생된 **Intrastat 모델(Litware)** 구성에 대한 새 **Intrastat 샘플 매핑** ER 모델 매핑 구성을 수동으로 추가합니다.

### <a name="add-a-new-model-mapping-component"></a>새 모델 매핑 구성 요소 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **Intrastat 모델** 구성을 확장합니다.
3. **Intrastat 샘플 매핑** 구성을 선택합니다.
4. **디자이너** 를 선택하여 매핑 목록을 엽니다.
5. **삭제** 를 선택하여 기존 매핑 구성 요소를 제거합니다.
6. **새로 만들기** 를 선택하여 새 매핑 구성 요소를 추가합니다.
7. **정의** 필드에서 **Intrastat** 를 선택하십시오.
8. **이름** 필드에 **Intrastat 매핑** 을 입력합니다.
9. **Designer** 를 선택하여 새 매핑을 구성합니다.

### <a name="design-the-added-model-mapping-component"></a>추가된 모델 매핑 구성 요소 설계

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>애플리케이션 테이블에 액세스하기 위한 데이터 소스 추가

Intrastat 트랜잭션의 세부 사항이 포함된 애플리케이션 테이블에 액세스하도록 데이터 소스를 구성하십시오.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **Dynamics 365 for Operations\\테이블 레코드** 를 선택합니다.
2. **데이터 원본** 창에서 **루트 추가** 를 선택하여 **Intrastat** 테이블에 액세스하는 데 사용할 새 데이터 원본을 추가합니다. **Intrastat** 테이블의 각 기록은 단일 Intrastat 트랜잭션을 나타냅니다.
3. **데이터 원본 속성** 대화 상자의 **이름** 필드에 **트랜잭션** 을 입력합니다.
4. **테이블** 필드에 **Intrastat** 를 입력합니다.
5. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Intrastat 트랜잭션을 그룹화하기 위해 데이터 소스 추가

Intrastat 트랜잭션을 그룹화하고 집계 함수를 계산하도록 **GroupBy** 데이터 소스를 구성합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 원본** 형식 창에서 **Functions\\Group by** 를 선택합니다.
2. **데이터 원본** 창에서 **루트 추가** 를 선택하여 Intrastat 트랜잭션을 그룹화하고 집계 함수를 계산하는 데 사용할 새 데이터 원본을 추가합니다.
3. **데이터 원본 속성** 대화 상자의 **이름** 필드에 **TransportRecord** 를 입력합니다.
4. 그룹화 조건을 구성하려면 **그룹화 기준 편집** 을 선택합니다.
5. **'그룹화 기준' 매개 변수 편집** 페이지의 오른쪽 창에 있는 데이터 원본 목록에서 **트랜잭션** 데이터 원본을 선택하고 확장합니다.
6. **트랜잭션** 데이터 원본이 구성된 **GroupBy** 데이터 원본의 <a name="BaseDataSource">기본 데이터 원본</a>으로 선택되었음을 나타내려면 **그룹화할 대상에 \> 필드 추가** 를 선택합니다. **트랜잭션** 데이터 소스의 기록이 그룹화되고 이 데이터 소스의 필드 값이 집계 함수의 계산에 사용됩니다.
7. **트랜잭션\전송** 필드를 선택한 다음 **그룹화 필드에 \> 필드 추가** 를 선택하여 기본 데이터 원본의 **전송** 필드가 구성된 **GroupBy** 데이터 원본에 대한 <a name="GroupingFields">그룹화 기준</a>으로 선택되었음을 나타냅니다. 즉, **트랜잭션** 데이터 원본의 기록은 **Transport** 필드의 값을 기준으로 그룹화됩니다. 구성된 **GroupBy** 데이터 소스의 모든 기록은 기본 데이터 소스의 기록에서 발견된 단일 전송 코드를 나타냅니다.
8. **Transaction\AmountMST** 필드를 선택하고 다음 단계를 수행합니다.

    1. 이 필드에 대해 <a name="AggregateFunctions">집계 함수</a>가 계산됨을 나타내려면 **집계 필드에 \> 필드 추가** 를 선택합니다.
    2. **집계** 창의 선택한 **Transaction\AmountMST** 필드에 대해 추가된 기록의 **방법** 필드에서 **Sum** 함수를 선택합니다.
    3. **이름** 선택적 필드에 **TotalInvoicedAmount** 를 입력합니다.

    이러한 설정은 모든 전송 그룹에 대해 **Transaction\AmountMST** 필드의 총 금액이 계산되도록 지정합니다.

9. **Transaction\RecId** 필드를 선택하고 다음 단계를 수행합니다.

    1. 이 필드에 대해 집계 함수가 계산됨을 나타내려면 **집계 필드에 \> 필드 추가** 를 선택합니다.
    2. **집계** 창의 선택한 **Transaction\RecId** 필드에 대해 추가된 기록의 **메서드** 필드에서 **Count** 함수를 선택합니다.
    3. **이름** 선택적 필드에 **NumberOfTransactions** 를 입력하십시오.

    이러한 설정은 모든 전송 그룹에 대해 그룹의 트랜잭션 수가 계산되도록 지정합니다.

10. **저장** 을 선택합니다.
11. 편집 가능한 데이터 소스의 <a name="ExecutionLocation">실행</a> 매개 변수를 검토하십시오. **Autodetect** 가 **Execution location** 필드에서 자동으로 선택되었고 **Execution at** 필드에는 **SQL** 값이 포함됩니다. 이러한 설정은 선택한 **트랜잭션** 기본 데이터 소스가 현재 쿼리 가능하고 데이터베이스 수준에서 편집 가능한 **GroupBy** 데이터 소스를 실행할 수 있음을 지정합니다.
12. **실행 위치** 필드에 대한 조회를 열어 사용 가능한 값 목록을 검토합니다. **쿼리** 또는 **메모리** 내를 선택하여 이 **GroupBy** 데이터 소스가 데이터베이스 수준이나 애플리케이션 서버 메모리에서 실행되도록 할 수 있습니다.
13. **저장** 을 선택하고 **'그룹화 기준' 매개 변수 편집** 페이지를 닫습니다.
14. **확인** 을 선택하여 **GroupBy** 데이터 원본의 설정을 완료합니다.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>GroupBy 데이터 소스를 데이터 모델 필드에 바인딩

구성된 데이터 소스를 데이터 모델의 필드에 바인딩하여 런타임 시 데이터 모델이 애플리케이션 데이터로 채워지는 방법을 지정합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 모델** 창에서 **전송** 노드를 확장합니다.
2. **데이터 원본** 창에서 **TransportRecord** 데이터 원본을 확장합니다.
3. 검색된 전송 그룹 목록을 표시하는 바인딩을 추가합니다.

    1. **데이터 모델** 창에서 **전송** 항목을 선택합니다.
    2. **데이터 원본** 창에서 **TransportRecord** 데이터 원본을 선택합니다.
    3. **바인딩** 을 선택합니다.

4. 검색된 각 전송 그룹의 전송 코드를 노출하는 바인딩을 추가합니다.

    1. **Transport.Code** 데이터 모델 항목을 선택하십시오.
    2. **TransportRecord.grouped.TransportMode** 그룹화된 필드를 선택하십시오.
    3. **바인딩** 을 선택합니다.

5. 검색된 각 전송 그룹에 대해 계산된 집계 함수의 값을 노출하는 바인딩을 추가합니다.

    1. **Transport.NumberOfTransactions** 데이터 모델 항목을 선택하십시오.
    2. **TransportRecord.aggregated.NumberOfTransactions** 집계 필드를 선택하십시오.
    3. **바인딩** 을 선택합니다.
    4. **Transport.TotalInvoicedAmount** 데이터 모델 항목을 선택하십시오.
    5. **TransportRecord.aggregated.TotalInvoicedAmount** 집계 필드를 선택하십시오.
    6. **바인딩** 을 선택합니다.

6. 검색된 각 전송 그룹에 속하는 트랜잭션 기록을 노출하는 바인딩을 추가합니다.

    1. **Transport.Transaction** 데이터 모델 항목을 선택하십시오.
    2. **TransportRecord.lines** 필드를 선택하십시오.
    3. **바인딩** 을 선택합니다.

    **Transport.Transaction** 데이터 모델 항목 및 **TransportRecord.lines** 데이터 소스 필드의 중첩 항목에 대한 바인딩을 계속 구성하여 검색된 각 전송 그룹에 속하는 Intrastat 트랜잭션의 세부 정보를 런타임에 노출할 수 있습니다.

![ER 모델 매핑 디자이너에서 구성된 모델 매핑.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>추가된 모델 매핑 구성 요소 디버그

[ER 데이터 소스 디버거](er-debug-data-sources.md)를 사용하여 구성된 모델 매핑을 테스트합니다.

1. **모델 매핑 디자이너** 페이지에서 **디버깅 시작** 을 선택합니다.
2. **디버그 데이터 원본** 페이지의 왼쪽 창에서 **TransportRecord** 데이터 원본을 선택한 다음 **모든 기록 읽기** 를 선택합니다.
3. **TransportRecord** 데이터 원본을 확장하고 다음 단계를 따릅니다.

    1. **TransportRecord.grouped.TransportMode** 데이터 소스를 선택하십시오.
    2. **값 가져오기** 를 선택합니다.
    3. **TransportRecord.grouped.NumberOfTransactions** 데이터 소스를 선택하십시오.
    4. **값 가져오기** 를 선택합니다.
    5. **TransportRecord.grouped.TotalInvoicedAmount** 데이터 소스를 선택하십시오.
    6. **값 가져오기** 를 선택합니다.

4. 오른쪽 창에서 **모두 확장** 을 선택합니다.

**TransportRecord** 데이터 소스는 두 개의 기록을 노출하고 두 개의 전송 코드를 제공합니다. 각 운송 코드에 대해 트랜잭션 수와 총 송장 금액이 계산됩니다.

> [!NOTE]
> '지연 읽기' 접근 방식은 **GroupBy** 데이터 소스가 데이터베이스 호출을 최적화하기 위해 호출될 때 사용됩니다. 따라서 **GroupBy** 데이터 소스의 일부 필드 값은 데이터 모델 필드에 바인딩된 경우에만 ER 데이터 소스 디버거에서 계산됩니다.

![디버그 데이터 소스 페이지의 데이터 소스 디버깅 결과입니다.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>그룹 총계를 계산할 때 총계를 계산하는 방법이 있습니까?

네. 총계를 계산하려면 이전에 구성한 **GroupBy** 데이터 원본이 기본 데이터 원본으로 사용되는 다른 **GroupBy** 데이터 원본을 구성합니다. 다음 그림은 **GroupBy** 유형의 **TransportRecord** 데이터 소스의 **SUM** 집계를 기반으로 집계 **SUM** 함수를 계산하는 데 사용되는 **GroupBy** 유형의 **총계** 데이터 소스를 보여줍니다.

![ER 모델 매핑 디자이너의 합계 데이터 소스입니다.](./media/er-groupby-data-sources-configure-model-mapping2.png)

다음 그림은 **Totals** 데이터 소스 디버깅 결과를 보여줍니다.

![디버그 데이터 소스 페이지의 총계 데이터 소스 디버깅 결과입니다.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [실행된 ER 형식의 데이터 소스를 디버그하여 데이터 흐름 및 변환 분석](er-debug-data-sources.md)
- [전자 보고 형식의 DATA COLLECTION 데이터 소스 사용](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
