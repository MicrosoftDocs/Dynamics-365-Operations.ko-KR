---
title: ER 계산 및 합산을 수행하는 형식 구성(1부 - 형식 만들기)
description: 이번에는 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (1부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d1a90c0949e98b4c1e9ccb356d39de9c23b670c518ad14a99974ae2aed7301
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460888"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER 계산 및 합산을 수행하는 형식 구성(1부 - 형식 만들기)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 '구성 공급자를 만들고 활성으로 표시' 절차의 단계를 완료해야 합니다.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 구성 목록에 액세스
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
    * 'Litware, Inc.' 공급자를 사용할 수 있으며 활성으로 표시됩니다.  
2. 'Litware, Inc.' 공급자를 선택합니다.
3. 저장소를 클릭합니다.
    * '작업 리소스' 유형의 저장소가 이미 있는 경우 현재 하위 작업의 나머지 단계를 건너뜁니다.  
4. 추가를 클릭하여 드롭 대화 상자를 엽니다.
5. 구성 리포지토리 유형 필드에 '작업 리소스'를 입력합니다.
6. 리포지토리 만들기를 클릭합니다.
7. '확인'를 클릭합니다.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 Intrastat 구성 가져오기
1. 열기를 클릭합니다.
2. 트리에서 'Intrastat 모델\Intrastat(DE)'를 선택합니다.
3. 가져오기를 클릭합니다.
    * 선택한 구성의 버전 1.1에 대해 가져오기를 클릭합니다.  
4. 예를 클릭합니다.
5. 페이지를 닫습니다.
6. 페이지를 닫습니다.
7. 보고 구성을 클릭합니다.
8. 트리에서 'Intrastat 모델'을 확장합니다.
9. 트리에서 'Intrastat 모델\Intrastat(DE)'를 선택합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]