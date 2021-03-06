---
title: 고객과의 공급업체 협업
description: 이 토픽에서는 공급업체 협업을 사용하여 PO 작업 및 위탁 재고 모니터링 방법에 대해 설명합니다.
author: TaylorVH
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart, VendVendorProfileCard, PurchVendorPortalAllResponse, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: v-savanh
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f699b00ab7ea2d043e12824015c54439caf8e63c
ms.sourcegitcommit: d58a891d9fe0aa0e6b2c20329250c8d74ffbee90
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2022
ms.locfileid: "8449794"
---
# <a name="vendor-collaboration-with-customers"></a>고객과의 공급업체 협업

[!include [banner](../includes/banner.md)]

이 토픽에서는 공급업체 협업을 사용하여 Microsoft Dynamics 365 Supply Chain Management에서 고객과 작업하는 방법에 대해 설명합니다. 공급업체는 다음 작업 영역에서 일련의 비즈니스 프로세스를 완료할 수 있습니다.

- **구매 주문 확인** – 구매 주문(PO)을 모니터링하고 응답합니다.
- **공급업체 입찰** – 견적 요청(RFQ)을 보고 입찰을 입력하여 응답합니다.
- **공급업체 정보** – 공급업체 마스터 데이터를 보고 업데이트합니다.
- **송장 발행** – 송장으로 작업합니다. 이 토픽에서는 **송장** 작업 영역을 다루지 않습니다. 이 작업 영역에 대한 자세한 내용은 [공급업체 협업 송장 작업 영역](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md)을 참조하세요.

공급업체는 위탁 재고에 대한 정보를 모니터링할 수도 있습니다.

## <a name="working-with-pos-in-the-purchase-order-confirmation-workspace"></a>구매 주문 확인 작업 공간에서 PO 작업

**구매 주문 확인** 작업 공간을 사용하면 검토를 위해 보낸 구매 주문(PO)에 응답할 수 있습니다. 또한 고객의 조치를 기다리고 있는 PO와 확인되었지만 아직 열려 있는 PO에 대한 정보를 볼 수 있습니다.

**구매 주문 확인** 작업 영역에는 세 가지 목록이 있습니다.

- **검토할 구매 주문** – 이 목록은 귀하에게 전송되었으며 귀하의 응답을 기다리고 있는 PO를 보여줍니다. 응답하면 PO가 목록에서 사라집니다. 이전 버전에 응답하기 전에 고객이 새 버전의 PO를 보낸 경우 최신 버전만 표시됩니다.
- **고객의 조치를 기다리는 중** – 이 목록에는 귀하가 응답했지만 고객이 아직 확인하지 않은 모든 PO가 표시됩니다. PO를 수락하면 상태가 **확인됨** 으로 변경될 때까지 이 목록에서 모니터링할 수 있습니다. PO를 거부하거나 변경 사항과 함께 수락하면 고객이 새 버전을 보낼 때까지 여기에서 모니터링할 수 있습니다.
- **확인된 구매 주문 열기** – 이 목록은 상태가 **확인됨** 인 계정의 모든 PO를 보여줍니다. 제품 또는 서비스가 PO에 대해 완전히 수신되면 PO가 목록에서 사라집니다.

다음 페이지를 사용하여 PO 작업을 할 수 있습니다.

- **검토할 구매 주문** – 이 페이지에는 작업 공간의 **검토할 구매 주문** 목록과 동일한 정보가 포함되어 있습니다. 이 토픽 앞부분의 설명을 참조하세요.
- **구매 주문 공급업체 확인 내역** - 이 페이지에는 공급업체에 전송된 모든 PO 및 모든 버전의 PO가 포함됩니다. 여기에는 공급업체에서 반환된 모든 응답도 포함됩니다.
- **확인된 구매 주문 열기** 이 페이지에는 작업 영역의 **확인된 구매 주문 열기** 목록과 동일한 정보가 포함되어 있습니다. 이 토픽 앞부분의 설명을 참조하세요.
- **확인된 모든 구매 주문** – 이 페이지에는 확인된 모든 PO가 포함되어 있습니다. 이 페이지에 표시된 PO에는 제품 또는 서비스를 받은 PO가 포함됩니다. 이 목록을 사용하여 송장을 보낼 수 있는 PO를 모니터링할 수 있습니다.

### <a name="responding-to-pos"></a>PO에 응답하기

고객이 검토를 위해 보낸 PO는 **구매 주문 확인** 작업 영역 및 **검토할 구매 주문** 페이지에 나타납니다. PO를 연 후에는 수락하거나 거부하거나 변경 사항과 함께 수락할 수 있습니다. PO 헤더 또는 개별 라인에 첨부 파일이 있을 수 있습니다. 또한 PO 헤더 또는 개별 라인의 응답에 정보를 첨부할 수 있습니다. 예를 들어, 라인 중 하나에 대한 대체 품목을 제안할 수 있습니다.

**미리보기/인쇄** 옵션을 사용하여 PO를 PDF 파일로 미리 보고 인쇄할 수 있습니다. **차원 표시** 작업을 사용하여 **사이트**, **창고**, **색상**, **크기**, **스타일** 및 **구성** 차원 열을 숨기거나 표시할 수도 있습니다. 

**변경사항 수락** 옵션을 사용할 경우 개별 라인을 수락하거나 거부할 수 있습니다. 행을 다음과 같이 변경할 수도 있습니다.

- 날짜 또는 수량을 변경합니다. 모든 라인의 확정 납품 일자를 업데이트하려면 PO 헤더의 **납품 일자 업데이트** 옵션을 사용하세요.
- 다른 배송 날짜 또는 수량에 대한 분할 라인.
- 항목을 대체합니다. **라인 세부사항** 섹션의 **외부** 필드에 품목 설명과 품목 번호를 입력합니다.

가격 정보나 요금은 변경할 수 없지만 메모를 사용하여 이러한 변경 사항을 제안할 수 있습니다.

고객이 새 버전의 PO를 보내는 경우 이전에 보낸 PO의 수정된 버전임을 나타내는 버전 접미사가 있습니다. **구매 주문 공급업체 확인 내역** 페이지에서 각 주문 내역을 추적할 수 있습니다.

## <a name="monitoring-consignment-inventory"></a>위탁 재고 모니터링

위탁 재고를 사용하는 경우 공급업체 협업 인터페이스를 사용하여 다음 페이지에서 정보를 볼 수 있습니다.

- **위탁 재고를 소비하는 구매 주문** – 위탁 재고에 대한 PO는 고객이 재고를 소유할 때 생성됩니다. 이 위탁 PO는 이 페이지에만 표시됩니다. **확인된 모든 구매 주문** 페이지에 포함되지 않습니다.
- **위탁 재고에서 입고된 제품** – 이 페이지는 제품의 소유권이 재고를 소비하는 회사로 이전된 모든 거래를 나열합니다. 이 정보를 사용하여 고객에게 송장을 보낼 수 있습니다.
- **현재고 위탁 재고** – 이 페이지는 귀사에서 소유하고 있지만 고객의 창고에 있는 현재고 위탁 재고를 보여줍니다.

## <a name="working-with-rfqs-in-the-vendor-bidding-workspace"></a>공급업체 입찰 작업 공간에서 RFQ 작업

**공급업체 입찰** 작업 영역에서는 회사가 응답하도록 초대된 견적 요청(RFQ)을 볼 수 있습니다. RFQ에 응답할 수도 있습니다.

작업 영역에는 또한 상실했거나 획득한 모든 RFQ가 표시됩니다. 또한 시스템이 공공 부문용으로 구성된 경우 작업 공간에는 공개적으로 사용 가능한 RFQ가 표시됩니다.

### <a name="viewing-rfqs"></a>RFQ 보는 중

**공급업체 입찰** 작업 영역을 열어 다음 정보에 액세스합니다.

- 회사가 응답하도록 초대된 RFQ를 보려면 **새 입찰 초대** 를 선택합니다. 여기에서 RFQ를 보고 입찰 프로세스를 시작할 수 있습니다. 새 입찰을 제출해야 하는 수정된 RFQ도 볼 수 있습니다.
- 추가 정보를 제공하거나 입찰을 업데이트할 수 있도록 고객이 귀하에게 반환한 RFQ를 보려면 **반환된 입찰** 을 선택합니다.
- 귀하 또는 귀하의 회사를 대표하는 담당자가 작업했지만 아직 제출하지 않은 RFQ를 보려면 **진행 중인 입찰** 을 선택합니다.
- 고객이 입찰에서 하나 이상의 항목을 낙찰했는지 확인하려면 **낙찰된 입찰** 을 선택합니다.
- 모든 라인이 거부된 입찰가를 보려면 **상실된 입찰** 을 선택합니다.
- **견적 요청** 링크를 선택하여 모든 공급업체의 RFQ 초대 목록과 제출된 입찰가를 확인합니다. **견적 요청** 페이지에는 공급업체가 관련된 모든 RFQ가 나열됩니다. 상태로 검색할 수 있습니다.
- 공급업체 담당자가 입찰을 거부한 모든 RFQ 목록을 보려면 **거부된 입찰** 링크를 선택합니다.

### <a name="working-with-rfqs-that-are-publicly-available"></a>공개적으로 사용 가능한 RFQ 작업

공공 부문에서 일하는 사람들은 공개된 RFQ와 만료된 RFQ를 볼 수 있습니다.

- **공개된 견적 요청 공개** 링크를 선택하여 공개된 공개 RFQ 목록을 확인합니다. 공개 RFQ는 아직 만료되지 않은 RFQ입니다. RFQ 헤더에서 만료 날짜와 시간을 찾을 수 있습니다.

    입찰에 초대를 받은 경우 **새 입찰 초대** 페이지에서 동일한 RFQ를 찾을 수 있습니다. 공개 RFQ에 입찰하고 싶지만 입찰에 초대받지 못한 경우가 있습니다. 이 경우 고객이 RFQ 사례에 대해 자체 초대를 활성화한 경우 자신을 초대할 수 있습니다. 

    **새 입찰 초대** 페이지는 열려 있는 RFQ를 보고 승인된 조달 범주와 일치하는 라인이 포함된 RFQ를 식별할 수 있는 필터를 제공할 수 있습니다. 이 필터를 사용 가능하게 하려면 시스템에서 *공급업체가 조달 범주별로 RFQ를 검색할 수 있도록 허용* 기능을 켜야 합니다. 관리자는 **기능 관리** 작업 영역을 사용하여 이 기능의 상태를 확인하고 필요한 경우 켤 수 있습니다. 거기에서 기능은 다음과 같은 방식으로 나열됩니다.

    - **모듈:** *지급 계정*
    - **기능 이름:** *공급업체가 조달 범주별로 RFQ를 검색할 수 있도록 허용* <!-- KFM: I don't see this here, is this right? -->

    *"공개된 견적 요청 공개" 링크를 타일로 표시* 기능을 켜서 **공개된 견적 요청 공개** 링크의 접근성을 향상할 수 있습니다. 이 기능은 링크를 타일로 변환하고 찾기 쉽도록 눈에 잘 띄는 위치로 이동합니다. 관리자는 **기능 관리** 작업 영역을 사용하여 이 기능의 상태를 확인하고 필요한 경우 켤 수 있습니다. (Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다.) 이 기능은 다음과 같이 나열됩니다.

    - **모듈:** *조달 및 소싱*
    - **기능 이름:** *"공개된 견적 요청 열기" 링크를 타일로 표시*

- **비공개된 견적 요청 공개** 링크를 선택하여 비공개된 공개 RFQ 목록을 확인합니다. 마감된 RFQ는 만료된 RFQ입니다. RFQ 헤더에서 만료 날짜와 시간을 찾을 수 있습니다.

    마감된 RFQ는 모든 공급업체 입찰가를 라인 수준까지 보여줍니다. 입찰이 낙찰되거나 거부되면 이 정보는 마감된 RFQ에 반영됩니다. 입찰에 포함된 모든 첨부 파일도 사용할 수 있습니다.

> [!NOTE]
> 이 기능은 공공 부문 구성이 켜져 있는 경우에만 사용할 수 있습니다.

### <a name="bidding"></a>입찰

- **입찰** 을 선택하여 RFQ에 대한 입찰을 시작합니다.

    RFQ의 헤더 및 라인에 있는 입찰 필드에 대해 편집이 활성화된 경우 라인 그리드에 직접 입찰가를 입력할 수 있습니다. 라인 세부 정보에 추가해야 하는 추가 입찰 정보도 고려해야 합니다.

    입찰 작업을 시작하면 **진행 중인 입찰** 섹션에 나타납니다.

    만료 날짜 이전에는 언제든지 입찰가를 저장할 수 있습니다. 그런 다음 나중에 돌아와 입찰을 완료하고 제출할 수 있습니다. 입찰을 제출한 후 만료 날짜까지 회수하고 업데이트할 수 있습니다.

- **RFQ에서 재설정** 을 선택하여 입찰에 대해 입력한 데이터를 재설정하고 원래 견적 요청으로 되돌립니다. 헤더 또는 라인을 재설정할 수 있습니다.
- 대체 항목을 사용하려면 라인 그리드에서 **대체 항목 추가** 또는 **대체 항목 제거** 를 선택합니다.

    일부 RFQ는 대체 입찰을 허용합니다. 특정 항목을 대체 항목으로 추가할 수 없기 때문에 **범주** 유형의 라인에 대해서만 대체 입찰가를 지정할 수 있습니다. 

- 고객이 견적 요청에 추가한 첨부를 열려면 **견적 요청 첨부** 또는 **견적 요청 라인 첨부** 를 선택합니다. **입찰 첨부 파일** 또는 **입찰 라인 첨부 파일** 을 선택하여 입찰과 함께 첨부 파일을 업로드합니다.

    입찰을 제출하기 전에 답변해야 하는 질문이 있을 수 있습니다.

- 입찰하지 않으려면 **거부** 를 선택합니다. **거부** 를 선택한 후에는 작업을 회수하고 입찰가를 입력할 수 없습니다.

RFQ가 수정되면 새 입찰가를 입력해야 합니다. RFQ 페이지의 **수정** 탭에서 수정 사항에 대한 정보를 찾을 수 있습니다. 수정된 RFQ는 **새 입찰 초대** 페이지에 나타납니다.

## <a name="accessing-vendor-master-data-in-the-vendor-information-workspace"></a>공급업체 정보 작업 영역에서 공급업체 마스터 데이터에 액세스

공급업체는 공급업체 마스터 레코드에서 고객이 유지 관리하는 정보의 일부에 액세스할 수 있습니다. 따라서 정보를 최신 상태로 유지할 수 있습니다. 정보를 업데이트하려면 공급업체 관리자(외부) 역할이 있어야 합니다.

액세스 가능한 정보는 공급업체 이름, 주소, 연락처 정보, 담당자 및 연락처 정보, 식별 번호, 세금 등록 번호, 공급업체가 고객에게 판매하도록 승인된 조달 범주 및 인증에 대한 정보입니다.

## <a name="additional-resources"></a>추가 리소스

[공급업체 협업 사용자 관리](manage-vendor-collaboration-users.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
