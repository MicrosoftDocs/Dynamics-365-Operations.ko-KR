---
title: 회사 내 상품 이동을 위한 이전 문서 설정
description: 이 절차는 회사 내에서 상품 이동을 위한 이전 문서를 설정하는 방법을 보여줍니다.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80805bf30b4be753d7543ed4c6de30401d36e981
ms.sourcegitcommit: 2fba4f2ef7e513357366fc640befe0d2f7bc31f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "8451042"
---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>회사 내 상품 이동을 위한 이전 문서 설정

[!include [banner](../../includes/banner.md)]

이 절차는 회사 내에서 상품 이동을 위한 이전 문서를 생성하는 방법을 보여줍니다. 이 절차는 리투아니아의 기본 주소를 가진 법인만 사용할 수 있습니다. 이 절차는 리투아니아의 기본 주소를 가진 데모 데이터 회사 DEMF를 사용하여 생성되었습니다. 이 절차를 완료하려면 먼저 "회사 내에서 상품 이동을 위한 이전 문서 설정" 절차를 완료해야 합니다. 이 절차는 재고 회계사를 대상으로 합니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="create-a-transfer-order"></a>전송 순서 생성
1. 인벤토리 관리 > 인바운드 주문 > 전송 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 출발 창고 필드에 값을 입력하거나 선택합니다.
4. 도착 창고 필드에 값을 입력하거나 선택합니다.
5. 추가를 클릭합니다.
6. 목록에서 선택한 행을 표시합니다.
7. 항목 번호 필드에서 값을 입력하거나 선택합니다.

## <a name="enter-transportation-details-for-the-transfer-order"></a>이전 주문에 대한 운송 세부 정보 입력
1. 저장을 클릭합니다.
2. 작업 창에서 배송을 클릭합니다.
3. 운송 세부 정보를 클릭합니다.
4. 전송 세부 정보 인쇄 필드에서 예를 선택합니다.
5. 발급 기준 물품 필드에 값을 입력하거나 선택합니다.
6. 패키지 필드에 값을 입력합니다.
7. 하중 필드의 위험 수준에 값을 입력합니다.
8. 운송업체 필드에 값을 입력하거나 선택합니다.
9. 모델 필드에 값을 입력하거나 선택합니다.
10. 등록 번호 필드에 값을 입력합니다.
11. 트레일러 등록 번호 필드에 값을 입력합니다.
12. 운전자 필드에 값을 입력하거나 선택합니다.
13. 운전자 이름 필드에 값을 입력합니다.
14. 저장을 클릭합니다.
15. 페이지를 닫습니다

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>게시되지 않은 이전 주문에 대한 포장 전표 보기
1. 포장 전표를 클릭합니다.
2. 확인을 클릭합니다.
3. 페이지를 닫습니다

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>게시된 이전 주문에 대한 포장 전표 보기
1. 작업 창에서 이전 주문을 클릭합니다.
2. 작업 창에서 배송을 클릭합니다.
3. 이전 주문 배송을 클릭합니다.
4. 일반 탭을 클릭합니다.
5. 업데이트 필드에서 옵션을 선택합니다.
6. 개요 탭을 클릭합니다.
7. 포장 명세서 필드에 값을 입력합니다.
8. 확인을 클릭합니다.
9. 작업 창에서 배송을 클릭합니다.
10. 포장 전표를 클릭합니다.
11. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
