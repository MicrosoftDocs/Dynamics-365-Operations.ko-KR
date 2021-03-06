---
title: 서비스 작업 개요
description: 서비스 작업을 사용하여 서비스 주문 중에 완료할 작업을 설명합니다. 기술자와 고객 모두 이 정보를 볼 수 있습니다.
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a789c435bfba6948895f6d00c6a350c03b2e9d63
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449647"
---
# <a name="service-tasks-overview"></a>서비스 작업 개요

[!include [banner](../includes/banner.md)]

서비스 작업을 사용하여 서비스 주문 중에 완료할 작업을 설명합니다.
기술자와 고객 모두 이 정보를 볼 수 있습니다.

**서비스 작업** 페이지에서 서비스 작업을 만들고 서비스 작업 관계를 만들어 서비스 작업을 특정 서비스 계약 또는 서비스 주문과 연결합니다. 서비스 작업 관계를 생성할 때마다 다음을 생성할 수 있습니다.

-  기술자가 알아야 하는 중요한 작업과 관련된 자세한 기술 요청과 같은 작업에 대한 내부 메모입니다.

-  고객이 볼 수 있는 외부 메모입니다. 이는 고객과 서비스 회사 간의 계약에 따라 완료되는 작업에 대해 덜 기술적인 설명을 제공할 수 있습니다.

서비스 작업과 서비스 주문 또는 서비스 계약 간의 서비스 작업 관계를 설정한 경우 현재 서비스 주문 또는 서비스 계약에 대한 서비스 주문 라인 또는 서비스 계약 라인을 생성할 때 이 서비스 작업을 지정할 수 있습니다.

서비스 계약에서 서비스 주문을 생성할 때 각 서비스 계약 라인에 지정된 서비스 작업을 사용하여 서비스 주문 라인을 서비스 주문으로 그룹화할 수 있습니다.

## <a name="create-a-service-task"></a>서비스 작업 만들기

1. **서비스 관리** \> **설정** \> **서비스 작업** 을 클릭합니다.
2. 새 라인을 만듭니다.
3. 서비스 ID 및 설명을 입력합니다.

## <a name="example"></a>예

기술자는 고객 사이트에서 기어박스(서비스 개체 GB-1234)에 대해 두 가지 작업을 완료해야 합니다. 고객에 대한 서비스 계약이 생성되고 여러 트랜잭션이 작업과 연결됩니다. 두 작업에 대한 서비스 계약 및 서비스 계약 라인은 다음과 같습니다.

### <a name="service-agreement"></a>서비스 계약

| 프로젝트  | 서비스 계약 | 설명                                  | 그룹   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | 검사 및 일상적인 교체 – GB-1234 | 프리미엄 |

### <a name="service-agreement-lines"></a>서비스 계약 라인

| 설명             | 트랜잭션 유형 | 서비스 개체 | 서비스 작업 |
|-------------------------|------------------|----------------|--------------|
| 검사 및 청소 | 시간             | GB-1234        | I/C - GB1234 |
| 여행                  | 경비          | GB-1234        | I/C - GB1234 |
| 자재               | 항목             | GB-1234        | I/C - GB1234 |
| 일상적인 교체     | 시간             | GB-1234        | RR - GB1234  |
| GR-1                    | 항목             | GB-1234        | RR - GB1234  |
| GR-5                    | 항목             | GB-1234        | RR - GB1234  |

두 작업에 대한 서비스 계약 라인에는 두 개의 서비스 작업이 첨부되어 있습니다. 서비스 작업은 각 작업에 속하는 트랜잭션을 결정합니다. 첫 번째 경우 서비스 작업 I/C - GB1234는 개체 GB-1234의 검사 및 청소와 관련된 모든 서비스 계약 라인을 식별합니다. 두 번째 경우, 서비스 작업 RR - GB1234는 일상적인 교체 작업을 완료하는 데 관련된 모든 서비스 계약 라인을 식별합니다.

서비스 작업을 특정 계약과 연결하는 서비스 작업 관계는 다음과 같습니다.

### <a name="service-tasks"></a>서비스 작업

| 서비스 작업 | 설명                             | 내부 메모                                                                                                                 | 외부 메모                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | 기어박스 GB-1234 검사           | 기어박스 GB-1234의 육안 및 기계적 검사 및 청소                                                              | 일상적인 기어박스 검사 |
| RR - GB1234  | GB-1234의 정기 부품 교체 | GR-1 및 GR-5 구성 요소의 정기 서비스 교체(2002년 이전에 제조된 기어박스의 경우 GR-2 구성 요소도 교체) | 정기 부품 교체  |

## <a name="group-service-orders"></a>그룹 서비스 주문

서비스 주문을 자동으로 생성할 때 서비스 작업을 그룹화 기준으로 사용할 수 있습니다. 서비스 작업별로 서비스 주문을 그룹화하려면 서비스 계약을 기반으로 하는 서비스 주문을 초기 그룹화 기준으로 서비스 작업 ID별로 그룹화해야 한다고 서비스 계약에 정의합니다.

**서비스 작업별 그룹화**

1. **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 클릭합니다.
2. **설정** 탭의 **서비스 주문 결합** 필드에서 **서비스 작업별** 을 선택합니다.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]