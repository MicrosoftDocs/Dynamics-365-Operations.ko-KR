---
title: Excel 템플릿을 다시 적용하여 전자 보고 형식 수정
description: 이 항목에서는 수정된 Excel 템플릿을 다시 적용하여 비즈니스 문서를 생성하는 데 사용되는 전자 보고(ER) 형식을 수정하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57f0db12657878fa34c86c55925d62100c26cad8799e5e6ace7e7dd81d91cd9f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460903"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Excel 템플릿을 다시 적용하여 전자 보고 형식 수정

[!include [banner](../includes/banner.md)]

전자 보고(ER) 도구는 전자 형식의 비즈니스 문서를 생성하는 데 사용됩니다. 비즈니스 문서를 생성하려면 ER 형식을 만든 다음 ER 디자이너를 사용하여 비즈니스 문서의 레이아웃을 정의하고 여기에 포함되어야 하는 데이터를 지정해야 합니다. 그런 다음 ER 형식을 실행하여 비즈니스 문서를 생성할 수 있습니다.

ER 도구는 Microsoft Excel 파일로 비즈니스 문서를 생성하는 데 사용할 수 있습니다. Excel 문서를 이러한 문서의 템플릿으로 사용할 수 있습니다. ER 디자이너에서 문서 레이아웃을 정의하기 위해 템플릿으로 사용하려는 Excel 문서의 내용을 정의된 ER 형식으로 가져올 수 있습니다. 자세한 내용을 보고 이 시나리오를 연습하려면 작업 가이드 **ER OPENXML 형식의 생성 보고서에 대한 구성 디자인** 을 재생하세요(7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677) 비즈니스 프로세스의 일부).

비즈니스 문서의 템플릿으로 사용되는 Excel 문서를 편집하는 경우 새로운 ER 기능을 통해 업데이트된 템플릿을 ER 형식으로 다시 적용할 수 있습니다. 그런 다음 ER 형식이 업데이트되어 업데이트된 템플릿을 준수합니다. 이 기능에 대한 자세한 내용은 작업 가이드 **ER Excel 템플릿을 재적용하여 서식 수정** 을 재생하세요(7.5.5.3 IT 서비스/솔루션 구성 요소 획득/개발(10683) 비즈니스 프로세스의 일부). 업데이트된 템플릿을 가져오는 작업 가이드 단계에서 템플릿으로 지불 보고서 Excel 파일의 수정된 템플릿 SampleVendPaymWsReport2를 사용합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]