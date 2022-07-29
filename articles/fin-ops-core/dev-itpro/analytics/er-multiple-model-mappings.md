---
title: 단일 모델 루트에 대한 여러 파생 매핑 관리
description: 이번에는 단일 모델 루트에 대해 구성된 여러 파생 매핑을 관리하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d71b05b3f2eda93a93f728926e675c040371781e
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461006"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>단일 모델 루트에 대한 여러 파생 매핑 관리

[!include [banner](../includes/banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 데이터 모델 구성 요소는 구성된 모든 ER 형식 구성 요소에서 아웃바운드 문서를 생성하기 위한 데이터 소스로 사용됩니다. 단일 비즈니스 도메인을 설명하려면 많은 루트 정의가 있는 데이터 모델 구성 요소를 구성하십시오. 

모든 루트 정의를 통해 특정 보고 목적에 가장 적합한 방식으로 해당 도메인의 데이터를 나타낼 수 있습니다. 모든 루트 정의에 대해 ER 모델 매핑 구성 요소를 데이터 모델의 Microsoft Dynamics 365 Finance 고유 구현으로 구성할 수 있습니다. 이러한 방식으로 데이터 모델이 런타임에 채워지는 방법을 설명합니다.

ER 모델 매핑 구성 요소는 ER 데이터 모델 [구성](general-electronic-reporting.md#Configuration) 및 ER 모델 매핑 구성에 상주할 수 있습니다. 단일 ER 구성에는 각각 단일 루트 정의에 대해 구성된 여러 매핑 구성 요소가 포함될 수 있습니다. 또는 단일 ER 구성에 단일 루트 정의에 대해 구성된 매핑 구성 요소가 하나만 포함될 수 있습니다.

많은 구성 공급자가 동일한 ER 데이터 모델에 대한 ER 모델 매핑 구성을 제공할 수 있습니다. 이러한 모델 매핑 구성에는 다른 루트 정의에 대한 매핑 구성 요소가 포함될 수 있습니다. 한 [제공자](general-electronic-reporting.md#Provider)가 제공하는 하나의 루트 정의에 대한 모델 매핑을 사용하고 다른 제공자가 제공하는 다른 루트 정의에 대한 모델 매핑을 사용할 수 있습니다.

이 항목의 절차에서는 동일한 루트 정의에 대해 구성된 서로 다른 모델 매핑 구성 요소가 포함된 경우 ER 데이터 모델의 여러 ER 모델 매핑 구성을 관리하는 방법을 설명합니다. 

이 항목의 절차를 완료하려면 시스템 관리자 또는 전자 보고 개발자 역할에 할당되어야 합니다.

아래의 모든 절차는 USMF 회사에서 수행할 수 있습니다. 코딩이 필요하지 않습니다.

## <a name="configure-the-er-framework"></a>ER 프레임워크 구성

전자 보고 개발자 역할의 사용자는 ER 프레임워크를 사용하여 비즈니스 문서를 생성하기 전에 [최소한의 ER 매개 변수 세트를 구성](er-quick-start2-customize-report.md#ConfigureFramework)하십시오.

## <a name="import-the-standard-er-format-configurations"></a>표준 ER 형식 구성 가져오기

현재 Finance 인스턴스에 표준 ER 구성을 추가하려면 해당 인스턴스에 대해 구성된 ER 저장소에서 가져와야 합니다. [구성 서비스의 글로벌 리포지토리에서 ER 구성 다운로드](er-download-configurations-global-repo.md)의 단계에 따라 다음 ER 형식 구성을 가져옵니다.

- **무료 텍스트 송장(Excel)**, 버전 220.106
- **프로젝트 송장(Excel)**, 버전 226.27

## <a name="review-the-imported-er-configurations"></a>가져온 ER 형식 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **송장 모델** 을 확장합니다.

    ![구성 페이지에서 가져온 구성 검토](./media/er-multiple-model-mappings-image1.png)

4. **무료 텍스트 송장(Excel)** 형식 검토:

    1. 왼쪽 창의 구성 트리에서 **자유 텍스트 송장(Excel)** 을 선택합니다.
    2. 작업 창에서 **디자이너** 를 선택합니다.
    3. **형식 디자이너** 페이지의 **매핑** 탭에 있는 데이터 원본 목록에서 **모델** 을 선택합니다.
    4. **보기** 를 선택합니다.
    
       현재 ER 형식은 **Invoice 모델** 의 **InvoiceCustomer** 루트 정의를 사용하도록 구성되어 있습니다. 이 형식이 실행되고 **모델** 데이터 소스가 호출되면 **InvoiceCustomer** 루트 정의에 대해 구성된 모델 매핑이 애플리케이션 데이터에 액세스하고 데이터 모델을 채우는 데 사용됩니다.

        ![형식 디자이너 페이지에서 모델 데이터 소스를 검토합니다.](./media/er-multiple-model-mappings-image2.png)

    6. **형식 디자이너** 페이지를 닫습니다.

5. **송장 모델 매핑** 구성의 내용을 검토합니다.

    1. 왼쪽 창의 구성 트리에서 **송장 모델 매핑** 을 선택합니다.
    2. 작업 창에서 **디자이너** 를 선택합니다.
    3. **모델 대 데이터 소스 매핑** 페이지에서 현재 ER 모델 매핑 구성에 여러 모델 매핑 구성 요소가 포함되어 있습니다.

        + **고객 송장** 모델 매핑은 **송장 모델** 의 **InvoiceCustomer** 루트 정의에 대해 구성됩니다. 따라서 **자유 텍스트 송장(Excel)** ER 형식이 실행될 때 이 ER 구성의 **고객 송장** 모델 매핑을 선택하여 애플리케이션 데이터에 액세스하고 데이터 모델을 채울 수 있습니다.
        + **프로젝트 송장** 모델 매핑은 **송장 모델** 의 **InvoiceProject** 루트 정의에 대해 구성됩니다. 따라서 **프로젝트 송장(Excel)** ER 형식이 실행될 때 이 ER 구성의 **프로젝트 송장** 모델 매핑을 선택하여 애플리케이션 데이터에 액세스하고 데이터 모델을 채울 수 있습니다.

        ![모델 대 데이터 소스 매핑 페이지의 송장 모델 매핑.](./media/er-multiple-model-mappings-image3.png)

    4. **데이터 소스 매핑 모델링** 페이지를 닫습니다.
    5. **버전** FastTab에서 **삭제** 를 선택하여 버전 240.175 이후의 이 ER 구성의 모든 버전을 삭제합니다.

6. **프로젝트 송장 모델 매핑(RDP)** 구성의 내용을 검토합니다.

    1. 왼쪽 창의 구성 트리에서 **프로젝트 송장 모델 매핑(RDP)** 을 선택합니다.
    2. 작업 창에서 **디자이너** 를 선택합니다.
    3. **모델 대 데이터 소스 매핑** 페이지에서 현재 ER 모델 매핑 구성에 **InvoiceProject** 모델 매핑이 포함되어 있으며 이 모델 매핑은 **Invoice 모델** 의 **InvoiceProject** 루트 정의에 대해 구성되어 있습니다. **프로젝트 송장(Excel)** ER 형식이 실행되면 이 ER 구성의 **InvoiceProject** 모델 매핑을 선택하여 애플리케이션 데이터에 액세스하고 데이터 모델을 채웁니다.

        ![데이터 소스 매핑 페이지에 모델의 프로젝트 송장 모델 매핑.](./media/er-multiple-model-mappings-image4.png)

    4. **데이터 소스 매핑 모델링** 페이지를 닫습니다.
    5. **버전** FastTab에서 **삭제** 를 선택하여 버전 226.35 이후의 이 ER 구성의 모든 버전을 삭제합니다.

## <a name="customize-the-imported-er-configurations"></a>가져온 ER 구성 사용자 지정

이 섹션에서는 Microsoft에서 제공하는 모델 매핑을 [사용자 지정](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration)하는 방법을 설명합니다. 예를 들어 사용자 지정 논리를 구현하거나 누락된 바인딩을 추가하려면 사용자 지정이 필요할 수 있습니다.

### <a name="customize-the-invoice-model-mapping-configuration"></a>송장 모델 매핑 구성 사용자 지정

1. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **송장 모델 매핑** 을 선택합니다.
2. 작업 창에서 **구성 만들기** 를 선택합니다.
3. **구성 만들기** 드롭다운 대화 상자의 **새로 만들기** 필드에서 이름에서 파생을 선택합니다 **송장 모델 매핑, Microsoft**.
4. **이름** 필드에 **송장 모델 매핑 Litware** 를 입력합니다.
5. **구성 만들기** 를 선택합니다.
6. 파생 매핑의 [초안](general-electronic-reporting.md#component-versioning) 버전을 런타임에 사용할 수 있는 것으로 [표시](er-quick-start2-customize-report.md#MarkFormatRunnable)합니다.

    1. 작업 창의 **제품** 탭에 있는 **설정** 그룹에서 **단위 변환** 을 선택합니다.
    2. **사용자 매개 변수** 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
    3. 필요에 따라 **편집** 을 선택하여 페이지를 편집 가능하게 만듭니다.
    4. 구성 트리에서 현재 선택된 **송장 모델 매핑 Litware** 구성의 경우 **Run Draft** 옵션을 **Yes** 로 설정합니다.

7. 작업 창에서 **디자이너** 를 선택하여 이 구성의 모델 매핑을 검토합니다.

    ![모델에서 데이터 소스로의 매핑 페이지에서 송장 모델 매핑을 검토합니다.](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > 이제 디자이너에서 이 ER 구성의 ER 모델 매핑 구성 요소를 열어 사용자 지정 논리를 구성할 수 있습니다. 자세한 내용은 [모델 매핑 구성 사용자 지정](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration)을 참조하십시오.

8. **데이터 소스 매핑 모델링** 페이지를 닫습니다.

이제 각각 **InvoiceCustomer** 루트 정의에 대해 구성된 모델 매핑이 있는 **송장 모델 매핑** 및 **송장 모델 매핑 Litware** 구성이 있습니다. **InvoiceCustomer** 루트 정의가 있는 모델 데이터 원본이 포함된 **자유 텍스트 송장(Excel)** 형식과 같은 ER 형식에서 사용되는 기본 모델 매핑으로 모델 매핑 중 하나를 명시적으로 할당합니다. 그렇지 않으면 ER 형식 중 하나를 실행, 편집 또는 검증할 때 기본 모델 매핑이 명시적으로 할당되지 않았음을 알리기 위해 다음 예외가 발생합니다.
 
> \<configuration names separated by commas\> 구성의 '\<model name\>(\<root descriptor\>)' 데이터 모델에 대해 둘 이상의 모델 매핑이 존재합니다. 구성 중 하나를 기본값으로 설정합니다.

![구성 페이지에서 편집할 형식을 엽니다.](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>프로젝트 송장 모델 매핑(RDP) 구성 사용자 지정

1. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **프로젝트 송장 모델 매핑(RDP)** 을 선택합니다.
2. 작업 창에서 **구성 만들기** 를 선택합니다.
3. **구성 만들기** 대화 상자의 **새로 만들기** 필드에서 이름에서 파생을 선택합니다 **프로젝트 송장 모델 매핑(RDP), Microsoft**.
4. **이름** 필드에 **프로젝트 송장 모델 매핑 Litware** 를 입력합니다.
5. **구성 만들기** 를 선택합니다.
6. 현재 구성 트리에서 선택된 **프로젝트 송장 모델 매핑 Litware** 구성의 경우 **초안 실행** 옵션을 **예** 로 설정합니다.
7. 작업 창에서 **디자이너** 를 선택하여 이 구성의 모델 매핑을 검토합니다.

    ![모델에서 데이터 소스로의 매핑 페이지에서 사용자 지정된 프로젝트 송장 모델 매핑을 검토하십시오.](./media/er-multiple-model-mappings-image7.png)

8. **데이터 소스 매핑 모델링** 페이지를 닫습니다.

이제 **송장 모델 매핑**, **프로젝트 송장 모델 매핑(RDP)** 및 **프로젝트 송장 모델 매핑 Litware** 구성이 있습니다. 이러한 각 구성에는 **InvoiceProject** 루트 정의에 대해 구성된 모델 매핑이 있습니다. ER 형식에서 사용되는 기본 모델 매핑으로 모델 매핑 중 하나를 명시적으로 할당합니다. 예를 들어 **InvoiceProject** 루트 정의가 있는 모델 데이터 원본이 포함된 **프로젝트 송장(Excel)** 형식을 사용합니다. 그렇지 않으면 ER 형식 중 하나를 실행하거나 편집할 때 기본 모델 매핑이 명시적으로 할당되지 않았음을 알리는 예외가 발생합니다.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>파생된 송장 모델 매핑 Litware 구성을 기본 모델 매핑이 포함된 구성으로 선택합니다.

1. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **송장 모델 매핑 Litware** 를 선택합니다.
2. **모델 매핑에 대한 기본값** 옵션을 **예** 로 설정합니다.

    ![구성 페이지에서 모델 매핑을 기본 모델 매핑으로 설정합니다.](./media/er-multiple-model-mappings-image8.png)

    이 설정 때문에 **고객 송장 복사** 모델 매핑은 **자유 텍스트 송장(Excel)** 을 실행하거나 편집하거나 유효성을 검사할 때 사용됩니다. **송장 모델 매핑** 구성의 **고객 송장** 모델 매핑은 무시됩니다.

    이제 형식 디자이너에서 검토를 위해 **무료 텍스트 송장(Excel)** 형식을 열 수 있습니다.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>파생된 프로젝트 송장 모델 매핑 Litware 구성을 기본 모델 매핑이 포함된 구성으로 선택합니다.

1. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **프로젝트 송장 모델 매핑 Litware** 를 선택합니다.
2. **모델 매핑에 대한 기본값** 옵션을 **예** 로 설정합니다.

    이 경우 이전 섹션의 **송장 모델 매핑 Litware** 구성에 대해 설명된 경우와 달리 **프로젝트 송장 모델 매핑 Litware** 구성에서 **InvoiceProject Copy** 모델 매핑 사용을 시작할 수 없습니다. **InvoiceProject** 루트 정의에 대한 모델 매핑을 포함하는 두 개의 구성이 현재 기본 구성으로 표시되어 있습니다. 따라서 사용 우선 순위가 동일합니다. 이 문제를 해결하려면 이 절차의 나머지 단계를 완료하십시오.

3. 왼쪽 창의 구성 트리에서 **Invoice 모델 매핑 Litware** 를 선택합니다.
4. 작업 창에서 **디자이너** 를 선택합니다.
5. **데이터 소스 매핑에 대한 모델** 페이지에서 **편집** 을 선택하여 필요에 따라 페이지를 편집 가능하게 만듭니다.
6. **프로젝트 송장 복사** 모델 매핑을 선택한 다음 **삭제됨** 확인란을 선택합니다.

    ![Model to datasource mapping(모델-데이터 소스 매핑) 페이지에서 모델 매핑을 가상 삭제로 설정합니다.](./media/er-multiple-model-mappings-image9.png)

    이 설정 때문에 **Invoice 모델 매핑 Litware** 구성은 **InvoiceProject** 루트 정의에 대한 모델 매핑이 없는 것처럼 처리됩니다. 기본적으로 발행된 **InvoiceProject Copy** 모델 매핑입니다. 이 모델 매핑을 포함하는 구성인 **프로젝트 송장 모델 매핑 Litware** 가 기본 구성으로 표시됩니다. 기본값으로 표시되기 때문에 **프로젝트 송장 모델 매핑(RDP)** 구성의 **InvoiceProject** 모델 매핑보다 우선 순위가 높습니다.

## <a name="other-considerations"></a>기타 고려 사항

**프로젝트 송장 모델 매핑** 의 **InvoiceProject 복사** 모델 매핑 Litware 구성은 **ReportDataProvider** 데이터 소스를 사용하도록 설계되었습니다. 데이터 소스는 **PsaProjInvoiceDP** 애플리케이션 클래스를 참조하는 *개체* 유형의 일부입니다. 이 클래스는 인쇄 관리 프레임워크의 프로젝트 송장 SQL Server Reporting Services(SSRS) 보고서에 대한 데이터 공급자로 구현됩니다. 이 데이터 소스를 ER [통합 포인트](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents)로 선택하십시오. 인쇄 관리 보고서에 대한 현재 ER 구현은 이 설정을 고려합니다. 자세한 내용은 **ERPrintMgmtDataProviderReport** 애플리케이션 클래스의 소스 코드를 검토하십시오. 런타임 시 **ReportDataProvider** 데이터 소스를 모델 매핑 통합 지점으로 지정하면 Finance에서 이 매핑 구성 요소를 **프로젝트 송장 모델 매핑(RDP)** 구성의 **InvoiceProject** 매핑 구성 요소보다 높은 우선 순위로 처리합니다.

## <a name="see-also"></a>또한, 다음을 참조하십시오.

- [별도의 ER 구성에서 ER 모델 매핑 관리](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [국가 컨텍스트 종속 ER 모델 매핑 구성](er-country-dependent-model-mapping.md)
- [전자 보고 프레임워크 API 변경](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
