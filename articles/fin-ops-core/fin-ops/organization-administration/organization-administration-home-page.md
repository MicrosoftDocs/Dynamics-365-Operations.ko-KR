---
title: 조직 관리 홈 페이지
description: 이 항목은 조직에서 도움이 될 리소스를 가리킵니다.
author: sericks007
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "20421"
- intro-internal
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04d188b0bf7d7fc7064467e1e05199d0eb90b4d0276a3c0c01ad8f9be78e76e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460730"
---
# <a name="organization-administration-home-page"></a>조직 관리 홈 페이지

[!include [banner](../includes/banner.md)]

이 항목은 고급 사용자와 관리자가 조직과 비즈니스를 위해 원활하고 효과적으로 작동하도록 시스템을 구성하는 데 도움이 되는 콘텐츠를 가리킵니다.

여기에 나열된 대부분의 콘텐츠는 **조직 관리** 모듈의 기능에 적용됩니다. 그러나 조직을 보다 효율적으로 운영하기 위해 모든 모듈에서 수행할 수 있는 레코드 템플릿 생성 및 사용과 같은 몇 가지 작업이 있습니다.

## <a name="number-sequences"></a>번호 시퀀스

번호 시퀀스는 식별자가 필요한 마스터 데이터 레코드 및 트랜잭션 레코드에 대해 읽을 수 있는 고유 식별자를 생성하는 데 사용됩니다. 식별자가 필요한 마스터 데이터 레코드 또는 트랜잭션 레코드를 *참조* 라고 합니다. 참조에 대한 새 레코드를 생성하려면 먼저 번호 시퀀스를 설정하고 참조와 연결해야 합니다.

- [숫자 시퀀스 개요](number-sequence-overview.md)
- [마법사를 사용하여 숫자 시퀀스 설정](tasks/set-up-number-sequences-wizard.md)(작업 가이드)
- [개별적으로 번호 시퀀스 설정](tasks/set-up-number-sequences-individual-basis.md)(작업 가이드)

## <a name="organizations"></a>조직

조직은 비즈니스 프로세스를 수행하거나 목표를 달성하기 위해 함께 일하는 사람들의 그룹입니다. 조직 계층은 비즈니스를 구성하는 조직 간의 관계를 나타냅니다.

조직 및 조직 계층을 설정하기 전에 비즈니스 모델링 방법을 계획해야 합니다. 조직 모델은 구현 및 비즈니스 프로세스에 상당한 영향을 미칩니다.

- [조직 및 조직 계층 개요](organizations-organizational-hierarchies.md)
- [조직 계층 구조 계획](plan-organizational-hierarchy.md)
- [조직 계층 만들기](tasks/create-organization-hierarchy.md)(작업 가이드)
- [법인 만들기](tasks/create-legal-entity.md)(작업 가이드)
- [운영 단위 생성](tasks/create-operating-unit.md)(작업 가이드)

## <a name="address-books"></a>주소록

전체 주소록은 회사가 상호 작용하는 모든 내부 및 외부 개인 및 조직에 대해 저장해야 하는 마스터 데이터의 중앙 저장소입니다. 당사자 레코드와 연결된 데이터에는 당사자의 이름, 주소 및 연락처 정보가 포함됩니다.

전체 주소록을 만든 후 필요에 따라 조직의 각 회사 또는 각 비즈니스 라인에 대한 별도의 주소록과 같은 추가 주소록을 만들 수 있습니다.

- [전체 주소록 개요](overview-global-address-book.md)
- [전체 주소록 및 기타 주소록 계획](plan-configuration-global-address-book-additional-address-books.md)
- [전체 주소록 구성](tasks/configure-global-address-book.md)
- [주소록 FAQ](qa-address-books.md)

## <a name="workflow"></a>워크플로

워크플로는 개별 워크플로 또는 비즈니스 프로세스를 만드는 데 사용할 수 있는 시스템입니다. 워크플로를 만들 때 작업을 완료하거나 결정을 내리거나 문서를 승인해야 하는 사람을 표시하여 시스템을 통해 문서가 어떻게 흐르거나 이동하는지 지정합니다.

- [워크플로 시스템 개요](overview-workflow-system.md)
- [워크플로 요소](workflow-elements.md)
- [워크플로 승인 프로세스의 작업](workflow-actions.md)
- [워크플로 만들기 개요](create-workflow.md)

## <a name="electronic-signatures"></a>전자 서명

전자 서명은 컴퓨팅 프로세스를 시작하거나 승인하려는 사람의 신원을 확인합니다. 일부 산업에서 전자 서명은 수기 서명만큼 법적 구속력이 있습니다. 전자 서명은 제약, 식품 및 음료, 항공 우주 및 방위 산업과 같은 여러 규제 산업에 대한 규정 준수 요구 사항입니다.

중요한 비즈니스 프로세스에 전자 서명을 사용할 수 있습니다. 일부 프로세스에는 전자 서명 기능이 내장되어 있습니다. 또한 모든 데이터베이스 테이블 및 필드에 대한 사용자 지정 서명 요구 사항을 만들 수 있습니다.

- [전자 서명 개요](electronic-signature-overview.md)
- [전자 서명 설정](tasks/set-up-electronic-signatures.md)(작업 가이드)

## <a name="case-management"></a>사례 관리

사례를 계획, 추적 및 분석하여 유사한 문제에 사용할 수 있는 효율적인 해결 방법을 개발할 수 있습니다. 예를 들어, 고객 서비스 담당자 또는 인사 담당자가 사례를 생성할 때 지식 문서에서 정보를 찾아 사례를 보다 효율적으로 작업하거나 해결할 수 있습니다.

- [케이스 관리 개요](cases.md)
- [사례 범주 보안, 사례 프로세스 및 사례 범주 계획](plan-case-management.md)

## <a name="record-templates"></a>레코드 템플릿

레코드 템플릿을 사용하면 레코드를 더 빠르게 생성할 수 있습니다. 자주 사용되는 필드 값을 각각의 새 레코드에 대해 명시적으로 입력할 필요가 없도록 레코드 템플릿을 생성할 수 있습니다.

- [레코드 템플릿 개요](record-templates.md)
- [데이터 입력을 용이하게 하는 레코드 템플릿 만들기](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md)(작업 가이드)
- [레코드 템플릿을 사용하여 새 레코드 만들기](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md)(작업 가이드)

## <a name="general-organization-administration"></a>일반 조직 관리

- [배너 또는 로고 변경](../get-started/tasks/change-banner-or-logo.md)(작업 가이드)
- [문서 관리 구성](configure-document-management.md)
- [이메일 구성 및 보내기](configure-email.md)
- [날짜/시간 데이터 및 표준 시간대](date-time-zones.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]