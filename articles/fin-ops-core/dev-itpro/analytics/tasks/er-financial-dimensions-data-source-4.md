---
title: ER 재무 차원을 데이터 소스로 사용(4부 - 보고서 실행)
description: 이번에는 재무 차원을 ER 보고서의 데이터 소스로 사용하도록 전자 보고(ER) 모델을 구성하는 방법에 대해 설명합니다. (4부)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f14be560ab014224e32169b4ac97682a669249b4
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460889"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER 재무 차원을 데이터 소스로 사용(4부 - 보고서 실행)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 재무 차원을 ER 보고서의 데이터 소스로 사용하도록 전자 보고(ER) 모델을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 DEMF 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 재무 차원을 데이터 소스로 사용(3부: 보고서 디자인)' 절차를 따르십시오. 전자 보고 매개 변수 페이지에서 기본 문서 유형도 구성해야 합니다. ER 구성을 다운로드하고 가져올 때도 기본 문서 유형이 설정됩니다. 


## <a name="run-report"></a>보고서 실행
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '재무 차원 샘플 모델'을 확장합니다.
3. 트리에서 '재무 차원 샘플 모델\원장 분개 보고서'를 선택합니다.
4. 실행을 클릭합니다.
![ER 구성 페이지.](../media/er-financial-dimensions-guides-run1.png)
5. 차원 이름 필드에 값을 입력하거나 선택합니다.
    * 현재 회사의 모든 차원을 선택하려면 다음 정보를 입력합니다.  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![전자 보고서 매개 변수 슬라이드 아웃, 차원 이름 드롭다운](../media/er-financial-dimensions-guides-run2.png)
6. 포함할 기록 섹션을 확장합니다.
7. 필터를 클릭합니다.
8. 원장 분개 테이블 및 분개 배치 번호 필드에 대한 행을 선택합니다.
9. 기준 필드에 '00057'을 입력합니다.
10. '확인'을 클릭합니다.
11. '확인'을 클릭합니다.
![전자 보고서 매개 변수 슬라이드 아웃, 보고서 포함 섹션.](../media/er-financial-dimensions-guides-run3.png)
    * 생성된 출력을 검토합니다. 선택한 배치의 각 트랜잭션에 대해 해당 차원 집합의 재무 차원이 표시됩니다. 이 보고서를 실행하고 다른 차원을 선택하여 보고서가 선택한 차원 수 또는 이 인스턴스에 대해 구성된 차원 수에 종속되지 않는지 확인합니다.  
![ER 구성이 출력을 생성했습니다.](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
