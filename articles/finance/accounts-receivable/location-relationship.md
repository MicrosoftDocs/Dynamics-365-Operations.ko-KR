---
title: 위치 및 당사자 관계 유형 추가
description: 이 항목에서는 새 위치 및 당사자 관계 유형을 추가하는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: a69ace892c55948305419a089cb91ac5b1e3c066177f8ce2ca441f1dd01c2af0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450295"
---
# <a name="add-location-and-party-relationship-types"></a>위치 및 당사자 관계 유형 추가 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>위치 역할 추가

주소 및 연락처 정보에 대한 새 위치 역할을 추가하는 방법에는 두 가지가 있습니다.

-  **주소 및 연락처 정보 목적** 페이지에서 추가합니다. 새 역할은 **LogisticsLocationRole** 테이블에 유형 = 0으로 저장됩니다. 이는 해당 역할이 **LogisticsLocationRoleType** 열거형 및 해당 확장에 정의된 시스템 역할이 아님을 나타냅니다. 사용자는 주소 또는 연락처 정보를 작성할 때 이 역할을 사용할 수 있습니다.

    ![주소 및 연락처 정보 목적.](media/Address-Contact.PNG)

-  **LogisticsLocationRoleType** 열거형 확장에 추가하고 데이터베이스 동기화 프로세스를 통해 채웁니다.

    1.  **LogisticsLocationRoleType** 열거형에 대한 확장을 만들고 확장에 새 역할을 추가합니다. 
  
        ![LogisticsLocationRoleType 열거형에 대한 확장.](media/Logistics.PNG)

    2. 새 역할에 대한 새 리소스 파일을 만든 다음 해당 속성에 값을 할당합니다.
     
     ![새 리소스 파일.](media/Resource.PNG)
        
    3.  데이터 채우기 클래스를 만들고 새 역할을 채우기 위한 처리기 메서드를 제공합니다. 

        ![데이터 채우기.](media/Dirdata.PNG)

    4.  새 위치 역할 채우기를 테스트하려면 실행 가능한 클래스를 만들고 Main()에서 DirDataPopulation::insertLogisticsLocationRoles()를 호출할 수 있습니다. 이 프로세스가 완료되면 **LogisticsLocationRole** 테이블에 유형 \> 0의 새 역할이 채워진 것을 볼 수 있습니다. 새 역할은 **주소 및 연락처 정보 목적** 페이지에 표시됩니다.

        ![새 위치를 삽입합니다.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>당사자 관계 유형 추가 

새 관계 유형을 추가하는 방법에는 두 가지가 있습니다.

-   **관계 유형** 페이지를 통해 추가합니다. 새 관계는 **DirRelationshipTypeTable** 에 systemtype = 0으로 저장됩니다.

    ![관계 유형.](media/Relationship.PNG)

-  **DirSystemRelationshipType** 열거형의 확장에 추가하고 데이터베이스 동기화 프로세스를 통해 채웁니다.

    1.  **DirSystemRelationshipType** 열거형에 대한 확장을 만들고 새 관계 유형을 추가합니다.

    2. 이 새 유형에 대한 이니셜라이저를 만듭니다. 핵심 코드에서 여러 예를 찾을 수 있으며 그중 하나가 **DirRelationshipTypeChildInitialize** 입니다. 이것은 당사자 관계 유형 "자식"의 이니셜라이저 클래스입니다. 이 코드를 복사하여 붙여넣고 이니셜라이저를 시작한 다음 강조 표시된 영역을 업데이트할 수 있습니다.
    
    ![DirRelationshipChild 이니셜라이저.](media/DirRelationship.PNG)

    3.  새 관계 유형 채우기를 테스트하려면 실행 가능한 클래스를 만들고 Main()에서 DirDataPopulation::insertDirRelationshipTypes()를 호출할 수 있습니다. **DirRelationshipTypeTable** 에 새 관계 유형이 표시되는 것을 볼 수 있고 **관계 유형** 페이지에서 새 관계 유형을 사용할 수 있습니다.

        ![실행 가능한 클래스.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]