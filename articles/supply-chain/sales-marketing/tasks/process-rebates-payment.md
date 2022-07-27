---
title: 결제에 대한 리베이트 처리
description: 이 절차는 승인 및 처리된 고객 리베이트를 신용 메모로 변환하는 방법을 보여줍니다.
author: Henrikan
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce813f0f5d9aa750828b524dd9fdf9b4a9f0854
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448522"
---
# <a name="process-rebates-for-payment"></a>결제에 대한 리베이트 처리

[!include [banner](../../includes/banner.md)]

이 절차는 승인 및 처리된 고객 리베이트를 신용 메모로 변환하는 방법을 보여줍니다. USMF 데모 회사에서 이 가이드를 사용할 수 있습니다. 이 가이드의 전제 조건은 마크 상태의 하나 이상의 리베이트 청구가 있어야 한다는 것입니다. USMF를 사용하는 경우 이 가이드를 시작하기 전에 "고객 리베이트 생성 및 처리" 가이드를 실행해야 합니다.


## <a name="convert-rebate-claims-to-credit-note"></a>리베이트 청구를 신용 메모로 변환
1. 모든 고객으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 작업 창에서 수집을 클릭합니다.
5. 트랜잭션 정산을 클릭합니다.
6. 기능을 클릭합니다.
7. 리베이트 프로그램을 클릭합니다.
    * 리베이트 페이지에는 고객 리베이트 워크벤치에서 처리했으며 상태 표시인 리베이트 청구가 나열됩니다.    
8. 편집을 클릭합니다.
    * 신용 메모에 포함할 청구에 대해 표시 필드에 확인 표시를 설정합니다.   
9. 기능을 클릭합니다.
10. 크레딧 메모 만들기를 클릭합니다.
    * 분개장이 전기되었음을 알리는 메시지가 나타납니다(수취 계정 매개 변수 페이지에 지정된 대로 수취 계정 소비 분개장입니다). 이로 인해 실제 부채(신용) 금액이 고객 잔액으로 이동됩니다. 이것은 고객의 계정이 대변에 기입되었고 리베이트 발생 계정이 인출되었음을 의미합니다.  
11. 페이지를 닫습니다.
12. 취소를 클릭합니다.
    * 업데이트를 볼 수 있도록 페이지를 새로 고칩니다.  
13. 작업 창에서 수집을 클릭합니다.
14. 트랜잭션 정산을 클릭합니다.
    * 송장 참조가 없는 총 리베이트 금액을 나타내는 음수 금액에 대한 트랜잭션이 고객 잔액에 추가되었습니다.   
15. 취소를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]