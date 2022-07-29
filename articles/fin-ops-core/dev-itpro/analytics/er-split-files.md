---
title: 파일 크기 및 콘텐츠 수량에 따라 생성된 XML 파일 분할
description: 이 항목에서는 파일 크기 및 콘텐츠 항목 수량에 따라 생성된 파일을 분할하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/23/2021
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
ms.openlocfilehash: 3735bcb06eff966fc364a891b38d44e34e845e35f59314822d13eba40d51d5f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460674"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>파일 크기 및 콘텐츠 수량에 따라 생성된 XML 파일 분할

[!include[banner](../includes/banner.md)]

전자 보고(ER) 형식을 설계하여 XML 형식의 발신 문서를 생성할 수 있습니다. 경우에 따라 이러한 문서는 최대 파일 크기 또는 일부 XML 노드의 최대 수와 같은 특정 기준을 충족하는 경우에만 허용될 수 있습니다. ER 형식을 설계하여 해당 문서의 수신자가 지정하는 요구 사항을 충족하는 전자 문서를 생성할 수 있습니다.

- FILE 형식 요소의 경우 파일 크기에 대한 제한을 ER 표현식으로 정의할 수 있습니다. ER 보고서 생성 시 정의된 제한을 초과하면 ER은 현재 파일 생성을 마치고 다음 파일 생성을 진행합니다.
- 모든 XML 요소 형식의 경우 요소의 수에 대한 제한을 ER 표현식으로 정의할 수 있습니다. ER 보고서 실행 시 생성된 파일에서 XML 노드 수가 정의된 제한을 초과하면 ER은 현재 파일 생성을 마치고 다음 파일 생성을 진행합니다.
- 모든 XML 시퀀스 형식 요소의 경우 하위 요소의 수에 대한 제한을 ER 표현식으로 정의할 수 있습니다. ER 보고서 실행 시 생성된 파일에서 형식 요소의 중첩된 XML 노드 수가 정의된 제한을 초과하면 ER은 현재 파일 생성을 마치고 다음 파일 생성을 진행합니다.
- 모든 XML ELEMENT 형식 요소를 깨지지 않는 것으로 표시할 수 있습니다. 이러한 방식으로 생성된 단일 파일의 형식 요소 아래에서 생성된 XML 노드의 중첩 항목을 유지할 수 있습니다.

XML ELEMENT 및 XML SEQUENCE 형식 요소를 사용하여 생성된 파일에 XML 노드를 추가하는 것 외에도 RAW XML 형식 요소를 사용할 수 있습니다. 그러나 RAW XML 형식 요소를 사용하여 추가한 노드는 요소 수에 대한 제한을 평가하기 위해 노드 수를 계산할 때 고려되지 않습니다.

특정 제한을 초과할 때마다 생성된 출력을 분할하도록 구성된 FILE 형식 요소에 대한 파일 대상을 구성한 경우 생성된 출력의 각 부분은 구성된 파일 대상에 개별 파일로 전송됩니다. 출력을 분할하여 생성된 파일의 이름을 고유하게 지정하려면 FILE 형식 요소에 대해 ER 표현식을 구성해야 합니다. NUMBER SEQUENCE 유형의 ER 데이터 소스를 포함하는 경우 분할 출력의 각 부분에 대해 숫자 시퀀스가 증가합니다.

이 기능에 대해 자세히 알아보려면 **ER 파일 크기 또는 콘텐츠 항목 수량에 따라 XML 파일 분할** 작업 가이드를 재생합니다. 이는 **7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677)** 비즈니스 프로세스의 일부이며 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=874684)에서 다운로드할 수 있습니다. 이 작업 가이드는 파일 크기 및 콘텐츠 항목 수량에 대한 제한을 기반으로 생성된 파일을 분할하도록 ER 형식을 구성하는 프로세스를 안내합니다. 작업 가이드를 완료하려면 다음 파일을 다운로드해야 합니다.

- [ER 모델 구성 - XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [ER 형식 구성 - XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>추가 리소스
[전자 보고(ER) 대상](electronic-reporting-destinations.md)

[전자 보고(ER) 공식 디자이너](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
