---
title: 서비스 수준 계약 개요
description: 서비스 수준 계약에서 고객은 서비스 회사가 문제를 기록하고 문제가 해결된 시점을 기준으로 최소 응답 시간에 동의합니다.
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a36b1c0e18201ae04a9fe13cb4f9524a19655c92
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449758"
---
# <a name="service-level-agreements-overview"></a>서비스 수준 계약 개요       

[!include [banner](../includes/banner.md)]


SLA(서비스 수준 계약)는 서비스 회사와 서비스 고객 간의 계약입니다. SLA에서 고객은 서비스 회사가 문제를 기록하고 문제가 해결된 시점을 기준으로 최소 응답 시간에 동의합니다.

SLA는 고객에게 제공되는 표준 수준의 서비스를 시행하고 서비스 작업을 완료해야 할 때 서비스 회사에 투명하게 만듭니다.

서비스 고객에게 다양한 수준의 서비스를 제공하기 위해 원하는 수의 SLA를 만들 수 있습니다.

## <a name="create-a-service-level-agreement"></a>서비스 수준 계약 만들기

1.  **서비스 관리** \> **설정** \> **서비스 계약** \> **서비스 수준 계약** 을 클릭합니다.

2.  **서비스 수준 계약** 필드에 서비스 수준 계약의 이름을 입력합니다.

3.  서비스 수준 계약에 첨부된 서비스 요청 완료에 허용할 시간을 입력합니다. 그런 다음 특정 달력을 기준으로 서비스 수준 계약을 설정하려면 달력을 선택합니다.

## <a name="apply-a-service-level-agreement"></a>서비스 수준 계약 적용

SLA는 서비스 계약에 직접 적용됩니다.

수동으로 생성하고 SLA가 있는 서비스 계약에 첨부하는 서비스 주문은 해당 SLA를 기준으로 측정됩니다.

자동으로 생성하는 서비스 주문은 SLA에 첨부되지 않습니다.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>서비스 계약에 서비스 수준 계약 적용

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 클릭합니다. SLA를 적용할 서비스 계약을 선택한 다음 **작업 창** 에서 **편집** 을 클릭합니다.

2.  **서비스 수준 계약** 필드에서 할당할 SLA를 선택합니다.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>서비스 계약 그룹에 서비스 수준 계약 적용

1.  **서비스 관리** \> **설정** \> **서비스 계약** \> **서비스 계약 그룹** 을 클릭합니다.

2.  **서비스 수준 계약** 필드에서 할당할 SLA를 선택합니다.

## <a name="track-time-on-a-service-order-against-an-sla"></a>SLA에 대한 서비스 주문 시간 추적

SLA가 할당된 서비스 계약에 대한 새 서비스 주문을 생성하면 서비스 제공을 위한 시간 간격이 시작되고 시스템이 제공 시간을 추적하기 시작합니다. 여기에 각 행에 대해 다음 옵션을 설정할 수 있습니다.

  - 서비스 주문에 소요된 총 시간을 등록하기 위해 서비스 주문에 대한 시간 기록을 시작 및 중지할 수 있습니다.

  - 서비스 수준 계약에 설정된 시간 간격의 준수 여부를 모니터링할 수 있습니다.

  - 서비스 수준 계약의 시간 간격을 초과하는 경우 설정해야 하는 이유 코드를 정의할 수 있습니다.

## <a name="see-also"></a>참고 항목

[서비스 수준 계약 준수 보기](view-compliance-with-service-level-agreements.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]