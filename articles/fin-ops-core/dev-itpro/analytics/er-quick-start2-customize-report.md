---
title: ER 형식을 조정하여 맞춤형 전자 문서 생성
description: 이 항목에서는 사용자 지정 전자 문서를 생성하도록 Microsoft에서 제공하는 전자 보고(ER) 형식을 조정하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14976aab474b6571c2a25907f04fd4d7ae053e74
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460672"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a>ER 형식을 조정하여 맞춤형 전자 문서 생성

[!include[banner](../includes/banner.md)]

이 항목의 절차는 시스템 관리자 또는 전자 보고 기능 컨설턴트 역할의 사용자가 다음 작업을 수행할 수 있는 방법에 대해 설명합니다.

- [전자 보고(ER) 프레임워크](general-electronic-reporting.md)에 대한 매개 변수를 구성합니다.
- [공급업체 지불](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md)이 처리되는 동안 Microsoft에서 제공하고 지불 파일을 생성하는 데 사용되는 ER 구성을 가져옵니다.
- Microsoft에서 제공하는 표준 ER 형식 구성의 사용자 지정 버전을 만듭니다.
- 특정 은행의 요구 사항을 충족하는 지불 파일을 생성하도록 사용자 지정 ER 형식 구성을 수정합니다.
- 사용자 지정 ER 형식 구성에서 표준 ER 형식 구성에 대한 변경 사항을 적용합니다.

다음 모든 절차는 **GBSI** 회사에서 수행할 수 있습니다. 코딩이 필요하지 않습니다.

- [ER 프레임워크 구성](#ConfigureFramework)

    - [ER 매개 변수 구성](#ConfigureParameters)
    - [ER 구성 공급자 활성화](#ActivateProvider)

        - [ER 구성 제공자 목록 검토](#ReviewProvidersList)
        - [새 ER 구성 공급자 추가](#ActivateProvider)
        - [ER 구성 공급자 활성화](#ActivateAddedProvider)

- [표준 ER 형식 구성 가져오기](#ImportERSolution1)

    - [표준 ER 구성 가져오기](#ImportERFormat1)
    - [가져온 ER 구성 검토](#ReviewImportedERSolution)

- [처리를 위해 공급업체 지불 준비](#PrepareVendorPayment)

    - [공급업체 계정에 대한 은행 정보 추가](#AddBankAccount)
    - [공급업체 지불 입력](#EnterVendorPayment)

- [표준 ER 형식을 사용하여 공급업체 지불 처리](#ProcessVendorPayment1)

    - [전자 결제 방법 설정](#ConfigureMethodOfPayment1)
    - [공급업체 지불 처리](#ProcessPayment1)

- [표준 ER 형식 사용자 지정](#CustomizeProvidedFormat)

    - [사용자 지정 형식 만들기](#DeriveProvidedFormat)
    - [사용자 지정 형식 편집](#ConfigureDerivedFormat)
    - [사용자 정의 형식을 실행 가능으로 표시](#MarkFormatRunnable)

- [사용자 지정 ER 형식을 사용하여 공급업체 지불 처리](#ProcessVendorPayment2)

    - [전자 결제 방법 설정](#ConfigureMethodOfPayment2)
    - [공급업체 지불 처리](#ProcessPayment2)

- [표준 ER 형식 구성의 새 버전 가져오기](#ImportERSolution2)

    - [표준 ER 구성의 새 버전 가져오기](#ImportERFormat2)
    - [가져온 ER 형식 구성 검토](#ReviewImportedERFormat)

- [가져온 형식의 새 버전에서 변경 사항을 사용자 지정 형식으로 채택](#AdoptNewBaseVersion)

    - [사용자 정의 형식의 현재 초안 버전 완성](#CompleteDerivedFormat)
    - [사용자 지정 형식을 새 기본 버전으로 리베이스](#RebaseDerivedFormat)
    - [리베이스된 ER 형식을 사용하여 공급업체 지불 처리](#ProcessPayment3)

- [추가 리소스](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>ER 프레임워크 구성

전자 보고 함수 컨설턴트 역할의 사용자는 ER 프레임워크를 사용하여 표준 ER 형식의 사용자 지정 버전을 디자인하기 시작하기 전에 최소 ER 매개 변수 세트를 구성해야 합니다.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>ER 매개 변수 구성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개변수** 페이지의 **일반** 탭에서 **디자인 모드 활성화** 옵션을 **네** 로 설정합니다.
4. **첨부** 탭에서 다음 매개 변수를 설정합니다.

    - **구성** 필드에서 **USMF** 회사의 **파일** 유형을 선택하십시오.
    - **작업 아카이브**, **임시**, **기준선** 및 **기타** 필드에서 **파일** 유형을 선택합니다.

ER 매개 변수에 대한 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md)을 참조하세요.

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>ER 구성 공급자 활성화

추가된 모든 ER 구성은 ER 구성 공급자가 소유한 것으로 표시됩니다. 이 목적으로 **전자 보고** 작업 영역에서 활성화된 ER 구성 공급자가 사용됩니다. 따라서 ER 구성을 추가하거나 편집하기 전에 **전자 보고** 작업 영역에서 ER 구성 공급자를 활성화해야 합니다.

> [!NOTE]
> ER 구성의 소유자만 편집할 수 있습니다. 따라서 ER 구성을 편집하기 전에 **전자 보고** 작업 영역에서 적절한 ER 구성 공급자를 활성화해야 합니다.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>ER 구성 제공자 목록 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자 테이블** 페이지에서 각 공급자 레코드에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하세요. **Litware, Inc.**(`https://www.litware.com`)의 레코드가 이미 존재하는 경우 다음 절차를 건너뛰고, [새 ER 구성 공급자를 추가](#ActivateProvider)합니다.

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>새 ER 구성 공급자 추가

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자** 페이지에서 **새로 만들기** 를 선택합니다.
4. **이름** 필드에서 **Litware, Inc.** 를 입력합니다.
5. **인터넷 주소** 필드에 `https://www.litware.com`을 입력합니다.
6. **저장** 을 선택합니다.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>ER 구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택한 다음 **활성으로 설정** 을 선택합니다.

ER 구성 공급자에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하세요.

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>표준 ER 형식 구성 가져오기

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a>표준 ER 구성 가져오기

Microsoft Dynamics 365 Finance의 현재 인스턴스에 표준 ER 구성을 추가하려면 해당 인스턴스에 구성한 ER [리포지토리](general-electronic-reporting.md#Repository)에서 가져와야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택한 다음 **리포지토리** 를 선택하여 Microsoft 공급자의 리포지토리 목록을 봅니다.
3. **구성 저장소** 페이지에서 **글로벌** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다. Regulatory Configuration Service에 연결할 권한을 묻는 메시지가 표시되면 권한 부여 지침을 따르세요.
4. **구성 리포지토리** 페이지의 왼쪽 창에 있는 구성 트리에서 **BACS(영국)** 형식 구성을 선택합니다.
5. **버전** 빠른 탭에서 선택한 ER 형식 구성의 버전 **1.1** 을 선택합니다.
6. **가져오기** 를 선택하여 글로벌 리포지토리에서 현재 재무 인스턴스로 선택한 버전을 다운로드합니다.

![구성 리포지토리 페이지.](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> [글로벌 리포지토리](er-download-configurations-global-repo.md) 접속에 문제가 있는 경우 Microsoft Dynamics Lifecycle Services(LCS)에서 [구성을 다운로드](download-electronic-reporting-configuration-lcs.md)할 수 있습니다.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>가져온 ER 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **지불 모델** 을 확장합니다.
4. 선택한 **BACS(영국)** ER 형식 외에도 기타 필수 ER 구성을 가져왔습니다. 구성 트리에서 다음 ER 구성을 사용할 수 있는지 확인하십시오.

    - **지불 모델** – 이 구성은 결제 비즈니스 도메인의 데이터 구조를 나타내는 데이터 모델 ER 컴포넌트를 포함합니다.
    - **지불 모델 매핑 1611** – 이 구성에는 런타임 시 데이터 모델이 애플리케이션 데이터로 채워지는 방법을 설명하는 모델 매핑 ER 구성 요소가 포함됩니다.
    - **BACS(영국)** – 이 구성에는 형식 및 형식 매핑 ER 구성 요소가 포함됩니다. 형식 구성 요소는 보고서 레이아웃을 지정합니다. 형식 매핑 구성 요소는 모델 데이터 소스를 포함하고 런타임 시 이 데이터 소스를 사용하여 보고서 레이아웃을 채우는 방법을 지정합니다.

![트리에서 사용 가능한 지정된 ER 구성이 있는 구성 페이지.](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a>처리를 위해 공급업체 지불 준비

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a>공급업체 계정에 대한 은행 정보 추가

나중에 등록된 결제에서 참조할 공급업체 계정에 대한 은행 정보를 추가해야 합니다.

1. **미지급금** \> **공급 업체** \> **모든 공급 업체** 로 이동합니다.
2. **모든 공급업체** 페이지에서 **GB_SI_000001** 공급업체 계정을 선택한 다음 작업 창에서 **공급업체** 탭의 **설정** 그룹에서 **은행 계좌** 를 선택합니다.
3. **공급업체 은행 계좌** 페이지에서 **새로 만들기** 를 선택하고 다음 정보를 입력합니다.

    1. **은행 계좌** 필드에 **GBP OPER** 을 입력합니다.
    2. **은행 그룹** 필드에서 **BankGBP** 를 선택합니다.
    3. **은행 계좌 번호** 필드에 **202015** 를 입력합니다.
    4. **SWIFT 코드** 필드에 <a id="DefineSWIFTCode"></a>**CHASDEFXXXX** 를 입력합니다.
    5. **IBAN** 필드에 **GB33BUKB20201555555555** 를 입력합니다.
    6. **라우팅 번호** 필드에 기본값 <a id="DefineRoutingNumber"></a>**123456** 을 유지합니다.

    ![공급업체 은행 계좌 페이지.](./media/er-quick-start2-bank-account.png)

4. **저장** 을 선택합니다.
5. 페이지를 닫습니다.
6. **모든 공급업체** 페이지에서 **GB_SI_000001** 공급업체 계정을 엽니다.
7. 공급업체 세부정보 페이지에서 **편집** 을 선택하여 필요한 경우 페이지를 편집 가능하게 만듭니다.
8. **지불** 빠른 탭의 **은행 계좌** 필드에서 **GBP OPER** 을 선택합니다.

    ![공급업체 세부 정보 페이지.](./media/er-quick-start2-bank-account-reference.png)

9. **저장** 을 선택합니다.
10. 페이지를 닫습니다.

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a>공급업체 지불 입력

[지불 제안](../../../finance/accounts-payable/create-vendor-payments-payment-proposal.md)을 사용하여 새 공급업체 지불을 입력해야 합니다.

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. **공급업체 지불 일지** 페이지에서 **새로 만들기** 를 선택합니다.
3. **이름** 필드에서 **VendPay** 를 선택합니다.
4. **라인** 을 선택합니다.
5. **지불 제안** \> **지불 제안 생성** 을 선택합니다.
6. **공급업체 지불 제안** 대화 상자에서 **GB_SI_000001** 공급업체 계정에 대해서만 레코드를 필터링할 조건을 구성한 다음 **확인** 을 선택합니다.
7. **00000007_Inv** 송장의 라인을 선택한 다음 **결제 생성** 을 선택합니다.

    ![공급업체 지불 제안 대화 상자.](./media/er-quick-start2-payment-proposal.png)

8. 입력한 결제가 **전자** 결제 방법을 사용하도록 구성되었는지 확인합니다.

    ![공급업체 지불 페이지.](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a>표준 ER 형식을 사용하여 공급업체 지불 처리

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a>전자 결제 방법 설정

가져온 ER 형식 구성을 사용하도록 전자 결제 방법을 구성해야 합니다.

1. **미지급금** \> **지급 설정** \> **지급 방법** 으로 이동하십시오.
2. **지불 방법 - 공급업체** 페이지에서 왼쪽 창의 **전자** 결제 방법을 선택합니다.
3. **편집** 을 선택합니다.
4. **파일 형식** 빠른 탭에서 **일반 전자 내보내기 형식** 옵션을 **네** 로 설정합니다.
5. **내보내기 형식 구성** 필드에서 **BACS(영국)** 형식 구성을 선택합니다.

    ![지불 방법 - 공급자 페이지에서 표준 형식을 사용하여 공급자 지불을 처리하기 위한 전자 지불 방법을 설정합니다.](./media/er-quick-start2-method-of-payment1.png)

6. **저장** 을 선택합니다.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a>공급업체 지불 처리

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. **공급업체 지불 일지** 페이지에서 이전에 추가한 지불 저널을 선택한 다음 **라인** 을 선택합니다.
3. **공급업체 지불** 페이지에서 **지불 생성** 을 선택합니다.
4. **지불 생성** 대화 상자에서 다음 정보를 입력합니다.

    - **결제 방법** 필드에서 **전자** 를 선택합니다.
    - **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.

5. **확인** 을 선택합니다.
6. **전자 보고 매개 변수** 대화 상자에서 **제어 보고서 인쇄** 옵션을 **네** 로 설정한 다음 **확인** 을 선택합니다.

    ![전자 보고서 매개변수 대화 상자 페이지.](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > 지불 파일 외에도 이제 제어 보고서를 생성할 수 있습니다.

7. Zip 파일을 다운로드한 후 다음 파일의 압축을 풉니다.

    - Excel 형식의 제어 보고서
    - TXT 형식의 결제 파일

        제공된 ER 형식의 [구조](#PositionRoutingNumber)애 따라 생성된 파일의 지불 라인은 구성된 은행 계좌에 [정의](#DefineRoutingNumber)된 라우팅 번호로 시작합니다.

        ![TXT 형식의 결제 파일.](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>표준 ER 형식 사용자 지정

이 섹션에 표시된 예의 경우 Microsoft에서 제공하는 ER 구성을 사용하여 BACS 형식의 공급업체 지불 파일을 생성하려고 하지만 특정 은행의 요구 사항을 지원하려면 사용자 지정을 추가해야 합니다. 또한 새 버전의 ER 구성을 사용할 수 있게 되면 사용자 지정 형식을 업그레이드할 수 있기를 원합니다. 그러나 가장 저렴한 비용으로 업그레이드를 수행할 수 있기를 원합니다.

이 경우 Litware, Inc.의 대표자로서 **BACS(영국)** Microsoft 제공 구성을 기본으로 사용하여 새로운 ER 형식의 구성을 생성(파생)하여야 합니다

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>사용자 지정 형식 만들기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **결제 모델** 을 확장하고 **BACS(영국)** 를 선택합니다. Litware, Inc.는 이 ER 형식 구성의 버전 1.1을 사용자 지정 버전의 기반으로 사용합니다.
3. **구성 만들기** 를 선택하여 드롭다운 대화 상자를 엽니다. 이 대화 상자를 사용하여 사용자 지정 지불 형식에 대한 새 구성을 만들 수 있습니다.
4. **새로 만들기** 필드 그룹에서 **이름에서 파생: BACS(영국), Microsoft** 옵션을 선택합니다.
5. **이름** 필드에 **BACS(영국 사용자 지정)** 를 입력합니다.

    ![구성 만들기 드롭다운 대화 상자.](./media/er-quick-start2-add-derived-format.png)

6. **구성 만들기** 를 선택합니다.

**BACS(영국 사용자 지정)** ER 형식 구성의 버전 1.1.1이 생성됩니다. 이 버전은 **초안** [상태](general-electronic-reporting.md#component-versioning)이며 편집할 수 있습니다. 사용자 지정 ER 형식의 현재 내용은 Microsoft에서 제공하는 형식의 내용과 일치합니다.

![BACS(영국 사용자 지정) ER 형식 구성의 버전 1.1.1이 있는 구성 페이지.](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a>사용자 지정 형식 편집

은행별 요구 사항을 충족하도록 사용자 지정 형식을 구성해야 합니다. 예를 들어, 은행은 생성된 지불 파일에 처리된 공급업체 지불에서 에이전트 역할이 할당된 은행의 SWIFT(Society for Worldwide Interbank Financial Telecommunication) 코드를 포함하도록 요구할 수 있습니다. SWIFT 코드는 전 세계의 특정 은행을 식별하는 국제 은행 코드입니다. 은행 식별 코드(BIC)라고도 합니다. SWIFT 코드는 11자 길이여야 하며 생성된 지불 파일의 모든 지불 라인 시작 부분에 입력해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **결제 모델** 을 확장하고 **BACS(영국 사용자 지정)** 를 선택합니다.
3. **버전** 빠른 탭에서 선택한 구성의 버전 **1.1.1** 을 선택합니다.
4. **디자이너** 를 선택합니다.
5. **형식 디자이너** 페이지에서 **세부 정보 표시** 를 선택하여 형식 요소에 대한 자세한 정보를 봅니다.
6. 다음 요소를 확장하고 검토합니다.

    - **폴더** 유형의 **BACSReportsFolder** 요소. 이 요소는 ZIP 형식으로 출력을 생성하는 데 사용됩니다.
    - **파일** 유형의 **파일** 요소. 이 요소는 TXT 형식으로 결제 파일을 생성하는 데 사용됩니다.
    - **시퀀스** 유형의 **트랜잭션** 요소. 이 요소는 결제 파일에 단일 결제 라인을 생성하는 데 사용됩니다.
    - **시퀀스** 유형의 **트랜잭션** 요소. 이 요소는 단일 결제 라인의 개별 필드를 생성하는 데 사용됩니다.

7. **거래** 요소를 선택합니다.

    ![ER 작업 디자이너의 트랜잭션 요소입니다.](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > 제공된 보고서는 <a id="PositionRoutingNumber"></a>모든 지불 라인은 은행 라우팅 번호로 시작하도록 구성됩니다. **vendBankRouteNum** 형식 요소가 이를 위해 사용됩니다. 

8. **추가** 를 선택한 다음 **텍스트\\문자열** 유형을 추가하려는 형식 요소로 선택합니다.

    1. **이름** 필드에 **vendBankSWIFT** 를 입력합니다.
    2. **최소 길이** 필드에 **11** 을 입력합니다.
    3. **최대 길이** 필드에 **11** 을 입력합니다.
    4. **확인** 을 선택합니다.

    > [!NOTE]
    > **vendBankSWIFT** 요소는 생성된 파일에 공급업체 은행의 SWIFT 코드를 입력하는 데 사용됩니다.

9. 형식 구조 트리에서 **vendBankSWIFT** 를 선택합니다.
10. **위로 이동** 을 선택하여 선택한 형식 요소를 한 단계 위로 이동합니다. **vendBankSWIFT** 요소가 <a id="PositionSWIFTCode"></a>부모 **거래** 요소 아래의 첫 번째 요소가 될 때까지 이 단계를 반복합니다.

    ![VendBankSWIFT는 ER 운영 디자이너에서 트랜잭션의 첫 번째 요소로 사용됩니다.](./media/er-quick-start2-derived-format1.png)

11. **vendBankSWIFT** 형식 구조 트리에서 여전히 선택되어 있는 동안 **매핑** 탭을 선택한 다음 **모델** 데이터 소스를 확장합니다.
12. **model.Payment** \> **model.Payment.CreditorAgent** 를 확장하고 **model.Payment.CreditorAgent.BICFI** 데이터 원본 필드를 선택합니다. 이 데이터 소스 필드는 처리된 공급업체 지불에서 에이전트 역할이 할당된 공급업체 은행의 SWIFT 코드를 노출합니다.
13. **바인딩** 을 선택합니다. **vendBankSWIFT** 형식 요소는 이제 **model.Payment.CreditorAgent.BICFI** 데이터 원본 필드와 바인딩되므로 SWIFT 코드가 생성된 지불 파일에 입력됩니다.

    ![vendBankSWIFT 형식 요소는 ER 운영 디자이너의 model.Payment.CreditorAgent.BICFI 데이터 소스 필드와 바인딩됩니다.](./media/er-quick-start2-derived-format2.png)

14. **저장** 을 선택합니다.
15. 디자이너 페이지를 닫습니다.

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>사용자 정의 형식을 실행 가능으로 표시

이제 사용자 정의 형식의 첫 번째 버전이 만들어지고 상태가 **초안** 이 되었으므로 테스트 목적으로 실행할 수 있습니다. 보고서를 실행하려면 사용자 정의 ER 형식을 참조하는 지불 방법을 사용하여 공급업체 지불을 처리해야 합니다. 기본적으로 애플리케이션에서 ER 형식을 호출할 때 상태가 **완료됨** 또는 **공유됨** 인 버전만 [고려됩니다](general-electronic-reporting.md#component-versioning). 이 동작은 미완성 디자인이 사용되는 ER 형식을 방지하는 데 도움이 됩니다. 그러나 테스트 실행의 경우 애플리케이션에서 상태가 **초안** 인 ER 형식 버전을 사용하도록 강제할 수 있습니다. 이러한 방식으로 수정이 필요한 경우 현재 형식 버전을 조정할 수 있습니다. 자세한 내용은 [적용 가능성](electronic-reporting-destinations.md#applicability)을 참조하십시오.

ER 형식의 초안 버전을 사용하려면 ER 형식을 명시적으로 표시해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
4. **편집** 을 선택하여 필요에 따라 현재 페이지를 편집 가능하게 만듭니다.
5. 왼쪽 창의 구성 트리에서 **BACS(영국 사용자 지정)** 를 선택합니다.
6. **초안 실행** 옵션을 **예** 로 설정합니다.

    ![구성 페이지에서 초안 옵션을 실행합니다.](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a>사용자 지정 ER 형식을 사용하여 공급업체 지불 처리

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a>전자 결제 방법 설정

사용자 정의 ER 형식이 공급업체 지불을 처리하는 데 사용되도록 전자 지불 방법을 구성해야 합니다.

1. **미지급금** \> **지급 설정** \> **지급 방법** 으로 이동하십시오.
2. **지불 방법 - 공급업체** 페이지에서 왼쪽 창의 **전자** 결제 방법을 선택합니다.
3. **편집** 을 선택합니다.
4. **파일 형식** 빠른 탭에서 **일반 전자 내보내기 형식** 옵션을 **네** 로 설정합니다.
5. **내보내기 형식 구성** 필드에서 **BACS(영국 사용자 지정)** 형식 구성을 선택합니다.

    ![지불 방법 - 공급자 페이지에서 사용자 지정 형식을 사용하여 공급자 지불을 처리하기 위한 전자 지불 방법을 설정합니다.](./media/er-quick-start2-method-of-payment2.png)

6. **저장** 을 선택합니다.

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a>공급업체 지불 처리

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. **공급업체 지불 일지** 페이지에서 이전에 만든 지불 저널을 선택합니다.
3. **라인** 을 선택합니다.
4. **공급업체 지불** 페이지의 그리드 위에서 **지불 상태** \> **없음** 을 선택합니다.
5. **결제 생성** 을 선택합니다.
6. **지불 생성** 대화 상자에서 다음 정보를 입력합니다.

    - **결제 방법** 필드에서 **전자** 를 선택합니다.
    - **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.

7. **확인** 을 선택합니다.
8. **전자 보고 매개 변수** 대화 상자에서 **제어 보고서 인쇄** 옵션을 **네** 로 설정한 다음 **확인** 을 선택합니다.

    > [!NOTE]
    > 지불 파일 외에도 제어 보고서만 생성할 수 있습니다.

9. Zip 파일을 다운로드한 후 다음 파일의 압축을 풉니다.

    - Excel 형식의 제어 보고서
    - TXT 형식의 결제 파일

        사용자 정의 ER 형식의 구조에 따라 이제 생성된 파일의 지불 라인이 결제가 처리된 공급업체의 은행 계좌에 [입력](#DefineSWIFTCode)된 SWIFT 코드로 [시작](#PositionSWIFTCode)합니다.

        ![공급업체 지불을 처리하는 데 사용되는 TXT 형식의 지불 파일입니다.](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a>표준 ER 형식 구성의 새 버전 가져오기

이 섹션에 표시된 예의 경우 기술 자료 문서 [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046)에 대한 알림을 받습니다. 이 알림은 Microsoft에서 게시한 **BACS(영국)** ER 형식의 새 버전에 대해 알립니다. 제어 보고서 외에도 이 새 버전을 사용하면 공급업체 지불이 처리되는 동안 사용자가 지불 조언 보고서와 메모 보고서를 생성할 수 있습니다. 해당 기능을 사용하기 시작하려고 합니다.

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a>표준 ER 구성의 새 버전 가져오기

현재 재무 인스턴스에 ER 구성의 새 버전을 추가하려면 구성한 ER [리포지토리](general-electronic-reporting.md#Repository)에서 가져와야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택한 다음 **리포지토리** 를 선택하여 Microsoft 공급자의 리포지토리 목록을 봅니다.
3. **구성 저장소** 페이지에서 **글로벌** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다. Regulatory Configuration Service에 연결할 권한을 묻는 메시지가 표시되면 권한 부여 지침을 따르세요.
4. **구성 리포지토리** 페이지의 왼쪽 창에 있는 구성 트리에서 **BACS(영국)** 형식 구성을 선택합니다.
5. **버전** 빠른 탭에서 선택한 ER 형식 구성의 버전 **3.3** 을 선택합니다.
6. **가져오기** 를 선택하여 글로벌 리포지토리에서 현재 재무 인스턴스로 선택한 버전을 다운로드합니다.

![구성 리포지토리 페이지, 버전 FastTab, 가져오기 버튼.](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> [글로벌 리포지토리](er-download-configurations-global-repo.md) 접속에 문제가 있는 경우 LCS에서 [구성을 다운로드](download-electronic-reporting-configuration-lcs.md)할 수 있습니다.

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a>가져온 ER 형식 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **결제 모델** 을 확장하고 **BACS(영국)** 를 선택합니다.
4. **버전** 빠른 탭에서 버전 **3.3** 을 선택합니다.
5. **디자이너** 를 선택합니다.
6. **형식 디자이너** 페이지에서 **BACSReportsFolder** 형식 요소를 확장합니다.
7.  버전 3.3에는 **지불 상담 보고서** 형식 요소가 포함되며, 이는 공급업체 지불이 처리될 때 지불 조언 보고서를 생성하는 데 사용됩니다.

    ![ER 작업 디자이너의 PaymentAdviceReport 형식 요소입니다.](./media/er-quick-start2-imported-solution2.png)

8. 디자이너 페이지를 닫습니다.

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a>가져온 형식의 새 버전에서 변경 사항을 사용자 지정 형식으로 채택

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a>사용자 정의 형식의 현재 초안 버전 완성

사용자 정의 형식의 현재 상태를 유지하려면 상태를 **초안** 에서 **완료됨** 변경하여 초안 버전 1.1.1을 완료합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **결제 모델** 을 확장하고 **BACS(영국)** 를 선택한 다음 **BACS(영국 사용자 지정)** 을 선택합니다.
4. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 1.1.1의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 1.1.2가 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 형식을 추가로 변경할 수 있습니다.

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a>사용자 지정 형식을 새 기본 버전으로 리베이스

사용자 지정으로 **BACS(영국)** 형식의 버전 3.3의 새로운 기능을 사용하려면 사용자 지정 구성에 대한 기본 구성 버전 **BACS(영국 사용자 지정)** 를 변경해야 합니다. 이 과정은 [리베이스](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase)라고 합니다. **BACS(영국)** 의 버전 1.1 대신 버전 3.3을 사용하세요.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **결제 모델** 을 확장하고 **BACS(영국 사용자 지정)** 를 선택합니다.
3. **버전** 빠른 탭에서 버전 **1.1.2** 를 선택한 다음 **리베이스** 를 선택합니다.
4. **리베이스** 대화 상자의 **대상 버전** 필드에서 버전 **3.3** 을 기본 구성으로 선택하여 새 기본으로 적용하고 구성을 업데이트하는 데 사용합니다.

    ![리베이스 대화 상자입니다.](./media/er-quick-start2-rebase1.png)

5. **확인** 을 선택합니다.
6. 초안 버전의 번호가 기본 버전의 변경 사항을 반영도록 **1.1.2** 에서 **3.3.2** 로 변경된 것을 볼 수 있습니다.

    사용자 지정 버전과 새 기본 버전을 병합할 때 자동으로 병합할 수 없는 형식 변경으로 인해 일부 충돌이 발견될 수 있습니다.

    ![구성 페이지에서 충돌이 있는 재구성된 구성입니다.](./media/er-quick-start2-rebase2.png)

    충돌이 발견되면 형식 디자이너에서 수동으로 해결해야 합니다.

7. **버전** 빠른 탭에서 버전 **3.3.2** 를 선택합니다.
8. **디자이너** 를 선택합니다.
9. **형식 디자이너** 페이지의 **세부 정보** 빠른 탭에서 리베이스 충돌 레코드를 선택한 다음 **기본 값 적용** 을 선택합니다.

    ![ER 작업 디자이너에서 충돌 레코드를 리베이스합니다.](./media/er-quick-start2-rebase3.png)

10. **저장** 을 선택합니다.

    리베이스 충돌 레코드가 더 이상 **세부 정보** 빠른 탭에 표시되지 않아야 합니다.

    ![ER 작업 디자이너에서 충돌 해결됨.](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > 기본 모델의 버전 3을 이 ER 형식으로 사용해야 함을 확인하여 충돌을 해결했습니다.

11. **BACSReportsFolder** \> **파일** \> **트랜잭션** \> **트랜잭션** 을 확장합니다.
12. **매핑** 탭에서 사용자 정의 ER 형식의 버전 3.3.2에는 사용자 정의(**vendBankSWIFT** 형식 요소 및 바인딩) 및 Microsoft에서 제공한 기본 ER 형식 버전 3.3의 새로운 기능(**지불 상담 보고서** 형식 요소와 중첩 요소 및 구성된 바인딩)이 포함됩니다. 몇 번의 마우스 클릭만으로 새 기본 버전의 수정 사항을 사용자 정의와 병합하여 적용할 수 있습니다.

    ![ER 작업 디자이너의 병합된 형식입니다.](./media/er-quick-start2-rebase5.png)

13. 디자이너 페이지를 닫습니다.

> [!NOTE]
> 리베이스 작업은 되돌릴 수 있습니다. 이 리베이스를 취소하려면 **버전** 빠른 탭에서 버전 **1.1.1** 의 **BACS(영국 커스텀)** 형식을 선택한 다음 **이 버전 받기** 를 선택합니다. 그러면 버전 3.3.2의 번호가 1.1.2로 다시 지정되고 초안 버전 1.1.2의 내용은 버전 1.1.1의 내용과 일치합니다.

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a>리베이스된 ER 형식을 사용하여 공급업체 지불 처리

1. **미지급금** \> **지급** \> **공급 업체 지급 분개** 로 이동합니다.
2. **공급업체 지불 일지** 페이지에서 이전에 만든 지불 저널을 선택합니다.
3. **라인** 을 선택합니다.
4. **공급업체 지불** 페이지의 그리드 위에서 **지불 상태** \> **없음** 을 선택합니다.
5. **결제 생성** 을 선택합니다.
6. **지불 생성** 대화 상자에서 다음 정보를 입력합니다.

    - **결제 방법** 필드에서 **전자** 를 선택합니다.
    - **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.

7. **확인** 을 선택합니다.
8. **전자 보고 매개 변수** 대화 상자에서 다음 정보를 입력합니다.

    - **인쇄 제어 보고서** 옵션을 **예** 로 설정합니다.
    - **인쇄 결제 조언** 옵션을 **예** 로 설정합니다.

    ![전자 보고서 매개변수 대화 상자.](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > 지불 파일 외에도 이제 제어 보고서와 지불 조언 보고서를 모두 생성할 수 있습니다.

9. **확인** 을 선택합니다.
10. Zip 파일을 다운로드한 후 다음 파일의 압축을 풉니다.

    - Excel 형식의 제어 보고서
    - Excel 형식의 결제 조언 보고서

        ![Excel 형식의 결제 조언 보고서.](./media/er-quick-start2-payment-advice-report.png)

    - TXT 형식의 결제 파일

        생성된 파일의 지불 라인이 결제가 처리된 공급업체의 은행 계좌에 입력된 SWIFT 코드로 시작합니다.

        ![리베이스된 ER 형식을 사용하여 공급업체 지불을 처리하는 데 사용되는 TXT 형식의 지불 파일입니다.](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [Lifecycle Services에서 ER 구성 다운로드](download-electronic-reporting-configuration-lcs.md)
- [구성 서비스의 글로벌 리포지토리에서 ER 구성 다운로드](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
