---
title: 템플릿 BOM 만들기
description: 다양한 방법을 사용하여 템플릿 BOM을 생성할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c10bf5e758a1752e1c50c602db85e0c53ee3e662
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448420"
---
# <a name="create-a-template-bom"></a>템플릿 BOM 만들기   

[!include [banner](../includes/banner.md)]


다양한 방법을 사용하여 템플릿 BOM을 생성할 수 있습니다. 모든 방법에서 **시작 날짜** 및 **종료 날짜** 필드는 선택 사항이며 참고용입니다.

## <a name="create-a-template-bom-manually"></a>수동으로 템플릿 BOM 만들기

1.  **서비스 관리** \> **설정** \> **서비스 개체** \> **템플릿 BOM** 으로 이동합니다.

2.  **새로 만들기** 를 선택하여 **템플릿 BOM 만들기** 양식을 엽니다.

3.  **참조에서 BOM 라인 복사** 에서 **수동** 옵션을 선택합니다.

4.  **품목 번호** 필드에 **BOM** 유형의 품목을 입력합니다.

5.  **이름** 필드에 템플릿의 이름을 입력합니다.

6.  **시작 날짜** 및 **종료 날짜** 필드에 템플릿 BOM이 활성화된 날짜 간격을 입력합니다.

7.  **확인** 을 선택합니다.

비어 있는 새 템플릿 BOM이 생성됩니다.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>다른 템플릿 BOM을 기반으로 템플릿 BOM 생성

1.  **서비스 관리** \> **설정** \> **서비스 개체** \> **템플릿 BOM** 으로 선택합니다.

2.  **새로 만들기** 를 선택하여 **템플릿 BOM 만들기** 양식을 엽니다.

3.  **참조에서 BOM 라인 복사** 에서 **템플릿 BOM** 옵션을 선택합니다.

4.  **참조 번호** 필드에서 기존 템플릿 BOM을 선택하여 새 템플릿 BOM에 복사합니다.

5.  **이름** 필드에 템플릿의 이름을 입력합니다.

6.  **시작 날짜** 및 **종료 날짜** 필드에 템플릿 BOM이 활성화된 날짜 간격을 입력합니다.

7.  **확인** 을 선택합니다.

새 템플릿 BOM은 원래 템플릿 BOM의 라인에 해당하는 라인을 사용하여 생성됩니다.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>다른 항목 BOM을 기반으로 템플릿 BOM 생성

1.  **서비스 관리** \> **설정** \> **서비스 개체** \> **템플릿 BOM** 으로 선택합니다.

2.  **새로 만들기** 를 선택하여 **템플릿 BOM 만들기** 양식을 엽니다.

3.  **참조에서 BOM 라인 복사** 에서 **BOM** 을 선택합니다.

4.  **참조 번호 필드** 에서 BOM 버전을 선택합니다. BOM 유형의 항목이 **품목 번호** 로 복사됩니다.

5.  **이름** 필드에 템플릿의 이름을 입력합니다.

6.  **시작 날짜** 및 **종료 날짜** 필드에 템플릿 BOM이 활성화된 날짜 간격을 입력합니다.

7.  **확인** 을 선택합니다.

**자재 명세서** 에 나열된 자재 명세서 라인에 해당하는 라인을 사용하여 새 템플릿 자재 명세서이 생성됩니다.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>생산 BOM을 기반으로 템플릿 BOM 생성

1.  **서비스 관리** \> **설정** \> **서비스 개체** \> **템플릿 BOM** 으로 선택합니다.

2.  **새로 만들기** 를 선택하여 **템플릿 BOM 만들기** 양식을 엽니다.

3.  **참조에서 BOM 라인 복사** 에서 **생산** 을 선택합니다.

4.  **참조 번호 필드** 에서 생산 BOM 버전을 선택합니다.

5.  **이름** 필드에 템플릿의 이름을 입력합니다.

6.  **시작 날짜** 및 **종료 날짜** 필드에 템플릿 BOM이 활성화된 날짜 간격을 입력합니다.

7.  **확인** 을 선택합니다.

**BOM** 에 나열된 BOM 라인에 해당하는 라인을 사용하여 새 템플릿 BOM이 생성됩니다.

## <a name="see-also"></a>참고 항목

[템플릿 BOM](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]