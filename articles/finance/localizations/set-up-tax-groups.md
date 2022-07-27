---
title: 세금 그룹 설정
description: 이 항목에서는 세금 계산 서비스에서 세금 그룹을 설정하는 방법을 설명합니다.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 50abafb958edfb8476434ff5842cd84cb186962f
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451228"
---
# <a name="set-up-tax-groups"></a>세금 그룹 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 세금 계산 서비스에서 세금 그룹을 설정하는 방법을 설명합니다. 또한 세금 그룹 적용 가능성 규칙 매트릭스를 설정하고 매트릭스에서 라인을 구성하는 방법을 설명합니다.

세금 계산 서비스의 세금 그룹 개념은 Microsoft Dynamics 365 Finance의 판매세 그룹 개념과 비슷합니다. 세금 코드의 그룹입니다. 세금 계산 서비스는 세금 그룹과 품목 세금 그룹의 교차를 사용하여 세금 코드를 결정합니다.

다만 세금 계산 서비스의 세금 그룹은 **사용세,** **면제세** 등 추가 매개 변수가 없다는 점에서 금융의 판매세 그룹과 차이가 있습니다. 대신 해당 매개 변수는 세금 코드 수준에서 사용할 수 있습니다.

> [!IMPORTANT]
> 세금 계산 서비스의 세금 그룹 설정은 법인에 영향을 받지 않습니다. 이 설정은 Regulatory Configuration Service(RCS)에서 한 번만 완료할 수 있습니다. Finance에서 세금 계산 서비스를 활성화하면 세금 그룹이 선택한 법인에 대해 자동으로 동기화됩니다.

## <a name="set-up-a-tax-group"></a>세금 그룹 설정

세금 그룹을 설정하려면 다음 단계를 따르십시오.

1. [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/)에 로그인합니다.
2. **작업 영역** \> **세계화 기능** \> **세금 계산** 으로 이동합니다.
3. 설정하려는 기능과 버전을 선택한 다음 **편집** 을 선택합니다.
4. **일반** 탭에서 **구성 버전** 을 선택합니다.
5. **세금 그룹** 탭에서 **열 관리** 를 선택합니다. 세금 그룹을 처음 설정하는 경우 **열 관리** 대화 상자의 필드가 자동으로 설정됩니다.
6. 왼쪽 목록에서 **라인** 노드를 확장하고 **세금 그룹** 확인란을 선택합니다.

    ![열 관리 대화 상자의 라인 노드에서 선택한 세금 그룹.](media/select-tax-group.png)

7. 오른쪽 화살표 버튼을 선택하여 **세금 그룹** 을 오른쪽의 **선택한 열** 목록에 추가합니다.

    ![세금 그룹이 선택한 열 목록에 추가됩니다.](media/add-tax-group.png)

8. **확인** 을 선택합니다.

## <a name="configure-a-tax-group"></a>세금 그룹 구성

세금 그룹을 설정하면 세금 그룹 적용 규칙 매트릭스가 생성됩니다. 매트릭스에 라인을 추가하여 세금 그룹을 구성할 수 있습니다.

1. **세금 그룹** 탭에서 **추가** 를 선택합니다.
2. **세금 그룹** 필드에 세금 그룹의 이름을 입력합니다.

    > [!IMPORTANT]
    > 세금 그룹의 이름은 10자로 제한하는 것이 좋습니다. 이 이름은 판매세 그룹 이름이 10자로 제한되는 Finance와 동기화됩니다.

3. **세금 코드** 필드에서 세금 그룹에 포함할 각 세금 코드의 확인란을 선택합니다. 하나의 세금 그룹에 여러 세금 코드를 포함할 수 있습니다.

    ![세금 코드 필드에서 여러 세금 코드 선택.](media/multiple-tax-codes-selection.png)

4. 세금 그룹을 더 추가하려면 1~3단계를 반복합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
