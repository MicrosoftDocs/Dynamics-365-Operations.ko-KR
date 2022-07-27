---
title: 프로덕션 작업자를 위한 혼합 현실 가이드 제공
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management의 생산 관리 모듈을 Dynamics 365 Guides와 통합하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "61943"
- intro-internal
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 703f2cb9a1ea8691420765a8598d59f3e6cc6488
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449854"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>프로덕션 작업자를 위한 혼합 현실 가이드 제공

[!include [banner](../includes/banner.md)]


생산 프로세스의 작업자는 작업 맥락에서 적시에 제공되는 관련 지침의 이점을 누릴 수 있습니다. *지침* 조립, 서비스, 운영, 인증 및 안전을 포함한 여러 작업 도메인에 적용됩니다. 이러한 모든 핵심 비즈니스 기능에 걸쳐 지속적인 교육 지침을 통해 근로자가 더 많은 것을 성취하고 더 잘 일할 수 있습니다.

## <a name="introduction"></a>소개

다양한 방법으로 지침을 제공할 수 있습니다. 기본적으로 제공되는 하나의 효율적인 시스템은 [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/)를 사용합니다.

Dynamics 365 Guides는 실습 학습을 통해 직원의 역량을 강화하는 데 도움이 될 수 있습니다. 직원에게 필요한 도구와 부품을 안내하고 직원들에게 실제 작업 상황에서 이러한 도구를 사용하는 방법을 보여주는 단계별 지침으로 표준화된 프로세스를 정의할 수 있습니다.

다음을 포함하여 생산 관리의 다양한 측면에 가이드를 첨부할 수 있습니다.

- [리소스](#resources)
- [리소스 그룹](#resource-groups)
- [출시된 제품](#released-products)
- [공식](#formulas)
- [공식 버전](#formula-versions)
- [BOM(모든 자재 명세서)](#bom)
- [BOM 버전](#bom-versions)
- [경로](#routes)
- [경로 버전](#route-versions)
- [경로 작업 관계](#route-operation-relations)

> [!NOTE]
> 자산 관리에 Guides를 첨부할 수도 있습니다. 해당 옵션에 대한 자세한 내용은 [Dynamics 365 Supply Chain Management(자산 관리)를 Dynamics 365 Guides와 통합](../asset-management/asset-management-guides-integration.md)을 참조하세요.

일선 작업자가 Supply Chain Management를 통해 작업 현장에서 작업을 선택하면 작업자는 작업 카드에서 [관련 가이드](#logic)를 볼 수 있습니다. 작업자가 특정 가이드를 선택하면 해당 가이드의 QR 코드가 화면에 표시됩니다. 그런 다음 작업자는 HoloLens를 사용하여 QR 코드를 스캔하면 Guides가 시작되고 필요한 지침이 표시됩니다.

다음 하위 섹션에서는 여러 업계의 회사가 Guides를 사용하여 제조 지침을 제시할 때 가장 큰 가치를 볼 수 있는 몇 가지 선택된 시나리오에 대해 설명합니다.

### <a name="assembly"></a>어셈블리

![어셈블리 작업에서 Guides를 사용하세요.](media/instruction-guides-hero-assembly.png "서비스 작업에서 가이드 사용")

어셈블리 작업의 지침은 작업자에게 필요한 도구와 부품과 실제 작업 상황에서 사용하는 방법을 보여줍니다.

생산 관리자는 예를 들어 [생산 경로](routes-operations.md), [작업 관계](routes-operations.md#operation-relations) 또는 [자재 명세서](bill-of-material-bom.md)에 대한 Guides를 만들고 할당할 수 있습니다. 작업자는 작업 현장에서 해당 작업 경험에 대한 관련 지침을 찾을 수 있습니다.

### <a name="service"></a>서비스

![서비스 작업에서 Guides를 사용하세요.](media/instruction-guides-hero-service.png "서비스 작업에서 가이드 사용")

기술자에게 작업 현장에서 안내 지침을 제공하여 추가 방문을 예약할 필요가 없습니다.

서비스 관리자는 예를 들어 품질 평가 루틴을 진행하는 특정 [제품](../../commerce/product.md)에 Guide를 할당할 수 있습니다.

### <a name="quality"></a>품질

![품질 보증 작업에서 Guides를 사용합니다.](media/instruction-guides-hero-quality.png "품질 보증 작업에서 Guides 사용")

직원 지식을 반복 가능한 도구로 전환하여 새로운 프로세스를 롤아웃하고 일관성을 높입니다.

예를 들어 품질 보증 관리자는 품질 평가 루틴을 안내하는 [제품](../../commerce/product.md)에 가이드를 할당할 수 있습니다.

### <a name="certifications"></a>인증

![인증 관련 작업에 Guides를 사용하세요.](media/instruction-guides-hero-certification.png "인증 관련 작업에 Guides 사용")

도움이 필요한 사람과 장소를 신속하게 식별하여 모든 직원이 높은 기준을 충족하도록 합니다.

### <a name="safety"></a>안전

![작업 안전 지침에서 Guides를 사용하세요.](media/instruction-guides-hero-safety.png "작업 안전 지침에서 Guides 사용")

물리적 환경에서 시도하기 전에 가상으로 위험한 절차를 안내하는 지침을 제공합니다. 혼합 현실 접근 방식을 통해 작업자는 위험한 절차를 가상으로 경험할 수 있습니다.

생산 관리자는 [제품 항목](../../commerce/product.md), [경로](routes-operations.md) 및 [작업](routes-operations.md#operation-relations)에 지침을 할당하여 위험 물질 취급 또는 섬세한 취급 절차에 대한 전용 취급 지침을 제공할 수 있습니다.

## <a name="get-started-with-instructions-and-guides"></a>지침 및 Guides 시작하기

생산 프로세스의 지침을 활성화하기 위해 Supply Chain Management는 Dynamics 365 Guides와의 즉시 사용 가능한 통합을 제공합니다. 프로덕션 자산 및 작업에 혼합 현실 지침을 빌드, 유지 관리 및 할당하려면 라이선스가 부여되고 설치된 Guides 애플리케이션 인스턴스가 필요합니다.

### <a name="prerequisites"></a>전제 조건

이 기능을 사용하려면 시스템에 다음이 포함되어 있어야 합니다.

- Dynamics 365 Supply Chain Management 버전 10.0.15 또는 이상
- Supply Chain Management 앱용 [이중 쓰기](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 버전 400.0.1.48 또는 이상

### <a name="turn-on-the-feature"></a>기능 켜기

시스템에서 기능을 사용할 수 있게 하려면 해당 구성 키를 활성화해야 합니다. 이 작업은 한 번만 수행하면 됩니다. 이렇게 하려면 관리자가 다음을 수행해야 합니다.

1. [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 시스템을 유지 관리 모드로 전환합니다.
1. **시스템 관리 \> 설정 \> 라이선스 구성** 으로 이동합니다.
1. **혼합 현실** 섹션을 확장한 다음 **혼합 현실 가이드** 확인란을 선택합니다.
1. **생산 관리** 섹션을 확장한 다음 **생산 지침** 확인란을 선택합니다.
1. [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 유지 관리 모드를 끕니다.
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Guides가 작업 현장에 표시되는 방식 구성

Guides가 작업 현장에 표시되는 방식을 구성하려면 **혼합 현실** \> Dynamics 365 Guides \> Guides 통합 구성으로 이동합니다.

![제조를 위한 Guide 통합을 구성합니다.](media/instruction-guides-configure-integration.png "제조를 위한 Guide 통합 구성")

다음 필드를 설정합니다.

- **Microsoft Dataverse** URL - Guides를 생성하는 Microsoft Dataverse 환경의 URL을 지정합니다. 형식은 "contoso.crm4.dynamics.com"입니다. 여기서 URL의 첫 번째 부분은 일반적으로 조직의 이름을 따서 지정되고(예: "contoso."), 두 번째 부분은 환경의 데이터 영역에 따라 지정됩니다(예: "crm4."), 마지막 부분은 도메인(예: "dynamics.com")입니다. 올바른 URL을 찾는 한 가지 방법은 [home.dynamics.com](https://home.dynamics.com/)으로 이동한 다음 Guides 앱을 여는 것입니다. Guides가 열리면 브라우저의 주소 표시줄에 URL이 표시됩니다(이전 예와 유사한 기본 URL만 사용). 이 값은 가이드 주소를 구성하는 데 사용되며 QR 코드로 인코딩됩니다."
- **QR 코드 크기** - 렌더링된 QR 코드의 크기를 설정합니다. 디스플레이 화면의 대부분을 채우지만 그 이상은 채우지 않는 크기를 선택하는 것이 좋습니다. 일반적으로 *15* 가 좋은 값입니다.
- **QR 코드 오류 수정 수준** - QR코드의 세분성을 설정합니다. 더 높은 세분성은 코드의 신뢰성을 높이는 데 도움이 될 수 있지만 **QR 코드 크기** 는 선택한 수정 수준에 필요한 세부 수준을 지원할 만큼 충분히 커야 합니다.

> [!TIP]
> - 디스플레이에 너무 큰 QR 코드 크기는 렌더링하는 데 시간이 조금 더 오래 걸리고 디스플레이에 맞게 축소됩니다. 이는 이점을 제공하지 않습니다.
> - QR 코드 크기가 너무 작으면 일부 환경에서 HoloLens가 코드를 제대로 읽는 기능이 저하될 수 있습니다.
> - HoloLens 사용자의 QR 코드를 표시할 각 디바이스에 대한 설정을 테스트하는 것이 좋습니다. 작업 현장 환경에서 충분한 가독성을 제공하는 설정을 선택하세요.  

## <a name="get-an-overview-of-all-guide-assignments"></a>모든 Guide 할당에 대한 개요 보기

**모든 가이드** 페이지를 사용하여 조직에서 사용 가능한 모든 가이드 목록과 생산 프로세스 및 리소스에 대한 모든 할당을 확인합니다. 열려면 **혼합 현실 \> Guides \> 모든 가이드** 로 이동하세요. 상단의 목록에는 사용 가능한 모든 가이드가 표시되며 여기에서 필드를 사용하여 목록을 필터링할 수 있습니다. 하단의 목록은 모든 Guide 할당을 보여주고 관리를 위한 도구 모음을 제공합니다.

![Guides를 관리합니다.](media/instruction-guides-allguides.png "Guides 관리")

다음 섹션에서는 Guides를 할당할 수 있는 개체 유형에 대해 설명합니다. 할당된 각 가이드는 해당 생산 작업에 자동으로 첨부되어 작업 현장에서 사용할 수 있는 지침을 제공합니다.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>리소스에 가이드 연결

관련 생산 작업의 맥락에서 가이드를 제공하기 위해 [리소스](operations-resources.md)에 가이드를 추가합니다.

### <a name="typical-scenario-using-resources"></a>리소스를 사용하는 일반적인 시나리오

예를 들어, 일반적인 기계 보안 또는 취급 지침이 있는 가이드를 기계 유형의 리소스에 첨부할 수 있습니다. 그러면 기계에서 수행되는 모든 작업에 대해 가이드를 사용할 수 있습니다.

### <a name="add-a-guide-to-a-resource"></a>리소스에 가이드 추가

리소스에 가이드 추가:

1. **생산 관리 \> 설정 \> 리소스 \> 리소스** 로 이동합니다.
1. 목록 창에서 가이드를 할당할 리소스를 선택합니다.
1. **관련된 Guides** 빠른 탭을 확장합니다.
1. **연결된 Guides** 도구 모음에서 **추가** 를 선택합니다. 새 라인이 그리드에 추가됩니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다. Guides가 많은 경우 목록을 필터링하여 원하는 가이드를 찾을 수 있습니다.
    ![Guides를 관리합니다.](media/instruction-guides-allguides.png "Guides 관리")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>리소스 그룹에 가이드 연결

기계, 생산 라인 또는 작업 셀 그룹을 관리하는 데 [리소스 그룹](tasks/define-discrete-manufacturing-resource-group.md)을 사용하는 경우 리소스 그룹에 가이드를 추가할 수 있습니다.

### <a name="typical-scenarios-using-resource-groups"></a>리소스 그룹을 사용하는 일반적인 시나리오

**예시 1:** 동일한 모델의 여러 시스템에 대한 리소스 그룹을 정의했습니다. 머신 모델에 대한 관련 처리 지침 가이드를 모든 관련 리소스에 할당하는 대신 해당 머신 모델을 반영하는 리소스 그룹에 가이드를 할당할 수 있습니다.

**예시 2:** 다른 기계가 포함된 작업 셀에 대한 자원 그룹을 정의했으며 작업 셀을 유지 관리하는 방법에 대한 일반 지침을 제공하는 안내서가 있습니다. 이 가이드는 이 작업 셀의 모든 생산 활동에 적용됩니다.

### <a name="add-a-guide-to-a-resource-group"></a>리소스 그룹에 가이드 추가

리소스 그룹에 가이드를 추가하려면:

1. **생산 관리 \> 설정 \> 리소스 \> 리소스 그룹** 으로 이동합니다.
1. 목록 창에서 가이드를 할당할 리소스 그룹을 선택합니다.
1. **관련된 Guides** 빠른 탭을 확장합니다.
1. **연결된 Guides** 도구 모음에서 **추가** 를 선택합니다. 새 라인이 그리드에 추가됩니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다. Guides가 많은 경우 목록을 필터링하여 원하는 가이드를 찾을 수 있습니다.
    ![리소스 그룹에 가이드 추가.](media/instruction-guides-resourcegroup.png "리소스 그룹에 가이드 추가")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>출시된 제품에 가이드 연결

[출시된 제품](../pim/tasks/create-released-product-single-company.md)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-released-products"></a>출시된 제품을 사용하는 일반적인 시나리오

제품 수준 가이드는 출시된 특정 제품이나 품목의 작동 또는 취급과 관련된 지침으로 작업 현장 작업자를 돕습니다.

### <a name="add-a-guide-to-a-released-product"></a>출시된 제품에 가이드 추가

출시된 제품에 가이드를 추가하려면:

1. **생산 정보 관리 \> 제품 \> 출시된 제품** 으로 이동합니다.
1. 가이드를 할당할 제품을 엽니다.
1. 작업 창에서 **엔지니어** 탭을 열고 **보기** 그룹에서 **관련 가이드** 를 선택합니다.
1. **선택한 제품** 에 대한 관련 안내서 페이지가 열립니다.
1. 작업 창에서 **추가** 를 선택하여 그리드에 새 줄을 추가합니다. 
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![출시된 제품에 가이드 추가.](media/instruction-guides-ReleasedProduct-AddGuides.png "출시된 제품에 가이드 추가")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>공식에 가이드 연결

[공식](bill-of-material-bom.md#formulas-co-products-and-by-products)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-formulas"></a>공식을 사용하는 일반적인 시나리오
  
공식 수준 가이드는 공식 또는 레시피의 맥락에서 작업 현장 작업자에게 안내 처리 지침을 제공합니다. 가이드는 공식에 할당할 수도 있습니다.

> [!NOTE]
> 루트, 루트 버전 또는 루트 운영 관계에 공식을 기반으로 생산 프로세스와 관련된 지침을 할당할 수 있습니다.  

> 가이드는 현재 개별 공식 라인에 첨부할 수 없습니다.

### <a name="add-a-guide-to-a-formula"></a>공식에 가이드 추가

공식에 가이드를 추가하려면:

1. **생산 정보 관리 \> 자재 명세서 및 공식 버전 \> 공식** 으로 이동합니다.
1. 가이드를 할당할 공식을 엽니다.
1. 상단 빠른 탭 위에 있는 **헤더** 탭을 엽니다.
1. **관련된 Guides** 빠른 탭을 확장합니다.
1. **연결된 Guides** 도구 모음에서 **추가** 를 선택합니다. 새 라인이 그리드에 추가됩니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![공식에 가이드를 추가.](media/instruction-guides-Formula.png "공식에 가이드를 추가")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>공식 버전에 가이드 연결

[공식 버전](bill-of-material-bom.md#bom-and-formula-versions)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-formula-versions"></a>공식 버전을 사용하는 일반적인 시나리오

공식의 개별 버전에 첨부된 가이드는 작업 현장 작업자에게 공식 레시피의 해당 버전을 생산하는 과정을 안내하는 지침을 제공합니다.

> [!TIP]
> 이 공식 버전을 기반으로 생산 프로세스와 관련된 지침을 경로, 경로 버전 또는 경로 운영 관계에 할당할 수 있습니다.  

> [!NOTE]
> 가이드는 현재 개별 공식 라인에 첨부할 수 없습니다.

### <a name="add-a-guide-to-a-formula-version"></a>공식 버전에 가이드 추가

공식 버전에 가이드를 추가하려면:

1. **생산 정보 관리 \> 자재 명세서 및 공식 버전 \> 공식** 으로 이동합니다.
1. 가이드를 할당할 버전이 포함된 공식을 엽니다.
1. 상단 빠른 탭 위에 있는 **헤더** 탭을 엽니다.
1. **공식 버전** 빠른 탭에서 가이드를 할당할 버전을 선택합니다.
1. **공식 버전** 도구 모음에서 **관련 가이드** 를 선택합니다.
    ![선택한 공식 버전과 관련 가이드를 엽니다.](media/instruction-guides-FormulaVersion.png "선택한 공식 버전과 관련 가이드 열기")
1. **공식 버전** 에 대한 관련 안내서 페이지가 열립니다.
1. 작업 창에서 **추가** 를 선택하여 그리드에 새 줄을 추가합니다. 
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![공식 버전에 가이드 추가.](media/instruction-guides-FormulaVersionAddGuide.png "공식 버전에 가이드 추가")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>자재 명세서에 가이드 연결

모든 BOM([자재 명세서](bill-of-material-bom.md))에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-bills-of-materials"></a>자재 명세서를 사용하는 일반적인 시나리오

자재 명세서에 첨부된 가이드는 작업 현장 작업자에게 BOM에서 재료를 준비하고 처리하는 방법을 설명하는 지침을 제공합니다. 안내선은 BOM에 할당할 수도 있습니다.

> [!NOTE]
> 가이드는 현재 개별 BOM 라인에 첨부할 수 없습니다.

### <a name="add-a-guide-to-a-bill-of-materials"></a>자재 명세서에 가이드 추가

자재 명세서에 가이드를 추가하려면:

1. **생산 정보 관리 \> 자재 명세서 및 공식 \> 자제 명세서** 로 이동합니다.
1. Guide를 할당할 자재 명세서를 엽니다.
1. 상단 빠른 탭 위에 있는 **헤더** 탭을 엽니다.
1. **관련된 Guides** 빠른 탭을 확장합니다.
1. **연결된 Guides** 도구 모음에서 **추가** 를 선택합니다. 새 라인이 그리드에 추가됩니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![BOM에 가이드를 추가.](media/instruction-guides-BOM.png "BOM에 가이드를 추가")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>자재 명세서 버전에 가이드 연결

모든 [자재 명세서 버전](bill-of-material-bom.md#bom-and-formula-versions)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-bill-of-materials-versions"></a>자재 명세서 버전을 사용하는 일반적인 시나리오

개별 BOM 버전에 첨부된 가이드는 작업 현장 작업자에게 일반 BOM 또는 다른 버전의 BOM과 다른 버전의 재료를 준비하고 처리하는 방법을 설명하는 지침을 제공합니다.

> [!NOTE]
> 가이드는 현재 개별 BOM 라인에 첨부할 수 없습니다.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>자재 명세서 버전에 가이드 추가

자재 명세서 버전에 가이드를 추가하려면:

1. **생산 정보 관리 \> 자재 명세서 및 공식 \> 자제 명세서** 로 이동합니다.
1. 가이드를 할당할 버전이 포함된 BOM을 엽니다.
1. 상단 빠른 탭 위에 있는 **헤더** 탭을 엽니다.
1. **BOM 버전** 빠른 탭에서 가이드를 할당할 버전을 선택합니다.
1. **BOM 버전** 도구 모음에서 **관련 가이드** 를 선택합니다.
    ![선택한 BOM 버전과 관련 가이드를 엽니다.](media/instruction-guides-BOMVersion.png "선택한 BOM 버전과 관련 가이드 열기")
1. **BOM 버전** 에 대한 관련 가이드 페이지가 열립니다.
1. 작업 창에서 **추가** 를 선택하여 그리드에 새 줄을 추가합니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![BOM 버전에 가이드 추가.](media/instruction-guides-BOMVersionAddGuide.png "BOM 버전에 가이드 추가")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>경로에 가이드 연결

[경로](routes-operations.md)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-routes"></a>경로를 사용하는 일반적인 시나리오

경로는 일반적으로 BOM 또는 BOM 버전 및 리소스 또는 리소스 그룹 집합을 기반으로 릴리스된 특정 제품을 생산하는 방법을 지정하는 데 사용됩니다.

각 생산 프로세스에 대한 단계별 지침을 제공하기 위해 경로에 가이드를 할당합니다.

### <a name="add-a-guide-to-a-route"></a>경로에 가이드 추가

경로에 가이드를 추가하려면:

1. **생산 관리 \> 모든 경로** 로 이동합니다.
1. 가이드를 할당할 경로를 엽니다.
1. **관련된 Guides** 빠른 탭을 확장합니다.
1. **연결된 Guides** 도구 모음에서 **추가** 를 선택합니다. 새 라인이 그리드에 추가됩니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![경로에 가이드를 추가.](media/instruction-guides-Route.png "경로에 가이드를 추가")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>경로 버전에 가이드 연결

[경로 버전](routes-operations.md#route-versions)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-route-versions"></a>경로 버전을 사용하는 일반적인 시나리오

경로 버전은 일반적으로 기존 경로를 기반으로 하는 생산 프로세스의 변형을 지정하는 데 사용됩니다. 각 경로 버전에 다른 가이드를 할당할 수 있습니다.

### <a name="add-a-guide-to-a-route-version"></a>경로 버전에 가이드 추가

경로 버전에 가이드를 추가하려면:

1. **생산 관리 \> 모든 경로** 로 이동합니다.
1. 가이드를 할당할 경로를 엽니다.
1. **버전** 빠른 탭에서 가이드를 할당할 버전을 선택합니다.
1. **버전** 도구 모음에서 **관련 가이드** 를 선택합니다.
    ![선택한 경로 버전과 관련 가이드를 엽니다.](media/instruction-guides-RouteVersion.png "선택한 경로 버전과 연결된 가이드 염")
1. **BOM 버전** 에 대한 관련 가이드 페이지가 열립니다.
1. 작업 창에서 **추가** 를 선택하여 그리드에 새 줄을 추가합니다.
1. 새 라인의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다.
    ![경로 버전에 가이드 추가.](media/instruction-guides-RouteVersionAddGuide.png "경로 버전에 가이드 추가")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>경로 작업 관계에 가이드 연결

[경로 작업 관계](routes-operations.md#operation-relations)에 가이드를 추가할 수 있습니다.

### <a name="typical-scenario-using-route-operation-relations"></a>경로 작업 관계를 사용하는 일반적인 시나리오

작업 관계는 제품 프로세스 및 관련 작업에 지침을 추가하는 가장 구체적인 방법입니다. 경로의 각 작업에 대한 지침을 지정하고 특정 항목, 구성 등과 같이 경로에 지정된 모든 유형의 관계 컨텍스트에 대해 다른 지침을 지정할 수 있습니다. 지침이 적용되는 작업 단계(예: 설정, 대기열, 프로세스 또는 전송)를 지정할 수도 있습니다.

> [!NOTE]
> 경로의 여러 작업 관계에 대한 안내를 지정하면 해당 안내 중 가장 구체적인 관계의 안내만 생성된 작업에 대한 작업 현장에 표시됩니다.

### <a name="add-a-guide-to-a-route-operation-relation"></a>경로 작업 관계에 가이드 추가

경로 작업 관계에 가이드를 추가하려면:

1. **생산 관리 \> 모든 경로** 로 이동합니다.
1. 가이드를 할당할 경로를 엽니다.
1. 작업 창에서 **경로** 탭을 열고 **유지 관리** 그룹에서 **경로 세부 정보** 를 선택합니다.
1. 선택한 경로에 대한 **경로 세부 정보** 페이지가 열립니다.
1. 상단 그리드에서 지침을 제공할 작업을 선택합니다.
1. 하단 그리드에서 특정 관계(또는 일반 **모든** 관계)를 선택합니다.
    ![작업을 선택한 다음 관계를 선택합니다.](media/instruction-guides-RouteOperationRelation.png "작업을 선택한 다음 관계 선택")
1. 하단 격자 위에서 **관련 가이드** 탭을 엽니다. ![관련 가이드 탭.](media/instruction-guides-RouteOperationRelation-AddGuide.png "연결된 가이드 탭")
1. 하단 그리드 상단의 도구 모음에서 **추가** 를 선택하여 그리드에 새 라인을 추가합니다.
1. 새 행의 경우 **이름** 열의 드롭다운 목록을 사용하여 할당하려는 가이드를 선택합니다. 행의 나머지 부분에서 선택한 가이드를 사용할 수 있어야 하는 각 컨텍스트에 대한 확인란을 선택합니다.

> [!NOTE]
> 각 작업의 각 단계에 대해 하나 이상의 가이드를 추가할 수 있습니다.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>작업 현장 실행 인터페이스에서 가이드 선택

작업자가 작업 현장 실행 인터페이스에서 작업 목록을 열면 Supply Chain Management는 표시된 작업에 대한 관련 가이드를 찾습니다. **가이드** 버튼을 사용하여 관련 가이드를 봅니다.

![작업 현장 실행 인터페이스의 가이드 버튼.](media/instruction-guides-Shopfloor1.png "작업 현장 실행 인터페이스의 가이드 버튼")

그런 다음 HoloLens를 착용하고 QR 코드를 보고 해당 가이드를 활성화하여 해당 가이드에 액세스합니다.

![HoloLens를 사용하여 가이드에 액세스하는 QR 코드.](media/instruction-guides-Shopfloor2.png "HoloLens를 사용하여 가이드에 액세스하는 QR 코드")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>가이드 선택 논리 해결

다음 프로덕션 데이터에 가이드를 추가할 수 있습니다.

- [리소스](#resources)
- [리소스 그룹](#resource-groups)
- [출시된 제품](#released-products)
- [수식](#formulas)
- [수식 버전](#formula-versions)
- [BOM(모든 자재 명세서)](#bom)
- [BOM 버전](#bom-versions)
- [경로](#routes)
- [경로 버전](#route-versions)
- [경로 작업 관계](#route-operation-relations)

Supply Chain Management가 생산 현장에 대한 작업을 생성할 때 해당 소스에서 관련 가이드를 수집합니다. 다음의 중요한 규칙에 유의하세요.

- BOM 버전 또는 공식 버전을 경로 또는 생산 주문에 첨부하면 이 버전에 첨부된 모든 가이드와 상위 BOM 또는 해당 버전의 공식에 첨부된 가이드가 작업에 표시됩니다.
- 생산 주문에 경로 버전을 첨부하면 이 버전에 첨부된 모든 가이드와 해당 버전의 상위 라우트에 첨부된 가이드가 작업에 표시됩니다.
- *모두* 관계를 포함하는 여러 루트 작업 관계를 정의하고 여기에 Guide를 할당하면 가장 구체적인 관계의 Guide만 작업에 대해 표시됩니다.  

![관련 가이드 해결에 대한 다이어그램.](media/instruction-guides-Resolve.png "관련 가이드 해결에 대한 다이어그램.")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]