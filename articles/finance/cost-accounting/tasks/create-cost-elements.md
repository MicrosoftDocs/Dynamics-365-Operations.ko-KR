---
title: 비용 요소 생성
description: 원가 회계에서 비용 요소를 생성하는 방법에는 여러 가지가 있습니다.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba36e8d2c5b1fc1df6e63e5eef20c465cbd0b693086eece4079ae2216d2c156e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450658"
---
# <a name="create-cost-elements"></a>비용 요소 생성 

[!include [banner](../../includes/banner.md)]

원가 회계에서 비용 요소를 생성하는 방법에는 여러 가지가 있습니다. 이 절차는 데이터 커넥터를 통해 기본 계정을 가져와 비용 요소를 생성하는 방법을 보여줍니다. USMF 데모 회사가 이 절차를 만드는 데 사용되었습니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 원가 회계 기능에 대한 것입니다.


## <a name="create-new-cost-elements"></a>새로운 비용 요소 생성
1. 원가 회계 > 차원 > 비용 요소 차원으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
4. 차원 구성원용 데이터 커넥터 필드에서 값을 입력하거나 선택합니다.
5. 설명 필드에 값을 입력합니다.
6. 저장을 클릭합니다.

## <a name="configure-the-data-connector"></a>데이터 커넥터 구성
1. 차원 구성원 공급자 구성을 클릭합니다.
2. 계정 차트 필드에서 값을 입력하거나 선택합니다.
    * 공유 계정 차트를 사용하려면 공유를 선택합니다.  
3. 새로 만들기를 클릭합니다.
4. 목록에서 선택한 행을 표시합니다.
    * 기준에 맞게 계정에 필터를 적용할 수 있습니다.  
5. 원본 주 계정 필드에서 값을 입력하거나 선택합니다.
6. 대상 주 계정 필드에서 값을 입력하거나 선택합니다.
7. '확인'을 클릭합니다.

## <a name="import-main-accounts"></a>주 계정 가져오기
1. 차원 구성원 가져오기를 클릭합니다.
    * 주 계정을 원가 회계로 가져와 비용 요소로 사용합니다.  
2. '확인'을 클릭합니다.

## <a name="view-the-imported-accounts-as-cost-elements"></a>가져온 계정을 비용 요소로 보기
1. 차원 구성원 보기를 클릭합니다.
    * 가져온 원장 계정을 비용이 유입될 수 있는 비즈니스의 비용 요소로 봅니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]