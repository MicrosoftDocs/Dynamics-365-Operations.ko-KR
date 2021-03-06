---
title: 전자 문서를 생성하기 위한 전자 보고 구성 사용자 정의
description: 이 항목에서는 사용자 지정 전자 문서를 생성하는데 사용되는 Microsoft에서 제공하는 전자 보고(ER) 구성을 사용자 지정하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: 2c8cf4866b6a8c239359d726d8cd4f03a9eb4137
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460995"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>전자 문서를 생성하기 위한 전자 보고 구성 사용자 정의

[!include[banner](../includes/banner.md)]

[전자 보고(ER) 프레임워크](general-electronic-reporting.md)를 사용하면 Microsoft가 Microsoft Dynamics 365 Finance 인스턴스에 제공하는 ER [구성](general-electronic-reporting.md#Configuration)을 업로드할 수 있습니다. 이러한 방식으로 Microsoft에서 제공하는 구성은 전자 고객 송장(전자 송장)을 생성하는 데 사용되는 ER 솔루션의 역할을 할 수 있습니다. 이 ER 솔루션을 사용하여 소스 코드를 편집할 필요 없이 사용자 지정 데이터베이스 필드에 액세스하고 특정 요구 사항을 준수하는 전자 인보이스를 생성하도록 사용자 지정 ER 솔루션을 구성할 수 있습니다.

## <a name="overview"></a>개요

이 항목의 예에서는 전자 송장을 발행하는 모든 고객의 새 사용자 정의 속성으로 연방 세금 식별 코드를 지정해야 합니다. 따라서 생성되는 모든 전자 인보이스에 세금 코드를 입력해야 하는 새 항목을 추가하여 현재 사용 중인 인보이스의 구조를 사용자 정의해야 합니다.

이 항목의 절차는 시스템 관리자, 전자 보고 개발자 또는 전자 보고 기능 컨설턴트 역할의 사용자가 재무 인스턴스의 다음 작업을 수행할 수 있는 방법에 대해 설명합니다.

- [ER 프레임워크 사용을 시작하는 데 필요한 최소한의 ER 매개변수 집합을 구성합니다](#ConfigureER).
- [전자 인보이스를 생성하기 위해 제공되는 표준 ER 구성의 초기 버전을 가져옵니다](#ImportERConfigurations1).
- [표준 ER 구성을 사용하기 시작하도록 미수금 매개변수를 구성합니다](#ConfigureAR1).
- [고객에게 송장을 보내는 법인 매개변수 구성](#ConfigureLE).
- [전자 송장 발행을 위한 고객 기록 준비](#ConfigureCustomer1).
- [표준 ER 구성을 사용하여 고객 송장 추가, 게시 및 보내기](#ProcessInvoice1).
- [고객에 대한 연방 세금 식별 코드를 관리하기 위해 사용자 지정 데이터베이스 필드 추가](#AddCustomField).
- [ER 메타데이터를 새로 고쳐 ER 모델 매핑 디자이너에 대한 데이터베이스 변경을 활성화합니다](#RefreshERMetadata).
- [새 세금 코드가 포함된 전자 인보이스를 생성하도록 사용자 지정 ER 구성을 설계합니다](#DesignCustomERConfigurations).
- [사용자 지정 ER 구성을 사용하기 시작하도록 미수금 매개변수를 구성합니다](#ConfigureAR2).
- [전자 송장 발행을 위한 고객 기록 업데이트](#ConfigureCustomer2).
- [사용자 지정 ER 구성을 사용하여 고객 송장 추가, 게시 및 보내기](#ProcessInvoice2).
- [전자 인보이스를 생성하기 위해 제공되는 표준 ER 구성의 새 버전을 가져옵니다](#ImportERConfigurations2).
- [사용자 지정 ER 구성에서 표준 ER 구성의 새 버전에 대한 변경 사항을 채택합니다](#RebaseCustomERConfigurations).
- [사용자 지정 ER 구성의 새 버전을 사용하여 고객 송장 추가, 게시 및 보내기](#ProcessInvoice3).

이러한 모든 절차는 **DEMF** 회사에서 완료할 수 있습니다.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>ER 프레임워크 구성

전자 보고 기능 컨설턴트 또는 전자 보고 개발자 역할의 사용자는 최소 ER 매개변수 세트를 구성해야 합니다. 그런 다음 ER 프레임워크를 사용하여 전자 인보이스를 생성하는 데 사용되는 ER 솔루션의 표준 구성에 대한 사용자 지정 버전을 설계할 수 있습니다.

### <a name="configure-er-parameters"></a>ER 매개 변수 구성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개변수** 페이지의 **일반** 탭에서 **디자인 모드 활성화** 옵션을 **네** 로 설정합니다.
4. **첨부 파일** 탭에서 **구성** 필드의 **파일** 을 선택합니다.
5. **작업 아카이브**, **임시**, **기준선** 및 **기타** 필드에서 **파일** 유형을 선택합니다.

ER 매개 변수에 대한 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md)을 참조하세요.

### <a name="activate-an-er-configuration-provider"></a>ER 구성 공급자 활성화

추가된 모든 ER 구성은 ER 구성 공급자가 소유한 것으로 표시됩니다. 이 목적으로 **전자 보고** 작업 영역에서 활성화된 ER 구성 공급자가 사용됩니다. 따라서 ER 구성을 추가하거나 편집하기 전에 **전자 보고** 작업 영역에서 ER 구성 공급자를 활성화해야 합니다.

> [!NOTE]
> ER 구성의 소유자만 편집할 수 있습니다. 따라서 ER 구성을 편집하기 전에 **전자 보고** 작업 영역에서 적절한 ER 구성 공급자를 활성화해야 합니다.

#### <a name="review-the-list-of-er-configuration-providers"></a>ER 구성 공급자 목록 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자 테이블** 페이지에서 각 공급자 레코드에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하세요. **Litware, Inc.**(`https://www.litware.com`)의 레코드가 이미 존재하는 경우 다음 절차를 건너뛰고, [새 ER 구성 공급자를 추가](#AddProvider)합니다.

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>새 ER 구성 공급자 추가

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자** 페이지에서 **새로 만들기** 를 선택합니다.
4. **이름** 필드에서 **Litware, Inc.** 를 입력합니다.
5. **인터넷 주소** 필드에 `https://www.litware.com`을 입력합니다.
6. **저장** 을 선택합니다.

#### <a name="activate-an-er-configuration-provider"></a>ER 구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택한 다음 **활성으로 설정** 을 선택합니다.

ER 구성 공급자에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하세요.

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>표준 ER 구성의 초기 버전 가져오기

현재 재무 인스턴스에 표준 ER 구성을 추가하려면 해당 인스턴스에 구성한 ER [리포지토리](general-electronic-reporting.md#Repository)에서 가져와야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택한 다음 **리포지토리** 를 선택하여 Microsoft 공급자의 리포지토리 목록을 봅니다.
3. **구성 저장소** 페이지에서 **글로벌** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다. Regulatory Configuration Service에 연결할 권한을 묻는 메시지가 표시되면 권한 부여 지침을 따르세요.
4. **구성 리포지토리** 페이지의 왼쪽 창에 있는 구성 트리에서 **Peppol 판매 인보이스** 형식 구성을 선택합니다.
5. **버전** 빠른 탭에서 버전 **11.2.2** 를 선택합니다.
6. **가져오기** 를 선택하여 글로벌 리포지토리에서 선택한 버전을 다운로드합니다.

![구성 리포지토리 페이지.](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> [글로벌 리포지토리](er-download-configurations-global-repo.md) 접속에 문제가 있는 경우 Microsoft Dynamics Lifecycle Services(LCS)에서 [구성을 다운로드](download-electronic-reporting-configuration-lcs.md)할 수 있습니다.

### <a name="review-the-imported-er-configurations"></a>가져온 ER 형식 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지에서 **구성 요소 구성** 빠른 탭을 확장합니다.
4. 왼쪽 창의 구성 트리에서 **송장 모델** 을 확장한 다음 **UBL 매도 인보이스** 를 확장합니다.

선택한 **Peppol 판매 인보이스** ER 형식 외에도 기타 필수 ER 구성을 가져왔습니다. ER 구성의 새 버전이 글로벌 리포지토리 및 LCS에 지속적으로 게시되어 해당 솔루션이 새로운 요구 사항을 준수하도록 하기 때문에 필요한 데이터 모델 구성 및 해당 모델 매핑 구성의 최신 버전을 가져왔습니다.

![구성 페이지.](./media/er-quick-start3-imported-solution1a.png)

버전을 가져온 경우 현재 Finance 인스턴스의 ER 구성이 있을 상태를 시뮬레이션하려면 **11.2.2** 의 **Peppol 판매 인보이스** 과거의 ER 형식(예: 2019년 8월 7일)은 다음 단계를 따르세요.

- 작업 창에서 **삭제** 를 선택하여 2019년 8월 7일 이후에 게시된 모든 ER 구성을 삭제합니다. **송장 모델**, **송장 모델 매핑**(처음에는 이름이 **고객 송장 모델 매핑**), **UBL 매도 인보이스** 및 **Peppol 판매 인보이스** 구성만 남겨 두어야 합니다.
- 나머지 ER 구성의 경우 **버전** 빠른 탭에서 **삭제** 를 선택하여 2019년 8월 7일 이후에 게시된 모든 버전의 ER 구성을 삭제합니다.

그런 다음 구성 트리에서 다음 구성을 사용할 수 있는지 확인합니다.

- **송장 모델** ER 데이터 모델 구성(처음에는 **고객 송장 모델**):

    - 버전 11에는 송장 발행 비즈니스 도메인의 데이터 구조를 나타내는 데이터 모델 ER 구성요소의 버전 10이 포함되어 있습니다. 이 ER 구성은 가져오기를 위해 선택한 **Peppol 판매 인보이스** ER 형식의 상위 항목으로 가져왔습니다.
    - 버전 50에는 데이터 모델 ER 구성요소의 버전 31이 포함됩니다. 이 ER 구성은 **송장 모델 매핑** ER 모델 매핑 2019년 8월 7일 버전의 상위 항목으로 가져왔습니다.

    ![구성 페이지의 송장 모델 ER 데이터 모델 구성입니다.](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > 이 데이터 모델의 버전 50이 표시되지 않으면 글로벌 리포지토리를 열고 **송장 모델 매핑** ER 구성 버전 50.19를 가져옵니다.

- **송장 모델 매핑** ER 모델 매핑 구성(처음에는 **고객 송장 모델 매핑**):

    - 버전 50.19는 **송장 모델** ER 데이터 모델 구성 버전 50의 최신 구현으로 가져왔습니다. 런타임에 데이터 모델이 애플리케이션 데이터로 채워지는 방법을 설명하는 두 가지 모델 매핑 ER 구성 요소가 포함되어 있습니다.

    ![구성 페이지의 송장 모델 매핑 ER 모델 매핑 구성입니다.](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > 이 모델 매핑의 버전 50.19가 표시되지 않으면 글로벌 리포지토리를 열고 **송장 모델 매핑** ER 구성 버전 50.19를 가져옵니다.

- **UBL 매도 인보이스** ER 형식 구성:

    - 버전 11.2에는 형식 및 형식 매핑 ER 구성 요소가 포함됩니다. 형식 구성 요소는 보고서 레이아웃을 지정합니다. 형식 매핑 구성 요소는 모델 데이터 원본을 포함하고 데이터 원본이 런타임 시 보고서 레이아웃을 채우는 데 사용되는 방법을 지정합니다. 이 ER 형식은 UBL(범용 비즈니스 언어) 형식의 전자 청구서를 생성하도록 구성되었습니다. 이 구성은 가져오기를 위해 선택한 **Peppol 판매 인보이스** ER 형식의 부로로 가져왔습니다.

- **Peppol 매도 인보이스** ER 형식 구성:

    - 버전 11.2.2에는 PEPPOL(Pan-European Public Procurement OnLine) 형식의 전자 송장을 생성하도록 구성된 형식 및 형식 매핑 ER 구성 요소가 포함되어 있습니다.

    ![구성 페이지의 Peppol 판매 청구서 ER 형식 구성.](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>수취 계정 매개 변수 구성

1. **수취 계정** \> **설정** \> **수취 계정 매개 변수** 로 이동합니다.
2. **전자 문서** 탭에서 **전자 보고** 빠른 탭의 **판매 및 무료 텍스트 송장** 필드에서 **Peppol 판매 인보이스** 를 선택합니다.
3. **저장** 을 선택합니다.

![수취 계정 매개 변수 페이지의 전자 문서 탭.](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>법인 매개 변수 구성

1. **조직 관리** \> **조직** \> **법인** 으로 이동합니다.
2. 선택한 **DEMF** 회사에 대해 **은행 계좌 정보** 빠른 탭의 **라우팅 번호** 필드에 **1234** 를 입력합니다.
3. **저장** 을 선택합니다.
4. **법인** 페이지를 닫습니다.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>고객 기록 준비

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. **모든 고객** 페이지에서 **DE-014** 고객 계정 링크를 선택합니다.

### <a name="add-a-customer-contact"></a>고객 연락처 추가

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. 작업 창의 **고객** 탭에 있는 **계정** 그룹에서 **연락처** 를 선택합니다.
3. **연락처 추가** 를 선택합니다.
4. **연락처** 페이지의 **이름** 필드에서 조회를 열고 **아담 카터** 를 선택한 다음 **선택** 을 선택하여 조회를 닫습니다.
5. **저장** 을 선택합니다.
6. **연락처** 페이지를 닫습니다.

### <a name="define-a-primary-contact"></a>기본 연락처 정의

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. **판매 인구 통계** 빠른 탭의 **기본 담당자** 필드에서 **아담 카터** 를 선택합니다.

### <a name="set-the-e-invoicing-option"></a>전자 인보이스 옵션 설정

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. **인보이스 및 배송** 빠른 탭에서 **전자 인보이스** 옵션을 **네** 로 설정합니다.
3. **저장** 을 선택합니다.
4. **모든 고객** 페이지를 닫습니다.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>표준 ER 구성을 사용하여 고객 송장 추가, 게시 및 보내기

이제 가져온 표준 ER 구성을 사용하여 고객에게 무료 텍스트 송장을 전자적으로 보낼 수 있습니다.

### <a name="add-a-new-invoice"></a>새 청구서 추가

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **자유 텍스트 청구서** 페이지에서 **새로 만들기** 를 선택합니다.
3. **자유 텍스트 인보이스 헤더** 빠른 탭의 **고객 계정** 필드에서 **DE-014** 를 선택합니다.
4. **송장 라인** 빠른 탭에 송장 라인이 자동으로 추가됩니다. 이 라인에서 다음 필드를 설정합니다.

    - **설명** 필드에 **Notebook** 을 입력합니다.
    - **주 계정** 필드에서 **401100** 을 선택합니다.
    - **단가** 필드에 **1000** 을 입력합니다.

5. **저장** 을 선택합니다.

![무료 텍스트 송장 페이지.](./media/er-quick-start3-add-invoice.png)

자세한 내용은 [자유 텍스트 송장 만들기](../../../finance/accounts-receivable/create-free-text-invoice-new.md)를 참조하세요.

### <a name="post-a-new-invoice"></a>새 청구서 기장

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **자유 텍스트 인보이스** 페이지의 작업 창에서 **기장** 을 선택합니다.
3. **자유 텍스트 송장 게시** 대화 상자에서 **확인** 을 선택합니다.

![자유 텍스트 송장 세부 정보 페이지.](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>게시된 인보이스 보내기

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **자유 텍스트 인보이스** 페이지에서 작업 창의 **문서** 그룹에서 **보내기** \> **원본** 을 선택합니다.

    ![원본 송장의 미리 보기.](./media/er-quick-start3-send-invoice.png)

3. **자유 텍스트 인보이스** 페이지를 닫습니다.

### <a name="analyze-a-generated-e-invoice"></a>생성된 전자 인보이스 분석

1. **조직 관리** \> **전자 보고** \> **전자 보고 작업** 으로 이동합니다.
2. **전자 보고 작업** 페이지에서 작업 설명 **전자 인보이스 XML 보내기** 가 있는 초기 레코드를 선택합니다.
3. **파일 표시** 를 선택하여 생성된 파일 목록에 액세스합니다.

    ![전자 보고 작업 페이지.](./media/er-quick-start3-jobs-list.png)

4. **열기** 를 선택하여 생성된 전자 인보이스 XML 파일을 다운로드합니다.
5. 전자 인보이스 XML 파일을 분석합니다. 고객 세금 스키마는 현재 **schemeID** 및 **schemeAgencyID** XML 특성으로 나타납니다. 또한 **cbc:CustomizationID** XML 요소에는 현재 다음 텍스트가 포함되어 있습니다. `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![생성된 전자 송장 XML 파일의 미리보기입니다.](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>사용자 정의 데이터베이스 필드 추가

[사용자 정의 필드](../../fin-ops/get-started/user-defined-fields.md)를 사용하여 현재 재무 인스턴스에서 다음 사용자 지정을 수행할 수 있습니다.

- 모든 고객에 대한 연방 세금 식별 코드를 저장하는 새로운 사용자 지정 데이터베이스 필드를 추가하여 데이터베이스 구조를 사용자 지정합니다.
- 새 사용자 정의 데이터베이스 필드에 세금 코드 값을 입력하는 데 사용할 수 있는 새 데이터 입력 필드를 추가하여 **고객** 페이지를 사용자 지정합니다.

사용자 정의를 수행하려면 다음 단계를 따르세요.

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. **모든 고객** 페이지에서 **DE-014** 고객 계정 링크를 선택합니다.
3. **일반** 빠른 탭에서 **언어** 아래의 빈 영역을 마우스 오른쪽 버튼으로 클릭한 다음 **개인화: UpperGroup** 을 선택합니다.

    **일반** 빠른 탭의 콘텐츠가 강조 표시되고 **개인화** 메뉴가 나타납니다.

4. **개인화** 메뉴에서 **필드 추가** 를 선택합니다.
5. **열 추가** 대화 상자에서 **새 필드 만들기** 를 선택합니다.
6. **새 필드 만들기** 대화 상자에서 **테이블 이름** 필드의 **고객** 을 선택합니다.
7. **이름 접두사** 필드에 **FederalTaxID** 를 입력합니다.

    > [!NOTE]
    > 전체 필드 이름은 **FederalTaxID\_Custom** 으로 자동 정의되었습니다.

8. **레이블** 필드에 **연방 세금 ID** 를 입력합니다.
9. **유형** 필드에서 **텍스트** 를 선택합니다.
10. **길이** 필드에 **20** 을 입력합니다.
11. **저장** 을 선택합니다.
12. 표시되는 메시지 상자에서 **네** 를 선택하여 **고객** 테이블에 대해 새로운 **FederalTaxID** 필드 입력을 만들 것을 확인합니다.
13. **삽입** 을 선택하여 <a name="insert_custom_field"></a> **FederalTaxID\_Custom** 필드를 현재 페이지에 추가합니다.

    ![모든 고객 페이지.](./media/er-quick-start3-create-new-field.gif)

14. **모든 고객** 페이지를 닫습니다.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>ER 메타데이터 새로 고침

추가한 사용자 정의 필드를 ER 모델 매핑 디자이너에 [표시](electronic-reporting-er-configure-parameters.md#frequently-asked-questions)되도록 하려면 ER 메타데이터를 새로 고쳐야 합니다.

1. **조직 관리** \> **전자 보고** \> **테이블 참조 다시 빌드** 로 이동합니다.
2. **데이터 모델 업데이트** 대화 상자에서 **확인** 을 선택합니다.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>맞춤형 ER 구성 설계

Microsoft 제공 ER 구성을 사용하여 새 세금 코드가 포함된 전자 인보이스를 생성하도록 사용자 지정 ER 구성을 디자인할 수 있습니다.

### <a name="customize-the-data-model-configuration"></a>데이터 모델 구성 사용자 지정

전자 보고 기능 컨설턴트 역할의 사용자는 사용자 지정 ER 데이터 모델을 디자인할 수 있습니다.

#### <a name="add-a-custom-data-model-configuration"></a>사용자 지정 데이터 모델 구성 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** 을 선택합니다.
3. 작업 창에서 **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자의 **새로 만들기** 필드에서 **이름에서 파생: 고객 송장 모델, Microsoft** 를 선택하여 새 사용자 지정 ER 데이터 모델 구성이 ER 데이터 모델 구성을 기반으로 해야 함을 나타냅니다.
5. **이름** 필드에서 **청구서 모델(Litware)** 을 입력합니다.
6. **구성 만들기** 를 선택하여 새 ER 구성을 추가합니다.

이제 ER 데이터 모델 디자이너를 사용하여 **초안** [상태](general-electronic-reporting.md#component-versioning)의 **인보이스 모델(Litware)** ER 구성의 버전 50.1을 편집할 수 있습니다.

![구성 페이지에서 ER 구성의 버전 50.1.](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>사용자 지정 데이터 모델 구성

연방 세금 식별 코드 값을 제공하기 위해 새 필드를 추가하여 사용자 정의 데이터 모델을 수정해야 합니다. 이 코드는 이 데이터 모델을 데이터 소스로 사용할 모든 ER 형식에 대한 고객 데이터의 일부입니다.

1. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **청구서 모델(Litware)** 을 선택합니다.
2. **버전** 빠른 탭에서 **초안** 상태인 선택한 ER 데이터 모델 구성의 버전 **50.1** 을 선택합니다.
3. 작업 창에서 선택한 구성 버전에 대해 **디자이너** 를 선택합니다.
4. **데이터 모델 디자이너** 페이지의 데이터 모델 트리에서 **고객 정보(고객)** 를 선택합니다.
5. **새로 만들기** 를 선택합니다.
6. 드롭다운 대화 상자의 **새 노드로** 필드에서 기본값 **활성 노드의 하위** 을 수락합니다.
7. **이름** 필드에 **FederalTaxID\_Litware** 를 입력합니다.
8. **항목 형식** 필드에서 기본값 **문자열** 을 수락합니다.
9. **추가** 를 선택하고 **저장** 을 선택합니다.

    ![데이터 모델 디자이너 페이지.](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > **레이블** 및 **설명** 필드는 새 필드의 목적을 설명합니다. 이 필드는 여러 언어로 채울 수 있습니다. 자세한 내용은 [전자 보고의 다국어 보고서 디자인](er-design-multilingual-reports.md)을 참조하세요.

10. **데이터 모델 디자이너** 페이지를 닫습니다.

#### <a name="complete-a-custom-data-model-configuration"></a>사용자 지정 데이터 모델 구성 완료

다른 사용자 지정 ER 구성을 추가할 수 있도록 사용자 지정 ER 데이터 모델 구성의 버전 50.1로 작업을 [완료](general-electronic-reporting.md#component-versioning)해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **청구서 모델** 을 확장하고 **청구서 모델(Litware)** 을 선택합니다.
3. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 50.1의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 50.2가 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 데이터 모델 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 50.1이 완료되었습니다.](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>모델 매핑 구성 사용자 지정

전자 보고 개발자 역할의 사용자는 사용자 지정 ER 모델 매핑을 디자인할 수 있습니다.

#### <a name="add-a-custom-model-mapping-configuration"></a>사용자 지정 모델 매핑 구성 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** 을 확장하고 **고객 청구서 모델 매핑** 을 선택합니다.
3. 작업 창에서 **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자의 **새로 만들기** 필드에서 **이름에서 파생: 고객 송장 모델 매핑, Microsoft** 를 선택하여 새 사용자 지정 ER 데이터 모델 매핑 구성이 ER 데이터 모델 매핑 구성을 기반으로 해야 함을 나타냅니다.
5. **이름** 필드에서 **청구서 모델 매핑(Litware)** 을 입력합니다.
6. **대상 모델** 필드에서 **인보이스 모델(Litware)** 을 선택합니다.

    > [!IMPORTANT]
    > 이 단계는 매우 중요합니다. 생략하면 구성된 모델 매핑에서 사용자 지정 데이터 모델을 사용할 수 없습니다.

7. **구성 만들기** 를 선택하여 새 ER 구성을 추가합니다.

![구성 페이지의 사용자 지정 모델 매핑 구성 추가.](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>사용자 지정 모델 매핑 구성

사용자 지정 모델 매핑을 수정하고 사용자 지정 데이터 모델의 **FederalTaxID\_Litware** 필드가 런타임 시 애플리케이션 데이터로 채워지는 방식을 지정해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** \> **고객 청구서 모델 매핑** 을 확장하고 **청구서 모델 매핑(Litware)** 을 선택합니다.
3. 작업 창에서 **디자이너** 를 선택합니다.
4. **데이터 소스 매핑에 대한 모델** 페이지에서 **고객 송장** 매핑을 선택합니다.

    ![데이터 소스 매핑 페이지에 대한 모델.](./media/er-quick-start3-select-customer-mapping.png)

5. **디자이너** 를 선택합니다.
6. **모델 매핑 디자이너** 페이지의 **데이터 소스** 창에서 **CustInvoiceJour** 애플리케이션 테이블을 나타내는 **CustInvoiceJour** 데이터 원본을 확장합니다.
7. **CustInvoiceJour** 에서 **관계** 를 확장하여 **CustInvoiceJour** 테이블에 대한 다대일(N:1) 유형의 관계 목록을 검토합니다.
8. **CustInvoiceJour** \> **관계** 에서 **고객(CustTable)** 을 확장하여 **고객(CustTable)** 테이블의 필드 및 관계에 액세스합니다.
9. [이전에](#insert_custom_field) 구현한 **FederalTaxID\_Custom** 데이터 원본 필드를 선택합니다.
10. **데이터 모델** 창에서 **고객 정보(고객)** 를 선택하고 **FederalTaxID\_Litware** 데이터 모델 필드를 선택합니다.
11. **바인딩** 을 선택합니다.

    ![모델 매핑 디자이너 페이지.](./media/er-quick-start3-customize-model-mapping.gif)

12. **저장** 을 선택합니다.
13. **모델 매핑 디자이너** 페이지를 닫습니다.
14. **데이터 소스 매핑 모델링** 페이지를 닫습니다.

#### <a name="complete-a-custom-model-mapping-configuration"></a>사용자 지정 모델 매핑 구성 완료

사용자 지정 ER 모델 매핑 구성의 버전 50.19.1로 작업을 [완료](general-electronic-reporting.md#component-versioning)하여 사용할 수 있도록 해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** \> **고객 청구서 모델 매핑** 을 확장하고 **청구서 모델 매핑(Litware)** 을 선택합니다.
3. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 50.19.1의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 50.19.2가 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 모델 매핑 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 50.19.1이 완료되었습니다.](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> 지원되는 구성 [수명 주기](general-electronic-reporting-manage-configuration-lifecycle.md)는 데이터베이스 변경의 수명 주기를 다루지 않습니다. 현재 재무 인스턴스에서 버전 50.19.1의 **송장 모델 매핑(Litware)** 구성을 내보내고 **CustTable** 테이블에서 **FederalTaxID\_Custom** 필드를 포함하지 않는 다른 인스턴스로 가져오려고 시도하면 예외가 발생합니다. 가져온 ER 구성이 대상 Finance 인스턴스의 메타데이터와 호환되지 않는다는 예외가 표시됩니다.

### <a name="customize-the-format-configuration"></a>형식 구성 사용자 지정

전자 보고 기능 컨설턴트 역할의 사용자는 사용자 지정 ER 형식을 디자인할 수 있습니다.

#### <a name="add-a-custom-format-configuration"></a>사용자 지정 형식 구성 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** \> **UBL 판매 청구서** 를 확장하고 **Peppol 판매 청구서** 를 선택합니다.
3. 작업 창에서 **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자의 **새로 만들기** 필드에서 **이름에서 파생: Peppol 판매 청구서, Microsoft** 를 선택하여 새 사용자 지정 ER 형식 구성이 ER 형식 구성을 기반으로 해야 함을 나타냅니다.
5. **이름** 필드에서 **Peppol 판매 청구서(Litware)** 를 입력합니다.
6. **데이터 모델** 필드에서 **인보이스 모델(Litware)** 을 선택하여 사용자 지정 데이터 모델 및 모델 매핑 구성 요소를 사용합니다.

    > [!NOTE]
    > 이 단계는 매우 중요합니다. 생략하면 구성된 형식에서 사용자 지정 데이터 모델을 사용할 수 없습니다.

7. **데이터 모델** 필드에서 **InvoiceCustomer** 루트 정의를 선택합니다.
8. **구성 만들기** 를 선택하여 새 ER 구성을 추가합니다.

![구성 페이지의 사용자 지정 형식 구성 추가.](./media/er-quick-start3-adding-custom-format.png)

이제 ER 작업 디자이너를 사용하여 **초안** [상태](general-electronic-reporting.md#component-versioning)의 **Peppol 판매 청구서(Litware)** ER 구성의 버전 11.2.2.1을 편집할 수 있습니다.

![구성 페이지에서 ER 구성의 버전 11.2.2.1.](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>사용자 지정 형식 구성

인보이스 발행 고객의 연방 세금 식별 코드 값을 입력하려면 새 형식 요소를 추가하여 사용자 정의 형식을 수정해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** \> **UBL 판매 청구서** \> **Peppol 판매 청구서** 를 확장하고 **Peppol 판매 청구서(Litware)** 를 선택합니다.
3. 작업 창에서 **디자이너** 를 선택합니다.
4. 형식 트리에서 **XMLHeader** \> **청구서** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** 를 확장하고 **cbc:ID** 를 선택합니다.
5. **추가** 를 선택하고 **XML** \> **특성** 을 선택합니다.
6. **구성 요소 속성** 대화 상자의 **이름** 필드에 **FederalTaxID** 를 입력합니다.
7. **확인** 을 선택하여 새 형식 요소를 추가하고 생성된 XML 파일의 **FederalTaxID** XML 특성을 만듭니다.
8. 형식 트리의 **XMLHeader** \> **청구서** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID** 에서 **FederalTaxID** 를 선택합니다.
9. **위로 이동** 을 선택합니다.

![형식 디자이너 페이지의 새 형식 요소입니다.](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>사용자 지정 형식 매핑 구성

1. **형식 디자이너** 페이지의 **매핑** 탭에서 **모델** 유형의 **송장** 데이터 소스를 확장합니다.
2. **송장** 에서 **고객 정보(고객)** 를 확장하고 **FederalTaxID\_Litware** 를 선택합니다.
3. **바인딩** 을 선택합니다.

    ![형식 디자이너 페이지.](./media/er-quick-start3-customized-format-mapping.png)

4. **모델** 유형의 **송장** 데이터 원본을 선택한 다음 **편집** 을 선택합니다.
5. **버전** 필드에서 사용자 지정 데이터 모델의 버전 **1** 을 선택한 다음 **확인** 을 선택합니다.
6. **저장** 을 선택합니다.
7. **형식 디자이너** 페이지를 닫습니다.

#### <a name="complete-a-custom-format-configuration"></a>사용자 지정 형식 구성 완료

사용자 지정 ER 형식 구성의 버전 11.2.2.1로 작업을 [완료](general-electronic-reporting.md#component-versioning)하여 사용할 수 있도록 해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **고객 청구서 모델** \> **UBL 판매 청구서** \> **Peppol 판매 청구서** 를 확장하고 **Peppol 판매 청구서(Litware)** 를 선택합니다.
3. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 11.2.2.1의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 11.2.2.2가 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 형식 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 11.2.2.1이 완료되었습니다.](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>사용자 지정 ER 구성을 사용하기 시작하도록 미수금 매개변수를 구성합니다

1. **수취 계정** \> **설정** \> **수취 계정 매개 변수** 로 이동합니다.
2. **전자 문서** 탭에서 **전자 보고** 빠른 탭의 **판매 및 무료 텍스트 송장** 필드에서 **Peppol 판매 인보이스(Litware)** 를 선택합니다.
3. **저장** 을 선택합니다.

![수취 계정 매개 변수 페이지, 전자 문서 탭, 전자 보고 빠른 탭.](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>연방 세금 식별 코드를 추가하여 고객 기록 업데이트

1. **수취 계정** \> **고객** \> **모든 고객** 으로 이동합니다.
2. **모든 고객** 페이지에서 **DE-014** 고객 계정 링크를 선택합니다.
3. **일반** 빠른 탭의 **연방 세금 ID** 필드에 **LITWARE-6789** 를 입력합니다.
4. **저장** 을 선택합니다.

    ![DE-014 고객 세부 정보 페이지.](./media/er-quick-start3-added-tax-id-value.png)

5. **모든 고객** 페이지를 닫습니다.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>사용자 지정 ER 구성을 사용하여 고객 송장 추가, 게시 및 보내기

### <a name="select-and-send-a-posted-invoice"></a>게시된 인보이스 선택 및 전송

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **자유 텍스트 인보이스** 페이지에서 이전에 추가하고 게시한 송장을 선택합니다.
3. 작업 창의 **문서** 그룹에서 **보내기** \> **원본** 을 선택합니다.
4. **자유 텍스트 인보이스** 페이지를 닫습니다.

### <a name="analyze-a-generated-e-invoice"></a>생성된 전자 인보이스 분석

1. **조직 관리** \> **전자 보고** \> **전자 보고 작업** 으로 이동합니다.
2. **전자 보고 작업** 페이지에서 작업 설명 **전자 인보이스 XML 보내기** 가 있는 최신 레코드를 선택합니다.
3. **파일 표시** 를 선택하여 생성된 파일 목록에 액세스합니다.
4. **열기** 를 선택하여 생성된 전자 인보이스 XML 파일을 다운로드합니다.
5. 전자 인보이스 XML 파일을 분석합니다. 사용자 정의에 따라 사용자 정의 세금 스키마는 **schemeID** 및 **schemeAgencyID** XML 특성 외에도 사용자 정의 **FederalTaxID** XML 특성을 포함합니다. 이 새 XML 속성의 값은 인보이스 발행 고객에 대해 입력한 **LITWARE-6789** 연방 세금 ID에 의해 지정됩니다.

    ![사용자 지정으로 생성된 전자 송장 XML 파일의 미리보기입니다.](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>표준 ER 구성의 최신 버전 가져오기

Finance 인스턴스에서 표준 ER 구성 세트를 [최신](general-electronic-reporting-manage-configuration-lifecycle.md)으로 유지하려면, 해당 인스턴스에 구성된 ER [리포지토리](general-electronic-reporting.md#Repository)에서 사용할 수 있게 될 때마다 새 버전을 가져와야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택한 다음 **리포지토리** 를 선택하여 Microsoft 공급자의 리포지토리 목록을 봅니다.
3. **구성 저장소** 페이지에서 **글로벌** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다. Regulatory Configuration Service에 연결할 권한을 묻는 메시지가 표시되면 권한 부여 지침을 따르세요.
4. **구성 리포지토리** 페이지의 왼쪽 창에 있는 구성 트리에서 **Peppol 판매 인보이스** 형식 구성을 선택합니다.
5. **버전** 빠른 탭에서 PEPPOL BIS 3 형식의 고객 전자 송장을 지원하기 위해 출시된 선택된 ER 형식 구성의 버전 **32.6.7** 을 선택합니다. 자세한 내용은 [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic)을 참조하세요.
6. **가져오기** 를 선택하여 글로벌 리포지토리에서 현재 재무 인스턴스로 선택한 버전을 다운로드합니다.

![구성 리포지토리 페이지에서 버전 32.6.7이 선택되었습니다.](./media/er-quick-start3-import-solution2.png)

이 프로세스를 자동화하는 방법에 대한 정보는 [업데이트된 버전의 ER 구성 가져오기](er-download-updated-versions-global-repo.md)를 참조하세요.

### <a name="review-the-imported-er-configurations"></a>가져온 ER 형식 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성 구성 요소** 빠른 탭을 확장합니다.
4. 왼쪽 창의 구성 트리에서 **청구서 모델** 을 확장합니다. 가져온 ER 데이터 모델 구성 중 하나에서 **고객 송장 모델** 이름이 **송장 모델** 로 변경되었습니다.
5. 왼쪽 창의 구성 트리에서 **청구서 모델 매핑** 을 확장합니다. 가져온 ER 모델 매핑 구성 중 하나에서 **고객 송장 모델 매핑** 이름이 **송장 모델 매핑** 으로 변경되었습니다.
6. **UBL 판매 청구서** \> **Peppol 판매 청구서** 를 확장합니다.

선택한 **Peppol 판매 인보이스** ER 형식 외에도 기타 필수 ER 구성의 최신 버전을 가져왔습니다. ER 구성의 새 버전이 글로벌 리포지토리 및 LCS에 지속적으로 게시되어 해당 ER 솔루션이 새로운 요구 사항을 준수하도록 하기 때문에 필요한 데이터 모델 구성 및 해당 모델 매핑 구성의 최신 버전을 가져왔습니다.

구성 트리에서 다음 ER 구성을 사용할 수 있는지 확인합니다.

- **송장 모델** ER 데이터 모델 구성:

    - 버전 206(이상)에는 송장 발행 비즈니스 도메인의 데이터 구조를 나타내는 데이터 모델 ER 구성요소의 버전 24(이상)가 포함되어 있습니다. 이 ER 구성은 사용 가능한 최신 **송장 모델 매핑** ER 모델 매핑 구성의 상위 항목으로 가져왔습니다.

    ![구성 페이지의 버전 206.](./media/er-quick-start3-imported-solution2b1.png)

- **송장 모델 매핑** ER 모델 매핑 구성:

    - 버전 206.132(이상)는 **송장 모델** ER 데이터 모델 구성 버전 206의 최신 구현으로 가져왔습니다. 런타임에 데이터 모델이 애플리케이션 데이터로 채워지는 방법을 설명하는 몇 가지 모델 매핑 ER 구성 요소가 포함되어 있습니다.

    ![구성 페이지의 버전 206.132.](./media/er-quick-start3-imported-solution2b2.png)

- **UBL 매도 인보이스** ER 형식 구성:

    - 버전 32.6에는 형식 및 형식 매핑 ER 구성 요소가 포함됩니다. 형식 구성 요소는 보고서 레이아웃을 지정합니다. 형식 매핑 구성 요소는 모델 데이터 원본을 포함하고 데이터 원본이 런타임 시 보고서 레이아웃을 채우는 데 사용되는 방법을 지정합니다. 이 ER 형식은 UBL 형식의 전자 청구서를 생성하도록 구성되었습니다. 이 구성은 가져오기를 위해 선택한 **Peppol 판매 인보이스** ER 형식의 부로로 가져왔습니다.

- **Peppol 매도 인보이스** ER 형식 구성:

    - 버전 32.6.7에는 PEPPOL 형식의 전자 송장을 생성하도록 구성된 형식 및 형식 매핑 ER 구성 요소가 포함되어 있습니다.

    ![구성 페이지의 버전 32.6.7.](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>사용자 지정 ER 구성에서 표준 ER 구성의 새 버전에 대한 변경 사항을 채택합니다

### <a name="adopt-your-custom-er-data-model"></a>맞춤형 ER 데이터 모델 채택

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **청구서 모델** 을 확장하고 **청구서 모델(Litware)** 을 선택합니다.
3. **버전** 빠른 탭에서 선택한 데이터 모델 구성의 초안 버전 **50.2** 에 대해 **리베이스** 를 선택합니다.
4. **대상 버전** 필드에서 기본 ER 데이터 모델 구성의 버전 **206** 선택을 확인한 다음 **확인** 을 선택합니다.

    사용자 지정 ER 데이터 모델 구성의 초안 버전은 **50.2** 에서 **206.2** 로 변경되어 기본 ER 데이터 모델 구성의 최신 버전(206) 변경 사항과 병합된 사용자 정의가 포함되어 있음을 나타냅니다.

    > [!NOTE]
    > 리베이스 작업은 되돌릴 수 있습니다. 이 리베이스를 취소하려면 **버전** 빠른 탭에서 버전 **50.1** 의 **청구서 모델(Litware)** 모델을 선택한 다음 **이 버전 받기** 를 선택합니다. 버전 206.2의 번호가 **50.2** 로 다시 지정되고 초안 버전 50.2의 내용은 버전 50.1의 내용과 일치합니다.

5. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 206.2의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 206.3이 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 데이터 모델 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 206.2가 완료되었습니다.](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>맞춤형 ER 모델 매핑 채택

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **청구서 모델** \> **청구서 모델 매핑** 을 확장하고 **청구서 모델 매핑(Litware)** 을 선택합니다.
3. **버전** 빠른 탭에서 선택한 모델 매핑 구성의 초안 버전 **50.19.2** 에 대해 **리베이스** 를 선택합니다.
4. **대상 버전** 필드에서 기본 ER 모델 매핑 구성의 버전 **206.132** 선택을 확인한 다음 **확인** 을 선택합니다.

    사용자 지정 ER 모델 매핑 구성의 초안 버전은 **50.19.2** 에서 **206.132.2** 로 변경되어 기본 ER 모델 매핑 구성의 최신 버전(206.132) 변경 사항과 병합된 사용자 정의가 포함되어 있음을 나타냅니다.

    일부 리베이스 충돌이 발견되었습니다. 이제 이러한 충돌을 수동으로 해결해야 합니다.

    ![구성 페이지의 리베이스 충돌 메시지입니다.](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. 작업 창에서 **디자이너** 를 선택한 다음 매핑 목록에서 **고객 송장** 을 선택합니다.
6. 각 리베이스 충돌에 대해 **자체 값 유지** 를 선택합니다. 이는 언급된 모든 구성 요소에 대해 사용자 지정 데이터 모델의 버전 번호를 유지해야 하기 때문입니다.

    ![모델 매핑 디자이너 페이지에서 리베이스 충돌.](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. **저장** 을 선택한 다음 **모델 매핑 디자이너** 페이지를 닫습니다.
8. 매핑 목록에서 **프로젝트 송장** 을 선택합니다.
9. 각 리베이스 충돌에 대해 **자체 값 유지** 를 선택합니다. 이는 언급된 모든 구성 요소에 대해 사용자 지정 데이터 모델의 버전 번호를 유지해야 하기 때문입니다.
10. **저장** 을 선택한 다음 **모델 매핑** 페이지를 닫습니다.

    > [!NOTE]
    > 리베이스 작업은 되돌릴 수 있습니다. 이 리베이스를 취소하려면 **버전** 빠른 탭에서 버전 **50.19.1** 의 **청구서 모델 매핑(Litware)** 모델 매핑을 선택한 다음 **이 버전 받기** 를 선택합니다. 버전 206.132.2의 번호가 **50.19.2** 로 다시 지정되고 초안 버전 50.19.2의 내용은 버전 50.19.1의 내용과 일치합니다.

11. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 206.132.2의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 206.132.3이 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 모델 매핑 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 206.132.2가 완료되었습니다.](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>맞춤형 ER 형식 채택

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **청구서 모델** \> **UBL 판매 청구서** \> **Peppol 판매 청구서** 를 확장하고 **Peppol 판매 청구서(Litware)** 를 선택합니다.
3. **버전** 빠른 탭에서 선택한 형식 구성의 초안 버전 **11.2.2.2** 에 대해 **리베이스** 를 선택합니다.
4. **대상** 버전 필드에서 기본 ER 형식 구성의 버전 **32.6.7** 선택을 확인한 다음 **확인** 을 선택합니다.

    사용자 지정 ER 형식 구성의 초안 버전은 **11.2.2.2** 에서 **32.6.7.2** 로 변경되어 기본 ER 형식 구성의 최신 버전(32.6.7) 변경 사항과 병합된 사용자 정의가 포함되어 있음을 나타냅니다.

    일부 리베이스 충돌이 발견되었습니다. 이제 이러한 충돌을 수동으로 해결해야 합니다.

5. 작업 창에서 **디자이너** 를 선택합니다.
6. 각 리베이스 충돌에 대해 **자체 값 유지** 를 선택합니다. 이는 언급된 모든 구성 요소에 대해 사용자 지정 데이터 모델의 버전 번호를 유지해야 하기 때문입니다.
7. **저장** 을 선택합니다.
8. **매핑** 탭에서 **모델** 유형의 **송장** 데이터 원본을 선택한 다음 **편집** 을 선택합니다.
9. **버전** 필드에서 사용자 지정 데이터 모델의 버전 **2** 를 선택한 다음 **확인** 을 선택합니다.
10. **저장** 을 선택합니다.

    > [!NOTE]
    > 리베이스 작업은 되돌릴 수 있습니다. 이 리베이스를 취소하려면 **버전** 빠른 탭에서 버전 **11.2.2.1** 의 **Peppol 판매 청구서(Litware)** 형식을 선택한 다음 **이 버전 받기** 를 선택합니다. 버전 32.6.7.2의 번호가 **11.2.2.2** 로 다시 지정되고 초안 버전 11.2.2.2의 내용은 버전 11.2.2.1의 내용과 일치합니다.

11. **형식 디자이너** 페이지를 닫습니다.
12. **버전** 빠른 탭에서 **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

버전 32.6.7.2의 상태가 **초안** 에서 **완료됨** 으로 변경되며 버전이 읽기 전용이 됩니다. 새로운 편집 가능한 버전 32.6.7.3이 추가되었으며 상태는 **초안** 입니다. 이 버전을 사용하여 사용자 정의 ER 형식 구성을 추가로 변경할 수 있습니다.

![구성 페이지에서 버전 32.6.7.2가 완료되었습니다.](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>사용자 지정 ER 구성의 새 버전을 사용하여 고객 송장 추가, 게시 및 보내기

### <a name="select-and-send-a-posted-invoice"></a>게시된 인보이스 선택 및 전송

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **자유 텍스트 인보이스** 페이지에서 이전에 추가하고 게시한 송장을 선택합니다.
3. 작업 창의 **문서** 그룹에서 **보내기** \> **원본** 을 선택합니다.

    > [!NOTE] 
    > 이제 두 가지 버전의 **Peppol 판매 송장(Litware)** ER 형식 구성이 있으며 두 버전 모두 [적용 날짜](general-electronic-reporting.md#component-date-effectivity) 값이 없고, 최신 버전은 전자 인보이스를 생성하는 데 사용됩니다.

4. **자유 텍스트 인보이스** 페이지를 닫습니다.

### <a name="analyze-a-generated-e-invoice"></a>생성된 전자 인보이스 분석

1. **조직 관리** \> **전자 보고** \> **전자 보고 작업** 으로 이동합니다.
2. **전자 보고 작업** 페이지에서 작업 설명 **전자 인보이스 XML 보내기** 가 있는 최신 레코드를 선택합니다.
3. **파일 표시** 를 선택하여 생성된 파일 목록에 액세스합니다.
4. **열기** 를 선택하여 생성된 전자 인보이스 XML 파일을 다운로드합니다.
5. 전자 인보이스 XML 파일을 분석합니다. 사용자 정의에 따라 사용자 정의 세금 스키마는 **schemeID** 및 **schemeAgencyID** XML 특성 외에도 사용자 정의 **FederalTaxID** XML 특성을 게속 포함합니다. 또한 베이스의 새 버전에서 변경 사항이 있기 때문에 **UBL 매도 인보이스** 형식이 사용자 정의와 병합되었으며, **cbc:CustomizationID** XML 요소가 `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`에서 `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`로 변경되었습니다.

    ![사용자 지정으로 생성된 전자 송장 XML 파일의 미리보기입니다.](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [Lifecycle Services에서 ER 구성 다운로드](download-electronic-reporting-configuration-lcs.md)
- [구성 서비스의 글로벌 리포지토리에서 ER 구성 다운로드](er-download-configurations-global-repo.md)
- [자유 텍스트 송장 생성](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [사용자 지정 필드 만들기 및 사용](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
