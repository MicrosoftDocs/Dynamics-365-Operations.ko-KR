---
title: 잠재 고객의 결제 유도
description: 이 항목에서는 Dynamics 365 Supply Chain Management과 Dynamics 365 Sales 간의 잠재 고객의 결제 유도 솔루션에 대한 개요를 제공합니다.
author: Henrikan
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b96f22d711ce5b34c2f8de5a86caf5f89dd3f337
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449170"
---
# <a name="prospect-to-cash"></a>잠재 고객의 결제 유도

[!include [banner](../includes/banner.md)]

잠재 고객의 결제 유도 솔루션은 Dynamics 365 Supply Chain Management 및 Dynamics 365 Sales에 직접 동기화 기능을 제공합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿은 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름을 가능하게 합니다. 데이터가 흐르는 동안 Sales에서 영업 및 마케팅 활동을 수행할 수 있으며 Supply Chain Management에서 재고 관리를 사용하여 주문 이행을 처리할 수 있습니다. 

잠재 고객의 결제 유도 통합에 대한 자세한 내용은 짧은 YouTube 비디오 [잠재 고객의 결제 유도 통합](https://www.youtube.com/watch?v=AVV9x5x-XCg)을 시청하세요.

현재 버전에서 잠재 고객의 결제 유도 솔루션은 다음 유형의 직접 동기화를 제공합니다.

- [Sales에서 Supply Chain Management의 고객으로 직접 계정 동기화](accounts-template-mapping-direct.md)
- [Supply Chain Management에서 Sales의 제품으로 직접 제품 동기화](products-template-mapping-direct.md)
- [Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화](contacts-template-mapping-direct.md)
- [Sales에서 Supply Chain Management로 직접 판매 견적 헤더 및 라인 동기화](sales-quotation-template-mapping-sales-fin.md)
- [Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화](sales-order-template-mapping-direct-two-ways.md)
- [Supply Chain Management에서 Sales로 직접 판매 송장 헤더 및 라인 동기화](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Supply Chain Management를 위한 시스템 요구 사항
잠재 고객의 결제 유도 통합은 다음 버전에서 지원됩니다.

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3(2017년 12월)

- Dynamics 365 for Finance and Operations, Enterprise Edition(2017년 12월) - 플랫폼 업데이트 12(7.0.4709.41129)가 포함된 애플리케이션 빌드 7.3.11971.56116

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition(2017년 7월)

- Dynamics 365 for Finance and Operations, Enterprise Edition(2017년 7월) - 플랫폼 업데이트 8 포함(플랫폼 빌드 7.0.4565.16212가 있는 애플리케이션 빌드 7.2.11792.56024).
- 다음 핫픽스가 필요합니다.

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – 이 핫픽스를 사용하면 데이터 통합 기능을 통해 Sales에서 Supply Chain Management로 판매 주문을 동기화할 수 있습니다. 또한 몇 가지 다른 개선 사항을 제공합니다.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – 이 핫픽스를 사용하면 데이터 통합 기능을 통해 Supply Chain Management에서 Sales로 판매 주문 라인을 동기화할 수 있습니다.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – 이 핫픽스를 사용하면 데이터 통합 기능을 통해 Supply Chain Management에서 Sales로 판매 주문을 동기화할 수 있습니다.

    > [!NOTE]
    > 설치에는 다른 핫픽스의 변경 사항이 포함되므로 KB4045570만 설치하면 됩니다. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations 버전 1611(2016년 11월)

- Dynamics 365 for Finance and Operations 플랫폼 업데이트 8 이상이 포함된 버전 1611(2016년 11월)

- 다음 핫픽스가 필요합니다.

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Supply Chain Management에서 Sales로 데이터 통합자와 판매 주문 동기화를 활성화합니다. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Supply Chain Management에서 Sales로 데이터 통합자와 판매 주문 헤더 및 라인 동기화를 활성화합니다.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - 데이터 엔터티를 통한 잠재 고객의 결제 유도 통합에 대한 지원이 필요합니다.
    
    > [!NOTE]
    > 핫픽스를 설치한 후 **SalesPopulateProspectToCash** 양식에서 다음 일괄 작업을 트리거해야 합니다. 이 양식은 한 번만 필요하므로 숨겨져 있습니다. 양식에 액세스하려면 환경에 로그인하고 브라우저 주소의 URL에 다음을 추가하세요. *&mi=action:SalesPopulateProspectToCash*, 예를 들어, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. 양식이 열리면 확인을 클릭합니다. 이렇게 하면 **SalesLine**, **SalesQuotationLine** 및 **CustInvoiceTrans** 테이블의 새 **LineCreationSequnceNumber** 필드가 고유한 값으로 채워지고 제품 목록이 새로 고쳐집니다. 이것은 잠재 고객의 결제 유도 통합이 작동하는 데 필요합니다.


## <a name="system-requirements-for-sales"></a>Sales를 위한 시스템 요구 사항

잠재 고객의 결제 유도 솔루션을 사용하려면 다음 구성 요소를 설치해야 합니다.

- Dynamics 365 Sales 버전 1612(8.2.1.207) (DB 8.2.1.207) 온라인 또는 이후 버전
- Dynamics 365 Sales용 P2C(Prospect to Cash) 솔루션, 버전 1.15.0.0 이상 버전. 솔루션은 AppSource에서 다운로드할 수 있습니다. [Dynamics 365, Prospect to Cash 다운로드 ](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]