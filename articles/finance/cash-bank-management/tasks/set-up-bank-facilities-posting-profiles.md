---
title: 수입화물선취보증서에 대한 은행 시설 및 게시 프로필 설정
description: 이 작업은 수입화물선취보증서를 처리하는 데 필요한 은행 시설 및 게시 프로필을 작성합니다.
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
ms.openlocfilehash: 1a7e60903e31d98e24f578dc381bb0b140944e07a88516a6a81bbba1b8981982
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450436"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>수입화물선취보증서에 대한 은행 시설 및 게시 프로필 설정

[!include [banner](../../includes/banner.md)]

이 작업은 수입화물선취보증서를 처리하는 데 필요한 은행 시설 및 게시 프로필을 작성합니다.



이 작업에는 USMF 데모 회사를 사용합니다. 




## <a name="general-ledger-parameter"></a>총계정원장 매개 변수
1. 현금 및 은행 관리 > 설정 > 현금 및 은행 관리 매개 변수로 이동합니다.
2. 은행 문서 섹션을 확장합니다.
3. 수입화물선취보증서 활성화 옵션을 선택합니다.
4. 거래 분개장 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 번호 시퀀스 탭을 클릭합니다.
    * 수입화물선취보증서 번호 및 수입화물선취보증서 거래 참조에 대한 번호 시퀀스 코드 정의  
8. 저장을 클릭합니다.
9. 페이지를 닫습니다.

## <a name="create-bank-facility"></a>은행 시설 작성
1. 현금 및 은행 관리 > 설정 > 은행 시설로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 시설 그룹 필드에 수입화물선취보증서 거래에 대한 은행 시설 그룹 이름을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 저장을 클릭합니다.
6. 시설 유형 탭을 클릭합니다.
7. 새로 만들기를 클릭합니다.
8. 시설 유형 필드에 은행 시설 계약과 관련된 은행 시설 유형의 이름을 입력합니다.
9. 설명 필드에 값을 입력합니다.
10. 시설 그룹 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
11. 목록에서 원하는 레코드를 찾아 선택합니다.
12. 목록에서 선택한 행의 링크를 클릭합니다.
13. 시설 특성에서 옵션을 선택합니다.
14. 저장을 클릭합니다.
15. 페이지를 닫습니다.

## <a name="bank-posting-profile"></a>은행 게시 프로필
1. 현금 및 은행 관리 > 설정 > 은행 문서 게시 프로필로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 계정/그룹 번호 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 정산 계정 필드에서 정산할 주 계정을 선택합니다.
7. 요금 계정 필드에서 비용 거래 계정을 선택합니다.
8. 마진 계정 필드에서 마진 거래를 위한 계정을 선택합니다.
9. 청산 계정 필드에서 수입화물선취보증서 거래에 대한 청산 계정을 선택합니다. 
10. 저장을 클릭합니다.
11. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]