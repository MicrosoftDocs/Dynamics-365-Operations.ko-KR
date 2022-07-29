---
title: 판매 주문 상태 열에 대한 매핑 설정
description: 이 항목에서는 이중 쓰기에 대한 판매 주문 상태 열을 설정하는 방법에 대해 설명합니다.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: damadipa
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 53d824ca2fb1eadf34e62bf9c08b837db3efaf42
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460901"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>판매 주문 상태 열에 대한 매핑 설정

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management 및 Dynamics 365 Sales에서 판매 주문 상태를 나타내는 열의 열거 값이 다릅니다. 이중 쓰기에서 이러한 열을 매핑하려면 추가 설정이 필요합니다.

## <a name="columns-in-supply-chain-management"></a>Supply Chain Management의 열

Supply Chain Management에서 두 개의 열은 판매 주문의 상태를 반영합니다. 매핑해야 하는 열은 **상태** 및 **문서 상태** 입니다.

**상태** 열거형은 주문의 전체 상태를 지정합니다. 이 상태는 주문 헤더에 표시됩니다.

**상태** 열거형에는 다음 값이 있습니다.

- 미결 주문
- 배송됨
- 송장 발부됨
- 취소됨

**문서 상태** 열거형은 주문에 대해 생성된 가장 최근 문서를 지정합니다. 예를 들어 주문이 확인된 경우 이 문서는 판매 주문 확인입니다. 판매 주문이 부분적으로 송장 발행되고 나머지 라인이 확정되면 문서 상태는 **송장** 으로 유지됩니다. 이는 송장이 나중에 프로세스에서 생성되기 때문입니다.

**문서 상태** 열거형에는 다음 값이 있습니다.

- 확인
- 불출 목록
- 포장 전표
- 청구서

## <a name="columns-in-sales"></a>Sales의 열

Sales에서 두 개의 열은 주문의 상태를 나타냅니다. 매핑해야 하는 열은 **상태** 및 **처리 상태** 입니다.

**상태** 열거형은 주문의 전체 상태를 지정합니다. 다음 값이 있습니다.

- 활성
- 제출됨
- 주문 이행됨
- 송장 발부됨
- 취소됨

**처리 상태** 열거형이 상태가 Supply Chain Management로 더 정확하게 매핑될 수 있도록 도입되었습니다.

다음 표는 Supply Chain Management의 **처리 상태** 매핑을 보여줍니다.

| 처리 상태   | Supply Chain Management의 상태 | Supply Chain Management의 문서 상태 |
|---------------------|-----------------------------------|--------------------------------------------|
| 활성              | 미결 주문                        | 없음                                       |
| 확인됨           | 미결 주문                        | 확인                               |
| 피킹됨              | 미결 주문                        | 불출 목록                               |
| 부분 배송됨 | 미결 주문                        | 포장 전표                               |
| 배송됨           | 배송됨                         | 포장 전표                               |
| 부분 청구됨  | 배송됨                         | 청구서                                    |
| 송장 발부됨            | 송장 발부됨                          | 청구서                                    |
| 취소됨           | 취소됨                         | 해당 없음                             |

다음 표는 Sales와 Supply Chain Management 사이의 **처리 상태** 매핑을 보여줍니다.

| 처리 상태   | Sales의 상태 | Supply Chain Management의 상태 |
|---------------------|-----------------|-----------------------------------|
| 활성              | 활성          | 미결 주문                        |
| 확인됨           | 제출됨       | 미결 주문                        |
| 피킹됨              | 제출됨       | 미결 주문                        |
| 부분 배송됨 | 활성          | 미결 주문                        |
| 부분 청구됨  | 활성          | 미결 주문                        |
| 부분 청구됨  | 주문 이행됨       | 배송됨                         |
| 송장 발부됨            | 송장 발부됨        | 송장 발부됨                          |
| 취소됨           | 취소됨       | 취소됨                         |

## <a name="setup"></a>설정

판매 주문 상태 열에 대한 매핑을 설정하려면 **IsSOPIntegrationEnabled** 및 **isIntegrationUser** 특성을 활성화해야 합니다.

**IsSOPIntegrationEnabled** 특성을 활성화하려면 다음 단계를 따르세요.

1. 웹 브라우저에서 `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`로 이동합니다. **\<test-name\>** 을 Sales에 대한 회사의 링크로 바꿉니다.
2. 열리는 페이지에서 **organizationid** 를 찾고 값을 기록해 둡니다.

    ![organizationid 찾기.](media/sales-map-orgid.png)

3. Sales에서 브라우저 콘솔을 열고 다음 스크립트를 실행합니다. 2단계의 **organizationid** 값을 사용합니다.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![브라우저 콘솔의 JavaScript 코드.](media/sales-map-script.png)

4. **IsSOPIntegrationEnabled** 가 **true** 로 설정되어 있는지 확인합니다. 1단계의 URL을 사용하여 값을 검사합니다.

    ![IsSOPIntegrationEnabled가 true로 설정됨.](media/sales-map-integration-enabled.png)

**isIntegrationUser** 특성을 활성화하려면 다음 단계를 따르세요.

1. Sales에서 **설정 \> 사용자 지정 \> 시스템 사용자 지정** 으로 이동하고 **사용자 테이블** 을 선택한 다음 **양식 \> 사용자** 를 엽니다.

    ![사용자 양식을 엽니다.](media/sales-map-user.png)

2. 필드 탐색기에서 **통합 사용자 모드** 를 찾고 두 번 클릭하여 양식에 추가합니다. 변경 사항을 저장합니다.

    ![통합 사용자 모드 열을 양식에 추가합니다.](media/sales-map-field-explorer.png)

3. Sales에서 **설정 \> 보안 \> 사용자** 로 이동하고 **활성화된 사용자** 에서 **애플리케이션 사용자** 로 보기를 변경합니다.

    ![활성화된 사용자에서 애플리케이션 사용자로 보기 변경.](media/sales-map-enabled-users.png)

4. **IntegrationUser** 에 대한 두 항목을 선택합니다.

    ![애플리케이션 사용자 목록.](media/sales-map-user-mode.png)

5. **통합 사용자 모드** 열의 값을 **네** 로 변경합니다.

    ![통합 사용자 모드 열의 값을 변경.](media/sales-map-user-mode-yes.png)

이제 판매 주문이 매핑되었습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]