---
title: 분개장에 대한 고급 규칙 만들기
description: 이 절차에서는 분개장에 대한 고급 규칙을 만드는 과정을 단계별로 진행합니다.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe26409ebaa83595885756056810a4a2037045f0f8ad312b52c507343dec3b2d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450862"
---
# <a name="create-advanced-rules-for-journals"></a>분개장에 대한 고급 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 절차에서는 분개장에 대한 고급 규칙을 만드는 과정을 단계별로 진행합니다. 여기에는 분개장 관리 및 사용자 전기 제한 설정이 포함됩니다. 이 절차에서는 USMF 데모 데이터 회사를 사용합니다.


## <a name="set-up-journal-control"></a>분개장 관리 설정
1. **탐색 창** 에서 **모듈 > 총계정원장 > 분개장 설정 > 분개장 이름** 으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. **작업 창** 에서 **분개장 관리** 를 클릭합니다.
4. **전기할 수 있는 계정 유형** 빠른 탭에서 **추가** 를 클릭합니다.
5. **회사 계정** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **이 분개장에 유효한 세그먼트 값** 빠른 탭에서 **추가** 를 클릭합니다.
9. **계정 구조** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
10. 목록에서 원하는 레코드를 찾아 선택합니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
12. **세그먼트** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
13. 목록에서 선택한 행의 링크를 클릭합니다.
14. **원본 값** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
15. 목록에서 원하는 레코드를 찾아 선택합니다.
16. 목록에서 선택한 행의 링크를 클릭합니다.
17. **대상 값** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
18. 목록에서 원하는 레코드를 찾아 선택합니다.
19. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="set-up-posting-restrictions"></a>전기 제한 설정
1. 페이지를 닫습니다.
2. **전기 제한** 을 클릭합니다.
3. **원하는 전기 제한 방법** 필드에서 '사용자 그룹별'을 선택합니다.
4. 트리에서 '이 분개장 이름에 대한 전기를 허용할 그룹'을 선택합니다.
5. **확인** 을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]