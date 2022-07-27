---
title: 세금 계산 구성을 위한 마스터 데이터 조회 활성화
description: 이 항목에서는 세금 계산 마스터 데이터 조회 기능을 설정하고 활성화하는 방법을 설명합니다.
author: kai-cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 455e8becfdfa910a3733719653e1a91557b2f59a
ms.sourcegitcommit: ac23a0a1f0cc16409aab629fba97dac281cdfafb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2021
ms.locfileid: "8451204"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>세금 계산 구성을 위한 마스터 데이터 조회 활성화 

[!include [banner](../includes/banner.md)]

이 항목에서는 세금 계산 마스터 데이터 조회 기능을 설정하고 활성화하는 방법을 설명합니다. 드롭다운 목록은 **법인**, **공급업체 계정**, **품목 코드** 및 **배달 조건** 과 같은 필드에 대한 세금 계산 구성의 값을 선택할 수 있습니다. 이러한 값은 Microsoft Dataverse 데이터 원본을 사용하여 연결된 Microsoft Dynamics 365 Finance 환경에서 가져옵니다.

> [!NOTE] 
> 세금 계산 마스터 데이터 조회 기능은 선택적 기능입니다. Regulatory Configuration Service(RCS)에서 **세금 서비스 Dataverse 데이터 원본 지원** 기능을 비활성화하면 다음 단계를 건너뛸 수 있습니다. 그러나 이 경우 세금 계산 구성에서 드롭다운 목록을 사용할 수 없습니다.

1. Microsoft Dynamics Lifecycle Services(LCS)에서 Microsoft Power Platform 통합을 설정합니다. 자세한 내용은 [Microsoft Power Platform 통합 - 추가 기능 개요](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)를 참조하세요. 이 단계를 완료하면 Microsoft Power Platform 환경의 이름이 **Power Platform 통합** 섹션에 나타납니다.
2. [Microsoft Power Platform 관리 센터](https://admin.powerplatform.microsoft.com/environments)로 이동하고 환경 이름을 선택합니다. 환경 URL이 제공됩니다.
3. Dynamics 365 Finance 및 Dataverse를 설정합니다. 자세한 내용은 [가상 엔터티 솔루션 얻기](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) 및 [인증 및 권한 부여](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization)를 참조하세요.
4. 다음 엔터티를 설정합니다. 자세한 내용은 [Microsoft Dataverse 가상 엔터티 활성화](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md)를 참조하세요.

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. RCS(Regulatory Configuration Service)를 설정합니다. **기능 관리** 작업 영역에서 다음 기능을 열고 활성화해야 합니다.

    - 전자 보고 Dataverse 데이터 원본 지원
    - 세금 서비스 Dataverse 데이터 원본 지원
    - 세계화 기능

6. 테넌트 관리자 계정을 사용하여 RCS에 로그인합니다.
7. **전자 보고** > **연결된 애플리케이션** 으로 이동합니다. 
8. **새로 만들기** 를 선택하고 다음 필드 정보를 입력합니다. 

    - **이름** 필드에 이름을 입력합니다.
    - **유형** 필드에서 **Dataverse** 를 선택합니다.
    - **애플리케이션** 필드에 Dataverse URL을 입력합니다.
    - **테넌트** 필드에 테넌트를 입력합니다.
    - **사용자 지정 URL** 필드에 Dataverse URL을 입력하고 "/api/data/v9.1"을 붙입니다.

9. **연결 확인** 을 선택하고 연결 프로세스를 완료합니다. 

    [![연결 버튼 확인.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. **전자 보고** > **세금 구성** 으로 이동하고 [세금 구성](https://go.microsoft.com/fwlink/?linkid=2158352)에서 세금 구성을 가져옵니다.

    [![세금 구성 페이지, 세금 데이터 모델 트리.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. **과세 가능 문서 모델 매핑** 또는 **Dataverse 모델 매핑**(Microsoft 구성을 사용하는 경우)으로 이동하고 **연결된 애플리케이션** 필드에 7단계에서 만든 레코드를 선택합니다.
12. **모델 매핑의 기본값** 을 **예** 로 설정합니다.

    [![모델 매핑 페이지.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
