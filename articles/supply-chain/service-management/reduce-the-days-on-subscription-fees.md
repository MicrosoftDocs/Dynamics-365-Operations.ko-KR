---
title: 구독료 일 수 감소
description: 기존 구독료의 일 수를 줄이기 위해 구독료 간격에 더 이상 포함되지 않아야 하는 기간을 제거하는 새 트랜잭션을 생성할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df1a27576b93c4ace4a5f17271595d259e96a51a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448603"
---
# <a name="reduce-the-days-on-subscription-fees"></a>구독료 일 수 감소 

[!include [banner](../includes/banner.md)]


기존 구독료의 일 수를 줄이기 위해 구독료 간격에 더 이상 포함되지 않아야 하는 기간을 제거하는 새 트랜잭션을 생성할 수 있습니다.

## <a name="reduce-the-days-on-a-subscription-fee"></a>구독료 일 수 감소

1.  **서비스 관리** \> **공통** \> **서비스 구독** \> **모든 서비스 구독** 을 클릭합니다. 서비스 구독을 선택하고 작업 창에서 **구독료** 를 클릭합니다.

2.  **구독 유형** 필드에서 **감소 일 수** 를 선택합니다.

3.  **시작일** 필드 및 **종료일** 필드를 사용하여 구독료 기간에서 제거할 구독료의 날짜 간격을 정의한 다음 **확인** 을 클릭합니다.

생성된 트랜잭션를 보려면 **구독** 양식에서 **수수료 트랜잭션** 을 클릭합니다.

## <a name="example"></a>예:

구독 거래 기간이 1월 1일부터 1월 31일까지 실행되고 기간을 10일 줄이려면 축소 기간이 1월 1일부터 1월 10일까지인 새 거래를 생성하세요. (감소 기간은 1월 5일부터 1월 15일까지 또는 기타 10일 기간이 될 수도 있습니다.)

또한 감소 기간의 **시작일** 이 1월 21일(31 - 10)인 경우 **종료일** 을 1월 31일 이후의 날짜로 설정할 수 있으며 수수료 트랜잭션 기간에서 10일이 제거됩니다.

## <a name="see-also"></a>참고 항목

[감소일 예시](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]