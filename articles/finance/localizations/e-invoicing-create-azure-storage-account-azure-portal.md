---
title: Azure 포털에서 Azure 스토리지 계정 생성
description: 이 항목에서는 전자 송장 발행용 Azure 스토리지 계정을 만드는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/14/2022
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
ms.openlocfilehash: 3d9647e234b3603ef6305ec6031a793b744bbe98
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451711"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Azure 포털에서 Azure 스토리지 계정 생성

[!include [banner](../includes/banner.md)]

전자 송장 발행 서비스에서 생성하거나 처리 중에 서비스로 이동하는 모든 전자 파일은 Microsoft Azure 스토리지 계정 컨테이너에 저장됩니다. 전자 송장 발행에서 해당 컨테이너에 액세스할 수 있도록 하려면 스토리지 계정의 공유 액세스 서명(SAS) 토큰을 전자 송장 발행 서비스에 제공해야 합니다. 또한 토큰이 안전하게 저장되도록 하려면 SAS 토큰을 직접 제공하지 마십시오. 대신 Azure Key Vault에 저장하고 Azure Key Vault 비밀을 제공하십시오.

1. 전자 송장 발행 서비스에 사용할 스토리지 계정을 엽니다.
2. **설정** \> **구성** 으로 이동하고 **Blob 공용 액세스 허용** 매개 변수를 **사용** 으로 설정합니다.
3. **데이터 저장소** \> **컨테이너** 로 이동하고 컨테이너를 만듭니다.
4. 컨테이너의 이름을 입력하고 **공용 액세스 수준** 필드를 **비공개(익명 액세스 불가)** 로 설정합니다.
5. 새 컨테이너를 열고 **설정** \> **액세스 정책** 으로 이동합니다.
6. **정책 추가** 를 선택하여 저장된 액세스 정책을 추가합니다.
7. **식별자** 필드를 적절하게 설정합니다.
8. **사용 권한** 필드에서 모든 사용 권한을 선택합니다.

    ![정책 추가 대화 상자의 사용 권한 필드에 선택된 모든 사용 권한.](media/e-invoicing-azure-1.png)

9. 시작 날짜와 종료 날짜를 입력합니다. 종료 날짜는 미래 날짜여야 합니다.
10. **확인** 을 선택하여 정책을 저장한 다음 변경 사항을 컨테이너에 저장합니다.
11. **설정** \> **공유 액세스 토큰** 으로 이동하고 필드 값을 설정합니다.
12. 시작 날짜와 종료 날짜를 입력합니다. 종료 날짜는 미래 날짜여야 합니다.
13. **사용 권한** 필드에서 다음 사용 권한을 선택합니다.

    - 읽기
    - 추가
    - 만들기
    - 쓰기
    - 삭제
    - 목록

14. **SAS 토큰 및 URL 생성** 을 선택합니다.
15. **Blob SAS URL** 필드에 값을 복사하고 저장합니다. 이 값은 이 절차의 뒷부분에서 사용되며 *공유 액세스 서명 URI* 라고 합니다.
16. 전자 송장 발행에 사용하려는 Key Vault를 엽니다.
17. **설정** \> **비밀** 로 이동하고 **생성/가져오기** 를 선택하여 비밀을 만듭니다.
18. **비밀 만들기** 페이지의 **업로드 옵션** 필드에서 **수동** 을 선택합니다.
19. 비밀의 이름을 입력합니다. 이 이름은 RCS(Regulatory Configuration Service)에서 서비스를 설정하는 동안 사용되며 *Key Vault 비밀 이름* 이라고 합니다. RCS를 설정하는 방법에 대한 자세한 내용은 [RCS(Regulatory Configuration Service) 설정](e-invoicing-set-up-rcs.md)을 참조하십시오.
20. **값** 필드에 이전에 복사한 공유 액세스 서명 URI를 입력합니다.
21. **만들기** 를 선택합니다.
