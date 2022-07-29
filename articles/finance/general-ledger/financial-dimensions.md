---
title: 재무 차원
description: 이 항목에서는 다양한 유형의 재무 차원과 설정 방법을 설명합니다.
author: aprilolson
ms.date: 01/03/2019
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 9d5de5b58f0d498c4766659671d43fdb216cd6a870345509505b5a6bc19bdd4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450565"
---
# <a name="financial-dimensions"></a>재무 차원

[!include [banner](../includes/banner.md)]

이 항목에서는 다양한 유형의 재무 차원과 설정 방법을 설명합니다.

계정 차트의 계정 세그먼트로 사용할 수 있는 재무 차원을 만들려면 **재무 차원** 페이지를 사용합니다. 재무 차원에는 사용자 지정 차원과 엔터티 지원 차원의 두 가지 유형이 있습니다. 사용자 지정 차원은 법인 간에 공유되며 사용자가 값을 입력하고 유지 관리합니다. 엔터티 지원 차원은 고객 또는 상점 엔터티와 같이 시스템의 다른 곳에서 값을 정의합니다. 일부 엔터티 지원 차원은 법인 간에 공유되지만 다른 엔터티 지원 차원은 회사별로 다릅니다.

재무 차원을 만든 후 각 재무 차원에 추가 속성을 할당하려면 **재무 차원 값** 페이지를 사용합니다.

재무 차원을 사용하여 법인을 나타낼 수 있습니다. Dynamics 365 Finance에서 법인을 만들 필요가 없습니다. 그러나 재무 차원은 법인의 운영이나 비즈니스 요구 사항을 해결하도록 설계되지 않았습니다. Finance의 단위 간 회계 기능은 각 거래로 생성된 회계 항목만 처리하도록 설계되었습니다.

재무 차원을 법인으로 설정하기 전에 다음 영역에서 비즈니스 프로세스를 평가하여 이 설정이 조직에 적합한지 결정하세요.

- 인벤토리
- 재무 차원 및 법인 간 판매 및 구매
- 판매세 계산 및 보고
- 운영 보고

다음은 제한 중 일부입니다.

- 판매세 기능은 재무 차원이 아닌 법인에만 사용할 수 있습니다.
- 일부 보고서에는 재무 차원이 포함되지 않습니다. 따라서 재무 차원을 보고하려면 보고서를 수정해야 할 수 있습니다.

## <a name="custom-dimensions"></a>사용자 지정 차원

사용자 정의 재무 차원을 만들려면 **다음 값 사용** 필드에서 **사용자 지정 차원** 을 선택합니다.

계정 마스크를 지정하여 차원 값에 입력될 수 있는 정보의 양과 유형을 제한할 수도 있습니다. 문자나 하이픈(-)과 같이 각 차원 값에 대해 동일한 문자를 입력할 수 있습니다. 또한 숫자 기호(\#)와 앰퍼샌드(&)를 차원 값이 생성될 때마다 변경되는 문자의 자리 표시자로 입력할 수 있습니다. 숫자의 자리 표시자로 숫자 기호(\#)를 사용하고 문자의 자리 표시자로 앰퍼샌드(&)를 사용합니다. 형식 마스크에 대한 필드는 **다음 값 사용** 필드에서 **사용자 지정 차원** 을 선택해야 사용할 수 있습니다.

**예**

차원 값을 문자 "CC"와 숫자 3개로 제한하려면 형식 마스크로 **CC-\#\#\#** 을 입력합니다.

## <a name="entity-backed-dimensions"></a>엔터티 지원 차원

엔터티 지원 재무 차원을 만들려면 **다음 값 사용** 필드에서 재무 차원의 기반이 될 시스템 정의 엔터티를 선택합니다. 그런 다음 해당 엔터티에서 재무 차원 값이 생성됩니다. 예를 들어 프로젝트에 대한 차원 값을 만들려면 **프로젝트** 를 선택합니다. 그런 다음 프로젝트 이름별로 차원 값이 생성됩니다. **재무 차원 값** 페이지는 엔터티의 값을 보여줍니다. 해당 값이 회사별로 지정된 경우 페이지에 회사도 표시됩니다.

## <a name="activating-dimensions"></a>차원 활성화

재무 차원을 활성화하면 재무 차원의 이름을 포함하도록 테이블이 업데이트됩니다. 삭제된 차원은 제거됩니다. 재무 차원을 활성화하기 전에 차원 값을 입력할 수 있습니다. 그러나 재무 차원은 활성화하기 전에는 어디에서도 사용할 수 없습니다. 예를 들어 재무 차원이 활성화될 때까지 계정 구조에 재무 차원을 추가할 수 없습니다. **활성화** 를 선택하면 모든 차원이 업데이트되고 상태 변경이 표시됩니다.

## <a name="translations"></a>번역

**텍스트 번역** 페이지에서 선택한 재무 차원에 대한 텍스트를 다양한 언어로 입력할 수 있습니다. **주 계정 번역** 페이지에서 주 계정에 대한 텍스트를 다양한 언어로 입력할 수 있습니다. 

## <a name="legal-entity-overrides"></a>법인 재정의

모든 차원이 모든 법인에 유효한 것은 아닙니다. 또한 일부 차원은 특정 기간에만 연관될 수 있습니다. 이럴 때 **법인 재정의** 섹션을 사용하여 차원을 일시 중단해야 하는 회사, 소유자 및 차원 활성화 기간을 지정할 수 있습니다.

## <a name="deleting-financial-dimensions"></a>재무 차원 삭제

데이터의 참조 무결성을 유지하기 위해 재무 차원은 거의 삭제할 수 없습니다. 재무 차원을 삭제하려고 하면 다음 기준이 평가됩니다.

- 게시되거나 게시되지 않은 거래 또는 모든 유형의 차원 값 조합에 재무 차원이 사용되었습니까?
- 활성 계정 구조, 고급 규칙 구조 또는 재무 차원 집합에 재무 차원이 사용됩니까?
- 재무 차원이 기본 재무 차원 통합 형식의 일부입니까?
- 재무 차원이 기본 차원으로 설정되었습니까?

기준 중 하나라도 충족되면 재무 차원을 삭제할 수 없습니다.

## <a name="default-dimension-values"></a>기본 차원 값

고객 및 공급업체와 같은 마스터 레코드의 값을 새 차원의 기본값으로 사용할 수 있습니다. 새 차원이 생성되면 마스터 레코드 ID가 해당 마스터 레코드의 차원 값에 입력됩니다. 예를 들어 새 고객을 만들 때 고객 ID가 고객 차원에 입력됩니다. 고객 ID가 필요한 판매 주문, 송장 또는 기타 문서를 만들 때 기존 기본값 설정 규칙이 사용되며 고객 ID가 문서에 추가됩니다.

이 기능은 차원의 설정으로 제어됩니다. 이 설정의 이름은 **새 DimensionName이 생성될 때마다 이 차원에 값 복사** 입니다. 여기서 **DimensionName** 은 차원의 이름입니다. 기본적으로 이 기능은 꺼져 있습니다. 그러나 언제든지 켤 수 있습니다.

차원에 대한 레코드가 이미 있는 경우 기능을 켜면 마스터 레코드가 업데이트됩니다. 그러나 기존 문서 및 거래는 업데이트되지 않습니다.

템플릿을 사용하여 마스터 레코드를 만들려면 마스터 차원에 대한 템플릿 값이 비어 있는지 확인합니다. 예를 들어 템플릿에서 고객을 만들려면 템플릿의 고객 차원이 비어 있는지 확인합니다. 고객 차원 값은 새 고객을 만들 때 새 고객 번호의 기본값이 됩니다.  

## <a name="derived-dimensions"></a>파생 차원

문서에 해당 차원을 입력할 때 다른 차원에 대한 정보가 자동으로 입력되도록 차원을 구성할 수 있습니다. 예를 들어 비용 센터 10을 입력하면 부서 차원에 값 **20** 이 자동으로 입력될 수 있습니다.

차원 페이지에서 파생된 값을 설정할 수 있습니다.

1. 차원을 선택한 다음 **파생 차원** 을 선택합니다.

    **파생 차원** 페이지에는 그리드가 포함됩니다. 선택한 차원 세그먼트는 이 그리드의 첫 번째 열입니다.

2. 파생될 세그먼트를 추가합니다. 각 세그먼트는 열로 표시됩니다.

첫 번째 열의 차원에서 파생될 차원 조합을 입력합니다. 예를 들어 비용 센터를 부서 및 위치가 파생된 차원으로 사용하려면 비용 센터 10, 부서 20 및 위치 30을 입력합니다. 그런 다음 마스터 레코드나 거래 페이지에 비용 센터 10을 입력하면 기본적으로 부서 20과 위치 30이 입력됩니다.

### <a name="overriding-existing-values-with-derived-dimensions"></a>파생 차원으로 기존 값 재정의
 
기본적으로 파생 차원 프로세스는 파생 차원의 기존 값을 재정의하지 않습니다. 예를 들어 비용 센터 10을 입력하고 다른 차원을 입력하지 않으면 기본적으로 부서 20과 위치 30이 입력됩니다. 그러나 비용 센터를 변경해도 이미 설정된 값은 변경되지 않습니다. 따라서 마스터 레코드에 기본 차원을 설정할 수 있으며 이러한 차원은 파생 차원에 의해 변경되지 않습니다.

**파생 차원** 페이지에서 **기존 차원 값을 파생 값으로 바꾸기** 확인란을 선택하면 파생 차원의 동작을 변경하여 기존 값을 재정의할 수 있습니다. 이 필드를 선택하면 파생된 차원 값이 있는 차원을 입력하고 파생된 차원 값으로 이미 존재하는 모든 값을 재정의할 수 있습니다. 이전 예제에서 비용 센터 10을 입력하고 다른 차원을 입력하지 않으면 기본적으로 부서 20과 위치 30이 입력됩니다. 그러나 값이 이미 부서 50 및 위치 60인 경우 값이 부서 20 및 위치 30으로 변경됩니다.
 
이 설정이 있는 파생 차원은 차원 값이 기본값일 때 기존 기본 차원 값을 자동으로 바꾸지 않습니다. 차원 값은 페이지에 새 차원 값을 입력하고 페이지에 해당 차원의 기존 파생 값이 있는 경우에만 재정의됩니다.

### <a name="preventing-changes-with-derived-dimensions"></a>파생 차원으로 변경 방지
 
**파생 차원 페이지** 에서 **세그먼트 추가** 를 사용하여 세그먼트를 파생 차원으로 추가하면 **세그먼트 추가** 페이지 하단에 페이지에서 파생될 때 해당 차원의 변경을 방지하는 옵션이 제공됩니다. 파생 차원 값이 변경되는 것을 방지하지 않도록 기본 설정은 꺼져 있습니다. 차원이 파생된 후 변경되지 않도록 하려면 설정을 **예** 로 변경합니다. 예를 들어 부서 차원의 값이 비용 센터 차원의 값에서 파생된 경우 **변경 방지** 설정이 **예** 이면 부서 값을 변경할 수 없습니다. 
 
차원 값이 유효한 경우 설정이 변경을 방지하지 않지만 파생 차원 목록에 나열되지 않습니다. 예를 들어 부서 20이 비용 센터 10에서 파생되고 비용 센터 10을 입력하면 부서 20을 편집할 수 없습니다. 그러나 비용 센터 20을 입력하고 비용 센터에 대한 파생 차원 목록에 없으면 부서 값을 편집할 수 있습니다. 
 
모든 경우에 계정 값과 모든 차원 값은 파생 차원 값이 적용된 후에도 계정 구조에 대해 계속 검증됩니다. 파생 차원을 사용하고 페이지에 사용될 때 유효성 검사에 실패하는 경우 파생 차원 페이지에서 파생 차원 값을 변경해야 거래에 사용할 수 있습니다. 
 
**재무 차원** 빠른 탭에서 차원을 변경할 때 변경 방지로 표시된 차원은 편집할 수 없습니다. 페이지의 세그먼트 입력 컨트롤에 계정 및 차원을 입력하면 차원을 편집할 수 있습니다. 그러나 세그먼트 입력 컨트롤에서 강조 표시를 옮겨서 다른 필드로 이동하거나 작업을 수행하면 적절한 값을 입력했는지 확인하기 위해 파생된 차원 목록 및 계정 구조에 대해 계정 및 차원의 유효성이 검사됩니다. 

### <a name="derived-dimensions-and-entities"></a>파생 차원 및 엔터티

엔터티를 사용하여 파생 차원 세그먼트 및 값을 설정할 수 있습니다.

- 파생 차원 엔터티는 해당 차원에 사용되는 주요 차원과 세그먼트를 설정합니다.
- 파생 차원 값 엔터티를 사용하면 각 주요 차원에 대해 파생되어야 하는 값을 가져올 수 있습니다.

엔터티를 사용하여 데이터를 가져올 때 해당 엔터티가 차원을 가져오는 경우 엔터티가 해당 차원을 특별히 재정의하지 않는 한 가져오는 동안 파생 차원 규칙이 적용됩니다.

자세한 내용은 다음 항목을 참조하세요.

- [재무 차원 정의](tasks/define-financial-dimensions.md)
- [재무 차원 기본 템플릿 유지](tasks/maintain-financial-dimension-default-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]