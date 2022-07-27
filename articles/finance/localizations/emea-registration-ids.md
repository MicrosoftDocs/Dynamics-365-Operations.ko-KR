---
title: 등록 ID
description: 이 항목에서는 등록 ID 설정 및 사용에 대한 정보를 제공합니다.
author: ShylaThompson
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 544e994a18811995afc64c052a3f97e622529162b8a14b17206c370026b78ac4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450889"
---
# <a name="registration-ids"></a>등록 ID

[!include [banner](../includes/banner.md)]

이 항목에서는 등록 ID 설정 및 사용에 대한 정보를 제공합니다.

많은 국가와 지역에는 등록 번호 또는 ID 기록에 대한 규정과 요구 사항이 다릅니다. 이 항목에서는 여러 유럽 국가/지역의 당사자에 대해 지원되는 등록 유형의 필수 설정 및 처리에 대한 개요를 제공합니다. 모든 국가/지역에는 다른 주 사무소에서 제공하는 등록 번호와 관련된 다양한 국가별 기능을 지원하기 위한 요구 사항이 있습니다. 등록 번호의 예로는 사회 보장 번호(SSN), 세금 식별 번호(TIN) 및 유럽 VAT 식별(EU VAT ID)이 있습니다. 이 기능은 일부 유럽 국가의 국가별 요구 사항을 고려하여 모든 지역의 모든 국가에 대한 통합 프레임워크를 제공합니다. 다음 섹션에서는 등록 ID를 설정하고 처리하는 데 사용되는 전체 정보 흐름에 대해 설명합니다.

## <a name="registration-type-creation"></a>등록 유형 생성
등록 ID를 입력하기 전에 각 당사자가 적용되는 다양한 유형의 등록 번호에 대한 등록 유형을 설정해야 합니다. **조직 관리** &gt; **글로벌 주소록** &gt; **등록 유형** &gt; **등록 유형** 페이지로 이동하여 여러 국가/지역의 공급업체, 고객, 근로자 및 법인에 대한 등록 유형을 생성하고 관리합니다.

|필드                 |설명      |
|------------------------------|----------------------------|                                                                           
| 이름                | 등록 유형의 이름입니다. |                                                                           
| 설명         | 등록 유형에 대한 설명입니다. |
| 국가/지역      | 국가/지역의 고유 식별자입니다.|
| 세무 당국       | 등록 유형과 연결된 세무 기관입니다.|
| 다음으로 제한됨       | 사업자 등록 유형에 적용되는 제한 유형: 없음, 개인, 조직.|
| 포맷              | 등록 유형에 대한 유효성 검사 형식입니다.|
| 업데이트 가능      | 등록 유형에 대한 등록 번호를 입력한 후 업데이트할 수 있는지 여부를 정의합니다.|
| 고유              | 등록 유형에 대한 등록 번호가 고유한지 여부를 정의합니다. |
| 국가 기본 | 당사자가 특정 국가의 하나 이상의 주소와 연결되어 있고 등록 ID가 이러한 모든 주소에 유효한 경우 하나의 주소를 해당 국가의 기본 주소로 지정해야 합니다. 하나의 ID만 기본으로 등록할 수 있습니다. 국가 주소의 기본에 대해서만 등록 번호를 입력할 수 있는지 여부를 정의합니다. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>등록 범주에 등록 유형 할당
등록 범주는 특정 국가/지역에서 세금, 관세 및 기타 목적으로 사용하도록 승인된 국가/지역 등록 식별자입니다. 이 카테고리는 특정 등록 ID(체크 디지트 등 포함) 및 다른 보고서에 포함 등록 ID의 유효성 검사 규칙을 정의합니다. **조직관리** &gt; **글로벌 주소록** &gt; **등록 유형** &gt; **등록 카테고리** 페이지를 사용하여 특정 국가의 등록 유형을 지원되는 등록 카테고리에 할당합니다.

| 필드            | 설명|
|-----------------------|----------------|
| 등록 유형     | 특정 국가/지역의 등록 유형입니다.|
| 다음으로 제한됨         | 사업자 등록 유형에 적용되는 제한 유형: 없음, 개인, 조직.|
| 등록 카테고리 | 해당 국가에서 사용하도록 승인된 고유 등록 식별자입니다. 지원되는 범주의 전체 목록은 이 항목의 뒷부분에 나와 있습니다. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>전체 주소록 기록에 대한 등록 ID 입력

GAB(전체 주소록)에는 고객, 공급업체, 연락처, 비즈니스 관계 및 법인에 대한 통합 주소 정보가 포함되어 있습니다. 자세한 내용은 [글로벌 주소록 개요](../../fin-ops-core/fin-ops/organization-administration/overview-global-address-book.md)를 참조하십시오. 전체 주소록에 저장된 당사자 레코드는 하나 이상의 주소 레코드를 포함할 수 있습니다. 이러한 주소는 청구 또는 배송과 같은 다양한 목적으로 사용됩니다. 고객, 공급업체, 근로자 및 법인의 주소 정보에 대한 등록 ID를 설정할 수 있습니다. 레지스터 ID를 입력하려는 파티(법인, 벤더, 고객, 작업자) 레코드를 찾은 다음 파티, 법인, 벤더, 고객, 작업자 관련 양식에서 **등록 ID** 를 클릭하여 **주소 관리** 페이지를 엽니다. **세금 등록** 탭에서 **추가** 를 클릭하고 등록 ID에 대한 다음 정보를 입력합니다.


|필드                |설명                                                |
|---------------------|-----------------------------------------------------------|
| 등록 유형   | 선택한 국가/지역의 등록 유형입니다.     |
| 등록 번호 | 당사자 등록 ID입니다.                                |
| 설명         | 등록 번호에 대한 설명입니다.               |
| 섹션             | 등록 번호에 대한 추가 정보입니다. |
| 발급 기관      | 등록 번호를 발급한 기관입니다.        |
| 발행일         | 등록 번호의 발급 날짜입니다.              |
| 유효           | 등록 번호의 유효 날짜입니다.           |
| 만료          | 등록 번호의 만료 날짜입니다.          |

> [!NOTE]
> 법인, 판매자, 고객의 면세 번호는 VAT ID와 관련된 등록 ID에서 선택하고 당사자에 대해 입력할 수 있습니다.

## <a name="search-for-records-by-registration-id"></a>등록 ID로 레코드 검색
등록 ID를 기반으로 한 파티 레코드 검색은 당사자, 법인, 공급업체, 고객 및 작업자와 관련된 양식에서 사용할 수 있습니다. **등록 ID 검색** 을 클릭하여 **등록 ID 검색 기준** 페이지를 엽니다. 검색 조건을 지정하고 **찾기** 를 클릭합니다. 시스템은 글로벌 주소록에서 선택한 레코드 및 관련 파티 레코드 유형을 표시합니다

## <a name="supported-registration-categories"></a>지원되는 등록 카테고리
다음 표에는 지원되는 등록 유형이 나열되어 있습니다. 등록 ID에 대한 Microsoft Dynamics AX 2012 필드에 대해 잘 알고 있는 경우 이 표에서는 이러한 필드를 Dynamics 365 Finance 등록 범주에도 매핑합니다.

| Finance 등록 카테고리         |국가/지역  | Dynamics AX 2012 조건/필드|
|---------------------------------------------------------------|---------------------|---------------------------------|
| VAT ID                                                        | 유럽 연합(EU)의 모든 국가|  면세 번호(AX 2012 R3의 입법 유형 세금 ID)|
| 기업 ID(COID)                                          | 벨기에 체코 에스토니아 헝가리 라트비아 리투아니아 폴란드 스위스 | 기업 번호(EnterpriseNumber) 등록 번호(RegNum\_W) 등록 번호(RegNum\_W) 등록 번호(RegNum\_ W) 등록 번호(RegNum\_W) 기업 코드(EnterpriseCode) 등록 번호(RegNum\_W) UID(AX 2012 R3의 입법 유형 UID) |
| 지점 ID                                                     | 벨기에            | 지점 번호(BranchNumber)|
| Spisová značka(등록 번호, 발급 기관, 섹션) | 체코     | 삽입 번호(CommercialRegisterInsetNumber) 상업 등록 보관(CommercialRegister) 상업 등록 섹션(CommercialRegisterSection)|
| 데모 고객 ID                                           | 핀란드 | 세관 고객 번호(CustomsCustomerNumber\_FI)|
| INN                                                           | 러시아 연방| INN(AX 2012 R3의 입법 유형 INN)|
| RRC                                                           | 러시아 연방| RRC(AX 2012 R3의 입법 유형 RRC)|
| OKDP                                                          | 러시아 연방| OKDP(AX 2012 R3의 입법 유형 OKDP)|
| OKPO                                                          | 러시아 연방| OKPO(AX 2012 R3의 입법 유형 OKPO)|
| RCOAD                                                         | 러시아 연방| RCOAD(AX 2012 R3의 입법 유형 RCOAD)|
| OGRN                                                          | 러시아 연방| OGRN(AX 2012 R3의 입법 유형 OGRN) |
| SNILS                                                         | 러시아 연방| SNILS(AX 2012 R3의 입법 유형 SNILS)|
| CIFTS                                                         | 러시아 연방| CIFTS(AX 2012 R3의 입법 유형 CIFTS)|
| 여권                                                      | 스페인             | 여권|
| 공식 신분증                              | 스페인             | 공식 신분증|
| 거주 증명서                                         | 스페인             | 거주 증명서|
| 기타 신분증                                 | 스페인             | 기타 신분증|
| 인구조사 안 됨                                                  | 스페인             | AX 2012 R3에서 사용할 수 없음|


필수 전제 조건을 포함하여 등록 ID 처리에 대한 자세한 내용은 LCS(Lifecycle Services)의 VAT ID에 대한 다음 작업 기록을 참조하십시오.

-   VAT ID 설정
-   공급업체 VAT ID 등록
-   VAT ID를 사용한 당사자 검색






[!INCLUDE[footer-include](../../includes/footer-banner.md)]