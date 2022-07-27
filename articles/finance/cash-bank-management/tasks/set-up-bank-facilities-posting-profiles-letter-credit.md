---
title: 신용장에 대한 은행 시설 및 게시 프로필 설정
description: 이 절차는 은행 시설을 만들고 신용장을 처리하는 데 필요한 프로필을 게시하는 과정을 안내합니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cdfceef4099a8f2ebfde22949d6439dfc623ac153578265da5bfb4052ee639d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450469"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>신용장에 대한 은행 시설 및 게시 프로필 설정

[!include [banner](../../includes/banner.md)]

이 절차는 은행 시설을 만들고 신용장을 처리하는 데 필요한 프로필을 게시하는 과정을 안내합니다. 

이 작업은 데모 회사 'USMF'를 사용합니다.






## <a name="general-ledger-parameter"></a>총계정원장 매개 변수
1. 현금 및 은행 관리 > 설정 > 현금 및 은행 관리 매개 변수로 이동합니다.
2. 은행 문서 섹션을 확장합니다.
3. 신용장 가져오기 활성화 옵션을 선택합니다.
4. 신용장 내보내기 활성화 옵션을 선택합니다.
5. 저장을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="create-bank-facility"></a>은행 시설 작성
1. 현금 및 은행 관리 > 설정 > 은행 시설로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 시설 그룹 필드에 은행 시설 그룹 이름을 입력합니다.
4. 설명 필드에 은행 시설 그룹 설명을 입력합니다.
5. 저장을 클릭합니다.
6. 시설 유형 탭을 클릭합니다.
7. 새로 만들기를 클릭합니다.
8. 시설 유형 필드에 고유 코드를 입력합니다.
9. 설명 필드에 값을 입력합니다.
10. 시설 그룹 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
11. 목록에서 원하는 레코드를 찾아 선택합니다.
12. 목록에서 선택한 행의 링크를 클릭합니다.
13. 시설 특성 필드에서 은행 시설의 특성을 선택합니다.
14. 저장을 클릭합니다.
15. 페이지를 닫습니다.

## <a name="bank-posting-profile"></a>은행 게시 프로필
1. 현금 및 은행 관리 > 설정 > 은행 문서 게시 프로필로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 계정/그룹 번호 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 정산을 위한 주 계정을 선택합니다.
    * 이 계정은 현금 흐름 예측을 계산할 때 사용됩니다.  
7. 요금 계정 필드에서 비용 거래 계정을 선택합니다.
8. 마진 계정 필드에서 마진 거래 계정을 선택합니다.
    * 이 계정은 개시 마진이 게시될 때 차변에 기입되고 지불이 게시될 때 대변에 기입됩니다.  
9. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]