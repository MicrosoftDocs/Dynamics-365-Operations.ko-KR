---
title: 파티 데이터 모델이 있는 Microsoft Power Apps 포털 사용
description: 이 항목에서는 이중 쓰기의 당사자 데이터 모델로 인한 Microsoft Power Apps 포털의 웹 역할에 대한 변경 사항에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8242a74b8b2251a8489b772f5c4746b113fe2987
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461021"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>파티 데이터 모델이 있는 Microsoft Power Apps 포털 사용

[!INCLUDE[banner](../../includes/banner.md)]



이중 쓰기 애플리케이션 오케스트레이션 솔루션 버전 2.0.999.0 이상에는 계정 및 연락처 테이블에 대한 당사자 및 전체 주소록에 대한 데이터 모델 변경 사항이 포함됩니다. 변경 사항은 고급 비즈니스 시나리오를 지원하는 다대다 관계를 허용합니다. 이러한 변경 사항은 기본 제공되거나 이중 쓰기를 설치하기 전에 환경에 존재했던 고객 포털을 포함하여 포털 웹 역할에서 지원되지 않습니다. 웹 역할이 예상대로 작동하려면 새 데이터 모델을 사용하여 새 웹 역할을 생성해야 합니다. 

요약하면 테이블이 상호 작용하는 방식이 변경되었지만 고객 포털의 테이블 권한은 변경되지 않았습니다. 이 항목에서는 새 고급 데이터 모델과 함께 작동하는 새 웹 역할을 만드는 방법에 대해 설명합니다.

이 다이어그램은 파티 및 전체 주소록 데이터 모델이 **없는** 테이블 관계를 보여줍니다.

   ![파티 모델 없이.](media/without-party-model.PNG)

이 다이어그램은 파티 및 전체 주소록 데이터 모델이 **있는** 테이블 관계를 보여줍니다.

   ![파티 모델 있음.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>새 테이블 권한 생성

이러한 새 테이블 권한을 생성하려면 다음 단계를 따르세요.

1. [Power Apps](https://make.powerapps.com)에 로그인하고 앱으로 이동합니다.
2. 포털 관리 앱을 선택합니다.
3. 사이드바에서 **보안 > 테이블 권한** 을 선택합니다.

    다음 세 가지 권한을 새로 생성해야 합니다.

    + **연락처** 에서 **파티** 테이블 연결
    + **파티** 에서 **계정** 테이블 연결
    + **계정** 에서 **주문** 테이블 연결

4. 연락처 대 당사자 연결에 대한 새 권한을 만들고 저장하고 다음 매개변수를 설정합니다.

    + **이름**: **파티** 에서 **계정** 테이블 연결(또는 귀하의 선택)
    + **테이블 이름**: msdyn_contactforparty
    + **웹 사이트**: 고객 포털
    + **범위**: 연락처
    + **권한**: 모두 선택
    + **웹 역할**: 인증된 사용자, 고객 대리인(또는 귀하의 선택)

5. 파티 대 계정 연결에 대한 새 권한을 만들고 저장하고 다음 매개변수를 설정합니다.

    + **이름**: 파티에서 계정(또는 귀하의 선택)
    + **테이블 이름**: 계정
    + **웹 사이트**: 고객 포털
    + **범위**: 부모
    + **권한**: 모두 선택
    + **상위 테이블 권한**: 연락처 대 파티 연결

6. 계정 대 주문 연결에 대한 새 권한을 만들고 저장하고 다음 매개변수를 설정합니다.

    + **이름**: 계정에서 주문(또는 귀하의 선택)
    + **테이블 이름**: salesorder
    + **웹 사이트**: 고객 포털
    + **범위**: 부모
    + **권한**: 모두 선택
    + **상위 테이블 권한**: 파티 대 계정 연결

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
