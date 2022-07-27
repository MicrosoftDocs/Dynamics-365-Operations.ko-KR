---
title: SharePoint 채널 구성
description: 이 항목에서는 수신하는 전자 송장을 처리하도록 Microsoft SharePoint 채널을 구성하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ea3e14ed00b0661d3923c1839135378a8a550499
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451714"
---
# <a name="configure-a-sharepoint-channel"></a>SharePoint 채널 구성

[!include [banner](../includes/banner.md)]

수신하는 문서를 처리하도록 Microsoft SharePoint 채널을 구성하기 위한 전제 조건으로 [SharePoint 연결 구성](e-invoicing-create-sharepoint-connection.md)에 설명된 단계를 완료하십시오.

그런 다음 SharePoint 채널을 사용하여 SharePoint 폴더에 저장된 파일에서 전자 공급업체 송장을 가져올 수 있습니다.

1. SharePoint 사이트에서 다음 폴더를 만듭니다.

    - **기본 폴더** – 서비스가 파일을 처리할 폴더입니다.
    - **보관 폴더** – 처리된 파일이 저장될 폴더입니다.
    - **오류 폴더** – 처리가 실패한 경우 시스템이 파일을 이동할 폴더입니다.

2. RCS(Regulatory Configuration Service)에서 생성한 전자 송장 발행 기능을 선택합니다. **초안** 상태의 버전을 선택했는지 확인합니다.
3. **설정** 탭에서 **추가** 를 선택합니다.
4. **기능 설정 만들기** 드롭다운 대화 상자의 **새로 만들기** 필드 그룹에서 **사용자 지정 설정** 옵션을 선택합니다.
5. **설정 유형** 필드 그룹에서 **데이터 채널** 옵션을 선택합니다.
6. **데이터 채널 선택** 필드에서 **SharePoint 폴더** 를 선택합니다.
7. **만들기** 를 선택합니다.
8. 생성한 라인을 선택하고 **편집** 을 선택합니다.
9. **데이터 채널** 탭의 **매개 변수** 섹션에서 다음 필수 필드를 설정합니다.

    | 필드                 | 설명 |
    |-----------------------|-------------|
    | 데이터 채널          | 데이터 채널을 식별하기 위한 고유한 이름을 입력합니다. 이름은 최대 10자까지 가능합니다. 통신 프로세스 동안 적용 가능성 규칙 및 연결된 애플리케이션에서 참조됩니다. |
    | SharePoint 주소    | SharePoint URL을 입력합니다. 예를 들어 `<domain>.sharepoint.com`을 입력합니다. |
    | 애플리케이션 ID        | SharePoint 사용자 계정의 ID가 포함된 Azure Key Vault 비밀의 이름을 입력합니다. 이 비밀은 Key Vault에서 만들고 서비스 환경에서 설정해야 합니다. 값은 [SharePoint 연결 구성](e-invoicing-create-sharepoint-connection.md)의 **애플리케이션(클라이언트) ID** 값입니다. |
    | 애플리케이션 비밀    | SharePoint 사용자 계정의 암호가 포함된 Key Vault 비밀의 이름을 입력합니다. 값은 [SharePoint 연결 구성](e-invoicing-create-sharepoint-connection.md)의 **앱 등록 비밀** 값입니다. |
    | 사이트 이름             | SharePoint 사이트의 이름을 입력합니다. |
    | 문서 라이브러리 이름 | SharePoint 문서 라이브러리의 이름을 입력합니다. |
    | 시간 초과               | 시스템이 응답을 기다려야 하는 최대 시간 제한(ms)을 입력합니다. 기본값은 10,000ms(10초)입니다. |
    | 기본 폴더           | 파일 가져오기 원본 또는 서비스가 파일을 처리해야 하는 폴더를 지정합니다. |
    | 보관 폴더        | 처리된 파일을 저장할 폴더를 지정합니다. |
    | 오류 폴더          | 처리가 실패할 경우 시스템에서 파일을 이동해야 하는 폴더를 지정합니다. |
    | 최대 파일 크기         | 처리되는 단일 파일의 최대 크기(바이트)를 입력합니다. 기본값은 20,000,000바이트입니다. |
    | 최대 파일 수      | 단일 작업에 대해 처리할 최대 파일 수를 입력합니다. 파일 수를 제한하지 않으려면 값을 **0** 으로 설정합니다. |
    | 파일 필터           | 파일 이름으로 필터링할 문자열을 입력합니다. 이 필드는 선택 사항입니다. **\*smth\*.ext** 와 같은 간단한 마스크가 지원되며 여기서 각 별표(\*)는 0개 이상의 문자를 나타냅니다. 예를 들어 PDF 파일을 읽도록 채널을 구성하려면 **\*.pdf** 를 입력합니다. |
    | 사용자 지정 파일 이름      | 클라이언트의 사용자 지정 파일 이름을 입력합니다. |

10. **적용 가능성 규칙** 탭에서 필요에 따라 기준을 검토하고 업데이트합니다. **채널** 필드의 값은 이전 단계에서 **데이터 채널** 필드에 입력한 값과 같아야 합니다.
11. **저장** 을 선택하고 페이지를 닫습니다.
