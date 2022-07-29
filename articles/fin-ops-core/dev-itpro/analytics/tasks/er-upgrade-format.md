---
title: ER 해당 형식의 새로운 기본 버전을 채택하여 형식 업그레이드
description: 이 항목에서는 전자 보고(ER) 형식 구성을 유지 관리하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bfcb85d964234063fd3c6a8e5ea29f7b222e966124b48e46b72b04f457c91e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460841"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a>ER 해당 형식의 새로운 기본 버전을 채택하여 형식 업그레이드

[!include [banner](../../includes/banner.md)]

다음 단계는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 전자 보고(ER) 형식 구성을 유지 관리할 수 있는 방법을 설명합니다. 이 절차에서는 CP(구성 제공자)로부터 받은 형식을 기반으로 사용자 지정 버전의 형식을 만드는 방법에 대해 설명합니다. 또한 해당 형식의 새로운 기본 버전을 채택하는 방법도 설명합니다.

이 단계를 완료하려면 먼저 "구성 제공자를 생성하고 활성으로 표시" 및 "생성된 형식을 사용하여 지불용 전자 문서 생성" 절차의 단계를 완료해야 합니다. 이 단계는 GBSI 회사에서 수행할 수 있습니다.

## <a name="select-format-configuration-for-customization"></a>사용자 정의를 위한 형식 구성 선택
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.

    이 예에서 샘플 회사 Litware, Inc.(https://www.litware.com)는 특정 국가의 전자 결제를 위한 형식 구성을 지원하는 구성 제공자 역할을 합니다.    샘플 회사 Proseware, Inc.(http://www.proseware.com)는 Litware, Inc.가 제공한 형식 구성의 소비자 역할을 합니다. Proseware, Inc.는 해당 국가의 특정 지역에서 형식을 사용합니다.  
2. 보고 구성을 클릭합니다.
3. 필터 표시를 클릭합니다.
4. 다음 필터를 적용합니다. "다음으로 시작" 필터 연산자를 사용하여 "이름" 필드에 "BACS(영국 가상)"의 필터 값을 입력하세요.
  
    선택한 형식 구성 BACS(영국 가상)는 공급자 Litware, Inc.가 소유합니다.  

5. 필터 표시를 클릭합니다.
6. 목록에서 원하는 기록을 찾아 선택합니다.

    완료됨 상태의 형식 버전은 사용자 지정을 위해 Proseware, Inc.에서 사용됩니다.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>전자 문서의 사용자 지정 형식에 대한 새 구성 만들기
Proseware, Inc.는 서비스 가입에 따라 Litware, Inc.로부터 전자 지불 문서를 생성하기 위한 초기 형식이 포함된 BACS(영국 가상) 구성 버전 1.1을 받았습니다. Proseware, Inc.는 이를 해당 국가의 표준으로 사용하기를 원하지만 특정 지역 요구 사항을 지원하려면 일부 사용자 지정이 필요합니다. Proseware, Inc.는 또한 Litware, Inc.에서 새 버전(새로운 국가별 요구 사항을 지원하기 위한 변경 포함)이 제공되는 즉시 사용자 지정 형식을 업그레이드할 수 있는 기능을 유지하기를 원하며 가장 낮은 비용으로 이 업그레이드를 수행하기를 원합니다.  

이를 위해 Proseware, Inc.는 Litware, Inc. 구성 BACS(영국 가상)를 기반으로 사용하여 구성을 생성해야 합니다.  

1. 페이지를 닫습니다.
2. Proseware, Inc.를 선택하여 활성 공급자로 만듭니다.
3. 활성으로 설정을 클릭합니다.
4. 보고 구성을 클릭합니다.
5. 트리에서 '결제(단순화된 모델)'를 확장합니다.
6. 트리에서 '결제(간략한 모델)\BACS(영국 가상)'를 선택합니다.

    Litware, Inc.에서 BACS(영국 가상) 구성을 선택합니다. Proseware, Inc.는 버전 1.1을 사용자 지정 버전의 기반으로 사용합니다.  

7. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.

    이를 통해 사용자 지정 지불 형식에 대한 새 구성을 만들 수 있습니다.  

8. 새로 만들기 필드에 '이름에서 파생: BACS(영국 가상), Litware, Inc.'를 입력합니다.

    파생 옵션을 선택하여 사용자 지정 버전을 만들기 위한 기반으로 BACS(영국 가상)의 사용을 확인합니다.  

9. 이름 필드에 'BACS(영국 가상 사용자 지정)'를 입력합니다.
10. 설명 필드에 'BACS 공급업체 결제(영국 가상 사용자 지정)'를 입력합니다.

    활성 구성 공급자(Proseware, Inc.)가 여기에 자동으로 입력됩니다. 이 공급자는 이 구성을 유지할 수 있습니다. 다른 공급자는 이 구성을 사용할 수 있지만 유지할 수는 없습니다.  

11. 구성 만들기를 클릭합니다.

## <a name="customize-your-format-for-the-electronic-document"></a>전자 문서의 형식 사용자 정의
1. 디자이너를 클릭합니다.
2. 펼치기/접기를 클릭합니다.
3. 펼치기/접기를 클릭합니다.
4. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank'를 선택합니다.
5. 추가를 클릭하여 드롭 대화 상자를 엽니다.
6. 트리에서 'XML\요소'를 선택합니다.
7. 이름 필드에 'IBAN'을 입력합니다.
8. 확인을 클릭합니다.
9. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'을 선택합니다.
10. 추가를 클릭하여 드롭 대화 상자를 엽니다.
11. 트리에서 '텍스트\문자열'을 선택합니다.
12. 확인을 클릭합니다.
13. 트리에서 'Xml\Message\Payments\Item\Vendor\Name\String'을 선택합니다.
14. 최대 길이 필드에 '60'을 입력합니다.
15. 매핑 탭을 클릭합니다.
16. 트리에서 '모델'을 확장합니다.
17. 트리에서 '모델\결제'를 확장합니다.
18. 트리에서 '모델\결제\채권자'를 확장합니다.
19. 트리에서 '모델\결제\채권자\계정'을 확장합니다.
20. 트리에서 '모델\결제\채권자\계정\IBAN'을 선택합니다.
21. 트리에서 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'을 선택합니다.
22. 바인딩을 클릭합니다.
23. 저장을 클릭합니다.

## <a name="validate-the-customized-format"></a>사용자 지정 형식 확인
1. 유효성 검사를 클릭합니다.

    사용자 지정된 형식 레이아웃과 데이터 매핑 변경 사항을 확인하여 모든 바인딩이 올바른지 확인합니다.  

2. 페이지를 닫습니다.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>사용자 정의 형식 구성의 현재 버전 상태 변경
지급 문서 생성에 사용할 수 있도록 설계된 형식 구성의 상태를 초안에서 완료로 변경합니다.  

1. 상태 변경을 클릭합니다.

    선택한 구성의 현재 버전은 초안 상태입니다.  

2. 완료를 클릭합니다.
3. 설명 필드에 값을 입력합니다.
4. 확인을 클릭합니다.
5. 목록에서 원하는 기록을 찾아 선택합니다.

    생성된 구성은 완료된 버전 1.1.1로 저장됩니다. 이는 결제(간체화된 모델) 데이터 모델의 버전 1을 기반으로 하는 BACS(영국 가상) 형식의 버전 1을 기반으로 하는 사용자 지정 BACS(영국 가상 사용자 지정) 형식의 버전 1임을 의미합니다.  

## <a name="test-the-customized-format-to-generate-payment-files"></a>지불 파일을 생성하기 위한 사용자 정의 형식 테스트
병렬 재무 및 운영 세션에서 "생성된 형식을 사용하여 지급용 전자 문서 생성" 절차의 단계를 완료합니다. 전자 지불 방법 매개변수에서 BACS(영국 가상 사용자 정의) 형식을 선택합니다. 생성된 결제 파일에 지역 요구 사항에 따라 IBAN 코드를 표시하는 최근에 도입된 XML 노드가 포함되어 있는지 확인합니다.  

## <a name="update-the-existing-country-specific-configuration"></a>기존 국가별 구성 업데이트
Litware, Inc.는 BACS(영국 가상) 구성을 업데이트하고 전자 문서 형식을 관리하기 위한 새로운 국가 요구 사항을 채택해야 합니다. 나중에 이것은 Proseware, Inc.를 포함한 서비스 가입자에게 제공될 이 구성의 새 버전에 포함될 것입니다.  

실제 서비스 제공 관련 프로세스에서 BACS(영국 가상)의 각 새 버전은 Litware, Inc. 구성의 LCS 저장소에서 Proseware, Inc.에서 가져올 수 있습니다. 이 절차에서는 서비스 공급자를 대신하여 BACS(영국 가상)를 업데이트하여 이를 시뮬레이션합니다.  

1. 페이지를 닫습니다.
2. Litware, Inc. 공급자를 선택합니다.
3. 활성으로 설정을 클릭합니다.
4. 보고 구성을 클릭합니다.
5. 트리에서 '결제(단순화된 모델)'를 확장합니다.
6. 트리에서 '결제(간략한 모델)\BACS(영국 가상)'를 선택합니다.

    Litware, Inc. 제공업체 BACS(영국 가상)가 소유한 초안 버전은 새로운 국가별 요구 사항을 지원하기 위해 변경 사항을 가져오기 위해 선택되었습니다.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>전자 문서의 기본 형식 현지화
Litware, Inc.에서 지원해야 하는 새로운 국가별 요구 사항이 있다고 가정합니다.  

- 각 지불 거래에서 채권자의 은행 SWIFT 코드 값.
- 생성 파일에서 공급업체 이름의 텍스트 길이는 100자로 제한됩니다.  
- 새로운 국가별 요구사항  
- 필요한 변경 사항을 적용하려면 원하는 구성의 초안 버전을 선택합니다.  


1. 디자이너를 클릭합니다.
2. 펼치기/접기를 클릭합니다.
3. 펼치기/접기를 클릭합니다.
4. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank'를 선택합니다.
5. 추가를 클릭하여 드롭 대화 상자를 엽니다.
6. 트리에서 'XML\요소'를 선택합니다.
7. 이름 필드에 'SWIFT'를 입력합니다.
8. 확인을 클릭합니다.
9. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'를 선택합니다.
10. 추가를 클릭하여 드롭 대화 상자를 엽니다.
11. 트리에서 '텍스트\문자열'을 선택합니다.
12. 확인을 클릭합니다.
13. 트리에서 'Xml\Message\Payments\Item\Vendor\Name\String'을 선택합니다.
14. 최대 길이 필드에 '100'을 입력합니다.
15. 매핑 탭을 클릭합니다.
16. 트리에서 '모델'을 확장합니다.
17. 트리에서 '모델\결제'를 확장합니다.
18. 트리에서 '모델\결제\채권자'를 확장합니다.
19. 트리에서 '모델\결제\채권자\에이전트'를 확장합니다.
20. 트리에서 '모델\결제\채권자\에이전트\SWIFT'를 선택합니다.
21. 트리에서 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'을 선택합니다.
22. 바인딩을 클릭합니다.
23. 저장을 클릭합니다.

## <a name="validate-the-localized-format"></a>현지화된 형식 확인
1. 유효성 검사를 클릭합니다.
2. 페이지를 닫습니다.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>기본 형식 구성의 현재 버전 상태 변경
업데이트된 기본 형식 구성의 상태를 초안에서 완료로 변경하여 지급 문서 생성 및 해당 문서에서 파생된 형식 구성 업데이트에 사용할 수 있도록 합니다.  

1. 상태 변경을 클릭합니다.

    선택한 구성의 현재 버전은 초안 상태입니다.  

2. 완료를 클릭합니다.
3. 설명 필드에 값을 입력합니다.
4. 확인을 클릭합니다.
5. 목록에서 원하는 기록을 찾아 선택합니다.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>사용자 지정 형식 구성의 기본 버전 변경

Proseware, Inc.는 최근 발표된 국가별 요구 사항에 따라 전자 지불 문서를 생성하기 위해 BACS(영국 가상) 구성의 새 버전 1.2를 사용할 수 있음을 알립니다. Proseware, Inc.는 이를 해당 국가의 표준으로 사용하기 시작했습니다.  

이를 위해 Proseware, Inc.는 사용자 지정 구성 BACS(영국 가상 사용자 지정)에 대한 기본 구성 버전을 변경해야 합니다. BACS(영국 가상)의 버전 1.1 대신 새 버전 1.2를 사용합니다.  

1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. Proseware, Inc. 공급자를 선택하여 활성으로 표시합니다.
3. 활성으로 설정을 클릭합니다.
4. 보고 구성을 클릭합니다.
5. 트리에서 '결제(단순화된 모델)'를 확장합니다.
6. 트리에서 '결제(간략한 모델)\BACS(영국 가상)'를 확장합니다.
7. 트리에서 '결제(간략한 모델)\BACS(영국 가상)\BACS(영국 가상 사용자 지정)'를 선택합니다.

    Proseware, Inc.가 소유한 BACS(영국 가상 사용자 지정) 구성을 선택합니다.  

    필요한 변경 사항을 적용하려면 선택한 구성의 초안 버전을 사용합니다.  

8. 리베이스를 클릭합니다.

    구성 업데이트를 위한 새 기반으로 적용할 기본 구성의 새 버전 1.2를 선택합니다.  

9. 확인을 클릭합니다.

    사용자 지정 버전과 새 기본 버전을 병합할 때 자동으로 병합할 수 없는 형식 변경으로 인해 일부 충돌이 발견되었습니다.  

## <a name="resolve-rebase-conflicts"></a>리베이스 충돌 해결
1. 디자이너를 클릭합니다.
    
    공급업체 이름 텍스트 길이 제한에 대한 변경 사항은 자동으로 해결할 수 없습니다. 따라서 이것은 충돌 목록에 표시됩니다. 업데이트 유형의 각 충돌에 대해 다음 옵션을 사용할 수 있습니다. - 이전 기본 값(그리드 상단의 버튼)을 적용하여 이전 기본 버전 값(이 경우 0)을 가져옵니다.  - 새 기본 버전 값(이 경우 100)을 가져오기 위해 기본 값(그리드 상단의 버튼)을 적용합니다.  - 자체(사용자 정의) 값을 유지합니다(이 경우 60).  공급업체 이름 텍스트 길이에 대해 국가별 제한인 100자를 적용하려면 기본 값 적용을 클릭합니다.  

    Proseware, Inc. 및 Litware, Inc.는 관리 형식에서 자동으로 병합되는 관련 구성 요소와 함께 IBAN 및 SWIFT 코드를 사용하는 이 형식의 사용자 지정 및 로컬 버전을 가지고 있습니다.  

2. 기본 값 적용을 클릭합니다.

    공급업체 이름에 대해 국가별 제한인 100자를 적용하려면 기본 값 적용을 클릭합니다.  

3. 저장을 클릭합니다.

    형식을 저장하면 충돌 목록에서 해결된 충돌이 제거됩니다.  

4. 페이지를 닫습니다.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>사용자 정의 형식 구성의 새 버전 상태 변경
1. 상태 변경을 클릭합니다.

    업데이트된 사용자 지정 형식 구성의 상태를 초안에서 완료로 변경합니다. 이렇게 하면 지불 문서 생성에 사용할 수 있는 형식 구성이 만들어집니다. 선택한 구성의 현재 버전은 초안 상태입니다.  

2. 완료를 클릭합니다.
3. 설명 필드에 값을 입력합니다.
4. 확인을 클릭합니다.

    생성된 구성은 완성된 버전 1.2.2: 기본 BACS(영국 가상 사용자 정의) 형식의 버전 2로 저장되며, 이는 지급 버전 1(간략한 모델) 데이터 모델을 기반으로 하는 기본 BACS(영국 가상) 형식의 버전 2를 기반으로 합니다.  

## <a name="test-the-customized-format-for-payment-files-generation"></a>지불 파일 생성을 위한 사용자 정의 형식 테스트
병렬 재무 및 운영 세션에서 "생성된 형식을 사용하여 지급용 전자 문서 생성" 절차의 단계를 완료합니다. 전자 지불 방법 매개변수에서 생성된 'BACS(영국 가상 사용자 정의)' 형식을 선택합니다. 생성된 결제 파일에 지역 요구 사항에 따라 IBAN 계정 코드를 표시하는 최근에 Proseware, Inc.에서 도입한 XML 노드가 포함되어 있는지 확인합니다. 파일에는 국가 요구 사항에 따라 SWIFT 은행 코드를 표시하는 Litware, Inc.에서 최근에 도입한 XML 노드도 포함되어야 합니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]