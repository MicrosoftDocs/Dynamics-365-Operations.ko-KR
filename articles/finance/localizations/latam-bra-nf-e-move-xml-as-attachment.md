---
title: NF-e XML 파일을 첨부 파일로 이동
description: 이 항목에서는 Microsoft Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management 데이터베이스에서 NF-e XML 파일을 이동하고 대신 첨부 파일로 사용할 수 있도록 하는 방법을 설명합니다.
author: gionoder
ms.date: 11/11/2021
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
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c7b82d486cecf6b20f1283fa609c360b3003efca
ms.sourcegitcommit: ebf6546835e4d6a80aea1dfae81e119e294387f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "8451192"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>NF-e XML 파일을 첨부 파일로 이동

[!include [banner](../includes/banner.md)] 


전자 회계 문서(NF-e)가 발행되면 XML 파일이 생성되고 Microsoft Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management 데이터베이스에 저장됩니다. 브라질 현지화에서는 **NF-e XML을 첨부 파일로 이동** 기능을 사용하여 해당 XML 파일이 소비하는 데이터베이스 공간을 확보할 수 있습니다.

특정 날짜 범위와 회계 설정의 경우 이 기능은 NF-e XML 파일을 Finance 또는 Supply Chain Management 데이터베이스에서 Azure 구독의 Blob Storage로 이동합니다. 이 이동을 수행하면 파일을 첨부 파일로만 사용할 수 있습니다. XML 파일이 Blob Storage로 이동되면 Finance 또는 Supply Chain Management 데이터베이스에서 원래 파일이 삭제됩니다. 따라서 해당 파일이 차지한 데이터베이스 공간이 해제됩니다.

**NF-e XML을 첨부 파일로 이동** 기능을 활성화하려면 다음 단계를 따르세요.

1. Finance 또는 Supply Chain Management에서 **기능 관리** 작업 영역을 엽니다.
2. **모두** 탭에서 **NF-e XML을 첨부 파일로 이동** 기능을 찾고 선택합니다.
3. **지금 활성화** 를 선택합니다.

NF-e XML 파일을 첨부 파일로 이동하려면 다음 단계를 따릅니다.

1. **수취 계정** \> **회계 문서** \> **전자 회계 문서** \> **NF-e XML을 첨부 파일로 이동** 으로 이동합니다.
2. **시작 날짜** 및 **종료 날짜** 필드에 시작 및 종료 날짜를 선택합니다.
3. **회계 기관 ID** 필드에서 값을 선택합니다.
4. **확인** 을 선택합니다.

> [!IMPORTANT]
> 이 프로세스는 되돌릴 수 없습니다. NF-e XML 파일을 이동한 후에는 **회계 문서** 페이지 상단의 **첨부 파일** 을 선택해야 사용자가 문서를 볼 수 있습니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
