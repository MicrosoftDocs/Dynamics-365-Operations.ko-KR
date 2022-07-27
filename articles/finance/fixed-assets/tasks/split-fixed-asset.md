---
title: 고정 자산 분할
description: 이 항목에서는 하나의 자산 장부를 새 자산 장부로 분할하는 방법에 대해 설명합니다.
author: moaamer
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2fbca50342196dd9f5acb53027fb9c0052a81de
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451246"
---
# <a name="split-a-fixed-asset"></a>고정 자산 분할

[!include [banner](../../includes/banner.md)]

이 항목에서는 하나의 자산 장부를 새 자산 장부로 분할하는 방법에 대해 설명합니다. 

## <a name="create-a-new-fixed-asset"></a>새 고정 자산 생성

1. 탐색 창에서 **모듈 \> 고정 자산 \> 고정 자산 \> 고정 자산** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **고정 자산 그룹** 필드에 값을 입력하거나 선택합니다. 나중에 분할 프로세스에서 사용할 고정 자산 번호를 기록해 두십시오.
4. **이름** 필드에 값을 입력합니다.
5. 양식을 닫습니다.

## <a name="split-a-fixed-asset"></a>고정 자산 분할

감가상각된 전체 자산을 분할하기 전에 자산 장부 상태를 수동으로 **닫힘** 에서 **열림** 으로 변경해야 합니다. 자산에 대한 트랜잭션을 게시해야 하는 경우(예: 처분 판매) 장부 상태가 **열려** 있어야 하므로 이 단계가 필요합니다. 또한 **총계정원장 매개 변수** 페이지의 **일반** 탭에서 **하나의 바우처 내에서 다중 트랜잭션 허용** 매개 변수를 설정해야 합니다. 자산 장부 상태가 변경되고 하나의 바우처 내에서 여러 트랜잭션이 허용된 후 다음 단계를 완료하여 자산을 분할합니다.

1. 목록에서 분할할 고정 자산의 링크를 찾아 선택합니다.
2. **장부** 를 선택합니다. 새 자산으로 분할할 장부를 선택합니다.
3. **기능** 을 선택합니다.
4. **고정 자산 분할** 을 선택합니다.
5. **고정 자산으로** 필드에 값을 입력하거나 선택합니다.
6. **장부로** 필드에서 드롭다운 단추를 선택하여 검색을 엽니다.
7. **거래 날짜** 필드에 날짜를 입력합니다.
8. **금액** 필드에 숫자를 입력합니다.
9. **분개장 이름** 필드에 값을 입력하거나 선택합니다.
10. **확인** 을 선택합니다.

## <a name="post-the-journal-transaction"></a>분개장 트랜잭션 게시

1. 탐색 창에서 **모듈 \> 고정 자산 \> 분개장 항목 \> 고정 자산 분개장** 으로 이동하십시오.
2. 목록에서 분할 프로세스로 생성된 분개장을 선택합니다.
3. **라인** 을 선택합니다.

    - 분개장 라인이 생성되었는지 확인합니다.
    - 원본 자산에 대해 Acquisition 조정 트랜잭션이 생성되어 분할 프로세스 중에 지정된 백분율만큼 값이 감소됩니다.
    - 새 자산에 대해 동일한 금액에 대한 획득 트랜잭션이 생성됩니다.

4. **게시** 를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
