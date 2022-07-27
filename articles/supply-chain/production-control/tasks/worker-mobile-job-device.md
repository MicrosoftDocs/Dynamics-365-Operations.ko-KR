---
title: 모바일 작업 디바이스를 사용하여 작업자 구성
description: 이 토픽에서는 작업자의 사용자 계정에 올바른 역할을 할당한 다음 작업자가 작업 현장 등록을 수행할 수 있도록 하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d9745995752c06385acc31e529de52eefaa6f96
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448627"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>모바일 작업 디바이스를 사용하여 작업자 구성

[!include [banner](../../includes/banner.md)]

이 토픽에서는 작업자의 사용자 계정에 올바른 역할을 할당한 다음 작업자가 작업 현장 등록을 수행할 수 있도록 하는 방법에 대해 설명합니다.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>작업자에게 특정 역할이 할당되었는지 확인

이 예의 경우 작업자 계정을 구성하기 전에 사용자 "SHANNON"에게 기계 운영자 역할이 할당되었는지 확인합니다.

1. **탐색 창 > 모듈 > 시스템 관리 > 사용자 > 사용자** 로 이동합니다.
2. 빠른 필터에서 사용자를 검색합니다. 이 예에서는 `shannon`을 입력합니다.
3. 표시되는 사용자 계정의 **사용자 ID** 열에서 링크를 선택합니다.
4. **사용자 역할** 트리에서 **역할 > 머신 운영자** 를 선택합니다.
5. 홈 페이지로 돌아가려면 **사용자 세부 정보** 및 **사용자** 페이지를 닫습니다.

## <a name="configure-worker-account"></a>작업자 계정 구성
1. **탐색 창 > 모듈 > 인적 자원 > 작업자 > 작업자** 로 이동합니다.
2. 빠른 필터에서 사용자를 검색합니다. 이 예에서는 `shannon`을 입력합니다.
3. 표시되는 사용자 계정의 **이름** 열에서 링크를 선택합니다.
4. **시간 등록** 탭을 선택합니다.
5. **등록 터미널에서 활성화** 를 선택합니다.
6. 다음 필드에 값을 입력하거나 선택합니다.  

    - **계산 그룹**  
    - **기본 계산 그룹**  
    - **승인 그룹**  
    - **표준 프로필**  
    - **프로필 그룹**  

7. **확인** 을 선택합니다.
8. **편집** 을 선택하여 새 시간 등록 직원의 배지 번호를 입력합니다. **배지 ID** 필드에 값을 입력합니다.
9. **저장** 을 선택합니다.
10. **작업자 세부 정보** 및 **작업자** 페이지를 닫습니다.

## <a name="assign-worker-to-device-group"></a>디바이스 그룹에 작업자 할당
1. **생산 제어 > 설정 > 제조 실행 > 디바이스에 대한 작업 카드 구성** 으로 이동합니다.
2. **추가** 를 선택합니다.
3. 목록에서 원하는 작업자를 선택합니다. 이 예에서는 **SHANNON** 을 선택합니다.
4. **확인** 을 선택합니다.
5. **편집** 을 선택합니다.
6. **생산 단위** 필드에서 작업자에 대한 기본 필터를 설정할 수 있습니다. 이렇게 하면 작업자가 디바이스에 로그온할 때 선택한 생산 단위에 대한 생산 작업만 표시됩니다. 원하는 값을 입력합니다.
7. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]