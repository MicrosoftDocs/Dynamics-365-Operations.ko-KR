---
title: 전자 서명 개요
description: 이 문서에서는 전자 서명에 대한 개요를 제공하고 전자 서명을 사용하는 방법을 설명합니다.
author: maertenm
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.custom:
- "13611"
- intro-internal
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9f80ecef043a697d288fed99e3118e268d4f993
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460740"
---
# <a name="electronic-signatures-overview"></a>전자 서명 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 전자 서명에 대한 개요를 제공하고 전자 서명을 사용하는 방법을 설명합니다.

## <a name="what-is-an-electronic-signature"></a>전자 서명이란 무엇입니까?

전자 서명은 컴퓨팅 프로세스를 시작하거나 승인하려는 사람의 신원을 확인합니다. 일부 산업에서 전자 서명은 수기 서명만큼 법적 구속력이 있습니다.

전자 서명은 제약, 식품 및 음료, 항공 우주 및 방위 산업과 같은 여러 규제 산업에 대한 규정 준수 요구 사항입니다. 또한 미국 식품의약국(FDA)에서 발행한 21 CFR Part 11의 규정을 준수해야 합니다.

> [!NOTE]
> 전자 서명 자체는 디지털 서명과 다릅니다. 전자 서명은 손으로 쓴 서명을 대신할 뿐인 반면 디지털 서명은 추가 보안 조치를 제공합니다. 디지털 서명은 다른 사용자나 프로세스가 데이터를 변조했는지 여부를 식별하는 데 도움이 될 수 있습니다. 디지털 서명도 확인할 수 있으며 데이터 서명에 사용된 인증서 소유자가 이 확인을 반박할 수 없습니다. 아래에 설명된 것처럼 전자 서명에는 디지털 서명 함수가 내장되어 있습니다.

## <a name="electronic-signatures"></a>전자 서명

중요한 비즈니스 프로세스에 전자 서명을 사용할 수 있습니다. 일부 프로세스에는 전자 서명 기능이 내장되어 있습니다. 또한 모든 데이터베이스 테이블 및 필드에 대한 사용자 지정 서명 요구 사항을 만들 수 있습니다.

전자 서명에는 디지털 서명 함수가 내장되어 있습니다. 문서에 서명하는 모든 사용자는 유효한 암호화 인증서를 받아야 합니다. 문서가 서명되면 해당 인증서와 연결된 개인 키의 유효성이 검사됩니다. 전자 서명 정보는 로그에 기록되어 감사 추적을 제공합니다. 전자 서명을 설정하려면 [전자 서명 설정](tasks/set-up-electronic-signatures.md)을 참조하십시오.

## <a name="users-who-require-access-to-electronic-signatures"></a>전자 서명에 대한 액세스 권한이 필요한 사용자

일반적으로 전자 서명 관리자, 서명자 및 전자 서명 감사자의 세 가지 유형의 사용자가 전자 서명에 대한 보안 액세스를 필요로 합니다.

### <a name="electronic-signature-administrator"></a>전자 서명 관리자

전자 서명 관리자는 서명 요구 사항, 일반 매개 변수 및 승인자를 설정하고 서명을 확인할 수 없는 경우 경고를 받습니다. 기본적으로 **정보 기술 관리자** 보안 역할에 속한 사용자는 전자 서명을 관리할 수 있는 권한이 있습니다.

### <a name="signer"></a>서명자

서명자는 서명이 필요한 문서 및 프로세스에 대한 전자 서명을 제공합니다. 기본적으로 **시스템 사용자** 보안 역할에 속하는 사용자는 문서에 전자적으로 서명할 수 있는 권한이 있습니다.

> [!NOTE]
> 서명자는 서명 중인 문서 또는 프로세스와 관련된 데이터에 대한 액세스 권한이 부여되기 전에 추가 권한이 필요할 수 있습니다. 데이터를 변경한 다음 해당 변경 사항에 서명해야 하는 사용자는 데이터를 변경할 수 있는 권한이 있어야 합니다. 다른 사용자를 대신하여 서명하는 사용자는 데이터에 대한 액세스가 필요하지 않을 수 있습니다. 이러한 유형의 사용자의 예로는 직원의 변경 사항에 서명하는 감독자가 있습니다.

### <a name="electronic-signature-auditor"></a>전자서명 감사인

전자 서명 감사자는 데이터베이스 로그와 데이터베이스 로그에서 사용할 수 있는 서명 검토 로그를 검토합니다. 기본적으로 **정보 기술 관리자** 보안 역할에 속하는 사용자는 전자 서명을 감사할 권한이 있습니다.

**정보 기술 관리자** 이외의 역할을 사용하는 경우 역할에 다음 권한이 할당되었는지 확인하십시오.

- 전자 서명 실패 보기
- 데이터베이스 로그 보기

## <a name="signing-documents-electronically"></a>전자적으로 문서 서명

### <a name="get-a-certificate"></a>인증서 받기

전자적으로 문서에 서명하기 전에 인증서를 요청해야 합니다.

> [!NOTE]
> Microsoft SQL Server 기능은 인증서를 생성하고 전자 서명을 활성화하는 데 사용됩니다. 추가 인증서 또는 PKI(공개 키 인프라)가 필요하지 않습니다.

인증서를 요청하면 공개 키와 개인 키가 생성됩니다. 개인 키는 본인만 알고 있는 암호를 사용하여 암호화됩니다. 전자적으로 문서에 서명하는 경우 비밀번호를 입력하면 신원이 확인됩니다.

인증서를 요청하려면 **옵션** 페이지의 **계정** 탭에서 **인증서 가져오기** 를 클릭합니다.

서명에 사용할 비밀번호를 입력하고 확인해야 합니다. 비밀번호는 개인 키를 보호하고 인증서 사용을 승인하는 데 사용됩니다. 이 암호는 데이터베이스에 저장되지 않으며 관리자를 비롯한 다른 사람이 사용할 수 없습니다.

인증서와 연결된 암호를 잊어버린 경우 해당 인증서를 재설정해야 합니다. 인증서를 재설정하면 이전 인증서를 사용하여 서명한 문서에 영향을 주지 않습니다. 인증서를 재설정하려면 **옵션** 페이지에서 **인증서 재설정** 을 클릭합니다.

### <a name="sign-a-document-electronically"></a>전자적으로 문서에 서명

전자 서명이 필요한 변경을 수행하면 **문서 서명** 페이지가 표시됩니다.

1. **문서 서명** 페이지에서 **문서** 탭을 클릭하여 문서의 변경 사항을 검토합니다.
2. **서명** 탭에서 이유 코드를 선택합니다.
3. 주석이 필요한 경우 주석을 입력합니다.
4. 사용자 ID가 **서명자** 필드에 나타나지 않으면 목록에서 선택하십시오.
5. 이 정보가 필요한 경우 위치를 입력하십시오.
6. **확인** 을 클릭합니다.

### <a name="sign-for-another-users-changes"></a>다른 사용자의 변경 사항에 서명

경우에 따라 사용자가 다른 사용자의 변경 사항에 서명하도록 할 수 있습니다. 예를 들어, 감독자는 직원이 BOM(자재 명세서)을 변경하는 데 서명해야 할 수 있습니다. 이 절차를 사용하여 사용자를 다른 사용자의 서명자로 지정합니다.

> [!NOTE]
> 한 사용자가 다른 사용자의 변경에 서명할 때 변경을 수행한 사용자의 워크스테이션에서 서명을 제공해야 합니다. 사용자는 서명이 제공될 때까지 변경 사항을 저장할 수 없습니다.

승인자를 지정하려면 다음 단계를 따르십시오.

1. **옵션** 페이지의 **계정** 탭에서 **승인자 지정** 을 클릭합니다.
2. **승인자 사용자 ID** 필드에서 다른 사용자의 변경 사항에 서명해야 하는 사용자의 ID를 선택하십시오.
3. **사용자 ID 서명** 필드에서 변경 사항에 서명해야 하는 사용자의 ID를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]