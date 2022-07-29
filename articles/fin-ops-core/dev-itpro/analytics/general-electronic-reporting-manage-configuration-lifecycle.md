---
title: 전자 보고(ER) 구성 수명 주기 관리
description: 이 항목에서는 Dynamics 365 Finance의 전자 보고(ER) 구성 수명 주기를 관리하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8b61082cf17707c952b6e07613769a671c349bb8fa92c21e3fe8524ef62dcb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460661"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>전자 보고(ER) 구성 수명 주기 관리

[!include [banner](../includes/banner.md)]

이 항목에서는 Dynamics 365 Finance의 전자 보고(ER) 구성 수명 주기를 관리하는 방법에 대해 설명합니다.

## <a name="overview"></a>개요

전자 보고(ER)는 법적 필수 및 국가별 전자 문서를 지원하는 엔진입니다. 일반적으로 ER은 단일 전자 문서에 대해 다음 작업을 수행할 수 있는 능력을 가정합니다. 자세한 내용은 [전자 보고(ER) 개요](general-electronic-reporting.md)를 참조하세요.

- 전자 문서용 템플릿 디자인:

    - 문서에 표시할 수 있는 필수 데이터 소스를 식별합니다.

        - 데이터 테이블, 데이터 엔터티 및 클래스와 같은 기본 데이터입니다.
        - 실행 날짜 및 시간, 표준 시간대와 같은 프로세스별 속성입니다.
        - 런타임 시 최종 사용자가 지정하는 사용자 입력 매개변수.

    - 필요한 문서 요소와 해당 토폴로지를 정의하여 최종 문서 형식을 지정합니다.
    - 선택한 데이터 소스에서 정의된 문서 요소로 원하는 데이터 흐름을 구성하고(문서 형식 구성 요소에 대한 데이터 소스 바인딩을 통해) 프로세스 제어 논리를 지정합니다.

- 다른 인스턴스에서 사용할 수 있도록 템플릿을 사용 가능하게 만드세요.

    - 생성된 문서 템플릿을 ER 구성으로 변환하고 현재 애플리케이션 인스턴스의 구성을 로컬 또는 LCS(Lifecycle Services)에 저장할 수 있는 XML 패키지로 내보냅니다.
    - ER 구성을 애플리케이션 문서 템플릿으로 변환합니다.
    - 로컬 또는 LCS에 저장된 XML 패키지를 현재 인스턴스로 가져옵니다.

- 전자 문서 템플릿 사용자 지정:

    - LCS의 템플릿을 ER 구성으로 현재 인스턴스로 가져옵니다.
    - ER 구성의 사용자 지정 버전을 디자인하고 기본 버전에 대한 참조를 유지합니다.

- 애플리케이션에서 사용할 수 있도록 템플릿을 특정 비즈니스 프로세스와 통합합니다.

    - 프로세스 관련 매개변수에서 해당 구성을 참조하여 애플리케이션이 ER 구성을 사용하기 시작하도록 설정을 구성합니다. 예를 들어, 송장 처리를 위한 전자 지불 메시지를 생성하려면 특정 미지급금 지불 방법의 ER 구성을 참조하세요.

- 특정 비즈니스 프로세스에서 템플릿 사용:

    - 특정 비즈니스 프로세스에서 ER 구성을 실행합니다. 예를 들어, 송장 처리를 위한 전자 지불 메시지를 생성하기 위해 ER 구성을 참조하는 결제 방법을 선택하는 경우.

## <a name="concepts"></a>개념
다음 역할 및 관련 활동은 ER 구성 수명 주기와 연결됩니다.

| 역할                                       | 활동                                                      | 설명 |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| 전자 보고 기능 컨설턴트 | ER 구성 요소(모델 및 형식)를 만들고 관리합니다.           | ER 도메인별 데이터 모델을 설계하고 전자 문서에 필요한 템플릿을 설계하고 그에 따라 바인딩하는 비즈니스 사람입니다. |
| 전자 보고 개발자             | 데이터 모델 매핑을 만들고 관리합니다.                          | 필요한 재무 데이터 소스를 선택하고 ER 도메인 특정 데이터 모델에 바인딩하는 전문가입니다. |
| 회계 감독관                      | ER 아티팩트를 참조하는 프로세스 관련 설정을 구성합니다. | 예를 들어, **회계 감독관** 역할은 송장 처리를 위한 전자 지불 메시지를 생성하기 위해 특정 미지급금 지불 방법에서 ER 구성 설정을 사용할 수 있도록 합니다. |
| 미지급금 사무원            | 특정 비즈니스 프로세스에서 ER 아티팩트 사용.                | 예를 들어, **미지급금 사무원** 역할은 특정 결제 방법에 대해 구성된 ER 형식을 기반으로 송장 처리를 위해 전자 결제 메시지를 생성할 수 있도록 합니다. |

## <a name="er-configuration-development-lifecycle"></a>ER 구성 개발 수명 주기
다음 ER 관련 이유로 개발 환경에서 ER 구성을 재무 및 운영의 별도 인스턴스로 설계하는 것이 좋습니다.

- **전자 보고 개발자** 역할 또는 **전자 보고 기능 컨설턴트** 역할의 사용자는 구성을 편집하고 테스트 목적으로 실행할 수 있습니다. 이 시나리오는 비즈니스 데이터와 인스턴스의 성능에 해를 끼칠 수 있는 클래스 및 테이블의 메서드 호출을 유발할 수 있습니다.
- ER 구성의 ER 데이터 소스로 클래스 및 테이블의 메서드 호출은 진입점 및 기록된 회사 콘텐츠에 의해 제한되지 않습니다. 따라서 **전자 보고 개발자** 역할 또는 **전자 보고 기능 컨설턴트** 역할의 사용자는 비즈니스에 중요한 데이터에 액세스할 수 있습니다.

개발 환경에서 설계된 ER 구성은 구성 평가(적절한 프로세스 통합, 결과의 정확성, 성능) 및 역할 중심 접근 권한의 정확성 및 직무 분리와 같은 품질 보증을 위한 테스트 환경에 [업로드](#data-persistence-consideration)할 수 있습니다. 이를 위해 ER 구성 교환을 가능하게 하는 기능을 사용할 수 있습니다. 입증된 ER 구성을 LCS에 업로드하여 서비스 가입자와 공유하거나 내부 사용을 위해 프로덕션 환경으로 [가져올](#data-persistence-consideration) 수 있습니다.

![ER 구성 수명 주기.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>데이터 지속성 고려 사항

ER [구성](general-electronic-reporting.md#Configuration)의 여러 [버전](general-electronic-reporting.md#component-versioning)을 재무 인스턴스에 개별적으로 [가져올](tasks/er-import-configuration-lifecycle-services.md) 수 있습니다. 새 버전의 ER 구성을 가져오면 시스템은 이 구성의 초안 버전 내용을 제어합니다.

- 가져온 버전이 현재 Finance 인스턴스에서 이 구성의 가장 높은 버전보다 낮은 경우 이 구성의 초안 버전 내용은 변경되지 않은 상태로 유지됩니다.
- 가져온 버전이 현재 Finance 인스턴스에서 이 구성의 다른 버전보다 높은 경우 가져온 버전의 내용이 이 구성의 초안 버전으로 복사되어 마지막으로 완료된 버전을 계속 편집할 수 있습니다.

이 구성이 현재 활성화되어 있는 구성 [공급자](general-electronic-reporting.md#Provider) 소유인 경우 이 구성의 초안 버전은 **버전** 빠른 탭의 **구성** 페이지(**조직 관리** > **전자 보고** > **구성**)에서 볼 수 있습니다. 구성의 초안 버전을 선택하고 관련 ER 디자이너를 사용하여 콘텐츠를 [수정](er-quick-start2-customize-report.md#ConfigureDerivedFormat)할 수 있습니다. ER 구성의 초안 버전을 편집한 경우 해당 콘텐츠는 현재 재무 인스턴스에서 이 구성의 가장 높은 버전의 콘텐츠와 더 이상 일치하지 않습니다. 변경 사항이 손실되지 않도록 하기 위해 이 구성의 버전이 현재 Finance 인스턴스에서 이 구성의 가장 높은 버전보다 높기 때문에 가져오기를 계속할 수 없다는 오류가 표시됩니다. 이러한 일이 발생하면 예를 들어 형식 구성 **X** 가 있는 경우 **형식 'X' 버전이 완료되지 않았습니다** 오류가 표시됩니다.

초안 버전에서 도입한 변경 사항을 취소하려면 **버전** 빠른 탭의 재무에서 ER 구성의 가장 완성되었거나 공유된 버전을 선택한 다음 **이 버전 받기** 옵션을 선택합니다. 선택한 버전의 내용이 초안 버전으로 복사됩니다.

## <a name="applicability-consideration"></a>적용 가능성 고려

ER 구성의 새 버전을 설계할 때 다른 소프트웨어 구성 요소에 [종속성](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)을 정의할 수 있습니다. 이 단계는 ER 리포지토리 또는 외부 XML 파일에서 이 구성 버전의 다운로드를 제어하고 버전을 추가로 사용하기 위한 전제 조건으로 간주됩니다. ER 구성의 새 버전을 가져오려고 하면 시스템은 구성된 전제 조건을 사용하여 버전을 가져올 수 있는지 여부를 제어합니다.

경우에 따라 새 버전의 ER 구성을 가져올 때 시스템이 구성된 전제 조건을 무시하도록 요구할 수 있습니다. 가져오는 동안 시스템이 전제 조건을 무시하도록 하려면 다음 단계를 따르세요.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **가져오는 동안 제품 업데이트 및 버전 전제 조건 확인 건너뛰기** 옵션을 **네** 로 설정합니다.

    > [!NOTE]
    > 이 매개 변수는 사용자 및 회사에 따라 다릅니다.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[다른 구성 요소에 대한 ER 구성의 종속성 정의](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
