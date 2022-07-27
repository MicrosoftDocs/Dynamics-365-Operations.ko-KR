---
title: IBAN(International Bank Account Number) 계좌 유효성 검사 관리
description: 이 항목에서는 IBAN(International Bank Account Number) 계좌 유효성 검사를 관리하는 방법을 설명합니다.
author: roschlom
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 210d2f57e21ec5ac38ba8ca07195e40ff507e2b9
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2021
ms.locfileid: "8451201"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>IBAN(International Bank Account Number) 계좌 유효성 검사 관리

[!include [banner](../includes/banner.md)]

IBAN(International Bank Account Number) 유효성 검사는 IBAN을 은행 계좌에 추가할 때 수행되는 유효성 검사의 양을 늘립니다.

IBAN의 구조에 대한 정보는 Microsoft Dynamics 365 Finance에 저장됩니다. 해당 정보는 은행 계좌에서 IBAN을 처음 사용할 때 자동으로 로드됩니다. 이 정보에는 IBAN의 길이, 은행 계좌 번호와 라우팅 번호의 시작 위치, 은행 계좌 번호와 라우팅 번호의 길이가 포함됩니다.

## <a name="set-up-iban-structures"></a>IBAN 구조 설정

1. **현금 및 은행 관리 \> 설정 \> IBAN 구조** 로 이동합니다.
2. 각 국가 또는 지역에 대한 IBAN 구조가 자동으로 설정되었음을 알 수 있습니다.
3. 특정 국가 또는 지역에 대한 구조를 사용자 지정하려는 경우 편집할 수 있습니다.
4. 구조 정의는 각각의 새 릴리스의 일부가 됩니다. 업데이트할 때마다 최신 정의를 로드하려면 **구조 재설정** 메뉴를 사용할 수 있습니다.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>은행 계좌의 IBAN 구조 유효성 검사

1. **현금 및 은행 관리 \> 은행 계좌 \> 은행 계좌** 로 이동합니다.
2. 은행 계좌를 만듭니다.
3. **추가 정보** 빠른 탭에서 IBAN을 입력합니다.

    IBAN의 길이가 각 국가 또는 지역에 대해 정의된 길이와 일치하지 않으면 경고 메시지가 표시됩니다. IBAN의 길이가 IBAN 구조에 지정된 길이와 일치하지 않으면 진행할 수 없습니다.

    유효성 검사는 또한 은행 계좌 번호가 은행 계좌 번호를 나타내는 IBAN 부분과 일치하는지 확인합니다. 은행 계좌 번호가 일치하지 않으면 경고 메시지가 표시됩니다. 이 메시지는 경고일 뿐입니다. 은행 계좌 번호가 일치하지 않아도 진행할 수 있습니다.

    유효성 검사는 또한 은행 라우팅 번호가 은행 라우팅 번호를 나타내는 IBAN 부분과 일치하는지 확인합니다. 라우팅 번호에는 은행 번호와 종종 추가 은행 지점이 포함됩니다. 은행 라우팅 번호가 일치하지 않으면 경고 메시지가 표시됩니다. 이 메시지는 경고일 뿐입니다. 은행 라우팅 번호가 일치하지 않아도 진행할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
