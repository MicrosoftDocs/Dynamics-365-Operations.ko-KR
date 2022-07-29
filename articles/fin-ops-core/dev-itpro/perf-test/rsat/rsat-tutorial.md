---
title: Regression Suite Automation Tool 자습서
description: 이 항목에서는 Regression Suite Automation Tool(RSAT)을 사용하는 방법을 보여줍니다. 다양한 기능을 설명하고 고급 스크립팅을 사용하는 예를 제공합니다.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 2f31009424629221a8e4f130b0ec1879c6c6e3d4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8461009"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Regression Suite Automation Tool 자습서

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> 인터넷 브라우저 도구를 사용하여 이 페이지를 PDF 형식으로 다운로드하고 저장하세요.

이 자습서에서는 Regression Suite Automation Tool(RSAT)의 고급 기능 중 일부를 살펴보고 데모 할당을 포함하며 전략 및 주요 학습 포인트를 설명합니다.

## <a name="notable-features-of-rsat-and-task-recorder"></a>RSAT 및 작업 레코더의 주요 기능

### <a name="validate-a-field-value"></a>필드 값 확인

RSAT를 사용하면 테스트 사례에 유효성 검사 단계를 포함하여 예상 값을 확인할 수 있습니다. 이 기능에 대한 자세한 내용은 문서 [예상 값 검증](rsat-validate-expected.md)을 참조하세요.

다음 예에서는 이 기능을 사용하여 현재고 재고가 0보다 큰지 여부를 검증하는 방법을 보여줍니다.

1. **USMF** 회사의 데모 데이터에서에서 다음 단계를 포함하는 작업 기록을 만듭니다.

    1. **제품 정보 관리 \> 제품 \> 릴리스된 제품** 으로 이동합니다.
    2. 빠른 필터를 사용하여 기록을 찾습니다. 예를 들어 **품목 번호** 필드에 대해 **1000** 값을 필터링합니다.
    3. **보유 재고** 를 선택합니다.
    4. 빠른 필터를 사용하여 기록을 찾습니다. 예를 들어 **사이트** 필드에 대해 **1** 값을 필터링합니다.
    5. 목록에서 선택한 행을 표시합니다.
    6. **총 사용 가능** 필드의 값이 **411.0000000000000000** 인지 확인합니다.

2. 작업 기록을 **개발자 녹음** 으로 저장하고 Azure Devops의 테스트 사례에 연결합니다.
3. 테스트 계획에 테스트 케이스를 추가하고 테스트 케이스를 RSAT에 로드합니다.
4. Excel 매개변수 파일을 열고 **TestCaseSteps** 탭으로 이동합니다.
5. 현재고가 항상 **0** 보다 많은지 확인하려면 **사용 가능한 총계 확인** 단계로 이동하고 값을 **411** 에서 **0** 으로 변경합니다. **연산자** 필드의 값을 등호(**=**)에서 보다 큼 기호(**\>**)로 변경합니다.
6. Excel 매개변수 파일을 저장하고 닫습니다.
7. **업로드** 를 선택하여 Excel 매개변수 파일에 대한 변경 사항을 Azure DevOps에 저장합니다.

이제 인벤토리의 특정 품목에 대한 **사용 가능한 총계** 필드의 값이 0(영)보다 크면 실제 현재고 값에 관계없이 테스트를 통과합니다.

### <a name="saved-variables-and-chaining-of-test-cases"></a>저장된 변수 및 테스트 케이스 연결

RSAT의 주요 기능 중 하나는 다른 테스트에 변수를 전달하기 위한 테스트 기능입니다. 자세한 내용은 문서 [체인 테스트 케이스에 변수 복사](rsat-chain-test-cases.md)를 참조하세요.

### <a name="derived-test-case"></a>파생된 테스트 케이스

RSAT를 사용하면 여러 테스트 사례에서 동일한 작업 기록을 사용할 수 있으므로 작업을 다른 데이터 구성으로 실행할 수 있습니다. 자세한 내용은 문서 [파생된 테스트 케이스](rsat-derived-test-cases.md)를 참조하세요.

### <a name="validate-notifications-and-messages"></a>알림 및 메시지 확인

이 기능을 사용하여 작업이 발생했는지 여부를 확인할 수 있습니다. 예를 들어, 생산 오더가 생성되고 추정된 후 시작되면 앱은 생산 오더가 시작되었음을 알리는 "생산 – 시작" 메시지를 표시합니다.

![생산 - 알림 시작.](./media/use_rsa_tool_05.png)

해당 녹음에 대한 Excel 매개변수 파일의 **MessageValidation** 탭에서 메시지 텍스트를 입력하여 RSAT를 통해 이 메시지의 유효성을 검사할 수 있습니다.

![메시지 유효성 검사 탭.](./media/use_rsa_tool_06.png)

테스트 케이스가 실행된 후 Excel 매개변수 파일의 메시지는 표시된 메시지와 비교됩니다. 메시지가 일치하지 않으면 테스트 케이스가 실패합니다.

> [!NOTE]
> Excel 매개변수 파일의 **MessageValidation** 탭에 하나 이상의 메시지를 입력할 수 있습니다. 메시지는 정보 메시지 대신 오류 또는 경고 메시지일 수도 있습니다.

### <a name="snapshot"></a>스냅샷

이 기능은 작업 기록 중에 수행된 단계의 스크린샷을 만듭니다. 감사 또는 디버깅 목적에 유용합니다.

- 사용자 인터페이스로 RSAT를 실행하는 동안 이 기능을 사용하려면 **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** 파일을 RSAT 설치 폴더 아래에서 열고(예: **C:\\Program Files (x86)\\Regression Suite Automation Tool**) 다음 요소의 값을 **거짓** 에서 **진실** 로 변경합니다.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- CLI로 RSAT를 실행하는 동안(예: Azure DevOps) 이 기능을 사용하려면 **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** 파일을 RSAT 설치 폴더 아래에서 열고(예: **C:\\Program Files (x86)\\Regression Suite Automation Tool**) 다음 요소의 값을 **거짓** 에서 **진실** 로 변경합니다.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

테스트 케이스를 실행하면 RSAT는 단계의 스냅샷(이미지)을 생성하고 작업 디렉토리의 테스트 케이스 재생 폴더에 저장합니다. 재생 폴더에는 별도의 하위 폴더가 생성되며 이름은 **StepSnapshots** 입니다. 해당 폴더에는 실행되는 테스트 사례에 대한 스냅샷이 포함되어 있습니다.

## <a name="assignment"></a>할당

### <a name="scenario"></a>시나리오

1. 제품 디자이너는 새로 출시된 제품을 만듭니다.
2. 생산 관리자는 생산 오더를 시작하여 재고 수준을 2개로 만듭니다.
3. 제조는 생산 오더를 시작 및 종료하고 현재고 수량이 2개인지 확인합니다.
4. 영업 팀은 새 제품 4개에 대한 주문을 받습니다. 따라서 영업 팀은 동적 계획을 통해 순 요구 사항을 업데이트합니다. 추가 용량을 사용할 수 없기 때문에 기본 주문 정책은 "제조 대신 구매"로 설정됩니다. 따라서 계획 구매 오더가 생성됩니다.
5. 구매자는 공급업체를 추가하고 계획된 구매 주문을 확정한 다음 구매 주문을 확인합니다.
6. 구매한 상품이 매장에 도착하면 매장 운영자는 관련 구매 주문서를 검색하여 상품을 수령합니다. 이제 주문이 완료되었으므로 판매 주문에 대해 상품을 선택하고 포장할 수 있습니다.
7. 재무는 구매 송장과 판매 송장을 전기하게 됩니다.

다음 그림은 이 시나리오의 흐름을 보여줍니다.

![데모 시나리오의 흐름입니다.](./media/use_rsa_tool_14.png)

다음 그림은 LCS 비즈니스 프로세스 모델러에서 이 시나리오에 대한 비즈니스 프로세스 계층을 보여줍니다.

![데모 시나리오의 비즈니스 프로세스.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>전략 – 핵심 학습

### <a name="data"></a>데이터

- 대표 데이터 볼륨(프로덕션/골든 구성 데이터와 마이그레이션된 데이터의 사본)이 있는지 확인하세요.
- 작업 레코더를 통해 새 데이터를 생성할 때 기존 이름과 충돌하지 않는 테스트 이름을 만듭니다(예: **RSATxxx**).
- Azure 지정 시간 복원을 사용하여 Tier 1이 아닌 환경에서 테스트를 다시 실행합니다.
- **RANDOM** 및 **NOW** Excel 함수를 사용하여 고유한 조합을 생성할 수 있지만 많은 노력이 필요합니다. 다음은 예입니다.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>작업 레코더

- 녹음을 시작하기 전에 시나리오를 정의합니다. 잘 관리되는 프로젝트에는 미리 정의된 테스트 시나리오가 있습니다. 테스트 케이스를 구축하려면 해당 테스트 시나리오의 결과가 얼마나 예측 가능한지 고려합니다.
- 다른 역할에 의해 수행되거나 다음 단계 전에 대기 시간이나 외부 이벤트가 있는 경우 분할 녹음을 수행합니다.
- 목록에서 값을 선택하지 마세요. 대신 **FIFO**, **AudioRM**, **SiteWH** 등의 텍스트 형식을 사용합니다. 목록에서 선택하면 값 자체가 아니라 목록에서 값의 위치가 기록됩니다. 해당 목록에 항목이 추가되면 값의 위치가 변경될 수 있습니다. 따라서 녹음에 다른 매개변수가 사용되며 시나리오의 나머지 부분이 영향을 받을 수 있습니다.
- 다중 사용자 행동에 대해 생각해 보세요. 예를 들어 새로 생성된 판매 주문이 항상 자동으로 선택될 것이라고 가정하지 마세요. 대신 항상 필터를 사용하여 올바른 순서를 찾으세요.
- 태스크 레코더의 복사 기능을 사용하여 체인된 테스트 케이스에서 사용할 수 있도록 새로 생성된 제품의 이름을 저장합니다.
- 작업 레코더의 유효성 검사 기능을 사용하여 단계가 올바르게 실행되었는지 확인하는 체크포인트를 설정합니다.

### <a name="rsat"></a>RSAT

- 다른 회사에서 테스트를 실행하려면 Excel 매개변수 파일의 **일반** 탭에서 회사를 변경할 수 있습니다. 새로 선택한 회사에서 설정 및 데이터를 사용할 수 있는지 확인하세요.
- Excel 매개변수 파일의 **일반** 탭에서 테스트 사용자를 변경할 수 있습니다. 테스트 케이스를 실행할 사용자의 이메일 ID를 지정하세요. 이런 식으로 지정된 사용자의 보안 권한을 사용하여 테스트 케이스를 실행할 수 있습니다.
- 테스트가 시작되기 전에 기다리려면 Excel 매개변수 파일의 **일반** 탭에서 일시 중지를 정의할 수 있습니다. 이 일시 중지는 일괄 작업에서 사용할 수 있습니다(예: 다음 단계를 수행하기 전에 워크플로를 실행해야 하는 경우).

## <a name="advanced-scripting"></a>고급 스크립팅

### <a name="cli"></a>CLI

RSAT는 **명령 프롬프트** 또는 **PowerShell** 창에서 호출할 수 있습니다.

> [!NOTE]
> **TestRoot** 환경 변수가 RSAT 설치 경로로 설정되었는지 확인합니다. (Microsoft Windows에서 **제어판** 을 열고 **시스템 및 보안 \> 시스템 \> 고급 시스템 설정** 을 선택한 다음 **환경 변수** 를 선택합니다.)

1. **명령 프롬프트** 또는 **PowerShell** 창을 관리자로 엽니다.
2. RSAT 설치 디렉터리로 이동합니다.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. 모든 명령을 나열합니다.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

사용 가능한 모든 명령과 해당 매개변수에 대한 도움말을 표시합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: 선택적 매개 변수

`command`: ``[command]``가 아래 지정된 명령 중 하나입니다.

#### <a name="about"></a>정보

현재 버전을 표시합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

화면을 지웁니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>다운로드

지정된 테스트 케이스에 대한 첨부 파일을 출력 디렉토리에 다운로드합니다.
``list`` 명령을 사용하여 사용 가능한 모든 테스트 케이스를 가져올 수 있습니다. 첫 번째 열의 값을 **test_case_id** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="download-required-parameters"></a>다운로드: 필수 매개 변수

+ `test_case_id`: 테스트 케이스 ID를 나타냅니다.
+ `output_dir`: 출력 디렉토리를 나타냅니다. 디렉토리가 존재해야 합니다.

##### <a name="download-examples"></a>다운로드: 예

`download 123 c:\temp\rsat`

`download 765 c:\rsat\last`

#### <a name="edit"></a>편집

Excel 프로그램에서 매개변수 파일을 열고 편집할 수 있습니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>편집: 필수 매개 변수

+ `excel_file`: 기존 Excel 파일에 대한 전체 경로를 포함해야 합니다.

##### <a name="edit-examples"></a>편집: 예

`edit c:\RSAT\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>생성

출력 디렉토리에 지정된 테스트 케이스에 대한 테스트 실행 및 매개변수 파일을 생성합니다. ``list`` 명령을 사용하여 사용 가능한 모든 테스트 케이스를 가져올 수 있습니다. 첫 번째 열의 값을 **test_case_id** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="generate-required-parameters"></a>생성: 필수 매개 변수

+ `test_case_id`: 테스트 케이스 ID를 나타냅니다.
+ `output_dir`: 출력 디렉토리를 나타냅니다. 디렉토리가 존재해야 합니다.

##### <a name="generate-examples"></a>생성: 예

`generate 123 c:\temp\rsat`

`generate 765 c:\rsat\last`

#### <a name="generatederived"></a>generatederived

제공된 테스트 케이스에서 파생된 새 테스트 케이스를 생성합니다. ``list`` 명령을 사용하여 사용 가능한 모든 테스트 케이스를 가져올 수 있습니다. 첫 번째 열의 값을 **test_case_id** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-required-parameters"></a>generatederived: 필수 매개 변수

+ `parent_test_case_id`: 상위 테스트 케이스 ID를 나타냅니다.
+ `test_plan_id`: 테스트 계획 ID를 나타냅니다.
+ `test_suite_id`: 테스트 스위트 ID를 나타냅니다.

##### <a name="generatederived-examples"></a>generatederived: 예

`generatederived 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

출력 디렉터리에 지정된 테스트 케이스에 대한 테스트 실행 파일만 생성합니다. ``list`` 명령을 사용하여 사용 가능한 모든 테스트 케이스를 가져올 수 있습니다. 첫 번째 열의 값을 **test_case_id** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: 필수 매개 변수

+ `test_case_id`: 테스트 케이스 ID를 나타냅니다.
+ `output_dir`: 출력 디렉토리를 나타냅니다. 디렉토리가 존재해야 합니다.

##### <a name="generatetestonly-examples"></a>generatetestonly: 예

`generatetestonly 123 c:\temp\rsat`

`generatetestonly 765 c:\rsat\last`

#### <a name="generatetestsuite"></a>generatetestsuite

출력 디렉토리에서 지정된 제품군에 대한 모든 테스트 케이스를 생성합니다. ``listtestsuitenames`` 명령을 사용하여 사용 가능한 모든 테스트 스위트를 가져올 수 있습니다. 열의 값을 **test_suite_name** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: 필수 매개 변수

+ `test_suite_name`: 테스트 스위트 이름을 나타냅니다.
+ `output_dir`: 출력 디렉토리를 나타냅니다. 디렉토리가 존재해야 합니다.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: 예

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite Purchase c:\rsat\last`

#### <a name="help"></a>도움말

[?](#section)와 동일 command.

#### <a name="list"></a>목록 개

사용 가능한 모든 테스트 케이스를 나열합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

사용 가능한 모든 테스트 계획을 나열합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

지정된 테스트 스위트에 대한 테스트 케이스를 나열합니다. ``listtestsuitenames`` 명령을 사용하여 사용 가능한 모든 테스트 스위트를 가져올 수 있습니다. 첫 번째 열의 값을 **suite_name** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: 필수 매개 변수

+ `suite_name`: 원하는 제품군의 이름입니다.

##### <a name="listtestsuite-examples"></a>listtestsuite: 예

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitenames"></a>listtestsuitenames

사용 가능한 모든 테스트 스위트를 나열합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>재생

Excel 파일을 사용하여 테스트 케이스를 재생합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="playback-required-parameters"></a>재생: 필수 매개 변수

+ `excel_file`: Excel 파일의 전체 경로입니다. 파일이 존재해야 합니다.

##### <a name="playback-examples"></a>재생: 예

`playback c:\RSAT\TestCaseParameters\sample1.xlsx`

`playback e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

한 번에 여러 테스트 케이스를 재생합니다. ``list`` 명령을 사용하여 사용 가능한 모든 테스트 케이스를 가져올 수 있습니다. 첫 번째 열의 값을 **test_case_id** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: 필수 매개 변수

+ `test_case_id1`: 기존 테스트 케이스의 ID입니다.
+ `test_case_id2`: 기존 테스트 케이스의 ID입니다.
+ `test_case_idN`: 기존 테스트 케이스의 ID입니다.

##### <a name="playbackbyid-examples"></a>playbackbyid: 예

`playbackbyid 878`

`playbackbyid 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Excel 파일을 사용하여 한 번에 많은 테스트 케이스를 재생합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="playbackmany-required-parameters"></a>playbackmany: 필수 매개 변수

+ `excel_file1`: Excel 파일의 전체 경로입니다. 파일이 존재해야 합니다.
+ `excel_file2`: Excel 파일의 전체 경로입니다. 파일이 존재해야 합니다.
+ `excel_fileN`: Excel 파일의 전체 경로입니다. 파일이 존재해야 합니다.

##### <a name="playbackmany-examples"></a>playbackmany: 예

`playbackmany c:\RSAT\TestCaseParameters\param1.xlsx`

`playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

지정된 테스트 스위트의 모든 테스트 케이스를 재생합니다.
``listtestsuitenames`` 명령을 사용하여 사용 가능한 모든 테스트 스위트를 가져올 수 있습니다. 첫 번째 열의 값을 **suite_name** 매개 변수로 사용합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: 필수 매개 변수

+ `suite_name`: 원하는 제품군의 이름입니다.

##### <a name="playbacksuite-examples"></a>playbacksuite: 예

`playbacksuite suiteName`

`playbacksuite sample_suite`

#### <a name="quit"></a>quit

애플리케이션을 닫습니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

#### <a name="upload"></a>업로드

지정된 테스트 스위트 또는 테스트 케이스에 속하는 모든 파일을 업로드합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="upload-required-parameters"></a>업로드: 필수 매개 변수

+ `suite_name`: 지정된 테스트 스위트가 속한 모든 파일을 업로드합니다.
+ `testcase_id`: 지정된 테스트 케이스가 속한 모든 파일을 업로드합니다.

##### <a name="upload-examples"></a>업로드: 예

`upload sample_suite`

`upload 123`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

지정된 테스트 케이스에 속하는 레코딩 파일만 업로드합니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: 필수 매개 변수

+ `testcase_id`: 지정된 테스트 케이스에 속하는 레코딩 파일을 업로드합니다.

##### <a name="uploadrecording-examples"></a>uploadrecording: 예

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>사용량

이 애플리케이션을 호출하는 두 가지 방법을 보여줍니다. 하나는 기본 설정 파일을 사용하는 것이고 다른 하나는 설정 파일을 제공하는 것입니다.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

### <a name="windows-powershell-examples"></a>Windows PowerShell 예

#### <a name="run-a-test-case-in-a-loop"></a>루프에서 테스트 케이스 실행

새 고객을 생성하는 테스트 스크립트가 있습니다. 스크립팅을 통해 이 테스트 케이스는 각 반복이 실행되기 전에 다음 데이터를 무작위화하여 루프에서 실행할 수 있습니다.

- 고객 ID
- 고객 이름
- 고객 주소

고객 ID 형식은 *ATCUS\<number\>* 이며 \<number\>는 **000000001** 과 **999999999** 사이의 값입니다.

다음 예에서는 하나의 매개변수 **시작** 을 사용하여 사용되는 첫 번째 숫자를 정의합니다. 두 번째 매개변수 **nr** 을 사용하여 생성해야 하는 고객 수를 정의합니다. 각 반복에 대해 Excel 매개변수 파일의 매개변수는 UpdateCustomer 함수를 사용하여 변경됩니다. 그런 다음 RSAT 명령줄이 RunTestCase 함수에서 호출됩니다.

관리 모드에서 Microsoft Windows PowerShell ISE(통합 스크립팅 환경)를 실행하고 다음 코드를 이름이 **Untitled1.ps1** 인 창에 붙여넣습니다.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365의 데이터에 의존하는 스크립트 실행

다음 예에서는 OData(Open Data Protocol) 호출을 사용하여 구매 주문의 주문 상태를 찾습니다. 상태가 **인보이스 발행** 이 아닌 경우, 예를 들어 송장을 게시하는 RSAT 테스트 사례를 호출할 수 있습니다.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
