---
title: 전자 보고(ER) 대상
description: 이번에는 전자 보고 대상 관리, 지원되는 대상 유형 및 보안 고려 사항에 대한 정보를 제공합니다.
author: nselin
ms.date: 09/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e8e176b8d4e14eee2050b3c66f7547ff878b5174
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "8460761"
---
# <a name="electronic-reporting-er-destinations"></a>전자 보고(ER) 대상

[!include [banner](../includes/banner.md)]

각 전자 보고(ER) 형식 구성 및 해당 출력 구성 요소(폴더 또는 파일)에 대한 대상을 구성할 수 있습니다. 적절한 액세스 권한이 있는 사용자는 런타임 시 대상 설정을 수정할 수도 있습니다. 이번에는 ER 대상 관리, 지원되는 대상 유형 및 보안 고려 사항에 대해 설명합니다.

ER 형식 구성에는 일반적으로 최소한 하나의 출력 구성 요소인 파일이 포함됩니다. 일반적으로 구성에는 단일 폴더 또는 여러 폴더로 그룹화되는 다양한 유형(예: XML, TXT, XLSX, DOCX 또는 PDF)의 여러 파일 출력 구성 요소가 포함됩니다. ER 대상 관리를 통해 각 구성 요소가 실행될 때 발생하는 작업을 미리 구성할 수 있습니다. 기본적으로 구성이 실행되면 파일을 저장하거나 열 수 있는 대화 상자가 나타납니다. ER 구성을 가져오고 특정 대상을 구성하지 않은 경우에도 동일한 동작이 발생합니다. 기본 출력 구성 요소에 대한 대상이 생성된 후 해당 대상은 기본 동작을 재정의하고 대상 설정에 따라 폴더 또는 파일이 전송됩니다.

## <a name="availability-and-general-prerequisites"></a>가용성 및 일반 전제 조건

ER 대상에 대한 함수은 Microsoft Dynamics AX 7.0(2016년 2월)에서 사용할 수 없습니다. 따라서 다음 대상 유형을 사용하려면 Microsoft Dynamics 365 for Operations 버전 1611(2016년 11월) 이상을 설치해야 합니다.

- [이메일](er-destination-type-email.md)
- [보관](er-destination-type-archive.md)
- [파일](er-destination-type-file.md)
- [선별 검사](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

또는 다음 필수 구성 요소 중 하나를 설치할 수 있습니다. 그러나 이러한 대안은 보다 제한된 ER 대상 경험을 제공합니다.

- Microsoft Dynamics AX 애플리케이션 버전 7.0.1(2016년 5월)
- [전자 보고 대상 관리 애플리케이션 핫픽스](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

[인쇄](er-destination-type-print.md) 대상 유형도 있습니다. 사용하려면 Microsoft Dynamics 365 Finance 버전 10.0.9(2020년 4월)를 설치해야 합니다.

## <a name="overview"></a>개요

현재 Finance 인스턴스로 [가져온](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) ER 구성과 **전자 보고 구성** 페이지에서 사용 가능한 형식에 대해서만 대상을 설정할 수 있습니다. ER 대상 관리 함수은 **조직 관리** \> **전자 보고** \> **전자 보고 대상** 에서 사용할 수 있습니다.

### <a name="default-behavior"></a>기본 동작

ER 형식 구성의 기본 동작은 ER 형식이 시작될 때 지정하는 실행 유형에 따라 다릅니다.

**Intrastat 보고서** 대화 상자의 **백그라운드 FastTab에서 실행** 에서 **일괄 처리** 옵션을 **아니요** 로 설정하면 ER 형식이 대화식 모드에서 즉시 실행됩니다. 이 실행이 성공적으로 완료되면 생성된 아웃바운드 문서를 다운로드할 수 있습니다.

**일괄 처리** 옵션을 **예** 로 설정하면 ER 형식이 [일괄 처리](../sysadmin/batch-processing-overview.md) 모드에서 실행됩니다. **ER 매개 변수** 대화 상자의 **백그라운드에서 실행** 탭에서 지정한 매개 변수를 기반으로 적절한 배치 작업이 생성됩니다.

> [!NOTE]
> 작업 설명은 ER 형식 매핑 실행에 대해 알려줍니다. 또한 실행되는 ER 구성 요소의 이름도 포함합니다.

[![ER 형식을 실행합니다.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

이 직업에 대한 정보는 여러 곳에서 찾을 수 있습니다.

- **일반** \> **문의** \> **일괄작업** \> **내 일괄작업** 으로 이동하여 예약된 작업의 상태를 확인하십시오.
- **조직 관리** \> **전자 보고** \> **전자 보고 작업** 으로 이동하여 예약된 작업의 상태와 완료된 작업의 실행 결과를 확인합니다. 작업 실행이 성공적으로 완료되면 **전자 보고 작업** 페이지에서 **파일 표시** 를 선택하여 생성된 아웃바운드 문서를 가져옵니다.

    > [!NOTE]
    > 이 문서는 현재 작업 기록의 첨부 파일로 저장되며 [문서 관리](../../fin-ops/organization-administration/configure-document-management.md) 프레임워크에 의해 제어됩니다. 이 유형의 ER 아티팩트를 저장하는 데 사용되는 [문서 유형](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)은 [ER 매개 변수](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)에서 구성됩니다.

- **전자 보고 작업** 페이지에서 **파일 표시** 를 선택하여 작업 실행 중에 생성된 오류 및 경고 목록을 봅니다.

    [![응급실 작업 목록을 검토합니다.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>사용자 구성 동작

**전자 보고 대상** 페이지에서 구성에 대한 기본 동작을 재정의할 수 있습니다. 가져온 구성은 **새로 만들기** 를 선택한 다음 **참조** 필드에서 대상 설정을 생성할 구성을 선택할 때까지 이 페이지에 표시되지 않습니다.

[![참조 필드에서 구성 선택.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

참조를 생성한 후 참조된 ER 형식의 각 **폴더** 또는 **파일** 출력 구성 요소에 대한 파일 대상을 생성할 수 있습니다.

[![파일 대상을 만드는 중입니다.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

이후 **대상 설정** 대화 상자에서 파일 대상에 대한 개별 대상을 활성화 및 비활성화할 수 있습니다. **설정** 버튼은 선택한 파일 대상의 모든 대상을 제어하는 데 사용됩니다. **대상 설정** 대화 상자에서 **사용** 옵션을 설정하여 각 대상을 개별적으로 제어할 수 있습니다.

**버전 10.0.9 이전** 의 Finance 버전에서는 **파일 이름** 필드에서 선택한 폴더 또는 파일과 같이 동일한 형식의 각 출력 구성 요소에 대해 **하나의 파일 대상** 을 생성할 수 있습니다. **그러나 버전 10.0.9 이상** 에서는 동일한 형식의 각 출력 구성 요소에 대해 **여러 파일 대상** 을 만들 수 있습니다.

예를 들어, 이 기능을 사용하여 Excel 형식의 아웃바운드 문서를 생성하는 데 사용되는 파일 구성 요소의 파일 대상을 구성할 수 있습니다. 하나의 대상([아카이브](er-destination-type-archive.md))은 원본 Excel 파일을 ER 작업 아카이브에 저장하도록 구성할 수 있고, 다른 대상([이메일](er-destination-type-email.md))은 Excel 파일을 PDF 형식으로 동시에 [변환하고](#OutputConversionToPDF) PDF 파일을 이메일로 보내도록 구성할 수 있습니다.

[![단일 형식 요소에 대해 여러 대상 구성.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

ER 형식을 실행하면 해당 형식의 구성 요소에 대해 구성된 모든 대상이 항상 실행됩니다. 또한 Finance **버전 10.0.17 이상** 에서는 ER 대상 함수가 향상되어 이제 단일 ER 형식에 대해 다양한 대상 세트를 구성할 수 있습니다. 이 구성은 각 세트를 특정 사용자 작업에 대해 구성된 것으로 표시합니다. ER API를 [확장하여](er-apis-app10-0-17.md) 사용자가 ER 형식을 실행하여 수행하는 작업을 제공할 수 있습니다. 제공된 작업 코드는 ER 대상으로 전달됩니다. 제공된 작업 코드에 따라 ER 형식의 다른 대상을 실행할 수 있습니다. 자세한 내용은 [작업 종속 ER 대상 구성](er-action-dependent-destinations.md)을 참조하십시오.

## <a name="destination-types"></a>대상 유형

다음 대상은 현재 ER 형식에 대해 지원됩니다. 모든 유형을 동시에 비활성화하거나 활성화할 수 있습니다. 이런 식으로 아무것도 하지 않거나 구성 요소를 구성된 모든 대상으로 보낼 수 있습니다.

- [이메일](er-destination-type-email.md)
- [보관](er-destination-type-archive.md)
- [파일](er-destination-type-file.md)
- [선별 검사](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [인쇄](er-destination-type-print.md)

## <a name="applicability"></a>적용 가능성

가져온 ER 구성 및 **전자 보고 구성** 페이지에서 사용할 수 있는 형식에 대해서만 대상을 설정할 수 있습니다.

> [!NOTE]
> 구성된 대상은 회사에 따라 다릅니다. 현재 Finance 인스턴스의 다른 회사에서 ER 형식을 사용하려는 경우 해당 회사 각각에 대해 해당 ER 형식의 대상을 구성해야 합니다.

선택한 형식에 대해 파일 대상을 구성할 때 전체 형식에 대해 구성합니다.

[![구성 링크.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

동시에 현재 Finance 인스턴스로 가져온 형식의 여러 [버전](general-electronic-reporting.md#component-versioning)이 있을 수 있습니다. **참조** 필드를 선택할 때 제공되는 **구성** 링크를 선택하면 볼 수 있습니다.

[![구성 버전.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

기본적으로 구성된 대상은 상태가 **완료됨** 또는 **공유됨** 인 ER 형식 버전을 실행할 때만 적용됩니다. 그러나 ER 형식의 초안 버전을 실행할 때 구성된 대상을 사용해야 하는 경우가 있습니다. 예를 들어 형식의 초안 버전을 수정하고 구성된 대상을 사용하여 생성된 출력이 전달되는 방식을 테스트하려고 합니다. 초안 버전이 실행될 때 ER 형식에 대한 대상을 적용하려면 다음 단계를 따르십시오.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **초안 상태에 대상 사용** 옵션을 **예** 로 설정합니다.

[![초안 상태 옵션에 대상을 사용합니다.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

ER 형식의 초안 버전을 사용하려면 그에 따라 ER 형식을 표시해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **실행 설정** 옵션을 **예** 로 설정합니다.

[![설정 옵션을 실행합니다.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

이 설정을 완료하면 수정하는 ER 형식에 대해 **초안 실행** 옵션을 사용할 수 있습니다. 형식이 실행될 때 형식의 초안 버전을 사용하려면 이 옵션을 **예** 로 설정합니다.

[![초안 옵션을 실행합니다.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>대상 장애 처리

일반적으로 ER 형식은 특정 비즈니스 프로세스의 범위 내에서 실행됩니다. 그러나 ER 형식을 실행하는 동안 생성된 아웃바운드 문서의 전달은 때때로 해당 비즈니스 프로세스의 일부로 간주되어야 합니다. 이 경우 생성된 아웃바운드 문서를 구성된 대상로 전달하는 데 실패하면 비즈니스 프로세스의 실행을 취소해야 합니다. 적절한 ER 대상을 구성하려면 **오류 시 처리 중지** 옵션을 선택합니다.

예를 들어, **ISO20022 신용 전송** ER 형식이 실행되어 지급 파일과 추가 문서(예: 커버 레터 및 통제 보고서)를 생성하도록 공급 업체 지급 처리를 구성합니다. 커버 레터가 이메일로 성공적으로 전달된 경우에만 결제가 성공적으로 처리된 것으로 간주되어야 하는 경우 다음 그림과 같이 해당 파일 대상의 **CoveringLetter** 구성 요소에 대해 **실패 시 처리 중지** 확인란을 선택해야 합니다. 이 경우, 처리를 위해 선택된 지급 상태는 생성된 커버 레터가 Finance 인스턴스에서 구성된 이메일 제공업체에 의해 전달을 위해 성공적으로 수락된 경우에만 **없음** 에서 **발송됨** 으로 변경됩니다.

[![파일 대상 실패에 대한 프로세스 처리 구성.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

대상의 **CoveringLetter** 구성 요소에 대해 **실패 시 처리 중지** 확인란을 선택 취소하면 전자 메일로 Covering Letter가 성공적으로 전달되지 않아도 결제가 성공적으로 처리된 것으로 간주됩니다. 수신인 또는 발신인의 이메일 주소가 누락되거나 정확하지 않은 등의 이유로 커버레터를 발송할 수 없는 경우에도 지급 상태가 **없음** 에서 **발송됨** 으로 변경됩니다.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>PDF로 출력 변환

PDF 변환 옵션을 사용하여 Microsoft Office(Excel 또는 Word) 형식의 출력을 PDF 형식으로 변환할 수 있습니다.

### <a name="make-pdf-conversion-available"></a>PDF 변환 가능

현재 Finance 인스턴스에서 PDF 변환 옵션을 사용할 수 있도록 하려면 **기능 관리** 작업 공간을 열고 **전자 보고 아웃바운드 문서를 Microsoft Office 형식에서 PDF로 변환** 기능을 켭니다.

[![기능 관리에서 아웃바운드 문서의 PDF 변환 기능을 켭니다.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>적용 가능성

**버전 10.0.18 이전** 의 Finance 버전에서 PDF 변환 옵션은 Office(Excel 또는 Word) 형식으로 출력을 생성하는 데 사용되는 **Excel\\File** 구성 요소에 대해서만 켤 수 있습니다. 이 옵션을 켜면 Office 형식으로 생성된 출력이 자동으로 PDF 형식으로 변환됩니다. 그러나 **버전 10.0.18 이상** 에서는 **Common\\File** 유형의 구성 요소에 대해 이 옵션을 켤 수도 있습니다.

> [!NOTE]
> **Common\\File** 유형의 ER 구성 요소에 대해 PDF 변환 옵션을 켤 때 수신되는 경고 메시지에 주의하십시오. 이 메시지는 디자인 타임에 선택한 파일 구성 요소가 런타임 시 PDF 형식의 콘텐츠 또는 PDF 변환 가능한 콘텐츠를 노출할 것임을 보장할 수 있는 방법이 없음을 알려줍니다. 따라서 선택한 파일 구성 요소가 런타임 시 PDF 형식의 콘텐츠 또는 PDF 변환 가능한 콘텐츠를 노출하도록 구성되어 있는 경우에만 옵션을 켜야 합니다.
> 
> 형식 구성 요소에 대해 PDF 변환 옵션을 켜고 해당 구성 요소가 PDF 이외의 형식으로 콘텐츠를 노출하고 노출된 콘텐츠를 PDF 형식으로 변환할 수 없는 경우 런타임에 예외가 발생합니다. 생성된 콘텐츠를 PDF 형식으로 변환할 수 없다는 메시지가 표시됩니다.

### <a name="limitations"></a>한계

PDF 변환 옵션은 클라우드 배포에만 사용할 수 있습니다.

생성되는 PDF 문서는 최대 300페이지로 제한됩니다.

Finance **버전 10.0.9** 에서는 Excel 출력에서 생성된 PDF 문서에서 가로 페이지 방향만 지원됩니다. Finance **버전 10.0.10(2020년 5월) 이상** 에서는 ER 대상을 구성하는 동안 Excel 출력에서 생성된 PDF [문서의 페이지 방향을 지정](#SelectPdfPageOrientation)할 수 있습니다.

Windows 운영 체제의 공통 시스템 글꼴만 포함된 글꼴이 포함되지 않은 출력을 변환하는 데 사용됩니다.

### <a name="use-the-pdf-conversion-option"></a>PDF 변환 옵션 사용

파일 대상에 대한 PDF 변환을 켜려면 **PDF로 변환** 확인란을 선택합니다.

[![파일 대상에 대해 PDF 변환을 켭니다.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">PDF 변환을 위한 페이지 방향 선택</a>

Excel 형식으로 ER 구성을 생성하고 이를 PDF 형식으로 변환하려는 경우 PDF 문서의 페이지 방향을 명시적으로 지정할 수 있습니다. Excel 형식으로 출력 파일을 생성하는 파일 대상에 대해 **PDF 변환** 을 켜기 위해 PDF로 변환 확인란을 선택하면 **PDF 변환 설정** FastTab에서 **페이지 방향** 필드를 사용할 수 있습니다. **페이지 방향** 필드에서 기본 방향을 선택합니다.

[![PDF 변환을 위한 페이지 방향 선택.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

PDF 페이지 방향을 선택하는 옵션을 사용하려면 Finance 버전 10.0.10 이상을 설치하십시오. **버전 10.0.23 이전** 의 Finance 버전에서 이 옵션은 다음 페이지 방향 옵션을 제공합니다.

- 초상화
- 풍경

선택한 페이지 방향은 Excel 형식으로 생성된 다음 PDF 형식으로 변환된 아웃바운드 문서의 모든 페이지에 적용됩니다.

그러나 **버전 10.0.23 이상** 에서는 페이지 방향 옵션 목록이 다음과 같이 확장되었습니다.

- 초상화
- 풍경
- 워크시트 특정

**워크시트 특정** 옵션을 선택하면 생성된 Excel 통합 문서의 모든 워크시트가 사용된 Excel 템플릿에서 이 워크시트에 대해 구성된 페이지 방향을 사용하여 PDF로 변환됩니다. 따라서 세로 및 가로 페이지가 포함된 최종 PDF 문서가 있을 수 있습니다. 

Word 형식의 ER 구성이 PDF 형식으로 변환되면 PDF 문서의 페이지 방향은 항상 Word 문서에서 가져옵니다.

## <a name="output-unfolding"></a>출력 전개

ER 형식의 **폴더** 구성 요소에 대한 대상을 구성할 때 해당 구성 요소의 출력이 구성된 대상에 전달되는 방법을 지정할 수 있습니다.

### <a name="make-output-unfolding-available"></a>출력 전개를 사용할 수 있도록 설정

현재 Finance 인스턴스에서 출력 전개 옵션을 사용할 수 있도록 하려면 **기능 관리** 작업 공간을 열고 **ER 대상을 구성하여 폴더 콘텐츠를 별도의 파일로 보내도록 허용** 기능을 켭니다.

### <a name="applicability"></a>적용 가능성

출력 펼치기 옵션은 **폴더** 유형의 형식 구성 요소에 대해서만 구성할 수 있습니다. **폴더** 구성 요소 구성을 시작하면 **전자 보고 대상** 페이지에서 **일반** FastTab을 사용할 수 있습니다. 

### <a name="use-the-output-unfolding-option"></a>출력 펼치기 옵션 사용

**일반** FastTab의 **폴더 보내기** 필드에서 다음 값 중 하나를 선택합니다.

- **ZIP 아카이브** – 생성된 파일을 zip 파일로 제공합니다.
- **개별 파일** – 생성된 zip 파일의 모든 파일을 개별 파일로 제공합니다.

    > [!NOTE]
    > **파일 분리** 를 선택하면 생성된 출력이 압축된 상태로 메모리에 수집됩니다. 따라서 실제 파일 크기가 이 제한을 초과할 수 있는 경우 압축된 출력에 최대 [파일 크기 제한](er-compress-outbound-files.md)이 적용됩니다. 생성된 출력의 크기가 너무 클 것으로 예상되는 경우 이 값을 선택하는 것이 좋습니다.

[![폴더 형식 구성 요소의 대상 구성.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>한계

다른 **중첩된 폴더** 구성 요소를 포함하는 **폴더** 구성 요소에 대해 **다른 이름으로 폴더 보내기** 필드를 **별도의 파일** 로 설정하면 설정이 중첩된 **폴더** 구성 요소에 반복적으로 적용되지 않습니다.

## <a name="security-considerations"></a>보안 고려 사항

ER 대상에는 두 가지 유형의 권한과 의무가 사용됩니다. 한 가지 유형은 법인에 대해 구성된 대상을 유지 관리하는 사용자의 전반적인 능력을 제어합니다(즉, **전자 보고 대상** 페이지에 대한 액세스를 제어함). 다른 유형은 런타임 시 ER 개발자 또는 ER 함수 컨설턴트가 구성한 대상 설정을 재정의하는 애플리케이션 사용자의 함수를 제어합니다.

| 역할(AOT 이름)                     | 역할 이름                                  | 의무(AOT 이름)                     | 직무 이름                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ER개발자                         | 전자 보고 개발자             | ERFormatDestinationConfigure        | 전자 보고 형식 대상 구성                |
| ER함수 컨설턴트              | 전자 보고 기능 컨설턴트 | ERFormatDestinationConfigure        | 전자 보고 형식 대상 구성                |
| PaymAccountsPayablePaymentsClerk    | 미지급금 사무원            | ERFormatDestinationRuntimeConfigure | 런타임 중 전자 보고 형식 대상 구성 |
| PaymAccountsReceivablePaymentsClerk | 미수금 지급 사무원         | ERFormatDestinationRuntimeConfigure | 런타임 중 전자 보고 형식 대상 구성 |

> [!NOTE]
> 앞의 임무에서 두 가지 권한이 사용됩니다. 이러한 권한은 해당 의무와 이름이 같습니다. **ERFormatDestinationConfigure** 및 **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>전자 구성을 가져왔고 전자 보고 구성 페이지에서 볼 수 있습니다. 하지만 전자 보고 대상 페이지에 표시되지 않는 이유는 무엇입니까?

**새로 만들기** 를 선택한 다음 **참조** 필드에서 구성을 선택했는지 확인합니다. **전자 보고 대상 페이지** 에는 대상이 구성된 구성만 표시됩니다.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>사용되는 Microsoft Azure Storage 계정 및 Azure Blob Storage를 정의하는 방법이 있습니까?

번호에서 값을 선택합니다. 문서 관리 시스템에 대해 정의되고 사용되는 기본 Microsoft Azure Blob 저장소가 사용됩니다.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>대상 설정에서 파일 대상의 목적은 무엇입니까? 그 설정은 무엇을 합니까?

**파일** 대상은 대화형 모드에서 ER 형식을 실행할 때 웹 브라우저의 대화 상자를 제어하는 데 사용됩니다. 이 대상을 활성화하거나 구성에 대해 대상이 정의되지 않은 경우 출력 파일이 생성된 후 웹 브라우저에 열기 또는 저장 대화 상자가 나타납니다.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>이메일을 보낼 수 있는 공급 업체 계정을 나타내는 공식의 예를 들어 주시겠습니까?

공식은 ER 구성에 따라 다릅니다. 예를 들어 ISO 20022 신용 전송 구성을 사용하는 경우 **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** 또는 **model.Payments.Creditor.Identification.SourceID** 를 사용하여 연결된 공급 업체 계정을 가져올 수 있습니다.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>내 형식 구성 중 하나에는 하나의 폴더로 그룹화된 여러 파일이 포함되어 있습니다(예: Folder1에는 File1, File2 및 File3이 포함됨). Folder1.zip이 전혀 생성되지 않고 File1이 이메일로 전송되고 File2가 SharePoint로 전송되고 구성이 실행된 직후 File3을 열 수 있도록 대상을 설정하려면 어떻게 해야 합니까?

형식은 먼저 ER 구성에서 사용할 수 있어야 합니다. 이 전제조건이 충족되면 **전자 보고 대상** 페이지를 열고 구성에 대한 새 참조를 작성하십시오. 이후 각 출력 구성 요소에 대해 하나씩 네 개의 파일 대상이 있어야 합니다. 첫 번째 파일 대상을 만들고 **폴더** 와 같은 이름을 지정한 다음 구성에서 폴더를 나타내는 파일 이름을 선택합니다. 이후 **설정** 을 선택하고 모든 대상이 비활성화되어 있는지 확인합니다. 이 파일 대상의 경우 폴더가 생성되지 않습니다. 기본적으로 파일과 상위 폴더 간의 계층적 종속성으로 인해 파일은 동일한 방식으로 작동합니다. 즉, 아무데도 보내지 않습니다. 해당 기본 동작을 재정의하려면 각 파일에 대해 하나씩 세 개의 파일 대상을 더 만들어야 합니다. 각각에 대한 대상 설정에서 파일을 보내야 하는 대상을 활성화해야 합니다.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[작업 종속 ER 대상 구성](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
