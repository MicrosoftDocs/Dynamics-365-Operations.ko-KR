---
title: 번호판 레이블 인쇄 사용
description: 이 토픽에서는 판매 피킹 작업 프로세스의 재고에서 마지막 품목을 피킹한 후 SSCC(일련 배송 컨테이너 코드) 레이블의 자동 인쇄를 활성화하는 방법을 보여줍니다.
author: perlynne
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b3895961f1f682a3fd06800a83a497afaf2fa65
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447793"
---
# <a name="enable-license-plate-label-printing"></a>번호판 레이블 인쇄 사용

[!include [banner](../../includes/banner.md)]

이 토픽에서는 판매 피킹 작업 프로세스의 재고에서 마지막 품목을 피킹한 후 SSCC(일련 배송 컨테이너 코드) 레이블의 자동 인쇄를 활성화하는 방법을 보여줍니다. 데모 데이터 회사 USMF에서 이 절차를 실행할 수 있습니다. 자신의 데이터를 사용하여 실행하는 경우 번호판에 대한 일련 번호를 설정해야 합니다. 이 작업을 시작하기 전에 라벨 프린터를 설정해야 합니다. 조직 관리 > 설정 > 네트워크 프린터로 이동합니다. 작업 창에서 옵션을 클릭한 다음 문서 라우팅 에이전트 설치 프로그램 다운로드 버튼을 클릭합니다. 설치 프로그램을 실행하고 절차를 계속하기 전에 작동하는 네트워크 프린터가 활성으로 설정되어 있는지 확인하세요.


## <a name="set-up-the-gs1-company-prefix"></a>GS1 회사 접두사 설정
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 창고 관리 매개 변수** 로 이동합니다.
2. **GS1 회사 접두사** 필드에 GS1 회사 번호 7자리를 입력합니다.
3. **저장** 을 선택합니다.
4. 페이지를 닫습니다

## <a name="setup-the-sscc-license-plate-number-sequence"></a>SSCC 번호판 번호 시퀀스 설정
1. **탐색 창 > 모듈 > 조직 관리 > 번호 시퀀스 > 번호 시퀀스** 로 이동합니다.
2. **영역** 필드에서 옵션을 선택합니다.
3. **참조** 필드에 옵션을 선택합니다.
4. **회사** 필드에 값을 입력합니다.
5. **세그먼트** 섹션을 펼칩니다.
6. **편집** 을 선택합니다.
7. **세그먼트** 테이블에서 행, 첫 번째 열을 선택합니다.
8. **제거** 를 선택합니다.
9. **제거** 를 선택합니다.
10. **저장** 을 선택합니다.
11. 페이지를 닫습니다

## <a name="create-the-document-route-layout"></a>문서 경로 레이아웃 만들기
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 문서 라우팅 > 문서 라우팅 레이아웃** 으로 이동합니다. SSCC 레이아웃을 활성화합니다.  
2. **새로 만들기** 를 선택합니다.
3. **레이아웃 ID** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **텍스트 끝에 삽입** 을 선택합니다.
6. **저장** 을 선택합니다.
7. 페이지를 닫습니다

## <a name="set-up-the-document-routing"></a>문서 라우팅 설정
1. **탐색 창 > 모듈 > 창고 관리 > 설정 > 문서 라우팅 > 문서 라우팅** 으로 이동합니다.
2. **작업 주문 유형** 필드에서 옵션을 선택합니다.
3. **새로 만들기** 를 선택합니다.
4. **창고** 필드에 값을 입력합니다.
5. **이름** 필드에 값을 입력합니다.
6. **새로 만들기** 를 선택합니다.
7. **레이아웃 ID** 필드에 값을 입력하거나 선택합니다.
8. **이름** 필드에 사용할 프린터 이름을 입력합니다.
9. **저장** 을 선택합니다.
10. 페이지를 닫습니다

## <a name="create-mobile-device-menu"></a>새 모바일 디바이스 메뉴 만들기
1. **탐색 창> 모듈 > 창고 관리 > 설정 > 모바일 디바이스 > 모바일 디바이스 메뉴 항목** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **메뉴 항목 이름** 필드에 값을 입력합니다.
4. **단위** 필드에 값을 입력합니다.
5. **모드** 필드에서 옵션을 선택합니다.
6. **기존 작업 사용** 필드에서 **예** 를 선택합니다.
7. **번호판 생성** 필드에서 **예** 를 선택합니다.
8. **작업 클래스** 섹션을 확장합니다.
9. **새로 만들기** 를 선택합니다.
10. **작업 클래스 ID** 필드에 값을 입력합니다.
11. **저장** 을 선택합니다.
12. 페이지를 닫습니다
13. **탐색 창> 모듈 > 창고 관리 > 설정 > 모바일 디바이스 > 모바일 디바이스 메뉴** 로 이동합니다.
14. 트리에서 이전에 생성한 메뉴 항목을 선택합니다.
15. **편집** 을 선택합니다.
16. 화살표를 선택하여 메뉴 항목을 메뉴에 추가합니다.
17. **저장** 을 선택합니다.
18. 페이지를 닫습니다

## <a name="update-a-work-template"></a>작업 템플릿 업데이트
1. **탐색 창에서 모듈 > 창고 관리 > 설정 > 작업 > 작업 템플릿** 으로 이동합니다.
2. **편집** 을 선택합니다.
3. **새로 만들기** 를 선택합니다.
4. **작업 유형** 필드에서 **인쇄** 를 선택합니다.
5. **작업 클래스 ID** 필드에서 값을 입력하거나 선택합니다.
6. **위로 이동** 을 선택합니다.
7. **저장** 을 선택합니다.
8. 페이지를 닫습니다



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]