---
title: 애플리케이션 클래스 메서드를 호출하는 ER 표현식 디자인
description: 이번에는 애플리케이션 클래스의 필수 메서드를 호출하여 전자 보고 구성에서 기존 애플리케이션 논리를 재사용하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "8460721"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>애플리케이션 클래스 메서드를 호출하는 ER 표현식 디자인

[!include [banner](../../includes/banner.md)]

이번에는 ER 표현식에서 애플리케이션 클래스의 필수 메서드를 호출하여 [전자 보고(ER)](../general-electronic-reporting.md) 구성에서 기존 애플리케이션 논리를 재사용하는 방법에 대해 설명합니다. 호출 클래스에 대한 인수 값은 런타임에 동적으로 정의할 수 있습니다. 예를 들어, 값은 정확성을 보장하기 위해 구문 분석 문서의 정보를 기반으로 할 수 있습니다.

이 항목의 예시에서는 애플리케이션 데이터 업데이트를 위해 수신 은행 거래 명세서를 구문 분석하는 프로세스를 설계합니다. 수신 은행 명세서를 IBAN(국제 은행 계좌 번호) 코드가 포함된 텍스트(.txt) 파일로 받게 됩니다. 은행 거래 명세서 가져오기 프로세스의 일부로 이미 사용 가능한 논리를 사용하여 IBAN 코드의 정확성을 검증해야 합니다.

## <a name="prerequisites"></a>전제 조건

이 항목의 절차는 **시스템 관리자** 또는 **전자 보고 개발자** 역할이 할당된 사용자를 위한 것입니다.

모든 데이터 세트를 사용하여 절차를 완료할 수 있습니다.

완료하려면 다음 파일을 다운로드하여 저장해야 합니다. [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

이번에는 Litware, Inc. 샘플 회사에 필요한 ER 구성을 생성합니다. 따라서 이 항목의 절차를 완료하기 전에 다음 단계를 수행해야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지에서 **Litware, Inc.** 샘플 회사의 구성 제공자가 사용 가능하고 활성으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 먼저 [구성 공급자 만들기의 단계를 완료하고 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md)해야 합니다.

## <a name="import-a-new-er-model-configuration"></a>새 ER 모델 구성 가져오기

1. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 구성 공급자에 대한 타일을 선택합니다.
2. **저장소** 를 선택합니다.
3. **현지화 리포지토리** 페이지에서 **필터 표시** 를 선택합니다.
4. 전역 리포지토리 기록을 선택하려면 **이름** 필터 필드를 추가합니다.
5. **이름** 필드에 **글로벌** 을 입력하십시오. 이후 **포함** 필터 연산자를 선택합니다.
6. **적용** 을 선택합니다.
7. **[열기](../er-download-configurations-global-repo.md#open-configurations-repository)** 를 선택하여 선택한 리포지토리의 ER 구성 목록을 검토합니다.
8. **구성 리포지토리** 페이지의 구성 트리에서 **결제 모델** 을 선택합니다.
9. **버전** FastTab에서 **가져오기** 버튼을 사용할 수 있는 경우 해당 버튼을 선택한 다음 **예** 를 선택합니다.

    **가져오기** 버튼을 사용할 수 없으면 **결제 모델** ER 구성의 선택한 버전을 이미 가져온 것입니다.

10. **구성 리포지토리** 페이지를 닫은 다음 **현지화 리포지토리** 페이지를 닫습니다.

## <a name="add-a-new-er-format-configuration"></a>새 ER 형식 구성 추가

수신 은행 명세서를 TXT 형식으로 구문 분석하기 위해 새 ER 형식을 추가합니다.

1. **현지화 구성** 페이지에서 **보고 구성** 타일을 선택합니다.
2. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **결제 모델** 을 선택합니다.
3. **구성 만들기** 를 선택합니다. 
4. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. **새로 만들기** 필드에 **데이터 모델 PaymentModel 기반 형식** 을 입력합니다.
    2. **이름** 필드에 **은행 거래 명세서 가져오기 형식(샘플)** 을 입력합니다.
    3. **데이터 가져오기 지원** 필드에서 **예** 를 선택합니다.
    4. **구성 생성** 을 선택하여 구성 생성을 마칩니다.

## <a name="design-the-er-format-configuration--format"></a>ER 형식 구성 설계 – 형식

외부 파일의 예상 구조를 TXT 형식으로 나타내는 ER 형식을 디자인합니다.

1. 추가한 **은행 거래 명세서 가져오기 형식(샘플)** 형식 구성에 대해 **디자이너** 를 선택합니다.
2. **형식 디자이너** 페이지의 왼쪽 창에 있는 형식 구조 트리에서 **루트 추가** 를 선택합니다.
3. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **Text\\Sequence** 를 선택하여 **시퀀스** 형식 구성 요소를 추가합니다.
    2. **이름** 필드에 **루트** 를 입력합니다.
    3. **특수 문자** 필드에서 **새 줄 - Windows(CR LF)** 를 선택합니다. 이 설정에 따라 구문 분석 파일의 각 행은 별도의 기록으로 간주됩니다.
    4. **확인** 을 선택합니다.

4. **추가** 를 선택합니다.
5. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **텍스트\\시퀀스** 를 선택합니다.
    2. **이름** 필드에 **행** 을 입력합니다.
    3. **다수** 필드에서 **하나 많은** 을 선택합니다. 이 설정에 따라 구문 분석 파일에 최소한 한 줄이 있어야 합니다.
    4. **확인** 을 선택합니다.

6. 트리에서 **Root\\Rows** 를 선택한 다음 **시퀀스 추가** 를 선택합니다.
7. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. **이름** 필드에 **필드** 를 입력합니다.
    2. **다중도** 필드에서 **정확히 하나** 를 선택하십시오.
    3. **확인** 을 선택합니다.

8. 트리에서 **Roo\\tRows\\Fields** 를 선택한 다음 **추가** 를 선택합니다.
9. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **Text\\스트링** 을 선택합니다.
    2. **이름** 필드에 **IBAN** 을 입력합니다.
    3.. **확인** 을 선택합니다.

10. **저장** 을 선택합니다.

이제 구문 분석 파일의 각 행에 IBAN 코드만 포함되도록 구성이 설정되었습니다.

![형식 디자이너 페이지의 은행 거래 명세서 가져오기 형식(샘플) 형식 구성.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>ER 형식 구성 설계 – 데이터 모델에 매핑

구문 분석 파일의 정보를 사용하여 데이터 모델을 채우는 ER 형식 매핑을 설계합니다.

1. **형식 디자이너** 페이지의 작업 창에서 **모델에 형식 매핑** 을 선택합니다.
2. **데이터 원본에 대한 모델 매핑** 페이지의 작업 창에서 **새로 만들기** 를 선택합니다.
3. **정의** 필드에서 **BankToCustomerDebitCreditNotificationInitiation** 을 선택하십시오.
4. **이름** 필드에 **데이터 모델에 매핑** 을 입력합니다.
5. **저장** 을 선택합니다.
6. **디자이너** 를 선택합니다.
7. **모델 매핑 디자이너** 페이지의 **데이터 원본** 유형 트리에서 **Dynamics 365 for Operations\\클래스** 를 선택합니다.
8. **데이터 소스** 섹션에서 **루트 추가** 를 선택하여 IBAN 코드 검증을 위해 기존 애플리케이션 로직을 호출하는 데이터 소스를 추가하십시오.
9. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. **이름** 필드에 **코\_드** 를 입력합니다.
    2. **클래스** 필드에 **ISO7064** 를 입력하거나 선택합니다.
    3. **확인** 을 선택합니다.

10. **데이터 원본 유형** 트리에서 다음 단계를 따르십시오.

    1. **형식** 데이터 소스를 확장합니다.
    2. 확장 **형식\\루트: 시퀀스(루트)**.
    3. 확장 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    4. 확장 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)**.

11. **데이터 모델** 트리에서 다음 단계를 따르십시오.

    1. 데이터 모델의 **지급** 필드를 확장하십시오.
    2. **Payments\\Creditor Account(CreditorAccount)** 를 확장합니다.
    3. **Payments\\Creditor Account(CreditorAccount)\\Identification** 을 확장합니다.
    4. **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN** 을 확장합니다.

12. 구성된 형식의 구성 요소를 데이터 모델 필드에 바인딩하려면 다음 단계를 따르십시오.

    1. 선택 **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    2. **지급** 을 선택합니다.
    3. **바인딩** 을 선택합니다. 이 설정에 따라 구문 분석 파일의 각 행은 단일 지급로 간주됩니다.
    4. **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)\\IBAN: String(IBAN)** 선택.
    5. **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN** 을 선택합니다.
    6. **바인딩** 을 선택합니다. 이 설정에 따라 데이터 모델의 **IBAN** 필드는 구문 분석 파일의 값으로 채워집니다.

    ![모델 매핑 디자이너 페이지의 데이터 모델 필드에 형식 구성 요소 바인딩.](../media/design-expressions-app-class-er-02.png)

13. **유효성 검사** 탭에서 다음 단계에 따라 잘못된 IBAN 코드가 포함된 구문 분석 파일의 모든 줄에 대한 오류 메시지를 표시하는 [유효성 검사](../general-electronic-reporting-formula-designer.md#Validation) 규칙을 추가합니다.

    1. **새로 만들기** 를 선택한 다음 **조건 편집** 을 선택합니다.
    2. **수식 디자이너** 페이지의 **데이터 원본** 트리에서 **ISO** 7064 애플리케이션 클래스를 나타내는 **Check\_codes** 데이터 원본을 확장하여 이 클래스의 사용 가능한 메서드를 봅니다.
    3. **Check\_codes\\verifyMOD1271\_36** 을 선택합니다.
    4. **데이터 원본 추가** 를 선택합니다.
    5. **수식** 필드에 다음 [표현식](../general-electronic-reporting-formula-designer.md#Binding)을 입력합니다. **Check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. **저장** 을 선택한 다음 페이지를 닫습니다.
    7. **메시지 편집** 을 선택합니다.
    8. **수식 디자이너** 페이지의 **수식** 필드에 **CONCATENATE('잘못된 IBAN 코드가 발견되었습니다:&nbsp;', format.Root.Rows.Fields.IBAN)** 를 입력합니다.
    9. **저장** 을 선택한 다음 페이지를 닫습니다.

    이러한 설정에 따라 유효성 검사 조건은 **ISO7064** 애플리케이션 클래스의 기존 **verifyMOD1271\_36** 메서드를 호출하여 잘못된 IBAN 코드에 대해 *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* 를 반환합니다. IBAN 코드의 값은 구문 분석 텍스트 파일의 내용을 기반으로 호출 메서드의 인수로 런타임에 동적으로 정의됩니다.

    ![모델 매핑 디자이너 페이지의 유효성 검사 규칙입니다.](../media/design-expressions-app-class-er-03.png)

14. **저장** 을 선택합니다.
15. **모델 매핑 디자이너** 페이지를 닫은 다음 **모델에서 데이터 원본 매핑** 페이지를 닫습니다.

## <a name="run-the-format-mapping"></a>형식 매핑 실행

테스트 목적으로 이전에 다운로드한 SampleIncomingMessage.txt 파일을 사용하여 형식 매핑을 실행합니다. 생성된 출력에는 선택한 텍스트 파일에서 가져오고 실제 가져오기 중에 사용자 지정 데이터 모델로 이식된 데이터가 포함됩니다.

1. **모델에서 데이터 원본으로의 매핑** 페이지에서 **실행** 을 선택합니다.
2. **전자 보고서 매개 변수** 페이지에서 **찾아보기** 를 선택하고 다운로드한 **SampleIncomingMessage.txt** 파일을 찾아 선택합니다.
3. **확인** 을 선택합니다.
4. **Model to datasource 매핑** 페이지에 잘못된 IBAN 코드에 대한 오류 메시지가 표시됩니다.

    ![데이터 소스에 대한 모델 매핑 페이지에서 형식 매핑을 실행한 결과입니다.](../media/design-expressions-app-class-er-04.png)

5. 선택한 파일에서 가져와 데이터 모델로 이식된 데이터를 나타내는 XML 형식의 출력을 검토합니다. 가져온 텍스트 파일의 세 줄만 오류 없이 처리되었음을 알 수 있습니다. 4행의 IBAN 코드가 유효하지 않아 건너뛰었습니다.

    ![XML 출력.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
