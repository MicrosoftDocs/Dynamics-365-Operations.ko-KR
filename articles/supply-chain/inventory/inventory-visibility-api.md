---
title: 재고 가시성 공개 API
description: 이 토픽에서는 재고 가시성에서 제공하는 공개 API에 대해 설명합니다.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f74bb4bd4ed66520c04261bd9f82faad7775817e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449836"
---
# <a name="inventory-visibility-public-apis"></a>재고 가시성 공개 API

[!include [banner](../includes/banner.md)]


이 토픽에서는 재고 가시성에서 제공하는 공개 API에 대해 설명합니다.

재고 가시성 추가 기능의 공개 REST API는 통합을 위한 몇 가지 특정 엔드포인트를 제공합니다. 네 가지 주요 상호 작용 유형을 지원합니다.

- 외부 시스템에서 추가 기능에 현재고 변경 사항 게시
- 외부 시스템의 추가 기능에서 현재고 수량 설정 또는 대체
- 외부 시스템에서 추가 기능에 예약 이벤트 게시
- 외부 시스템에서 현재고 수량 질의

다음 테이블에서는 현재 사용 가능한 API가 나열되어 있습니다.

| 경로 | 메서드 | 설명 |
|---|---|---|
| /api/environment/{environmentId}/onhand | 게시 | [하나의 현재고 변경 이벤트 생성](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | 게시 | [여러 변경 이벤트 만들기](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | 게시 | [현재고 수량 설정/대체](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | 게시 | [하나의 예약 이벤트 생성](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | 게시 | [여러 변경 이벤트 만들기](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | 게시 | [post 메서드를 이용한 쿼리](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Get | [get 메서드를 이용한 쿼리](#query-with-get-method) |

Microsoft는 즉시 사용 가능한 *Postman* 요청 컬렉션을 제공했습니다. 다음 공유 링크를 사용하여 이 컬렉션을 *Postman* 소프트웨어로 가져올 수 있습니다. <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>

> [!NOTE]
> 경로의 {environmentId} 일부는 Microsoft Dynamics LCS(Lifecycle Services)의 환경 ID입니다.
> 
> 대량 API는 각 요청에 대해 최대 512개의 레코드를 반환할 수 있습니다.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Lifecycle Services 환경에 따라 엔드포인트 찾기

재고 가시성의 마이크로 서비스는 여러 지역 및 여러 지역의 Microsoft Azure Service Fabric에 배포됩니다. 현재 요청을 해당 지역 및 지역으로 자동 리디렉션할 수 있는 중앙 엔드포인트가 없습니다. 따라서 다음 패턴을 사용하여 정보 조각을 URL로 구성해야 합니다.

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

지역 약칭은 Microsoft Dynamics LCS(Lifecycle Services) 환경에서 찾을 수 있습니다. 다음 테이블에서는 현재 사용 가능한 지역이 나열되어 있습니다.

| Azure 지역        | 지역 약칭 |
| ------------------- | ----------------- |
| 오스트레일리아 동부      | eau               |
| 오스트레일리아 남동부 | seau              |
| 캐나다 중부      | cca               |
| 캐나다 동부         | eca               |
| 북유럽        | neu               |
| 서유럽         | weu               |
| 미국 동부             | eus               |
| 미국 서부             | wus               |
| 영국 남부            | suk               |
| 영국 서부             | wuk               |
| 일본 동부          | ejp               |
| 일본 서부          | wjp               |
| 브라질 남부        | sbr               |
| 미국 중남부    | scus              |

섬 번호는 LCS 환경이 Service Fabric에 배포된 위치입니다. 현재 사용자 측에서 이 정보를 얻을 수 있는 방법이 없습니다.

Microsoft는 마이크로서비스의 완전한 끝점을 얻을 수 있도록 Power Apps에 UI(사용자 인터페이스)를 구축했습니다. 자세한 내용은 [서비스 엔드포인트 찾기](inventory-visibility-configuration.md#get-service-endpoint)를 참조하세요.

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>인증

플랫폼 보안 토큰은 재고 가시성 공개 API를 호출하는 데 사용됩니다. 따라서 Azure AD 애플리케이션을 사용하여 _Azure Active Directory(Azure AD) 토큰_ 을 생성해야 합니다. 그런 다음 Azure AD 토큰을 사용하여 보안 서비스에서 _access token_ 을 가져와야 합니다.

Microsoft는 즉시 사용 가능한 *Postman* get 토큰 컬렉션을 제공합니다. 다음 공유 링크를 사용하여 이 컬렉션을 *Postman* 소프트웨어로 가져올 수 있습니다. <https://www.getpostman.com/collections/496645018f96b3f0455e>

보안 서비스 토큰을 얻으려면 다음 단계를 따르세요.

1. Azure Portal에 로그인하고 이를 사용하여 Dynamics 365 Supply Chain Management 앱에 대한 `clientId` 및 `clientSecret` 값을 찾습니다.
1. 다음 속성이 있는 HTTP 요청을 제출하여 Azure AD 토큰(`aadToken`)을 가져옵니다.

   - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **메서드** `GET`
   - **본문 내용(양식 데이터):**

     | 키           | 값                                |
     | ------------- | ------------------------------------ |
     | client_id     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | resource      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   응답으로 Azure AD 토큰(`aadToken`)을 받아야 합니다. 다음 예제와 유사해야 합니다.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
       "access_token": "eyJ0eX...8WQ"
   }
   ```

1. 다음 예제와 유사한 JSON(JavaScript Object Notation) 요청을 공식화합니다.

   ```json
   {
       "grant_type": "client_credentials",
       "client_assertion_type": "aad_app",
       "client_assertion": "{Your_AADToken}",
       "scope": "https://inventoryservice.operations365.dynamics.com/.default",
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
       "context_type": "finops-env"
   }
   ```

   다음 요점을 확인하세요.

   - `client_assertion` 값은 이전 단계에서 받은 Azure AD 토큰(`aadToken`)이어야 합니다.
   - `context` 값은 추가 기능을 배포하려는 LCS 환경 ID여야 합니다.
   - 예와 같이 다른 모든 값을 설정합니다.

1. 다음 속성이 있는 HTTP 요청을 제출하여 액세스 토큰(`access_token`)을 가져옵니다.

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **메서드** `POST`
   - **HTTP 헤더:** API 버전을 포함합니다. (키는 `Api-Version`이고 값은 `1.0`입니다.)
   - **본문 내용:** 이전 단계에서 생성한 JSON 요청을 포함합니다.

   응답으로 액세스 토큰(`access_token`)을 받아야 합니다. 재고 가시성 API를 호출하려면 이 토큰을 전달자 토큰으로 사용해야 합니다. 다음은 예입니다.

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> *Postman* 요청 컬렉션을 사용하여 재고 가시성 공개 API를 호출하는 경우 각 요청에 대해 전달자 토큰을 추가해야 합니다. 전달자 토큰을 찾으려면 요청 URL 아래의 **인증** 탭을 선택하고 **전달자 토큰** 유형을 선택한 다음 마지막 단계에서 가져온 액세스 토큰을 복사합니다. 이 토픽의 이후 섹션에서 `$access_token`은 마지막 단계에서 가져온 토큰을 나타내는 데 사용됩니다.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>하나의 현재고 변경 이벤트 생성

직접 변경 이벤트를 생성하기 위한 두 가지 API가 있습니다.

- 단일 레코드 생성: `/api/environment/{environmentId}/onhand`
- 여러 레코드 생성: `/api/environment/{environmentId}/onhand/bulk`

다음 테이블에는 JSON 본문에서 각 필드의 의미가 요약되어 있습니다.

| 필드 ID | 설명 |
|---|---|
| `id` | 특정 변경 이벤트에 대한 고유 ID입니다. 이 ID는 게시 중 서비스와의 통신이 실패할 경우 동일한 이벤트가 다시 제출될 경우 시스템에서 두 번 계산되지 않도록 하는 데 사용됩니다. |
| `organizationId` | 이벤트에 연결된 조직의 식별자입니다. 이 값은 Supply Chain Management의 조직 또는 데이터 영역 ID에 매핑됩니다. |
| `productId` | 제품의 식별자입니다. |
| `quantities` | 현재고 수량이 변경되어야 하는 수량입니다. 예를 들어 10개의 새 책이 서가에 추가되면 이 값은 `quantities:{ shelf:{ received: 10 }}`이 됩니다. 서가에서 세 권의 책을 꺼내거나 판매하는 경우 이 값은 `quantities:{ shelf:{ sold: 3 }}`입니다. |
| `dimensionDataSource` | 변경 게시 이벤트 및 쿼리에 사용되는 차원의 데이터 원본입니다. 데이터 원본을 지정하면 지정된 데이터 원본의 사용자 정의 차원을 사용할 수 있습니다. 재고 가시성은 차원 구성을 사용하여 사용자 정의 차원을 일반 기본 차원에 매핑할 수 있습니다. `dimensionDataSource` 값이 지정되지 않은 경우 쿼리에 일반 [기본 차원](inventory-visibility-configuration.md#data-source-configuration-dimension)만 사용할 수 있습니다. |
| `dimensions` | 동적 키-값 쌍입니다. 값은 Supply Chain Management의 일부 차원에 매핑됩니다. 그러나 이벤트가 Supply Chain Management에서 오는지 아니면 외부 시스템에서 오는지를 나타내기 위해 사용자 정의 차원(예: _소스_)을 추가할 수도 있습니다. |

> [!NOTE]
> `SiteId` 및 `LocationId` 매개 변수는 [파티션 구성](inventory-visibility-configuration.md#partition-configuration)을 구성합니다. 따라서 현재고 변경 이벤트를 생성하거나, 현재고 수량을 설정 또는 대체하거나, 예약 이벤트를 생성할 때 차원에서 지정해야 합니다.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>하나의 현재고 변경 이벤트 생성

이 API는 단일 변경 이벤트를 생성합니다.

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

다음 예는 샘플 본문 내용을 보여줍니다. 이 샘플에서는 *티셔츠* 제품에 대한 변경 이벤트를 게시합니다. 이 이벤트는 POS(Point of Sale) 시스템에서 진행되며 고객이 빨간색 티셔츠를 매장에 반품했습니다. 이 이벤트는 *티셔츠* 제품의 수량을 1 증가시킵니다.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

다음 예는 `dimensionDataSource`이 없는 샘플 본문 콘텐츠를 보여줍니다. 이 경우 `dimensions`이 [기본 차원](inventory-visibility-configuration.md#data-source-configuration-dimension)이 됩니다. `dimensionDataSource`이 설정되면 `dimensions`는 데이터 원본 차원 또는 기본 차원이 될 수 있습니다.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>여러 변경 이벤트 만들기

이 API는 동시에 여러 레코드를 생성할 수 있습니다. 이 API와 [단일 이벤트 API](#create-one-onhand-change-event)의 유일한 차이점은 `Path` 및 `Body` 값입니다. 이 API의 경우 `Body`는 레코드 배열을 제공합니다. 최대 레코드 수는 512개이며, 이는 즉시 변경 대량 API가 한 번에 최대 512개의 변경 이벤트를 지원할 수 있음을 의미합니다.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

다음 예는 샘플 본문 내용을 보여줍니다.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>현재고 수량 설정/재정의

_현재고 설정_ API는 지정된 제품의 현재 데이터를 재정의합니다.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

다음 예는 샘플 본문 내용을 보여줍니다. 이 API의 동작은 이 항목 앞부분의 [현재고 변경 이벤트 생성](#create-onhand-change-event) 섹션에 설명된 API의 동작과 다릅니다. 이 샘플에서 *티셔츠* 제품의 수량은 1로 설정됩니다.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>예약 이벤트 생성

*예약* API를 사용하려면 예약 기능을 열고 예약 구성을 완료해야 합니다. 자세한 내용은 [예약 구성(선택 사항)](inventory-visibility-configuration.md#reservation-configuration)을 참조하세요.

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>하나의 예약 이벤트 생성

다른 데이터 원본 설정에 대해 예약할 수 있습니다. 이 유형의 예약을 구성하려면 먼저 `dimensionDataSource` 매개 변수에 데이터 원본을 지정하세요. 그런 다음 `dimensions` 매개 변수에서 대상 데이터 원본의 차원 설정에 따라 차원을 지정합니다.

예약 API를 호출할 때 요청 본문에 부울 `ifCheckAvailForReserv` 매개 변수를 지정하여 예약 유효성 검사를 제어할 수 있습니다. 값 `True`는 유효성 검사가 필요함을 의미하고 `False` 값은 유효성 검사가 필요하지 않음을 의미합니다. 기본값은 `True`입니다.

예약을 취소하거나 지정된 재고 수량을 예약 해제하려면 수량을 음수로 설정하고 `ifCheckAvailForReserv` 매개 변수를 `False`로 설정하여 유효성 검사를 건너뜁니다.

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

다음 예는 샘플 본문 내용을 보여줍니다.

```json
{
    "id": "reserve-0",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>여러 예약 이벤트 생성

이 API는 [단일 이벤트 API](#create-one-reservation-event)의 벌크 버전입니다.

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="query-on-hand"></a>보유 재고 쿼리

_보유 재고 쿼리_ API를 사용하여 제품에 대한 현재 보유 재고 데이터를 가져옵니다. API는 현재 `ProductID` 값으로 최대 100개의 개별 항목 쿼리를 지원합니다. 여러 `SiteID` 및 `LocationID` 값을 각 쿼리에 지정할 수도 있습니다. 최대 제한은 `NumOf(SiteID) * NumOf(LocationID) <= 100`로 정의됩니다.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>post 메서드를 이용한 쿼리

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

이 요청의 본문 부분에서 `dimensionDataSource`는 여전히 선택적 매개변수입니다. 설정하지 않으면 `filters`가 *기본 차원* 으로 처리됩니다. `filters`에는 `organizationId`, `productId`, `siteId` 및 `locationId`의 네 가지 필수 필드가 있습니다.

- `organizationId`에는 값이 하나만 포함되어야 하지만 여전히 배열입니다.
- `productId`에는 하나 이상의 값을 포함할 수 있습니다. 빈 배열이면 모든 제품이 반환됩니다.
- `siteId` 및 `locationId`는 재고 가시성에서 파티셔닝에 사용됩니다. *보유 재고 쿼리* 요청에서 둘 이상의 `siteId` 및 `locationId` 값을 지정할 수 있습니다. 현재 릴리스에서는 `siteId` 및 `locationId` 값을 모두 지정해야 합니다.

`groupByValues` 매개 변수는 인덱싱 구성을 따라야 합니다. 자세한 내용은 [제품 인덱스 계층 구성](./inventory-visibility-configuration.md#index-configuration)을 참조하세요.

`returnNegative` 매개 변수는 결과에 음수 항목이 포함되는지 여부를 제어합니다.

다음 예는 샘플 본문 내용을 보여줍니다.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

다음 예는 특정 사이트 및 위치의 모든 제품을 쿼리하는 방법을 보여줍니다.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>get 메서드를 이용한 쿼리

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

다음은 샘플 가져오기 URL입니다. 이 get 요청은 이전에 제공된 포스트 샘플과 정확히 동일합니다.

```txt
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
