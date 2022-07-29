---
title: 프린터 ER 대상 유형
description: 이번에는 전자 보고(ER) 형식의 각 FOLDER 또는 FILE 구성 요소에 대해 프린터 대상을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8460951"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>프린터 대상

[!include [banner](../includes/banner.md)]

생성된 문서를 직접 네트워크 프린터로 보내 직접 인쇄할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

시작하기 전에 Document Routing Agent를 설치 및 구성한 다음 네트워크 프린터를 등록해야 합니다. 자세한 내용은 [네트워크 인쇄를 활성화하기 위해 Document Routing Agent 설치](./install-document-routing-agent.md)를 참조하십시오.

## <a name="make-the-printer-destination-available"></a>프린터 대상을 사용할 수 있도록 설정

현재 Microsoft Dynamics 365 Finance 인스턴스에서 **프린터** 대상을 사용할 수 있도록 하려면 **기능 관리** 작업 공간으로 이동하여 다음 기능을 순서대로 켭니다.

1. 전자 보고 아웃바운드 문서를 Microsoft Office 형식에서 PDF로 변환
2. 아웃바운드 문서의 전자 보고 대상인 Document Routing Agent

[![기능 관리에서 ER 프린터 대상 기능을 켭니다.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>적용 가능성

#### <a name="pdf-printing"></a>PDF 인쇄

버전 10.0.18 이전의 Finance 버전에서는 인쇄 가능한 PDF 형식(**PDF Merger** 또는 **PDF 파일** 형식 요소) Microsoft Office Excel 또는 Word 형식(**Excel 파일** 형식 요소)으로 출력을 생성하는 데 사용되는 파일 구성 요소에 대해서만 **프린터** 대상을 구성할 수 있습니다. 출력이 PDF 형식으로 생성되면 프린터로 전송됩니다. **Excel 파일** 형식 요소를 사용하여 Office 형식으로 출력을 생성하면 자동으로 PDF 형식으로 변환되어 프린터로 전송됩니다.

그러나 버전 10.0.18부터 **공통 파일** 형식 요소에 대한 **프린터** 대상을 구성할 수 있습니다. 이 형식 요소는 주로 TXT 또는 XML 형식으로 출력을 생성하는 데 사용됩니다. **공통 파일** 형식 요소를 루트 형식 요소로 포함하고 **이진 콘텐츠** 형식 요소를 그 아래에 있는 유일한 중첩 요소로 포함하는 ER 형식을 구성할 수 있습니다. 이 경우 **공통 파일** 형식 요소는 **이진 콘텐츠** 형식 요소에 대해 구성한 바인딩에서 지정한 형식으로 출력을 생성합니다. 예를 들어, PDF 또는 Office(Excel 또는 Word) 형식의 [문서 관리](../../fin-ops/organization-administration/configure-document-management.md) 첨부 파일 내용으로 이 요소를 [채우도록](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) 이 바인딩을 구성할 수 있습니다. 구성된 **프린터** 대상을 사용하여 출력을 인쇄할 수 있습니다. 

> [!NOTE]
> **Common\\File** 형식 요소를 선택하여 **프린터** 대상을 구성하면 디자인 타임에 선택한 요소가 PDF 형식으로 출력을 생성하거나 PDF 형식으로 변환할 수 있는 출력을 생성한다는 보장이 없습니다. 따라서 다음과 같은 경고 메시지가 나타납니다. 선택한 형식 구성 요소에 의해 생성된 출력을 PDF로 변환할 수 있는지 확인하십시오. 그렇지 않으면 로 변환' 옵션의 선택을 취소하십시오.  런타임 시 인쇄를 위해 PDF가 아닌 또는 PDF로 변환할 수 없는 출력이 제공되는 경우 런타임 문제를 방지하는 데 도움이 되는 조치를 취해야 합니다. Office(Excel 또는 Word) 형식으로 출력을 받으려면 **PDF로 변환** 옵션을 선택해야 합니다.
>
> 버전 10.0.26 이상에서 **PDF로 변환** 옵션을 사용하려면 구성된 **프린터** 대상의 **문서 라우팅 유형** 매개 변수로 **PDF** 를 선택해야 합니다.

#### <a name="zpl-printing"></a>ZPL 인쇄

버전 10.0.26 이상에서는 **문서 라우팅 유형** 매개 변수에 대해 **ZPL** 을 선택하여 **Common\\File** 형식 요소에 대한 **프린터** 대상을 구성할 수 있습니다. 이 경우 런타임 시 **PDF로 변환** 옵션이 무시되고 [DRA(문서 라우팅 에이전트)](install-document-routing-agent.md)의 ZPL(Zebra 프로그래밍 언어) 계약을 사용하여 TXT 또는 XML 출력이 선택한 프린터로 직접 전송됩니다. ZPL II 라벨 레이아웃을 나타내는 ER 형식에 이 기능을 사용하여 다양한 라벨을 인쇄합니다.

[![대상 설정 대화 상자에서 문서 라우팅 유형 매개 변수 설정.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

이 기능에 대한 자세한 내용은 [ZPL 레이블을 인쇄하기 위한 새 ER 솔루션 설계](er-design-zpl-labels.md)를 참조하십시오.

### <a name="limitations"></a>한계

**프린터** 대상은 클라우드 배포용으로만 구현됩니다.

### <a name="use-the-printer-destination"></a>프린터 대상 사용

1. 생성된 문서를 프린터로 보내려면 **사용** 옵션을 **예** 로 설정합니다.
2. **프린터 이름** 필드에서 필요한 네트워크 프린터를 선택합니다.
3. **인쇄 아카이브로 저장을 설정하시겠습니까?** 추가 인쇄에 사용할 수 있도록 생성된 출력을 인쇄 아카이브에 저장하려면 옵션을 **예** 로 설정합니다. 아카이브된 출력에 나중에 액세스하려면 **조직 관리** \> **조회 및 보고서** \> **보고서 아카이브** 로 이동하십시오.

[![프린터 대상 사용.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> **프린터** 대상을 구성할 때 **PDF로 변환** 옵션을 켤 필요가 없습니다. 옵션이 꺼져 있어도 인쇄용 PDF 변환이 발생합니다.

Excel 형식으로 아웃바운드 문서를 인쇄할 때 특정 [페이지 방향](electronic-reporting-destinations.md#SelectPdfPageOrientation)을 사용하려면 **PDF로 변환** 옵션을 켜야 합니다. **PDF로 변환** 옵션을 **예** 로 설정하면 **페이지 방향** 필드를 사용할 수 있습니다. **페이지 방향** 필드에서 페이지 방향을 선택할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [전자 보고(ER) 대상](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
