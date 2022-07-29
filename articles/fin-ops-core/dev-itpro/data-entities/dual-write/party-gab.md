---
title: 파티 및 전체 주소록
description: 이 항목에서는 이중 쓰기의 파티 및 전체 주소록 기능에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 2e0d16b29a71da23acc925c09c87f0bb4776759c
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8461020"
---
# <a name="party-and-global-address-book"></a>파티 및 전체 주소록

[!include [banner](../../includes/banner.md)]



*파티* 및 *전체 주소록* 은 재무 및 운영 응용 프로그램의 개념입니다. 파티는 조직이나 개인이 될 수 있습니다. 이름, 언어, 연락처 및 주소와 같은 당사자의 속성을 전역적으로 저장하고 관리하는 것이 편리합니다. 그런 다음 한 곳에서 속성 값이 변경되면 해당 변경 사항이 당사자가 관련된 모든 곳에 반영됩니다.

## <a name="party"></a>당사자

당사자는 비즈니스에 관련된 개인 또는 조직입니다. 당사자 개념이 사용되는 경우 개인 또는 조직은 비즈니스에서 둘 이상의 역할(예: 작업자, 고객, 공급업체 또는 담당자)을 수행할 수 있습니다. 역할은 컨텍스트와 목적을 기반으로 합니다. 다음은 두 가상 회사 Contoso 및 Fabrikam의 역할에 대한 몇 가지 예입니다.

+ **작업자** – 직원. Contoso의 직원이 그 예입니다.
+ **공급업체** – 기업에 상품이나 서비스를 공급하는 공급업체 조직 또는 개인 사업자. 예를 들어 Fabrikam이 Contoso에 소모품을 판매하는 경우 Fabrikam은 Contoso의 공급업체입니다.
+ **연락처** – 연락할 사람. 예를 들어 Contoso가 Fabrikam에서 소모품을 구매하는 경우 Contoso의 직원은 Fabrikam의 연락처에 연락합니다.
+ **고객** – 회사에서 물건을 사는 사람이나 회사. 예를 들어 Contoso가 Fabrikam에서 소모품을 구매하는 경우 Contoso는 Fabrikam의 고객입니다.

파티 모델은 특히 파티가 둘 이상의 역할을 수행할 때 조직과 사람 간의 중간에서 복잡한 관계를 나타내는 데 자주 사용됩니다. 여기 일반적인 예가 있습니다.

+ 당사자는 고객과 공급업체 모두가 될 수 있습니다. 예를 들어 북미에서 Fabrikam은 Contoso에 전선을 판매하고 Contoso에서 조립된 스피커를 구입합니다. 유럽에서 Fabrikam은 Contoso에 부품을 판매하지만 Contoso에서는 아무것도 사지 않습니다.
+ 파티는 직원과 고객 모두가 될 수 있습니다. 예를 들어 Contoso의 직원이 개인용으로 Contoso에서 전자 제품을 구입합니다.
+ 사람과 조직 사이에는 다대다(N:N) 관계가 있을 수 있습니다. 예를 들어 Fabrikam은 서비스 전문가를 제공하고 배치 조정자를 고용합니다. 배치 조정자는 여러 Fabrikam 고객의 작업 요청에 서비스 전문가를 연결합니다. Contoso는 Fabrikam의 고객 중 하나입니다. Contoso는 서비스 전문가가 필요한 경우 배치 조정자에게 연락하여 요청을 용이하게 합니다. 배치 조정자는 모든 고객에 대한 요청을 처리하기 때문에 N:N 관계가 관련됩니다.

다음 그림은 파티의 데이터 모델을 보여줍니다.

![파티에 대한 데이터 모델입니다.](media/party-gab-image1.png)

> [!TIP]
> 새 계정 레코드를 만들려고 할 때 **파티** 필드를 사용하여 이름으로 레코드를 검색하세요. 이런 식으로 레코드를 찾으면 선택하기만 하면 됩니다. 그러면 시스템이 당사자의 모든 데이터를 자동으로 채웁니다. 모든 필수 필드를 수동으로 설정할 필요는 없습니다. 이 동작은 기본 제공 **계정**, **연락처** 및 **공급업체** 페이지에서 찾을 수 있습니다.

이중 쓰기는 재무 및 운영 앱의 모든 당사자 역할을 지원하지 않습니다. 당사자 역할의 전체 목록은 [전체 주소록 개요](../../../fin-ops/organization-administration/overview-global-address-book.md)를 참조하세요.

### <a name="global-address-book"></a>전체 주소록

전체 주소록은 비즈니스에 참여하는 조직 및 개인의 우편 및 전자 주소 목록입니다.

전체 주소록은 필요한 만큼의 우편 주소와 전자 주소를 저장하고 처리합니다. 예를 들어 Fabrikam은 50개 위치에 주유소를 보유하고 있습니다. 각 위치에는 다른 우편 주소, 이메일 주소 및 전화 번호가 있습니다. 모든 비즈니스 구매는 주요 주유소로 청구되지만 구매를 요청한 특정 주유소로 직접 배송됩니다. 전체 주소록은 주 주유소를 Fabrikam의 청구 주소로 저장하고 각 주유소를 배송 주소로 저장합니다. 주소는 한 번 저장한 다음 견적 및 주문에 필요한 대로 검색할 수 있습니다.

비즈니스 컨텍스트에 따라 개인 또는 조직이 둘 이상의 역할을 수행할 수 있으며 모든 역할에 동일한 우편 주소 및 전자 주소가 사용될 수 있습니다. 이 경우 한 역할의 주소 변경이 다른 모든 역할에 나타나야 합니다. 전체 주소록은 주소를 전역적으로 저장하고 처리합니다.

다음 그림은 전체 주소록의 데이터 모델을 보여줍니다.

![전체 주소록에 대한 데이터 모델입니다.](media/party-gab-image2.png)

## <a name="contact"></a>연락처

Customer Engagement 앱에서 연락처는 사람입니다. 그러나 **연락처** 테이블이 사람, 포털 사용자, B2C(기업 대 소비자) 고객 또는 공급업체를 나타내기 위해 오버로드되었습니다. 표현은 암시적이며 관련 트랜잭션을 조사하지 않는 한 차이점을 알 수 없습니다. **연락처** 테이블은 **계정** 테이블과 일대일(1:1) 관계로 제한되었습니다. 당사자 및 전체 주소록 모델의 일부로 이중 쓰기는 분류를 위한 명시적 속성을 도입하고 개인과 조직인 연락처 간의 N:N 관계를 허용합니다(**계정** 또는 **공급업체** 엔터티).

두 가지 유형의 **연락처** 행이 있습니다.

+ **줄무늬 연락처** - **회사** 필드에 필수 값이 있는 **연락처** 행.
+ **줄무늬 없는 연락처** - **회사** 필드가 비어 있는 **연락처** 행.

**연락처** 테이블은 다음 유형의 행을 저장할 수 있습니다.

| 행 유형 | 설명 |
|----------|-------------|
| 고객인 사람(예: 판매 가능한 연락처 또는 B2C 고객) | **회사** 필드가 비어 있지 않고 **고객임** 필드가 **예** 로 설정된 스트라이프 연락처 레코드. |
| 공급업체인 사람(예: 공급업체와 같은 개인사업자) | **회사** 필드가 비어 있지 않고 **공급업체임** 필드가 **예** 로 설정된 스트라이프 연락처 레코드. |
| 고객과 공급업체 모두가 될 수 있는 사람 | **회사** 필드가 비어 있지 않고 **고객임** 필드가 **예** 로 설정되어 있으며 **공급업체임** 필드가 **예** 로 설정된 스트라이프 연락처 레코드. 사람은 한 제품의 생산자이자 다른 제품의 소비자가 될 수 있습니다. 재무 및 운영 앱과 이중 쓰기 모두 이 관계를 지원합니다. |
| 조직의 담당자이지만 고객이나 공급업체는 아닌 사람 | **회사** 필드가 비어 있고 **고객임** 필드가 **아니요** 로 설정되어 있으며 **공급업체임** 필드가 **아니요** 로 설정된 언스트라이프 연락처 레코드. |

## <a name="contact-for-party-table"></a>파티 테이블 문의

**파티 문의** 테이블은 **계정** 행과 **연락처** 행 사이의 N:N 관계를 저장하고 처리합니다. 스트라이프되지 않은 행에서 스트라이프 **연락처** 행을 필터링하고 스트라이프되지 않은 **연락처** 행을 **계정** 또는 **공급업체** 행과 연결할 수 있습니다.

예를 들어 Natasha Jones와 Miguel Reyes는 해당 지역의 농장을 돌보는 수의사입니다. 나타샤는 시애틀 지역을 담당하고 미구엘은 켄트 지역을 담당합니다. Customer Engagement 앱에서 농장은 고객으로 표시되고 수의사는 담당자로 표시됩니다. Natasha에 대한 단일 **연락처** 레코드는 Natasha가 작업하는 모든 농장과 연결되어 있습니다. 마찬가지로 Miguel에 대한 단일 **연락처** 레코드는 Miguel이 작업하는 모든 농장과 연결되어 있습니다.

이러한 관계는 **파티 문의** 테이블에 저장됩니다. 기본 제공 **계정**, **연락처** 및 **공급업체** 페이지에서 정보를 찾을 수 있습니다.

+ **계정** 페이지에서 **연결된 연락처** 탭을 사용하여 하나 이상의 연락처를 **계정** 열과 연결할 수 있습니다. 이러한 방식으로 조직의 담당자를 지정합니다. 그런 다음 한 연락처를 계정의 기본 연락처로 선택할 수 있습니다. **빠른 만들기** 페이지에서는 담당자만 선택할 수 있습니다. 동작은 **공급업체** 페이지를 사용 중일 때와 레코드 유형이 **조직** 인 경우 동일합니다.
+ **연락처** 페이지에서 행이 고객, 공급업체 또는 둘 다(스트라이프 연락처)인 경우 **연결된 연락처** 탭을 사용하여 하나 이상의 연락처를 연결할 수 있습니다. 이러한 방식으로 B2C 고객 또는 공급업체의 담당자를 지정합니다. 그런 다음 한 연락처를 기본 연락처로 선택할 수 있습니다. **빠른 만들기** 페이지에서는 담당자만 선택할 수 있습니다.
+ **연락처** 페이지에서 행이 연락처 사람(스트라이프되지 않은 연락처)인 경우 **연결된 조직** 탭을 사용하여 하나 이상의 고객 또는 공급업체를 연결할 수 있습니다. 이러한 방식으로 고객이나 공급업체를 기본 담당자에게 할당합니다. 고객 또는 공급업체는 조직, 개인 또는 둘 다일 수 있습니다. 한 번에 4개의 필드 중 하나만 값을 선택할 수 있습니다.

    + **파티 ID** 필드에서 값을 선택하면 기본 연락처는 선택한 당사자의 모든 역할에 할당됩니다.
    + **관련 연락처** 필드에서 에서 값을 선택하면 **사람** 유형의 스트라이프 연락처를 선택하게 됩니다.
    + **연결된 계정** 또는 **관련 공급업체** 필드에서 에서 값을 선택하면 조직을 선택하게 됩니다.

    ![연락처 페이지의 관련 조직 탭.](media/party-gab-image3.png)

    선택에 관계없이 연결은 당사자 수준에서 생성되고 당사자의 모든 역할에 적용되며 **파티 문의** 엔터티에 저장됩니다.

> [!NOTE]
> Customer Engagement 앱의 **파티 문의** 테이블에 있는 표시 이름은 **고객/공급업체 연락처** 입니다.

**고객임** 필드와 **공급업체임** 필드가 모두 **아니요** 로 설정된 **연락처** 행을 열면 **관련 조직** 탭이 표시됩니다. 이 탭을 사용하여 하나 이상의 고객 또는 공급업체 조직을 연락처와 연결합니다.

**고객임** 필드 또는 **공급업체임** 필드가 **예** 로 설정된 **연락처** 행을 열면 **관련 연락처** 탭이 표시됩니다. 이 탭을 사용하여 하나 이상의 연락처를 연결합니다.

## <a name="postal-addresses"></a>우편 주소

새 **주소** 탭이 **계정**, **연락처** 및 **공급업체** 페이지에 추가되었습니다. 이 탭은 다음 그림과 같이 그리드를 사용하여 여러 우편 주소를 지원합니다.

![우편 주소 그리드.](media/party-gab-image4.png)

그리드에는 다음 열이 포함됩니다.

+ **우편 주소 역할** – 우편 주소의 목적.
+ **기본** – 주소가 기본 주소인지 여부를 나타내는 값입니다.
+ **주소 번호** – 주소 순서.

그리드 위의 **새 주소** 버튼을 클릭하여 원하는 만큼의 우편 주소를 생성합니다.

**계정** 페이지의 **요약** 탭에 있는 **주소 1** 및 **주소 2** 필드는 각각 **배달** 및 **송장** 주소에 해당합니다.

![우편 주소에 대한 요약 탭.](media/party-gab-image5.png)

**연락처** 페이지의 **요약** 탭에 있는 **주소 1**, **주소 2** 및 **주소 3** 필드는 각각 **비즈니스**, **배달** 및 **송장** 주소에 해당합니다.

## <a name="electronic-addresses"></a>전자 주소

새 **전자 주소** 탭이 **계정**, **연락처** 및 **공급업체** 페이지에 추가되었습니다. 이 탭은 다음 그림과 같이 그리드를 사용하여 여러 전자 주소를 지원합니다.

![전자 주소 그리드.](media/party-gab-image6.png)

그리드에는 다음 열이 포함됩니다.

+ **유형** - 전자 주소 유형.
+ **기본** 주소가 기본 주소인지 여부를 나타내는 값입니다.
+ **목적** – 전자 주소의 목적.

그리드 위의 **새 전자 주소** 버튼을 클릭하여 원하는 만큼의 주소를 생성합니다.

전자 주소는 이 그리드에서만 사용할 수 있습니다. 향후 릴리스에서는 모든 우편 주소 및 전자 주소 필드가 다른 탭에서 제거됩니다(예: **요약** 및 **세부** 탭). **세부 정보** 탭에 표시되는 연락처 세부 정보는 기본 전화, 기본 이메일, 기본 전화, 기본 팩스 및 기본 Twitter ID와 같은 기본 전자 주소의 읽기 전용 복사본입니다. 리드 자격 프로세스 중에 회사 전화 번호와 휴대 전화 번호를 모두 제공할 수 있습니다. **IsMobile=No** 및 **IsMobile=Yes** 인 경우 휴대폰 번호가 보조 전화로 고려되면 회사 전화번호가 기본 전화로 간주됩니다.

> [!TIP]
> **계정** 및 **연락처** 양식의 **주소** 및 **전자 주소** 탭을 사용하여 우편 및 전자 주소를 관리합니다. 이렇게 하면 주소 데이터가 재무 및 운영 앱과 동기화됩니다.

## <a name="setup"></a>설정

1. Customer Engagement 앱 환경을 엽니다.

2. [이중 쓰기 애플리케이션 오케스트레이션 솔루션](https://aka.ms/dual-write-app)의 최신 버전(2.2.2.60 이상)을 설치합니다.

3. [이중 쓰기 파티 및 전체 주소록 솔루션](https://aka.ms/dual-write-gab)을 설치합니다.

4. 금융 및 운영 앱을 엽니다. 데이터 관리 모듈로 이동하여 이중 쓰기 탭을 선택합니다. 이중 쓰기 관리 페이지가 열립니다.

5. [솔루션 적용](link-your-environment.md) 함수를 사용하여 2단계와 3단계에서 설치된 두 솔루션을 모두 적용합니다.

6. 다음 지도는 더 이상 필요하지 않으므로 중지하세요. 대신 `Contacts V2 (msdyn_contactforparties)` 지도를 실행합니다.

    + CDS 연락처 V2 및 연락처(고객 연락처 참조)
    + CDS 연락처 V2 및 연락처(공급업체 연락처 참조)

7. 파티 기능을 위해 다음 엔티티 매핑이 업데이트되었으므로 이러한 매핑에 최신 버전을 적용해야 합니다.

    지도 | 이 버전으로 업데이트 | 변경 사항
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.5 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Customers V3 (accounts)` | 1.0.0.5 |`PartyNumber` 및 이름, 개인 정보, 우편 주소 필드 및 전자 연락처 주소와 같은 기타 당사자 관련 필드가 삭제되었습니다.
    `Customer V3 (contacts)` | 1.0.0.5 | `PartyNumber` 및 이름, 개인 정보, 우편 주소 필드 및 전자 연락처 주소와 같은 기타 당사자 관련 필드가 삭제되었습니다.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | `PartyNumber` 및 이름, 개인 정보, 우편 주소 필드 및 전자 연락처 주소와 같은 기타 당사자 관련 필드가 삭제되었습니다.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | 담당자를 `ContactforParty` 참조로 교체했습니다.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | 담당자를 `ContactforParty` 참조로 교체했습니다.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | 담당자를 `ContactforParty` 참조로 교체했습니다.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.1 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Complimentary Closings ( msdyn_compliemntaryclosings)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | 이것은 이번 릴리스의 일부로 추가된 새로운 맵입니다.

8. 위의 맵을 실행하기 전에 다음 단계에 설명된 대로 통합 키를 수동으로 업데이트해야 합니다. 그런 다음 **저장** 을 선택합니다.

    | 지도 | 키 |
    |-----|------|
    | 거래처 |  accountnumber [계정 번호]<br>msdyn_company.cdm_companycode [회사(회사 코드)] |
    | 연락처 | msdyn_contactpersonid [계정 번호/연락처 개인 ID]<br>msdyn_company.cdm_companycode [회사(회사 코드)] |
    | 고객/공급업체 연락처 | msdyn_contactforpartynumber [파티 번호 문의]<br>msdyn_associatedcompanyid.cdm_companycode [관련 회사(회사 코드)] |
    | 공급 업체 | msdyn_vendoraccountnumber [공급업체 계정 번호]<br>msdyn_company.cdm_companycode [회사(회사 코드)]|

9. Dataverse에서 중복 탐지 규칙의 글자 수 제한이 450자에서 700자로 증가했습니다. 이 제한을 통해 중복 탐지 규칙에 하나 이상의 키를 추가할 수 있습니다. 다음 필드를 설정하여 **계정** 테이블에 대한 중복 탐지 규칙을 확장합니다.

    | 필드 | 값 |
    |-------|-------|
    | 이름 | 동일한 계정 이름을 가진 계정. |
    | 설명 | 계정 이름 속성에 동일한 값이 있는 계정 레코드를 감지합니다. |
    | 기준 레코드 종류 | 거래처 |
    | 일치하는 레코드 종류 | 거래처 |
    | 어카운트 이름(필드) | 정확히 일치 |
    | 회사(필드) | 정확히 일치 |
    | 관계 유형(필드) | 정확히 일치 |
    | 파티 ID(필드) | 정확히 일치 |
    | 선택(필드) | (비어 있음) |

    ![계정에 대한 중복 규칙입니다.](media/duplicate-rule-1.PNG)

10. 다음 필드를 설정하여 **연락처** 테이블에 대한 중복 탐지 규칙을 확장합니다.

    | 필드 | 값 |
    |-------|-------|
    | 이름 | 이름과 성이 같은 연락처. |
    | 설명 | 이름 및 성 필드에 동일한 값이 있는 연락처 레코드를 감지합니다. |
    | 기준 레코드 종류 | 연락처 |
    | 일치하는 레코드 종류 | 연락처 |
    | 이름(필드) | 정확히 일치 |
    | 성(필드) | 정확히 일치 |
    | 회사(필드) | 정확히 일치 |
    | 파티 ID(필드) | 정확히 일치 |
    | 선택(필드) | (비어 있음) |

    ![연락처에 대한 중복 규칙입니다.](media/duplicate-rule-2.PNG)

11. 기존 이중 쓰기 사용자인 경우 [파티 및 전체 주소록 모델로 업그레이드](upgrade-party-gab.md)의 안내를 따르고 데이터를 업그레이드하세요. **이 단계를 완료하지 않고 12단계로 진행하지 마세요.** 새로운 이중 쓰기 사용자인 경우 12단계로 진행합니다.

12. 기존 이중 쓰기 사용자인 경우 11단계를 완료하면 다음 순서로 맵을 실행할 수 있습니다. 신규 이중 쓰기 고객인 경우 직접 진행할 수 있습니다. "프로젝트 유효성 검사에 실패했습니다. 누락된 목적지 필드..." 오류 메시지가 나타나면 지도를 열고 **테이블 새로 고침** 을 선택한 다음 지도를 실행합니다.

    금융 및 운영 앱 | Customer Engagement 앱  
    ----------------------------|------------------------
    [CDS 당사자](mapping-reference.md#220) | msdyn_parties
    [CDS 우편 주소 위치](mapping-reference.md#234) | msdyn_postaladdresscollections
    [CDS 우편 주소 기록 V2](mapping-reference.md#235) | msdyn_postaladdresses
    [CDS 파티 우편 주소 위치](mapping-reference.md#233) | msdyn_partypostaladdresses
    [파티 연락처 V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [고객 V3](mapping-reference.md#101) | 계정
    [고객 V3](mapping-reference.md#116) | 연락처
    [공급업체 V2](mapping-reference.md#202) | msdyn_vendors
    [담당자 직함](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [결구](mapping-reference.md#222) | msdyn_complimentaryclosings
    [인사말](mapping-reference.md#228) | msdyn_salutations
    [의사결정 역할](mapping-reference.md#224) | msdyn_decisionmakingroles
    [고용 직무 기능](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [충성도 수준](mapping-reference.md#226) | msdyn_loyaltylevels
    [개인 문자 유형](mapping-reference.md#227) | msdyn_personalcharactertypes
    [연락처 V2](mapping-reference.md#221) | msdyn_contactforparties
    [CDS 판매 견적 헤더](mapping-reference.md#215) | 견적
    [CDS 판매 주문 헤더](mapping-reference.md#217) | salesorders
    [판매 송장 헤더 V2](mapping-reference.md#118) | 송장

> [!NOTE]
> `CDS Contacts V2 (contacts)` 맵은 1단계에서 멈춘 지도입니다. 다른 맵을 실행하려고 하면 이 2개의 맵이 종속 목록에 나타날 수 있습니다. 이 지도를 실행하지 마세요.
>
> 파티 및 전체 주소록 솔루션이 설치된 경우 이름이 `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`인 연결을 비활성화해야 합니다. 파티 및 전체 주소록 솔루션을 제거하는 경우 플러그인을 다시 활성화해야 합니다.
>
> **계정**, **연락처** 및 **공급업체** 테이블에 포함된 `msdyn_*partynumber`필드(한 줄 텍스트 필드)는 앞으로 테이블을 사용하면 안 됩니다. 레이블 이름에는 명확성을 위해 **(지원 중단됨)** 접두사가 있습니다. 대신 **msdyn_partyid** 필드를 사용하세요. 필드는 **msdyn_party** 테이블에 대한 조회입니다.

> 테이블 이름 | 이전 필드 | 새 필드
> --------|-------|--------
> 거래처 | `msdyn_partynumber` | `msdyn_partyid`
> 연락처 | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>템플릿

테이블 맵 컬렉션은 다음 표와 같이 파티 및 전체 주소록 상호 작용에 함께 작동합니다.

| 금융 및 운영 앱 | Customer Engagement 앱 | 설명 |
|----------------------------|-------------------------|-------------|
| [담당자 직함](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [고객 V3](mapping-reference.md#101) | 계정 |
| [고객 V3](mapping-reference.md#116) | 연락처 |
| [CDS 당사자](mapping-reference.md#220) | msdyn\_parties |
| [CDS 파티 우편 주소 위치](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [CDS 우편 주소 기록 V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [CDS 우편 주소 위치](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [CDS 판매 견적 헤더](mapping-reference.md#215) | 견적 |
| [CDS 판매 주문 헤더](mapping-reference.md#217) | salesorders |
| [결구](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [연락처 V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [의사결정 역할](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [고용 직무 기능](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [충성도 수준](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [파티 연락처 V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [개인 문자 유형](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [판매 송장 헤더 V2](mapping-reference.md#118) | 송장 |
| [인사말](mapping-reference.md#228) | msdyn\_salutations |
| [공급업체 V2](mapping-reference.md#202) | msdyn\_vendors |

자세한 내용은 [이중 쓰기 매핑 참조](mapping-reference.md)를 참조하세요.

## <a name="known-issues-and-limitations"></a>알려진 문제 및 제한 사항

+ 금융 및 운영 앱에서 주소와 함께 고객을 생성하고 저장할 때 주소가 **주소** 테이블에 동기화되지 않을 수 있습니다. 이는 이중 쓰기 플랫폼 시퀀싱 문제 때문입니다. 해결 방법으로 먼저 고객을 생성하고 저장합니다. 그런 다음 주소를 추가합니다.
+ 재무 및 운영 앱에서 고객 레코드에 기본 주소가 있고 해당 고객에 대한 새 연락처를 생성하면 연락처 레코드는 연결된 고객 레코드의 기본 주소를 상속합니다. 이는 공급업체 연락처에서도 발생합니다. Dataverse는 현재 이 동작을 지원하지 않습니다. 이중 쓰기가 활성화된 경우 재무 및 운영 앱에서 기본 주소로 상속된 고객 연락처가 주소와 함께 Dataverse에 동기화됩니다.
+ **계정**, **연락처** 및 **공급업체** 양식의 전자주소 탭에서 설정한 전자주소는 `msdyn_partyelectronicaddress` 테이블에서 가져옵니다. 이 정보는 판매 주문, 견적 및 구매 주문과 같은 관련 거래로 흐르지 않습니다. 증분 릴리스에서 이 문제를 수정할 계획입니다. 계정 및 연락처 레코드의 전자 주소 필드에 있는 기존 데이터는 판매 주문, 견적 및 구매 주문과 같은 거래에서 계속 작동합니다.
+ 재무 및 운영 앱에서 **연락처 추가** 양식으로 연락처 레코드를 생성할 수 있습니다. **연락처 보기** 양식에서 새 연락처를 만들려고 할 때 작업이 실패합니다. 이것은 알려진 문제입니다.

    ![연락처 추가의 알려진 문제입니다.](media/party-gab-contact-issue.png)

+ **초기 동기화** 는 **ContactForParty** 에서 **사용 가능 시작** 및 **사용 가능 끝** 시간 필드를 지원하지 않습니다. DIXF는 값을 정수 대신 문자열로 변환하기 때문입니다. 변환으로 인해 다음 오류가 발생합니다. `Cannot convert the literal '<say 08:00:00>’ to the expected type edm.int32`.
+ 우편 주소가 비즈니스 통신 주소 및 청구서 수신 주소와 같이 두 가지 이상의 이유로 사용되는 경우 다음 이미지와 같이 `Business;Invoice`로 표시되어야 합니다. 값 사이에 공백을 추가하면 오류가 발생합니다.

    ![주소의 알려진 문제입니다.](media/party-gab-address-issue.png)

+ 이중 쓰기 기능이 있는 재무 및 운영 앱을 사용하여 앞 날짜의 우편 주소를 입력할 수 없습니다. Dataverse가 날짜 유효성을 지원하지 않기 때문입니다. 재무 및 운영 앱을 사용하여 미래 날짜의 우편 주소를 입력하면 Dataverse에 완전히 동기화되고 사용자 인터페이스에 즉시 주소가 표시됩니다. 이 레코드를 업데이트하면 재무 및 운영 앱에서 현재 날짜가 아닌 미래 날짜이므로 오류가 발생합니다.
