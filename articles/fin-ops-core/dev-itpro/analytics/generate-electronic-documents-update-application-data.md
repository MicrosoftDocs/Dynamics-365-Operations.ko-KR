---
title: ER을 이용한 전자문서 생성 및 지원자료 업데이트
description: 발신 전자 문서를 생성하기 위해 애플리케이션에서 사용할 수 있는 전자 보고(ER) 형식을 디자인할 수 있습니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460659"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>ER을 이용한 전자문서 생성 및 지원자료 업데이트

[!include [banner](../includes/banner.md)]

발신 전자 문서를 생성하기 위해 애플리케이션에서 사용할 수 있는 전자 보고(ER) 형식을 디자인할 수 있습니다. 수신 전자 문서를 구문 분석하고 해당 문서의 내용을 사용하여 애플리케이션 데이터를 업데이트하는 ER 형식을 설계할 수도 있습니다.

이 기능을 통해 단일 ER 형식을 사용하여 발신 전자 문서를 생성한 다음 애플리케이션 데이터를 업데이트할 수 있습니다. 이 기능은 다음 시나리오에서 사용할 수 있습니다.

- 후속 프로세스에서 애플리케이션 데이터의 반복 사용을 방지하기 위해 전자 문서 생성에 사용된 애플리케이션 데이터를 즉시 표시할 수 있습니다. 예를 들어, 생성된 지불 메시지에 포함된 직후 지불 트랜잭션을 이미 처리된 것으로 표시할 수 있습니다.
- ER 로직을 사용하여 생성된 전자 문서의 처리 기록을 저장합니다. 예를 들어, ER 표현식을 사용하여 생성된 고유한 지불 메시지 ID입니다. 식은 문서를 생성하기 위해 ER 형식을 실행할 때 ER 대화 상자에 입력한 정보를 기반으로 합니다.

이 기능에 대해 자세히 알아보려면 ER 세트를 재생합니다. 애플리케이션 데이터 업데이트로 문서 생성 작업 가이드(7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677) 비즈니스 프로세스의 일부)에서 Intrastat 보고에 대한 세부 정보를 설명합니다. 이 작업 가이드의 특정 단계를 완료하려면 다음 파일이 필요합니다. 이 파일을 다운로드하여 로컬 컴퓨터에 저장합니다.

- [ER 데이터 모델: Intrastat(모델)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [ER 모델 매핑 구성: Intrastat(매핑)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [ER 형식 구성: Intrastat(형식)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
