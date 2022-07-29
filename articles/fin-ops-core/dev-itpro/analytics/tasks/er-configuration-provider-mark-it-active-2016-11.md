---
title: 구성 공급자를 만들고 활성으로 표시
description: 이번에는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 구성 공급자를 생성할 수 있는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5b429badcbcc0e9829d82785a6e1f1a2504f5ec9b9ac74d249032f272dea103
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460720"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>구성 공급자를 만들고 활성으로 표시

[!include [banner](../../includes/banner.md)]

이번에는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 전자 보고(ER)용 구성 공급자를 생성하는 방법에 대해 설명합니다. 각 ER 구성은 공급자를 구성 작성자로 참조합니다. 이 예시에서는 샘플 회사인 Litware, Inc.에 대한 구성 공급자를 생성합니다. ER 구성 공급자는 모든 회사에서 공유되므로 이러한 단계는 모든 회사에서 수행할 수 있습니다.

## <a name="create-a-provider"></a>공급자 만들기
1. 왼쪽 상단의 **탐색 창** 으로 이동하여 **조직 관리** 를 선택합니다.
2. **작업 공간 > 전자 보고** 로 이동합니다.
3. **관련 링크 > 구성 공급자** 로 이동합니다.
4. **새로 만들기** 를 선택합니다.
    - 공급자 기록에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하고 Litware, Inc. (https://www.litware.com)에 대한 기록이 이미 있는 경우 이 절차를 건너뜁니다.  
5. 이름 필드에 `Litware, Inc.`를 입력하십시오.
6. 인터넷 주소 필드에 `https://www.litware.com`를 입력합니다.
7. **저장** 을 선택합니다.
8. 페이지를 닫습니다.

## <a name="select-as-an-active-provider"></a>활성 공급자로 선택합니다.
1. Litware, Inc. 공급자를 선택합니다.
2. **활성 설정** 을 선택합니다.

![전자 보고 작업 공간 페이지.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]