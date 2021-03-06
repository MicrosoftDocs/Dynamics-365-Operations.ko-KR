---
title: 차원 계층
description: 이 항목에서는 차원 계층에 대한 정보를 제공합니다. 차원 계층을 사용하여 비용 회계에서 보고 구조, 비용 정책, 보안 설정을 정의할 수 있습니다.
author: AndersGirke
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 40ae7b61537cdcd1934056b9e289f342e96b57d3eebe5a6e713b2db91310ed9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450703"
---
# <a name="dimension-hierarchy"></a>차원 계층

[!include [banner](../includes/banner.md)]

이 항목에서는 차원 계층에 대한 정보를 제공합니다. 차원 계층을 사용하여 비용 회계에서 보고 구조, 비용 정책, 보안 설정을 정의할 수 있습니다.  

## <a name="overview"></a>개요

차원 계층은 비용 회계의 다양한 위치에서 사용됩니다. 차원 계층으로 다음 정보를 정의할 수 있습니다.

-  조직의 요구 사항에 적합한 보고서 구조
-  비용 정책
-  보안 설정

다음은 차원 계층의 예입니다.

![차원 계층의 예입니다.](./media/dimension-hierarchy.png)

차원 계층은 다음 유형의 차원에 생성할 수 있습니다.

-  비용 요소 차원
-  비용 개체 차원
-  통계적 차원

> [!NOTE]
> - 다른 관점이 필요한 경우 동일한 차원에 여러 차원 계층을 생성할 수 있습니다.
> - 차원 계층은 하나의 차원에만 연결할 수 있습니다.
> - 차원 계층은 구조에서 무제한 수준을 가질 수 있습니다. 모든 수준은 **비용 제어** 작업 영역에서 사용할 수 있습니다. 보고 목적으로 Microsoft Excel 또는 Microsoft Power BI를 사용하는 경우 차원 계층의 처음 15개 수준만 내보냅니다. Excel과 Power BI 모두 고정 스키마가 필요하기 때문에 이 제한이 있습니다.
> - 차원 계층은 날짜 영향이 없습니다. 따라서 차원 계층의 변경 내용이 즉시 레코드에 저장되므로 이전 날짜와 이후 날짜를 비교할 수 없습니다.

## <a name="dimension-hierarchy-type"></a>차원 계층 유형

새 차원 계층을 생성할 때는 계층 유형을 선택해야 합니다. **비용 회계**  > **차원** > **차원 계층** 으로 이동합니다. **새로 만들기** 를 클릭하고 차원 계층 유형을 선택합니다. **차원 범주 구분 계층** 또는 **차원 분류 계층** 을 선택할 수 있습니다.

### <a name="dimension-categorization-hierarchy"></a>차원 범주 구분 계층

**차원 범주 구분 계층** 유형은 보고 목적으로 사용됩니다. 비용 요소 차원만 지원합니다. 이 유형을 선택하면 다음 규칙이 적용됩니다.

-  차원 구성원은 계층 구조에서 여러 번 연결될 수 있습니다.
-  리프 노드에 비용 동작을 할당하여 비용 요소 차원 구성원을 다른 노드에 배치할 수 있습니다.

### <a name="dimension-classification-hierarchy"></a>차원 분류 계층

**차원 분류 계층** 유형은 규칙 정의와 보고서 생성에 사용됩니다. 비용 개체, 비용 요소 및 통계 차원과 같은 모든 차원을 지원합니다. 이 유형을 선택하면 차원 구성원을 계층 구조에서 한 번만 연결할 수 있습니다.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>차원 계층 생성 및 유지 관리

차원 계층은 노드와 리프 노드 관계를 갖는 트리 구조로 생성됩니다.

-  노드에는 1:_n_ 개의 하위 노드를 가질 수 있습니다.
-  노드에 하위 노드와 리프 노드를 모두 할당할 수는 없습니다.
-  리프 노드는 계층 내 가장 낮은 수준에만 할당할 수 있습니다.

### <a name="example"></a>예

소규모 회사의 조직 구조입니다. 재무와 인사 리소스가 관리 아래 부서이고 조립과 포장이 생산 아래 부서입니다.

![조직 구조의 예입니다.](./media/dimension-hierarchy-org.png)

비용 개체 차원은 조직의 모든 비용 센터를 나타냅니다.

- 비용 개체 차원
    - 비용 센터

모든 비용 센터를 나타내는 비용 개체 차원은 다음과 같이 설정할 수 있습니다.

| 비용 센터 | 설명 |
|--------------|-------------|
| CC001        | HR          |
| CC002        | Finance     |
| CC003        | 세금         |
| CC007        | AR/AP       |
| CC005        | 조립    |
| CC006        | 포장   |

비용 요소 차원은 조직의 모든 비용 요소를 나타냅니다.

- 비용 요소 차원
    - 비용 요소

모든 비용 요소를 나타내는 비용 요소 차원은 다음과 같이 설정할 수 있습니다.

| 비용 요소 | 설명 |
|---------------|-------------|
| 10001         | 전기 |
| 10010         | 청소    |
| 10011         | 난방     |
| 40001         | COGS        |

조직 보고 요구 사항을 충족하는 차원 계층을 다음과 같이 설정할 수 있습니다.

**차원 계층 세부 정보**

| 차원 계층 이름 | 차원    | 차원 계층 유형 이름      | 액세스 목록 계층 |
|--------------------------|--------------|------------------------------------|-----------------------|
| 조직             | 비용 센터 | 차원 분류 계층 | 아니요                    |

보고를 위한 차원 계층은 다음과 같이 설정할 수 있습니다.

**차원 구성원 범위**

|   노드           |   차원 구성원에서   |   차원 구성원으로   |
|-------------------|---------------------------|-------------------------|
| 조직      |                           |                         |
| &nbsp;&nbsp;관리자         |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finance   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | CC001                     | CC001                   |
| &nbsp;&nbsp;생산    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;포장 | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;조립  | CC006                     | CC006                   |

정책 요구 사항을 충족하는 차원 계층을 다음과 같이 설정할 수 있습니다.

**차원 계층 세부 정보**

| 차원 계층 이름 | 차원     | 차원 계층 유형 이름      |
|--------------------------|---------------|------------------------------------|
| 비용 동작            | 비용 요소 | 차원 분류 계층 |

정책을 위한 차원 계층은 다음과 같이 설정할 수 있습니다.

**차원 구성원 범위**

|   노드           |   차원 구성원에서   |   차원 구성원으로   |
|-------------------|---------------------------|-------------------------|
| 비용 동작     |                           |                         |
| &nbsp;&nbsp;고정 비용    | 10001                     | 10011                   |
| &nbsp;&nbsp;가변 비용 | 40001                     | 40010                   |

> [!NOTE]
> **차원 구성원 범위** 에서 노드는 1:_n_ 개의 차원 구성원 범위를 포함할 수 있습니다. 아직 차원 구성원으로 존재하지 않는 차원 구성원 ID를 삽입할 수 있습니다. 이 접근 방식은 계층 구조가 나중에 탄력적으로 변화할 수 있게 합니다.  

### <a name="copy-a-hierarchy"></a>계층 구조 복사

현재 차원 계층을 새 차원 계층의 시작점으로 복사할 수 있습니다. 이 방식은 이전 차원 계층을 새 차원 계층과 비교하려는 경우 유용합니다.

### <a name="rearrange-nodes-in-a-hierarchy"></a>계층의 노드 재정렬

구조의 현재 수준 내에서 노드를 위아래로 이동할 수 있습니다. 이 방법으로 **비용 관리** 작업 영역에서 보고할 노드의 순서를 재정렬할 수 있습니다.

대상 노드를 선택하여 노드를 계층 내 새 위치로 이동합니다. 노드를 이동하려면 다음 두 가지 방법이 있습니다.

- **아래로 이동** – 택한 노드를 계층의 현재 위치에서 이동하여 선택한 대상 노드 **아래** 에 삽입합니다.
- **뒤로 이동** – 선택한 노드를 계층 내 현재 위치에서 이동하여 계층의 수준에서 선택한 대상 노드 **뒤** 에 삽입합니다.

> [!NOTE] 
> Excel 또는 Power BI로 데이터를 내보낼 때 노드의 순서는 유지되지 않습니다. 이러한 도구는 기본적으로 영숫자 정렬 순서를 사용하기 때문입니다. 수동으로 순서를 다시 정렬해야 합니다.

## <a name="define-dimension-hierarchies-for-reporting"></a>보고를 위한 차원 계층 정의

차원 계층은 보고에 중요합니다. 개별 조직에 적합한 특정 구조를 정의할 수 있습니다. 차원 계층의 노드 수준에서 수행되는 집계를 통해 조직의 모든 수준의 이해 관계자가 모든 수준의 데이터를 볼 수 있습니다.

차원 계층을 다음 보고 도구에서 사용할 수 있습니다. 이 접근 방식은 보고서 구조의 일관성을 보장하는 데 도움이 됩니다.

- **비용 제어** 작업 영역(클라이언트):

    - 구성에 의해 제어됩니다.

- **비용 제어** 작업 영역(모바일 애플리케이션):

    - 구성에 의해 제어됩니다.

- Excel

    - 다음 내보내기 정의별로 특정 차원 계층을 선택하는 옵션을 제공합니다.

        - 하나의 비용 요소 차원 계층(필수)
        - 하나의 비용 개체 차원 계층(옵션)
        - 하나의 통계적 차원 계층(옵션)

- Power BI:

    - 모든 차원 계층을 사용할 수 있습니다.
    
Excel 또는 Power BI를 사용하여 보고서를 만드는 경우 차원 계층의 처음 15개 수준만 내보냅니다. Excel 및 Power BI에서 고정 스키마가 필요하기 때문에 이 제한이 존재합니다. 계층에 15개 이상의 수준이 있는 경우 추가 수준은 내보내지 않습니다. 정규화된 테이블에는 계층의 각 차원 구성원에 대한 레코드가 포함됩니다. 따라서 자동 집계가 발생합니다. 이 동작을 통해 계층 내에서 사용 가능한 15개 수준의 균형을 계속 유지할 수 있습니다.

다음 예는 보고서 구조에서 차원 계층이 어떤 모습인지 보여 줍니다.

| 비용 개체 차원 계층 – 수준 1 | 비용 개체 차원 계층 – 수준 2 | 비용 개체 차원 계층 – 수준 3 | 비용 개체 차원 계층 – 수준 4 | 비용 개체 차원 계층 – 수준 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| 조직                              | 관리자                                     | Finance                                   | CC002                                     |                                            |
| 조직                              | 관리자                                     | Finance                                   | CC003                                     |                                            |
| 조직                              | 관리자                                     | Finance                                   | CC007                                     |                                            |
| 조직                              | 관리자                                     | HR                                        | CC001                                     |                                            |
| 조직                              | 생산                                | 포장                                 | CC005                                     |                                            |
| 조직                              | 생산                                | 조립                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>보고에 사용되는 차원 계층 업데이트 

시간이 지나면 앞에서 설명한 보고 도구에서 사용되는 차원 계층을 업데이트해야 합니다. 클라이언트를 새로 고쳐 차원 계층을 업데이트할 수 있습니다.

- **비용 제어** 작업 영역(클라이언트)
- **비용 제어** 작업 영역(모바일 애플리케이션)

차원 계층에 대한 업데이트는 미리 캐시된 작업에 의해 24시간마다 선택됩니다. 내보낸 데이터가 업데이트되면 다음 도구에서 업데이트된 차원 계층을 사용할 수 있습니다.

- Excel
- Power BI

> [!NOTE] 
> 차원 계층 캐시의 업데이트를 수동으로 트리거하려면 업데이트해야 하는 차원 계층에 대해 새로운 Excel로 내보내기를 생성할 수 있습니다.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>비용 정책을 위한 차원 계층 정의

비용 회계는 세부 규칙이 정의된 여러 정책으로 구성됩니다. 다음 정책에 대해 하나 이상의 차원 계층을 정의해야 합니다.

- 비용 동작
- 비용 배분
- 비용 할당
- 비용 롤업

차원 계층으로 규칙을 쉽게 만들 수 있습니다. 모든 차원 구성원에 대한 규칙을 생성하지 않으려면 차원 계층 수준에서 제공하는 차원 구성원의 집계를 활용할 수 있습니다. 중복되는 규칙이 있는 경우 시스템이 오버헤드 계산을 할 때 고려하는 특정 규칙을 정의해야 합니다.

### <a name="example-define-a-cost-behavior-policy"></a>예: 비용 동작 정책 정의

새로운 비용 동작 정책이 생성되고 다음과 같이 정책에 적절한 차원 계층이 할당됩니다.

**비용 동작 정책**

| 정책 이름   | 비용 요소 차원 계층 | 원가 대상 차원 계층 | 회계 통화 |
|---------------|----------------------------------|---------------------------------|---------------------|
| 비용 동작 | 비용 동작                    | 조직                    | USD                 |

**규칙**

| 비용 요소 차원 계층 노드 | 원가 개체 차원 계층 노드 | 고정 비율 | 고정 금액 | 유효 기간 시작 | 유효 기간 끝 |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| 고정 비용                            | 조직                         | 100.00           | 0.00         | 1/1/2017   | 절대 아님    |
| 10001                                 | 조직                         | 0.00             | 150.00       | 1/1/2017   | 절대 아님    |
| 10001(\*)                             | Finance                              |                  | 50.00        | 1/1/2017   | 절대 아님    |
| 비용 동작 또는 가변 비용(\*\*)   | 조직                         | 0.00             | 0.00         | 1/1/2017   | 절대 아님    |

\* 가변 비용 노드는 필요하지 않습니다. 비용이 고정 비용으로 분류되지 않았으면 가변 비용이어야 합니다.

\*\* 비용 요소 구성원 10001과 재무 계층 수준(CC002, CC003, CC007)으로 집계된 모든 비용 개체 멤버의 조합에 대한 자세한 규칙이 생성됩니다.

앞의 규칙은 차원 계층이 가진 유연성을 보여줍니다. 높은 수준의 규칙을 정의하면 유지 관리를 최소화할 수 있습니다. 그런 다음 특정 비즈니스 목표에 맞게 세부 규칙을 정의할 수 있습니다.

규칙에서 사용되는 차원 계층이 업데이트되면 시스템이 자동으로 업데이트를 가져옵니다.

규칙의 세분성 수준이 더 이상 필요하지 않으면 규칙이 만료될 수 있습니다.

예를 들어 재무 비용 개체 차원 계층 노드에 대한 특정 비용 동작 규칙은 더 이상 필요하지 않습니다. 이 경우 **규칙 만료** 를 클릭하여 규칙을 만료시킵니다.

| 비용 요소 차원 계층 노드 | 원가 개체 차원 계층 노드 | 고정 비율 | 고정 금액 | 유효 기간 시작 | 유효 기간 끝  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| 고정 비용                            | 조직                         | 100,00           | 0,00         | 1/1/2017   | 절대 아님     |
| 10001                                 | 조직                         | 0,00             | 150,00       | 1/1/2017   | 절대 아님     |
| 10001                                 | Finance                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| 비용 동작 또는 가변 비용        | 조직                         | 0,00             | 0,00         | 1/1/2017   | 절대 아님     |

2017년 1월 20일 이후에 실행되는 오버헤드 계산에서는 이 규칙이 더 이상 고려되지 않습니다.

> [!NOTE] 
> **유효 기간 시작** 및 **유효 기간 끝** 필드는 날짜와 시간의 영향이 있습니다. 규칙을 만료하고 같은 날짜에 새 오버헤드 계산을 실행할 수 있습니다.

## <a name="define-dimension-hierarchies-for-security-setup"></a>보안 설정을 위한 차원 계층 정의

비용 회계 데이터는 보고 단위를 담당하는 모든 관리자가 이용할 수 있어야 합니다. 비용 회계 용어에서 보고 단위는 비용 개체 또는 비용 개체 집합을 나타냅니다.

잠재적으로 모든 관리자는 수익 및 마진과 같은 매우 민감한 비즈니스 데이터에 액세스할 수 있습니다. 따라서 관리자가 자신과 관련된 데이터만 볼 수 있도록 보안을 설정하는 것이 중요합니다. 데이터 보안을 제어하기 위해 차원 계층을 정의합니다.

- 차원 계층은 차원 계층 참조에서 선택한 차원 값이 비용 개체 차원인 경우에만 사용됩니다.
- 액세스 목록 계층에서 비용 개체 차원별로 활성화할 수 있는 차원 계층은 1개뿐입니다.

**차원 계층 세부 정보**

| 차원 계층 이름 | 차원    | 차원 계층 유형 이름      | 액세스 목록 계층 |
|--------------------------|--------------|------------------------------------|-----------------------|
| 조직             | 비용 센터 | 차원 분류 계층 | **예**               |

계층 디자이너에서 새로운 **사용자** FastTab을 사용할 수 있습니다. 여기서 계층 내 각 노드에 하나 이상의 사용자 ID를 삽입할 수 있습니다.

**사용자 및 차원 구성원 범위**

|   노드         |   사용자 ID        |   차원 구성원에서   |   차원 구성원으로   |
|-----------------|------------------|---------------------------|-------------------------|
| 조직    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;관리자         | 4월            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finance   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;생산    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;포장 | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;조립  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> 비용 회계는 비용 회계의 모든 항목을 표시할 수 있도록 계층의 최상위 수준에 할당해야 합니다.

액세스 목록의 계층과 보안 설정을 사용하려면 **비용 회계** > **설정** > **매개 변수** > **일반** 으로 이동합니다. **비용 개체 차원 구성원에 대한 보기 액세스 활성화** 매개 변수를 선택합니다.

액세스 목록 계층 설정은 다음 영역에 표시되는 데이터를 제어하기 위해 사용됩니다.

- **비용 제어** 작업 영역(클라이언트):

    - 시나리오를 드릴스루하는 데 사용되는 양식의 데이터

- **비용 제어** 작업 영역(모바일 애플리케이션):

    - 카드 잔액

- Power BI:

    - Power BI 시각화에 표시되는 데이터
    - Dynamics 365 Finance 클라이언트에 내장된 데이터 Power BI 시각화

> [!NOTE] 
> - 액세스 목록 계층이 Power BI의 데이터에 영향을 미치기 전에 Power BI의 액세스 목록 계층과 행 수준의 보안을 페어링해야 합니다. 자세한 내용은 [비용 회계 콘텐츠 팩을 위한 보안 설정](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)을 참조하십시오.
> - 액세스 목록 계층은 Excel로 데이터를 내보내는 데 도움이 되지 않습니다. 따라서 이 보고서 생성 도구는 데이터를 표시하기 위해 완전한 액세스 권한을 가져야 하는 비용 회계사 및 관리자만 사용해야 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]