---
title: 주 계정 카테고리 설정
description: 이 항목에서는 Dynamics 365 Finance에서 기본 계정 범주를 설정하는 방법에 대해 설명합니다.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3530ba65dc0a4978ca4b1ca4b1acd96c79749a6f16e430fb260729dd3e28dbac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450328"
---
# <a name="set-up-main-account-categories"></a>주 계정 카테고리 설정

[!include [banner](../../includes/banner.md)]

이 항목에서는 에서 기본 계정 범주를 설정하는 방법에 대해 설명합니다. 기본 계정 범주는 재무 보고 및 Power BI의 기본 보고서에 사용됩니다. 기본적으로 생성되는 기본 계정 범주는 이름을 변경할 수 있지만 삭제할 수는 없습니다. 보고 및 분석 목적으로 추가 계정 범주를 만들고 사용할 수 있습니다. 이 항목에서는 USMF 데모 회사를 사용합니다.

## <a name="create-a-main-account-category"></a>기본 계정 범주 생성
1. 탐색 창에서 **모듈 > 총계정원장 > 계정 차트 > 계정 > 기본 계정 카테고리** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **기본 계정 카테고리** 필드에 고유한 이름을 입력합니다.
4. **설명** 필드에 기본 계정 카테고리에 대한 설명을 입력합니다.
5. **기본 계정 유형** 필드에서 카테고리에 연결할 기본 계정 유형을 선택합니다.

## <a name="link-main-accounts-to-account-category"></a>기본 계정을 계정 카테고리에 연결
1. **기본 계정 연결** 을 클릭합니다.
2. 목록에서 **연결됨** 열의 상자를 선택하여 기본 계정 카테고리에 할당할 기본 계정을 선택합니다. 기본 계정을 기본 계정 범주에 할당하면 해당 범주가 재무 보고 및 분석에 사용될 때 계정의 잔액이 집계됩니다.  
3. 기본 계정을 선택하려면 **연결됨** 옵션을 선택하거나 선택 취소합니다.
4. **확인** 을 선택합니다.
5. **예** 를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]