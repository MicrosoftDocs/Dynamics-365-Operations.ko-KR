---
title: 생산 흐름 버전의 만료 날짜 정의
description: 주어진 날짜에 생산 흐름 버전의 유효성 및 처리를 종료하거나 활성 버전을 새 버전으로 교체하려면 버전에 만료 날짜를 설정해야 합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f6ee9177664767c31eaa3e9b65d7559a1a9662f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448726"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>생산 흐름 버전의 만료 날짜 정의

[!include [banner](../../includes/banner.md)]

주어진 날짜에 생산 흐름 버전의 유효성 및 처리를 종료하거나 활성 버전을 새 버전으로 교체하려면 버전에 만료 날짜를 설정해야 합니다. 버전을 비활성화할 필요는 없습니다.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>프로덕션 흐름 버전을 종료하려면 만료 날짜를 설정하세요.
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이미 정의된 버전이 있는 생산 흐름을 선택합니다.  
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 편집을 클릭합니다.
5. 목록에서 선택한 행을 표시합니다.
6. 만료 날짜 필드에 날짜와 시간을 입력합니다.
    * 만료 날짜의 경우 새 버전이 시작되거나 활성화되지 않습니다. 또한 이 생산 흐름에 대한 작업을 더 이상 만들거나 시작할 수 없습니다. 만료 날짜 후에도 시작된 작업을 계속 완료할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]