---
title: 비용 개체 생성
description: 이 절차에서는 데이터 커넥터를 통해 비용 센터 재무 차원을 원가 회계로 가져와 비용 개체를 생성하는 방법을 보여줍니다.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0215e815e3e44568fb81ab7fad9b44c219e961cb6ef68996bf43218ef817e8d9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450676"
---
# <a name="create-cost-objects"></a>비용 개체 생성 

[!include [banner](../../includes/banner.md)]

이 절차에서는 데이터 커넥터를 통해 비용 센터 재무 차원을 원가 회계로 가져와 비용 개체를 생성하는 방법을 보여줍니다. USMF 데모 회사가 이 절차를 만드는 데 사용되었습니다. 


## <a name="create-new-cost-objects"></a>새 비용 개체 생성
1. 원가 회계 > 차원 > 비용 개체 차원으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
4. 차원 구성원용 데이터 커넥터 필드에서 값을 입력하거나 선택합니다.
5. 설명 필드에 값을 입력합니다.
6. 저장을 클릭합니다.

## <a name="configure-the-data-connector"></a>데이터 커넥터 구성
1. 차원 구성원 공급자 구성을 클릭합니다.
    * CostCenter를 선택하여 CostCenter 차원을 원가 회계로 가져옵니다.  
2. 차원 이름 필드에서 비용 센터를 선택합니다.
3. '확인'을 클릭합니다.

## <a name="import-cost-centers"></a>비용 센터 가져오기
1. 차원 구성원 가져오기를 클릭합니다.
2. '확인'을 클릭합니다.

## <a name="view-the-imported-cost-centers"></a>가져온 비용 센터 보기
1. 차원 구성원 보기를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]