---
title: 보너스 감가상각 설정
description: 이 절차는 특수 감가상각 허용값을 만들고 고정 자산 장부와 연결하는 방법을 보여줍니다.
author: moaamer
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bfa433c07a2acb37c8e73dfa5db7d1e1715cd1d
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451252"
---
# <a name="set-up-bonus-depreciation"></a>보너스 감가상각 설정

[!include [banner](../../includes/banner.md)]

이 절차는 특수 감가상각 허용값을 만들고 고정 자산 장부와 연결하는 방법을 보여줍니다. 이 절차에서는 USMF 법인에 대한 회계사 역할과 데모 데이터를 사용합니다.


## <a name="create-a-special-depreciation-allowance"></a>특수 감가상각 허용값 만들기
1. 고정 자산 > 설정 > 특수 감가상각 허용값으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 특수 감가상각 허용값 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 백분율 필드에 숫자를 입력합니다.
    * 백분율이 지정되지 않은 경우 금액을 설정합니다.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>고정 자산 그룹 장부에 특수 감가상각 허용값 연결
1. 고정 자산 > 설정 > 고정 자산 그룹으로 이동합니다.
2. 목록에서 특수 감가상각 허용값과 연결된 고정 자산 그룹을 선택합니다.
3. 장부를 클릭합니다.
4. 목록에서 특수 감가상각 허용값과 연결된 장부를 선택합니다.
5. 특수 감가상각 허용값을 클릭합니다.
6. 새로 만들기를 클릭합니다.
7. 특수 감가상각 허용값 필드에 값을 입력하거나 선택합니다.
    * 백분율 또는 금액의 기본값은 특수 감가상각 허용값 설정에서 가져옵니다.  
8. 우선순위 필드에 숫자를 입력합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
