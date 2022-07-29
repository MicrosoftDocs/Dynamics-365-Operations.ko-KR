---
title: ER 구성의 성능 문제 해결
description: 이 항목에서는 전자 보고(ER) 구성에서 성능 문제를 찾고 수정하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b5f5308f171b6cd4224debec897dbde133e6d8424673aabfab51e6b83b9014e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8461025"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>ER 구성의 성능 문제 해결

이 항목에서는 [전자 보고](general-electronic-reporting.md)(ER) [구성](general-electronic-reporting.md#Configuration)에서 성능 문제를 찾고 수정하는 방법에 대해 설명합니다.

일반적으로 성능 조사는 여러 단계로 구성됩니다.

1. 데이터를 [수집](#collecting-data)합니다.
2. 수집된 데이터를 분석합니다.
3. 분석 결과를 바탕으로 ER 구성을 사용하여 [변경](#making-changes)하거나 더 많은 데이터를 수집하기로 결정합니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="analyze-execution-time"></a>실행 시간 분석

실행 시간은 동일한 환경에서 실행 중인 다른 작업 및 처음 호출될 때 데이터를 사용하는 캐싱과 같은 예측할 수 없는 요인에 따라 달라질 수 있습니다. 따라서 여러 번 실행과 측정을 반복해야 합니다.

보고에 사용되는 ER 형식 구성으로 인해 성능 문제가 발생하지 않는 경우가 있습니다. 대신 해당 ER 형식 구성을 여는 데 사용되는 X++ 코드로 인해 발생합니다.

1. [작업 센터](#infolog-time) 또는 [이벤트 로그](#event-log-time)에서 보고서의 실행 시간을 봅니다.
2. 보고서의 실행 시간을 시나리오의 총 실행 시간과 비교합니다.
3. 보고서의 실행 시간이 총 실행 시간보다 훨씬 짧은 경우 보고서가 처리하는 데이터의 양을 고려합니다.

    - 보고서가 소량의 데이터를 처리하는 경우 문제는 구성 로드 시간과 관련될 수 있습니다.
    - 보고서가 많은 양의 데이터를 처리하는 경우 문제는 X++ 사전 처리와 관련될 수 있습니다. [추적 파서](#analyze-trace-parser-trace)를 사용하여 이 경우를 분석합니다.

    다른 경우에는 다음 섹션을 참조하세요.

4. 실행 시간이 데이터 양에 따라 어떻게 달라지는지 확인하기 위해 서로 다른 양의 데이터를 포함하는 여러 테스트를 실행합니다.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>추적 파서 추적 분석

작은 예를 준비하거나 보고서 생성의 임의 부분에서 여러 추적을 수집합니다.

그런 다음 [추적 파서](#trace-parser)에서 표준 상향식 분석을 수행하고 다음 질문에 답합니다.

- 시간 소비 측면에서 가장 높은 방법은 무엇입니까?
- 이러한 방법은 전체 시간 중 어느 부분을 사용합니까?

쿼리에 대해 동일한 질문에 대답합니다.

메소드 앞에 "ER"이 붙은 것을 보면 다음 섹션으로 넘어갑니다.

메서드나 쿼리가 애플리케이션 제품군에서 시작된 경우 일반 최적화(예: 인덱스 생성)를 고려합니다.

통화 수를 분석합니다. 숫자가 예상보다 훨씬 높으면 구성의 해당 노드를 캐싱하는 것을 고려합니다.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>데이터베이스 호출 분석

[ER 추적](#electronic-reporting-traces)을 수집할 수 있도록 소량의 데이터가 있는 예제를 준비합니다.

그런 다음 ER 모델 매핑 디자이너에서 추적을 열고 페이지 하단을 확인합니다. 다음 질문에 답합니다.

- 쿼리 중복이 있습니까? 있는 경우 다음 수정 사항 중 하나를 고려하세요.

    - 하나의 상위 레코드 안에 여러 호출이 있다고 생각하는 경우 [캐싱을 사용](#use-caching)합니다.
    - 다른 레코드 내에서 동일한 레코드에 대한 호출이 있다고 생각하는 경우 [캐시되고 매개변수화된 계산 필드를 사용](#cached-parameterized)합니다.
    - 데이터베이스에서 상당한 수의 다른 레코드를 읽어야 하는 경우 [**JOIN** 데이터 소스를 사용](#use-join-datasource)합니다.

- 쿼리 및 가져온 레코드 수가 전체 데이터 양과 일치합니까? 예를 들어 문서에 10줄이 있는 경우 보고서가 10줄 또는 1,000줄을 추출한다고 통계에 표시됩니까? 가져온 레코드 수가 많은 경우 다음 수정 사항 중 하나를 고려합니다.

    - [**FILTER** 함수를 **WHERE** 함수 대신 사용](#filter)하여 SQL Server 측에서 데이터를 처리합니다.
    - 캐싱을 사용하여 동일한 데이터를 가져오지 않도록 합니다.
    - [수집된 데이터 기능을 사용](#collected-data)하여 요약을 위해 동일한 데이터를 가져오는 것을 방지합니다.

### <a name="analyze-perfview-traces"></a>PerfView 추적 분석

[PerfView](#perfview)는 숙련된 개발자를 위한 도구입니다. 다음 단계에 대한 자세한 내용은 [벽시계 시간 조사 기본 사항](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics)을 참조하세요.

1. 스레드 시간을 사용하여 추적을 수집합니다.
2. **runUnattended** 를 사용하는 스택만 포함하여 구성 실행이 있는 스레드만 필터링합니다. (**runUnattended** 를 **IncPats** 입력 상자에 추가합니다.)
3. 모든 CPU, 네트워크 및 차단 시간을 접습니다.
4. [PerfView용 ER 사전 설정](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml)을 로드합니다.
5. **ER** \> **기타 사전 설정** 을 선택합니다.
6. 이름을 확인하세요.

    - 아마도 가장 많은 시간을 소비하는 플랫폼 코드를 보게 될 것입니다.
    - 두 번 탭(또는 두 번 클릭)하고 **피호출자** 를 수행할 수 있습니다.

        접두사가 "ERExpression"인 클래스를 발견하고 수식과 관련된 함수인 경우 클래스 이름을 기반으로 함수 이름을 추측할 수 있으며 ER repo에서 속성을 볼 수 있습니다.

### <a name="fixes"></a>수정

- 대부분의 CPU 시간이 쿼리에 사용되는 경우 쿼리 수를 줄이세요.

    - 중복된 쿼리에 대한 [ER 추적을 검토](#analyze-database-calls)합니다.
    - 가져온 레코드 수를 확인하고 이론적으로 가져와야 하는 데이터의 양을 평가합니다.

- CPU 시간의 대부분이 사용되는 기능에 의해 소비되는 경우 구성에서 리소스를 가장 많이 소비하는 위치를 찾습니다.
- 대부분의 CPU 시간이 데이터 수집 기능에 사용되는 경우 모델 매핑 측면에서 *SQL 그룹화 기준* 으로 바꾸는 것이 좋습니다.

### <a name="collecting-data"></a><a name="collecting-data"></a>데이터 수집

환경에 따라 사용 가능한 데이터를 수집하는 몇 가지 방법이 있습니다.

- 총 실행 시간 가져오기:

    - 작업 센터에서
    - 이벤트 로그에서

- 실행 프로파일:

    - ER 도구를 사용하여
    - 추적 파서를 사용하여
    - PerfView를 사용하여

#### <a name="collecting-data-in-a-production-environment"></a>프로덕션 환경에서 데이터 수집

때때로 문제는 프로덕션 환경에서만 재현될 수 있습니다. 데이터는 다음과 같은 방법으로 수집할 수 있습니다.

- [추적 파서](../perf-test/trace-trace-tutorial.md) 추적을 사용하여
- [ER 실행](trace-execution-er-troubleshoot-perf.md) 추적을 사용하여
- 총 실행 시간을 사용하여

#### <a name="collecting-data-in-a-development-environment"></a>개발 환경에서 데이터 수집

프로덕션 환경에서 사용할 수 있는 도구 외에도 개발 환경에서 사용할 수 있는 몇 가지 도구가 있습니다.

- 이벤트 로그(Microsoft-Dynamics-ElectronicReporting). 이 로그는 총 실행 시간을 제공할 수 있습니다.
- PerfView와 같은 일반적인 .NET 도구.

또한 개발 환경을 통해 보다 유연하게 실험할 수 있습니다. 예를 들어 보고서의 일부를 해제하여 실행 시간이 어떻게 영향을 받는지 확인할 수 있습니다.

### <a name="tools"></a><a name="tools"></a>도구

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>작업 센터의 실행 시간

ER은 작업 센터에서 구성의 실행 시간을 표시할 수 있습니다. 이 옵션은 특정 사용자와 특정 회사에 대해서만 작동하며 대화형 세션에만 적용됩니다. 이 기능을 사용하려면 다음 단계를 따르세요.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **파일 생성 시간 표시** 옵션을 **네** 로 설정합니다.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>이벤트 로그의 실행 시간

1. Windows 이벤트 뷰어를 엽니다.
2. **애플리케이션 및 서비스 로그** 에서 **Microsoft-Dynamics-ElectronicReporting/Operational** 을 엽니다.
3. , 이러한 이벤트에는 경과 시간에 대한 정보가 포함되어 있으므로 **EventID=2** 인 **FormatMapingRun** 이벤트를 찾습니다.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>추적 파서 추적 

ER은 X++로 구현되기 때문에 일반적인 X++ 도구를 사용하여 성능을 분석할 수 있습니다. 자세한 내용은 [추적 파서를 사용하여 추적 가져오기](../perf-test/trace-trace-tutorial.md)를 참조하세요.

이 접근 방식에는 몇 가지 제한 사항이 있습니다. ER의 일부는 C#으로 구현되어 있으므로 모든 세부 정보를 사용할 수 없습니다. 그러나 데이터 사용량 세부 정보를 볼 수 있습니다. 또한 긴 보고서 실행은 추적 저장소 제한을 초과할 수 있습니다.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>ER 추적

ER은 자체 추적을 수집할 수 있으며 이러한 추적에 대한 시각화 및 분석 도구가 있습니다. 자세한 내용은 [ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)을 참조하세요.

#### <a name="perfview"></a><a name="perfview"></a>PerfView

X++와 ER은 모두 .NET 플랫폼 위에 구현되기 때문에 일반적인 .NET 도구를 사용할 수 있습니다. 예를 들어 무료 [PerfView](https://github.com/Microsoft/perfview) 도구를 사용할 수 있습니다.

명령줄에서 데이터를 수집할 수도 있습니다. 예를 들어 다음 Windows PowerShell 스크립트는 시스템에서 형식 실행이 중지될 때까지 실행 시간을 수집합니다.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

이 접근 방식에는 몇 가지 제한 사항이 있습니다. 시스템에 대한 관리 액세스 권한이 있어야 합니다. 또한 학습 곡선이 가파르기 때문에 숙련된 개발자여야 합니다.

### <a name="making-changes"></a><a name="making-changes"></a>변경

#### <a name="use-caching"></a><a name="use-caching"></a>캐싱 사용

캐싱은 데이터를 다시 가져오는 데 필요한 시간을 줄여주지만 메모리 비용이 듭니다. 가져온 데이터의 양이 많지 않은 경우 캐싱을 사용합니다. 자세한 내용과 캐싱 사용 방법을 보여주는 예는 [실행 추적 정보를 기반으로 모델 매핑 개선](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace)을 참조하세요.

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>캐시되고 매개 변수화된 계산 필드 사용

값을 반복적으로 조회해야 하는 경우가 있습니다. 예를 들면 계좌 이름과 계좌 번호가 있습니다. 시간을 절약하기 위해 최상위 수준에 매개 변수가 있는 계산된 필드를 만든 다음 해당 필드를 캐시에 추가할 수 있습니다.

캐시된 데이터의 크기가 작은 경우에만 이 방법을 사용하는 것이 좋습니다. 자세한 내용은 [매개 변수화된 CALCULATED FIELD 데이터 소스를 추가하여 ER 솔루션의 성능 향상](er-calculated-field-ds-performance.md)을 참조하세요.

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>JOIN 데이터 원본 사용

**JOIN** 데이터 소스를 사용하면 하나의 쿼리로 연결된 여러 레코드를 가져올 수 있습니다. 연결된 각 레코드를 가져오기 위해 별도의 쿼리를 사용할 필요가 없습니다. 예를 들어, 1,000개의 라인이 있고 관계별로 각 라인에 대한 항목 데이터를 가져오는 경우 1,001개의 쿼리(= 1,000 + 1)가 있습니다. **JOIN** 데이터 원본을 사용하는 경우 동일한 데이터를 가져오는 데 하나의 쿼리만 사용합니다. 자세한 내용은 [ER 모델 매핑에서 JOIN 데이터 소스를 사용하여 여러 애플리케이션 테이블에서 데이터 가져오기](er-join-data-sources.md)를 참조하세요.

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>WHERE 함수 대신 FILTER 함수 사용

**[FILTER](er-functions-list-filter.md)** 함수는 SQL Server에서 조건을 실행하는 반면 **WHERE** 함수는 한 번에 한 레코드씩 목록에서 모든 데이터를 가져오고 각 레코드에 조건을 적용합니다. 예를 들어, 1,000개의 레코드 중 하나의 레코드를 선택하려고 합니다. **WHERE** 를 사용하는 경우 1,000개의 레코드를 모두 가져옵니다. 그러나 **FILTER** 를 사용하는 경우 정확히 하나의 레코드를 가져옵니다. **FILTER** 는 데이터베이스 측에서 인덱스를 사용할 수도 있습니다.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>수집된 데이터 기능 또는 축적된 데이터 소스 사용

구성에 이전에 가져온 데이터를 보고서별로 요약하는 *그룹화 기준* 이 있으면 구성 요소는 모든 데이터를 다시 가져옵니다. 수집된 데이터 기능을 사용하면 ER이 첫 번째 페치 동안 데이터를 누적할 수 있습니다. 자세한 내용은 [ER 계산 및 합산을 수행하는 형식 구성](tasks/er-format-counting-summing-2.md)을 참조하세요.

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>X++에서 구성의 일부 다시 작성

ER은 확장을 포함하여 테이블 및 클래스의 호출 메서드를 지원합니다. 성능 향상에 도움이 되도록 X++에서 모델 매핑의 일부를 다시 작성하는 것을 고려하세요.

ER은 다음 소스에서 데이터를 사용할 수 있습니다.

- 클래스(**object** 및 **class** 데이터 원본)
- 테이블(**table** 및 **table records** 데이터 원본)

[ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory)는 또한 호출 코드에서 미리 계산된 데이터를 보내는 방법을 제공합니다. 응용 프로그램 제품군에는 이 접근 방식의 다양한 예가 포함되어 있습니다.
