---
title: 원시 XML로 콘텐츠를 추가하여 보고서 생성
description: XML 형식으로 발신 문서를 생성하는 전자 보고(ER) 형식을 디자인할 수 있습니다.
author: NickSelin
ms.date: 05/25/2018
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
ms.openlocfilehash: 160f27f4f44ab6982addb7294db889e2a8dbfcfbc03f7849548c44364b070aa9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460834"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>원시 XML로 콘텐츠를 추가하여 보고서 생성

[!include[banner](../includes/banner.md)]

새로운 **RAW XML** 형식 요소를 사용하여 XML 형식으로 발신 문서를 생성하는 전자 보고(ER) 형식을 디자인할 수 있습니다. 경우에 따라 다음 이유 중 하나 이상으로 인해 이러한 보고서에 원시 XML 데이터를 추가하는 것을 선호할 수 있습니다.

- XML 구조는 런타임 표현식을 실행하여 자동으로 생성될 수 있기 때문에 원본 디자인 및 보고서의 지속적인 유지 관리를 위해 원시 XML을 사용하는 것이 더 편리합니다. 따라서 디자인 타임에 여러 형식 요소에 대해 여러 바인딩을 결정할 필요가 없습니다. 사용 중인 데이터 원본에 보고서가 생성되는 동안 XML 요소를 만드는 데 사용할 수 있는 정보가 포함되어 있을 때 가능합니다.
- 이전에 시스템에 수신되어 저장된 XML 콘텐츠로 보고서를 채우는 데 다른 방법을 사용할 수 없습니다. 예를 들어 생성된 XML 응답에는 이전에 보낸 XML 요청의 내용이 포함되어야 할 수 있습니다.
- 숫자 코드를 기반으로 생성된 문서에 문자를 삽입하는 데 다른 방법을 사용할 수 없습니다. 일부 언어 및 문자의 경우 이 유형의 코드가 존재하지 않습니다. 예에는 그리스 문자 rho(ρ) 및 \&eacute;와 같은 HTML 엔티티 코드가 포함됩니다. 예리한 악센트(é)가 있는 *e* 의 경우.

> [!NOTE]
> 프레임워크는 **RAW XML** 형식 요소를 사용하여 생성된 문서에 배치된 XML 콘텐츠가 올바른지 여부를 제어하지 않습니다.

이 기능에 대해 자세히 알아보려면 **ER 원시 XML 데이터를 사용하여 XML 보고서 생성(1부: 데이터 모델 설계)** 및 **ER 원시 XML 데이터를 사용하여 XML 보고서 생성(2부: 7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677)** 비즈니스 프로세스의 **일부인 디자인 및 실행 보고서**) 작업 가이드는 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=874684)에서 다운로드할 수 있습니다. 이 작업 가이드는 원시 XML 데이터를 생성된 파일에 삽입하도록 ER 형식을 구성하는 과정을 안내합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]