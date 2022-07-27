---
title: 공급업체 카탈로그 가져오기
description: 이 토픽에서는 공급업체 카탈로그 데이터를 가져오는 프로세스에 대해 설명합니다.
author: Henrikan
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: henrikan
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: fb7e9735ac29fae50a4a3874b713a9a75799605c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448303"
---
# <a name="import-vendor-catalogs"></a>공급업체 카탈로그 가져오기

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>공급업체 카탈로그 가져오기

Dynamics 365 Supply Chain Management에서는 구매 전문가가 사내에서 사용하기 위한 물품 및 서비스를 주문할 때 회사 직원이 사용할 카탈로그를 만들고 유지 관리할 수 있습니다. 조달 카탈로그를 만들려면 제품 카탈로그 데이터를 가져오거나 제품 카탈로그 데이터를 제품 마스터에 수동으로 추가하여 직원이 사용할 수 있도록 하려는 항목 및 서비스를 추가할 수 있습니다. 

Microsoft Dynamics 365 클라이언트에서 공급업체가 제출한 카탈로그 데이터를 업로드할 수 있습니다.

공급업체가 카탈로그 유지 관리 요청(CMR) 파일 형식으로 귀하에게 제출하는 제품 데이터는 XML 파일 형식이어야 합니다. CMR 파일에는 공급업체가 귀사에 공급하는 제품에 대한 세부 정보가 포함되어야 합니다.

## <a name="import-vendor-catalog-data"></a>공급업체 카탈로그 데이터 가져오기

공급업체 카탈로그 데이터를 가져오려면 다음 작업을 완료해야 합니다.

1. 데이터 매핑 규칙을 정의한 데이터 관리 작업 영역에서 프로젝트를 설정합니다. **데이터 관리** 를 선택한 다음 **데이터 프로젝트에 대한 역할 설정** 을 선택합니다.

2. 조달 범주 계층을 설정하고 공급업체를 조달 범주에 지정합니다. 상품 코드를 사용하는 경우 상품 코드를 조달 범주에 추가합니다. 조달 범주 계층 구조 설정에 대한 자세한 내용은 [조달 범주 계층 구조 설정](../procurement/tasks/set-up-procurement-category-hierarchy.md)을 참조하세요.

3. 카탈로그 가져오기를 위해 공급업체를 구성합니다. 공급업체를 선택한 다음 **조달** > **설정** > **카탈로그 가져오기를 위한 공급업체 구성** 을 선택합니다.

4. 카탈로그 가져오기에 대한 워크플로를 구성합니다. CMR 파일 템플릿을 만들고 이를 공급업체와 공유합니다.

5. **조달 및 소싱** \> **공통** \> **카탈로그** \> **공급업체 카탈로그** 를 선택하여 공급업체 카탈로그를 생성합니다. 공급업체로부터 받은 CMR(카탈로그 유지 관리 요청) 파일은 이 카탈로그에 그룹화되어 있습니다. 

6. CRM 파일을 업로드합니다.

7. 공급업체 카탈로그의 제품을 검토, 승인 또는 거부합니다. 제품은 조달 범주에 자동으로 매핑됩니다. 

승인된 제품은 제품 마스터에 추가되고 선택한 법인에 릴리스됩니다. 승인된 제품만 조달 카탈로그에 추가할 수 있습니다.

## <a name="generate-a-catalog-import-file-template"></a>카탈로그 가져오기 파일 템플릿 생성

카탈로그 가져오기 파일 템플릿은 공급업체 제품에 대한 CMR 파일을 만드는 데 사용하는 XSD 파일입니다. CMR 파일을 사용하여 새 카탈로그를 생성하거나 기존 카탈로그를 교체하거나 기존 카탈로그를 수정할 수 있습니다.

1. **조달 및 소싱** \> **카탈로그** \> **공급업체 카탈로그** 를 선택하고 작업할 카탈로그를 더블 클릭합니다.

2. 현재 카탈로그 가져오기 템플릿(XSD 파일)을 다운로드합니다. **카탈로그 업데이트** 페이지의 **작업 창** 에 있는 **카탈로그** 탭에 있는 **관련 정보** 그룹에서 **카탈로그 템플릿 생성** 을 클릭하고 **조달 범주** 를 선택합니다.

    - **조달 범주** 옵션을 사용하면 공급업체가 제품을 제공할 권한이 있는 조달 범주를 포함하는 카탈로그 템플릿을 생성할 수 있습니다.

3. **다른 이름으로 저장** 대화 상자에서 카탈로그 파일 템플릿을 저장할 위치를 선택하고 파일을 저장합니다.

자세한 내용과 예는 블로그 게시물 [Dynamics AX의 공급업체 카탈로그](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]