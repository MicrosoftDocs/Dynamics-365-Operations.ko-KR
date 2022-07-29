---
title: (RCS) 선택적 속성이 있는 XML 형식의 파일 가져오기
description: 이 항목에서는 선택적 속성이 포함된 XML 형식의 파일을 가져오기 위해 사용자가 ER 형식 구성을 디자인하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9447c827a02acb616bbfdcb2c7305e8bdd013c9811e28bb25256db056d85d6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460909"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) 선택적 속성이 있는 XML 형식의 파일 가져오기

[!include [banner](../../includes/banner.md)]

다음 단계는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 ER 형식 구성을 설계하여 선택적 특성이 포함된 XML 형식의 파일을 가져올 수 있습니다. 이 단계를 완료하려면 먼저 '구성 공급자를 만들고 활성으로 표시' 절차의 단계를 완료해야 합니다. 시작하기 전에 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=874684)에서 IncomingDocumentToLearnHowToHandleOptionalAttributes.xml 파일을 로컬로 다운로드하여 저장하세요.

1.    **조직 관리 작업 공간** > **전자 보고** 로 이동합니다.
2.    샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 **활성** 으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 [구성 공급자 만들기](er-configuration-provider-mark-it-active-2016-11.md) 절차의 단계를 완료하고 활성으로 표시합니다.
3.    **보고 구성** 을 클릭합니다.

## <a name="create-a-new-data-model-configuration"></a>새 데이터 모델 구성 만들기
1.    **구성 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
2.    **이름** 필드에 'xml 파일을 가져올 모델'을 입력합니다.
3.    **구성 만들기** 를 클릭합니다.
4.    **디자이너** 를 클릭합니다.
5.    **새로 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
6.    **이름** 필드에 '루트'를 입력합니다.
7.    **추가** 를 클릭합니다.
8.    **새로 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
9.    **이름** 필드에 '목록'을 입력합니다.
10.    **항목 유형** 필드에서 **기록 목록** 을 선택하십시오.
11.    **추가** 를 클릭합니다.
12.    **새로 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
13.    **이름** 필드에 '코드'를 입력합니다.
14.    **항목 유형** 필드에서 **스트링** 을 선택하십시오.
15.    **추가** 를 클릭합니다.
16.    **저장** 을 클릭합니다.
17.    페이지를 닫습니다.
18.    **상태 변경** 을 클릭합니다.
19.    **완료** 를 클릭합니다.
20.    **확인** 을 클릭합니다.

## <a name="create-a-format-for-data-import"></a>데이터 가져오기를 위한 형식 만들기
1.    **구성 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
2.    **새로 만들기** 필드에 'xml 파일을 가져올 데이터 모델 모델 기반 형식'을 입력합니다.
3.    **이름** 필드에 'xml 파일을 가져올 형식'을 입력합니다.
4.    **데이터 가져오기 지원** 필드에서 **예** 를 선택합니다.
5.    **구성 만들기** 를 클릭합니다.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>들어오는 파일을 xml 형식으로 구문 분석하는 형식 설계
1.    **디자이너** 를 클릭합니다.
2.    **루트 추가** 를 클릭하여 드롭 대화 상자를 엽니다.
3.    트리에서 **XML\요소** 를 선택합니다.
4.    **이름** 필드에 '루트'를 입력합니다.
5.    **확인** 을 클릭합니다.
6.    **추가** 를 클릭하여 드롭 대화 상자를 엽니다.
7.    트리에서 **XML\요소** 를 선택합니다.
8.    **이름** 필드에 '문서'를 입력합니다.
9.    **다수** 필드에서 **하나 많은** 을 선택합니다.
10.    **확인** 을 클릭합니다.
11.    트리에서 **루트\문서** 를 선택합니다.
12.    **추가** 를 클릭하여 드롭 대화 상자를 엽니다.
13.    트리에서 **XML\특성** 을 선택합니다.
14.    **이름** 필드에 'ID'를 입력합니다.
15.    **확인** 을 클릭합니다.
16.    **저장** 을 클릭합니다.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>구문 분석된 정보를 데이터 모델에 저장하기 위한 형식 매핑 설계
1. **모델에 형식 매핑** 을 클릭합니다.
2. **새로 만들기** 를 클릭합니다.
3. **정의** 필드에 값을 입력하거나 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. **이름** 필드에 '매핑'을 입력합니다.
6. **저장** 을 클릭합니다.
7. **디자이너** 를 클릭합니다.
8. 트리에서 **형식** 을 확장합니다.
9. 트리에서 **형식\루트: XML 요소(루트)** 를 확장합니다.
10.    트리에서 **형식\루트: XML 요소(루트)\문서: XML 요소 1..* (문서)**.
11.    **바인딩** 을 클릭합니다.
12.    트리에서 **형식\루트: XML 요소(루트)\문서: XML 요소 1..* (문서)**.
13.    트리에서 **형식\루트: XML 요소(루트)\문서: XML 요소 1..* (문서)\id**.
14.    트리에서 **목록 = 형식.루트.문서** 를 확장합니다.
15.    트리에서 **목록 = 형식.루트.문서\코드** 를 선택합니다.
16.    **바인딩** 을 클릭합니다.
17.    **저장** 을 클릭합니다.
18.    페이지를 닫습니다.
 
## <a name="run-format-mapping"></a>형식 매핑 실행
1. **실행** 을 클릭합니다.
2. **찾아보기** 를 클릭하고 **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** 을 선택합니다.
3. **확인** 을 클릭합니다.

> [!NOTE]
> 형식 디자인은 'document' 요소에 대한 'id' 속성이 있다고 가정하므로 선택한 파일을 가져오지 않았지만 가져온 파일에는 그러한 속성이 없습니다.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Xml 속성을 선택 사항으로 처리하도록 형식 구조 수정
1. 페이지를 닫습니다.
2. 트리에서 **루트\문서** 를 확장합니다.
3. 트리에서 **루트\문서\ID** 를 선택합니다.
4. **누락된 속성에 대한 빈 문자열** 필드에서 **예** 를 선택합니다.
5. **저장** 을 클릭합니다.
 
## <a name="run-format-mapping-to-test-changes"></a>변경 사항을 테스트하기 위해 형식 매핑 실행
1. **모델에 형식 매핑** 을 클릭합니다.
2. **실행** 을 클릭합니다.
3. **찾아보기** 를 클릭하고 **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** 파일을 선택합니다.
4. **확인** 을 클릭합니다.
5. 생성된 파일을 검토합니다. 

> [!NOTE]
> 형식 디자인이 이제 'document' 요소의 'id' 속성을 선택 사항으로 간주하므로 동일한 파일을 가져왔습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]