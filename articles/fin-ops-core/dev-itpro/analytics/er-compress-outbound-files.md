---
title: 전자보고에서 생성되는 대용량 문서 압축
description: 이번에는 전자 보고(ER) 형식으로 생성된 큰 문서를 압축하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7ef8f730f2e207a8fd28c2bf5167d14f57d6c607314bfc48d4358a59d3ef5c43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460697"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>전자보고에서 생성되는 대용량 문서 압축 

[!include [banner](../includes/banner.md)]

[전자 보고(ER) 프레임워크](general-electronic-reporting.md)를 사용하여 아웃바운드 문서를 생성하기 위해 트랜잭션 데이터를 가져오는 솔루션을 구성할 수 있습니다. 이 생성된 문서는 상당히 클 수 있습니다. 이러한 유형의 문서가 생성되면 [AOS(Application Object Server)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations) 메모리가 문서를 보유하는 데 사용됩니다. 어느 시점에서 문서는 Microsoft Dynamics 365 Finance 애플리케이션에서 다운로드해야 합니다. 현재 ER에서 생성되는 단일 문서의 최대 크기는 2GB로 제한됩니다. 또한 Finance는 현재 다운로드한 파일의 크기를 1GB로 [제한](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3)합니다. 따라서 이러한 제한이 초과될 가능성을 줄이고 산술 연산 예외에서 **스트림이 너무 길거나** **오버플로 또는 언더플로를 수신할 가능성** 을 줄이는 ER 솔루션을 구성해야 합니다.

솔루션을 구성할 때 **폴더** 유형의 루트 요소를 추가하여 중첩된 요소에 의해 생성된 콘텐츠를 압축하여 Operations 디자이너에서 ER 형식을 조정할 수 있습니다. 압축은 '적시에' 작동하므로 최대 메모리 사용량과 다운로드할 파일 크기를 줄일 수 있습니다.

> [!NOTE]
> 파일 압축은 CPU 사용량의 추가 비율을 차지합니다.

이 접근 방식에 대한 자세한 내용은 이 항목의 예시를 완료하십시오.

## <a name="example-compress-an-outbound-document"></a>예:, 아웃바운드 문서 압축

이 예는 **시스템 관리자** 또는 **전자 보고 함수 컨설턴트** 역할에 지정된 사용자가 생성된 문서를 압축하도록 ER 형식을 구성할 수 있는 방법을 보여줍니다.

### <a name="prerequisites"></a>전제 조건

이 항목의 절차를 완료하기 전에 다음 단계를 완료해야 합니다.

1. [구성 공급자를 활성화합니다](er-defer-xml-element.md#activate-a-configuration-provider).
2. [샘플 ER 구성을 가져옵니다](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [가져온 형식을 검토합니다](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> 현재 형식 구조는 **File** 유형의 **Report** 요소에서 시작하며 XML 요소를 포함합니다. 따라서 아웃바운드 문서는 XML 형식으로 생성되며 압축은 사용되지 않습니다.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>압축되지 않은 문서를 얻기 위해 ER 형식 생성

1. [가져온 형식을 실행합니다](er-defer-xml-element.md#run-the-imported-format).
2. XML 형식으로 생성된 문서의 크기는 3KB입니다.

    ![압축되지 않은 아웃바운드 문서의 미리보기입니다.](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>생성된 출력을 압축하도록 형식 수정

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **모델을 확장하여 지연된 요소** 를 학습합니다.
3. **지연된 XML 요소 구성을 학습하려면 형식** 을 선택하십시오.
4. **디자이너** 를 선택하여 형식 구조를 수정합니다.
5. **형식 디자이너** 페이지의 **형식** 탭에서 **루트 추가** 를 선택하여 루트 형식 요소를 추가합니다.
6. **추가** 대화 상자에서 **Common\\Folder** 를 선택합니다.
7. **확인** 을 선택하여 새 루트 요소의 추가를 확인합니다.
8. **저장** 을 선택합니다.

> [!NOTE]
> 형식 구조는 **Folder** 유형의 요소에서 시작합니다. 이 요소는 압축(zip) 파일로 출력을 생성합니다. **Report** 요소에 의해 생성된 문서를 아웃바운드 zip 파일에 넣으면 내용이 압축되어 아웃바운드 파일의 크기가 줄어듭니다.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>압축 문서를 얻기 위해 ER 형식 생성

1. **형식 디자이너** 페이지에서 **실행** 을 선택합니다.
2. 웹 브라우저에서 제공하는 zip 파일을 다운로드하고 검토를 위해 엽니다.
3. ZIP 형식으로 생성된 문서의 크기는 1KB입니다.

    > [!NOTE] 
    > 이 zip 파일이 보유하고 있는 XML 파일의 압축률은 87%입니다. 압축 비율은 압축되는 데이터에 따라 다릅니다.

    ![압축된 아웃바운드 문서의 미리보기입니다.](./media/er-compress-outbound-files2.png)

> [!NOTE]
> 출력을 생성하는 형식 요소(이 예시에서는 **보고서** 요소)에 대해 ER [대상](electronic-reporting-destinations.md)이 구성된 경우 출력 압축이 무시됩니다.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[전자 보고(ER) 대상](electronic-reporting-destinations.md)

[ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]