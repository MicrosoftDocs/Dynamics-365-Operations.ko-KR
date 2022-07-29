---
title: 비즈니스 문서 템플릿의 구조 업데이트
description: 이번에는 비즈니스 문서 관리 기능을 사용하여 비즈니스 문서 템플릿의 구조를 업데이트하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 2f57e3f3a84a6e767755c69074bc194e90793e6edd79d0e07ae7449d45ec7539
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460997"
---
# <a name="update-the-structure-of-a-business-document-template"></a>비즈니스 문서 템플릿의 구조 업데이트 

[!include[banner](../includes/banner.md)]

[비즈니스 문서 관리](er-business-document-management.md) 템플릿 편집기의 **템플릿 구조** 창에서 Microsoft Excel의 템플릿에 [새 필드를 추가](er-bdm-add-field-to-excel-template.md)하여 비즈니스 문서 템플릿을 수정할 수 있습니다. 그러면 템플릿 구조가 **템플릿 구조** 창에서 변경한 내용을 반영하도록 Dynamics 365 Finance에서 자동으로 업데이트됩니다.

Office 365 온라인 함수를 사용하여 템플릿을 수정할 수도 있습니다. 예를 들어 그림이나 도형과 같이 이름이 지정된 새 항목을 편집 가능한 워크시트에 추가할 수 있습니다. 이 경우 템플릿의 구조가 Finance에서 자동으로 업데이트되지 않고 추가한 항목이 **템플릿 구조** 창에 나타나지 않습니다. 템플릿 편집기 페이지에서 구조 업데이트를 선택하여 재무에서 **템플릿 구조** 를 수동으로 업데이트합니다.

이 기능에 대한 자세한 내용은 다음 예를 완료하십시오.

## <a name="example-update-the-structure-of-a-business-document-template"></a>예:, 비즈니스 문서 템플릿의 구조 업데이트

이 예시에서는 에서 템플릿이 수정된 후 Office Online 시스템 관리자가 Finance에서 비즈니스 문서 템플릿의 구조를 업데이트할 수 있는 방법을 보여줍니다. 다음 섹션에서는 관련된 단계를 설명합니다.

### <a name="prepare-a-business-document-template-for-editing"></a>편집을 위한 비즈니스 문서 템플릿 준비

[비즈니스 문서 관리 개요](er-business-document-management.md)에서 다음 절차를 완료하십시오.

1. [ER 매개 변수 구성](er-business-document-management.md#configure-er-parameters)
2. [응급실 솔루션 가져오기](er-business-document-management.md#import-er-solutions)
3. [비즈니스 문서 관리 활성화](er-business-document-management.md#enable-business-document-management)
4. [매개 변수 구성](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>비즈니스 문서 템플릿 편집

1. **비즈니스 문서 관리** 작업 영역에서 **새 문서** 를 선택합니다.
2. **새 템플릿 만들기** 페이지에서 **무료 텍스트 송장(ER 샘플)(Excel)** 템플릿을 선택합니다.
3. **문서 만들기** 를 선택합니다.
4. **제목** 필드에 **FTI 샘플 Litware** 를 입력합니다.
5. **확인** 을 선택하여 새 템플릿을 만듭니다.

    > [!NOTE]
    > 아직 Office Online 에 로그인하지 않은 경우 [Office 365 로그인 페이지로 이동](er-business-document-management.md#frequently-asked-questions)합니다. 재무 환경으로 돌아가려면 브라우저에서 **뒤로** 버튼을 선택하십시오.

    템플릿 편집기 페이지의 Excel Online 포함 컨트롤에서 편집을 위해 새 템플릿이 열립니다.

[![비즈니스 문서 관리 작업 공간을 사용하여 비즈니스 문서 템플릿 편집을 시작합니다.](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>편집 가능한 템플릿의 현재 구조 검토

1. Excel Online의 리본 메뉴에 있는 **보기** 탭에 있는 **표시** 그룹에서 **눈금선** 을 선택합니다.
2. 편집 가능한 템플릿에서 템플릿 제목 위의 사각형을 선택합니다. 이 사각형은 **rptHeaderCompLogo** 라는 그림입니다.
3. **템플릿 구조** 창이 숨겨진 경우 **구조 표시** 를 선택합니다.
4. **템플릿 구조** 창에서 **보고서 \> 송장 \> rptHeader \> rptHeaderPart1** 을 확장합니다.
5. Finance의 템플릿 구조에서 **rptHeaderCompLogo** 항목은 **보고서 \> 송장 \> rptHeader \> rptHeaderPart1** 의 하위 항목으로 표시됩니다.

[![비즈니스 문서 관리 작업 공간을 사용하여 편집 가능한 템플릿의 현재 구조를 검토합니다.](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>그림을 삭제하여 비즈니스 문서 템플릿의 구조 업데이트

1. Excel Online의 편집 가능한 템플릿에서 **rptHeaderCompLogo** 그림을 선택합니다.
2. 편집 가능한 템플릿에서 선택한 사진을 삭제하려면 다음 단계 중 하나를 따르십시오.

    - 키보드에서 **Delete** 키를 선택합니다.
    - 사진을 길게 선택(또는 마우스 오른쪽 버튼으로 클릭)한 다음 **잘라내기** 를 선택합니다.

    > [!NOTE]
    > 그림이 더 이상 Excel 템플릿에 포함되지 않더라도 **rptHeaderCompLogo** 항목은 현재 Finance의 템플릿 구조에 있습니다.

3. **구조 업데이트** 를 선택하여 Excel 및 Finance에서 편집 가능한 템플릿의 구조를 동기화합니다.
4. **템플릿 구조** 창에서 **보고서 \> 송장 \> rptHeader \> rptHeaderPart1** 을 확장합니다.
5. **rptHeaderCompLogo** 항목은 더 이상 Finance의 템플릿 구조에 포함되지 않습니다.

[![비즈니스 문서 관리 작업 영역을 사용하여 비즈니스 문서 템플릿에서 그림을 삭제합니다.](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>그림을 추가하여 비즈니스 문서 템플릿의 구조 업데이트

1. Excel Online의 리본 메뉴에 있는 **삽입** 탭에 있는 **일러스트레이션** 그룹에서 **그림** 을 선택합니다.
2. **파일 선택** 을 선택하고 추가할 이미지를 찾아 선택한 다음 **확인** 을 선택합니다.
3. **삽입** 을 선택합니다.
4. 새 그림이 올바른 위치에 올 때까지 이동합니다. 기본적으로 Excel은 그림의 이름을 지정합니다. 예를 들어 그림의 이름을 **Picture 2** 로 지정할 수 있습니다.
5. **구조 업데이트** 를 선택하여 Excel 및 Finance에서 편집 가능한 템플릿의 구조를 동기화합니다.
6. **템플릿 구조** 창에서 **보고서 \> 송장 \> rptHeader \> rptHeaderPart1** 을 확장합니다.
7. 이제 새 그림이 Finance의 템플릿 구조에 항목으로 포함됩니다.

[![비즈니스 문서 관리 작업 영역을 사용하여 비즈니스 문서 템플릿에 그림을 추가합니다.](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>관련된 링크들

[전자 보고(ER) 개요](general-electronic-reporting.md)

[비즈니스 문서 관리 개요](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]