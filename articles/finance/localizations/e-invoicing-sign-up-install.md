---
title: 전자 송장 발행 서비스 가입 및 설치
description: 이 항목에서는 전자 송장 서비스에 가입하고 설치하는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 4ab16652e4a50dd71a5d0b2b49b4dd79e327f7a8
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451690"
---
# <a name="sign-up-for-and-install-the-electronic-invoicing-service"></a>전자 송장 발행 서비스 가입 및 설치

[!include [banner](../includes/banner.md)]

이 항목에서는 전자 송장 서비스에 가입하고 설치하는 방법에 대한 정보를 제공합니다. 이 프로세스에는 네 단계가 있습니다. 1~3단계는 필수이며 4단계는 선택 사항입니다.

### <a name="step-1-sign-up-for-regulatory-configuration-service"></a>1단계: Regulatory Configuration Service 등록

RCS(Regulatory Configuration Service)는 전자 송장을 구성하는 데 사용되는 구성 및 설계 환경을 제공합니다. 환경 및 전자 송장 기능과 같은 리소스가 RCS에서 생성, 유지 및 관리됩니다. 리소스가 준비되면 전자 송장 서비스에 게시됩니다.

RCS에 대한 자세한 내용은 [Regulatory Configuration Services(RCS) - 세계화 기능](rcs-globalization-feature.md)을 참조하십시오.

RCS에 가입하려면 [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/) 페이지를 방문하십시오.

### <a name="step-2-install-the-add-in-for-microservices-in-microsoft-dynamics-lifecycle-services"></a>2단계: Microsoft Dynamics Lifecycle Services에서 마이크로 서비스용 추가 기능 설치

전자 송장 서비스는 Microsoft 데이터 센터에서 호스팅되는 일련의 마이크로 서비스입니다. 기본적으로 Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management 고객은 전자 송장 서비스에 액세스할 수 없습니다. LCS(Microsoft Dynamics Lifecycle Services)의 추가 기능으로 설치해야 합니다. 추가 기능을 설치하면 Finance 또는 Supply Chain Management 환경이 전자 송장 서비스에 연결할 수 있는 애플리케이션 등록부에 등록됩니다.

이 단계를 완료하려면 [Lifecycle Services에서 마이크로 서비스용 추가 기능 설치](e-invoicing-install-add-in-microservices-lcs.md)를 참조하십시오.

### <a name="step-3-set-up-rcs"></a>3단계: RCS 설정

RCS와 전자 송장 서비스 간의 통합을 설정해야 합니다. 또한 주요 구성 요소를 설정해야 합니다.

이 단계를 완료하려면 [RCS(Regulatory Configuration Service) 설정](e-invoicing-set-up-rcs.md)을 참조하십시오.

### <a name="step-4-microsoft-power-platform-plug-in-admin-reference"></a>4단계: Microsoft Power Platform 플러그인 관리자 참조

일부 시나리오에서는 Microsoft Power Platform의 범위에서 Dataverse와 통합해야 합니다.

현재 인도네시아 전자 인보이스 시나리오에 전자 인보이스 솔루션을 사용하려는 경우 이 설정은 필수입니다. 그러나 사우디 아라비아 전자 송장 발행 시나리오에서는 선택 사항입니다. 자세한 내용은 [국가 또는 지역별 전자 송장 발행 기능 제공](e-invoicing-country-specific-availability.md)을 참조하십시오.

이 단계를 완료하려면 [Microsoft Power Platform 플러그인 관리자 참조](e-invoicing-power-platform-plug-in.md)를 참조하십시오.
