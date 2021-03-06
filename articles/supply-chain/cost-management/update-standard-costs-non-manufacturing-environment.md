---
title: 비제조 환경에서 표준 비용 업데이트
description: 이 문서에서는 비제조 환경에서 표준 비용을 업데이트하기 위한 지침을 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 139c72fc60330427336de872d7c9730fd12e291f8cad3f7327380b2003535d78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447094"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>비제조 환경에서 표준 비용 업데이트

[!include [banner](../includes/banner.md)]

이 문서에서는 비제조 환경에서 표준 비용을 업데이트하기 위한 지침을 제공합니다.

다음 지침에서는 표준 비용을 업데이트하기 위해 두 가지 버전의 접근 방식을 사용한다고 가정합니다. 이 접근 방식에서 한 원가 계산 버전에는 동결 기간에 대해 원래 정의된 표준 원가가 포함되고 두 번째 원가 계산 버전에는 증분 업데이트가 포함됩니다. 각 업데이트는 두 번째 비용 계산 버전에 포함된 비용 레코드로 입력되고 결국 활성화됩니다. 대안적인 단일 버전 접근 방식은 원래 정의된 일련의 표준 비용을 사용합니다. 두 가지 버전 접근 방식을 사용하려면 두 번째 원가 계산 버전을 정의해야 합니다. 다음은 이 원가계산 버전을 정의하기 위한 지침입니다.

-   **표준 비용** 의 원가 계산 유형을 지정합니다.
-   **2016-UPDATES** 와 같이 비용 산정 버전의 내용을 나타내는 중요한 식별자를 할당합니다.
-   콘텐츠에 비용 레코드가 포함되어 있는지 확인합니다.
-   모든 사이트에 대해 비용 레코드를 입력할 수 있습니다. 사이트를 지정하면 해당 사이트에 대해서만 비용 기록을 입력할 수 있습니다.
-   **없음** 의 대체 원칙을 나타냅니다. 대체 원칙은 제조 품목에 대한 비용 계산에만 적용됩니다.

새 항목에 대한 표준 비용을 수정, 조정 또는 업데이트하려면 다음 단계를 따르세요.

1.  **원가 계산 버전** **설정** 페이지를 사용하여 비용 데이터를 두 번째 원가 계산 버전에 입력할 수 있습니다. 선택적으로 보류 비용의 활성화를 방지하여 보류 비용이 완전하고 정확하게 정의된 후에 활성화가 허용됩니다. 선택적으로 **시작 날짜** 필드에 날짜를 입력할 수도 있습니다. 일반적인 지침으로 증분 업데이트를 활성화하려는 날짜를 사용하세요. 또는 원가 계산 버전의 **시작 날짜** 필드를 공백으로 두고 각 비용 레코드의 **시작 날짜** 필드에 날짜를 입력합니다.
2.  **항목 가격** 페이지를 사용하여 두 번째 원가 계산 버전에 포함된 항목 원가 레코드로 업데이트를 입력합니다.
3.  **품목 가격** 보고서를 사용하여 두 번째 원가 계산 버전에 포함된 품목 원가 레코드의 완전성과 정확성을 확인합니다.
4.  **원가 계산 버전 유지 관리** 페이지를 사용하여 차단 플래그를 변경하여 두 번째 원가 계산 버전에 포함된 보류 중인 비용 레코드의 활성화를 허용합니다.
5.  **가격 활성화** 페이지(**원가 계산 버전 유지 관리** 페이지에서 열림)를 사용하여 두 번째 비용 계산 버전에 포함된 모든 보류 중인 항목 비용 레코드를 활성화합니다. **항목 가격** 페이지에서 **보류 중인 가격 활성화** 버튼을 클릭하여 개별 항목에 대한 보류 중인 비용 레코드를 활성화할 수도 있습니다.
6.  추가 데이터 유지 관리를 방지하려면 **원가 계산 버전 설정** 페이지를 사용하여 두 번째 원가 계산 버전에 포함된 차단 플래그를 변경합니다. 차단 정책은 새로운 보류 비용의 입력과 보류 비용의 활성화를 방지합니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]