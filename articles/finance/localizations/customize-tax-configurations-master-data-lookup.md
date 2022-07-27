---
title: 마스터 데이터 조회를 위한 세금 구성 사용자 지정
description: 이 항목에서는 마스터 데이터 검색 기능을 확장하기 위해 세금 구성을 사용자 지정하는 방법을 설명합니다.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 498201d5c0377058e86b25953ebbe401ae1af9e3
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2021
ms.locfileid: "8451111"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>마스터 데이터 조회를 위한 세금 구성 사용자 지정

[!include [banner](../includes/banner.md)]

마스터 데이터 검색 기능을 확장하도록 세금 구성을 사용자 지정하려면 이 항목의 단계를 따르십시오.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>Microsoft에서 제공하는 세금 구성 가져오기

1. RCS(Regulatory Configuration Service)의 **전자 보고** 작업 영역에서 **Microsoft** 구성 공급자를 선택합니다.
2. **리포지토리** 를 선택합니다.
3. **전역** 을 선택하고 **열기** 를 선택합니다.
4. **세금 계산 구성** 과 같은 세금 구성을 선택한 다음 **버전** 탭에서 버전을 선택합니다.
5. **가져오기** 를 선택합니다.

> [!NOTE]
> 기본적으로 Dataverse 모델 매핑을 가져옵니다. 구성 가져오기 프로세스 중에 경고 메시지가 표시되면 Dataverse에서 가상 엔터티를 사용하도록 설정합니다. 자세한 내용은 [Dataverse 가상 엔터티 활성화](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md)를 참조하십시오.

## <a name="create-a-customized-data-model-configuration"></a>사용자 지정된 데이터 모델 구성 만들기

1. **전자 보고** 작업 영역에서 **세금 구성** 을 선택한 후 확장할 데이터 모델 구성을 선택합니다. 예를 들어 **세금 계산 데이터 모델** 을 선택합니다.
2. **구성 만들기** 를 선택합니다.
3. **이름으로 세금 문서 모델 선택: 세금 계산 데이터 모델, Microsoft** 를 선택합니다.
4. **이름** 필드에 **사용자 지정 데이터 모델** 을 입력합니다.
5. **구성 만들기** 를 선택합니다.

## <a name="create-customized-reference-models"></a>사용자 지정 참조 모델 만들기

1. **세금 구성** 페이지에서 **사용자 지정 데이터 모델** 을 선택한 다음 **디자이너** 를 선택합니다.
2. 줄임표 버튼(**...**)을 선택한 다음 **참조 모델** 보기를 선택합니다.

    [![참조 모델.](./media/pic2.png)](./media/pic2.png)

3. 사용자 지정 참조 모델 만들기 사용자 지정 모델은 루트 모델입니다. 사용자 지정 엔터티는 레코드 목록입니다. 사용자 지정 필드는 조회에 사용할 문자열 필드입니다. 필요에 따라 필드를 더 추가할 수 있습니다.
4. 줄임표 버튼(**...**)을 선택한 다음 **세금 문서** 보기를 선택합니다.
5. 사용자 지정 참조 모델에 바인딩할 특성을 선택합니다. 예를 들어 **사용자 지정 특성** 을 선택하고 다음 단계를 따릅니다.

    1. **참조 모델 선택** 을 선택합니다.
    2. **사용자 지정 모델** 을 선택하고 **확인** 을 선택합니다. 참조 모델 이름이 **자연 키** 필드의 값으로 업데이트됩니다.

        [![참조 모델 선택 대화 상자.](./media/pic5.png)](./media/pic5.png)

    3. **저장** 을 선택하고 **완료** 를 선택합니다.

## <a name="create-a-customized-model-mapping-configuration"></a>사용자 지정된 모델 매핑 구성 만들기

1. **전자 보고** 작업 영역에서 **세금 구성** 을 선택한 후 **Dataverse 모델 매핑** 구성을 선택합니다.
2. **모델 매핑의 기본값** 필드에서 **아니요** 를 선택합니다.
3. **구성 만들기** 를 선택합니다.
4. **이름으로 세금 문서 모델 선택: Dataverse 모델 매핑, Microsoft** 를 선택합니다.
5. **이름** 필드에 **사용자 지정 모델 매핑** 을 입력합니다.
6. **대상 모델** 필드에서 **사용자 지정 데이터 모델** 데이터 모델을 선택합니다.
7. **구성 만들기** 를 선택합니다.

    [![구성 만들기 드롭다운 대화 상자.](./media/pic6.png)](./media/pic6.png)

8. **사용자 지정 모델 매핑** 을 선택하고 **연결된 애플리케이션** 필드를 [마스터 데이터 조회를 위한 환경 설정](tax-service-set-up-environment-master-data-lookup.md)의 8단계에서 생성한 연결로 설정합니다.
9. **모델 매핑의 기본값** 필드를 **예** 로 설정합니다.

## <a name="create-customized-model-mappings"></a>사용자 지정된 모델 매핑 만들기

1. **세금 구성** 페이지에서 **사용자 지정 모델 매핑** 을 선택합니다.
2. **디자이너** 를 선택하고 **사용자 지정 모델** 을 선택합니다.

    [![사용자 지정 모델.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>모델 매핑을 Dataverse 엔터티에 매핑

1. **모델 매핑 디자이너** 페이지에서 **사용자 지정 모델** 을 선택한 다음 **디자이너** 를 선택합니다.
2. **데이터 원본 유형** 트리에서 **Dataverse 테이블** 을 선택합니다.
3. **데이터 원본** 탭에서 **루트 추가** 를 선택합니다.
4. **이름** 필드에 **사용자 지정 Dataverse** 를 입력합니다.
5. 두 번째 **이름** 필드에서 엔터티를 선택합니다.
6. **확인** 을 선택합니다.

    [!['테이블' 데이터 원본 속성 대화 상자.](./media/pic9.png)](./media/pic9.png)

7. **사용자 지정 Dataverse** 및 **사용자 지정 엔터티** 를 선택하고 **바인드** 를 선택합니다.

    [![사용자 지정 Dataverse 및 사용자 지정 엔터티 바인딩.](./media/pic10.png)](./media/pic10.png)

8. **사용자 지정 Dataverse** 및 **사용자 지정 필드** 에서 필드를 선택하고 **바인드** 를 선택합니다.

    [![사용자 지정 Dataverse 및 사용자 지정 필드 바인딩.](./media/pic11.png)](./media/pic11.png)

9. **저장** 을 선택하고 **완료** 를 선택합니다.

## <a name="create-a-customized-tax-configuration"></a>사용자 지정된 세금 구성 만들기

1. **전자 보고** 작업 영역에서 **세금 구성** 을 선택하고 **세금 계산 구성** 을 선택합니다.
2. **구성 만들기** 를 선택합니다.
3. **이름으로 세금 서비스 구성 선택을 선택: 세금 계산 구성, Microsoft** 를 선택합니다.
4. **이름** 필드에 **사용자 지정 구성** 을 입력합니다.
5. **구성 만들기** 를 선택합니다.
6. **사용자 지정 구성** 을 선택하고 **디자이너** 를 선택합니다.
7. **데이터 모델** 필드에서 사용자 **지정 데이터 모델** 을 선택합니다.
8. **데이터 모델 버전** 필드에서 해당하는 데이터 모델 버전을 선택합니다.

    [![속성 섹션.](./media/pic13.png)](./media/pic13.png)

9. **완료** 를 선택합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
