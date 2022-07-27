---
title: 고객 인증서 및 비밀
description: 이 항목에서는 전자 송장 발행에서 고객 인증서 및 비밀을 설정하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/07/2022
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
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451717"
---
# <a name="customer-certificates-and-secrets"></a>고객 인증서 및 비밀

[!include [banner](../includes/banner.md)]

RCS(Regulatory Configuration Service)에 Microsoft Azure Key Vault 참조가 이미 있는 경우 Key Vault 인증서 및 비밀에 대한 참조를 만들 수 있습니다. 아직 Key Vault 참조가 없는 경우 이를 만드는 방법은 [서비스 환경](e-invoicing-service-environments.md)을 참조하십시오.

## <a name="create-certificates-and-secrets"></a>고객 인증서 및 비밀 만들기

인증서와 비밀을 만들고 설정하려면 다음 단계를 따릅니다.

1. RCS 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **환경** 섹션에서 **전자 송장 발행** 타일을 선택합니다.
3. **환경 설정** 페이지의 작업 창에서 **서비스 환경** 을 선택합니다.
4. **서비스 환경** 페이지의 작업 창에서 **Key Vault 매개 변수** 를 선택합니다.
5. **Key Vault 매개 변수** 페이지에서 Key Vault 참조를 선택한 다음 **인증서** 섹션에서 **추가** 를 선택합니다.
6. **이름** 필드에 Key Vault 인증서 또는 비밀의 이름을 입력합니다. 자세한 내용은 [Azure Portal에서 Azure 스토리지 계정 만들기](e-invoicing-create-azure-storage-account-azure-portal.md)를 참조하십시오.
7. **설명** 필드에 설명을 입력합니다.
8. Key Vault에 저장된 인증서를 참조하는 경우 **유형** 필드에서 **인증서** 를 선택합니다. Key Vault에 저장된 비밀을 참조하는 경우 **비밀** 을 선택합니다.
9. **저장** 을 선택합니다.

> [!NOTE]
> 일부 시나리오에서는 파일 이름 확장명이 .cer인 공용 인증서를 사용해야 합니다. 그러나 Key Vault는 이 유형의 인증서를 Key Vault 인증서로 가져오고 저장하는 것을 지원하지 않습니다. 이러한 시나리오에서는 .cer 파일을 Base-64로 인코딩된 X.509(.CER) 문자열로 저장해야 합니다. 그런 다음 Key Vault 비밀에서 **BEGIN CERTIFICATE** 줄과 **END CERTIFICATE** 줄 사이에 나오는 문자열을 파일에 저장합니다. 서비스 환경에서는 여전히 Key Vault 레코드에 대한 참조를 만들고 **유형** 필드를 **인증서** 로 설정해야 합니다.

## <a name="create-a-chain-of-certificates"></a>인증서 체인 만들기

국가/지역별 송장에 디지털 서명을 적용하거나 외부 웹 서비스에 대한 보안(Secure Sockets Layer \[SSL\]) 연결을 설정하기 위해 인증서 체인이 필요한 경우 인증서가 다음 순서의 인증서 체인을 만듭니다.

1. 루트 인증서
2. 중간 인증서
3. 최종 사용자 인증서

루트 인증 기관(CA)은 신뢰할 수 있는 인증서 출처입니다. 중간 CA 인증서는 최종 사용자 인증서를 루트 CA 인증서에 연결하는 브리지입니다.

인증서의 체인을 만들고 설정하려면 다음 단계를 따릅니다.

1. **Key Vault 매개 변수** 페이지의 작업 창에서 **인증서 체인** 을 선택합니다.
2. **새로 만들기** 를 선택하여 인증서 체인을 만듭니다.
3. **이름** 필드에 인증서 체인의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **인증서** 섹션에서 **추가** 를 선택하여 체인에 인증서를 추가합니다.
6. **위로** 또는 **아래로** 버튼을 사용하여 체인에서 인증서의 위치를 변경합니다. CA 루트 인증서를 목록 상단에 유지하고 최종 사용자 인증서를 하단에 유지합니다.
7. **저장** 을 선택합니다.

RCS에서 원하는 만큼 Key Vault 참조를 만들 수 있습니다. 스토리지 공유 액세스 서명(SAS) 토큰의 비밀은 지정된 서비스 환경을 Key Vault 참조에 연결하는 데 사용됩니다. 서비스 환경을 설정할 때 사용하는 스토리지 SAS 토큰에 대한 비밀도 포함하는 Key Vault에 저장된 Key Vault 인증서 및 비밀을 참조할 수 있습니다.
