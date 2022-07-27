---
title: 자산 대출
description: 이 항목에서는 자산 관리에서 대출 자산을 등록하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 65809d9be39372412d5d6b419f7356fe2c9668a1a01ede32ef52cbd66753e6d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447037"
---
# <a name="asset-loans"></a>자산 대출

[!include [banner](../../includes/banner.md)]

 

회사가 내부 위치 또는 고객으로부터 수리 또는 유지 관리 작업을 위한 자산을 받고 해당 위치 또는 고객에게 자산을 일시적으로 대출하는 경우 자산 관리는 자산 대출을 추적할 수 있습니다.

## <a name="register-asset-loans-on-a-maintenance-request"></a>유지 관리 요청에 자산 대출 등록

1. **자산 관리** \> **공통** \> **유지 관리 요청** \> **모든 유지 관리 요청** 또는 **활성 유지 관리 요청** 을 선택합니다.
2. 자산 대출을 등록할 유지 관리 요청을 선택한 후 **편집** 을 선택합니다.
3. **요청** 페이지에서 **대출 자산 보내기** 를 선택합니다.
4. 자산을 선택하고 예상 반환 날짜를 입력합니다.
5. **확인** 을 선택합니다.

> [!NOTE]
> - 동일한 자산 유형의 자산이 사용 가능한 경우에만 대출 자산을 보낼 수 있습니다.
> - 대출하는 자산에는 대출 자산으로 사용할 수 있는 자산 수명 주기 상태가 있어야 합니다(예: **InStorage**). 자산 대출이 등록되면 자산의 자산 수명 주기 상태가 자동으로 다음과 같이 업데이트됩니다(예: **OnLoan**).

다른 위치 또는 고객에게 대출한 모든 자산 목록을 보려면 **자산 관리** \> **공통** \> **자산 대출** \> **모든 자산 대출** 을 선택합니다. 자산에 **종료됨** 확인란이 선택되어 있으면 자산이 회사에 반환된 것으로 등록됩니다.

![유지 관리 요청을 관리합니다.](media/06-manage-maintenance-requests.png)

**활성 자산 대출** 페이지에서 아직 회사에 반환되지 않은 모든 대출 자산 목록을 볼 수 있습니다.

## <a name="register-loan-assets-as-returned"></a>대출 자산 반환으로 등록

1. **자산 관리** \> **공통** \> **자산 대출** \> **활성 자산 대출** 을 선택합니다.
2. 반납으로 등록할 자산론을 선택한 후 **자산 대출 반환** 을 선택합니다.
3. **반환됨** 필드에 날짜와 시간을 입력합니다.
4. **확인** 을 선택합니다.
5. **활성 자산 대출** 목록 페이지를 새로 고치고 자산 대출이 더 이상 목록에 나타나지 않는지 확인합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]