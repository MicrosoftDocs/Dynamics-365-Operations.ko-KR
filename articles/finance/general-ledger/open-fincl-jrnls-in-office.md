---
title: Office에서 재무 분개장 템플릿 열기
description: 이 문서에서는 Microsoft Excel 템플릿을 사용하여 사용자 지정 재무 분개장을 작성할 때 발생할 수 있는 문제점들에 대해 설명합니다.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896351"
---
# <a name="open-financial-journal-templates-in-office"></a>Office에서 재무 분개장 템플릿 열기

[!include [banner](../includes/banner.md)]

이 문서에서는 Microsoft Excel 템플릿을 사용하여 사용자 지정 재무 분개장을 작성할 때 발생할 수 있는 문제점들에 대해 설명합니다.

## <a name="symptom"></a>증상

재무 저널용 사용자 지정 Excel 템플릿을 만들었지만 이 템플릿이 **Excel에서 라인 열기** 메뉴에 표시되지 않습니다. 또는 이 템플릿이 메뉴에 표시되지만 일단 선택하면 다른 템플릿이 열립니다.

## <a name="resolution"></a>해결책

Excel에서 열기 기능(기본 설정된 기능)은 현재 페이지의 루트 데이터 원본(테이블)을 사용하여 **Excel에서 열기** 메뉴의 옵션으로 표시되는 Office 템플릿 또는 데이터 엔터티를 결정합니다. 이러한 동작은 재무 분개장에서 결코 바람직한 경험이 아닙니다. 그 이유는 재무 분개장이 기타 다양한 유형에 속한 분개장의 루트 데이터 원본과 동일한 테이블(LedgerJournalTable 및 LedgerJournalTrans)을 사용하기 때문입니다.

재무 분개장의 경우, Excel의 라인 열기 기능은 일반 분개장 또는 지불 분개장과 같이 현재 작업 중인 분개장에 맞게 설계된 템플릿을 표시하는 데 사용됩니다. 예를 들어, 공급업체 지불 분개장과 함께 사용하도록 고안된 템플릿은 기본 계정을 공급업체 계정으로 사용하도록 설계됩니다.

**Excel에서 라인 열기** 와 **Excel에서 열기** 메뉴에서 사용할 수 있도록 템플릿을 판촉하려는 경우, 쉬운 개발자 경험은 **LedgerIJournalExcelTemplate** 인터페이스를 구현하고 **DocuTemplateRegistrationBase** 클래스를 확장하는 데 그 의의가 있습니다. 이러한 접근 방식의 상당수 예들은 시스템에서 구현됩니다. 참고로 사용할 수 있는 한 가지 예는 일반 분개장(또는 일일 분개장) 용도로 생성된 **LedgerDailyJournalExcelTemplate** 인터페이스입니다.

**LedgerIJournalExcelTemplate** 인터페이스는 템플릿에 대해 구현되며 **Excel에서 라인 열기** 메뉴는 사용 중인 분개장의 분개장 유형에 따라 템플릿을 필터링하고 해당 분개장에 사용할 수 있는 템플릿만 표시합니다. 또한 인터페이스는 계정 유형 요구 사항을 충족하지 않는다면 분개장에 대해 템플릿을 열 수 없도록 하는 유효성 검사 방법도 제공합니다. 예를 들어, 계정 유형은 **공급업체** 또는 **원장** 유형에 속해야 한다고 지정할 수 있습니다.

이 기능에 관한 자세한 내용은 [Excel에서 라인 열기 메뉴에 템플릿 추가](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md)를 참조하세요.
