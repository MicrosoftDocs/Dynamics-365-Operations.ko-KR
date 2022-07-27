---
title: 서비스 환경 및 연결된 애플리케이션 구성
description: 이 항목에서는 서비스 환경 및 연결된 애플리케이션을 구성하는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451675"
---
# <a name="configure-service-environments-and-connected-applications"></a>서비스 환경 및 연결된 애플리케이션 구성

[!include [banner](../includes/banner.md)]

이 항목에서는 서비스 환경 및 연결된 애플리케이션을 구성하는 방법에 대한 정보를 제공합니다. 이 프로세스에는 세 단계가 있습니다. 1단계는 필수이고 2단계와 3단계는 선택 사항입니다.

## <a name="step-1-create-a-service-environment"></a>1단계: 서비스 환경 만들기

서비스 환경을 만들 때는 세계화 기능을 배포할 수 있는 사용자 목록을 정의합니다. 일부 시나리오의 경우 선택적으로 전자 송장 발행 서비스와 통신할 수 있는 외부 애플리케이션 목록을 정의합니다. 시나리오에서 사용할 경우 번호 시퀀스를 설정합니다.

이 단계를 완료하려면 [서비스 환경](e-invoicing-service-environments.md)을 참조하십시오.

## <a name="step-2-add-certificates-and-secrets"></a>2단계: 인증서 및 비밀 추가

시나리오에 사용할 Microsoft Azure Key Vault에 대한 참조 및 비밀을 추가합니다. 이 단계는 처리 파이프라인의 작업이 디지털 서명 또는 외부 웹 서비스와의 통신을 위해 인증서 및 비밀을 사용하는 경우 필수입니다.

이 단계를 완료하려면 [고객 인증서 및 비밀](e-invoicing-customer-certificates-secrets.md)을 참조하십시오.

## <a name="step-3-configure-connected-applications"></a>3단계: 연결된 애플리케이션 구성

Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management 애플리케이션과 전자 송장 발행 간의 연결을 설정하려면 Finance 또는 Supply Chain Management를 구성하여 전자 송장 서비스에 대한 호출을 설정하고 필요한 전자 형식으로 변환할 수 있는 통합 구조로 비즈니스 데이터를 준비해야 합니다. 또한 애플리케이션은 서비스의 응답을 올바르게 처리해야 합니다. 이 구성은 Finance 또는 Supply Chain Management 환경에서 직접 완료하거나 RCS(Regulatory Configuration Service)에서 완료할 수 있습니다. RCS에서 구성을 완료하면 Finance 또는 Supply Chain Management에 구성을 배포할 수 있습니다. 이 단계에서는 매개 변수 배포를 위해 연결된 애플리케이션을 등록합니다.

이 단계를 완료하려면 [연결된 애플리케이션](e-invoicing-connected-applications.md)을 참조하십시오.
