---
title: 전체 주소록 및 기타 주소록 계획
description: 이 항목에서는 계획 프로세스 중에 내려야 하는 고려 사항과 결정 사항에 대해 설명합니다.
author: msftbrking
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b3f6a74c217b0cc7cec784ca6a964ab2caae0c7e9438aee2cc82987a508d63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460605"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>전체 주소록 및 기타 주소록 계획

[!include [banner](../includes/banner.md)]

이 항목에서는 전체 주소록 및 추가 주소록을 설정 및 구성하기 전에 계획 프로세스 동안 수행해야 하는 고려 사항 및 결정에 대해 설명합니다. 일부 결정에서는 조직 계층 구조와 같은 제품의 다른 영역에 대해 내린 결정을 확인해야 합니다.

## <a name="global-address-book"></a>전체 주소록

전체 주소록 작업을 시작하기 전에 해당 주소록의 기본값을 결정해야 합니다. 이 기본값은 생성하는 추가 주소록에 사용됩니다.

**결정**

- **사람** 유형의 파티 기록에 대해 어떤 순서로 이름을 표시해야 합니까? 예를 들어, 하나의 시퀀스는 성, 중간 이름, 이름입니다.
- 역할 기록이 삭제되면 주소록에서 당사자 기록을 삭제해야 합니까? 예를 들어 고객 기록이 삭제되면 당사자 기록도 삭제되어야 합니까?
- 새 레코드가 생성될 때 전체 주소록에서 중복 레코드가 발견되면 사용자에게 알려야 합니까?
- DUNS(Data Universal Numbering System) 번호가 당사자 기록 정보에 포함되어야 합니까?
- 파티 기록에 DUNS 수가 포함되어 있으면 번호의 고유성을 확인해야 합니까?
- 전체 주소록에 당사자 레코드가 생성될 때 기본 당사자 유형, 개인 또는 조직을 원하십니까?
- 당사자 기록의 개인 주소 및 연락처 정보에 액세스할 수 있는 사용자 역할은 무엇입니까?

## <a name="additional-address-books"></a>추가 주소록

전체 주소록을 만든 후 필요에 따라 조직의 각 회사 또는 각 비즈니스 라인에 대한 별도의 주소록과 같은 추가 주소록을 만들 수 있습니다. 예를 들어, Fabrikam은 여러 회사와 여러 비즈니스 라인이 있는 국제 조직입니다. Fabrikam은 각 비즈니스 라인에 대한 주소록을 만들 계획입니다. 공압 도구 비즈니스와 같이 둘 이상의 위치에서 발생하는 비즈니스 라인의 경우 Fabrikam은 각 위치에 대한 주소록을 만들 계획입니다. Fabrikam의 IT 관리자인 Chris는 필요한 주소록 목록을 다음과 같이 만들었습니다. 이 목록은 또한 각 주소록에 포함되어야 하는 당사자 기록에 대해 설명합니다.

- **공공 부문 계약(PubSC)** – Fabrikam이 보유하고 있는 공공 부문 계약에 관련된 모든 당사자의 당사자 기록.
- **민간 부문 계약(PriSC)** – Fabrikam이 보유하고 있는 민간 부문 계약에 관련된 모든 당사자의 당사자 기록.
- **전자 도구(ET)** – 전자 도구의 구매 또는 판매에 관여하거나 Fabrikam-Japan 회사에서 Fabrikam이 제공하거나 구매한 전자 도구와 상호 작용하는 모든 당사자의 당사자 기록.
- **공압 도구(PTJPN)** – 공압 도구의 구매 또는 판매에 관여하거나 Fabrikam-Japan 회사에서 Fabrikam이 제공하거나 구매한 공압 도구와 상호 작용하는 모든 당사자의 당사자 기록.
- **공압 도구(PTUSA)** – 공압 도구의 구매 또는 판매에 관여하거나 Fabrikam-US 회사에서 Fabrikam이 제공하거나 구매한 공압 도구와 상호 작용하는 모든 당사자의 당사자 기록.

**결정:**

- 추가 주소록을 몇 개나 만드시겠습니까?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]