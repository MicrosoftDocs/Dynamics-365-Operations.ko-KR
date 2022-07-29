---
title: (ER) RCS에서 구성 가져오기
description: 이 항목에서는 사용자가 RCS에서 ER 구성의 새 버전을 가져오는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5674c418baaac7817c27780e2f0137ce6e7137eb3f1665f768ad843cc5b3114
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460879"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) RCS에서 구성 가져오기

[!include [banner](../../includes/banner.md)]

다음 단계는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 Microsoft Regulatory Configuration Services(RCS)에서 전자 보고(ER) 구성의 새 버전을 가져오는 방법을 설명합니다. 이 예에서는 RCS 인스턴스에 구성된 ER 구성 버전을 선택하고 샘플 회사 Litware, Inc.의 현재 인스턴스로 가져옵니다. 이 단계는 ER 구성이 회사 간에 공유되므로 모든 회사에서 수행할 수 있습니다. 이러한 단계를 완료하려면 RCS에서 [구성 공급자를 만들고 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md) 토픽의 절차를 완료해야 합니다. 이 단계를 완료하려면 **완료됨** 또는 **공유됨** 상태의 ER 구성이 포함된 RCS 인스턴스에 대한 액세스 권한도 있어야 합니다.

1. **조직 관리** > **작업 영역** > **전자 보고** 로 이동합니다. 
2. 샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 **활성** 으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 [구성 공급자를 만들고 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md) 토픽의 단계를 완료하세요. 
3. 회사에 프로비저닝된 RCS 환경이 없는 경우 **Regulatory services – 구성** 외부 링크로 이동하고 지침에 따라 RCS 환경을 프로비저닝합니다. 
4. **전자 보고 매개 변수** 를 선택합니다. 
5. **RCS** 탭을 선택합니다. 
6. RCS 환경이 이미 회사에 프로비저닝되어 있는 경우 페이지에 표시된 URL을 사용하여 액세스합니다. 
7. 페이지를 닫습니다. 

## <a name="register-a-new-er-repository"></a>새 ER 리포지토리를 등록합니다. 
1. 목록에서 선택한 행을 표시합니다. 
2. Litware, Inc. 공급자를 선택합니다. 
3. 리포지토리를 선택합니다. 
4. 추가를 선택하여 드롭 대화 상자를 엽니다. 
5. 구성 리포지토리 유형 필드에서 'RCS'를 입력합니다. 
6. 리포지토리 생성을 선택합니다. 
7. RCS 환경 표시 이름 필드에 값을 입력하거나 선택합니다. 
8. 원하는 RCS 인스턴스를 선택합니다. 이 중 몇 가지를 가질 수 있습니다. 
9. 확인을 선택합니다. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>RCS 기반 리포지토리에서 ER 구성 가져오기
1. **필터 표시** 를 선택합니다. 
2. **begins with** 필터 연산자를 사용하여 **이름** 필드에 "RCS"의 필터 값을 입력합니다. 
3. 선택한 저장소를 열면 **Regulatory Configuration Services에 연결** 페이지에서 **Regulatory Configuration Services에 연결하려면 여기를 선택** 링크를 선택합니다. 
4. **열기** 를 선택합니다. 
5. **닫기** 를 선택합니다. 
6. 원하는 ER 구성 버전을 선택하고 **가져오기** 를 선택하여 현재 인스턴스로 가져옵니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]