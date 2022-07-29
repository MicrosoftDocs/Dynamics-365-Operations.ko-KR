---
title: ER 수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가(2부 - 실행 형식)
description: 이번에는 보고서를 OPENXML 워크시트(Excel) 파일로 생성하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다. (2부)
author: NickSelin
ms.date: 08/29/2018
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
ms.openlocfilehash: 22a7b2ce07aa172ab759d6e18d34afd7aa21609acc7fe5fc691244b66c4379a6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460913"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER 수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가(2부 - 실행 형식)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER(전자 보고) 형식을 구성하여 보고서를 OPENXML 워크시트(Excel) 파일로 생성할 수 있는 방법을 설명합니다. 여기서 필요한 열은 수평 확장 가능한 범위로 동적으로 생성될 수 있습니다. 이러한 단계는 DEMF 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 가로로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가(1부: 디자인 형식)' 절차를 따릅니다.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="find-created-format"></a>생성된 형식 찾기
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '재무 차원 샘플 모델'을 확장합니다.
3. 트리에서 '재무 차원 샘플 모델\가로 확장 가능한 범위가 있는 샘플 보고서'를 선택합니다.

## <a name="execute-format-to-create-excel-output"></a>형식을 실행하여 Excel 출력 생성
1. 실행을 클릭합니다.
2. 차원 이름 필드에 'BusinessUnit;CostCenter;Department'를 입력합니다.
    * 차원 이름 필드에 값을 입력하거나 선택합니다.  현재 회사의 모든 차원을 선택하려면 다음을 입력합니다.  사업부;비용센터;부서;항목그룹;주계정;프로젝트  
3. 포함할 기록 섹션을 확장합니다.
4. 필터를 클릭합니다.
5. 원장 분개 테이블 및 분개 배치 번호 필드에 대한 행을 선택합니다.
6. 기준 필드에 '00057..00058'을 입력합니다.
    * 00057..00058  
7. '확인'을 클릭합니다.
8. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 새로 생성된 Excel 파일에는 재무 차원에 대해 선택한 것과 동일한 수의 열이 포함되어 있습니다. 해당 열의 보고서 머리글은 재무 차원의 이름을 나타냅니다. 해당 열의 거래 행은 재무 차원을 나타냅니다. 이 보고서를 실행하고 다른 차원을 선택하여 보고서가 선택한 차원 수 또는 이 인스턴스에 대해 구성된 차원 수에 종속되지 않는지 확인합니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]