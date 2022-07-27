---
title: PunchOut 전자 조달을 위한 외부 카탈로그 사용
description: 이 토픽에서는 외부 카탈로그를 사용하여 구매요청을 생성하고 제출하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b236a17a7f93bfeb60d64fa25745bd1b4cb1b34b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449068"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>PunchOut 전자 조달을 위한 외부 카탈로그 사용

[!include [banner](../includes/banner.md)]

PunchOut 전자 조달을 위한 외부 카탈로그를 사용하면 자신의 마스터 데이터에서 공급업체 제품에 대한 정보를 유지할 필요가 없습니다. 대신, 공급업체 웹사이트의 장바구니가 올바른 제품 정보가 있는 구매요청 라인으로 변환됩니다. 

자신의 제품 마스터 데이터에서 공급업체 제품의 설명과 가격을 유지하는 것을 피해야 합니다. 대신 PunchOut 전자 조달을 위한 외부 카탈로그를 사용합니다. 그런 다음 직원이 구매요청을 생성할 때 공급업체의 외부 카탈로그 사이트로 "펀치아웃"할 수 있습니다(즉, 시스템을 떠나 공급업체 사이트로 이동). 그런 다음 공급업체 웹사이트의 장바구니에 추가된 제품을 구매요청 라인으로 변환할 수 있습니다. 따라서 올바른 제품 정보(제품 ID, 이름, 가격 등)를 얻을 수 있습니다.

외부 카탈로그를 사용하려면 직원이 **내 구매 요청** 페이지에서 요청을 생성해야 합니다.

요청서를 작성하는 직원을 요청서 작성자라고 합니다. 작성자는 다음 작업을 완료할 수 있습니다.

**외부 카탈로그** 라인 작업을 사용하여 지정된 요청자, 구매 법인 및 수신 운영 단위에 사용할 수 있는 모든 외부 카탈로그가 포함된 페이지를 엽니다.

권한에 따라 요청자, 구매 법인 및 수신 운영 단위를 변경하세요. 이러한 값을 변경하면 요청자가 사용할 수 있는 외부 카탈로그 목록이 변경될 수 있습니다. 사용 가능한 외부 카탈로그는 구매 법인 또는 수신 운영 단위에 대한 현재 활성 구매 정책에 따라 다릅니다. 이러한 정책은 특정 조달 범주에 대한 액세스를 허용하거나 금지할 수 있습니다. 따라서 이러한 조달 범주에 매핑된 외부 카탈로그 목록이 영향을 받을 수 있습니다.

정책에 대한 자세한 내용은 [구매 정책 개요](../procurement/purchase-policies.md)를 참조하세요.

- 특정 조달 범주에 대한 외부 카탈로그를 찾으려면 카탈로그 검색 필드에 텍스트를 입력하세요.
- 공급업체 웹 사이트의 공급업체 외부 카탈로그에서 제품을 추가하려면 외부 카탈로그를 클릭합니다. 그런 다음 장바구니에 제품을 추가하고 확인하세요. 장바구니 라인이 Microsoft Dynamics 365로 이전됩니다.

조달 범주에 대한 옵션이 여러 개인 경우 구매요청에 라인을 추가하기 전에 올바른 조달 범주를 선택합니다.
라인이 구매요청에 추가된 후 외부 카탈로그를 사용하지 않고 라인을 더 추가할 수 있습니다. 또는 외부 카탈로그를 계속 사용하여 라인을 추가할 수 있습니다.

요청이 준비되면 **워크플로**  >  **제출** 작업을 사용하여 승인을 위해 제출합니다.

### <a name="additional-resources"></a>추가 리소스

- [PunchOut 전자 조달을 위한 외부 카탈로그 설정](set-up-external-catalog-for-punchout.md)
- [cXML 개선 사항 구매](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]