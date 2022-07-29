---
title: 인쇄 가능한 FTI 양식 생성
description: 이번에는 전자 보고(ER) 프레임워크를 사용하여 인쇄 가능한 자유 텍스트 송장(FTI) 양식을 Microsoft Office 문서로 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: be5e3ef0f6ecb3d8f911b5be5f8bc9102d201fd299425e847a2df233d9b4edf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460673"
---
# <a name="generate-printable-fti-forms"></a>인쇄 가능한 FTI 양식 생성

[!include[banner](../includes/banner.md)]

전자 보고(ER) 프레임워크를 사용하면 인쇄 가능한 자유 텍스트 송장(FTI) 양식을 Microsoft Office 문서로 생성할 수 있습니다. 이번에는 사용 가능한 구성 템플릿에 대한 세부 정보와 고유한 구성을 구축하는 방법에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

Microsoft SQL Server Reporting Services(SSRS)를 사용하여 인쇄 가능한 FTI 양식을 생성하는 기존 기능 외에도 이제 ER 프레임워크를 사용할 수 있습니다. Microsoft Office Excel 및 Word에서 인쇄 가능한 FTI 양식을 관리할 수 있습니다. 또한 코드를 변경하지 않고도 특정 요구 사항을 충족하도록 레이아웃, 데이터 흐름 및 서식을 수정할 수 있습니다.

> [!NOTE]
> 인쇄 가능한 FTI 양식 솔루션의 이 샘플에 대한 기존 ER 구성의 개요로 시작하려면 이 항목 뒷부분의 **샘플 ER 구성 다운로드** 섹션으로 직접 이동하여 인쇄 가능한 FTI 양식을 생성할 수 있습니다.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>FTI 인쇄 가능한 양식에 대한 맞춤형 구성 생성
인쇄 가능한 FTI 양식에 대한 사용자 지정 솔루션의 일부로 ER 구성 세트를 생성해야 합니다.

### <a name="configure-the-er-data-model"></a>ER 데이터 모델 구성
애플리케이션에는 고객 송장 발행 비즈니스 도메인을 설명하는 데이터 모델이 포함된 ER 데이터 모델 구성이 포함되어야 합니다. 요구 사항에 따라 데이터 모델의 이름은 **CustomersInvoicing** 이어야 합니다. ER 데이터 모델을 디자인하는 방법에 대한 자세한 내용은 [ER 디자인 도메인별 데이터 모델](tasks/er-design-domain-specific-data-model-2016-11.md)을 참조하십시오.

### <a name="configure-the-er-model-mapping"></a>ER 모델 매핑 구성
애플리케이션에는 CustomersInvoicing 데이터 모델에 대한 ER 모델 매핑이 포함되어야 합니다. 모델 매핑은 ER 데이터 모델 구성 또는 ER 모델 매핑 구성에 있을 수 있습니다. 그러나 모델 매핑의 루트 설명자의 이름은 **FreeTextInvoice** 여야 합니다.

매핑에는 다음 데이터 소스가 포함되어야 합니다.

- 데이터 소스 유형: **테이블 기록**

    - 이 데이터 소스의 이름은 **CustInvoiceJour** 로 지정해야 합니다.
    - CustInvoiceJour 애플리케이션 테이블을 참조해야 합니다.
    - 런타임에 인쇄를 위해 선택된 송장 목록을 매핑하는 ER 모델로 애플리케이션에서 전달하는 데 사용됩니다.

- 데이터 소스 유형: **개체**

    - 이 데이터 소스의 이름은 **PrintMgmtPrintSettingDetail** 이어야 합니다.
    - **PrintMgmtPrintSettingDetail** 애플리케이션 클래스를 참조해야 합니다.
    - 실행 중인 ER 형식에 대한 인쇄 관리 설정의 세부 정보 매핑을 애플리케이션에서 ER 모델로 전달하기 위해 런타임에 사용됩니다.

ER 프레임워크와 애플리케이션 통합에 대한 세부 정보는 애플리케이션 소스 코드의 **ERPrintMgmtReportFormatSubscriber** 클래스(ER 애플리케이션 제품군 통합 모델)에서 찾을 수 있습니다.

ER 모델 매핑 디자인에 대한 자세한 내용은 [ER 모델 매핑 정의 및 이에 대한 데이터 원본 선택](tasks/er-define-model-mapping-select-data-sources-2016-11.md)을 참조하십시오.

### <a name="configure-the-er-format"></a>ER 형식 구성
애플리케이션 인스턴스에서 FTI 양식을 생성하는 데 사용할 ER 형식 구성이 있어야 합니다. 

> [!NOTE]
> 이 형식 구성은 CustomersInvoicing 데이터 모델에 대해 생성되어야 하며 **FreeTextInvoice** 루트 설명자가 있는 모델 매핑을 사용해야 합니다.

ER 형식을 구성하는 방법에 대한 자세한 내용은 [ER 형식 구성 만들기(2016년 11월)](tasks/er-format-configuration-2016-11.md)를 참조하십시오. OpenXML 형식으로 보고서를 생성하도록 ER 형식을 디자인하는 방법에 대한 정보는 [ER 디자인 OPENXML 형식으로 보고서를 생성하기 위한 구성(2016년 11월)](tasks/er-design-reports-openxml-2016-11.md)을 참조하십시오.

## <a name="configure-print-management"></a>인쇄 관리 구성
ER 프레임워크를 사용하여 FTI 양식을 생성하려면 SSRS 보고서를 할당하는 것과 같은 방식으로 ER 형식을 할당할 수 있습니다. ER 형식을 모든 매출채권 FTI와 연결하려면 **매출채권** \> **설정** \> **양식** \> **양식 설정** \> **일반** \> **인쇄 관리** \> **자유 텍스트 송장** \> **원본** 으로 이동합니다. ER 형식을 특정 고객 또는 송장과 연결하려면 다음 단계를 따르십시오.

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. ER 형식을 연결할 FTI를 선택하고 **인쇄 관리 설정** 페이지를 엽니다.
3. 처리할 송장의 범위를 지정하려면 문서 레벨을 선택하십시오.
4. 지정된 문서 수준에 대한 ER 형식을 선택합니다.

![인쇄 관리 설정.](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> **CustomersInvoicing** 데이터 모델의 **FreeTextInvoice** 루트 설명자를 사용하는 ER 형식만 선택한 형식에 대한 **보고서 형식 조회** 필드에 나타납니다.

## <a name="generate-fti-forms"></a>FTI 양식 생성
FTI 양식은 SSRS 보고서가 생성되는 것과 동일한 방식으로 ER 프레임워크에서 생성됩니다.

FTI 양식을 생성하려면 범위 또는 선택으로 송장을 선택할 수 있습니다. 

![송장 선택.](media/FTIbyGER-InvoiceSelection.png)

![송장 미리보기.](media/FTIbyGER-InvoiceExcelPreview.png)

ER 형식을 사용하여 이러한 방식으로 FTI 양식을 인쇄하는 경우 기본 ER 파일 대상이 사용됩니다. 대상을 변경할 수 없습니다. ER 형식에 대해 ER 대상을 구성하는 방법에 대한 자세한 내용은 [전자 보고(ER) 대상](electronic-reporting-destinations.md)을 참조하십시오.

FTI를 게시할 때 **송장 인쇄** 를 켜고 인쇄 **관리 대상 사용을 끄면 FTI 양식** 을 생성할 수도 있습니다.

> [!NOTE]
> ER 형식을 사용하여 이러한 방식으로 FTI 양식을 인쇄하는 경우 기본 ER 파일 대상이 사용됩니다. 대상이 이미 구성된 경우 런타임 시 기본 대상을 변경할 수 있습니다. 대상을 변경하려면 다음 보안 권한이 있어야 합니다.
>
> - **이름:** ERFormatDestinationRuntimeMaintain
> - **상표** 런타임 동안 전자 보고 형식 대상 유지

![전자 보고 대상.](media/FTIbyGER-ERFileDestinationSetting.png)

![전자 보고 형식 대상.](media/FTIbyGER-ERFileDestinationUsage.png)

ER 프레임워크는 현재 생성된 문서에 대해 다음 대상을 지원합니다.

- **다운로드된 파일** – 생성된 양식은 브라우저를 사용하여 저장할 수 있는 다운로드로 제공됩니다.
- **화면** – Microsoft 365 Excel은 생성된 FTI 양식을 Excel 형식으로 미리 보는 데 사용됩니다.
- **SharePoint 폴더** – 생성된 양식은 문서 관리 프레임워크의 설정에 따라 저장됩니다.
- **애플리케이션 아카이브** – 생성된 양식은 Microsoft Azure 스토리지에 실행 로그 기록의 첨부 파일로 저장됩니다.
- **이메일** – 생성된 양식은 이메일 첨부 파일로 전송됩니다.

> [!NOTE]
> Dynamics Printer Routing Agent를 사용하는 직접 인쇄는 현재 지원되지 않으므로 생성된 FTI 양식을 프린터로 직접 보낼 수 없습니다.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>샘플 ER 구성을 다운로드하여 인쇄 가능한 FTI 양식 생성
FTI 솔루션의 템플릿으로 사용할 샘플 ER 구성을 다운로드할 수 있습니다. 구성은 Microsoft Dynamics LCS(Lifecycle Services)의 공유 자산 라이브러리에 저장됩니다. 구성에는 다음이 포함됩니다.

- **고객 송장 발행 모델** 구성에는 필수 데이터 모델 및 모델 매핑이 포함됩니다.
- **고객 FTI 보고서(GER)** 구성에는 샘플 형식이 포함되어 있습니다.

> [!NOTE]
> 이러한 구성은 가능한 시나리오를 명확히 하는 데 도움이 되는 샘플로 만들어졌습니다. 이러한 구성의 미래는 이 평가의 결과와 받은 피드백에 따라 다릅니다.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>샘플 ER 형식으로 구현된 기능
샘플 ER 형식 구성에서 Excel 파일은 FTI 양식을 생성하기 위한 템플릿으로 사용됩니다.

![포맷 디자이너.](media/FTIbyGER-ERFormat.png)

현재 이 샘플 ER 형식은 FTI 형식을 생성하기 위해 다음 기능을 지원합니다.

- FTI 양식은 전기된 원본 송장과 아직 전기되지 않은 원본 송장 모두에 대해 생성됩니다. 수정된 송장 및 신용 메모는 지원되지 않습니다.
- FTI 양식은 송장 언어로 생성됩니다. 생성된 양식의 값 및 날짜 형식은 사용자의 클라이언트 로캘 설정을 기반으로 합니다.
- 생성된 송장은 처리된 송장에 라인이 없는 경우 데이터 비가용성 알림을 표시합니다.
- 생성된 송장 헤더는 **미수금 매개 변수** 페이지에서 FTI 양식에 대해 선택한 종이 형식을 기반으로 합니다. 회사 세부 정보는 종이 형식이 비어 있는 경우에만 생성된 송장 양식의 헤더에 나타납니다.
- **미수금 매개 변수** 페이지에서 FTI 양식에 대해 적절한 옵션을 선택한 경우 생성된 송장 양식에 회사 및 고객 면세 번호가 표시됩니다.
- 생성된 송장 라인 및 송장 합계 섹션에는 송장 등록 통화로 기본 송장의 통화 세부 정보가 표시됩니다.
- **미수금 매개 변** 수 페이지에서 유로를 나타내는 통화로 **금액 인쇄 옵션** 이 활성화된 경우 생성된 송장 합계 섹션에 유로 통화 및 송장 등록 통화로 화폐 세부정보가 표시될 수 있습니다.
- 생성된 송장 양식에는 **미수금 매개 변수** 페이지의 설정에 따라 사용 가능한 모든 프로세스 송장 메모가 표시됩니다. 전체 송장과 각 송장 라인 모두에 대한 메모가 포함됩니다.
- 생성된 송장 양식에는 AR 양식 메모 목록에서 구성된 경우 고객 FTI 양식 및 처리 송장 언어에 대한 메모가 포함됩니다.
- 인쇄 관리 설정에 따라 생성된 송장은 송장 언어, ER 형식 및 FTI 문서 범위에 대해 구성된 경우 사용자 지정 바닥글 텍스트를 포함합니다.
- 생성된 송장 양식의 합계 섹션에는 사용 가능한 모든 현금 할인 정보가 포함됩니다.
- 생성된 송장 양식의 지급 일정 섹션에는 사용 가능한 지급 일정 세부 정보가 포함됩니다.
- 생성된 송장 양식의 마크업 섹션에는 사용 가능한 모든 요금 거래가 포함됩니다.
- 생성된 송장 양식에는 **미수금 매개 변수** 페이지의 판매세 사양 설정에 따라 **판매세 세부 정보** 가 포함됩니다. 이 섹션은 세금 세부 정보를 송장 등록 통화로만 표시하거나 송장 등록 통화와 회사 회계 통화로 동시에 표시할 수 있습니다.
- 생성된 송장 양식에는 자동이체 알림 세부정보가 표시됩니다. 예를 들어 송장에 대해 필수 자동이체 위임 ID가 있는 결제 방법이 선택된 경우, 처리 송장이 유로 통화로 등록된 경우, 자동이체 위임 ID가 송장에 대해 정의된 경우를 표시합니다.
- 생성된 송장에는 전기된 송장에 사용할 수 있는 선급금 세부정보가 표시됩니다.
- 생성된 송장 양식은 이메일 첨부 파일로 송장 고객에게 보낼 수 있습니다. 사용 중인 ER 형식에 대해 적절한 ER 파일 대상을 구성해야 합니다.

### <a name="countryregion-specific-features"></a>국가/지역별 기능 
다음 국가/지역별 기능은 샘플 ER 형식에 포함되어 ER 구성에서 특정 요구 사항을 처리할 수 있는 방법을 보여줍니다.

#### <a name="norway"></a>노르웨이
기업 등록 기간은 다음 방식으로 구성된 법인에 대해 송장이 처리될 때 생성된 송장 양식의 헤더에 표시됩니다.

- 노르웨이의 국가/지역 컨텍스트가 사용됩니다.
- Print **Foretaksregisteret** 매개 변수는 판매 문서에서 활성화됩니다.

#### <a name="spain"></a>스페인
**현금 회계 방법 기간에 대한 특별 제도** 는 다음 방식으로 구성된 법인에 대해 송장이 처리될 때 생성된 송장 양식의 헤더에 추가됩니다.

- 스페인의 국가/지역 컨텍스트가 사용됩니다.
- 현금 회계 방법에 대한 특별 제도는 송장 처리 일자에 활성화됩니다.

현금 할인 금액 및 송장 라인 순 금액과 같은 현금 할인 세부 정보를 사용할 수 있는 경우 다음 방식으로 구성된 법인에 대해 처리될 때 생성된 송장 양식의 송장 합계 섹션에 표시됩니다.

- 스페인의 국가/지역 컨텍스트가 사용됩니다.
- 송장 옵션(**총계정원장 매개 변수** \> **판매세 섹션**)에서 **송장에 현금 할인이 적용** 됩니다.

#### <a name="italy"></a>이탈리아
상품 할인 표시는 이탈리아의 국가/지역 컨텍스트를 사용하여 구성된 법인에 대해 처리될 때 생성된 송장의 송장 라인에 포함됩니다.

#### <a name="finland"></a>핀란드
생성된 송장 양식 외에도 다음과 같이 Giro 송금 전표를 생성할 수 있습니다.

- 핀란드의 국가/지역 컨텍스트를 사용하고 **Giro 계정** 및 **은행 바코드** 로 표시된 은행 계좌가 하나 이상 있는 법인의 경우. 
- **핀란드** 관련 지급 첨부 파일에 대해 필수로 표시된 송장의 경우.

![지로 슬립.](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> 샘플 ER 형식은 별도의 워크시트에서 선택적으로 Giro 송금 전표를 생성하도록 구성되었습니다.

> [!NOTE]
> Excel 형식으로 생성된 송장 양식을 미리 볼 로컬 컴퓨터에 바코드를 생성하는 데 사용되는 글꼴을 먼저 설치해야 합니다.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>샘플 ER 형식을 사용하여 이메일 대상 구성
샘플 ER 형식의 다음 요소를 사용하여 이메일 대상을 구성합니다.

- 고객 연락처의 이메일 주소는 **model.InvoiceBase.Contact.ElectronicMail** ER 표현식을 통해 액세스할 수 있습니다.
- 이메일 제목 텍스트는 다음 ER 표현식을 통해 액세스할 수 있습니다. **Emailing.TxtToUse.Subject**.
- 이메일 본문 텍스트는 다음 ER 표현식을 통해 액세스할 수 있습니다. **Emailing.TxtToUse.Body**.

![대상 설정.](media/FTIbyGER-ERFileDestinationSettingEmail.png)

이메일 제목과 본문의 기본 텍스트는 샘플 ER 형식으로 정의됩니다. 언어는 형식의 레이블에 따라 다릅니다. 이 기본 텍스트는 사전 정의된 **ERFTITMP** ID가 있는 사용자 지정 조직 이메일 템플릿이 추가되지 않은 경우 이메일에 사용됩니다.

> [!NOTE]
> **ERFTITMP** 이메일 템플릿 ID는 샘플 ER 형식으로 정의되었습니다. 이 샘플 형식에서 생성된 새 ER 형식에서 필요에 따라 변경할 수 있습니다.

사전 정의된 **ERFTITMP** ID가 있는 조직 이메일 템플릿이 송장을 처리하는 법인에 추가된 경우 이메일 제목 및 본문 텍스트에 대한 템플릿이 이메일을 생성하는 데 사용됩니다. 

![조직 이메일 템플릿.](media/FTIbyGER-EmailTemplate.png)

![이메일 템플릿을 업로드합니다.](media/FTIbyGER-EmailTemplateBody.png)

샘플 ER 형식의 **Emailing.TxtToUse.Subject** ER 표현식은 모든 %1 자리 표시자를 처리 송장 ID로 바꾸도록 구성됩니다.

샘플 형식의 **Emailing.TxtToUse.Body** 식은 다음과 같은 자리 표시자를 대체하도록 구성됩니다.

- %1는 고객의 담당자 이름으로 대체됩니다.
- %2 회사 이름으로 대체됩니다.
- %3 고객 이름으로 대체됩니다.
- %4 회사 담당자의 이름으로 대체됩니다.
- %5 는 회사 담당자의 직함으로 대체됩니다.
- %6 회사 담당자의 이메일 주소로 대체됩니다.

![이메일:](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>추가 리소스
[전자 보고(ER) 개요](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]