---
title: ER 모델 및 형식의 데이터 바인딩에서 상대 경로 사용
description: 전자 보고 도구를 사용하면 전자 형식 구조를 정의한 다음 구조를 채우는 방법을 설명할 수 있습니다.
author: NickSelin
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: af3a646e24976d50f83d8564e3006fc2c50d8e2a
ms.sourcegitcommit: 8bcb9c13eccb14e61c39ca6578d135b64090fad2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460776"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>ER 모델 및 형식의 데이터 바인딩에서 상대 경로 사용

[!include[banner](../includes/banner.md)]

전자 보고(ER) 도구를 사용하면 전자 형식 구조를 정의한 다음 응용 프로그램에 있는 데이터와 알고리즘을 사용하여 이러한 구조를 채우는 방법을 설명할 수 있습니다. 자세한 내용은 [전자 보고(ER) 구성 만들기](electronic-reporting-configuration.md)를 참조하세요. 재무 및 운영 데이터를 검색하고 이를 사용하여 전자 문서를 생성하기 위한 데이터 흐름을 지정하려면 다음을 수행해야 합니다.

- 구성된 데이터 소스를 설계된 도메인별 데이터 모델의 요소에 바인딩합니다. 모델 구조와 선택한 데이터 소스는 복잡한 계층 구조의 일부일 수 있습니다. 이 때문에 최종 바인딩은 상당히 클 수 있으며 다양한 유형의 요소(예: 관계, 테이블 및 메서드)를 포함할 수 있습니다. 바인딩은 특히 소유자가 아닌 경우 가독성이 떨어지고 검토하고 이해하기가 상당히 복잡해질 수 있습니다. 
- 데이터 모델 요소를 형식 구성 요소와 바인딩하여 데이터 모델에서 생성된 형식의 출력으로 채워질 데이터를 정의합니다.

ER 매핑 디자이너의 사용성을 향상시키기 위해 [상대 경로](er-formula-language.md#relative-path) 기능이 출시되었습니다. 기본적으로 상대 경로 표시 옵션은 ER 디자인 경험이 활성화된 응용 프로그램의 모든 새 인스턴스에 대해 켜져 있습니다(Microsoft Dynamics 365 Finance, Microsoft Regulatory Configuration Service). 사용자가 이 ER 바인딩 프레젠테이션으로 작업할 때 전체 경로를 계속 사용할 수 있도록 상대 경로 매개변수를 구현했습니다.

[![사용자 매개 변수.](./media/relative-path-01.png)](./media/relative-path-01.png)

 
상대 경로 사용 매개변수가 켜져 있으면 단일 @ 문자가 현재 모델 요소의 바인딩에서 상위 항목에 대한 경로를 대체합니다. 전체 바인딩 경로가 짧아져 전체 매핑이 더 명확하고 이해하기 쉽습니다. 대부분의 경우 데이터 모델의 모든 바인딩을 보기 위해 ER 디자이너에서 추가 스크롤이 필요하지 않습니다.

[![모델 매핑 디자이너.](./media/relative-path-02.png)](./media/relative-path-02.png)
 
새 ER 표현식 디자인을 시작할 때 상위 항목의 필드에 대한 바인딩을 정의하기 위해 한 문자만 입력하면 됩니다.

[![수식 디자이너.](./media/relative-path-03.png)](./media/relative-path-03.png)
 
절대 경로를 사용하여 상위 모델 항목의 데이터 소스를 변경하기로 결정한 경우 이 모델 항목과 모든 중첩 항목을 새 데이터 소스에 수동으로 다시 바인딩해야 합니다. 상대 경로 사용이 켜져 있고 상위 항목에 바인딩할 새 데이터 소스를 선택하면 한 번의 클릭으로 이 상위 항목의 모든 중첩 요소를 자동으로 다시 바인딩하는 옵션이 제공됩니다.

[![기존 경로 메시지를 바꿉니다.](./media/relative-path-04.png)](./media/relative-path-04.png)
 
중첩 항목의 리바인딩을 확인하면 새 상위 항목이 기존 상위 항목을 포함하는 각 중첩 항목의 경로에 배치됩니다.
이 기능은 ER 프레임워크의 이전 버전과의 호환성을 손상시키지 않습니다. 이전에 설계된 모든 ER 구성은 이 새로운 기능과 함께 작동하며 업그레이드나 변환이 필요하지 않습니다.

> [!NOTE]
> 모델 매핑에서 중첩 요소의 바인딩을 대량 수정하여 도입된 모든 변경 사항은 구성 델타(변경 사항 추적)에 올바르게 저장됩니다. 이를 통해 고객은 파생된 버전의 모델 매핑을 이 새 기능을 사용하여 수정된 새 기본 버전으로 리베이스할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[ER 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
