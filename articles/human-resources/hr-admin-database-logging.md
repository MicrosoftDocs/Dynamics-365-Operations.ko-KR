---
title: 데이터베이스 로깅 구성 및 관리
description: 데이터베이스 로깅을 사용하여 Dynamics 365 Human Resources의 테이블 및 필드에 대한 변경 사항을 추적할 수 있습니다.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3cbe4c105b14935db6803e4bded0d891c564fb81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452239"
---
# <a name="configure-and-manage-database-logging"></a>데이터베이스 로깅 구성 및 관리


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

데이터베이스 로깅을 사용하여 Dynamics 365 Human Resources의 테이블 및 필드에 대한 변경 사항을 추적할 수 있습니다. 이 항목에서는 다음 작업 방법을 설명합니다.

- 데이터베이스 로깅을 위한 보안 및 성능 관리
- 데이터베이스 로깅 설정
- 데이터베이스 로그 정리

## <a name="overview-of-database-logging"></a>데이터베이스 로깅 개요

데이터베이스 로깅은 Microsoft Dynamics 365 Human Resources 테이블 및 필드에 대한 특정 변경 사항을 추적합니다. 이러한 변경에는 삽입, 업데이트 또는 삭제가 포함됩니다. 데이터베이스 로깅은 데이터베이스 로그 테이블의 테이블이나 필드에 대한 변경 기록을 저장합니다.

데이터베이스 로깅의 비즈니스 용도는 다음과 같습니다.

- 중요한 정보가 포함된 특정 테이블의 변경 사항에 대한 감사 레코드 생성
- 단일 거래 추적 데이터베이스 로깅은 일괄 작업으로 실행되는 자동화된 트랜잭션을 추적하기 위한 기능이 아닙니다.

## <a name="security-for-database-logging"></a>데이터베이스 로깅을 위한 보안

데이터베이스 로그에는 중요한 데이터가 포함될 수 있습니다. 로그 데이터에 액세스해야 하는 보안 역할만 액세스할 수 있게 제한하세요.

## <a name="database-logging-and-performance"></a>데이터베이스 로깅 및 성능

데이터베이스 로깅은 비즈니스 관점에서는 유용하지만 리소스 사용 및 관리에 큰 비용이 소요될 수 있습니다. 데이터베이스 로깅의 성능에 대한 영향은 다음과 같습니다.

- 데이터베이스 로그 테이블은 빠르게 커져서 데이터베이스 크기를 증가시킬 수 있습니다. 얼마나 증가할지는 유지하는 로깅 데이터의 양에 따라 다릅니다. 기본적으로 데이터베이스 로그 테이블은 30일 동안의 로그 데이터만 유지합니다. 

- 데이터베이스 로깅은 장기 데이터 가져오기와 같이 장기 자동화 프로세스에 부정적인 영향을 미칠 수 있습니다.

### <a name="best-practices"></a>모범 사례

성능을 향상하려면 전체 테이블 대신 기록할 특정 필드를 선택하여 로그 항목을 제한하세요. 전반적인 성능을 유지하기 위해 데이터베이스 로깅은 20개의 테이블로 제한됩니다.

> [!NOTE]
> 개별 필드에 대한 업데이트만 기록할 수 있습니다.

## <a name="set-up-database-logging"></a>데이터베이스 로깅 설정

**데이터베이스 변경 사항 로깅** 마법사를 사용하여 데이터베이스 로깅을 설정할 수 있습니다. 마법사는 테이블 또는 필드에 대한 로깅을 설정하는 유연한 방법을 제공합니다.

1. **시스템 관리 > 연결 > 데이터베이스 > 데이터베이스 로그 설정** 으로 이동합니다. **새로 만들기** 를 선택하여 **데이터베이스 변경 사항 로깅** 마법사를 시작합니다.
2. **다음** 을 선택합니다. 
3. 마법사의 **테이블 및 필드** 페이지에서 데이터베이스 로깅을 활성화할 테이블과 필드를 선택하고 **다음** 을 선택합니다.

   > [!Note]
   > Human Resources 데이터베이스의 모든 테이블에 데이터베이스 로깅을 사용할 수 있는 것은 아닙니다. 목록 아래의 **모든 테이블 표시** 를 선택하면 테이블 및 필드 목록이 확장되어 데이터베이스 로깅을 사용할 수 있는 모든 데이터베이스 테이블이 표시되지만 이는 전체 데이터베이스 테이블 목록의 하위 집합입니다.

4. 마법사의 **변경 유형** 페이지에서 각 테이블 및 필드에 대한 변경 내용을 추적할 데이터 작업을 선택하고 **다음** 을 선택합니다. 로깅에 사용할 수 있는 데이터 작업에 대한 설명은 아래 표를 참조하세요.
5. **마침** 페이지에서 변경 사항을 검토하고 **마침** 을 선택합니다.

| 작업 | 설명 |
| -- | -- |
| 새 거래 추적 | 테이블에 생성된 새 레코드에 대한 로그를 생성합니다. |
| 업데이트 | 테이블 레코드의 업데이트 또는 테이블에서 개별적으로 선택한 필드의 업데이트에 대한 로그를 생성합니다. 테이블에 대한 업데이트를 기록하도록 선택하면 테이블에 있는 레코드의 필드가 업데이트될 때마다 로그 레코드가 생성됩니다. 특정 필드에 대한 업데이트를 기록하도록 선택하면 테이블 레코드의 해당 필드가 업데이트될 때만 로그 레코드가 생성됩니다. |
| 삭제 | 테이블에서 삭제된 레코드에 대한 로그를 생성합니다. |
| 키 이름 바꾸기 | 테이블 키의 이름이 변경될 때 로그 레코드를 만듭니다. |


## <a name="clean-up-database-logs"></a>데이터베이스 로그 정리

다음 옵션을 사용하여 데이터베이스 로그의 전체 또는 일부를 삭제할 수 있습니다.

- 특정 테이블의 모든 로그를 선택합니다.
- 특정 유형의 데이터베이스 로그를 선택합니다.
- 로그가 생성된 날짜와 시간을 선택합니다.

데이터베이스 로그 정리를 설정하려면 다음 단계를 따릅니다. 

1. **시스템 관리 > 연결 > 데이터베이스 > 데이터베이스 로그** 로 이동합니다. **로그 정리** 를 선택합니다.
2. **포함할 레코드** 헤더에서 **필터** 를 선택합니다.
3. 삭제할 로그를 선택할 방법을 선택합니다. 다음 옵션 중 하나를 입력합니다.

   - 테이블 ID
   - 로그 유형
   - 생성 날짜 및 시간

4. **데이터베이스 로그 정리** 탭을 사용하여 로그 정리 작업을 실행할 시기를 결정합니다. 기본적으로 데이터베이스 로그는 30일 동안 사용할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]