---
title: 비용 개체 컨트롤러에 대한 액세스 권한 구성
description: 이 절차를 사용하여 비용 개체 컨트롤러에 대한 액세스 권한을 구성합니다.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70428b653f1263f5c753e0c2d756238b647fe4ba657add467a0142369bbbdd8b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450850"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>비용 개체 컨트롤러에 대한 액세스 권한 구성

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 비용 개체 컨트롤러에 대한 액세스 권한을 구성합니다. 이 레코딩은 USP2 데모 데이터 회사를 사용합니다.


## <a name="assign-the-cost-object-controller-role"></a>비용 개체 컨트롤러 역할 할당
1. 시스템 관리 > 사용자 > 사용자로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어, 값이 'alicia'인 사용자 이름 필드를 필터링합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 역할 할당을 클릭합니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
6. '확인'을 클릭합니다.

## <a name="enable-access-list-security"></a>액세스 목록 보안 사용
1. 원가 회계 > 차원 > 차원 계층으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 조직을 선택합니다.  
3. 편집을 클릭합니다.
4. 액세스 목록 계층 필드에서 예를 선택합니다.
5. 계층 보기를 클릭합니다.

## <a name="assign-access-rights-to-user"></a>사용자에게 액세스 권한 할당
1. 새로 만들기를 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
3. 사용자 ID 필드에 값을 입력하거나 선택합니다.
    * 관리자를 선택합니다.  
4. 트리에서 'Organization\CEO\CFO\FIM'을 선택합니다.
5. 새로 만들기를 클릭합니다.
6. 목록에서 선택한 행을 표시합니다.
7. 사용자 ID 필드에 값을 입력하거나 선택합니다.
    * Alicia를 선택합니다.  
8. 저장을 클릭합니다.

## <a name="enable-access-rights-in-cost-accounting"></a>비용 회계에서 액세스 권한 활성화
1. 원가 회계 > 설정 > 매개 변수로 이동합니다.
2. 일반 탭을 클릭합니다.
3. 비용 개체 차원 구성원 필드에 대한 보기 액세스 활성화에서 예를 선택합니다.
4. 저장을 클릭합니다.
5. 페이지를 닫습니다.
6. 비용 회계 > 설정 > 원가 관리 작업 영역 구성으로 이동합니다.
7. 편집을 클릭합니다.
8. 게시 필드에서 예를 선택합니다.
    * 예를 선택하면 다음 네 가지 역할 중 하나가 할당된 사용자가 원가 관리 작업 영역에서 보고서를 볼 수 있습니다: 원가 회계 관리자, 원가 회계사, 원가 회계 직원 및 원가 개체 컨트롤러. 아니오를 선택하면 다음 역할 중 하나가 할당된 사용자만 보고서를 볼 수 있습니다: 원가 회계 관리자, 원가 회계사, 원가 회계 직원 및 원가 개체 컨트롤러.    
9. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]