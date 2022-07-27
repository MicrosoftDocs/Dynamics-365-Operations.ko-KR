---
title: 원래 예산을 생성한 다음 공공 부문의 예비 예산 입력을 취소합니다
description: 이 항목에서는 예비 예산 금액이 있는 예산 모델 및 차원 값을 사용하여 원래 예산 입력을 생성하고 취소하는 방법에 대한 정보를 제공합니다.
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7758a1c9edfa129ba8b63a146b38ed3f119fd051
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8451570"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a>원래 예산을 생성한 다음 공공 부문의 예비 예산 입력을 취소합니다

[!include [banner](../../includes/banner.md)]

원래 예산 항목을 생성하고 예비 예산 금액이 포함된 예산 모델 및 차원 값을 사용하는 경우 예비 예산 금액을 취소할 수 있습니다. 이 절차는 공공 부문 파티션의 PSUS 데모 회사 데이터를 사용하여 작성되었습니다.

1. **예산 편성 > 예산 등록 항목** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **예산 모델** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. **예산 코드** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 **원래 예산** 을 클릭합니다.
7. **저장** 을 클릭합니다.
8. **라인 추가** 를 클릭합니다.
9. 선택 사항: 헤더에 있는 날짜에서 날짜를 변경하려면 새 날짜를 입력합니다. 이 날짜는 예산이 기록될 회계 기간을 결정합니다.
10. **계정 구조** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
11. 목록에서 원하는 레코드를 찾아 선택합니다.
12. **차원 값** 필드에서 원하는 값을 지정합니다.
13. **금액** 필드에 숫자를 입력합니다.
14. **통화** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
15. 목록에서 선택한 행의 링크를 클릭합니다.
16. **저장** 을 클릭합니다.
17. **예산 잔액 업데이트** 를 클릭합니다.
    * 선택 사항: **예비 예산 취소** 옵션을 선택할 수 있습니다. 모든 예비 예산 입력을 취소하거나 지정한 예산 코드가 있는 예비 예산 입력만 취소할 수 있습니다.  
    * 옵션을 선택하려면 **잠금 해제** 아이콘을 클릭합니다.  
18. **업데이트** 를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
