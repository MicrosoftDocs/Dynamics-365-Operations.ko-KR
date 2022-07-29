---
title: 전자 서명 설정
description: 이 절차를 사용하여 전자 서명을 설정합니다.
author: maertenm
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4075e47013bb6a3f42cb07f88df121cef8688463cab25c4a734c5363106ace4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460766"
---
# <a name="set-up-electronic-signatures"></a>전자 서명 설정

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 전자 서명을 설정합니다. 전자 서명은 컴퓨팅 프로세스를 시작하거나 승인하려는 사람의 신원을 확인합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 DAT입니다.


## <a name="enable-the-electronic-signature-configuration-key"></a>전자 서명 구성 키 활성화
1. 시스템 관리 > 설정 > 라이선스 구성으로 이동합니다.
2. 트리에서 '관리'를 확장합니다.
    * 전자 서명 확인란이 선택되어 있는지 확인합니다.  
    * 전자 서명 확인란이 선택되지 않은 경우 유지 관리 모드를 활성화해야 합니다. 이 환경에서는 Lifecycle Services에서 유지 관리 작업을 실행하거나 Deployment.Setup 도구를 로컬로 사용하여 유지 관리 모드를 활성화할 수 있습니다.  
3. 페이지를 닫습니다.

## <a name="set-up-electronic-signature-parameters"></a>전자 서명 매개 변수 설정
1. 조직 관리 > 설정 > 전자 서명 > 전자 서명 매개 변수로 이동합니다.
2. 편집을 클릭합니다.
3. 공지 필드에 값을 입력합니다.
    * 서명이 요청될 때 서명자가 받게 될 통지를 입력합니다. 모든 텍스트를 입력할 수 있습니다. 일반적으로 이 텍스트는 전자적으로 문서에 서명하는 것이 무엇을 의미하는지 사용자에게 알려줍니다.  
    * 통지 텍스트를 다른 언어로 입력하려면 번역 버튼을 클릭합니다.  
4. 저장을 클릭합니다.
5. 페이지를 닫습니다.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>전자 서명의 이유 코드 설정
1. 조직 관리 > 설정 > 전자 서명 > 전자 서명 이유 코드로 이동합니다.
2. 새로 만들기를 클릭합니다.
    * 전자 서명을 사용하기 전에 사유 코드를 설정해야 합니다. 문서에 서명할 때 유효한 이유 코드가 필요합니다.     서명자는 전자 서명의 목적을 나타내기 위해 이유 코드를 선택합니다. 예를 들어, 이유 코드를 사용하여 법적 승인을 나타낼 수 있습니다.  
3. 이유 코드 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
    * 필요한 경우 추가 이유 코드를 입력합니다.  
5. 저장을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="require-electronic-signatures-for-existing-processes"></a>기존 프로세스에 전자 서명 필요
1. 조직 관리 > 설정 > 전자 서명 > 전자 서명 요구 사항으로 이동합니다.
2. 목록에서 원하는 기록을 찾아 선택합니다.
    * 전자 서명이 필요한 프로세스를 선택합니다.  
3. 서명 필요 확인란을 선택하거나 선택 취소합니다.
    * 전자 서명이 필요한 각 프로세스에 대해 이 단계를 반복합니다.  
4. 저장을 클릭합니다.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>전자 서명에 대한 사용자 지정 요구 사항 만들기
1. 새로 만들기를 클릭합니다.
2. 서명 필요 확인란을 선택하거나 선택 취소합니다.
3. 이름 필드에 전자 서명이 필요한 프로세스 이름을 입력합니다.
4. 테이블 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 서명해야 하는 데이터가 저장된 테이블을 찾아 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 필드 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
8. 목록에서 모니터링할 테이블의 필드를 찾아 선택합니다.
9. 목록에서 선택한 행의 링크를 클릭합니다.
    * 서명이 필요한 시점을 지정합니다.     필드의 데이터가 변경될 때 서명이 필요한 경우 항상을 선택합니다.     특정 조건에서만 서명이 필요한 경우에만 선택합니다. 전용을 선택하는 경우 레코드가 삽입될 때, 레코드가 업데이트될 때 또는 레코드가 삭제될 때 옵션 중 하나도 선택해야 합니다.  
10. 저장을 클릭합니다.
11. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]