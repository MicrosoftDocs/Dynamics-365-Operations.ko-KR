---
title: 전자 보고로 테스트 자동화
description: 이번에는 전자 보고(ER) 프레임워크의 기본 함수를 사용하여 함수 테스트를 자동화하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: da69cc903197dbfae536c8494f126074c51aa77f9522d57f2673c97b1e682d9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460962"
---
# <a name="automate-testing-with-electronic-reporting"></a>전자 보고로 테스트 자동화

[!include[banner](../includes/banner.md)]

이번에는 전자 보고(ER) 프레임워크를 사용하여 일부 함수의 테스트를 자동화하는 방법에 대해 설명합니다. 이 항목의 예는 공급 업체 지급 처리 테스트를 자동화하는 방법을 보여줍니다.

애플리케이션은 ER 프레임워크를 사용하여 공급 업체 지급 처리 중에 지급 파일 및 해당 문서를 생성합니다. ER 프레임워크는 다양한 지급 유형에 대한 지급 처리와 다양한 형식의 문서 생성을 지원하는 데이터 모델, 모델 매핑 및 형식 구성 요소로 구성됩니다. 이러한 구성 요소는 Microsoft Dynamics LCS(Lifecycle Services)에서 다운로드하여 인스턴스로 가져올 수 있습니다.

또한 각 Microsoft 구성 요소를 사용자 지정하여 고유한 사용자 지정 구성 요소의 기반으로 사용할 수도 있습니다. 사용자 지정 버전을 생성하여 특정 요구 사항을 지원하는 변경을 수행할 수 있습니다. 예를 들어, ER 데이터 모델과 ER 모델 매핑을 조정하여 고객별 애플리케이션 데이터에 액세스하거나 ER 형식을 변경하여 생성된 문서의 레이아웃을 수정할 수 있습니다.

사용자 지정된 ER 형식을 사용하여 공급 업체 지급을 생성하는 지급 파일을 처리하고 제어 보고서를 처리할 수도 있습니다. 버전 관리는 ER 구성 요소에서 지원됩니다. 따라서 Microsoft는 공급 업체 지급 처리를 위한 업데이트된 버전의 ER 솔루션을 제공할 수 있으며 업데이트된 버전을 기반으로 사용자 지정된 구성 요소와 자동으로 병합할 수 있습니다. 그러나 리베이스 버전을 테스트하여 예상대로 작동하는지 확인해야 합니다.

ER 데이터 모델 및 ER 모델 매핑은 다양한 유형의 지급을 처리하고 국가/지역별 지급 문서를 생성하는 데 사용되는 많은 ER 형식에 일반적입니다. 따라서 여러 회사에서 자동으로 수행하되 각 대상 회사의 국가/지역 컨텍스트를 고려하고 다른 데이터 세트를 사용하는 등 사용자 수락 및 통합 테스트를 자동화하는 것이 매우 바람직합니다.

구성 공급자로부터 받은 형식을 기반으로 하는 형식의 사용자 지정 버전을 만드는 방법에 대한 자세한 내용은 [ER 해당 형식의 새 기본 버전을 채택하여 형식 업그레이드](./tasks/er-upgrade-format.md)를 참조하십시오.

## <a name="key-concepts"></a>주요 컨셉

함수적인 고급 사용자는 소스 코드를 작성하지 않고도 사용자 승인 및 통합 테스트를 작성할 수 있습니다.

- ER 베이스라인 기능을 사용하여 생성된 문서를 마스터 사본과 비교합니다. 자세한 내용은 [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md)를 참조하십시오.
- 작업 레코더를 사용하여 테스트 사례를 기록하고 기준 평가를 포함합니다. 자세한 내용은 [작업 레코더 리소스](../user-interface/task-recorder.md)를 참조하십시오.
- 필요한 테스트 시나리오에 대한 그룹 테스트 사례. 자세한 내용은 [사용자 승인 테스트 생성 및 자동화](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)를 참조하십시오.

    - LCS에서 BPM(Business Process Modeler)을 사용하여 사용자 승인 테스트용 라이브러리를 만듭니다.
    - BPM 테스트 라이브러리를 사용하여 Microsoft Azure DevOps Services(Azure DevOps)에서 테스트 계획 및 테스트 스위트를 작성하십시오.

함수적인 고급 사용자는 사용자 승인 및 통합 테스트를 실행할 수 있습니다.

- Regression Suite Automation Tool(RSAT)를 사용하여 원하는 테스트 스위트의 테스트 케이스를 실행하십시오.
- 테스트 결과를 Azure DevOps에 보고하고 이 서비스를 사용하여 해당 결과를 조사합니다.

## <a name="prerequisites"></a>전제 조건

이 항목의 작업을 완료하려면 먼저 다음 전제 조건을 완료해야 합니다.

- 테스트 자동화를 지원하는 토폴로지를 배포합니다. **시스템 관리자** 역할에 대해 이 토폴로지의 인스턴스에 대한 액세스 권한이 있어야 합니다. 이 토폴로지는 이 예시에서 사용할 데모 데이터를 포함해야 합니다. 자세한 내용은 [지속적인 빌드 및 테스트 자동화를 지원하는 환경 배포 및 사용](../perf-test/continuous-build-test-automation.md)을 참조하십시오.
- 사용자 승인 및 통합 테스트를 자동으로 실행하려면 사용 중인 토폴로지에 RSAT를 설치하고 적절한 방식으로 구성해야 합니다. RSAT를 설치 및 구성하고 재무 및 운영 앱과 Azure DevOps 함께 작동하도록 구성하는 방법에 대한 자세한 내용은 [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)를 참조하십시오. 도구 사용을 위한 전제 조건에 주의하십시오. 다음 그림은 RSAT 설정의 예를 보여줍니다. 파란색 직사각형은 Azure DevOps에 대한 액세스를 지정하는 매개 변수를 묶습니다. 녹색 사각형은 인스턴스에 대한 액세스를 지정하는 매개 변수를 묶습니다.

    ![RSAT 설정.](media/GER-Configure.png "RSAT 설정 대화 상자의 스크린샷")

- 추가 보고 및 조사를 위해 테스트 실행 로그를 수집할 수 있도록 올바른 실행 순서를 보장하도록 테스트 케이스를 제품군으로 구성하려면 배포된 토폴로지에서 Azure DevOps에 대한 액세스 권한이 있어야 합니다.
- 이 항목의 예를 완료하려면 [RSAT 테스트에 대한 ER 사용](https://go.microsoft.com/fwlink/?linkid=874684)을 다운로드하는 것이 좋습니다. 이 zip 파일에는 다음 작업 가이드가 포함되어 있습니다.

    | 콘텐츠                                           | 파일 이름 및 위치 |
    |---------------------------------------------------|------------------------|
    | 테스트를 위한 데이터 준비를 위한 샘플 작업 기록 | \\Recording.xml 준비 |
    | 공급 업체 지급을 처리하기 위한 샘플 작업 기록   | \\Recording.xml 처리 |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>공급 업체 지급을 처리하기 위한 미지급금 모듈 준비

1. 인스턴스에 로그인합니다.
2. LCS에서 다음 ER 구성을 다운로드합니다. 지침은 [ER Lifecycle Services에서 구성 가져오기](./tasks/er-import-configuration-lifecycle-services.md)를 참조하십시오.

    - **결제 모델** ER 모델 구성
    - **결제 모델 매핑 1611** ER 모델 매핑 구성
    - **BACS(영국)** ER 형식 구성

    ![전자 보고 구성.](media/GER-Configurations.png "전자 보고의 구성 페이지 스크린샷")

3. 영국에 국가/지역 컨텍스트가 있는 **GBSI** 데모 데이터 회사를 선택하십시오.
4. 미지급금 매개 변수 구성:

    1. **미지급금 \> 지급 설정 \> 지급 방법** 으로 이동하십시오.
    2. **전자** 결제수단을 선택하십시오.
    3. 공급 업체 결제 처리를 위해 이전에 다운로드한 **BACS(UK)** ER 형식을 사용하도록 선택한 결제 방법을 구성합니다.

        1. **파일 형식** FastTab에서 **일반 전자 내보내기 형식** 옵션을 **예** 로 설정합니다.
        2. **내보내기 형식 구성** 필드에서 **BACS(영국)** 를 선택합니다.

    ![결제 방법 페이지입니다.](media/GER-APParameters.png "결제 방법 페이지 스크린샷")

    > [!NOTE]
    > 사용자 지정을 지원하기 위해 생성된 이 ER 형식의 파생 버전이 있는 경우 **전자** 결제 방법에서 이 구성을 선택할 수 있습니다.

5. 공급 업체 지급 예시 생성:

    1. **외상 매입 계정 \> 지불 \> 지불 저널**.
    2. 지급 일지를 게시하지 않았는지 확인하십시오.

        ![지급 일지 페이지.](media/GER-APJournal.png "지급 분개 페이지의 스크린샷")

    3. **라인** 을 선택하고 다음 정보가 있는 라인을 입력합니다.

        | 필드               | 예시 값   |
        |---------------------|-----------------|
        | 공급 업체 이름         | GB\_SI\_000001  |
        | 차변               | 1000.00        |
        | 통화            | GBP             |
        | 상계 계정 유형 | 은행            |
        | 상계 계정      | GBSI 오퍼       |
        | 지급 방법   | 전자      |

    ![공급 업체 결제 페이지입니다.](media/GER-APJournalLines.png "공급 업체 지급 페이지의 스크린샷")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>공급 업체 지급 처리를 테스트하기 위한 ER 프레임워크 준비

### <a name="configure-er-parameters"></a>ER 매개 변수 구성

1. **조직 관리 \> 전자 보고 \> 전자 보고 매개 변수** 로 이동합니다.
2. **첨부** 탭의 **기준선** 필드에서 DM(문서 관리) 프레임워크가 기준선 기능과 관련된 문서를 DM 첨부로 유지하는 데 사용하는 문서 유형으로 **파일** 을 선택합니다.

    ![전자 보고 매개 변수 페이지.](media/GER-ERParameters.png "전자 보고 매개 변수 페이지의 스크린샷")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>공급 업체 지급 관련 문서의 기본 사본 생성

1. **외상 매입 계정 \> 지불 \> 지불 저널**.
2. **라인** 을 선택합니다.
3. **결제 생성** 을 선택합니다.
4. **전자** 결제수단을 선택하십시오.
5. **GBSI OPER** 은행 계좌를 선택합니다.
6. **인쇄 제어 보고서** 옵션을 **예** 로 설정합니다.
7. 생성된 출력을 zip 파일로 다운로드합니다.
8. 다운로드한 파일을 엽니다.
9. 다운로드한 파일에서 다음 파일의 압축을 풉니다.

    - 텍스트 형식의 결제 **파일** 제출
    - XLSX 형식의 **ERVendOutPaymControlReport** 제어 보고서 파일

    ![추출된 파일입니다.](media/GER-APJournalProcessed.png "Windows 탐색기에서 추출된 파일 이름의 스크린샷")

### <a name="turn-on-the-er-baseline-feature"></a>응급실 기준선 기능 켜기

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. 작업 창의 **작업** 탭에서 **주기 집계** 를 선택합니다.
3. **디버그 모드에서 실행** 옵션을 **예** 로 설정합니다.

**디버그 모드에서 실행** 매개 변수를 켜면 나가는 문서를 생성하는 ER 형식을 실행한 후 ER 프레임워크가 다음 작업을 수행하도록 합니다.

1. 실행된 ER 형식의 구성 요소에 대해 기준선이 구성되었는지 확인합니다.
2. 구성된 각 기준선이 현재 조건(로그인한 회사의 회사 코드, 생성된 출력의 파일 이름 및 파일 이름 확장명 등)에 적용 가능한지 여부를 결정합니다.
3. 적용 가능한 각 기준선에 대해 다음 작업을 수행합니다.

    1. ER 형식을 실행하는 동안 생성된 출력을 해당 기준과 비교합니다.
    2. ER 구성 디버그 로그에 비교 결과를 저장합니다.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>공급 업체 지급 처리를 위한 ER 기준 구성

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **기준선** 을 선택합니다.
3. **새로 만들기** 를 선택합니다.
4. **참조** 필드에서 **BACS(영국)** 형식을 선택합니다.
5. **첨부 파일** 을 선택합니다.
6. 공급 업체 지급 파일에 대한 새 기준선을 추가합니다.

    1. **새로 만들기** 를 선택합니다.
    2. **유형** 필드에서 기준선 아티팩트를 저장하기 위해 ER 매개 변수에서 구성한 **파일** DM 문서 유형을 선택하십시오.
    3. 텍스트 형식으로 로컬에 저장된 **파일** 결제 파일을 찾아 선택합니다.
    4. **설명** 필드에 **지급 TXT 파일** 을 입력합니다.

7. 공급 업체 지급에 대한 통제 보고서에 대한 새 기준선을 추가합니다.

    1. **새로 만들기** 를 선택합니다.
    2. **유형** 필드에서 기준선 아티팩트를 저장하기 위해 ER 매개 변수에서 구성한 **파일** DM 문서 유형을 선택하십시오.
    3. XLSX 형식으로 로컬에 저장된 **ERVendOutPaymControlReport** 제어 보고서 파일을 찾아 선택합니다.
    4. **설명** 필드에 **지급 XLSX 제어 보고서** 를 입력합니다.

    ![공급 업체 지급 파일 및 통제 보고서에 대한 기준입니다.](media/GER-BaselineAttachments.png "결제 XLSX 제어 보고서가 선택된 구성 페이지의 스크린샷")

8. 페이지를 닫습니다.
9. **기준선** FastTab에서 **새로 만들기** 를 선택하여 지급 파일에 대한 기준선을 구성합니다.

    1. **지급 파일에 대한 라인 기준** 설정의 이름을 지정합니다.
    2. **파일 구성 요소 이름** 필드에서 BACS(UK) 텍스트 형식의 지급 파일을 생성하는 ER 형식 출력에 이 기준선을 적용할 **파일** 을 선택합니다.
    3. **회사** 필드에서 **BACS (UK)** ER 형식이 **GBSI** 회사에서 실행될 때 이 기준선을 적용하려면 GBSI를 선택하십시오.
    4. **파일 이름 마스크** 필드에 **\*.TXT** 를 입력하여 파일 이름 확장명이 **.txt** 인 **파일** 형식 구성 요소의 출력에만 이 기준선을 적용합니다.
    5. **기준선** 필드에서 **지급 TXT 파일** 을 선택하여 이 기준선이 생성된 출력과 비교하는 데 사용되도록 합니다.

10. **새로 만들기** 를 선택하여 제어 보고서에 대한 기준을 구성합니다.

    1. **제어 보고서에 대한 기준선** 설정의 이름을 지정합니다.
    2. **파일 구성 요소 이름** 필드에서 **ERVendOutPaymControlReport** 를 선택하여 이 기준선을 제어 보고서를 생성하는 ER 형식 출력에 적용합니다.
    3. **회사** 필드에서 **BACS (UK)** ER 형식이 **GBSI** 회사에서 실행될 때 이 기준선을 적용하려면 GBSI를 선택하십시오.
    4. **파일 이름 마스크** 필드에 **\*.XLSX** 를 입력하여 파일 이름 확장명이 **.xslx** 인 **ERVendOutPaymControlReport** 형식 구성 요소의 출력에만 이 기준선을 적용합니다.
    5. **기준선** 필드에서 **지급 XLSX 제어 보고서** 를 선택하여 이 기준선이 생성된 출력과 비교하는 데 사용되도록 합니다.

    ![구성 페이지의 기준선 FastTab.](media/GER-BaselineRules.png "구성 페이지의 Baselines FastTab 스크린샷")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>공급 업체 지급 처리를 검증하기 위한 테스트 기록

함수적 고급 사용자는 공급 업체 지급 처리를 테스트하기 위해 자신의 단계를 기록할 수 있습니다. 이전에 다운로드한 **Prepare\\Recording.xml** 작업 기록을 재생하고 필요에 따라 편집하는 것이 좋습니다. 이 기록은 모든 테스트 데이터를 올바른 상태로 설정하는 데 사용됩니다. 테스트를 여러 번 수행할 수 있고 모든 테스트에서 동일한 상태의 데이터를 사용해야 하기 때문에 이 단계가 필요합니다.

### <a name="reset-user-settings"></a>사용자 설정 재설정

1. 기본 대시보드를 엽니다.
2. **설정** 버튼(기어 기호)을 선택합니다.
3. **사용자 옵션** 을 선택합니다.
4. **사용 데이터** 를 선택합니다.
5. **재설정** 을 선택합니다.
6. **예** 를 선택하여 부하 삭제를 확인합니다.
7. 페이지를 닫습니다.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>테스트를 위한 데이터 준비 단계 기록

1. **설정** 버튼(기어 기호)을 선택합니다.
2. **작업 레코더** 를 선택합니다.
3. **재생 기록** 을 선택합니다.
4. **이 PC에서 열기** 를 선택합니다.
5. **찾아보기** 를 선택하고 로컬로 저장되는 **Prepare\\Recording.xml** 파일을 선택합니다.
6. **시작** 을 선택합니다.
7. 기록의 모든 단계가 재생될 때까지 **다음 보류 단계 재생** 을 계속 선택합니다.

이 작업 기록은 다음 작업을 수행합니다.

1. 처리된 지급 라인의 상태를 **없음** 으로 설정합니다.

    ![작업 기록 단계 3~4.](media/GER-Recording1Review1.png "작업 기록 단계 3~4의 스크린샷")

2. **디버그 모드에서 실행** ER 사용자 매개 변수를 켭니다.

    ![작업 기록 단계 9~10.](media/GER-Recording1Review2.png "작업 기록 단계 9~10의 스크린샷")

3. 생성된 파일을 기준선과 비교한 결과가 포함된 ER 디버그 로그를 정리합니다.

    ![작업 기록 단계 13~15.](media/GER-Recording1Review3.png "작업 기록 단계 13~15의 스크린샷")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>공급 업체 지급 처리를 테스트하는 단계를 기록합니다.

이전에 다운로드한 **Prepare\\Recording.xml** 작업 기록을 재생하고 필요에 따라 편집하는 것이 좋습니다. 이 기록은 공급 업체 지급을 처리하고 생성된 문서를 해당 기준선과 비교한 결과를 검증하는 데 사용됩니다.

1. **설정** 버튼(기어 기호)을 선택합니다.
2. **작업 레코더** 를 선택합니다.
3. **재생 기록** 을 선택합니다.
4. **이 PC에서 열기** 를 선택합니다.
5. **찾아보기** 를 선택하고 로컬에 저장된 **Process\\Recording.xml** 파일을 선택합니다.
6. **시작** 을 선택합니다.
7. 기록의 모든 단계가 재생될 때까지 **다음 보류 단계 재생** 을 계속 선택합니다.

이 작업 기록은 다음 작업을 수행합니다.

1. 공급 업체 지급 처리를 시작합니다.
2. 올바른 런타임 매개 변수를 선택하고 제어 보고서 생성을 켭니다.

    ![작업 기록 단계 3~8.](media/GER-Recording2Review1.png "작업 기록 단계 3~8의 스크린샷")

3. ER 디버그 로그에 액세스하여 생성된 출력을 해당 기준선과 비교한 결과를 기록합니다.

    ER 디버그 로그에서 비교 결과가 **생성된 텍스트** 필드에 나타납니다. 로그 항목 필드를 유발한 **형식 구성 요소** 및 **형식 경로** 는 생성된 출력이 기준선과 비교된 파일 구성 요소를 참조합니다.

    ![전자 보고 실행 로그 페이지의 항목입니다.](media/GER-ERDebugLog.png "전자 보고 실행 로그 페이지의 항목 스크린샷")

4. 현재 출력과 기준선의 비교는 작업 **확인** 레코더 옵션을 사용하고 **현재 값** 을 선택하여 기록됩니다.

    ![현재 값과 비교하기 위해 Validate 옵션을 사용합니다.](media/GER-TRRecordValidation.png "현재 값과 비교하기 위해 유효성 검사 옵션을 사용하는 스크린샷")

    다음 그림은 작업 기록에서 기록된 검증 단계가 어떻게 보이는지 보여줍니다.

    ![작업 기록 단계 13 및 15.](media/GER-Recording2Review2.png "작업 기록 단계 13 및 15의 스크린샷")

## <a name="add-the-recorded-tests-to-azure-devops"></a>기록된 테스트 추가 Azure DevOps

1. Azure DevOps 환경을 엽니다.
2. [도구를 구성](#prerequisites)할 때 RSAT 매개 변수에서 정의한 프로젝트를 선택하십시오.
3. [도구를 구성](#prerequisites)할 때 RSAT 매개 변수에 정의한 테스트 계획을 선택합니다.
4. 선택한 테스트 계획에 대한 새 테스트 케이스를 만듭니다.

    1. 테스트 케이스의 이름을 지정합니다. **벤더의 전자 결제 처리를 테스트하기 위해 데이터를 준비** 합니다.
    2. 이전에 다운로드한 **Prepare** 폴더에서 **Recording.xml** 파일을 첨부합니다.

5. 선택한 테스트 계획에 대한 새 테스트 케이스를 만듭니다.

    1. **테스트 케이스의 이름을 ER 형식 BACS(UK)** 를 사용하여 공급 업체 지급의 테스트 처리로 지정합니다.
    2. 이전에 다운로드한 **Process** 폴더에서 **Recording.xml** 파일을 첨부합니다.

    ![선택한 테스트 계획에 대한 새 테스트 사례입니다.](media/GER-RSAT-DevOps-Tests-Passed.png "선택한 테스트 계획에 대한 새 테스트 사례의 스크린샷")

> [!NOTE]
> 추가된 테스트의 올바른 실행 순서에 주의하십시오.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>기록된 테스트를 실행하기 위해 RSAT 준비

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Azure DevOps에서 RSAT로 테스트 로드

1. 현재 토폴로지에서 로컬 RSAT 애플리케이션을 엽니다.
2. **로드** 를 선택하여 현재 상주하는 테스트를 Azure DevOps RSAT에 로드합니다.

    ![테스트가 RSAT에 로드되었습니다.](media/GER-RSAT-RSAT-Tests-Loaded.png "RSAT에 로드된 테스트의 스크린샷")

### <a name="create-automation-and-parameters-files"></a>자동화 및 매개 변수 파일 생성

1. RSAT에서 로드한 테스트를 Azure DevOps 선택합니다.
2. **새로 만들기** 를 선택하여 RSAT 자동화 및 매개 변수 파일을 만듭니다.

    ![RSAT에서 생성된 RSAT 자동화 및 매개 변수 파일.](media/GER-RSAT-RSAT-Tests-Initiated.png "RSAT에서 생성된 RSAT 자동화 및 매개 변수 파일의 스크린샷")

### <a name="modify-the-parameters-files"></a>매개 변수 파일 수정

1. RSAT에서 **데이터 준비를 선택하여 공급 업체의 전자 결제 테스트 케이스 처리** 를 테스트합니다.
2. **편집** 을 선택합니다.
3. Microsoft Excel 열려 있는 통합 문서의 **일반** 워크시트에서 이 회사가 테스트 실행에 사용되므로 회사 코드를 **GBSI** 로 변경합니다.
4. RSAT에서 **ER 형식 BACS(UK) 테스트 사례를 사용하여 공급 업체 지급 테스트 처리** 를 선택합니다.
5. **편집** 을 선택합니다.
6. 열려 있는 Excel 통합 문서의 **일반** 워크시트에서 회사 코드를 **GBSI로** 변경합니다.
7. **ERFormatMappingRunLogTable** 워크시트에서 셀 A:3 및 C:3에는 출력과 기준선 비교 결과의 유효성을 검사하는 데 사용되는 ER 디버그 로그 테이블의 필드 텍스트가 포함되어 있습니다. 이 텍스트는 테스트 실행 중에 생성되는 ER 디버그 로그 기록을 평가하는 데 사용됩니다.

    ![ERFormatMappingRunLogTable 워크시트.](media/GER-RSAT-RSAT-ExcelParameters.png "ERFormatMappingRunLogTable 워크시트의 스크린샷")

## <a name="run-the-tests-and-analyze-the-results"></a>테스트 실행 및 결과 분석

### <a name="run-the-tests-in-rsat"></a>RSAT에서 테스트 실행

1. RSAT에서 로드된 테스트를 선택합니다.
2. **실행** 을 선택합니다.

테스트 케이스는 웹 브라우저를 사용하여 애플리케이션에서 자동으로 실행됩니다.

### <a name="analyze-the-results-of-test-execution"></a>테스트 실행 결과 분석

테스트 실행 결과는 RSAT에 저장됩니다. 두 테스트가 모두 통과되었음을 알 수 있습니다.

![RSAT에서 통과한 테스트입니다.](media/GER-RSAT-RSAT-Tests-Passed.png "RSAT에서 통과한 테스트의 스크린샷")

추가 분석을 수행할 수 있도록 Azure DevOps 테스트 실행 결과도 로 전송됩니다.

![Azure DevOps에서 테스트 실행 결과.](media/GER-RSAT-DevOps-Tests-Added.png "테스트 실행 결과 스크린샷 Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>테스트가 실패한 상황 시뮬레이션

이 테스트 스위트는 생성된 출력 중 하나 이상이 해당 기준과 일치하지 않을 때 실패해야 합니다. 이 상황을 달성하려면 해당 기준과 다른 콘텐츠를 포함하는 지급 파일을 생성하는 파생된 버전의 **BACS(영국)** 를 사용할 수 있습니다. 이 상황을 시뮬레이션하기 위해 동일한 **BACS(영국)** 형식을 사용할 수 있지만 처리된 지급 라인에서 지급 금액을 변경할 수 있습니다.

1. **애플리케이션을 열고 \> 미지급금 \> 지급 분개** 로 이동합니다.
2. **라인** 을 선택합니다.
3. 지급 라인을 선택한 다음 **지급 상태 \> 없음** 을 선택합니다.
4. **차변** 필드에서 값을 **1,000.00** 에서 **2,000.00** 으로 변경합니다.
5. **저장** 을 선택하여 변경 사항을 저장합니다.

### <a name="run-the-tests-in-rsat"></a>RSAT에서 테스트 실행

1. RSAT에서 로드된 테스트를 선택합니다.
2. **실행** 을 선택합니다.

테스트 케이스는 웹 브라우저를 사용하여 애플리케이션에서 자동으로 실행됩니다.

### <a name="analyze-the-results-of-test-execution"></a>테스트 실행 결과 분석

테스트 실행 결과는 RSAT에 저장됩니다. 두 번째 테스트는 두 번째 실행 중에 실패했습니다.

![RSAT에서 실패한 테스트 결과입니다.](media/GER-RSAT-RSAT-Tests-Failed.png "RSAT에서 실패한 테스트 결과의 스크린샷")

추가 분석을 수행할 수 있도록 Azure DevOps 테스트 실행 결과도 로 전송됩니다.

![Azure DevOps에서 테스트 결과가 실패했습니다.](media/GER-RSAT-DevOps-Tests-Failed.png "에서 실패한 테스트 결과의 스크린샷 Azure DevOps")

각 테스트의 상태에 액세스할 수 있습니다. 실행 로그에 액세스하여 실패 원인을 분석할 수도 있습니다. 다음 그림에서 실행 로그는 생성된 결제 파일과 기준선 간의 콘텐츠 차이로 인해 장애가 발생했음을 보여줍니다.

![Azure DevOps의 실패 분석을 위한 실행 로그입니다.](media/GER-RSAT-DevOps-Tests-Failed-Log.png "실패 분석을 위한 실행 로그 스크린샷 Azure DevOps")

따라서 지금까지 살펴본 것처럼 RSAT를 테스트 플랫폼으로 사용하고 ER 기준 함수를 사용하는 작업 레코더 기반 테스트 사례를 사용하여 모든 ER 형식의 함수를 자동으로 평가할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [작업 레코더 리소스](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [사용자 승인 테스트 생성 및 자동화](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [지속적인 빌드 및 테스트 자동화를 지원하는 환경 배포 및 사용](../perf-test/continuous-build-test-automation.md)
- [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md)
- [ER 해당 형식의 새로운 기본 버전을 채택하여 형식을 업그레이드하십시오.](tasks/er-upgrade-format.md)
- [ER Lifecycle Services에서 구성 가져오기](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]