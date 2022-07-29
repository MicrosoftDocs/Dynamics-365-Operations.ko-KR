---
title: 이메일 ER 대상 유형
description: 이번에는 전자 보고(ER) 형식의 각 FOLDER 또는 FILE 구성 요소에 대한 전자 메일 대상을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2248b8a35b076eb778a50bbbc67d083380ceee62
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460859"
---
# <a name="email-er-destination-type"></a>이메일 ER 대상 유형

[!include [banner](../includes/banner.md)]

전자 보고(ER) 형식이 실행되면 하나 이상의 아웃바운드 문서가 생성될 수 있습니다. **폴더** 또는 **파일** 형식 구성 요소는 아웃바운드 문서의 구조를 지정하기 위해 ER 형식에서 사용됩니다. 아웃바운드 문서를 이메일 첨부 파일로 보내도록 이러한 유형의 구성 요소에 대한 이메일 대상을 구성할 수 있습니다.

ER 형식의 각 **폴더** 또는 **파일** 구성 요소에 대해 이메일 대상을 구성할 수 있습니다. 이 경우 **각 아웃바운드 문서는 개별적으로 이메일로 전송됩니다**. 이 대상 설정에 따라 생성된 문서는 이메일의 첨부 파일로 전달됩니다. 

> [!NOTE]
> 문서가 생성되지 않으면 관련 **File** 구성 요소에 대한 **Enabled** 식이 **False** Boolean 값을 반환하도록 구성되었으므로 구성 요소에 대해 전자 메일 대상이 구성되고 활성화된 경우에도 전자 메일이 전송되지 않습니다.

여러 **폴더** 또는 **파일** 구성 요소를 함께 [그룹화한](#grouping) 다음 그룹의 모든 구성 요소에 대한 전자 메일 대상을 구성할 수도 있습니다. 이 경우 그룹에 속한 구성 요소에서 생성된 모든 아웃바운드 문서는 **단일 이메일의 여러 첨부 파일로 전송** 됩니다. 이 대상 설정에 따라 생성된 각 문서는 단일 이메일의 첨부 파일로 전달됩니다.

> [!NOTE]
> 구성 요소 그룹의 **파일** 구성 요소에 의해 하나 이상의 문서가 생성되면 전자 메일이 전송됩니다. 그룹화된 구성 요소에서 생성된 문서가 없으면 각 **파일** 구성 요소에 대한 **Enabled** 표현식이 **False** Boolean 값을 반환하도록 구성되었기 때문에 해당 구성 요소 그룹에 대해 전자 메일 대상이 구성되고 활성화된 경우에도 전자 메일이 전송되지 않습니다.
>
> **이메일** 은 구성 요소 그룹에 대해 구성할 수 있는 유일한 대상입니다. 그룹의 이메일 대상 설정에 따라 이메일로 전송되는 문서를 배달하려면 대상 기록을 하나 더 추가하고 원하는 구성 요소를 선택한 다음 이 기록에 대해 다른 대상을 구성합니다.

단일 ER 형식 구성에 대해 여러 구성 요소 그룹을 구성할 수 있습니다. 이러한 방식으로 모든 구성 요소 그룹에 대한 전자 메일 대상과 모든 구성 요소에 대한 전자 메일 대상을 구성할 수 있습니다.

## <a name="enable-an-email-destination"></a>이메일 대상 활성화

하나 이상의 출력 파일을 이메일로 보내려면 다음 단계를 따르십시오.

1. **전자 보고 대상** 페이지의 **파일 대상** FastTab에서 그리드의 구성 요소 또는 구성 요소 그룹을 선택합니다.
2. **설정** 을 선택한 다음 **대상 설정** 대화 상자의 **전자 메일** 탭에서 **사용** 옵션을 **예** 로 설정합니다.

[![이메일 대상에 대해 사용 옵션을 예로 설정합니다.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>이메일 대상 구성

### <a name="email-content"></a>전자 메일 콘텐츠

이메일 메시지의 제목과 본문을 편집할 수 있습니다.

**제목** 필드에 런타임에 생성되는 전자 메시지의 제목 필드에 나타나야 하는 이메일 제목의 텍스트를 입력합니다. **본문** 필드에 전자 메시지의 본문 필드에 나타나야 하는 이메일 본문의 텍스트를 입력합니다. 이메일 제목과 본문에 대한 상수 텍스트를 설정하거나 ER [공식](er-formula-language.md)을 사용하여 런타임에 이메일 텍스트를 동적으로 생성할 수 있습니다. 구성된 수식은 [스트링](er-formula-supported-data-types-primitive.md#string) 유형의 값을 반환해야 합니다.

이메일 본문은 이메일 클라이언트에 따라 TEXT 또는 HTML 형식으로 구성됩니다. HTML 및 인라인 Cascading Style Sheets(CSS)에서 허용하는 모든 레이아웃, 스타일 및 브랜딩을 사용할 수 있습니다.

> [!NOTE]
> 이메일 클라이언트는 HTML을 CSS 조정해야 하고 메시지 본문에 사용하는 레이아웃 및 스타일 제한을 부과합니다. 가장 많이 사용되는 이메일 클라이언트가 지원할 HTML 작성 모범 사례를 숙지하는 것이 좋습니다.
>
> 본문 형식에 따라 올바른 인코딩을 사용하여 캐리지 리턴을 구현하십시오. 자세한 내용은 [스트링](er-formula-supported-data-types-primitive.md#string) 데이터 형식의 정의를 참조하십시오.

### <a name="email-addresses"></a>이메일 주소

이메일 발신자와 이메일 수신자를 지정할 수 있습니다. 기본적으로 이메일은 현재 사용자를 대신하여 전송됩니다. 다른 이메일 발신자를 지정하려면 **보낸 사람** 필드를 구성해야 합니다.

> [!NOTE]
> 전자 메일 대상이 구성되면 **보낸 사람** 필드는 `ERFormatDestinationSenderEmailConfigure` 보안 권한이 있는 사용자에게만 표시됩니다. **ER 형식 대상에 대한 보낸 사람 전자 메일 주소 구성**.
>
> [런타임](electronic-reporting-destinations.md#security-considerations) 시 수정을 위해 이메일 대상이 제공되면 **보낸 사람** 필드는 `ERFormatDestinationSenderEmailMaintain` 보안 권한이 있는 사용자에게만 표시됩니다. **ER 형식 대상에 대한 보낸 사람 이메일 주소 유지 관리**.
>
> **보낸 사람** 필드가 현재 사용자가 아닌 다른 이메일 주소를 사용하도록 구성된 경우 **다른 사람 이름으로 보내기** 또는 **대신 보내기** 권한이 미리 올바르게 [설정되어](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group) 있어야 합니다. 그렇지 않으면 런타임에 다음 예외가 발생합니다. \<current user account\> 계정에서 \<from email account\>로 이메일을 보낼 수 없습니다. \<from email account\>에서 '다른 이름으로 보내기' 권한을 확인하십시오.

둘 이상의 이메일 주소를 반환하도록 **보낸 사람** 필드를 구성할 수 있습니다. 이 경우 목록의 첫 번째 주소가 이메일 발신인 주소로 사용됩니다.

이메일 수신자를 지정하려면 **받는 사람** 및 **참조**(선택 사항) 필드를 구성해야 합니다.

두 가지 방법으로 ER에 대한 이메일 주소를 구성할 수 있습니다. 인쇄 관리 기능과 동일한 방법으로 구성을 완료하거나 수식을 통해 ER 구성에 대한 직접 참조를 사용하여 이메일 주소를 확인할 수 있습니다.

## <a name="email-address-types"></a>이메일 주소 유형

**대상 설정** 대화 상자에서 **보낸 사람**, **받는 사람** 또는 **참조** 필드 옆에 있는 **편집** 을 선택하면 적절한 **전자 메일 보낸 사람**, **전자 메일 받는 사람** 또는 **전자 메일 참조** 대화 상자가 나타납니다. 여기에서 이메일 발신자와 이메일 수신자를 구성할 수 있습니다. **추가** 를 선택한 다음 사용할 전자 메일 주소 유형을 선택합니다. 현재 두 가지 유형이 지원됩니다. **인쇄 관리 이메일** 및 **구성 이메일**.

[![이메일 주소 유형 선택.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>인쇄 관리 이메일

**인쇄 관리 이메일** 을 이메일 주소 유형으로 선택한 경우 다음 필드를 설정하여 **이메일 발신자**, **이메일 수신자** 또는 **이메일 참조** 대화 상자에 고정 이메일 주소를 입력할 수 있습니다.

- **이메일 소스** 필드에서 **없음** 을 선택하십시오.
- **추가 이메일 주소에서 ';'** 필드에 고정 이메일 주소를 입력합니다.

또는 아웃바운드 문서를 생성하는 당사자의 연락처 세부 정보에서 이메일 주소를 얻을 수 있습니다. 고정되지 않은 이메일 주소를 사용하려면 **이메일 소스** 필드에서 파일 대상에 대한 당사자의 [역할](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles)을 선택합니다. 다음과 같은 가능성이 지원됩니다.

- 고객
- 공급 업체
- 예상 후보자
- 연락처
- 경쟁자
- 작업자
- 적용 가능성
- 예상 공급 업체
- 허용되지 않는 공급 업체
- 법인

예를 들어, **공급 업체** 지급을 처리하는 데 사용되는 ER 형식의 이메일 대상을 구성하려면 공급 업체 역할을 선택합니다.

원하는 역할을 선택한 후 **이메일 소스 계정** 필드 옆에 있는 **바인딩** 버튼(체인 기호)을 선택하여 [수식 디자이너](general-electronic-reporting-formula-designer.md) 페이지를 엽니다. 이후 이 페이지를 사용하여 런타임 시 처리된 문서에서 이메일 대상으로 구성된 역할에 할당된 당사자의 계정 번호를 반환하는 공식을 구성할 수 있습니다.

> [!NOTE]
> 공식은 ER 구성에 따라 다릅니다.

**공식 디자이너** 페이지의 **공식** 필드에 지원되는 역할에 대한 문서별 참조를 입력합니다. 참조를 입력하는 대신 **데이터 원본** 창에서 구성된 역할의 계정을 나타내는 데이터 원본 노드를 찾아 선택한 다음 **데이터 원본 추가** 를 선택하여 수식을 업데이트합니다. 예를 들어, 공급 업체 지급을 처리하는 데 사용되는 **ISO 20022 신용 전송** 구성에 대한 이메일 대상을 구성하는 경우 공급 업체 계정을 나타내는 노드는 `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`입니다.

![이메일 소스 계정 구성.](./media/er_destinations-emaildefineaddresssource.gif)

구성된 역할의 계정 번호가 Microsoft Dynamics 365 Finance의 전체 인스턴스에 대해 고유한 경우 **전자 메일 대상 대화 상자** 의 **전자 메일** 원본 회사 필드를 공백으로 둘 수 있습니다.

또는 [전체 주소록](../../fin-ops/organization-administration/overview-global-address-book.md)의 다른 당사자가 동일한 계정 번호를 사용하여 구성된 역할을 채우는 방식으로 다른 회사([법인](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities))에 등록된 상황이 있을 수 있습니다. 이 경우 구성된 역할의 계정 번호는 전체 Finance 인스턴스에 대해 고유하지 않습니다. 따라서 당사자를 명시적으로 선택하기 위해 계좌번호만 지정할 수는 없습니다. 또한 구성된 역할을 채우기 위해 범위에서 당사자가 등록된 회사를 지정해야 합니다. **전자 메일 대상** 대화 상자에서 **전자 메일 원본 회사** 필드 옆에 있는 **바인딩** 버튼(체인 기호)를 선택하여 [수식 디자이너](general-electronic-reporting-formula-designer.md) 페이지를 엽니다. 이후 이 페이지를 사용하여 런타임 시 범위에서 원하는 소스를 찾아야 하는 회사 코드를 반환하는 수식을 구성할 수 있습니다.

> [!TIP]
> 회사 코드를 사용하여 ER 형식을 실행해야 하지만 ER 형식이 회사 코드를 가져올 수 있는 데이터 소스를 제공하지 않는 경우 기본 제공 [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md) ER 함수를 사용하여 `GetCurrentCompany()` 공식을 구성하십시오.

> [!NOTE]
> 공식은 ER 구성에 따라 다릅니다.

런타임에 사용해야 하는 **이메일 주소** 유형을 지정하려면 이메일 대상 대화 상자에서 **받는 사람** 필드 옆에 있는 **편집** 을 선택하여 **이메일 주소 할당** 드롭다운 대화 상자를 엽니다. 이후 다음 필드를 설정합니다.

- **목적** 필드에서 원하는 목적을 선택합니다. 발견된 당사자의 연락처에서 선택한 목적의 이메일 주소만 사용됩니다.
- 검색된 당사자에 대해 구성된 이메일 주소를 **기본 이메일 주소** 로 사용하려면 기본 연락처 옵션을 **예** 로 설정합니다.

> [!NOTE]
> **목적** 필드에서 목적을 선택하고 **기본 연락처** 옵션을 동시에 **예** 로 설정하면 하나 이상의 구성된 기준을 충족하는 모든 이메일이 런타임에 사용됩니다.

### <a name="configuration-email"></a>구성 이메일

사용하는 구성에 세미콜론(;)으로 구분된 단일 전자 메일 주소 또는 여러 전자 메일 주소를 반환하는 노드가 데이터 원본에 있는 경우 **구성 전자 메일** 을 전자 메일 주소 유형으로 선택합니다. 수식 디자이너의 데이터 원본 및 [함수](er-formula-language.md#Functions)를 사용하여 올바른 형식의 전자 메일 주소 또는 세미콜론으로 구분된 올바른 형식의 전자 메일 주소를 가져올 수 있습니다. 예를 들어 **ISO 20022 신용 전송 구성** 을 사용하는 경우 커버 레터를 보내야 하는 공급 업체 연락처 세부 정보에서 공급 업체의 기본 이메일 주소를 나타내는 노드는 `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`입니다.

[![이메일 주소 소스 구성.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>그룹 형식 구성 요소

형식 구성 요소를 그룹화하려면 **전자 보고 대상** 페이지의 **파일 대상** FastTab에서 그리드의 구성 요소를 선택한 다음 **그룹** 을 선택합니다.

**이메일** 은 선택한 구성 요소에 대해 계속 사용할 수 있는 이전에 구성된 유일한 대상입니다. 이전에 구성된 다른 대상은 구성 요소 그룹에 대해 지원되지 않는 것으로 간주되기 때문에 사용할 수 없습니다. 귀하는 이러한 변경 사항에 대해 적절하게 통지를 받을 것입니다.

이전에 추가한 기록은 생성된 그룹의 헤더로 간주됩니다. 이 헤더 기록은 그룹에 대한 이메일 대상 설정을 보유합니다. 다른 기록은 그룹 헤더 기록의 이메일 대상 설정을 사용하는 그룹 구성원입니다.

형식 구성 요소의 그룹을 해제하려면 **파일 대상** FastTab에서 그룹에 속한 기록을 선택한 다음 **그룹 해제** 를 선택합니다.

- 헤더 기록을 선택하면 전체 그룹이 그룹 해제됩니다.
- 회원 기록을 선택하고 그룹의 마지막 회원 기록인 경우 전체 그룹이 그룹 해제됩니다.
- 그룹의 마지막 구성원 기록이 아닌 구성원 기록을 선택하면 해당 기록은 현재 그룹에서 제외됩니다.

다음 그림은 징수 편지 메모와 PDF 형식의 적절한 고객 송장을 포함하는 압축된 아웃바운드 파일을 생성하도록 구성된 ER 형식의 구조를 보여줍니다.

[![아웃바운드 문서를 생성하는 ER 형식의 구조입니다.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

다음 그림은 이 항목에 설명된 대로 개별 구성 요소를 그룹화하고 새 그룹에 대한 **전자 메일** 대상을 활성화하여 수집 편지 메모가 전자 메일 첨부 파일로 적절한 고객 송장과 함께 전송되도록 하는 프로세스를 보여줍니다.

[![개별 구성 요소를 그룹화하고 이메일 대상을 활성화합니다.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [전자 보고(ER) 대상](electronic-reporting-destinations.md)
- [전자 보고(ER) 공식 디자이너](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
