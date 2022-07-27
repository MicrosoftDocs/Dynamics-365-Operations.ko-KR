---
title: 고객 포털 사용자 지정 및 사용
description: 이 토픽에서는 시스템에 추가된 고객 포털을 사용자 지정하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 02ad0470b7886b2e9b259682a7f8c8150d656cfb
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449866"
---
# <a name="customize-and-use-the-customer-portal"></a>고객 포털 사용자 지정 및 사용

[!include [banner](../includes/banner.md)]


이 토픽에서는 기본적으로 고객 포털에서 사용할 수 있는 다양한 페이지에 대해 설명합니다. 페이지의 기능과 사용자 지정 방법에 대해 설명합니다.

고객 포털은 몇 가지 웹 페이지와 즉시 사용할 수 있는 작업을 제공합니다. 다음 사이트 맵은 해당 웹 페이지 및 작업에 대한 개요와 작업을 수행할 수 있는 역할을 제공합니다.

![고객 포털 사이트 맵.](media/customer-portal-site-map.png "고객 포털 사이트 맵")

## <a name="typical-customizations"></a>일반적인 사용자 지정

다음 토픽은 Power Apps 포털에 대한 기본 사항과 포털을 사용자 지정하는 방법을 배우는 데 도움이 됩니다.

- [템플릿 작업](/powerapps/maker/portals/work-with-templates) – 이 토픽에서는 Power Apps 포털의 작동 방식과 포털의 간단한 사용자 지정을 수행하는 방법에 대한 일반적인 개요를 제공합니다.
- [포털 콘텐츠 관리](/dynamics365/portals/manage-portal-content) – 이 토픽에서는 포털에 표시되는 콘텐츠를 관리하고 사용자 지정하는 방법에 대해 설명합니다.
- [CSS 편집](/powerapps/maker/portals/edit-css) – 이 토픽은 포털의 UI(사용자 인터페이스)에 대해 보다 복잡한 사용자 지정 항목을 수행하는 데 도움이 됩니다.
- [포털 테마 만들기](/dynamics365/portals/create-theme) – 이 토픽은 포털의 UI 테마를 만드는 데 도움이 됩니다.
- [포털 콘텐츠를 쉽게 만들고 노출하가](/dynamics365/portals/create-expose-portal-content) – 이 토픽은 포털에 사용하는 기본 데이터 및 테이블을 관리하는 데 도움이 됩니다.
- [포털에서 사용할 연락처 구성](/powerapps/maker/portals/configure/configure-contacts) – 이 토픽에서는 사용자 역할을 만들고 사용자 지정하는 방법과 Power Apps 보안 및 인증이 작동하는 방법에 대해 설명합니다.
- [포털에서 테이블 양식 및 웹 양식에 대한 메모 구성](/powerapps/maker/portals/configure-notes) – 이 토픽에서는 포털에 문서 및 추가 스토리지를 추가하는 방법에 대해 설명합니다.
- [포털 웹 사이트에 대한 오류 처리](/powerapps/maker/portals/admin/view-portal-error-log) – 이 토픽에서는 포털 오류 로그를 보고 Microsoft Azure Blob Storage 계정에 저장하는 방법에 대해 설명합니다.

## <a name="customize-the-order-creation-process"></a>주문 생성 프로세스 사용자 지정

사용자가 고객 포털을 사용하여 주문을 제출하면 주문이 해당 Dynamics 365 Supply Chain Management 환경에 자동으로 동기화됩니다. 사용자는 외부 고객이기 때문에 일부 필수 정보는 의도적으로 숨겨져 있습니다. 이 정보는 양식이 제출될 때 자동으로 채워집니다.

이 섹션에서는 오류를 방지하기 위해 연락처를 설정하는 방법을 보여줍니다. 자동으로 설정되는 필드와 필요한 경우 해당 필드의 값을 수정하는 방법에 대해 설명합니다.

### <a name="the-out-of-box-order-creation-process"></a>기본 주문 생성 프로세스

다음은 고객 포털에서 주문을 제출하는 표준 단계입니다.

1. 홈 페이지에서 **주문 만들기** 타일을 선택하여 **주문 만들기** 마법사를 엽니다.
1. **주문 정보** 페이지에서 다음 필드를 설정합니다.

    - **요청받은 수령일** - 배송일을 지정합니다.
    - **배송 주소** – 주문을 배송해야 하는 주소를 입력합니다.
    - **회사** – 고객 회사 이름을 선택합니다. 이 필드는 관리자가 아닌 사용자에 대해 자동으로 설정됩니다.
    - **요청 번호** – 주문의 요청 번호를 입력합니다. 이 필드는 필수 항목이 아닙니다.
    - **배송 국가/지역** – 항목이 배송될 국가 또는 지역을 입력합니다. 이 필드는 관리자가 아닌 사용자에 대해 자동으로 설정됩니다.

    ![주문 정보 페이지.](media/customer-portal-order-information.png "주문 정보 페이지")

1. **다음** 을 선택합니다.
1. **항목** 페이지에서 **항목 추가** 를 선택합니다.

    ![항목 페이지.](media/customer-portal-items.png "항목 페이지")

1. **항목 정보** 대화 상자에서 다음 필드를 설정합니다.

    - **제품 이름** – 주문에 추가할 제품을 찾아 선택합니다.
    - **수량** – 선택한 제품의 수량을 입력합니다.
    - **단위** – 측정 단위를 지정합니다(예: **개**., **kg** 또는 **상자**).
    - **예상 순액** – 값은 항목의 예상 가격 × 선택한 단위의 수량으로 계산됩니다. 

    ![항목 정보 대화 상자.](media/customer-portal-item-information.png "항목 정보 대화 상자")

1. **제출** 을 선택하여 항목을 주문에 추가합니다.
1. 주문하려는 항목을 모두 추가할 때까지 4~6단계를 반복합니다.
1. 항목이 추가되면 **항목** 페이지에서 **다음** 을 선택합니다.
1. **주문 정보** 페이지는 주문 요약을 제공합니다. 주문 내용 및 배달 세부 정보를 확인하세요. 모든 것이 올바르면 **제출** 을 선택하여 주문을 제출합니다.

    ![주문 정보 페이지를 완료했습니다.](media/customer-portal-order-submit.png "주문 정보 페이지 완료")

### <a name="standard-data-setup"></a>표준 데이터 설정

원활한 사용자 경험을 보장하기 위해 고객 포털은 여러 필수 필드에 대한 값을 자동으로 채웁니다. 이 값은 주문을 제출하는 고객의 연락처 레코드에 있는 정보를 기반으로 합니다.

고객 포털을 사용하여 주문을 제출할 고객에 속한 각 [연락처 행](/powerapps/maker/portals/configure/configure-contacts)에 대해 다음 필수 필드에 값을 지정해야 합니다. 지정하지 않으면 오류가 발생합니다.

- **회사** – 주문이 속한 법인
- **잠재 고객** – 주문과 연결된 고객 계정
- **가격표** – 고객을 위한 맞춤형 가격표
- **통화** – 가격의 통화
- **배송 국가/지역** – 항목이 배송될 국가 또는 지역

판매 주문 테이블에 대해 다음 필드가 자동으로 설정됩니다.

- **언어** – 주문 언어(기본적으로 연락처 레코드에서 값을 가져옴)
- **배송 국가/지역** – 항목이 배송될 국가 또는 지역(기본값은 연락처 레코드에서 가져옴)
- **담당자** – 주문에 대한 정보를 문의할 수 있는 사용자(기본값은 연락처 레코드에서 가져옴)
- **회사** – 주문이 속한 법인(기본적으로 연락처 레코드에서 값을 가져옴)
- **잠재 고객** – 주문과 연결된 고객 계정(기본적으로 연락처 레코드에서 값을 가져옴)
- **송장 고객** – 주문의 청구 계정(기본값은 연락처 레코드의 잠재 고객)
- **판매 주문 이름** – 판매 주문의 이름(기본값은 **판매 주문**)
- **통화** – 가격의 통화(기본적으로 값은 연락처 레코드에서 가져옴)
- **가격표** – 고객에 대한 사용자 정의 가격 목록(기본적으로 값은 연락처 레코드에서 가져옴)
- **배달 주소 설명** – 판매 주문의 배송 주소(기본값은 **배달 주소 설명**)

### <a name="modify-the-order-creation-process"></a>주문 생성 프로세스 수정

기본 주문 생성 절차를 변경하지 않으면 고객 포털의 모양과 UI를 자유롭게 수정할 수 있습니다. 주문 생성 절차를 변경하려는 경우 염두에 두어야 할 몇 가지 사항이 있습니다.

Microsoft Dataverse의 판매 주문 테이블에서 다음 열을 제거하지 마세요. 이중 쓰기로 판매 주문을 생성하는 데 필요하기 때문입니다.

- **회사** – 주문이 속한 법인
- **이름** – 판매 주문의 이름
- **통화** – 가격의 통화
- **가격표** – 고객을 위한 맞춤형 가격표
- **배송 국가/지역** – 항목이 배송될 국가 또는 지역
- **잠재 고객** – 주문과 연결된 고객 계정
- **언어** – 주문 언어(일반적으로 이 언어는 잠재 고객의 언어)
- **배달 주소 설명** – 판매 주문의 배달 주소

항목의 경우 다음은 필수 열입니다.

- **제품** – 주문할 제품
- **수량** – 선택한 제품의 수량
- **단위** – 측정 단위(예: **개**., **kg** 또는 **상자**)
- **배송 국가/지역** – 배송 국가 또는 지역
- **배달 주소 설명** – 판매 주문의 배달 주소

고객 포털이 이러한 모든 열에 대한 값을 어떻게든 제출하는지 확인해야 합니다.

페이지에 열을 추가하거나 열을 제거하려면 [간소화된 데이터 입력 환경을 위한 빠른 만들기 양식 만들기 또는 편집](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms)을 참조하세요.

열이 사전 설정되는 방식과 페이지가 저장될 때 값이 설정되는 방식을 변경하려면 Power Apps 포털 설명서에서 다음 정보를 참조하세요.

- [사전에 필드 채우기](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [저장 시 값 설정](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>홈 페이지 사용자 지정

고객 포털의 모든 컨트롤은 기본 제공 Power Apps 포털 컨트롤입니다. Power Apps 포털 문서의 [페이지 작성](/powerapps/maker/portals/compose-page)에 있는 단계에 따라 이를 사용자 지정할 수 있습니다.

고객 포털 템플릿에 포함된 유일한 사용자 지정 컨트롤은 홈 페이지에 타일을 만드는 데 사용됩니다.

![홈 페이지의 타일.](media/customer-portal-home-page-tiles.png "홈 페이지의 타일")

타일을 수정하려면 다음 단계를 따르세요.

1. [포털 관리 앱](/powerapps/maker/portals/configure/configure-portal)을 엽니다.
1. 왼쪽 탐색 창에서 **페이지 템플릿** 을 선택합니다.

    ![포털 관리 탐색 창.](media/customer-portal-nav.png "포털 관리 탐색 창")

1. **홈** 이라는 페이지 템플릿을 선택합니다.
1. **웹 템플릿** 필드에서 **홈** 링크를 선택하여 해당 페이지의 소스 코드를 엽니다.

    ![웹 템플릿 필드.](media/customer-portal-web-template.png "웹 템플릿 필드")

1. 이제 홈 페이지의 모든 소스 코드가 표시되어야 하며 필요에 따라 수정할 수 있습니다.

## <a name="resources"></a>리소스

고객 포털을 설정하고 사용자 지정하는 방법에 대해 자세히 알아보려면 다음 리소스를 참조하세요.

- [Power Apps 포털 문서](/powerapps/maker/portals/overview)
- [이중 쓰기 문서](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [포털 수명 주기 정보](/powerapps/maker/portals/admin/portal-lifecycle)
- [포털 업그레이드](/powerapps/maker/portals/admin/upgrade-portal)
- [포털 구성 마이그레이션](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [솔루션 수명 주기 관리: Dynamics 365 for Customer Engagement 앱](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]