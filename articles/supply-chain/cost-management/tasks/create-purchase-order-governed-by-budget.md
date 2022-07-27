---
title: 예산으로 관리되는 구매 주문 생성
description: 이 절차를 사용하여 사용 가능한 예산이 확인되는 구매 발주를 생성합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e2bfec4d7d38ef95d1f0ce3bd89938337ecf731
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448477"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>예산으로 관리되는 구매 주문 생성

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 사용 가능한 예산이 확인되는 구매 발주를 생성합니다. 이 레코딩은 데모 데이터 회사 USMF를 사용합니다.


## <a name="review-the-budget-control-configuration"></a>예산 통제 구성 검토
1. 예산 책정 > 설정 > 예산 관리 > 예산 관리 구성으로 이동합니다.
2. 사용 가능한 예산 탭을 클릭합니다.
3. 문서 및 분개 탭을 클릭합니다.
4. 예산 통제 규칙 정의 탭을 클릭합니다.
5. 예산 그룹 정의 탭을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="create-the-purchase-order-header"></a>구매 주문 헤더 생성
1. 조달 및 소싱 > 구매 주문 > 모든 구매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 공급업체 계정 필드에서 값을 입력하거나 선택합니다.
4. 일반 섹션을 확장합니다.
5. 회계 날짜 필드에서 날짜를 '2016-01-01'로 설정합니다.
6. 확인을 클릭합니다.

## <a name="add-a-purchase-order-line"></a>구매 주문 라인 추가
1. 조달 범주 필드에서 값을 입력하거나 선택합니다.
2. 수량을 '2'로 설정합니다.
3. 단위 필드에 값을 입력하거나 선택합니다.
4. 단가를 '10000'으로 설정합니다.
5. 재무를 클릭합니다.
6. 금액 분배를 클릭합니다.
7. 원장 계정 필드에 '601300-001-023--' 값을 지정합니다.
8. 페이지를 닫습니다.

## <a name="perform-budget-checking"></a>예산 확인 수행
1. 재무를 클릭합니다.
2. 예산 확인 수행을 클릭합니다.
3. 재무를 클릭합니다.
4. 예산 확인 오류 또는 경고를 클릭합니다.
5. 닫기를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]