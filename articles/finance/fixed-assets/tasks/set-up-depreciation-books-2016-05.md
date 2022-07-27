---
title: 감가상각 장부 설정
description: 이 절차는 새 감가상각 장부를 만들고 고정 자산 그룹과 연결하는 프로세스를 안내합니다.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 42b8a15ac60fd2620c600d78b84a25e3caf6d2bf
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451255"
---
# <a name="set-up-depreciation-books"></a>감가상각 장부 설정 

[!include [banner](../../includes/banner.md)]

이 절차는 새 감가상각 장부를 만들고 고정 자산 그룹과 연결하는 프로세스를 안내합니다. 

## <a name="create-a-depreciation-book"></a>감가상각 장부 만들기
1. 고정 자산 > 설정 > 감가상각 장부로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 감가상각 장부 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 감가상각 계산 확인란을 선택하거나 선택 취소합니다.
6. 감가상각 프로필 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
7. 목록에서 원하는 감가상각 프로필을 찾아 선택합니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
9. 대체 감가상각 프로필 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
10. 목록에서 원하는 감가상각 프로필을 선택합니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
    * 특별 감가상각 프로필은 비정상적인 상황에서 자산의 추가 감가상각에 사용됩니다. 예를 들어, 이것을 사용하여 자연 재해로 인한 감가상각을 기록할 수 있습니다.  
12. 기준 조정을 사용하여 감가상각 조정 만들기 확인란을 선택하거나 선택 취소합니다.
13. 달력 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
14. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>감가상각 장부를 고정 자산 그룹 연결
1. 고정 자산 그룹을 클릭합니다.
2. 고정 자산 그룹 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 감가상각 규칙 필드에서 옵션을 선택합니다.
6. 사용 수명 필드에 숫자를 입력합니다.
    * 감가상각 기간 필드 값은 사용 수명을 설정한 후 계산됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
