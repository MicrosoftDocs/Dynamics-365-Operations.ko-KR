---
title: 공급업체에 대한 소급 수표 등록 및 게시
description: 저널 바우처를 사용하여 공급업체에 수표를 발행하기 전에 기한이 지난 수표의 세부 정보를 등록할 수 있습니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ca63923a18ce531493e390ec3883910fe25b0fb4d4dc61203285a33bee2714e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450640"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>공급업체에 대한 소급 수표 등록 및 게시

[!include [banner](../../includes/banner.md)]

저널 바우처를 사용하여 공급업체에 수표를 발행하기 전에 기한이 지난 수표의 세부 정보를 등록할 수 있습니다. 또한 기한이 지난 수표를 게시하고 회계 트랜잭션을 생성할 수도 있습니다. 공급업체에서 기한이 지난 수표를 등록하고 게시하기 전에 다음 작업을 완료합니다. 

현금 및 은행 관리 페이지에서 기한이 지난 수표를 설정합니다. 



이 작업 가이드의 역할은 재무입니다. 이 작업에는 USMF 데모 회사를 사용합니다.

1. 지급 계정 > 결제 > 결제 저널로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 'VendPay'를 입력합니다.
4. 라인을 클릭합니다.
5. 계정 필드에서 원하는 값을 지정합니다.
6. 목록에서 선택한 행을 표시합니다.
7. 출금 필드에 숫자를 입력합니다.
8. 결제 방법 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
    * 기한이 지난 수표의 결제 방법을 선택합니다.  
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 목록에서 선택한 행의 링크를 클릭합니다.
11. 기한이 지난 수표 탭을 클릭합니다.
12. 수표 번호 필드에 값을 입력합니다.
    * 기한이 지난 수표 번호를 입력하거나 수정합니다.  
13. 발행 은행 이름 필드에 값을 입력합니다.
    * 발급 은행 이름 필드에 값을 입력합니다.  
14. 목록 탭을 클릭합니다.
15. 게시를 클릭합니다.
16. 페이지를 닫습니다
17. 기한이 지난 수표 탭을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]