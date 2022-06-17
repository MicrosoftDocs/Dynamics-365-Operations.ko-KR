---
title: Excel 통합 문서를 만들어 소매 거래 편집
description: 이 항목에서는 Microsoft Dynamics 365 Commerce에서 소매 거래를 편집할 수 있도록 Excel 통합 문서를 만드는 방법을 설명합니다.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: bfc3f6898087445e0276994ceeb52c178785bf3604fa163939327e99a0564f64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452776"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Excel 통합 문서를 만들어 소매 거래 편집

[!include [banner](../includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Commerce에서 소매 거래를 편집할 수 있도록 Excel 통합 문서를 만드는 방법을 설명합니다.

## <a name="overview"></a>개요

고객이 시스템의 다른 부분에서 액세스하여 소매 거래를 편집 및 감사하는 데 사용할 수 있는, 미리 정의된 Excel 템플릿이 있습니다. 그러나 고객은 이러한 작업을 위해 사용자 지정 Excel 통합 문서를 만들 수도 있습니다.

## <a name="create-and-configure-an-excel-workbook"></a>Excel 통합 문서 생성 및 구성

소매 거래를 편집할 수 있도록 Excel 통합 문서를 만들고 구성하려면 다음 단계를 따르세요.

1. Excel을 열고 빈 통합 문서를 만듭니다.
1. **삽입** 탭에서 **내 추가 기능** 을 선택합니다.
1. 오른쪽 창에서 **서버 정보 추가** 링크를 선택합니다.
1. 서버 URL을 입력한 다음 **확인** 을 선택합니다.
1. "애플릿 등록을 찾을 수 없음" 오류 메시지가 나타나면 다음 단계에 따라 문제를 해결하세요.

    1. Commerce에서 **시스템 관리 \> 설정 \> Office 앱 매개 변수** 로 이동합니다.
    1. **앱 매개 변수** 빠른 탭에서 **앱 매개 변수 초기화** 를 선택합니다.
    1. 확인 메시지 상자에서 **확인** 을 선택합니다.
    1. **등록된 애플릿** 빠른 탭에서 **애플릿 등록 초기화** 를 선택합니다.
    1. 필요하다면 앞의 세 단계를 반복합니다.

1. **디자인** 을 선택하고 **표 추가** 를 선택합니다.
1. 수정해야 하는 데이터를 기준으로, 편집을 위해 Excel 통합 문서에 추가해야 하는 엔터티를 선택합니다. 다음 표를 참조로 사용하세요.

    | 거래 유형 | 사용할 데이터 엔터티 |
    |------------------|----------------------|
    | 현금 판매 거래, 온라인 주문, 비동기식 고객 주문, 비동기식 고객 견적 | 거래(감사 가능), 판매 거래(감사 가능), 결제 거래(감사 가능), 세금 거래(감사 가능), 할인 거래(감사 가능), 청구 거래(감사 가능) |
    | 은행 드롭 | 거래(감사 가능), 은행 입찰 거래(감사 가능) |
    | 금고 드롭 | 거래(감사 가능), 금고 입찰 거래(감사 가능) |
    | 입찰 선언 | 거래(감사 가능), 입찰 선언 거래(감사 가능) |
    | 수입, 지출 | 거래(감사 가능), 수입/지출 거래(감사 가능), 결제 거래(감사 가능) |
    | 개시 금액 선언, 입찰 제거, 유동 입력, 입찰 변경, 송장 결제, 고객 보증금 | 거래(감사 가능), 결제 거래(감사 가능) |

    > [!NOTE]
    > 각 Excel 통합 문서에 데이터 엔터티를 반드시 하나만 추가해야 합니다. 또한 키 기호가 표시된 모든 필드를 관련 통합 문서에 추가해야 합니다.

1. 통합 문서가 구성되면 필요한 필터를 적용합니다. 파일의 모든 워크시트에 동일한 필터를 적용해야 합니다. 대량의 데이터를 Excel 파일에 로드해선 안 됩니다. 이렇게 하면 성능이 저하되고 Excel과 시스템 속도가 느려질 수 있습니다. 항상 "회사"와 "명세서 번호" 또는 "거래 번호"를 파일의 필터로 사용하는 것이 좋습니다.
1. 필터가 구성되면 **새로 고침** 을 선택하여 데이터를 로드합니다.
1. 필요한 데이터를 편집한 다음 게시합니다. **게시** 단추를 사용할 수 없다면 일부 중요 필드가 Excel 통합 문서에 추가되지 않았을 것입니다.

## <a name="additional-resources"></a>추가 리소스

[현금 판매 거래 및 현금 관리 거래 편집 및 감사](edit-cash-trans.md)

[온라인 주문 및 비동기 고객 주문 거래 편집 및 감사](edit-order-trans.md)

[소매 거래의 재무 차원 편집](edit-financial-dim.md)

[Excel 통합 문서에 필드를 추가해 소매 거래 편집](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]