---
title: 서비스 작업 관계 만들기
description: 계약 또는 주문에 대해 완료할 서비스 작업을 설명하기 위해 서비스 작업을 서비스 계약 또는 서비스 주문과 연결할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b13309816af6984e77f828e827ecffe6266b3ede
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448918"
---
# <a name="create-service-task-relations"></a>서비스 작업 관계 만들기    

[!include [banner](../includes/banner.md)]

계약 또는 주문에 대해 완료할 서비스 작업을 설명하기 위해 서비스 작업을 서비스 계약 또는 서비스 주문과 연결할 수 있습니다. 이 정보는 서비스 기술자와 고객이 사용할 수 있습니다.

## <a name="create-a-relation-with-a-service-agreement"></a>서비스 계약을 통해 관계 만들기

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 으로 이동합니다.

2.  기존 서비스 계약을 선택하거나 새 서비스 계약을 생성합니다.

3.  작업 창에서 **서비스 작업** 단추를 선택합니다.

4.  **서비스 작업** 양식에서 **새로 만들기** 를 선택하여 새 줄을 만든 다음 서비스 작업 목록에서 **서비스 작업** 을 선택하여 서비스 작업을 서비스 계약에 첨부합니다.

5.  **설명** 탭에서 자유 텍스트 필드에 내부 또는 외부 메모 설명을 입력합니다.

6.  레코드를 저장하려면 양식을 닫습니다.

서비스 계약에 필요한 모든 서비스 작업 관계를 생성할 때까지 이 절차를 반복합니다. 이제 첨부된 모든 계약 라인에 대해 이러한 서비스 작업을 지정할 수 있습니다.

서비스 계약에 생성된 서비스 작업 관계는 서비스 계약에 첨부된 모든 서비스 주문에서 사용할 수 있습니다.

## <a name="create-a-relation-with-a-service-order"></a>서비스 주문을 통해 관계 만들기

1.  **서비스 관리** \> **일반** \> **서비스 주문** \> **서비스 주문** 으로 이동합니다.

2.  기존 서비스 주문을 선택하거나 새 서비스 주문을 생성합니다.

3.  작업 창에서 **서비스 작업** 단추를 선택합니다.

4.  **서비스 작업** 양식에서 **새로 만들기** 를 선택하여 새 줄을 만든 다음 서비스 작업 목록에서 **서비스 작업** 을 선택하여 서비스 작업을 서비스 주문에 첨부합니다.

5.  **설명** 탭에서 자유 텍스트 필드에 내부 또는 외부 메모 설명을 입력합니다.

6.  레코드를 저장하려면 양식을 닫습니다.

서비스 주문에 필요한 모든 서비스 작업 관계를 생성할 때까지 이 절차를 반복합니다. 이제 서비스 주문 라인을 생성할 때 관계를 생성한 서비스 작업를 선택할 수 있습니다.

서비스 주문에서 생성된 서비스 작업 관계는 특정 서비스 주문에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[서비스 작업 개요](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]