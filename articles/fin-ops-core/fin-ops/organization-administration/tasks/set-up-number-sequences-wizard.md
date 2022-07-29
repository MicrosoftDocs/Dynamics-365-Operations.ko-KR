---
title: 마법사를 사용하여 숫자 시퀀스 설정
description: 이 항목에서는 마법사를 사용하여 필요한 모든 번호 시퀀스를 동시에 설정하는 방법에 대해 설명합니다.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7388a835147e1e8242463fee98c57c300d062877
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "8460763"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>마법사를 사용하여 숫자 시퀀스 설정

[!include [banner](../../includes/banner.md)]

번호 시퀀스는 필요한 마스터 데이터 레코드 및 트랜잭션 레코드에 대해 읽을 수 있는 고유 식별자를 생성하는 데 사용됩니다. 식별자가 필요한 마스터 데이터 또는 트랜잭션 레코드를 참조라고 합니다. 참조에 대한 새 레코드를 생성하려면 먼저 번호 시퀀스를 설정하고 참조와 연결해야 합니다. 이 항목에서는 마법사를 사용하여 필요한 모든 번호 시퀀스를 동시에 설정하는 방법에 대해 설명합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

1. **탐색 > 모듈 > 조직 관리 > 번호 시퀀스 > 번호 시퀀스** 로 이동합니다.
2. **생성** 을 선택합니다.
3. **다음** 을 선택합니다.

   - 이 페이지에서 식별 코드, 최저값, 최고값을 수정할 수 있습니다. 또한 숫자 시퀀스가 연속적이어야 하는지 여부를 나타낼 수 있습니다.   
   - 숫자 시퀀스에 대해 숫자를 미리 할당해야 하는 경우 **연속** 옵션을 선택하지 마세요. 범위 세그먼트를 숫자 시퀀스 형식에 추가하려면 목록에서 형식을 선택한 다음 **형식에 범위 포함** 을 선택합니다. 범위 세그먼트를 숫자 시퀀스 형식에서 제거하려면 목록에서 형식을 선택한 다음 **형식에서 범위 제거** 를 선택합니다. 자동 생성에서 번호 시퀀스를 제외하려면 목록에서 번호 시퀀스를 선택한 다음 **삭제** 를 선택합니다.  

4. **다음** 을 선택합니다.
5. **완료** 를 선택합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
