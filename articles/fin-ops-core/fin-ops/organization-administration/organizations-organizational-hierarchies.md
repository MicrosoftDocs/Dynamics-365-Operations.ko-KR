---
title: 조직 및 조직 계층 개요
description: 조직 계층은 비즈니스를 구성하는 조직 간의 관계를 나타냅니다.
author: sericks007
ms.date: 01/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.custom:
- "17291"
- intro-internal
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8e8f2c2004582f42c3f464fedf9f3d049b5278f
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460843"
---
# <a name="organizations-and-organizational-hierarchies-overview"></a>조직 및 조직 계층 개요

[!include [banner](../includes/banner.md)]

조직은 비즈니스 프로세스를 수행하거나 목표를 달성하기 위해 함께 일하는 사람들의 그룹입니다. 조직 계층은 비즈니스를 구성하는 조직 간의 관계를 나타냅니다.

## <a name="organizations"></a>조직

법인, 운영 단위 및 팀과 같은 내부 조직 유형을 정의할 수 있습니다.

모든 내부 조직은 **파티** 엔터티 유형입니다. 따라서 이러한 조직에서는 주소록을 사용하여 주소 및 연락처 정보를 저장합니다. 개인 또는 조직이 될 수 있는 당사자는 하나 이상의 주소록에 속할 수 있습니다.

### <a name="legal-entities"></a>법인

법인은 등록되거나 입법화된 법적 구조를 가진 조직입니다. 법인은 법적 계약을 체결할 수 있으며 성과에 대해 보고하는 진술서를 준비해야 합니다.

회사는 일종의 법인입니다. 현재 회사는 만들 수 있는 유일한 법인 유형이며 모든 법인은 회사 ID와 연결되어 있습니다. 이 연결은 프로그램의 일부 기능 영역이 데이터 모델에서 회사 ID 또는 DataAreaId를 사용하기 때문에 존재합니다. 이러한 기능 영역에서 회사는 데이터 보안의 경계로 사용됩니다. 사용자는 현재 로그온한 회사의 데이터에만 액세스할 수 있습니다.

### <a name="operating-units"></a>운영 단위

운영 단위는 비즈니스에서 경제적 자원의 통제와 운영 프로세스를 나누는 데 사용되는 조직입니다. 운영 단위의 사람들은 희소한 자원의 사용을 최대화하고 프로세스를 개선하며 자신의 성과를 설명할 의무가 있습니다.

운영 단위의 유형에는 비용 센터, 사업부, 가치 흐름, 부서 및 상거래 채널이 포함됩니다. 다음 표는 각 조작 단위 유형에 대한 자세한 정보를 제공합니다.

| 운영 단위 유형 | 설명 | 목적 |
|---------------------|-------------|---------|
| Cost center         | 관리자가 예산 및 실제 지출에 대해 책임을 지는 운영 단위입니다. | 법인에 걸친 비즈니스 프로세스의 관리 및 운영 제어에 사용됩니다. |
| 사업부       | 전략적 비즈니스 목표를 달성하기 위해 생성된 반자율적 운영 단위입니다. | 조직이 법인과 독립적으로 서비스하는 산업 또는 제품 라인을 기반으로 하는 재무 보고에 사용됩니다. |
| 가치 흐름        | 하나 이상의 생산 흐름을 통제하는 운영 단위. | 일반적으로 린 제조에서 소비자에게 제품이나 서비스를 공급하는 데 필요한 활동과 흐름을 제어하는 데 사용됩니다. |
| 부서          | 영업 또는 회계와 같은 특정 작업을 수행하는 조직의 범주 또는 기능적 부분을 나타내는 운영 단위입니다. | 기능 영역에 대한 보고에 사용됩니다. 부서는 손익 책임이 있을 수 있으며 비용 센터 그룹으로 구성될 수 있습니다. |
| 소매 채널      | 오프라인 상점, 온라인 상점 또는 콜 센터를 나타내는 운영 단위입니다. | 법인 내부 또는 전체에 걸쳐 하나 이상의 매장을 관리 및 운영하는 데 사용됩니다. |

### <a name="teams"></a>팀

팀은 구성원이 공통의 책임, 관심 또는 목표를 공유하는 조직입니다. 조직 계층에서는 팀을 사용할 수 없습니다.

## <a name="organizational-hierarchies"></a>조직 계층 구조

조직 계층을 설정하여 다양한 관점에서 비즈니스를 보고 보고합니다. 예를 들어 세금, 법인 또는 법정 보고를 위해 법인 계층을 설정할 수 있습니다. 법적으로 요구되지는 않지만 내부 통제에 사용되는 재무 정보를 보고하기 위해 운영 단위를 기반으로 하는 계층을 설정합니다. 예를 들어 구매 계층을 생성하여 구매 정책, 규칙 및 비즈니스 프로세스를 제어할 수 있습니다.

> [!NOTE]
> 운영 단위가 계층에 추가된 후에는 운영 단위를 삭제할 수 없습니다. 

각 계층에는 목적이 할당됩니다. 계층 구조의 목적은 계층 구조에 포함될 수 있는 조직 유형을 결정합니다. 목적에 따라 계층 구조를 사용할 수 있는 응용 프로그램 시나리오도 결정됩니다.

계층 구조의 조직은 매개변수, 정책 및 트랜잭션을 공유할 수 있습니다. 조직은 상위 조직의 매개변수를 상속하거나 재정의할 수 있습니다. 단, 제품, 주소록 등의 공유 마스터 데이터는 전체 조직에 적용되며, 개별 조직에 대해서는 무시할 수 없습니다. 조직과 계층을 생성하려면 신중한 계획이 필요합니다. 자세한 내용은 [조직 계층 계획](plan-organizational-hierarchy.md)을 참조하세요.

## <a name="additional-resources"></a>추가 리소스
- [조직 계층 구조 계획](plan-organizational-hierarchy.md)
- [조직 계층 구조 만들기](tasks/create-organization-hierarchy.md)
- [법인 만들기](tasks/create-legal-entity.md)
- [운영 단위 만들기](tasks/create-operating-unit.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
