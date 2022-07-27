---
title: NF-e 사용자 지정 인증서 유효성 검사
description: 이 항목에서는 NF-e 사용자 지정 인증서를 활성화하고 사용하는 데 관한 정보를 제공합니다.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450577"
---
# <a name="nf-e-custom-certificate-validation"></a>NF-e 사용자 지정 인증서 유효성 검사

[!include [banner](../includes/banner.md)]

브라질 루트 인증 기관에서 발급한 인증서의 **서버 인증 목적** 속성은 기본적으로 꺼져 있으며 수동으로 활성화해야 합니다. 경우에 따라 자동 인증서 업데이트가 이 속성을 더는 사용하지 않도록 전환할 수 있습니다. 이 경우 TLS 연결이 영향을 받고 더는 신뢰할 수 없게 됩니다. Minas Gerais(MG) 및 Paraná(PR) 주의 프로덕션 환경에서 브라질 전자 회계 문서 모델 55(NF-e)를 발행하는 기능이 영향을 받습니다.

**NF-사용자 지정 인증서 유효성 검사** 에 대한 수정을 활성화하려면 **기능 관리** 로 이동합니다. 이 기능은 V5 및 V10 인증서 유효성 검사를 위한 대체 솔루션을 허용하고 NF-e의 보안 전송과 SEFAZ의 권한 부여 수신에 필요한 웹 서비스와의 신뢰할 수 있는 연결을 허용합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
