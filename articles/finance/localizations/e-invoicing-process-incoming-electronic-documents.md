---
title: 수신 전자 문서 처리
description: 이 항목에서는 수신 전자 문서 처리에 대한 개요를 제공합니다.
author: dkalyuzh
ms.date: 02/28/2022
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
ms.openlocfilehash: 9701367e1ba1f9dbd1e53deb863c10af4213a359
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451672"
---
# <a name="processing-of-incoming-electronic-documents"></a>수신 전자 문서 처리

[!include [banner](../includes/banner.md)]

공급업체 전자 송장과 같은 수신 전자 문서는 다음의 두 가지 방법으로 가져오고 처리할 수 있습니다.

- 파일은 외부 채널에서 검색되어 연결된 애플리케이션으로 직접 전달됩니다. 거기에서 추가 변환을 거친 다음 데이터베이스로 가져옵니다.
- 파일은 전자 송장 발행 서비스에서 사전 처리된 다음 연결된 애플리케이션으로 전달됩니다.

전자 송장 발행은 수신 문서에 대해 이메일 및 Microsoft SharePoint 폴더의 두 채널을 지원합니다.

문서가 사전 처리를 거치는지 아니면 연결된 애플리케이션에 직접 전달되는지를 지정하는 두 설정 유형이 있습니다.

- **데이터 채널** – 시스템은 문서를 연결된 애플리케이션으로 직접 전달합니다.
- **처리 파이프라인이 있는 데이터 채널** – 문서가 연결된 애플리케이션에 전달되기 전에 실행할 추가 작업을 설정할 수 있습니다.

다른 채널의 수신 전자 문서를 처리하기 위한 시나리오를 설정하는 방법에 대해서는 [이메일 채널 구성](e-invoicing-configure-email.md) 및 [SharePoint 채널 구성](e-invoicing-configure-sharepoint-channel.md)을 참조하십시오.
