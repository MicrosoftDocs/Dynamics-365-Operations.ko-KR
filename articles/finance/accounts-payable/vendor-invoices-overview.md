---
title: 공급업체 송장 개요
description: 이 항목에서는 공급업체 송장에 대한 일반 정보를 제공합니다.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b54a60ac3b1868ea7cc5ed88d5a31203b4bd29d3
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451657"
---
# <a name="vendor-invoices-overview"></a>공급업체 송장 개요

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


이 항목에서는 공급업체 송장에 대한 일반 정보를 제공합니다. 공급업체 송장은 제품 및 서비스에 대한 지불 요청입니다. 공급업체 송장은 지속적인 서비스에 대한 청구서를 나타내거나 특정 품목 및 서비스에 대한 구매 주문에 기반을 둘 수 있습니다.

## <a name="vendor-invoices"></a>공급업체 송장

구매 주문의 공급업체 송장은 공급업체에 제출한 구매 주문에 따라 제품이나 서비스를 수령할 때 생성됩니다. 공급업체 송장에는 하나의 헤더와 품목 또는 서비스에 대한 하나 이상의 라인이 포함됩니다. 공급업체 송장은 구매 주문에서 제품 수령, 공급업체 송장까지의 주기를 완료합니다.

일부 공급업체 송장은 구매 주문에 연결되지만 공급업체 송장은 구매 주문 라인에 해당하지 않는 라인을 포함할 수도 있습니다. 구매 주문과 연결되지 않은 공급업체 송장을 만들 수도 있습니다. 이러한 공급업체 송장은 공과금 청구서와 같은 지속적인 서비스를 나타낼 수 있습니다. 지속적인 서비스를 추가할 때 구매 주문을 참조할 필요가 없습니다.

공급업체 송장을 입력하는 여러 방법이 있습니다.

- 공급업체 송장 등록부를 사용하면 구매 주문을 참조하지 않는 송장을 빠르게 입력하여 경비를 적립할 수 있습니다. 공급업체 송장 승인 분개장을 사용하여 해당 송장을 선택하고 이를 공급업체 잔액에 게시하여 적립을 취소할 수 있습니다.
- 공급업체 송장 분개장을 사용하면 구매 주문을 참조하지 않는 송장을 한 번에 빠르게 입력할 수 있습니다.
- 공급업체 송장 풀과 함께 공급업체 송장 등록부를 사용하면 송장을 빠르게 입력하여 경비를 적립할 수 있습니다. 나중에 관련 구매 주문을 열어 경비 계정에 대한 송장을 게시할 수 있습니다.
- **미결 공급업체 송장** 및 **보류 중인 공급업체 송장** 페이지에서 확정된 구매 주문의 공급업체 송장을 만들 수 있습니다.

다음 토론에서는 **미결 공급업체 송장** 또는 **보류 중인 공급업체 송장** 페이지를 사용하여 구매 주문의 공급업체 송장을 만드는 방법에 관한 자세한 정보를 제공합니다.

## <a name="understanding-invoice-line-quantities"></a>송장 라인 수량 이해

관련 구매 주문에서 공급업체 송장을 열면 시스템이 구매 주문에서 송장 라인을 생성합니다. 기본적으로 시스템은 제품 영수증에서 수량을 가져옵니다. 그러나 다음 기본 동작 중 하나를 사용할 수 있습니다.

- **지금 수령 수량** – 부분 배송의 경우 이 옵션을 사용합니다. **수량** 필드의 기본값은 구매 주문의 **지금 수령** 필드에 지정된 수량으로 설정됩니다.
- **주문 수량** – 전체 배송에 이 옵션을 사용합니다. **수량** 필드의 기본값은 구매 주문의 **주문** 필드에 지정된 수량으로 설정됩니다.
- **등록 수량** – **품목 모델 그룹** 페이지에 지정된 대로 품목을 등록해야 하는 경우 이 옵션을 사용합니다. **수량** 필드의 기본값은 등록된 실제 업데이트 수량입니다.
- **제품 수령 수량** – 주문에 대한 제품 영수증이 이미 수신된 경우 이 옵션을 사용합니다. **수량** 필드의 기본값은 사용 가능한 제품 영수증의 총 수량입니다.
- **등록 수량 및 서비스** – 재고 품목 또는 재고가 없는 품목에 대한 도착 분개장에 수량이 등록된 경우 이 옵션을 사용합니다. 이 옵션에는 등록 여부와 관계없이 서비스도 포함됩니다.

법인에서 송장 매칭을 사용하는 경우 **제품 수령 수량 일치** 열에서 수량 일치의 결과를 볼 수 있습니다. 작업 창의 **검토** 탭에 있는 **매칭 세부 정보** 버튼을 사용하여 수량 일치의 결과를 볼 수도 있습니다.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>구매 주문에 없는 라인 추가

구매 주문에 없는 라인을 공급업체 송장에 추가할 수 있습니다. 품목 번호 또는 조달 범주를 선택해야 합니다. 그런 다음 라인에 수량, 가격 및 금액을 추가할 수 있습니다. 라인은 송장 합계에 대한 매칭 정책에만 포함됩니다.

## <a name="submitting-a-vendor-invoice-for-review"></a>검토를 위해 공급업체 송장 제출

조직에서 워크플로를 사용하여 공급업체 송장에 대한 검토 프로세스를 관리할 수 있습니다. 송장 헤더, 송장 라인 또는 둘 다에 대해 워크플로 검토가 필요할 수 있습니다. 워크플로 컨트롤은 컨트롤을 선택할 때 포커스가 있는 위치에 따라 헤더나 라인에 적용됩니다. **게시** 버튼 대신 **제출** 버튼은 검토 프로세스를 통해 공급업체 송장을 보냅니다.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>송장이 워크플로에 제출되지 않도록 방지 

다음은 송장이 워크플로에 제출되는 것을 방지하는 몇 가지 방법입니다.

- **송장 총액과 등록 총액이 같지 않습니다.** 송장을 제출한 사람은 합계가 같지 않다는 경고를 받게 됩니다. 이 경고는 송장을 워크플로에 다시 제출하기 전에 잔액을 수정할 기회를 제공합니다. 이 기능은 **기능 관리** 페이지의 **송장 총액과 등록 송장 총액이 같지 않은 경우 워크플로 제출 금지** 매개 변수가 켜져 있는 경우 사용할 수 있습니다. 
- **송장에 할당되지 않은 요금이 포함되어 있습니다.** 송장을 제출한 사람은 송장에 할당되지 않은 요금이 있다는 경고를 받으며 워크플로에 다시 제출하기 전에 송장을 수정할 수 있습니다. 이 기능은 **기능 관리** 페이지의 **공급업체 송장에 할당되지 않은 요금이 있는 경우 워크플로 제출 금지** 매개 변수가 켜져 있는 경우 사용할 수 있습니다.
- **송장에 다른 게시된 송장과 같은 송장 번호가 있습니다.** 송장을 제출한 사람은 번호가 중복된 송장이 발견되었다는 메시지를 받습니다. 워크플로에 송장을 다시 제출하기 전에 중복 번호를 수정할 수 있습니다. 이 경고는 지급 계정의 **사용된 송장 번호 확인** 매개 변수가 **중복 거부** 로 설정된 경우 표시됩니다. 이 기능은 **기능 관리** 페이지의 **송장 번호가 게시된 송장에 이미 존재하고 시스템이 중복 송장 번호를 허용하도록 설정되지 않은 경우 워크플로 제출 금지** 가 켜져 있는 경우 사용할 수 있습니다
- **송장에 송장 수량이 매칭된 제품 수령 수량보다 적은 라인이 있습니다.** 송장을 제출하거나 게시하려는 사람이 수량이 같지 않다는 메시지를 받게 됩니다. 이 메시지는 송장을 워크플로에 다시 제출하기 전에 값을 수정할 기회를 제공합니다. 이 기능은 **기능 관리** 페이지에서 **워크플로에 공급업체 송장 게시 및 제출 차단** 매개 변수가 켜져 있고 **지급 계정 매개 변수** 페이지에서 **게시 및 워크플로 제출 차단** 매개 변수가 켜져 있으면 사용할 수 있습니다.

## <a name="matching-vendor-invoices-to-product-receipts"></a>공급업체 송장과 제품 수령 매칭

공급업체 송장에 대한 정보를 입력 및 저장할 수 있으며 송장 라인을 제품 수령 라인과 매칭할 수 있습니다. 라인에 대한 부분 수량을 매칭할 수도 있습니다.

특정 구매 주문에 대한 모든 품목을 아직 수령하지 않은 경우에도 현재 날짜까지 수령한 제품 수령 개별 품목에 따라 공급업체 송장을 만들 수 있습니다. 예를 들어 공급업체가 한 달에 하나의 송장을 보내 해당 월에 배송된 모든 배달을 처리하는 경우 이 옵션을 사용할 수 있습니다. 각 제품 수령은 구매 주문 품목의 부분 또는 전체 배달을 나타냅니다.

송장이 워크플로에 있을 때 승인자는 송장 수량을 업데이트하여 **일치할 제품 입고 수량** 필드의 값과 일치하도록 할 수 있습니다. 그렇게 하려면 **기능 관리** 작업 영역에서 **워크플로의 제품 입고 수량과 일치하도록 송장 수량 업데이트** 기능을 선택하고 **활성화** 를 선택합니다. 워크플로 프로세스의 승인자가 송장 라인의 모든 제품 수령에서 모든 일치 품목을 제거한 경우 송장 라인이 삭제됩니다. 이 기능이 활성화되지 않은 경우 워크플로의 송장에 대한 송장 수량이 업데이트되지 않습니다.

송장을 게시하면 각 품목에 대한 **송장 잔액** 이 선택한 제품 수령의 총 수령 수량으로 업데이트됩니다. 구매 주문의 모든 품목에 대한 **송장 잔여분** 수량 및 **잔여분 배달** 수량이 모두 0(영)이면 구매 주문의 상태가 **송장 발행됨** 으로 변경됩니다. **송장 잔여분** 수량이 0(영)이 아닌 경우 구매 주문의 상태가 변경되지 않은 상태로 유지되며 추가 송장을 입력할 수 있습니다.

이 옵션은 구매 주문에 대해 하나 이상의 제품 수령이 게시되었다고 가정합니다. 공급업체 송장은 이러한 제품 수령 기반으로 하며 그 수량을 반영합니다. 송장에 대한 재무 정보는 송장을 전기할 때 입력한 정보를 기반으로 합니다.

자세한 내용은 [공급업체 송장을 기록하고 수령 수량과 일치](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md)를 참조하세요.

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>일괄 작업을 사용하여 공급업체 송장을 게시하도록 공급업체 송장 워크플로에 대한 자동화된 작업 구성

송장이 일괄 처리되도록 자동화된 게시 작업을 공급업체 송장 워크플로에 추가할 수 있습니다. 송장을 일괄 처리로 게시하면 게시가 완료될 때까지 기다릴 필요 없이 워크플로 프로세스를 계속할 수 있으므로 워크플로에 제출된 모든 작업의 전반적인 성능이 향상됩니다.

공급업체 송장을 일괄적으로 게시하려면 **기능 관리** 페이지에서 **공급업체 송장 일괄 게시** 매개 변수를 켭니다. 공급업체 송장 워크플로는 **지급 계정 > 설정 > 지급 계정 워크플로** 로 이동하여 구성합니다.

기능 매개 변수 **공급업체 송장 일괄 게시** 활성화와 관계없이 워크플로 편집기에서 **일괄 처리를 사용하여 공급업체 송장 게시** 작업을 볼 수 있습니다. 기능 매개 변수가 활성화되지 않은 경우 **일괄 처리를 사용하여 공급업체 송장 게시** 가 포함된 송장은 매개 변수가 활성화될 때까지 워크플로에서 처리되지 않습니다. **일괄 처리를 사용하여 공급업체 송장 게시** 작업은 **공급업체 송장 게시** 자동화 작업과 같은 워크플로에서 사용하면 안 됩니다. 또한 **일괄 처리를 사용하여 공급업체 송장 게시** 작업은 워크플로 구성의 마지막 요소여야 합니다.

**지급 계정 > 설정 > 지급 계정 매개 변수 > 송장 > 송장 워크플로** 로 이동하여 일괄 처리에 포함할 송장 수와 일괄 처리 일정을 조정하기 전에 대기할 시간을 지정할 수 있습니다. 

## <a name="working-with-multiple-invoices"></a>여러 송장 작업

동시에 여러 송장으로 작업하고 모든 송장을 동시에 게시할 수 있습니다. 여러 송장을 만들어야 하는 경우 **보류 중인 공급업체 송장** 페이지를 사용합니다. 여러 공급업체 송장을 게시하고 인쇄해야 하는 경우 **송장 승인 분개장** 을 사용합니다. **송장 승인 분개장** 을 사용하는 경우 구매 주문에 대해 하나 이상의 제품 수령을 게시해야 하고 구매 주문에 대한 송장은 송장 등록부에 게시해야 합니다. 송장에 대한 재무 정보는 등록부에 게시된 송장에서 가져옵니다.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>사용 중인 공급업체 송장 복구

공급업체 송장을 사용하는 동안 다른 사용자는 수정할 수 없습니다. 그러나 송장이 활발하게 편집되고 있지 않더라도 송장의 상태가 송장이 사용 중임을 나타내는 경우가 있습니다. 예를 들어, 송장을 편집하는 동안 애플리케이션이 응답하지 않거나 사용자가 실수로 애플리케이션에서 송장을 열어 두었을 수 있습니다.

**공급업체 송장 복구** 페이지를 사용하여 4시간 이상 사용된 공급업체 송장을 복구하거나 해제하여 편집할 수 있습니다. **정기 작업** 탐색 또는 **공급업체 송장 입력** 작업 영역의 타일에서 이 페이지를 열 수 있습니다. 송장이 복구되면 **공급업체 송장** 페이지에서 수정할 수 있습니다.

**사용 중인 공급업체 송장 복구** 보안 의무 및 권한이 할당된 경우에만 **공급업체 송장 복구** 페이지에 액세스할 수 있습니다. 또한 **지급 계정 매개 변수** 페이지의 **공급업체 송장 복구 허용** 매개 변수가 켜져 있어야 합니다.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>공급업체 송장의 워크플로 상태를 복구 불가능에서 초안으로 재설정

복구할 수 없는 오류로 인해 중지된 워크플로 인스턴스는 **복구 불가능** 상태가 됩니다. 공급업체 송장 워크플로의 상태가 **복구 불가능** 인 경우 **회수** 를 선택하여 **초안** 으로 재설정할 수 있습니다. 그런 다음 공급업체 송장을 편집할 수 있습니다. 이 기능은 **기능 관리** 페이지의 **공급업체 송장의 워크플로 상태를 복구 불가능에서 초안으로 재설정** 매개 변수가 켜져 있는 경우 사용할 수 있습니다.

**워크플로 기록** 페이지를 사용하여 워크플로 상태를 **초안** 으로 재설정할 수 있습니다. **공급업체 송장** 또는 **공통 > 문의 > 워크플로** 탐색에서 이 페이지를 열 수 있습니다. 워크플로 상태를 **초안** 으로 재설정하려면 **회수** 를 선택합니다. **공급업체 송장** 또는 **보류 중인 공급업체 송장** 페이지에서 **회수** 작업을 선택하여 워크플로 상태를 초안으로 재설정할 수도 있습니다. 워크플로 상태가 **초안** 으로 재설정되면 **공급업체 송장** 페이지에서 편집할 수 있습니다.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>보류 중인 공급업체 송장 페이지에서 송장 합계 보기

**지급 계정 매개 변수** 페이지에서 **보류 중인 공급업체 송장 목록에 송장 합계 표시** 매개 변수를 활성화하면 **보류 중인 공급업체 송장** 페이지에서 송장 합계를 볼 수 있습니다. 

## <a name="vendor-open-transactions-report"></a>공급업체 미결 거래 보고서

**공급업체 미결 거래** 보고서는 지정한 날짜를 기준으로 각 공급업체의 미결 거래에 관한 자세한 정보를 제공합니다. 이 보고서는 공급업체 장부 거래와 원장 계정 거래 간의 잔액을 확인하기 위한 감사 절차 중에 자주 사용됩니다.

보고서에는 각 거래에 대한 다음 세부 정보가 포함됩니다.

- 송장 번호
- 거래 날짜
- 전표 번호
- 거래 금액(거래 통화 및 회계 통화)
- 대변 잔액(거래 통화 및 회계 통화)
- 차변 잔액(거래 통화 및 회계 통화)
- 소계 금액(회계 통화)
- 지불 기한

### <a name="filter-the-data-on-the-report"></a>보고서의 데이터 필터링

**공급업체 미결 거래** 보고서를 생성할 때 다음 기본 매개 변수를 사용할 수 있습니다. 보고서에 포함될 데이터를 필터링하는 데 사용할 수 있습니다.

- **향후 정산 제외** – **미결 거래 기준** 필드에 입력한 날짜 이후에 정산된 거래를 제외하려면 이 확인란을 선택합니다.
- **미결 거래 기준** – 해당 날짜의 미결 거래를 포함할 날짜를 입력합니다. 날짜를 입력하지 않으면 이 필드는 최대 날짜로 설정됩니다. (최대 날짜는 시스템이 승인하는 가장 늦은 날짜인 2154년 12월 31일입니다) 기본적으로 다음에 보고서가 실행될 때 이 필드는 보고서에 입력된 마지막 날짜로 설정됩니다.

**포함할 기록** 필드 아래의 필터를 사용하여 보고서에 포함되는 거래 데이터를 추가로 제한할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [공급업체 송장 정책 설정](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [공급업체 송장을 사용하여 AP 시스템으로 송장 데이터 입력](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [승인 분개장을 사용하여 지급 계정으로 송장 데이터 입력](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [송장 풀을 사용하여 AP 시스템으로 송장 데이터 입력](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [송장 분개장에 공급업체 송장 기록](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]