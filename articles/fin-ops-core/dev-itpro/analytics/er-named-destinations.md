---
title: 인쇄 관리 기록별 ER 대상 구성
description: 이번에는 아웃바운드 문서를 생성하도록 구성된 전자 보고(ER) 형식에 대해 인쇄 관리 기록 특정 대상을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2021
ms.locfileid: "8461030"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>인쇄 관리 기록별 ER 대상 구성

[!include [banner](../includes/banner.md)]

이번에는 시스템 관리자 또는 미수금 사무원 역할의 사용자가 다음 작업을 수행할 수 있는 방법에 대해 설명합니다.

- 무료 텍스트 송장을 생성하는 ER 솔루션에 대해 명명된 [전자 보고(ER)](general-electronic-reporting.md) 대상을 구성합니다.
- 단일 [인쇄 관리](document-reporting-services.md) 기록에 ER 대상을 지정합니다.

절차는 USMF 회사에서 완료할 수 있습니다. 코딩이 필요하지 않습니다.

## <a name="introduction"></a>소개

아웃바운드 문서를 생성하는 데 사용되는 ER [형식](general-electronic-reporting.md#FormatComponentOutbound) [구성](general-electronic-reporting.md#Configuration)의 파일 출력 구성 요소에서 각 폴더에 대한 [대상](electronic-reporting-destinations.md)을 구성할 수 있습니다. 이 유형의 ER 형식을 실행할 때 적절한 액세스 권한이 있는 경우 런타임 시 구성된 대상 설정을 변경할 수도 있습니다.

Microsoft Dynamics 365 Finance **버전 10.0.17 이상** 에서는 사용자가 해당 ER 형식을 실행하여 수행하는 작업을 지정하기 위해 ER 형식에 대한 작업 코드를 [설정](er-apis-app10-0-17.md)할 수 있습니다. 예를 들어 **미수금** 모듈의 인쇄 관리 설정에서 자유 텍스트 송장과 같은 특정 비즈니스 문서를 생성하는 ER 형식을 선택할 수 있습니다. 이후 **보기** 를 선택하여 송장을 미리 보거나 **인쇄** 를 선택하여 프린터로 보낼 수 있습니다. 런타임 시 실행 중인 ER 형식에 대해 작업이 전달되면 [다른 사용자 작업에 대해 다른 ER 대상을 구성](er-action-dependent-destinations.md)할 수 있습니다.

Finance **버전 10.0.21 이상** 에서는 ER 형식에 대해 명명된 대상을 [설정](er-apis-app10-0-21.md)하고 해당 ER 형식이 실행될 때 처리되는 인쇄 관리 기록에 할당할 수 있습니다. 예를 들어, **미수금** 모듈의 인쇄 관리 설정에서 다음 작업을 수행하도록 **원본** 기록을 구성하려고 합니다.

- ER 형식을 실행합니다.
- 생성된 송장을 고객에게 이메일로 보냅니다.
- 동일한 형식을 실행하도록 **복사** 기록을 구성합니다.
- 송장 사본을 네트워크 프린터로 인쇄합니다.

이 경우 실행 중인 ER 형식에 대해 다른 ER 대상을 구성해야 하고 다른 인쇄 관리 기록에 대한 대상을 선택해야 합니다.

## <a name="prerequisites"></a>전제 조건

시작하기 전에 [기능 관리](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) 작업 영역에서 **인쇄 관리 항목당 ER 대상 설정 허용** 기능이 켜져 있어야 합니다. 현재 Finance 인스턴스에서 명명된 ER 대상 구성을 허용하고 [새](er-apis-app10-0-21.md) ER API를 활성화하려면 소스 코드도 변경해야 합니다.

또한 **무료 텍스트 송장(Excel)** ER 구성을 Finance 인스턴스로 [가져와야](er-download-configurations-global-repo.md) 합니다.

## <a name="configure-a-new-er-destination"></a>새 ER 대상 구성

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. 고객 계정 **US-001** 에 대한 송장을 선택하십시오.
3. **무료 텍스트 송장** 페이지의 **송장** 탭에 있는 **인쇄 관리** 그룹에서 **인쇄 관리** 를 선택합니다.
4. **인쇄 관리 설정** 페이지에서 **모듈 - 미수금** \> **문서** \> **무료 텍스트 송장** 을 확장하고 **원본** 기록을 선택한 후 다음 단계를 따릅니다.

    1.  선택한 기록의 현재 설정을 관찰합니다.
        -   기본 SSRS 보고서 **FreeTextInvoice.Report** 는 **보고서 형식** 필드에서 선택됩니다.
        -   **\<Default\>** 이름은 지정된 SSRS 보고서에 대해 선택된 사용자 지정 대상이 없음을 알리는 **대상** 필드에 표시됩니다. 
    2.  **보고서 형식** 필드에서 **자유 텍스트 송장(Excel)** ER 형식 구성을 선택합니다.
        -   **대상** 필드의 이름이 **대상 이름** 으로 변경됩니다.
        -   지정된 ER 형식에 대해 선택된 명명된 대상이 없음을 알리는 **대상 이름** 필드에 **\<No named destination\>** 이름이 표시됩니다.
    3.  **대상 이름** 필드 오른쪽에 있는 화살표 버튼을 선택합니다.    
    4. **이름이 지정된 전자 보고** 페이지의 **이름** 필드에 **기본 대상** 을 입력합니다.
    5. **저장** 을 선택합니다.
    6. **파일 대상** FastTab에서 **보고서** 구성 요소에 대한 **전자 메일** 대상을 [구성](er-destination-type-email.md)합니다.
    7. **대상 페이지라는 이름의 전자 보고** 를 닫습니다.
    8. **인쇄 관리 설정** 페이지의 **대상 이름** 필드에서 대상이라는 **기본 대상** 을 선택합니다.

    ![선택한 ER 형식에 대해 명명된 ER 대상 구성 및 인쇄 관리 설정 페이지에서 구성된 인쇄 관리 기록에 할당](./media/er-named-destinations-01.gif)

    이제 **무료 텍스트 송장(Excel)** 형식에 대해 명명된 ER 대상 **기본 대상** 을 구성하고 이를 **모듈 - 매출채권** \> **문서** \> **무료 텍스트 송장** 아래의 **원본** 인쇄 관리 기록에 할당했습니다.

5. **모듈 - 미수금** \> **계정 - US-001** \> **자유 텍스트 송장** 을 확장하고 **원본** 기록을 선택한 후 다음 단계를 수행합니다.

    1. 기록을 길게 선택하거나 마우스 오른쪽 버튼으로 클릭한 다음 **재정의** 를 선택합니다.
    2. **대상 이름** 필드 오른쪽에 있는 화살표 버튼을 선택합니다.
    3. **전자 보고 대상** 페이지의 작업 창에서 **새로 만들기** 를 선택합니다.
    4. **이름** 필드에 **US-001 대상** 를 입력합니다.
    5. **파일 대상** FastTab에서 **보고서** 구성 요소에 대한 **프린터** 대상을 [구성](er-destination-type-print.md)합니다.
    6. **대상 페이지라는 이름의 전자 보고** 를 닫습니다.
    7. **인쇄 관리 설정** 페이지의 **대상 이름** 필드에서 대상이라는 **US-001 대상** 을 선택합니다.

    ![선택한 ER 형식에 대해 명명된 ER 대상 구성 및 인쇄 관리 설정 페이지에서 구성된 인쇄 관리 기록에 할당](./media/er-named-destinations-02.gif)

    이제 **자유 텍스트 송장(Excel)** 형식에 대해 명명된 ER 대상 **US-001 대상** 을 구성하고 이를 **모듈 - 미수금** \> **계정 - US-001** \> **무료 텍스트 송장** 아래의 **원본** 인쇄 관리 기록에 할당했습니다.

이제 자유 텍스트 송장을 처리할 때 **자유 텍스트 송장(Excel)** ER 형식이 실행되고 다음 이벤트 중 하나가 발생합니다.

- 무료 텍스트 송장이 US-001이 아닌 고객을 위한 것인 경우 생성된 문서는 이메일로 전송됩니다.
- 자유 텍스트 송장이 US-001 고객용인 경우 생성된 문서가 인쇄됩니다.

> [!NOTE]
> 런타임에 처리되는 인쇄 관리 기록에 대해 명명된 대상이 정의되지 않은 경우 실행 중인 ER 형식에 사용할 수 있는 경우 기본 ER 대상이 사용됩니다.

> [!IMPORTANT]
> **전자 보고 대상** 페이지(**조직 관리** \> **전자 보고** \> **전자 보고 대상**)에서 하나 이상의 명명된 대상이 구성된 ER 형식을 선택하면 명명된 대상이 있다는 알림을 받습니다.
>
> ![전자 보고 대상 페이지에서 선택한 ER 형식에 대해 구성된 명명된 대상의 존재에 대한 알림](./media/er-named-destinations-03.png)
>
> 기본 대상을 삭제하면 명명된 모든 대상도 삭제됩니다. 인쇄 관리 기록에 대해 명명된 수신인을 선택한 경우 명명된 수신인의 선택이 취소됩니다.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>기존 ER 대상을 새 명명된 대상으로 복사

기본 명명된 ER 대상을 ER 형식에 사용할 수 있는 경우 새 ER 대상에 대한 템플릿으로 사용할 수 있습니다. 기본 대상을 기반으로 하는 새 ER 대상을 생성하려면 **대상라는 이름의 전자 보고** 페이지에서 **기본값에서 복사** 를 선택하십시오. 새 대상의 이름은 **기본값** 입니다. 이 단계를 필요한 만큼 반복할 수 있습니다.

기존의 명명된 대상을 새 명명된 대상의 템플릿으로 선택할 수 있습니다. 선택한 명명된 대상을 기반으로 하는 명명된 ER 대상을 새로 생성하려면 **명명된 전자 보고 대상** 페이지에서 **복사** 를 선택합니다. 새 대상은 선택한 명명된 대상과 이름이 같지만 접미사 '복사'가 추가됩니다. 이 단계를 필요한 만큼 반복할 수 있습니다.

## <a name="security-considerations"></a>보안 고려 사항

이 작업을 수행할 [권한](../sysadmin/role-based-security.md#permissions)이 있는 경우에만 **인쇄 관리 설정** 페이지에서 명명된 ER 대상을 설정할 수 있습니다. **전자 보고 형식 구성 대상** [의무](../sysadmin/role-based-security.md#duties)가 [보안 역할](../sysadmin/role-based-security.md#security-roles) 중 하나에 할당된 경우 권한이 부여될 수 있습니다. 자세한 내용은 [보안 고려 사항](electronic-reporting-destinations.md#security-considerations)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[전자 보고(ER) 대상](electronic-reporting-destinations.md)

[애플리케이션 업데이트 10.0.17에 대한 전자 보고 프레임워크 API 변경](er-apis-app10-0-17.md)

[애플리케이션 업데이트 10.0.21에 대한 전자 보고 프레임워크 API 변경](er-apis-app10-0-21.md)

[사용자가 명명된 ER 대상을 구성하고 사용할 수 있도록 코드 변경](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
