---
title: 법인 전체의 고정 자산 감가상각 계산
description: 고정 자산 감가상각은 단일 단계로 법인 전체에서 실행할 수 있습니다.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 769e271ec9bb202ca695e5430c79e66f7320838fdfd232bab7c72ce5816a7b05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450478"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>법인 전체의 고정 자산 감가상각 계산

[!include [banner](../../includes/banner.md)]

고정 자산 감가상각은 단일 단계로 법인 전체에서 실행할 수 있습니다. 이 절차는 여러 법인에 대한 프로세스를 설정하고 실행하는 방법을 보여줍니다. 이 절차에서는 USMF 법인에 대한 회계사 역할과 데모 데이터를 사용합니다.


## <a name="set-up-cross-company-depreciation-run-journals"></a>회사 간 감가상각 실행 분개장 설정
1. 고정 자산 > 설정 > 고정 자산 매개 변수로 이동합니다.
2. 고정 자산 제안 섹션을 확장합니다.
3. 추가를 클릭합니다.
4. 포스팅 레이어 필드에 값을 입력하거나 선택합니다.
5. 분개장 이름 필드에 값을 입력하거나 선택합니다.
    * 각 법인의 고정 자산 매개 변수 페이지에서 분개장 설정을 반복합니다.  

## <a name="depreciation-run"></a>감가상각 실행
1. 고정 자산 > 분개장 항목 > 감가상각 제안 생성으로 이동합니다.
2. 포스팅 레이어 필드에 값을 입력하거나 선택합니다.
    * 분개장 이름은 고정 자산 매개 변수의 기본값이 됩니다. 현재 법인에 대해 여기에서 변경할 수 있습니다.  
3. 종료 날짜 필드에 날짜를 입력합니다.
    * 감가상각 실행에 포함할 법인을 선택합니다.  
    * 고정 자산 매개 변수 페이지에서 고정 자산 제안에 대해 설정된 분개장이 있는 법인만 목록에 표시됩니다.  
4. 분개장 전기 필드에서 예를 선택합니다.
    * 필터링 필드에는 이 감가상각 실행에 대해 선택한 법인에 대한 모든 고정 자산, 그룹 및 장부가 포함됩니다.  
    * 배치 프로세싱 옵션은 기본적으로 활성화되어 있습니다. 이 옵션이 활성화되면 감가상각 분개장 생성 및 전기가 백그라운드에서 실행됩니다.  
5. 분개장 생성을 클릭합니다.
6. 고정 자산 > 분개 항목 > 고정 자산 분개장으로 이동합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]