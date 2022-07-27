---
title: 지급 계정에서 자산 생성 및 취득
description: 이 절차는 구매 프로세스와 함께 고정 자산의 생성 및 취득을 안내합니다.
author: saraschi2
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbac069362a15b5ab1d2dbf88a732a14a3cf709d
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450925"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>지급 계정에서 자산 생성 및 취득

[!include [banner](../../includes/banner.md)]

이 절차는 구매 프로세스와 함께 고정 자산의 생성 및 취득을 안내합니다.  회계사 및 지급 계정 직원과 데모 회사 USMF를 사용합니다.


## <a name="set-fixed-assets-parameters"></a>고정 자산 매개 변수 설정
1. **탐색 창** 에서 **모듈 > 고정 자산 > 설정 > 고정 자산 매개 변수** 로 이동합니다.
2. **구매 주문** 빠른 탭을 확장합니다.
3. **구매에서 자산 취득 허용** 확인란을 선택합니다.
4. **제품 수령 또는 송장 전기 중 자산 생성** 확인란을 선택합니다.

## <a name="create-a-new-vendor-invoice"></a>새 공급업체 송장 만들기
1. **탐색 창** 에서 **모듈 > 지급 계정 > 작업 영역 > 공급업체 송장 입력** 으로 이동합니다.
2. **새 공급업체 송장** 을 클릭합니다.
3. **송장 계정** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. **번호** 필드에 값을 입력합니다.
6. **전기 날짜** 필드에 날짜를 입력합니다.
7. **라인 추가** 를 클릭합니다.
8. **항목 번호** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다. 비재고 품목 또는 조달 범주를 고정 자산 취득에 사용할 수 있습니다.  
9. 목록에서 선택한 행의 링크를 클릭합니다.
10. **수량** 필드에 숫자를 입력합니다. 하나의 송장 라인은 수량에 관계없이 하나의 고정 자산만 생성합니다. 송장 수량 필드 값은 고정 자산 수량으로 이전됩니다.  
11. **단가 필드** 에 숫자를 입력합니다.
12. **라인 세부 정보** 빠른 탭을 확장합니다.
13. **고정 자산** 탭을 클릭합니다.
14. **새 고정 자산 생성** 확인란을 선택합니다.
15. **고정 자산 그룹** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
16. 목록에서 새 고정 자산을 생성할 때 사용할 고정 자산 그룹을 선택합니다.
17. 목록에서 선택한 행의 링크를 클릭합니다.
18. **전기** 를 클릭합니다. 고정 자산은 송장이 전기될 때 생성 및 취득됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
