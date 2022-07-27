---
title: 전자 송장 설정
description: 이 항목에서는 전자 송장을 설정하고 구성하는 프로세스에 대한 개요를 제공합니다.
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
ms.openlocfilehash: 8138c63e9eff1d2ca934f9d4467e4e3b73dae941
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451693"
---
# <a name="electronic-invoicing-setup"></a>전자 송장 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 전자 송장을 설정하고 구성하는 프로세스에 대한 개요를 제공합니다. 여기에 지정된 순서대로 설정 단계를 완료해야 합니다. 필수 단계지만 건너뛰면 기능이 제대로 작동하지 않고 후속 단계에서 또는 기능을 사용할 때 여러 번 오류가 발생합니다. 

시작하기 전에 모든 주요 구성 요소가 올바르게 설정되어 있는지, RCS(Regulatory Configuration Service)에 등록되어 있고 RCS의 인스턴스가 있는지, Microsoft Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management 환경에 전자 송장 추가 기능이 설치되어 있는지 확인하십시오. 자세한 내용은 [전자 송장 가입 및 설치](e-invoicing-install-add-in-microservices-lcs.md)를 참조하십시오.

다음으로 전자 인보이스가 작업을 수행하는 데 필요한 Azure 리소스를 설정합니다. 자세한 내용은 [전자 송장을 위한 Azure 리소스 설정](e-invoicing-set-up-azure-resources.md)을 참조하십시오.

주요 구성 요소가 구성된 후 RCS와 함께 전자 송장의 주요 논리적 구성 요소를 설정합니다. 먼저 유지 관리할 서비스 환경의 수를 정의합니다. 이러한 방식으로 논리적 데이터 및 구성 분할을 정의하여 개발 또는 테스트 환경과 프로덕션 환경 사이에 경계가 있는지 확인합니다. 유연한 방식으로 개발 프로세스를 설정하려면 여러 개의 개별 개발 및 테스트 환경이 필요할 수 있습니다. 서비스 환경을 정의하는 것 외에도 Finance 또는 Supply Chain Management와 같은 비즈니스 애플리케이션에 대한 링크를 RCS에서 직접 설정하여 전자 송장과 함께 적절한 작동에 필요한 매개변수를 설정합니다. 환경에 대한 자세한 내용은 [서비스 환경](e-invoicing-service-environments.md)을 참조하십시오.

모든 것이 설정되면 전자 문서를 처리하고 데이터를 변환하거나 글로벌 리포지토리에서 문서를 가져오기 위한 다양한 시나리오를 정의하는 고유한 글로벌화 기능을 생성할 수 있습니다. 세계화 기능을 사용하는 방법에 대한 자세한 내용은 [세계화 기능 사용](e-invoicing-working-globalization-features.md)을 참조하십시오.

세계화 기능에 구축할 프로세스를 구성하는 처리 파이프라인의 작업에 대한 자세한 내용은 **[완료!: 문서 처리 작업]** 을 참조하십시오.

인바운드 전자 문서를 처리하기 위해 전자 메일 또는 SharePoint와의 통합이 필요한 경우 해당 채널을 설정하고 사용하는 방법에 대한 자세한 내용은 [수신 전자 문서 처리](e-invoicing-process-incoming-electronic-documents.md)를 참조하십시오.
