---
title: 고정 자산 이전
description: 이 작업 가이드는 고정 자산 장부에 대한 재무 정보를 한 재무 차원 집합에서 새 재무 차원 집합으로 이전합니다.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e573386ddbb97bf60e2e501ba92b225f8716c73a
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451213"
---
# <a name="transfer-a-fixed-asset"></a>고정 자산 이전

[!include [banner](../../includes/banner.md)]

이 작업 가이드는 고정 자산 장부에 대한 재무 정보를 한 재무 차원 집합에서 새 재무 차원 집합으로 이전합니다.  

1. 탐색 창에서 **모듈 > 고정 자산 > 고정 자산 > 고정 자산** 으로 이동합니다.
2. 목록에서 이전할 고정 자산을 찾아 선택합니다.
3. 작업 창에서 **고정 자산** 을 클릭합니다.
4. **고정 자산 이전** 을 클릭합니다.
5. **이전 날짜** 필드에 날짜를 입력합니다.
6. 이전을 설명하는 코멘트를 입력합니다.
    
    이 목록에는 고정 자산에 대한 모든 장부가 표시됩니다.  
7. 새로운 재무 차원 집합으로 이전할 장부를 표시합니다.
    * 이 목록에는 선택한 장부의 기존 재무 차원 값이 표시됩니다.  
    * 선택한 고정 자산 장부에 대해 업데이트할 재무 차원을 선택합니다.  
8. **재무 차원** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 다른 재무 차원 값을 적절하게 설정합니다.  
    * 모든 재무 차원 값은 입력되거나 비어 있는지와 관계없이 이전이 발생하면 변경됩니다. 예를 들어 BusinessUnit에 값을 입력하고 CostCenter 및 Department 재무 차원을 비워둘 수 있습니다. 계정 구조에서 CostCenter 및 Department에 빈 값을 허용하는 경우 이전하면 각 값 모델에 BusinessUnit에 새 값과 CostCenter 및 Department에 빈 값이 있게 됩니다.  
9. **업데이트** 를 클릭합니다.
    * 이전을 완료하기 전에 변경 사항을 미리 볼 수 있습니다.  
    * 고정 자산 장부를 이전하기 전에 결과를 검토합니다.  
10. **이전** 을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
