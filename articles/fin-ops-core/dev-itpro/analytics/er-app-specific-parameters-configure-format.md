---
title: 법인별로 지정된 매개 변수를 사용하도록 ER 형식 구성
description: 이번에는 법인별로 지정된 매개 변수를 사용하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 2bf4d1ecad3e25299df7c87ffa2236736ddcac300a5ded779616b25920745d7e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460703"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>법인별로 지정된 매개 변수를 사용하도록 ER 형식 구성

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>개요

설계할 많은 전자 보고(ER) 형식에서 인스턴스의 각 법인에 특정한 값 집합(예: 세금 거래를 필터링하기 위한 세금 코드 집합)을 사용하여 데이터를 필터링해야 합니다. 현재 이 유형의 필터링이 ER 형식으로 구성된 경우 법인에 종속된 값(예: 세금 코드)은 데이터 필터링 규칙을 지정하기 위해 ER 형식의 표현식에 사용됩니다. 따라서 ER 형식은 법인별로 만들어지며 필요한 보고서를 생성하려면 ER 형식을 실행해야 하는 각 법인에 대해 원본 ER 형식의 파생된 복사본을 만들어야 합니다. 파생된 각 ER 형식은 법인별 값을 가져오도록 편집해야 하며, 원래(기본) 버전이 업데이트될 때마다 다시 기반을 두고, 테스트 환경에서 내보내고, 프로덕션 사용을 위해 배포해야 하는 경우 프로덕션 환경으로 가져와야 합니다. 등등. 따라서 이러한 유형의 구성된 ER 솔루션의 유지 관리는 여러 가지 이유로 복잡하고 시간이 많이 소요됩니다.

-   법인이 많을수록 더 많은 ER 형식 구성을 유지해야 합니다.
-   ER 구성을 유지 관리하려면 비즈니스 사용자에게 ER 지식이 있어야 합니다.

ER 애플리케이션별 매개 변수 기능을 사용하면 고급 사용자가 ER 형식으로 데이터 필터링을 구성하여 추상 규칙 집합을 기반으로 할 수 있습니다. 이 규칙 세트는 ER 형식으로 사용 가능한 데이터 소스를 사용하도록 구성할 수 있습니다. 이후 비즈니스 사용자는 해당 ER 형식의 설정과 ER 형식의 데이터 소스에서 액세스할 현재 법인 데이터를 기반으로 자동 생성되는 사용자 인터페이스(UI)를 사용하여 ER 프레임워크를 넘어서는 실제 규칙을 지정할 수 있습니다. ER 형식에 대해 지정된 규칙 세트는 Dynamics 365 Finance(재무) 인스턴스의 현재 법인에서 내보낼 수 있습니다. 이후 동일한 ER 형식에 대한 규칙 집합으로 동일한 Finance 인스턴스 또는 다른 인스턴스의 다른 법인으로 가져올 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이 주제의 예를 완료하려면 다음 역할 중 하나에 대해 Finance와 동일한 테넌트에 대해 프로비저닝된 RCS(Regulatory Configuration Services) 인스턴스에 대한 액세스 권한이 있어야 합니다.

- 전자 보고 개발자
- 전자 보고 기능 컨설턴트
- 시스템 관리자

[CALCULATED FIELD 유형](er-calculated-field-type.md)의 ER 데이터 소스에 대한 매개 변수화된 호출 지원 항목의 단계를 완료하는 것이 좋습니다. 이러한 단계를 이미 완료한 경우 뒤에 나오는 **RCS로 ER 구성 가져오기** 섹션의 단계를 건너뛸 수 있습니다.

## <a name="import-er-configurations-into-rcs"></a>ER 구성을 RCS로 가져오기

다음 ER 구성을 다운로드하여 로컬에 저장합니다.

| **콘텐츠 설명**                        | **파일 이름**                                        |
|------------------------------------------------|------------------------------------------------------|
| 샘플 **ER 데이터 모델** 구성 파일    | [매개 변수화된 호출을 학습하는 모델.version.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| 샘플 **ER 메타데이터** 구성 파일      | [매개 변수화된 호출을 학습하기 위한 메타데이터.version.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| 샘플 **ER 모델 매핑** 구성 파일 | [매개 변수화된 호출을 학습하기 위한 매핑.version.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| 샘플 **ER 형식** 구성             | [매개 변수화된 호출을 학습하기 위한 형식.version.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

이후 RCS 인스턴스에 로그인합니다.

이 예시에서는 Litware, Inc 샘플 회사에 대한 구성을 생성합니다. 이 절차를 완료하기 전에 [구성 공급자 만들기](tasks/er-configuration-provider-mark-it-active-2016-11.md)의 단계를 완료하고 RCS에서 활성 항목으로 표시해야 합니다.

1.  기본 대시보드에서 **전자 보고** 를 선택합니다.
2.  **보고 구성** 을 선택합니다.
3.  데이터 모델, 메타데이터, 모델 매핑 및 형식의 순서로 이전에 다운로드한 ER 구성을 RCS로 가져옵니다. 각 ER 구성에 대해 다음 단계를 따르십시오.

    1.  **교환** 을 선택합니다.
    2.  **XML 파일에서 로드** 를 선택합니다.
    3.  **찾아보기** 를 선택하여 필요한 ER 구성에 대한 파일을 XML 형식으로 선택합니다.
    4.  **확인** 을 선택합니다.

## <a name="review-the-er-solution-that-is-provided"></a>제공된 ER 솔루션 검토

1.  구성 트리에서 모델의 내용을 확장하여 **매개 변수화된 호출 항목** 을 학습합니다.
2.  **매개 변수화된 호출 항목** 을 학습하는 형식을 선택합니다.
3.  **디자이너** 를 선택합니다.
4.  **확장/축소** 를 선택합니다.

    **매개 변수화된 호출을 학습하는 형식** ER 형식은 여러 수준의 과세(일반, 경감 및 없음)를 나타내는 XML 형식의 세금 명세서를 생성하도록 설계되었습니다. 각 레벨에는 다른 수의 세부 정보가 있습니다.

    ![여러 수준의 ER 형식, 매개 변수화된 호출을 학습하기 위한 형식.](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  **매핑** 탭에서 **모델**, **데이터** 및 **요약** 항목을 확장합니다.

    **Model.Data.Summary** 데이터 소스는 세금 거래 목록을 반환합니다. 이러한 거래는 세금 코드로 요약됩니다. 이 데이터 원본의 경우 **Model.Data.Summary.Level** 계산 필드가 요약된 각 기록의 과세 수준에 대한 코드를 반환하도록 구성되었습니다. 런타임 시 **Model.Data.Summary** 데이터 소스에서 검색할 수 있는 모든 세금 코드의 경우 계산된 필드는 과세 수준 코드(**일반**, **감소**, **없음** 또는 **기타**)를 텍스트 값으로 반환합니다. **Model.Data.Summary.Level** 계산 필드는 **Model.Data.Summary** 데이터 소스의 기록을 필터링하고 **Model.Data2.Level1**, **Model.Data2** 를 사용하여 과세 수준을 나타내는 각 XML 요소에 필터링된 데이터를 입력하는 데 사용됩니다. .Level2 및 **Model.Data2.Level3** 필드.

    ![세금 거래의 Model.Data.Summary 데이터 소스 목록입니다.](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    **Model.Data.Summary.Level** 계산 필드가 ER 표현식을 포함하도록 구성되었습니다. 세금 코드(**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** 및 **InVAT0**)는 이 구성에 하드코딩됩니다. 따라서 이 ER 형식은 이러한 세금 코드가 구성된 법인에 따라 다릅니다.

    ![하드코딩된 세금 코드가 있는 Model.Data.Summary.Level 계산 필드입니다.](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    각 법인에 대해 다른 세금 코드 세트를 지원하려면 다음 단계를 따라야 합니다.

    - 각 법인에 대해 파생된 버전의 ER 형식을 만듭니다.
    - 법인 설정에 따라 **Model.Data.Summary.Level** 계산 필드에서 세금 코드를 업데이트합니다.

6.  **형식 디자이너** 페이지를 닫습니다.

## <a name="create-a-derived-format"></a>파생 형식 만들기

다음으로 ER 애플리케이션별 매개 변수 기능을 사용하여 단일 ER 형식의 각 법인에 대해 서로 다른 세금 코드 세트를 지원합니다.

1.  구성 트리에서 모델의 내용을 확장하여 **매개 변수화된 호출 항목** 을 학습합니다.
2.  **매개 변수화된 호출 항목** 을 학습하는 형식을 선택합니다.
3.  **구성 만들기** 를 선택합니다.
4.  **이름에서 파생 선택: 매개 변수화된 호출을 학습하는 형식, Microsoft** 옵션.
5.  **이름** 필드에 형식을 입력하여 **LE 데이터를 조회하는 방법** 을 알아봅니다.
6.  **구성 만들기** 를 선택합니다.

## <a name="configure-a-derived-format"></a>파생 형식 구성

### <a name="add-a-format-enumeration"></a>형식 열거형 추가

다음으로 새 ER 형식 열거를 추가합니다. 이 형식 열거의 값은 ER 형식에서 사용되는 다양한 과세 수준에 대해 법인 종속 세금 코드 집합을 지정하는 비즈니스 사용자에게 표시됩니다.

1.  **디자이너** 를 선택합니다.
2.  **형식 열거** 를 선택합니다.
3.  **추가** 를 선택합니다.
4.  **이름** 필드에 **과세 수준 목록** 을 입력합니다.
5.  **저장** 을 선택합니다.
6.  **열거형 값 형식** 탭에서 **추가** 를 선택합니다.
7.  **이름** 필드에 **일반 과세** 를 입력합니다.
8.  **추가** 를 다시 선택합니다.
9.  **이름** 필드에 **감세** 를 입력합니다.
10. **추가** 를 다시 선택합니다.
11. **이름** 필드에 **과세 없음** 을 입력합니다.
12. **추가** 를 다시 선택합니다.
13. **이름** 필드에 **기타** 를 입력합니다.

    ![형식 열거 페이지의 새 기록입니다.](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    비즈니스 사용자는 다른 언어를 사용하여 법인 종속 세금 코드 집합을 지정할 수 있으므로 이 열거 값을 Finance에서 해당 사용자의 기본 언어로 구성된 언어로 변환하는 것이 좋습니다.

14. **과세 기록 없음** 을 선택합니다.
15. **레이블** 필드를 클릭합니다.
16. **번역** 을 선택합니다.
17. **텍스트 번역** 창의 **레이블 ID** 필드에 **LBL_LEVELENUM_NO** 를 입력합니다.
18. **기본 언어의 텍스트** 필드에 **과세 없음** 을 입력합니다.
19. **언어** 필드에서 **DE** 를 선택하십시오.
20. **번역된 텍스트** 필드에 **keine Besteuerung** 을 입력합니다.
21. **번역** 을 선택합니다.

    ![텍스트 번역 슬라이드 아웃.](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. **저장** 을 선택합니다.
23. **서식 열거** 페이지를 닫습니다.

### <a name="add-a-new-lookup-data-source"></a>새 조회 데이터 소스 추가

다음으로 비즈니스 사용자가 요약된 각 거래 기록에 대한 올바른 과세 수준을 인식하기 위해 법인 종속 규칙을 지정하는 방법을 지정하는 새 데이터 소스를 추가합니다.

1.  **매핑** 탭에서 **추가** 를 선택합니다.
2.  **형식 열거\조회** 를 선택합니다.

    비즈니스 사용자가 과세 수준 인식을 위해 지정하는 각 규칙이 ER 형식 열거 값을 반환한다는 것을 방금 확인했습니다. **조회** 데이터 원본 유형은 **형식 열거** 블록 외에도 **데이터 모델** 및 **Dynamics 365 for Operations** 블록에서 액세스할 수 있습니다. 따라서 ER 데이터 모델 열거 및 애플리케이션 열거를 사용하여 해당 유형의 데이터 소스에 대해 반환되는 값 유형을 지정할 수 있습니다. **조회** 데이터 원본에 대한 자세한 내용은 [ER 애플리케이션별 매개 변수 기능을 사용하도록 조회 데이터 원본 구성](er-lookup-data-sources.md)을 참조하십시오.
    
3.  **이름** 필드에 **선택기** 를 입력합니다.
4.  **형식 열거** 필드에서 **과세 수준 목록** 을 선택합니다.

    이 데이터 소스에 지정된 각 규칙에 대해 비즈니스 사용자가 **과세 수준 목록** 형식 열거 값 중 하나를 반환 값으로 선택해야 한다고 지정했습니다.
    
5.  **조회 편집** 을 선택합니다.
6.  **열** 을 선택합니다.
7.  **모델** 항목을 확장합니다.
8.  **데이터** 항목을 확장합니다.
9.  **세금** 항목을 확장합니다.
10. **Model.Data.Tax.Code** 항목을 선택합니다.
11. **추가** 버튼(오른쪽 화살표)을 선택합니다.

    ![열이 미끄러집니다.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    과세 수준 인식을 위해 이 데이터 소스에 지정된 각 규칙에 대해 비즈니스 사용자가 세금 코드 중 하나를 조건으로 선택해야 한다고 지정했습니다. 비즈니스 사용자가 선택할 수 있는 세금 코드 목록은 **Model.Data.Tax** 데이터 소스에서 반환됩니다. 이 데이터 원본에는 **이름** 필드가 포함되어 있으므로 비즈니스 사용자에게 제공되는 조회의 각 세금 코드 값에 대해 세금 코드 이름이 표시됩니다.
    
12. **확인** 을 선택합니다.

    ![디자이너 페이지를 찾습니다.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    비즈니스 사용자는 이 데이터 소스의 기록으로 여러 규칙을 추가할 수 있습니다. 각 기록은 라인 코드로 번호가 매겨집니다. 규칙은 줄 번호가 증가하는 순서로 평가됩니다.

    이 조회 데이터 소스의 규칙에 대한 조건으로 **세금 코드** 필드를 선택했고 **세금 코드** 가 **스트링** 데이터 유형의 필드로 설정되었기 때문에 각 규칙은 전달된 세금 코드를 비교하여 런타임에 평가됩니다. 데이터 소스의 이 기록에 정의된 세금 코드가 있는 데이터 소스입니다.

    구성된 조건을 만족하는 규칙이 발견되면 이 데이터 소스는 **조회 결과** 필드에 정의된 규칙의 조회 값을 리턴합니다. 규칙이 없으면 현재 데이터 원본이 올바른 값을 반환할 수 없음을 사용자에게 알리기 위해 예외가 발생합니다.

13. **저장** 을 선택합니다.
14. **조회 디자이너** 페이지를 닫습니다.
15. **확인** 을 선택합니다.

    **스트링 데이터 유형** 의 Code 매개 변수 인수로 데이터 소스에 전달되는 모든 세금 코드에 대한 **과세 수준 목록** 형식 열거의 값으로 **과세 수준** 을 반환하는 새 데이터 원본을 추가했습니다.
    
    ![새 데이터 소스로 디자이너 페이지 서식을 지정합니다.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    구성된 규칙의 평가는 해당 규칙의 조건을 정의하기 위해 선택한 필드의 데이터 유형에 따라 다릅니다. **숫자** 또는 **날짜** 데이터 유형의 필드로 구성된 필드를 선택하는 경우 기준은 이전에 **스트링** 데이터 유형에 대해 설명한 기준과 다릅니다. **숫자** 및 **날짜** 필드의 경우 규칙을 값 범위로 지정해야 합니다. 그러면 데이터 소스에 전달된 값이 구성된 범위에 있을 때 규칙 조건이 충족된 것으로 간주됩니다.
    
    다음 그림은 이러한 설정 유형의 예를 보여줍니다. **스트링** 데이터 유형의 **Model.Data.Tax.Code** 필드 외에도 **Real** 데이터 유형의 **Model.Tax.Summary.Base** 필드는 조회 데이터 소스에 대한 조건을 지정하는 데 사용됩니다.
    
    ![추가 열이 있는 조회 디자이너 페이지.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    이 조회 데이터 소스에 대해 **Model.Data.Tax.Code** 및 **Model.Tax.Summary.Base** 필드가 선택되었기 때문에 이 데이터 소스의 각 규칙은 다음과 같은 방식으로 구성됩니다.
    
    -   표시된 목록에서 **과세 수준 목록** 형식 열거 값을 반환 값으로 선택해야 합니다.
    -   이 규칙의 조건으로 세금 코드를 입력해야 합니다. **Model.Data.Tax** 데이터 소스에서 제공하는 세금 코드만 적용할 수 있습니다.
    -   이 규칙의 조건으로 과세표준 금액의 최소값과 최대값을 입력해야 합니다.

    이 데이터 소스의 각 규칙이 런타임에 평가되는 방식은 다음과 같습니다.
    -   이 데이터 소스에 전달된 **스트링** 데이터 유형의 코드가 규칙의 세금 코드와 동일합니까?
    -   이 데이터 소스에 전달된 **실제** 데이터 유형의 값이 특정 최소값과 최대값 사이에 있습니까?

    두 조건이 모두 충족되면 규칙이 적용되는 것으로 간주됩니다.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>추가된 조회 데이터 소스의 레이블 번역

비즈니스 사용자는 다른 언어를 사용하여 법인 종속 세금 코드 집합을 지정할 수 있으므로 추가하는 조회 데이터 원본의 레이블을 번역하여 해당 페이지에서 각 사용자의 기본 언어로 표시되도록 하는 것이 좋습니다.

1.  **Model.Data.Selector** 데이터 소스를 선택하십시오.
2.  **편집** 을 선택합니다.
3.  **레이블** 필드를 클릭합니다.
4.  **번역** 을 선택합니다.
5.  **텍스트 번역** 창의 **레이블 ID** 필드에 **LBL_SELECTOR_DS** 를 입력합니다.
6.  **기본 언어의 텍스트** 필드에 세금 코드로 **세금 수준 선택** 을 입력합니다.
7.  **언어** 필드에서 **DE** 를 선택하십시오.
8.  **번역된 텍스트** 필드에 **Steuerebene für Steuerkennzeichen auswählen** 을 입력합니다.
9.  **번역** 을 선택합니다.
10. **확인** 을 선택합니다.

    ![데이터 소스 속성이 슬라이드 아웃됩니다.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>구성된 조회를 사용할 새 필드 추가

1.  **Model.Data** 항목을 확장합니다.
2.  **Model.Data.Summary** 항목을 선택하십시오.
3.  **추가** 를 선택합니다.
4.  **함수/계산된 필드** 를 선택합니다.
5.  **이름** 필드에 **LevelByLookup** 을 입력합니다.
6.  **수식 편집** 을 선택합니다.
7.  **수식 필드** 에 **Model.Selector(Model.Data.Summary.Code)** 를 입력합니다.
8.  **저장** 을 선택합니다.

    ![수식 디자이너 페이지에 Model.Selector(Model.Data.Summary.Code)를 추가합니다.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  **수식 편집기** 페이지를 닫습니다.
10. **확인** 을 선택합니다.

    ![새로운 공식이 추가된 형식 디자이너 페이지.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    추가한 **LevelByLookup** 계산 필드는 각 요약된 세금 거래 기록에 대한 **과세 수준 목록** 형식 열거 값으로 과세 수준을 반환합니다. 기록의 세금 코드는 **Model.Selector** 조회 데이터 소스로 전달되고 이 데이터 소스에 대한 규칙 세트는 올바른 과세 수준을 선택하는 데 사용됩니다.

### <a name="add-a-new-format-enumeration-based-data-source"></a>새 형식 열거 기반 데이터 소스 추가

다음으로 이전에 추가한 형식 열거를 참조하는 새 데이터 원본을 추가합니다. 이 데이터 소스의 값은 나중에 ER 형식 표현식에서 사용됩니다.

1.  **루트 추가** 를 선택합니다.
2.  **열거 형식\열거** 를 선택합니다.
3.  **이름** 필드에 **TaxationLevel** 을 입력합니다.
4.  **형식 열거** 필드에서 **과세 수준 목록** 을 선택합니다.
5.  **저장** 을 선택합니다.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>조회를 사용하려면 기존 필드를 수정하십시오.

다음으로, 구성된 조회 데이터 원본을 사용하여 세금 코드에 따라 올바른 과세 수준 값을 반환하도록 기존 계산된 필드를 수정합니다.

1.  **Model.Data.Summary.Level** 항목을 선택하십시오.
2.  **편집** 을 선택합니다.
3.  **수식 편집** 을 선택합니다.

    **Model.Data.Summary.Level** 필드의 현재 표현식에는 다음과 같은 하드 코딩된 세금 코드가 포함되어 있습니다.
    
    CASE(@.Code, 'VAT19', '일반', 'InVAT19', '일반', 'VAT7', '감소됨', 'InVAT7', '감소됨', 'THIRD', '없음', 'InVAT0', '없음', '기타')

4.  **수식** 필드에 **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', 'Regular', TaxationLevel.'Reduced taxation', 'Reduced', TaxationLevel.'No taxation', 'None', 'Other')** 를 입력합니다.

    ![ER 오퍼레이션 디자이너 페이지.](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    **Model.Data.Summary.Level** 필드의 표현식은 현재 기록의 세금 코드와 **Model.Data.Selector** 조회 데이터 소스에서 비즈니스 사용자가 구성한 규칙 집합을 기반으로 과세 수준을 반환합니다. .
    
5.  **저장** 을 선택합니다.
6.  **수식 디자이너** 페이지를 닫습니다.
7.  **확인** 을 선택합니다.
8.  **저장** 을 선택합니다.
9.  **형식 디자이너** 페이지를 닫습니다.

## <a name="complete-the-draft-version-of-a-derived-format"></a>파생 형식의 초안 버전 완성

1.  **버전** FastTab에서 **상태 변경** 을 선택합니다.
2.  **완료** 를 선택합니다.
3.  **확인** 을 선택합니다.

## <a name="export-completed-version-of-modified-format"></a>수정된 형식의 완성된 버전 내보내기

1.  구성 트리에서 형식을 선택하여 **LE 데이터 항목을 조회하는 방법** 을 배우십시오.
2.  **버전** FastTab에서 **완료됨** 상태의 기록을 선택합니다.
3.  **교환** 을 선택합니다.
4.  **XML 파일로 내보내기** 를 선택합니다.
5.  **확인** 을 선택합니다.
6.  웹 브라우저는 **LE data.xml 파일을 찾는 방법을 배우기 위해 형식을 다운로드** 합니다. 이 파일을 로컬에 저장합니다.

형식의 상위 항목에 대해 이 섹션의 단계를 반복하여 **LE 데이터 형식을 조회하고 다음 파일을 로컬로 저장하는 방법** 을 배우십시오.

-   매개 변수화된 호출을 학습하는 형식.xml
-   매개 변수화된 calls.xml을 학습하기 위한 매핑
-   매개 변수화된 호출을 학습하는 모델.xml

구성된 **형식을 사용하여 다른 과세 수준별로 세금 거래를 필터링** 하기 위해 [법인 종속 세금 코드 세트를 설정](er-app-specific-parameters-set-up.md)하기 위해 LE 데이터 ER 형식을 조회하는 방법을 배우려면 ER 매개 변수 설정의 단계를 완료하십시오. 법인 주제별 형식.

## <a name="additional-resources"></a>추가 리소스

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[법인별 ER 형식의 매개 변수 설정](er-app-specific-parameters-set-up.md)

[ER 애플리케이션별 매개 변수 기능을 사용하도록 조회 데이터 소스 구성](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
