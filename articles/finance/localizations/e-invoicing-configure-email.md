---
title: 이메일 채널 구성
description: 이 항목에서는 전자 송장을 수신하도록 이메일 채널을 구성하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6a5896a033212cf0f29f686eec0ab6fb3bc1d2a6
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451687"
---
# <a name="configure-an-email-channel"></a>이메일 채널 구성

[!include [banner](../includes/banner.md)]

생성한 전자 송장 기능이 이메일로 수신된 첨부 파일에서 전자 공급업체 송장을 가져오는 경우 이메일 계정 채널을 구성해야 합니다.

1. RCS(Regulatory Configuration Service)에서 생성한 전자 송장 발행 기능을 선택합니다. **초안** 상태의 버전을 선택했는지 확인합니다.
2. **설정** 탭에서 **추가** 를 선택합니다.
3. **기능 설정 만들기** 드롭다운 대화 상자의 **새로 만들기** 필드 그룹에서 **사용자 지정 설정** 옵션을 선택합니다.
4. **설정 유형** 필드 그룹에서 **데이터 채널** 옵션을 선택합니다.
5. **데이터 채널 선택** 필드에 **수신 이메일** 을 입력합니다.
6. **만들기** 를 선택합니다.
7. 생성한 라인을 선택하고 **편집** 을 선택합니다.
8. **데이터 채널** 탭의 **매개 변수** 섹션에서 다음 필수 필드를 설정합니다.

    | 필드                | 설명 |
    |----------------------|-------------|
    | 데이터 채널         | 데이터 채널을 식별하기 위한 고유한 이름을 입력합니다. 이름은 최대 10자까지 가능합니다. 통신 프로세스 동안 적용 가능성 규칙 및 연결된 애플리케이션에서 참조됩니다. |
    | 서버 주소       | 이메일 계정 공급자의 서버 주소를 입력합니다. 예를 들어 `https://outlook.live.com` 공급자의 서버 주소는 imap-mail.outlook.com입니다. |
    | 서버 포트          | 이메일 계정 공급자가 사용하는 포트 번호를 입력합니다. 예를 들어 `https://outlook.live.com` 공급자의 서버 포트는 993입니다. |
    | 사용자 이름 비밀     | 이메일 사용자 계정의 ID가 포함된 Microsoft Azure Key Vault 비밀의 이름을 입력합니다. 이 비밀은 Key Vault에서 만들고 서비스 환경에서 설정해야 합니다. |
    | 사용자 암호 비밀 | 이메일 사용자 계정의 ID가 포함된 Key Vault 비밀의 암호를 입력합니다. |
    | 시간 초과              | 시스템이 응답을 기다려야 하는 최대 시간 제한(ms)입니다. 기본값은 10,000ms(10초)입니다. |
    | 기본 폴더          | 이메일 가져오기 원본 또는 서비스가 이메일을 처리해야 하는 폴더를 지정합니다. |
    | 보관 폴더       | 처리된 이메일을 저장할 폴더를 지정합니다. 이 폴더를 지정하지 않으면 시스템이 자동으로 폴더를 생성합니다. |
    | 오류 폴더         | 처리가 실패할 경우 시스템에서 이메일을 이동해야 하는 폴더를 지정합니다. 이 폴더를 지정하지 않으면 시스템이 자동으로 폴더를 생성합니다. |
    | 최대 메시지 크기     | 처리되는 단일 메시지의 최대 크기(바이트)를 입력합니다. 기본값은 20,000,000바이트입니다. |
    | 최대 메시지 수   | 단일 작업에 대해 처리할 최대 메시지 수를 입력합니다. 메시지 수를 제한하지 않으려면 값을 **0** 으로 설정합니다. |
    | 보낸 사람 필터          | 보낸 사람 주소로 필터링할 문자열을 입력합니다. 보낸 사람 주소가 필터와 일치하는 이메일만 처리됩니다. 이 필드는 선택 사항입니다. 여러 발신자 주소를 지정하려면 세미콜론(;)을 구분 기호로 사용합니다. |
    | 제목 필터       | 제목으로 필터링할 문자열을 입력합니다. 제목이 필터와 일치하는 이메일만 처리됩니다. 이 필드는 선택 사항입니다. **\*smth\*.ext** 와 같은 간단한 마스크가 지원되며 여기서 각 별표(\*)는 0개 이상의 문자를 나타냅니다. |
    | 날짜 필터          | 처리되는 메시지의 최대 기간(일)을 정의하는 날짜를 지정합니다. 이 필드는 선택 사항입니다. 기본값은 30일입니다. |
    | 처리 모드      | <p>다음 옵션 중 하나를 선택하여 이메일의 모든 첨부 파일을 함께 처리할 수 있는지 또는 각 첨부 파일을 별도로 처리해야 하는지를 지정합니다.</p><ul><li><b>첨부 파일로</b> – 이메일의 각 첨부 파일에 대해 새 이메일이 생성됩니다. 예를 들어, 하나의 이메일에 전자 송장 데이터가 포함된 여러 파일이 포함된 경우 각 파일은 시스템에서 새 전자 송장으로 간주됩니다.</li><li><b>이메일로</b> – 하나의 첨부 파일은 기본 첨부 파일로 간주되며 하나의 전자 송장이 시스템에서 생성됩니다. 기타 첨부 파일은 지원 파일로 사용할 수 있습니다.</li></ul> |

9. **첨부 파일 필터** 섹션에서 파일 필터링 정보를 추가합니다. 정의된 필터를 충족하는 첨부 파일만 처리됩니다. 예를 들어 **\*.xml** 은 파일 이름 확장명이 .xml인 첨부 파일을 필터링합니다. 첨부 파일의 이름은 설정하는 동안 Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management에서 사용됩니다.

    - 이전 단계에서 **처리 모드** 필드를 **이메일로** 로 설정한 경우 여기에 여러 필터를 추가할 수 있습니다. 이름은 특정 문서를 식별합니다.
    - **처리 모드** 필드를 **첨부파일로** 로 설정하면 필터를 하나만 추가할 수 있습니다.

10. **적용 가능성 규칙** 탭에서 필요에 따라 기준을 검토하고 업데이트합니다. **채널** 필드의 값은 8단계에서 **데이터 채널** 필드에 입력한 값과 같아야 합니다.
11. **저장** 을 선택하고 페이지를 닫습니다.