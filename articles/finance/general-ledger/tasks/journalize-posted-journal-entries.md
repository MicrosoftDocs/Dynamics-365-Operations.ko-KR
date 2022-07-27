---
title: 게시된 분개장 항목 분개
description: 이 절차는 게시된 분개장 항목을 분개하는 방법을 보여줍니다.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8451753"
---
# <a name="journalize-posted-journal-entries"></a>게시된 분개장 항목 분개

[!include [banner](../../includes/banner.md)]

총계정원장의 분개 프로세스는 총계정원장에 게시된 전표 항목을 그룹화하고 보고하는 방법을 제공합니다. 제공한 기준에 따라 처리는 고유 번호 시퀀스를 사용하고 총계정원장 **분개장 번호** 값을 참조로 포함하는 전표 목록을 생성합니다.

게시된 분개장 항목을 분개하려면 다음 단계를 따릅니다. 이 절차에서는 **USMF** 데모 데이터 회사를 사용합니다.

1. **총계정원장** \> **원장 설정** \> **총계정원장 매개 변수** 로 이동합니다.
2. **확장 원장 분개장** 필드에서 값을 선택합니다. **예** 를 선택하면 보고서 출력이 달라집니다.
3. 분개 프로세스가 실행되지 않은 경우 기간을 마감할 수 있는지를 선택합니다. **예** 를 선택하면 해당 기간에 대한 분개 프로세스가 완료될 때까지 기간을 마감할 수 없습니다.
4. 페이지를 닫습니다.
5. **총계정원장** \> **정기 작업** \> **분개** 로 이동하고 **필터** 를 선택합니다.
6. 정의할 필터 기준에 대한 행을 선택합니다.
7. **기준** 필드에서 값을 입력하거나 필터 기준을 선택합니다.
8. **확인** 을 선택하여 페이지를 닫습니다.
9. **확인** 을 선택하여 분개 프로세스를 시작합니다. 프로세스가 완료되면 보고서가 생성됩니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
