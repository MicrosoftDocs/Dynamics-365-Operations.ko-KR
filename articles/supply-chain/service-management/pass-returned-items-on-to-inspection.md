---
title: 반품된 품목을 검사에 전달
description: 반품된 품목을 등록할 때 재고로 반품되거나 다른 방식으로 폐기되기 전에 검사를 위해 품목을 보내야 하는지 결정하세요.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7c238536ead603b11d4c97e98289ab157ad86db
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449143"
---
# <a name="pass-returned-items-on-to-inspection"></a>반품된 품목을 검사에 전달 

[!include [banner](../includes/banner.md)]


반품된 품목을 등록할 때 재고로 반품되거나 다른 방식으로 폐기되기 전에 검사를 위해 품목을 보내야 하는지 결정할 수 있습니다.

1.  **재고 관리** \> **분개** \> **품목 도착** \> **품목 도착** 을 클릭합니다.
    
    \-또는
    
    **재고 관리** \> **분개** \> **품목 도착** \> **생산 입력** 을 클릭합니다.

2.  **위치 분개장** 양식에서 평소와 같이 품목의 입고를 등록합니다.
    

    > [!NOTE]
    > <P>반품 품목 입고 등록에 대한 자세한 내용은 <A href="register-the-receipt-of-returned-items.md">반품 품목 입고 등록</A>을 참조하세요.</P>



3.  **기본값** 탭의 **취급 모드** 영역에서 **검역 관리** 상자를 선택합니다.

그러면 시스템에서 검역 명령을 생성하라는 메시지가 표시되고 검사를 수행하는 사람이나 부서는 **검역 명령** 양식을 사용하여 이 명령에 응답합니다.

## <a name="see-also"></a>참고 항목

[검수를 통한 반품 접수](take-returned-items-through-inspection.md)

[반품 처리 방법 지정](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]