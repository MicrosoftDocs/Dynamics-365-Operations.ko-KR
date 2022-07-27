---
title: 세금 계산 가져오기 및 내보내기
description: 이 항목에서는 세금 계산 서비스의 가져오기 및 내보내기 기능에 대한 정보를 제공합니다.
author: Kai-Cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 76ea99510455e984d94a93d87ee788fdcf00c376
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451282"
---
# <a name="import-and-export-tax-calculations"></a>세금 계산 가져오기 및 내보내기

이 항목에서는 세금 계산 서비스의 가져오기 및 내보내기 기능에 대한 정보를 제공합니다. 이 기능은 유연하고 효율적인 구성 환경을 보장하는 데 도움이 됩니다.

## <a name="import-and-export-tax-codes"></a>세금 코드 가져오기 및 내보내기

### <a name="export-templates"></a>템플릿 내보내기

1. [Regulatory Configuration Service(RCS)](https://marketing.configure.global.dynamics.com/)에 로그인합니다.
2. **세계화 기능** 작업 영역에서 **기능** 을 선택한 다음 **세금 계산** 타일을 선택합니다.
3. 기존 기능을 선택하거나 [새 기능을 만듭니다](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. **버전** 그리드에서 **편집** 을 선택합니다.
5. **세금 계산** 기능 페이지에서 [구성 버전](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)을 설정합니다.
6. **세금 코드** 탭에서 **가져오기** 를 선택합니다.
7. **세금 코드 내보내기** 를 선택하여 **TaxCodesTemplate.zip** 파일을 다운로드합니다.
8. **TaxCodesTemplate.zip** 의 압축을 풉니다. 세금 코드 템플릿은 **계산 출처** 값에 따라 별도로 압축됩니다.
9. **By Net Amount.zip** 압축을 풀어 다음 CSV(쉼표로 구분된 값) 파일을 가져옵니다.

    - **TaxCode.csv** – 세금 코드를 입력합니다.
    - **TaxLimit.csv** – 각 세금 코드의 세금 한도를 입력합니다.
    - **TaxRate.csv** – 각 세금 코드의 세율을 입력합니다.

> [!NOTE]
> 기본적으로 **샘플** 세금 코드에 대한 항목을 템플릿에서 사용할 수 있습니다. **샘플** 세금 코드가 CSV 파일에서 제거되지 않으면 기능으로 가져옵니다.

### <a name="import-tax-codes"></a>세금 코드 가져오기

템플릿의 **샘플** 세금 코드를 세금 계산 기능으로 가져오려면 다음 단계를 따릅니다.

1. RCS의 **세금 계산** 기능 페이지에 있는 **세금 코드** 탭에서 **가져오기** 를 선택합니다.
2. **찾아보기** 를 선택하고 **TaxCode.csv** 파일을 찾아 선택한 다음 **대상 테이블** 필드에서 **세금 코드** 를 선택합니다.
3. **확인** 을 선택하여 세금 코드를 가져옵니다.
4. **TaxRate.csv** 파일을 찾아 선택한 다음 **대상 테이블** 필드에서 **세율** 을 선택합니다.
5. **확인** 을 선택하여 세율을 가져옵니다.
6. **TaxLimit.csv** 파일을 찾아 선택한 다음 **대상 테이블** 필드에서 **세금 한도** 를 선택합니다.
7. **확인** 을 선택하여 세금 한도를 가져옵니다.

세 개의 CSV 파일이 모두 포함된 zip 파일을 직접 가져올 수도 있습니다. 이렇게 하면 빠르고 쉽게 가져오기를 완료할 수 있습니다.

1. RCS의 **세금 계산** 기능 페이지에 있는 **세금 코드** 탭에서 **가져오기** 를 선택합니다.
2. **찾아보기** 를 선택하고 **By Net Amount.zip** 파일을 찾아 선택한 다음 **확인** 을 선택합니다.

### <a name="export-tax-codes"></a>세금 코드 내보내기

1. RCS의 **세금 계산** 기능 페이지에 있는 **세금 코드** 탭에서 **내보내기** 를 선택합니다.

    **내보내기** 버튼은 **세금 코드** 그리드에 하나 이상의 세금 코드가 있는 경우 사용할 수 있습니다.

2. **확인** 을 선택하여 기능의 모든 세금 코드를 zip 파일로 내보냅니다.

> [!NOTE]
> 내보낸 파일을 템플릿으로 사용하여 세금 코드를 해당 기능으로 가져옵니다.

## <a name="import-and-export-applicability-rules"></a>적용 가능성 규칙 가져오기 및 내보내기

### <a name="export-applicability-rules"></a>적용 가능성 규칙 내보내기

1. [RCS](https://marketing.configure.global.dynamics.com/)에 로그인합니다.
2. **세계화 기능** 작업 영역에서 **기능** 을 선택한 다음 **세금 계산** 타일을 선택합니다.
3. 기존 기능을 선택하거나 [새 기능을 만듭니다](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. **버전** 그리드에서 **편집** 을 선택합니다.
5. **세금 계산** 기능 페이지에서 [구성 버전](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs)을 설정합니다.
6. **세금 그룹 적용 가능성** 탭의 **세금 그룹 적용 가능성 설정** 그리드에서 행을 선택합니다.
7. **Microsoft Office에서 열기** 버튼을 선택한 후 **세금 서비스 동적 적용 가능성 매트릭스** 를 선택합니다.

    [![세금 계산 기능 페이지에서 적용 가능성 규칙을 Microsoft Excel로 내보내기.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. **다운로드** 를 선택하여 선택한 행을 Microsoft Excel 워크시트로 내보냅니다.

### <a name="import-applicability-rules"></a>적용 가능성 규칙 가져오기

다운로드한 Excel 워크시트에는 **세금 그룹 적용 가능성 설정** 그리드의 구조가 포함되어 있습니다. 워크시트에서 직접 새 규칙을 추가할 수 있습니다. 완료되면 다음 단계에 따라 새 규칙을 **세금 그룹 적용 가능성 설정** 그리드로 다시 가져옵니다.

1. Excel 워크시트에서 가져올 행을 선택하여 복사합니다.
2. RCS의 **세금 계산** 기능 페이지의 **세금 그룹 적용 가능성** 탭에서 **추가** 를 선택하여 **세금 그룹 적용 가능성 설정** 그리드 하단에 빈 레코드를 삽입합니다.
3. **Ctrl+V** 를 선택하여 복사한 행을 그리드에 붙여넣습니다.
4. **저장** 을 선택합니다.
