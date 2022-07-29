---
title: ER 대상 구성
description: 이번에는 폴더나 파일과 같은 전자 보고(ER) 출력 구성 요소에 대해 다른 대상을 설정하고 사용하는 방법을 보여줍니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERFormatDestinationTable, SysLookupPicklist, ERFormatDestinationSettings, ERFormatDestinationEmailSettings, ERExpressionDesignerFormula, SRSPrintDestinationTokens
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1e679b52b28ff1ca117c5224fc7e2825feb26e5e5aea1c8b5bc3a88d1eaf235
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460714"
---
# <a name="er-configure-destinations"></a>ER 대상 구성

[!include [banner](../../includes/banner.md)]

이번에는 폴더나 파일과 같은 전자 보고(ER) 출력 구성 요소에 대해 다른 대상을 설정하고 사용하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 DEMF입니다. 독일은 법인 기본 주소의 국가\지역이지만 이 절차에는 모든 법인을 사용할 수 있습니다. 

이 예시에서 사용된 형식은 ISO20022 신용 전송이지만 이미 가져온 형식을 사용할 수 있습니다. 이번에는 단일 파일 및 단일 대상 설정의 예입니다. 전자 보고 대상 관리에 대한 자세한 내용은 Dynamics 365 Finance 도움말에서 찾을 수 있습니다.

1. 조직 관리 > 전자 보고 > 전자 보고 대상으로 이동합니다.
2. 새로 만들기를 클릭하여 형식에 대한 새 대상 집합을 만듭니다.
3. 참조 필드에서 대상을 구성할 형식을 선택합니다.
    * 선택할 값이 없으면 전자 보고 형식 구성을 가져오지 않았음을 의미합니다. 대상을 설정하기 전에 형식 구성을 가져와야 합니다.  
4. 새로 만들기를 클릭하여 새 파일 대상을 만듭니다.
    * 폴더나 파일과 같은 동일한 형식의 각 출력 구성 요소에 대해 하나의 파일 대상을 만들 수 있습니다. 설정에서 대상을 별도로 활성화 및 비활성화할 수 있습니다.  
5. 이름 필드에 출력 구성 요소의 사용자에게 친숙한 이름을 입력합니다.
    * '결제 파일' 또는 '제어 보고서'와 같은 의미 있는 이름을 사용하는 것이 좋습니다. 이러한 이름은 구성 런타임에 대상 설정과 함께 사용자에게 표시됩니다.  
6. 파일 이름에서 해당 형식에 해당하는 파일이나 폴더를 선택합니다.
7. 설정을 클릭합니다.
8. 게시 필드에서 예를 선택합니다.
    * 각 탭의 Enabled 확인란은 각 대상을 개별적으로 활성화 및 비활성화합니다. 이 예시에서는 파일이 생성될 때 출력 파일을 메일 수신자에게 보내는 것을 활성화합니다.  
9. 편집을 클릭하여 이메일 수신자를 설정합니다.
10. 추가를 클릭합니다.
11. 인쇄 관리 이메일을 클릭합니다.
12. 이메일 소스 필드에서 옵션을 선택하십시오.
    * 고객 또는 공급 업체 유형과 같은 다양한 이메일 소스 유형을 선택할 수 있습니다. 이것은 이메일 소스 계정 수식에 의해 반환될 인수 유형을 정의합니다. 다음 단계에서 설명하는 이메일 소스 계정 공식은 이메일 소스를 바인딩하는 위치입니다. 수식이 공급 업체 계정을 반환하는 경우 공급 업체를 선택합니다. ISO 20022 신용 이전 구성 예를 사용하는 경우 공급 업체를 사용하십시오.  
13. 이메일 소스 바인딩 버튼을 클릭합니다.
14. 공식에서 이전에 선택한 당사자 유형에 대한 문서별 참조를 입력합니다.
    * 입력하는 대신 당사자 계정을 나타내는 데이터 소스 노드를 찾고 데이터 소스 추가 버튼을 클릭하여 공식을 업데이트할 수 있습니다. 예를 들어 ISO 20022 신용 전송 구성을 사용하는 경우 공급 업체 계정을 나타내는 노드는 '$PaymentsForCoveringLetter'.Creditor.Identification.SourceID입니다. 그렇지 않으면 'DE-001'과 같은 스트링 값을 입력하여 수식을 저장합니다.  
15. 저장을 클릭합니다.
16. 페이지를 닫습니다.
17. 편집을 클릭하여 당사자의 연락처 세부 정보를 구성합니다.
18. 기본 연락처 필드에서 예를 선택합니다.
    * 다른 옵션을 사용하여 이 대상의 이메일 주소로 사용해야 하는 당사자의 연락처 유형을 지정할 수 있습니다. 이 예시에서는 기본 연락처를 사용합니다.  
19. '확인'을 클릭합니다.
20. '확인'을 클릭합니다.
21. 송장 필드에 값을 입력합니다.
22. '확인'을 클릭합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]