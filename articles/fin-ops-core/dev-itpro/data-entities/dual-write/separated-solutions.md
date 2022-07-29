---
title: 분리된 이중 쓰기 애플리케이션 오케스트레이션 패키지
description: 이중 쓰기 응용 프로그램 조정 패키지는 더 이상 단일 패키지가 아니라 더 작은 패키지로 분리되었습니다. 이 항목에서는 각 패키지에 포함된 솔루션 및 맵과 다른 패키지에 대한 종속성에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 11/29/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: e2f870368dc662032a3e7ca7ddca902feb23a713
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461040"
---
# <a name="separated-dual-write-application-orchestration-package"></a>분리된 이중 쓰기 애플리케이션 오케스트레이션 패키지

[!include [banner](../../includes/banner.md)]



이전에는 이중 쓰기 애플리케이션 오케스트레이션 패키지가 다음 솔루션이 포함된 단일 패키지였습니다.

- Dynamics 365 노트
- Dynamics 365 Finance 및 운영 공통 앵커
- Dynamics 365 Finance 및 작업 이중 쓰기 엔터티 맵
- Dynamics 365 자산 관리 앱
- Dynamics 365 자산 관리
- HCM 공통
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Dynamics 365 Finance 및 운영 공통
- Dynamics 365 Company
- 통화 환율
- Field Service Common

단일 패키지였기 때문에 이 패키지는 고객에게 "전부 아니면 전무" 상황을 만들었습니다. 그러나 Microsoft는 이제 이를 더 작은 패키지로 분리했습니다. 따라서 고객은 필요한 솔루션에 대한 패키지만 선택할 수 있습니다. 예를 들어 Microsoft Dynamics 365 Supply Chain Management 고객이며 Dynamics 365 Human Resources, 노트 및 자산 관리와 통합할 필요가 없다면 해당 솔루션을 설치된 솔루션에서 제외할 수 있습니다. 기본 솔루션 이름, 게시자 및 지도 버전이 동일하게 유지되기 때문에 이 변경 사항은 중요하지 않습니다. 기존 설치가 업그레이드됩니다.

![분리된 패키지입니다.](media/separated-package-1.png)

이 항목에서는 각 패키지에 포함된 솔루션 및 맵과 다른 패키지에 대한 종속성에 대해 설명합니다.

## <a name="dual-write-application-core"></a>이중 쓰기 애플리케이션 코어

이중 쓰기 애플리케이션 코어 패키지를 사용하면 사용자가 고객 참여 앱 없이 이중 쓰기를 설치 및 구성할 수 있습니다. 여기에는 다음 5가지 솔루션이 포함되어 있습니다.

| 고유 이름                           | 디스플레이 이름                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Finance 및 운영 공통 |
| CurrencyExchangeRates                 | 통화 환율                    |
| msdyn_DualWriteAppCoreMaps            | 이중 쓰기 애플리케이션 핵심 엔티티 맵   |
| msdyn_DualWriteAppCoreAnchor          | 이중 쓰기 애플리케이션 코어 앵커        |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영 앱     | Customer Engagement 앱                    |
|---------------------------------|---------------------------------------------|
| 운영 단위                  | msdyn_internalorganizations                 |
| 조직 계층 구조          | msdyn_internalorganizationhierarchies       |
| 법인                  | msdyn_internalorganizations                 |
| 법인                  | cdm_companies                               |
| 조직 계층 구조 목적 | msdyn_internalorganizationhierarchypurposes |
| 환율 통화 쌍     | msdyn_currencyexchangeratepairs             |
| 이름 접미사                    | msdyn_nameaffixes                           |
| 환율 유형              | msdyn_exchangeratetypes                     |
| CDS 환율              | msdyn_currencyexchangerates                 |
| 조직 계층 구조 유형     | msdyn_internalorganizationhierarchytypes    |
| 통화                      | transactioncurrencies                       |
| 혼합 현실 가이드 엔터티     | msmrw_guides                                |

**종속성 정보**

이중 쓰기 Application Core 패키지는 다른 패키지에 종속되지 않습니다.

## <a name="dual-write-human-resources"></a>이중 쓰기 인적 자원

이중 쓰기 인적 자원 패키지에는 인적 자원 데이터를 동기화하는 데 필요한 솔루션과 맵이 포함되어 있습니다. 여기에는 다음 3가지 솔루션이 포함되어 있습니다.

| 고유 이름                | 디스플레이 이름                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | HCM 공통                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources 엔티티 맵 |
| msdyn_Dynamics365HCMAnchor | Dynamics 365 Human Resources 앵커      |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영 앱 | Customer Engagement 앱         |
|-----------------------------|----------------------------------|
| 민족적 혈통              | cdm_ethnicorigins                |
| 보상 직무 기능   | cdm_jobfunctions                 |
| 직위 V2                | cdm_jobpositions                 |
| 직무                        | cdm_jobs                         |
| 보상 직무 유형       | cdm_jobtypes                     |
| 언어 코드              | cdm_languages                    |
| 직책 유형               | cdm_positiontypes                |
| 작업자 배정 직위 | cdm_positionworkerassignmentmaps |
| 베테랑 상태              | cdm_veteranstatuses              |
| 작업자                      | cdm_workers                      |
| 기업별 고용      | cdm_employments                  |

**종속성 정보**

이중 쓰기 인적 자원 패키지는 이중 쓰기 애플리케이션 코어 패키지에 따라 다릅니다. 따라서 이중 쓰기 인적 자원 패키지를 설치하기 전에 이중 쓰기 애플리케이션 코어 패키지를 설치해야 합니다.

## <a name="dual-write-supply-chain"></a>이중 쓰기 공급망

이중 쓰기 공급망 패키지에는 Supply Chain Management 데이터를 동기화하는 데 필요한 솔루션과 맵이 포함되어 있습니다. 여기에는 다음 3가지 솔루션이 포함되어 있습니다.

| 고유 이름                                | 디스플레이 이름                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management 확장 엔터티 맵 |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management 확장 앵커      |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영 앱                 | Customer Engagement 앱                      |
|---------------------------------------------|-----------------------------------------------|
| 단위                                       | uoms                                          |
| CDS 판매 주문 헤더                     | salesorders                                   |
| CDS 판매 주문 라인                       | salesorderdetails                             |
| CDS 판매 견적 헤더                  | quotes                                        |
| CDS 판매 견적 라인                   | quotedetails                                  |
| CDS 출시 고유 제품              | 제품                                      |
| 창고 구역                             | msdyn_warehousezones                          |
| 창고 구역 그룹                       | msdyn_warehousezonegroups                     |
| 창고 작업 라인                        | msdyn_warehouseworklines                      |
| 창고 작업 헤더                      | msdyn_warehouseworkheaders                    |
| 창고                                  | msdyn_warehouses                              |
| 인벤토리 통로                             | msdyn_warehouseaisles                         |
| 단위 변환                            | msdyn_unitofmeasureconversions                |
| 배달 조건                           | msdyn_termsofdeliveries                       |
| 배송 모드                           | msdyn_shipvias                                |
| 제품 마스터 스타일                       | msdyn_sharedproductstyles                     |
| 판매 송장 라인 V2                      | invoicedetails                                |
| 판매 송장 헤더 V2                    | 송장                                      |
| 제품 마스터 크기                        | msdyn_sharedproductsizes                      |
| 출시된 제품 V2                        | msdyn_sharedproductdetails                    |
| 제품 마스터 구성               | msdyn_sharedproductconfigurations             |
| 제품 마스터 색상                       | msdyn_sharedproductcolors                     |
| 판매 주문 기원 코드                    | msdyn_salesorderorigins                       |
| 제품 영수증 헤더                      | msdyn_purchaseorderreceipts                   |
| 제품 수령 라인                        | msdyn_purchaseorderreceiptproducts            |
| 구매 주문 헤더 V2                   | msdyn_purchaseorders                          |
| CDS 구매 주문 라인 일시 삭제 엔터티 | msdyn_purchaseorderproducts                   |
| CDS 구매 주문 라인 엔터티              | msdyn_purchaseorderproducts                   |
| 추적 규모 그룹                   | msdyn_producttrackingdimensiongroups          |
| 스타일                                      | msdyn_productstyles                           |
| 재고 규모 그룹                    | msdyn_productstoragedimensiongroups           |
| 제품별 단위 변환           | msdyn_productspecificunitofmeasureconversions |
| 제품 기본 주문 설정 V2           | msdyn_productspecificdefaultordersettings     |
| 크기                                       | msdyn_productsizes                            |
| 제품 크기 그룹                    | msdyn_productdimensiongroups                  |
| 기본 주문 설정                      | msdyn_productdefaultordersettings             |
| 구성                              | msdyn_productconfigurations                   |
| 모든 제품                                | msdyn_globalproducts                          |
| 색상                                      | msdyn_productcolors                           |
| 제품 범주 계층 역할            | msdyn_productcategoryhierarchyroles           |
| 제품 범주 계층                | msdyn_productcategoryhierarchies              |
| 제품 범주 할당                | msdyn_productcategoryassignments              |
| 제품 범주                          | msdyn_productcategories                       |
| 창고 위치                         | msdyn_inventorylocations                      |
| CDS 재고 켜기                            | msdyn_inventoryonhandentries                  |
| 제품 범주                          | msdyn_productcategories                       |
| CDS 재고 켜기                            | msdyn_inventoryonhandrequests                 |
| 제품 번호 식별 바코드           | msdyn_productbarcodes                         |
| 로열티 카드                                | msdyn_loyaltycards                            |
| 충성도 보상 포인트                       | msdyn_loyaltyrewardpoints                     |
| 가격 고객 그룹                       | msdyn_pricecustomergroups                     |
| 사이트                                       | msdyn_operationalsites                        |
| CDS 판매 견적 라인                   | quotedetails                                  |
| CDS 판매 주문 라인                       | salesorderdetails                             |

**종속성 정보**

이중 쓰기 공급망 패키지는 다음 세 가지 패키지에 따라 다릅니다. 따라서 이중 쓰기 공급망 패키지를 설치하기 전에 이러한 패키지를 설치해야 합니다.

- 이중 쓰기 애플리케이션 코어 패키지
- 이중 쓰기 금융 패키지
- 이중 쓰기 인적 자원 패키지

## <a name="dual-write-finance"></a>이중 쓰기 금융

이중 쓰기 금융 패키지에는 Dynamics 365 Finance 데이터를 동기화하는 데 필요한 솔루션과 맵이 포함되어 있습니다. 여기에는 다음 4가지 솔루션이 포함되어 있습니다.

| 고유 이름                            | 디스플레이 이름                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Dynamics 365 Finance Extended 엔터티 맵 |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Dynamics 365 Finance Extended 앵커      |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영 앱             | Customer Engagement 앱        |
|-----------------------------------------|---------------------------------|
| 원천징수세 그룹                  | msdyn_withholdingtaxgroups      |
| CDS 연락처 V2(고객)              | 연락처                        |
| CDS 연락처 V2(공급업체)                | 연락처                        |
| 고객 V3                            | 연락처                        |
| 원천징수세 코드                   | msdyn_withholdingtaxcodes       |
| 공급업체 V2                              | msdyn_vendors                   |
| 공급업체 결제 방법                   | msdyn_vendorpaymentmethods      |
| 공급업체 그룹                           | msdyn_vendorgroups              |
| 계정 차트                       | msdyn_chartofaccountses         |
| 판매세 원장 기장 그룹 V2      | msdyn_taxpostinggroups          |
| 품목 판매세 그룹                    | msdyn_taxitemgroups             |
| 판매세 그룹                        | msdyn_taxgroups                 |
| 판매 면세 코드 엔터티 CDS        | msdyn_taxexemptcodes            |
| 고객 그룹                         | msdyn_customergroups            |
| 고객 결제 방법                 | msdyn_customerpaymentmethods    |
| 재무 차원                    | msdyn_dimensionattributes       |
| 판매세 당국                   | msdyn_taxauthorities            |
| 재무 차원 형식              | msdyn_financialdimensionformats |
| 회계 달력 기간                  | msdyn_fiscalcalendarperiods     |
| 회계 캘린더 통합 엔터티      | msdyn_fiscalcalendars           |
| 회계 캘린더 연도 통합 엔터티 | msdyn_fiscalcalendaryears       |
| 지불 조건                        | msdyn_paymentterms              |
| 지불 일정                        | msdyn_paymentschedules          |
| 지불 일정 라인                  | msdyn_paymentschedulelines      |
| 지불일 CDS                        | msdyn_paymentdays               |
| 지불일 라인 CDS V2                | msdyn_paymentdaylines           |
| 주 계정                            | msdyn_mainaccounts              |
| 주 계정 카테고리                 | msdyn_mainaccountcategories     |
| 원장                                  | msdyn_ledgers                   |
| 고객 V3                            | 계정                        |

**종속성 정보**

이중 쓰기 금융 패키지는 이중 쓰기 애플리케이션 코어 패키지에 따라 다릅니다. 따라서 이중 쓰기 금융 패키지를 설치하기 전에 이중 쓰기 애플리케이션 코어 패키지를 설치해야 합니다.

## <a name="dual-write-notes"></a>이중 쓰기 메모

이중 쓰기 노트 패키지에는 노트 또는 주석 데이터를 동기화하는 데 필요한 솔루션과 맵이 포함되어 있습니다. 여기에는 다음 4가지 솔루션이 포함되어 있습니다.

| 고유 이름                  | 디스플레이 이름                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 노트             |
| Dynamics365NotesExtended     | Dynamics 365 노트 확장    |
| msdyn_Dynamics365NotesMaps   | Dynamics 365 노트 엔터티 맵 |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 노트 앵커      |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영                     | Customer Engagement |
|--------------------------------------------|---------------------|
| 매도 주문 헤더 문서 첨부 파일    | 주석         |
| 고객 첨부 파일                       | 주석         |
| 공급업체 문서 첨부                | 주석         |
| 구매 주문 헤더 문서 첨부 파일 | 주석         |

**종속성 정보**

이중 쓰기 노트 패키지는 다음 두 가지 패키지에 따라 다릅니다. 따라서 이중 쓰기 노트 패키지를 설치하기 전에 이러한 패키지를 설치해야 합니다.

- 이중 쓰기 애플리케이션 코어 패키지
- 이중 쓰기 금융 패키지

## <a name="dual-write-asset-management"></a>이중 쓰기 자산 관리

이중 쓰기 자산 관리 패키지에는 Supply Chain Management 또는 Dynamics 365 Field Service의 자산 데이터를 동기화하는 데 필요한 솔루션과 맵이 포함되어 있습니다. 여기에는 다음 4가지 솔루션이 포함되어 있습니다.

| 고유 이름                          | 디스플레이 이름                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 자산 관리             |
| Dynamics365AssetManagementApp        | Dynamics365 자산 관리 앱          |
| msdyn_DualWriteAssetManagementMaps   | Dynamics 365 자산 관리 엔터티 맵 |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 자산 관리 앵커      |

이 패키지에서 다음과 같은 맵을 사용할 수 있습니다.

| 금융 및 운영 앱                           | Customer Engagement 앱                |
|-------------------------------------------------------|-----------------------------------------|
| 자산 관리 보증                             | msdyn_warranties                        |
| 자산 관리 모델                               | msdyn_models                            |
| 자산 관리 제조업체                        | msdyn_manufacturers                     |
| 자산 관리 기능적 위치 유형            | msdyn_functionallocationtypes           |
| 자산 관리 기능적 위치                 | msdyn_functionallocations               |
| 자산 관리 기능적 위치 수명 주기 상태 | msdyn_functionallocationlifecyclestates |
| 자산 관리 기능적 위치 수명 주기 모델 | msdyn_functionallocationlifecyclemodels |
| 자산 관리 자산                               | msdyn_customerassets                    |
| 자산 관리 자산 유형                          | msdyn_customerassetcategories           |
| 자산 관리 자산 수명 주기 상태               | msdyn_assetlifecyclestates              |
| 자산 관리 자산 수명 주기 모델               | msdyn_assetlifecyclemodels              |

**종속성 정보**

이중 쓰기 자산 관리 패키지는 이중 쓰기 애플리케이션 코어 패키지에 따라 다릅니다. 따라서 이중 쓰기 자산 관리 패키지를 설치하기 전에 이중 쓰기 애플리케이션 코어 패키지를 설치해야 합니다.

## <a name="packages-required-for-project-operations"></a>Project Operations에 필요한 패키지
Project Operations는 다음 패키지에 따라 다릅니다. 따라서 Project Operations를 설치하기 전에 이러한 패키지를 설치해야 합니다.

- 이중 쓰기 애플리케이션 코어 패키지
- 이중 쓰기 금융 패키지
- 이중 쓰기 공급망 패키지
- 이중 쓰기 자산 관리 패키지
- 이중 쓰기 인적 자원 패키지
