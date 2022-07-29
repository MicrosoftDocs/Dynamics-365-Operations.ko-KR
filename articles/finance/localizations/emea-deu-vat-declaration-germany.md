---
title: VAT 신고(독일)
description: 이 항목에서는 독일의 VAT(사전 부가가치세) 선언을 공식 XML 형식으로 설정하고 생성하는 방법에 대해 설명합니다.
author: anasyash
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: a761a145a876584728098a92b3f3e93ac718a164
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8451756"
---
# <a name="vat-declaration-germany"></a>VAT 신고(독일)

[!include [banner](../includes/banner.md)]

이 항목에서는 독일의 VAT(사전 부가가치세) 선언을 공식 XML 형식으로 설정하고 생성하는 방법에 대해 설명합니다. 이 항목에서는 Microsoft Excel에서 VAT 신고를 미리 보는 방법도 설명합니다.

보고서를 자동으로 생성하려면 사전 VAT 신고의 각 상자에 대해 별도의 VAT 회계를 유지하기에 충분한 판매세 코드를 생성하십시오. 또한 사전 VAT 신고에 대한 전자 보고(ER) 형식의 애플리케이션별 매개변수에서 VAT 신고의 상자에 대한 조회 결과와 판매세 코드를 연결합니다.

독일의 경우 **보고서 필드 조회** 를 구성해야 합니다. 애플리케이션별 매개 변수를 설정하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [VAT 선언 필드에 대한 애플리케이션별 매개 변수 설정](#set-up-application-specific-parameters-for-vat-declaration-fields) 섹션을 참조하십시오.

다음 표에서 "조회 결과" 열은 VAT 신고 형식의 특정 VAT 신고 행에 대해 미리 구성된 조회 결과를 보여줍니다. 이 정보를 사용하여 판매세 코드를 조회 결과와 올바르게 연결한 다음 VAT 신고 행과 연결하십시오.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>VAT 신고 개요

독일 사전 VAT 신고에는 다음 정보가 포함되어 있습니다.

**섹션 – 배송 및 기타 서비스**

**과세 대상 판매**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                                                                                                                      | 조회 결과                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | 코드 제외     | 19%의 세율로 과세 대상 판매.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard(81/50) – 빼기 기호 포함             |
| 21  | 86             | 코드 제외     | 7%의 세율로 과세 대상 판매.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced(86/50) – 빼기 기호 포함               |
| 22  | 35             | 36               | 다른 세율로 과세 대상 판매.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates(35/36/50) – 빼기 기호 포함      |
| 23  | 77             | *세액 없음*  | 독일 VAT법(UStG) §24에 따라 농업 및 임업 사업체에서 VAT ID 번호가 있는 고객에게 배송됩니다. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24(77/50) – 빼기 기호 포함 |
| 24  | 76             | 80               | UStG의 §24에 따라 세금을 지불해야 하는 판매(제재 제품, 음료 및 알코올성 액체).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24(76/80/50)                    |

**매입세액공제가 있는 면세 판매**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                                                       | 조회 결과                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *세액 없음*  | VAT ID가 있는 고객에게 커뮤니티 내 배송.                       | 26-EUSales                          |
| 27  | 44             | *세액 없음*  | VAT ID가 없는 구매자에게 새 차량을 지역 사회 내로 배송합니다.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *세액 없음*  | 회사 외부에서 새 차량의 지역 사회 내 배송.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *세액 없음*  | 수출 배송과 같이 매입세 공제가 있는 기타 면세 판매. | 29-ExportOtherTaxFreeSales          |

**매입세액공제가 없는 면세 판매**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                            | 조회 결과                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *세액 없음*  | 매입세액공제가 없는 면세판매. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**커뮤니티 내 인수**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                                                                                                   | 조회 결과                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *세액 없음*  | 일부 개체 및 투자 금에 대한 면세 커뮤니티 내 취득.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | 코드 제외     | 19%의 세율로 과세 대상 지역사회 내 취득.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | 코드 제외     | 7%의 세율로 과세 대상 지역사회 내 취득.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced(93/61)          |
| 36  | 95             | 98               | 기타 세율에 따라 지역 내 취득세를 과세.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates(95/98/61) |
| 37  | 94             | 96               | VAT ID 번호가 없는 공급업체로부터 일반 세율로 과세 대상 지역사회 내에서 새 차량을 취득합니다. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles(94/96/61)     |

**섹션 – 세금 채무자로서의 수혜자**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                                                        | 조회 결과                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | 나머지 커뮤니티 영역을 기반으로 하는 기업가의 기타 서비스.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor(46/47/66)                                                                              |
| 41  | 73             | 74               | UStG의 섹션 13b(2) 3에 해당하는 판매                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer(73/74/67) |
| 42  | 84             | 85               | UStG의 섹션 13b(2) 1, 2, 4~12에 해당하는 판매 | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther(84/85/67)                           |

**섹션 – 판매에 대한 추가 정보**

| 행 | 박스 - 과세 표준  | 박스 - 세액 | 설명                                                                                                | 조회 결과                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *세액 없음*  | 커뮤니티 내 삼각 거래의 경우 첫 번째 고객에 의해 배송됩니다.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *세액 없음*  | 서비스 수혜자가 그에 따라 세금을 내야 하는 수행 기업가의 과세 대상 판매. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *세액 없음*  | 기타 비과세 서비스.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *세액 없음*  | 성과 장소가 독일이 아닌 경우 기타 비과세 판매.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *세액 없음* | *세액 없음*  | VAT.                                                                                                       | 행 20 + 행 21 + 행 22 + 행 24 + 행 34 + 행 35 + 행 36 + 행 37 + 행 40 + 행 41 + 행 42 |

**섹션 – 공제 가능한 입력세**

| 행 | 박스 - 세액 | 설명                                                                                                | 조회 결과                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | 다른 회사, 서비스 및 커뮤니티 내 삼각 거래의 송장 세금 금액을 입력합니다.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – 빼기 기호 포함                                                                   |
| 56  | 61               | 지역사회 내 상품 취득으로 인한 매입세액.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced(93/61)</br>36-UseTaxEUPurchaseOtherRates(95/98/61)</br>37-UseTaxEUPurchaseVehicles(94/96/61) |
| 57  | 62               | 발생한 수입 판매세.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | UStG §13b의 의미 내에서 서비스의 매입세액.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer(73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther(84/85/67)                                                 |
| 59  | 63               | 일반 평균 세율에 따라 계산된 매입세액입니다.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – 빼기 기호 포함                                                                                    |
| 60  | 59               | 회사 및 소규모 사업체 외부에서 신차를 지역사회 내로 인도하는 경우 매입세 공제. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – 빼기 기호 포함                                                                  |
| 61  | 64               | 매입세액공제 수정.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | 남은 금액                                                                                      | 행 52 – 행 55 – 행 56 – 행 57 – 행 58 – 행 50 – 행 60 – 행 61                                                                                                        |

**섹션 – 기타 세액**

| 행 | 박스 - 세액 | 설명                                                                                                                                                                                                                                                         | 조회 결과                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | 과세형태 변경으로 인한 세금 및 세율 변경으로 인한 계약금에 대한 가산세.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | 송장에 표시된 부정확하거나 부당한 세액, UStG의 6a(4)문 2절, 17(1)문 7 또는 25b(2)문에 따라 납부해야 하거나 다음에 의해 납부해야 하는 세액 아웃소싱 회사 또는 창고지기. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | 영구연장을 위한 고정 특별 선지급금 공제 이 행은 일반적으로 과세 기간의 마지막 사전 통지로만 채워집니다.                                                                                                  | 보고서 대화 상자의 사용자 입력 매개변수 |
| 68  | 83               | 나머지 선지급 판매세 및 나머지 초과액. 금액 앞에 빼기 기호 포함.                                                                                                                                                          | 62행 + 64행 – 65행 – 66행             |

**섹션 – 공제에 대한 추가 정보**

| 행 | 박스 - 과세 표준 | 박스 - 세액 | 설명                                                            | 조회 결과                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | 20~24행에 대한 과세 기준 감소.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24(76/80/50) |
| 74  | \-             | 37               | 55, 59 및 60행의 공제 가능한 매입세액 감소 | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>역 청구 구매 VAT

사용세를 사용하여 들어오는 역청구 VAT를 게시하도록 판매세 코드를 구성하는 경우 이름에 "사용세"가 포함된 보고서 **필드 조회 결과** 와 판매세 코드를 연결하십시오.

또는 두 개의 별도 판매세 코드를 구성할 수 있습니다. 하나는 VAT 납부용이고 다른 하나는 VAT 공제용입니다. 그런 다음 각 코드를 **보고서 필드 조회** 의 해당 조회 결과와 연결하십시오.

예를 들어, 과세 대상 커뮤니티 내 취득의 경우 사용세와 함께 판매세 코드 **UT_S_EU** 를 구성하고 이를  **보고서 필드 조회** 에 대한 **34-UseTaxEUPurchaseStandard** 에 연결합니다. 이 경우 사용하는 금액은 **UT_S_EU** 판매세 코드는 상자 089 및 061(34 및 56행)에 반영됩니다.

또는 다음과 같은 두 가지 판매세 코드를 구성할 수 있습니다.

  - **VAT_S_EU**, 세율 값이 -19%입니다.
  - **InVAT_S_EU**, 세율 값이 -19%입니다.

그런 다음 다음과 같은 방법으로 코드를 **보고서 필드 조회** 의 조회 결과와 연결합니다.

  - **VAT_S_EU** 를 **34-EUPurchaseStandard** 조회 결과에 연결합니다.
  - **InVAT_S_EU** 를 **56-InputTaxEUPurchase** 조회 결과와 연결합니다.

이 경우 **VAT_S_EU** 판매세 코드를 사용한 금액은 상자 089(34행)에 반영됩니다. **InVAT_S_EU** 판매세 코드를 사용하는 금액은 상자 061(56행)에 반영됩니다.

역청구 VAT를 구성하는 방법에 대한 자세한 내용은 [역청구](emea-reverse-charge.md)를 참조하십시오.

## <a name="configure-system-parameters"></a>시스템 매개 변수 구성

VAT 신고를 생성하려면 조직의 세금 번호(Steuernummer)를 구성해야 합니다.

1. **조직 관리**  >  **조직**  >  **법인** 으로 이동합니다.
2. 법인을 선택한 후 **등록 ID** 를 선택합니다.
3. 독일에서 주소를 선택하거나 만든 다음 **등록 ID** 빠른 탭에서 **추가** 를 선택합니다.
4. **등록 유형** 필드에서 독일 전용으로 **Enterprise Id(COID)** 등록 범주를 사용하는 등록 유형을 선택합니다.
5. **등록 번호** 필드에 세금 번호를 입력합니다.
6. **일반** 탭의 **유효** 필드에 번호가 유효한 날짜를 입력합니다.

등록 카테고리 및 등록 유형을 설정하는 방법에 대한 자세한 내용은 [등록 ID](emea-registration-ids.md)를 참조하십시오.

## <a name="set-up-a-vat-declaration-for-germany"></a>독일에 대한 VAT 신고 설정

### <a name="import-er-configurations"></a>ER 구성 가져오기

**전자 보고** 작업 공간을 열고 이러한 ER 형식의 다음 버전 이상을 가져옵니다.

   - VAT Declaration Excel (DE).version.101.16.12.xml
   - VAT Declaration XML (DE).version.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>VAT 신고 필드에 대한 애플리케이션별 매개변수 설정

VAT 신고를 자동으로 생성하려면 애플리케이션에서 판매세 코드를 연결하고 ER 구성에서 조회 결과를 찾습니다.

> [!NOTE]
> **기능 관리** 작업 공간에서 **이전 버전의 ER 형식에서 애플리케이션별 매개 변수 사용** 기능을 실행하는 것이 좋습니다. 이 기능이 활성화되면 ER 형식의 이전 버전에 대해 구성된 매개변수가 동일한 형식의 이후 버전에 자동으로 적용됩니다. 이 기능이 활성화되지 않은 경우 각 형식 버전에 대해 애플리케이션별 매개변수를 명시적으로 구성해야 합니다. **이전 버전의 ER 형식에서 애플리케이션별 매개 변수 사용** 기능은 Finance 버전 10.0.23부터 시작되는 **기능 관리** 작업 공간에서 사용할 수 있습니다. 각 법인에 대한 ER 형식의 매개 변수를 설정하는 방법에 대한 자세한 내용은 [법인당 ER 형식의 매개 변수 설정](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md)을 참조하십시오.

다음 단계에 따라 VAT 신고에서 어떤 상자를 생성하는 판매세 코드를 정의하십시오.

1. **작업 영역**  >  **전자 보고** 로 이동하여 **보고 구성** 을 선택합니다.
2. **VAT 선언 XML(DE)** 구성을 선택한 다음 **구성 \> 애플리케이션별 매개 변수 설정** 을 선택합니다.
3. **애플리케이션별 매개 변수** 페이지의 **조회** 빠른 탭에서 **보고서 필드 조회** 를 선택하십시오.
4. **조건** 빠른 탭에서 다음 필드를 설정하여 판매세 코드 및 보고서 필드를 연결하십시오.

    | 필드                  | 설명                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | 조회 결과          | 보고서 필드의 값을 선택하십시오. 값 및 VAT 신고 행에 대한 할당에 대한 자세한 내용은 이 항목의 앞부분에 있는 [VAT 신고 개요](#vat-declaration-overview) 섹션을 참조하십시오.                                                                                               |
    | 세금 코드               | 보고서 필드와 연결할 판매세 코드를 선택합니다. 선택한 판매세 코드를 사용하는 전기된 세금 거래는 해당 신고 상자에 수집됩니다. 하나의 판매세 코드가 하나의 신고 상자에만 금액을 생성하도록 판매세 코드를 분리하는 것이 좋습니다. |
    | 거래 분류자 | 신고 상자를 결정하기에 충분한 판매세 코드를 생성한 경우 **\*비어 있지 않음\*** 을 선택합니다. 하나의 판매세 코드가 하나의 신고 상자에서만 금액을 생성하도록 판매세 코드를 충분히 생성하지 않은 경우 거래 분류자를 설정할 수 있습니다. 다음 거래 분류자를 사용할 수 있습니다.</br>-   **구매**</br>-   **PurchaseExempt**(면세 구매)</br>-   **PurchaseReverseCharge**(역청구로 받을 세금)</br>-   **영업**</br>-   **SalesExempt**(면세 판매)</br>-   **SalesReverseCharge**(구매 취소 수수료 또는 판매 취소 수수료에 부과되는 세금)</br>-   **사용세**. </br>각 거래 분류자에 대해 신용 메모에 대한 분류자도 사용할 수 있습니다. 예를 들어 이러한 분류기 중 하나가 **PurchaseCreditNote**(구매 신용 메모)입니다.</br>각 판매세 코드에 대해 두 줄을 생성해야 합니다. 하나는 거래 분류자 값이고 다른 하나는 신용 메모 값에 대한 거래 분류자입니다. |

    > [!NOTE]
    > 모든 판매세 코드를 조회 결과와 연결합니다. 판매세 코드가 VAT 신고서에 값을 생성하지 않아야 하는 경우 **기타** 조회 결과와 연결합니다.

    ![애플리케이션별 매개 변수 페이지](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. **상태** 필드에서 값을 **완료** 로 변경합니다.
6. 작업 창에서 **내보내기** 를 선택하여 응용 프로그램별 매개 변수의 설정을 내보냅니다.
7. **VAT 선언 Excel(DE)** 구성을 선택한 다음 작업 창에서 **가져오기** 를 선택하여 **VAT 선언 XML(DE)** 에 대해 구성한 매개 변수를 가져옵니다.
8. **상태** 필드에서 **완료** 를 선택합니다.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Excel에서 미리보기 금액에 대한 VAT 보고 형식 설정

1. **기능 관리** 작업 공간에서 **VAT 문 형식 보고서** 기능을 찾아 활성화합니다.
2. **총계정원장**  >  **설정**  >  **총계정원장 매개 변수** 로 이동합니다.
3. **판매세** 탭의 **세금 옵션** 빠른 탭 **부가가치세 명세서 형식 매핑** 필드에서 **부가가치세 신고 Excel(DE)** 을 선택합니다.

   이 형식은 **정산 기간 매출세 신고** 보고서를 실행하면 출력됩니다. 또한 **판매세 납부** 페이지에서 **인쇄** 를 선택하면 인쇄됩니다.

4. **세무 기관** 페이지에서 세무 기관을 선택한 다음 **보고서 레이아웃** 필드에서 **기본값** 을 선택하십시오.

[여러 VAT 등록](emea-reporting-for-multiple-vat-registrations.md)을 보유한 법인에 VAT 신고서를 구성하는 경우 이 단계를 따르십시오.

1. **총계정원장**  >  **설정**  >  **총계정원장 매개 변수** 로 이동합니다.
2. **판매세** 탭의 **국가/지역에 대한 전자 보고** 빠른 탭의 **DEU** 행에서 **VAT 신고 Excel(DE)** ER 형식을 선택합니다.

## <a name="set-up-electronic-messages"></a>전자 메시지 설정

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>전자 메시지에 대한 예제 설정이 있는 데이터 패키지 다운로드 및 가져오기

데이터 패키지에는 XML 형식으로 VAT 선언을 생성한 다음 Excel에서 미리 보는 데 사용되는 전자 메시지 설정이 포함되어 있습니다. 이 설정을 확장하거나 직접 만들 수 있습니다. 전자 메시징을 사용하고 사용자 고유의 설정을 만드는 방법에 대한 자세한 내용은 [전자 메시징](../general-ledger/electronic-messaging.md)을 참조하십시오.

1. 공유 자산 라이브러리의 [LCS(Microsoft Dynamics Lifecycle Services)](https://lcs.dynamics.com/v2)에서 자산 유형으로 **데이터 패키지** 를 선택한 다음 **DE VAT 선언 EM 패키지** 를 다운로드하십시오. 다운로드한 파일의 이름은 **DE VAT declaration EM package.zip** 입니다.
2. Dynamics 365 Finance의 **데이터 관리** 작업 공간에서 **가져오기** 를 선택합니다.
3. **가져오기** 빠른 탭의 **그룹 이름** 필드에 작업의 이름을 입력하십시오.
4. **선택한 엔터티** 빠른 탭에서 **파일 추가** 를 선택합니다.
5. **파일 추가** 대화 상자에서 **원본 데이터 형식** 필드가 **패키지** 로 설정되어 있는지 확인하고 **업로드 및 추가** 를 선택한 다음 이전에 다운로드한 zip 파일을 선택하십시오.
6. **닫기** 를 선택합니다.
7. 데이터 엔터티가 업로드된 후 작업 창에서 **가져오기** 를 선택합니다.
8. **세금** > **조회 및 신고** > **전자 메시지** > **전자 메시지** 로 이동하여 가져온 전자메시지 처리(DKV AT 신고)를 확인합니다.

### <a name="configure-electronic-messages"></a>전자 메시지 구성

1. **세금** > **설정** > **전자 메시지** > **레코드 채우기 작업** 으로 이동합니다.
2. **DE VAT 반환 레코드 채우기** 행을 선택한 다음 **쿼리 편집** 을 선택합니다.
3. 필터를 사용하여 보고서에 포함할 결제 기간을 지정합니다.
4. 다른 결산 기간의 세금 거래를 다른 신고로 보고해야 하는 경우 신규 **레코드 채우기** 작업을 만들고 적절한 정산 기간을 선택하십시오.

## <a name="preview-the-vat-declaration-in-excel"></a>Excel에서 VAT 신고 미리보기

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>정산 기간의 판매세 신고 주기 작업에서 Excel로 VAT 신고 미리보기

1. **세금** > **정기 작업** > **신고** > **판매세** > **정산기간 판매세 신고** 로 이동합니다.
2. **정산 기간** 필드에서 값을 선택합니다.
3. **판매세 납부 버전** 필드에서 다음 값 중 하나를 선택합니다.

    - **원래**: 최초 판매세 납부 또는 판매세 납부가 생성되기 전의 판매세 거래에 대한 보고서를 생성합니다.
    - **수정**: 해당 기간에 대한 모든 후속 판매세 납부의 판매세 거래에 대한 보고서를 생성합니다.
    - **전체 목록**: 원본 및 모든 수정을 포함하여 해당 기간의 모든 판매세 거래에 대한 보고서를 생성합니다.

4. **시작 날짜** 필드에서 보고 기간의 시작 날짜를 선택합니다.
5. **확인** 을 선택하고 Excel 보고서를 검토합니다.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>매출세 정산 후 납부

1. **세금**  >  **정기업무**  >  **신고서**  >  **판매세**  >  **정산 후 판매세** 로 이동합니다.
2. **정산 기간** 필드에서 값을 선택합니다.
3. **판매세 납부 버전** 필드에서 다음 값 중 하나를 선택합니다.

    - **원래**: 정산기간에 대한 판매세 원천징수를 생성합니다.
    - **최신 수정 사항**: 정산기간에 대한 최초 판매세 납부가 생성된 후 정정 판매세 납부를 생성합니다.

4. **시작 날짜** 필드에서 보고 기간의 시작 날짜를 선택합니다.
5. **확인** 을 선택합니다.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>판매세 납부에서 Excel의 VAT 신고 미리보기

1. **세금** > **문의 및 신고** > **판매세 문의** > **판매세 지불** 로 이동하여 판매세 납부 라인을 선택합니다.
2. **보고서 인쇄** 를 선택하고 **확인** 을 선택합니다.
3. 선택한 판매세 납부 라인에 대해 생성된 Excel 파일을 검토합니다.

    > [!NOTE]
    > 보고서는 판매세 납부의 선택된 라인에 대해서만 생성됩니다. 예를 들어, 해당 기간에 대한 모든 수정 사항이 포함된 수정 신고서 또는 원본 데이터와 모든 수정 사항이 포함된 교체 신고서를 생성해야 하는 경우, **결산 기간 정기 작업에 대한 보고서** 판매세를 사용하십시오.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>전자 메시지에서 VAT 신고 생성

전자 메시지를 사용하여 보고서를 생성할 때 여러 법인에서 세금 데이터를 수집할 수 있습니다. 자세한 내용은 이 항목의 뒷부분에 나오는 [여러 법인에 대해 VAT 신고 실행](#run-a-vat-declaration-for-multiple-legal-entities) 섹션을 참조하십시오.

다음 절차는 이전에 LCS 공유 자산 라이브러리에서 가져온 전자 메시지 처리 예제에 적용됩니다.

1. **세금** > **문의 및 신고** > **전자 메시지** > **전자 메시지** 로 이동합니다.
2. 왼쪽 창에서 **DE VAT 신고** 를 선택합니다.
3. **메시지** 빠른 탭에서 **새로 만들기** 를 선택한 다음 **처리 실행** 대화 상자에서 **확인** 을 선택합니다.
4. 생성된 메시지 라인을 선택하고 설명을 입력한 다음 선언의 시작 날짜와 종료 날짜를 지정합니다.

    > [!NOTE]
    > 5~7단계는 선택 사항입니다.

5. 선택 사항: **메시지** 빠른 탭에서 **데이터 수집** 을 선택한 다음 **확인** 을 선택합니다. 이전에 생성된 판매세 지불이 메시지에 추가됩니다. 자세한 내용은 이 항목의 앞부분에 있는 [정산 및 사후 판매세](#settle-and-post-sales-tax) 섹션을 참조하십시오. 이 단계를 건너뛰어도 **선언** 대화상자의 **세금 신고 버전** 필드를 사용하여 VAT 신고서를 생성할 수 있습니다.
6. 선택 사항: **메시지 항목** 빠른 탭에서 처리를 위해 이전된 판매세 납부를 검토합니다. 기본적으로 동일한 처리의 다른 메시지에 포함되지 않은 선택한 기간의 모든 판매세 납부가 포함됩니다.
7. 선택 사항: 판매세 납부를 검토하려면 **원본 문서** 를 선택하고, 처리에서 판매세 납부를 제외하려면 **삭제** 를 선택합니다. 이 단계를 건너뛰어도 **선언** 대화상자의 **세금 신고 버전** 필드를 사용하여 VAT 신고서를 생성할 수 있습니다.
8. **메시지** 빠른 탭에서 **업데이트 상태** 를 선택합니다. **업데이트 상태** 대화 상자에서 **생성할 준비** 를 선택한 다음 **확인** 을 선택합니다. 메시지 상태가 **생성 준비** 로 변경되었는지 확인합니다.
9. **보고서 생성** 을 선택합니다. VAT 신고 금액을 미리 보려면 **처리 실행** 대화 상자에서 **보고서 미리 보기** 를 선택한 다음 **확인** 을 선택하십시오.
10. **전자 보고 매개 변수** 대화 상자에서 다음 필드를 설정하고 **확인** 을 선택합니다.

    | **필드**                                   | **설명**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | 정산 기간                           | 정산 기간을 선택합니다. 5단계에서 **데이터 수집** 을 선택한 경우 이 필드를 비워 둘 수 있습니다. 징수된 판매세 납부에 포함된 판매세 거래에 대한 보고서가 생성됩니다. |
    | 세금 신고 버전                     | 다음 값 중 하나를 선택합니다.</br>-   **원래** - 최초 판매세 납부 또는 판매세 납부가 생성되기 전의 판매세 거래에 대한 보고서를 생성합니다.</br>-   **수정** - 해당 기간에 대한 모든 후속 판매세 납부의 판매세 거래에 대한 보고서를 생성합니다.</br>-   **전체 목록** - 원본 및 모든 수정을 포함하여 해당 기간의 모든 판매세 거래에 대한 보고서를 생성합니다.|
    | 세무 대리인 | 해당되는 경우 VAT 신고를 위한 세무 대리인인 당사자를 선택합니다. 선택한 당사자에 대한 정보가 **DatenLieferant** XML 요소로 내보내집니다. |
    | 담당자 | 데이터 공급자인 조직의 개인을 선택합니다. 선택한 사람에 대한 정보가 **DatenLieferant** XML 요소로 내보내집니다. |
    | 수정 반환 | VAT 선언 수정일 경우 **예** 를 선택합니다.= 이 경우 XML 요소 KZ10의 값은 **1** 이 됩니다.|
    | 지원 문서 | 지원 문서도 발송할 경우 **예** 를 선택합니다. 이 경우 XML 요소 KZ22의 값은 **1** 이 됩니다.|
    | SEPA 직접 차변 위임은 예외로 취소됩니다.| 이 사전 등록 기간에 대한 예외로 SEPA 직접 차변 사용 권한을 취소하려면 **예** 를 선택합니다. 예를 들어, 오프셋 요청이 있을 수 있습니다. 나머지 잔액은 별도로 지불해야 합니다. 이 경우 XML 요소 KZ26의 값은 **1** 이 됩니다. |
    | 원하는 상환 금액의 상계 | 보상 금액을 상쇄하거나 보상 금액이 할당된 경우 **예** 를 선택합니다. 이 경우 XML 요소 KZ29의 값은 **1** 이 됩니다. |
    | 특별 선지급 영구 연장 | 영구 연장 특별 선급금의 공제 금액을 입력합니다. 이 공제 금액은 일반적으로 과세 기간의 마지막 사전 등록에서만 완료됩니다. 금액은 VAT 신고의 67행(상자 39) 및 XML 요소 KZ39에서 내보내집니다. |

11. 페이지의 오른쪽 상단 모서리에 있는 **첨부 파일** 을 선택한 후 **열기** 를 선택합니다.
12. Excel 문서의 금액을 검토한 후 **보고서 생성** 을 선택합니다.
13. XML 형식으로 VAT 선언을 생성하려면 **처리 실행** 대화 상자에서 **보고서 생성** 을 선택한 다음 **확인** 을 선택하십시오.
14. **전자 보고 매개 변수** 대화 상자에서 10단계에서 설명한 대로 필드를 설정합니다.
15. 페이지의 오른쪽 상단 모서리에 있는 **첨부 파일** 을 선택하고 파일을 다운로드한 후 세무 기관에 제출하는 데 사용합니다.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>여러 법인에 대해 VAT 신고 실행

형식을 사용하여 법인 그룹에 대한 VAT 신고를 보고하려면 먼저 모든 필수 법인의 판매세 코드에 대한 ER 형식의 애플리케이션별 매개변수를 설정해야 합니다.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>여러 법인으로부터 세금 데이터를 수집하기 위한 전자 메시지 설정

여러 법인에서 데이터를 수집하도록 전자 메시지를 설정하려면 다음 단계를 따르십시오.

1. **작업 공간**  >  **기능 관리** 로 이동합니다.
2. 목록에서 **레코드 채우기 작업 기능에 대한 회사 간 쿼리** 를 찾아 선택한 다음 **지금 사용** 을 선택합니다.
3. **세금**  >  **설정**  >  **전자 메시지 \> 레코드 채우기 작업** 으로 이동합니다.
4. **레코드 채우기 작업** 페이지에서 **DE VAT 반환 레코드 채우기** 행을 선택합니다.

   **데이터 원본 설정** 그리드에서 새 **회사** 필드를 사용할 수 있습니다. 기존 레코드의 경우 이 필드에는 현재 법인의 식별자가 표시됩니다.

5. **데이터 원본 설정** 그리드에서 보고에 포함되어야 하는 각 추가 법인에 대한 행을 추가하고 다음 필드를 설정합니다. 각 새 줄에 대해 다음 필드를 설정합니다.

    | 필드                  | 설명                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | 이름                   | 이 레코드의 출처를 이해하는 데 도움이 되는 값을 입력합니다. 예를 들어 **자회사 1의 부가가치세 납부** 를 입력합니다. |
    | 메시지 항목 유형      | **부가가치세 반환** 을 선택합니다. 이 값은 모든 레코드에 사용할 수 있는 유일한 값입니다.                                    |
    | 계정 유형           | **모두** 를 선택합니다.                                                                                                               |
    | 마스터 테이블 이름      | 모든 레코드에 대해 **TaxReportVoucher** 를 지정합니다.                                                                             |
    | 문서 번호 필드  | 모든 레코드에 대해 **Voucher** 를 지정합니다.                                                                                      |
    | 문서 날짜 필드    | 모든 레코드에 대해 **TransDate** 를 지정합니다.                                                                                    |
    | 문서 계정 필드 | 모든 레코드에 대해 **TaxPeriod** 를 지정합니다.                                                                                    |
    | 회사                | 법인 ID를 선택합니다.                                                                                            |
    | 사용자 쿼리             | 이 확인란은 **쿼리 편집** 을 선택하여 기준을 정의할 때 자동으로 선택됩니다.                                 |

6. 새 줄마다 **쿼리 편집** 을 선택하고 줄의 **회사** 필드에 지정된 법인에 대한 관련 정산 기간을 지정합니다.

설정이 완료되면 **전자 메시지** 페이지의 **데이터 수집** 기능은 사용자가 정의한 모든 법인의 판매세 납부를 수집합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]