---
title: 생성된 파일에서 BOM 문자를 억제하도록 ER 구성 설계
description: 이 항목에서는 BOM(바이트 순서 표시) 문자를 표시하지 않는 보고서를 생성하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9265578deaff4100eb5987eb6090eaa12876044
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461012"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>생성된 파일에서 BOM 문자를 억제하도록 ER 구성 설계

[!include [banner](../includes/banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) [솔루션](er-quick-start1-new-solution.md)을 설계하여 발신 문서를 생성할 수 있습니다. 문서를 텍스트 또는 XML 파일로 생성하려면 솔루션에 ER 형식 구성 요소가 포함된 ER [구성](general-electronic-reporting.md#Configuration)이 있어야 합니다. 생성된 파일의 문자 집합을 나타내는 [문자 인코딩](/windows/win32/intl/character-sets)을 지정하려면 ER 형식이 **공통\\파일** 형식 요소를 포함해야 합니다. ER 형식 구성 요소를 구성하려면 ER 형식 디자이너에서 [초안](general-electronic-reporting.md#component-versioning) 버전의 ER 구성을 열고 **공통\\파일** 요소를 추가합니다. **인코딩** 필드에서 이 구성 요소를 사용하여 런타임에 생성되는 아웃바운드 파일의 인코딩을 지정합니다.

> [!NOTE]
> 형식에 잘못된 인코딩 이름이 포함된 경우 형식 설정에 대한 변경 사항을 저장할 때 오류가 발생합니다.

![형식 디자이너 페이지의 루트 요소 추가.](./media/er-suppress-bom-characters-image1.gif)

**UTF-8**, **UTF-16** 또는 **UTF-32** 를 인코딩으로 지정하면 **BOM 문자 억제** 옵션을 사용할 수 있게 됩니다. 이 옵션을 **예** 로 설정하여 편집 가능한 ER 형식이 실행될 때 런타임에 생성되는 아웃바운드 파일에서 [바이트 순서 표시(BOM) 문자](/globalization/encoding/byte-order-mark)를 제한합니다.

> [!NOTE]
> **인코딩** 필드를 비워 두면 기본 **UTF-8** 인코딩이 사용됩니다.

![형식 디자이너 페이지에서 BOM 문자 표시 안 함 옵션을 설정합니다.](./media/er-suppress-bom-characters-image2.gif)

런타임 시 기능을 검토하려면 적절한 절차를 완료합니다. 예를 들어 [ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md) 토픽의 단계를 완료합니다. 토픽의 [계산이 생성된 출력을 기반으로 하도록 형식 수정](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) 섹션의 단계를 완료한 후 다음 추가 단계를 따르세요.

1. UTF 인코딩을 지정합니다.

    1. **공통\\파일** 유형의 **보고서** 유형을 선택합니다.
    2. **인코딩** 필드에서 **UTF-8** 인코딩을 지정합니다.

2. BOM 문자를 포함하는 XML 파일 생성:

    1. **BOM 문자 억제** 옵션을 **아니요** 로 설정하여 생성된 XML 파일에 BOM 문자를 포함합니다.
    2. [ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md) 토픽의 [계산된 합계가 사용되도록 요약 XML 요소의 실행 연기](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) 섹션에 있는 단계를 완료하고 생성된 파일을 **SampleXmlReport.xml** 로 저장합니다.

3. BOM 문자를 포함하지 않는 XML 파일 생성:

    1. **BOM 문자 억제** 옵션을 **예** 로 설정하여 생성된 XML 파일에 BOM 문자를 억제합니다.
    2. [ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md) 토픽의 [계산된 합계가 사용되도록 요약 XML 요소의 실행 연기](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) 섹션에 있는 단계를 완료하고 생성된 파일을 **SampleXmlReport (1).xml** 로 저장합니다.

4. 파일 비교 유틸리티에서 생성된 파일을 비교합니다.

    가장 먼저 눈에 띄는 차이점은 파일 헤더에 있습니다. SampleXmlReport.xml 파일에는 BOM 문자가 포함되어 있지만 SampleXmlReport(1).xml 파일에는 없습니다.

    ![파일 비교 유틸리티를 사용하여 생성된 파일을 비교합니다.](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>또한, 다음을 참조하세요.

- [ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
