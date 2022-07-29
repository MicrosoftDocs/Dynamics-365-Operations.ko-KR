---
title: 실행된 ER 형식의 데이터 소스를 디버그하여 데이터 흐름 및 변환 분석
description: 이번에는 구성된 데이터 흐름 및 변환을 더 잘 이해하기 위해 실행된 ER 형식의 데이터 소스를 디버그하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 02aee8c6ec3b2720c2fcbb17f15791d88d688a34
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460864"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a>실행된 ER 형식의 데이터 소스를 디버그하여 데이터 흐름 및 변환 분석

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

아웃바운드 문서를 생성하도록 전자 보고(ER) 솔루션을 [구성할](tasks/er-format-configuration-2016-11.md) 때 애플리케이션에서 데이터를 가져오고 생성된 출력에 입력하는 데 사용되는 방법을 정의합니다. ER 솔루션의 수명 주기 지원을 보다 효율적으로 만들려면 솔루션이 ER 데이터 모델과 해당 매핑 구성 요소, ER 형식 및 매핑 구성 요소로 구성되어야 합니다. 애플리케이션에 구애받지 않습니다. 따라서 여러 ER 구성 요소가 생성된 출력에 데이터를 입력하는 프로세스에 영향을 줄 수 있습니다.

때때로 생성된 출력의 데이터가 애플리케이션 데이터베이스의 동일한 데이터와 다르게 보일 수 있습니다. 이러한 경우 데이터 변환을 담당하는 ER 구성 요소를 결정해야 합니다. ER 데이터 소스 디버거 기능은 이 조사에 소요되는 시간과 비용을 크게 줄여줍니다. ER 형식의 실행을 중단하고 데이터 소스 디버거 인터페이스를 열 수 있습니다. 여기에서 사용 가능한 데이터 소스를 찾아보고 실행할 개별 데이터 소스를 선택할 수 있습니다. 이 수동 실행은 ER 형식의 실제 실행 중에 데이터 소스의 실행을 시뮬레이션합니다. 수신된 데이터를 분석할 수 있는 페이지에 결과가 표시됩니다.

데이터 소스 디버깅 기능을 켜려면 ER 사용자 매개 변수에서 **형식 실행 시 데이터 디버깅 활성화** 옵션을 **예** 로 설정합니다. 이후 ER 형식을 실행하여 아웃바운드 문서를 생성하는 동안 데이터 소스 디버깅을 시작할 수 있습니다. **디버깅 시작** 옵션을 사용하여 [ER 작업 디자이너](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document)에서 구성된 ER 형식에 대한 데이터 소스 디버깅을 시작할 수도 있습니다.

이번에는 실행된 ER 형식에 대한 데이터 소스 디버깅을 시작하기 위한 지침을 제공합니다. 정보가 데이터 흐름 및 데이터 변환을 이해하는 데 어떻게 도움이 되는지 설명합니다. 이 항목의 예시에서는 공급 업체 지급 처리를 위한 비즈니스 프로세스를 사용합니다.

## <a name="limitations"></a>한계

데이터 소스 디버거는 아웃바운드 문서를 생성하기 위해 실행되는 ER 형식으로 사용되는 데이터 소스의 데이터에 액세스하는 데 사용할 수 있습니다. 인바운드 문서를 구문 분석하도록 설계된 ER 형식의 데이터 소스를 디버그하는 데 사용할 수 없습니다.

다음 ER 형식 설정은 현재 데이터 소스 디버깅에 액세스할 수 없습니다.

- 형식 변환
- 형식 및 매핑 유효성 검사 규칙
- 표현식 활성화
- 메모리 내 데이터 수집 세부 정보

## <a name="prerequisites"></a>전제 조건

- 이 주제의 예를 완료하려면 다음 [역할](../sysadmin/tasks/assign-users-security-roles.md) 중 하나에 대한 액세스 권한이 있어야 합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 회사는 **DEMF** 로 설정되어야 합니다.

- 이 항목의 [부록 1](#appendix1)에 있는 단계에 따라 공급 업체 지급을 처리하는 데 필요한 Microsoft ER 솔루션의 구성 요소를 다운로드하십시오.
- 다운로드할 ER 솔루션을 사용하여 공급 업체 지급 처리를 위해 미지급금을 준비하려면 이 항목의 [부록 2](#appendix2)에 있는 단계를 따르십시오.

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a>지급 파일을 얻기 위해 공급 업체 지급을 처리하십시오.

1. 공급 업체 지급을 처리하려면 이 항목의 [부록 3](#appendix3)에 있는 단계를 따르십시오.

    ![공급 업체 지급 처리가 진행 중입니다.](./media/er-data-debugger-process-payment.png)

2. zip 파일을 다운로드하여 로컬 컴퓨터에 저장합니다.
3. zip 파일에서 **ISO20022 Credit transfer.xml** 결제 파일의 압축을 풉니다.
4. XML 파일 뷰어를 사용하여 추출된 결제 파일을 엽니다.

    지급 파일에서 공급 업체 은행 계좌의 국제 은행 계좌 번호(IBAN) 코드에는 공백이 없습니다. 따라서 **은행 계좌** 페이지에서 [입력한](#enteredIBANcode) 값과 다릅니다.

    ![공백이 없는 IBAN 코드.](./media/er-data-debugger-payment-file.png)

    ER 데이터 소스 디버거를 사용하여 IBAN 코드에서 공백을 자르는 데 사용되는 ER 솔루션의 구성 요소를 알 수 있습니다.

## <a name="turn-on-data-source-debugging"></a>데이터 소스 디버깅 켜기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **형식 실행 시 데이터 디버깅 활성화** 옵션을 **예** 로 설정합니다.

    > [!NOTE]
    > 이 매개 변수는 사용자 및 회사에 따라 다릅니다.

    ![사용자 매개 변수 대화 상자.](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a>디버깅을 위한 공급 업체 지급 처리

1. 공급 업체 지급을 처리하려면 이 항목의 [부록 3](#appendix3)에 있는 단계를 따르십시오.
2. 메시지 상자에서 **예** 를 선택하여 공급 업체 지급 처리를 중단하고 대신 **데이터 소스 디버그** 페이지에서 데이터 소스 디버깅을 시작할 것임을 확인합니다.

    ![확인 메시지 상자.](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a>결제 처리에 사용되는 디버그 데이터 소스

### <a name="debug-the-model-mapping"></a>모델 매핑 디버그

1. **데이터 소스 디버그** 페이지의 작업 창에서 **모델 매핑** 을 선택하여 이 ER 구성 요소에서 디버그를 시작합니다.
2. 왼쪽의 데이터 원본 창에서 **\$notSentTransactions** 데이터 원본을 선택한 다음 **모든 기록 읽기** 를 선택합니다.

    **1개 기록 읽기**, **10개 기록 읽기**, **100개 기록 읽기** 또는 **모든 기록 읽기** 를 선택하여 선택한 데이터 소스에서 적절한 수의 기록을 강제로 읽을 수 있습니다. 이러한 방식으로 실행 중인 ER 형식에서 데이터 소스에 대한 액세스를 시뮬레이션할 수 있습니다.

3. 오른쪽의 데이터 창에서 **모두 확장** 을 선택합니다.

    선택한 **기록 목록** 유형의 데이터 소스에 단일 기록이 포함되어 있음을 알 수 있습니다.

4. **\$notSentTransactions** 데이터 소스를 확장하고 중첩된 **vendBankAccountInTransactionCompany()** 메서드를 선택합니다.
5. **vendBankAccountInTransactionCompany()** 메서드를 확장하고 중첩된 **IBAN** 필드를 선택합니다.
6. **값 가져오기** 를 선택합니다.

    **값 가져오기** 를 선택하여 선택한 데이터 소스의 선택된 필드 값을 강제로 읽을 수 있습니다. 이러한 방식으로 실행 중인 ER 형식에서 이 필드에 대한 액세스를 시뮬레이션할 수 있습니다.

7. **모두 확장** 을 선택합니다.

    ![모델 매핑의 IBAN 필드 값입니다.](./media/er-data-debugger-debugging-model-mapping.png)

    보시다시피 모델 매핑은 잘린 공백에 대해 책임이 없습니다. 공급 업체 은행 계좌에 대해 반환하는 IBAN 코드에 공백이 포함되기 때문입니다. 따라서 데이터 소스 디버깅을 계속해야 합니다.

### <a name="debug-the-format-mapping"></a>형식 매핑 디버그

1. **데이터 소스 디버그** 페이지의 작업 창에서 **매핑 형식** 을 선택하여 이 ER 구성 요소에서 계속 디버그합니다.
2. **\$PaymentByDebtor** 데이터 원본을 선택한 다음 **모든 기록 읽기** 를 선택합니다.
3. **\$PaymentByDebtor** 를 확장합니다.
4. **\$PaymentByDebtor.Lines** 를 확장한 다음 **모든 기록 읽기** 를 선택합니다.
5. **\$PaymentByDebtor.Lines.CreditorAccount** 를 확장합니다.
6. **\$PaymentByDebtor.Lines.CreditorAccount.Identification** 을 확장한 다음 **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN** 을 선택합니다.
7. **값 가져오기** 를 선택합니다.
8. **모두 확장** 을 선택합니다.

    ![형식 매핑의 IBAN 필드 값입니다.](./media/er-data-debugger-debugging-format-mapping.png)

    보시다시피 형식 매핑의 데이터 소스는 잘린 공백에 대해 책임이 없습니다. 공급 업체 은행 계좌에 대해 반환하는 IBAN 코드에 공백이 포함되기 때문입니다. 따라서 데이터 소스 디버깅을 계속해야 합니다.

### <a name="debug-the-format"></a>형식 디버그

1. **디버그 데이터 소스** 페이지의 작업 창에서 **형식** 을 선택하여 이 ER 구성 요소에서 디버그를 계속합니다.
2. 형식 요소를 확장하여 **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** 를 선택한 다음 **모든 기록 읽기** 를 선택합니다.
3. 형식 요소를 확장하여 **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** 를 선택한 다음 **모든 기록 읽기** 를 선택합니다.
4. 형식 요소를 확장하여 **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** 을 선택한 다음 **값 가져오기** 를 선택합니다.
5. **모두 확장** 을 선택합니다.

    ![형식의 IBAN 필드 값입니다.](./media/er-data-debugger-debugging-format.png)

   보시다시피 형식 바인딩은 벤더 은행 계좌에 대해 반환하는 IBAN 코드에 공백이 포함되어 있기 때문에 잘린 공백에 대해 책임이 없습니다. 따라서 **BankIBAN** 요소는 공백을 자르는 형식 변환을 사용하도록 구성됩니다.

6. 데이터 소스 디버거를 닫습니다.

### <a name="review-the-format-transformations"></a>형식 변환 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 **지급 모델** \> **ISO20022 신용 전송** 을 선택하십시오.
3. **디자이너** 를 선택한 다음 요소를 확장하여 **문서** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** 을 선택합니다.

    ![형식 디자이너 페이지의 BankIBAN 요소입니다.](./media/er-data-debugger-referred-transformation.png)

    보시다시피 **BankIBAN** 요소는 **영숫자가 아닌 제거** 변환을 사용하도록 구성되어 있습니다.

4. **변환** 탭을 선택합니다.

    ![BankIBAN 요소에 대한 변환 탭입니다.](./media/er-data-debugger-transformation.png)

    보시다시피, **영숫자가 아닌 제거** 변환은 제공된 텍스트 스트링에서 공백을 자르는 표현식을 사용하도록 구성됩니다.

## <a name="start-to-debug-in-the-operation-designer"></a>작업 디자이너에서 디버그 시작

작업 디자이너에서 직접 실행할 수 있는 ER 형식의 초안 버전을 구성하는 경우 작업 창에서 **디버깅 시작** 을 선택하여 데이터 소스 디버거에 액세스할 수 있습니다.

![형식 디자이너 페이지에서 디버깅 시작 버튼.](./media/er-data-debugger-run-from-designer.png)

편집 중인 ER 형식의 형식 매핑 및 형식 구성 요소는 디버깅에 사용할 수 있습니다.

## <a name="start-to-debug-in-the-model-mapping-designer"></a>모델 매핑 디자이너에서 디버그 시작

**모델 매핑** 페이지에서 실행할 수 있는 ER 모델 매핑을 구성할 때 작업 창에서 **디버깅 시작** 을 선택하여 데이터 소스 디버거에 액세스할 수 있습니다.

![모델 매핑 디자이너 페이지에서 디버깅 시작 버튼을 클릭합니다.](./media/er-data-debugger-run-from-designer-mapping.png)

편집 중인 ER 매핑의 모델 매핑 구성 요소를 디버깅에 사용할 수 있습니다.

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a>부록 1 응급실 솔루션 받기

### <a name="download-an-er-solution"></a>응급실 솔루션 다운로드

ER 솔루션을 사용하여 처리되는 공급 업체 지급에 대한 전자 지급 파일을 [생성하려는](download-electronic-reporting-configuration-lcs.md) 경우 Microsoft Dynamics LCS(Lifecycle Services)의 공유 자산 라이브러리 또는 **ISO20022 크레딧 전달** 글로벌 저장소.

![구성 리포지토리 페이지에서 ER 지급 형식을 가져옵니다.](./media/er-data-debugger-import-from-repo.png)

선택한 ER 형식 외에도 **ISO20022 신용 전송** ER 솔루션의 일부로 다음 [구성](general-electronic-reporting.md#Configuration)을 Microsoft Dynamics 365 Finance 인스턴스로 자동으로 가져와야 합니다.

- **결제 모델** ER 데이터 모델 구성
- **ISO20022 신용 이체** ER 형식 구성
- **결제 모델 매핑 1611** ER 모델 매핑 구성
- **대상 ISO20022** ER 모델 매핑 구성에 대한 결제 모델 매핑

ER 프레임워크(**조직 관리** \> **전자 보고** \> **구성**)의 **구성** 페이지에서 이러한 구성을 찾을 수 있습니다.

![구성 페이지에서 가져온 구성입니다.](./media/er-data-debugger-configurations.png)

이전에 나열된 구성 중 구성 트리에서 누락된 구성이 있는 경우 **ISO20022 신용 전송** ER 지급 형식을 다운로드한 것과 동일한 방식으로 LCS 공유 자산 라이브러리에서 수동으로 다운로드해야 합니다.

### <a name="analyze-the-downloaded-er-solution"></a>다운로드한 ER 솔루션 분석

#### <a name="review-the-model-mapping"></a>모델 매핑 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **결제 모델** \> **결제 모델 매핑 1611** 을 선택합니다.
3. **디자이너** 를 선택합니다.
4. **결제 모델 매핑 ISO20022 CT** 매핑 기록을 선택합니다.
5. **디자이너** 를 선택한 다음 열려 있는 모델 매핑을 검토합니다.

    데이터 모델의 지급 필드는 처리 중인 공급 업체 **지급** 라인 목록을 반환하는 **\$notSentTransactions** 데이터 소스에 바인딩됩니다.

    ![모델 매핑 디자이너 페이지의 지급 필드입니다.](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a>형식 매핑 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **지급 모델** \> **ISO20022 신용 이체** 를 선택하십시오.
3. **디자이너** 를 선택합니다.
4. **매핑** 탭에서 열려 있는 형식 매핑을 검토합니다.

    **ISO20022CTReports** \> **XMLHeader** 파일의 **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** 요소는 데이터 모델의 **Payments** 필드에 대한 그룹 기록을 구성하도록 구성된 **\$PaymentByDebtor** 데이터 소스에 바인딩됩니다.

    ![형식 디자이너 페이지의 PmtInf 요소입니다.](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a>형식 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **지급 모델** \> **ISO20022 신용 이체** 를 선택하십시오.
3. **디자이너** 를 선택한 다음 열려 있는 형식을 검토합니다.

    **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** 아래의 형식 요소는 지급 파일에 공급 업체 계정의 IBAN 코드를 입력하도록 구성되어 있습니다.

    ![형식 디자이너 페이지의 BankIBAN 형식 요소입니다.](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a>부록 2 미지급금 구성

### <a name="modify-a-vendor-property"></a>공급 업체 속성 수정

1. **미지급금** \> **공급 업체** \> **모든 공급 업체** 로 이동합니다.
2. 공급 업체 **DE-01002** 를 선택한 다음 작업 창의 **공급 업체** 탭에 있는 **설정** 그룹에서 **은행 계좌** 를 선택합니다.
3. **식별** FastTab의 **IBAN** 필드에 <a name="enteredIBANcode"></a>**GB33 BUKB 2020 1555 5555 55** 를 입력합니다.
4. **저장** 을 선택합니다.

![공급 업체 은행 계좌 페이지에 설정된 IBAN 필드.](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a>결제 수단 설정

1. **미지급금** \> **지급 설정** \> **지급 방법** 으로 이동하십시오.
2. **SEPA CT** 결제 수단을 선택합니다.
3. **파일 형식** FastTab의 **파일 형식** 섹션에서 **일반 전자 내보내기** 형식 옵션을 **예** 로 설정합니다.
4. **내보내기 형식 구성** 필드에서 **ISO20022 신용 전송** ER 형식을 선택합니다.
5. **저장** 을 선택합니다.

![결제 방법 페이지의 파일 형식 설정.](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a>공급 업체 결제 추가

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. 새 지급 분개를 추가하십시오.
3. **라인** 을 선택하고 새 지급 라인을 추가합니다.
4. **계정** 필드에서 공급 업체 **DE-01002** 를 선택합니다.
5. **차변** 필드에 값을 입력합니다.
6. **지급 방법** 필드에서 **SEPA CT** 를 선택합니다.
7. **저장** 을 선택합니다.

![공급 업체 결제 페이지에 공급 업체 결제가 추가되었습니다.](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a>부록 3 공급 업체 결제 처리

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. **공급 업체 지급 분개** 페이지에서 이전에 생성한 지급 분개를 선택한 다음 **라인을** 선택합니다.
3. 지급 라인을 선택한 다음 **지급 상태** \> **없음** 을 선택합니다.
4. **결제 생성** 을 선택합니다.
5. **지급 방법** 필드에서 **SEPA CT** 를 선택합니다.
6. **은행 계좌** 필드에서 **DEMF OPER** 를 선택하십시오.
7. **지급 생성** 대화 상자에서 **확인** 을 선택합니다.
8. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
