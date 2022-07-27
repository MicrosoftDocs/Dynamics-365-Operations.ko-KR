---
title: PunchOut 전자 조달을 위한 외부 카탈로그 설정
description: 이 토픽에서는 외부 카탈로그 또는 PunchOut 카탈로그를 사용하여 공급업체로부터 견적 정보를 수집하고 요청에 추가하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f1065c68723baa395bc06be6313e45a44661ea3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447967"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>PunchOut 전자 조달을 위한 외부 카탈로그 설정

[!include [banner](../includes/banner.md)]

외부 카탈로그를 사용하면 Supply Chain Management에서 이후에 처리하는 제품 및 가격 정보가 정확하고 최신 상태인지 확인할 수 있습니다. 그런 다음 요청이 승인되고 구매 주문으로 변환될 수 있으며 주문은 공급업체에 배치될 수 있습니다.

외부 카탈로그가 설정되고 직원이 요청을 준비할 때 외부 사이트인 외부 카탈로그로 리디렉션하고 외부 사이트에서 생성된 장바구니를 반환하는 옵션이 있습니다. 이 통신은 cXML 프로토콜을 기반으로 하며 구매 시스템과 판매 조직 간에 설정되어야 합니다.

통신을 설정하기 위해 공급업체는 ID, 구매자 회사 도메인, "DUNS" 및 "DUNS 번호", 자격 증명 및 공급업체 카탈로그에 도달하기 위한 URL과 같은 외부 카탈로그 구성에 사용할 정보를 제공해야 합니다.

## <a name="setting-up-an-external-catalog"></a>외부 카탈로그 설정

외부 카탈로그는 구매 요청을 입력하는 직원이 제품을 선택하기 위해 외부 사이트로 리디렉션될 수 있도록 해야 합니다. 직원이 외부 카탈로그에서 선택한 제품은 최신 가격 정보와 함께 반환되며 여기에서 구매 요청에 추가할 수 있습니다. 직원이 외부 사이트에서 주문할 수 있도록 하려는 것이 아닙니다. 외부 카탈로그 설정 시 외부 카탈로그에서 접속할 수 있는 사이트의 목적이 실제 주문을 하는 것이 아니라 견적 정보를 수집하는 것인지 확인해야 합니다.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>외부 공급업체 카탈로그를 설정하려면 다음 작업을 완료하세요.

1. 조달 범주 계층 설정. 자세한 내용은 [조달 범주 계층 구조에 대한 정책 설정](tasks/set-up-policies-procurement-category-hierarchies.md)을 참조하세요.
2. Supply Chain Management에 공급업체를 등록합니다. 외부 공급업체 카탈로그에 액세스하도록 구성을 설정하려면 먼저 Microsoft Dynamics 365에서 공급업체 및 공급업체 연락처를 설정해야 합니다. 외부 카탈로그의 공급업체도 선택한 조달 범주에 추가해야 합니다. 공급업체 등록에 대한 자세한 내용은 [공급업체 협업 사용자 관리](manage-vendor-collaboration-users.md)를 참조하세요. 공급업체를 조달 범주에 지정하는 방법에 대한 자세한 내용은 [특정 조달 범주에 대한 공급업체 승인](tasks/approve-vendors-specific-procurement-categories.md)을 참조하세요.
3. 공급업체에서 사용하는 측정 단위와 통화가 설정되어 있는지 확인하세요. 측정 단위를 만드는 방법에 대한 자세한 내용은 [측정 단위 관리](../pim/tasks/manage-unit-measure.md)를 참조하세요.
4. 공급업체의 외부 카탈로그 사이트에 대한 요구 사항을 사용하여 외부 공급업체 카탈로그를 구성합니다. 이 작업에 대한 자세한 내용은 [외부 공급업체 카탈로그 구성](#configure-the-external-vendor-catalog)을 참조하세요.
5. 공급업체의 외부 카탈로그 구성을 테스트하여 설정이 유효하고 공급업체의 외부 카탈로그에 액세스할 수 있는지 확인하세요. **설정 확인** 작업을 사용하여 정의한 요청 설정 메시지를 확인합니다. 이 메시지로 인해 공급업체 외부 카탈로그 사이트가 브라우저 창에서 열립니다. 유효성 검사 중에는 공급업체에서 항목 및 서비스를 주문할 수 없습니다. 항목 및 서비스를 주문하려면 구매 요청에서 공급업체의 카탈로그에 액세스해야 합니다.
6. **외부 카탈로그** 페이지에서 **카탈로그 활성화** 단추를 사용하여 외부 카탈로그를 활성화합니다. 직원이 사용하려면 먼저 외부 카탈로그를 활성화해야 합니다. 외부 카탈로그는 언제든지 비활성화할 수 있습니다.


## <a name="configure-the-external-vendor-catalog"></a>외부 공급업체 카탈로그 구성

이 섹션에서는 이전 섹션의 작업 4에 대해 자세히 설명합니다.

1. 공급업체 외부 카탈로그의 이름과 설명을 입력합니다. 입력한 이름은 요청을 생성하는 직원에게 표시되는 외부 카탈로그를 나타내는 카트에 나타납니다. 직원은 카트를 클릭하여 공급업체의 외부 카탈로그 사이트에서 카탈로그를 열 수 있습니다.
2. **외부 카탈로그 이미지** 작업을 사용하여 이미지를 추가합니다. 이름은 요청을 생성하는 직원에게 표시되는 외부 카탈로그를 나타내는 카트에 나타납니다. 이미지의 너비와 높이는 같아야 합니다. 그렇지 않으면 이미지가 올바르게 표시되지 않습니다.
3. 공급업체의 외부 카탈로그 웹사이트를 직원이 구매 요청을 생성한 브라우저 창과 동일한 브라우저 창에 표시해야 하는지 또는 새 창에서 열어야 하는지 선택합니다.
4. 카탈로그의 공급업체를 선택합니다. **법인** 목록에는 공급업체가 설정된 각 법인에 대한 행이 있습니다. 사용자가 일부 법인의 공급업체 카탈로그에서 직접 제품을 요청할 수 있도록 하고 다른 법인은 허용하지 않으려면 카탈로그를 제공하거나 제공하지 않으려는 각 법인에 대해 **액세스 방지** 또는 **액세스 허용** 단추를 사용할 수 있습니다.
5. **기본 만료(일)** 필드에 외부 카탈로그에서 받은 견적이 유효하고 외부 공급업체로부터 구매하는 데 사용할 수 있는 일 수를 입력합니다. 공급업체의 외부 카탈로그 사이트에서 견적이 생성 및 검색되면 견적은 현재 시스템 날짜를 기준으로 유효하며 이 필드에 입력한 일수 동안 유효합니다.
6. **추가** 단추를 클릭하여 조달 범주를 외부 카탈로그에 매핑하기 시작합니다. 그런 다음 카테고리 명칭 목록에서 범주를 선택합니다. 범주 목록은 공급업체에 대해 설정된 모든 법인에서 공급업체가 매핑된 조달 범주의 상위 집합입니다.

    > [!NOTE]
    > 조달 정책은 구매 법인 또는 수령 운영 단위의 범주에 대한 액세스를 허용하거나 제한하는 데 사용됩니다. 외부 카탈로그에 대한 펀치아웃은 카탈로그에 매핑된 조달 범주 중 하나 이상에 대한 액세스가 허용되어야 합니다.

7. 공급업체에 보낼 cXML 설정 요청 메시지를 설정합니다. 자동으로 생성된 메시지 형식은 세션을 시작하는 데 필요한 최소 템플릿입니다. 태그 값을 입력합니다.

**메시지 형식 복원** 을 클릭하여 언제든지 시스템 생성 메시지 템플릿을 다시 로드할 수 있습니다. 메시지 형식을 복원하면 현재 메시지가 태그가 비어 있는 자동으로 생성된 메시지 형식으로 대체됩니다.

### <a name="cxml-setup-message"></a>cXML 설정 메시지
아래에서 템플릿에 포함된 태그에 대한 설명을 찾을 수 있습니다.

| 필드 | 설명 | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|구매자 회사의 도메인입니다.|
|< Header >< From >< Credential>< Identity >< /Identity > | 구매자 회사의 ID입니다.|
|< Header >< To >< Credential domain=”” > | 공급업체 회사의 도메인입니다.|
|< Header >< To >< Credential>< Identity >< /Identity> | 공급업체 회사의 ID입니다.|
|< Header >< Sender >< Credential domain=”” > | 구매자 회사의 도메인입니다.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | 구매자 회사의 ID입니다.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|구매자 회사의 공유 비밀입니다.|
|< Request deploymentMode=”” >|테스트 또는 프로덕션 배포입니다.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|PunchOut 엔드포인트의 URL입니다.|

### <a name="extrinsic-elements"></a>외부 요소

외부 요소는 펀치 아웃하는 사용자를 기반으로 하는 사용자 이름과 같은 추가 정보입니다. 외부 요소는 PunchOut이 발생할 때 설정되며 요청 설정 메시지로 보낼 수 있습니다.
공급업체에는 설정 요청에서 외부 요소를 수신해야 하는 요구 사항이 있을 수 있습니다. 이 경우 **외부 카탈로그** 페이지의 **메시지 형식** 섹션에 있는 외부 요소 목록에 외부 요소를 추가해야 합니다.
공급업체가 인식하고 값에 매핑할 수 있는 외부 요소의 이름을 지정합니다. 값 옵션은 사용자 이름, 사용자 이메일 또는 임의 값입니다.
cXML 프로토콜에 대한 자세한 내용은 [cXML.org 웹 사이트](http://cxml.org/)를 참조하세요.

## <a name="post-back-message"></a>포스트백 메시지
포스트백 메시지는 사용자가 외부 사이트에서 체크아웃하고 Supply Chain Management로 돌아올 때 공급업체로부터 수신되는 메시지입니다. 포스트백 메시지는 구성할 수 없습니다. 메시지는 cXML 프로토콜 정의를 기반으로 합니다. 다음은 요청 라인에서 수신되는 포스트백 메시지의 일부일 수 있는 정보입니다.

| 공급업체로부터 받은 메시지 | 구매 요청 라인에 복사됨|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |수량|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|외부 항목 ID|
|< ItemDetail>< UnitPrice >< Money currency=”” >| 통화|
|< ItemDetail >< UnitPrice >< Money >< /Money >| 단가|
|< ItemDetail >< Description ShortName=”” >|제품 이름|
|< ItemDetail >< Description >< /Description >|항목 설명에 포함됨, ShortName이 지정되지 않은 경우 제품 이름입니다.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|단위|
|< ItemDetail >< Classification >< /Classification >|항목 설명에 포함|
|< ItemDetail >< Classification domain=”” >|항목 설명에 포함|

## <a name="delete-an-external-catalog"></a>외부 카탈로그 삭제
페이지에서 삭제 작업으로 외부 카탈로그를 삭제합니다.

외부 공급업체 카탈로그의 제품이 요청된 경우 외부 공급업체 카탈로그를 삭제할 수 없습니다. 대신 외부 공급업체 카탈로그의 상태가 비활성으로 설정됩니다. 외부 공급업체의 카탈로그 사이트에 대한 액세스를 제거하지만 삭제하지 않으려면 외부 카탈로그 상태를 비활성으로 변경합니다.

## <a name="additional-resources"></a>추가 리소스

- [cXML 개선 사항 구매](purchasing-cxml-enhancements.md)
- [PunchOut 전자 조달을 위한 외부 카탈로그 사용](use-external-catalogs-for-punchout.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]