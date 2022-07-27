---
title: 생산 주문 생성
description: 이 절차에서는 생산 주문을 만드는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb7eb237758acb6f27c636050fa5a74d1fd758f1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449341"
---
# <a name="create-a-production-order"></a>생산 주문 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 생산 주문을 만드는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 생산 주문 수명 주기를 설명하는 7가지 중 첫 번째 절차입니다.


## <a name="create-a-production-order"></a>생산 주문 생성
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
2. 새로운 생산 주문을 클릭합니다.
3. 품목 번호 필드에 'D0001'을 입력합니다.
4. 배달 필드에 날짜를 입력합니다.
    * 배송 날짜는 정시에 배송하기 위해 생산 주문이 종료되어야 하는 시간을 나타냅니다. 이 날짜는 스케줄링 프로세스에서 사용할 수 있습니다. 예를 들어, 배송 날짜로부터 뒤로 주문을 예약할 수 있습니다.  
5. 수량을 '20'으로 설정합니다.
    * 참고: BOM 번호 필드에는 현재 품목에 대한 활성 BOM의 번호가 자동으로 표시되지만 승인된 BOM 버전 목록에서 활성 BOM을 선택하여 생산 오더에 대한 BOM을 변경할 수 있습니다.    경로 번호 필드에는 현재 품목에 대한 활성 경로의 번호가 자동으로 표시되지만 승인된 경로 버전 목록에서 활성 경로를 선택하여 생산 오더에 대한 경로를 변경할 수 있습니다.  
6. 만들기를 클릭합니다.

## <a name="validate-the-production-order"></a>생산 주문 유효성 검사
1. 목록에서 선택한 행의 링크를 클릭합니다.
    * 방금 생성한 생산 주문 번호에 대한 링크를 클릭합니다. 그러면 주문에 대한 세부 정보 페이지가 열립니다.  
2. 편집을 클릭합니다.
3. 배달 필드에 날짜를 입력합니다.
    * 예를 들어, 생산 주문의 배송 날짜를 변경할 수 있습니다.  
4. 저장을 클릭합니다.
5. 페이지를 닫습니다.

## <a name="update-the-bom"></a>BOM 업데이트
1. 작업 창에서 생산 주문을 클릭합니다.
2. BOM을 클릭합니다.
    * BOM 페이지를 열어 생산 오더가 생성될 때 기본 데이터에서 복사된 BOM 데이터를 검증합니다. 이 절차에서는 BOM의 수량을 업데이트해야 합니다.  
3. 편집을 클릭합니다.
4. 수량 필드에 숫자를 입력합니다.
    * BOM 라인의 수량을 변경하면 생산 오더에 대한 자재 소비 비용 추정에 영향을 줍니다.  
5. 저장을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="update-the-production-route"></a>생산 경로 업데이트
1. 작업 창에서 생산 주문을 클릭합니다.
2. 경로를 클릭합니다.
    * 경로 페이지를 열어 주문이 생성될 때 기본 데이터에서 복사된 생산 경로의 데이터를 검증합니다. 이 절차에서는 생산 경로의 작업 중 하나에 대한 수량을 업데이트해야 합니다.  
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 편집을 클릭합니다.
5. 절차 수량 필드에 숫자를 입력합니다.
    * 프로세스 시간을 변경하면 예상 경로 소비와 생산 주문 비용에 영향을 줍니다.  
6. 저장을 클릭합니다.
7. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]