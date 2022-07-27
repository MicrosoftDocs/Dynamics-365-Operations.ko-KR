---
title: 청구서 송장 승인
description: 이 항목은 공급업체 송장의 모바일 승인을 활용 사례로 사용하여 모바일 시나리오를 설계하는 실용적인 접근 방식을 제공하기 위한 것입니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 83d95ef6d9fcff060ac992b11ab5773af075fea5409e43430b4826dc097570c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450391"
---
# <a name="mobile-invoice-approvals"></a>청구서 송장 승인

[!include [banner](../includes/banner.md)]

비즈니스 사용자는 모바일 기능으로 모바일 환경을 디자인할 수 있습니다. 고급 시나리오의 경우 개발자는 플랫폼을 통해 원하는 대로 기능을 확장할 수도 있습니다. 모바일에서 몇 가지 새로운 개념을 배우는 가장 효과적인 방법은 몇 가지 시나리오를 디자인하는 과정을 거치는 것입니다. 이 항목은 공급업체 송장의 모바일 승인을 활용 사례로 사용하여 모바일 시나리오를 설계하는 실용적인 접근 방식을 제공하기 위한 것입니다. 이 항목은 시나리오의 다른 변형을 디자인하는 데 도움이 되며 공급업체 송장과 관련이 없는 다른 시나리오에도 적용할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

| 전제 조건                                                                                            | 설명                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 모바일 핸드북 미리 읽기                                                                                |[모바일 플랫폼](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | 버전 1611 및 플랫폼 업데이트 3(2016년 11월)이 있는 환경                   |
| 핫픽스 KB 3204341을 설치합니다.                                                                              | 작업 레코더가 드롭다운 대화 상자에 대해 두 개의 닫기 명령을 잘못 기록할 수 있습니다. 플랫폼 업데이트 3(2016년 11월 업데이트)에 포함되어 있습니다. |
| 핫픽스 KB 3207800을 설치합니다.                                                                              | 이 핫픽스를 사용하면 모바일 클라이언트에서 첨부 파일을 볼 수 있습니다. 플랫폼 업데이트 3(2016년 11월 업데이트)에 포함되어 있습니다.           |
| 핫픽스 KB 3208224를 설치합니다.                                                                              | 모바일 공급업체 송장 승인 애플리케이션의 애플리케이션 코드입니다. 버전 7.0.1(2016년 5월)에 포함되어 있습니다.                          |
| 모바일 앱이 설치된 Android 또는 iOS 또는 Windows 디바이스. | 해당 앱 스토어에서 앱을 검색합니다.                                                                                                                     |

## <a name="introduction"></a>소개
공급업체 송장을 위한 모바일 승인에는 "전제 조건" 섹션에 나온 세 가지 핫픽스가 필요합니다. 이러한 핫픽스가 송장 승인을 위한 작업 영역을 제공하는 것은 아닙니다. 모바일 컨텍스트의 작업 영역이 무엇인지 알아보려면 "전제 조건" 섹션에 언급된 모바일 핸드북을 읽어보세요. 송장 승인 작업 영역을 디자인해야 합니다. 

모든 조직이 공급업체 송장에 대한 비즈니스 프로세스를 다르게 조정하고 정의합니다. 공급업체 송장 승인을 위한 모바일 환경을 디자인하기 전에 비즈니스 프로세스의 다음 측면을 고려해야 합니다. 이러한 데이터 포인트를 가능한 한 많이 사용하여 디바이스에서 사용자 경험을 최적화하는 것이 좋습니다.

-   사용자가 모바일 환경에서 송장 헤더의 어떤 필드를 어떤 순서로 보려고 합니까?
-   사용자가 모바일 환경에서 송장 라인의 어떤 필드를 어떤 순서로 보려고 합니까?
-   송장에는 몇 개의 송장 라인이 있습니까? 여기에 80-20 규칙을 적용하고 80%를 최적화합니다.
-   사용자는 검토 중에 모바일 디바이스에서 회계 분포(송장 코딩)를 보려고 합니까? 이 질문에 대한 대답이 예인 경우 다음 질문을 고려합니다.
    -   송장 라인에 대한 회계 분포(총 금액, 판매세, 요금, 분할 등)는 몇 개나 있습니까? 여기에도 80-20 규칙을 적용합니다.
    -   송장의 송장 헤더에도 회계 분포가 있습니까? 그렇다면 이러한 회계 분포를 디바이스에서 사용할 수 있어야 합니까?

    > [!NOTE]
    > 이 기능은 현재 모바일 시나리오에서 지원되지 않으므로 이 항목에서는 회계 분포를 편집하는 방법은 설명하지 않습니다.

-   사용자가 디바이스에서 송장의 첨부 파일을 보기 원합니까?

송장 승인을 위한 모바일 환경의 디자인은 이러한 질문에 대한 답변에 따라 달라집니다. 목표는 조직이 모바일에서 비즈니스 프로세스에 대한 사용자 환경을 최적화하는 것입니다. 이 항목의 나머지 부분에서는 앞의 질문에 대한 서로 다른 답변을 기반으로 두 가지 시나리오 변형을 살펴보겠습니다. 

일반적인 지침으로 모바일 디자이너와 작업할 때 업데이트 손실을 방지하기 위해 변경 사항을 '게시'해야 합니다.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Contoso에 대한 간단한 송장 승인 시나리오 디자인
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오 특성</th>
<th>답변</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>사용자가 모바일 환경에서 송장 헤더의 어떤 필드를 어떤 순서로 보려고 합니까?</td>
<td><ol>
<li>공급업체 이름</li>
<li>송장 합계</li>
<li>송장 계정</li>
<li>송장 번호</li>
<li>송장 날짜</li>
<li>송장 설명</li>
<li>마감일</li>
<li>송장 통화</li>
</ol></td>
</tr>
<tr class="even">
<td>사용자가 모바일 환경에서 송장 라인의 어떤 필드를 어떤 순서로 보려고 합니까?</td>
<td><ol>
<li>조달 범주</li>
<li>수량</li>
<li>단가</li>
<li>라인 순액</li>
<li>1099 금액</li>
</ol></td>
</tr>
<tr class="odd">
<td>송장에는 몇 개의 송장 라인이 있습니까? 여기에 80-20 규칙을 적용하고 80%를 최적화합니다.</td>
<td>1</td>
</tr>
<tr class="even">
<td>사용자는 검토 중에 모바일 디바이스에서 회계 분포(송장 코딩)를 보려고 합니까?</td>
<td>예</td>
</tr>
<tr class="odd">
<td>송장 라인에 대한 회계 분포(총 금액, 판매세, 요금 등)는 몇 개나 있습니까? 여기에도 80-20 규칙을 적용합니다.</td>
<td>총 금액: 2 판매세: 0 요금: 0</td>
</tr>
<tr class="even">
<td>송장의 송장 헤더에도 회계 분포가 있습니까? 그렇다면 이러한 회계 분포를 디바이스에서 사용할 수 있어야 합니까?</td>
<td>사용하지 않음</td>
</tr>
<tr class="odd">
<td>사용자가 디바이스에서 송장의 첨부 파일을 보기 원합니까?</td>
<td>예</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>작업 영역 만들기

1.  브라우저에서 애플리케이션에 로그인합니다.
2.  로그인한 후 다음 예와 같이 URL에 **&mode=mobile** 을 추가하고 페이지를 새로 고칩니다. https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  페이지 오른쪽 상단의 **설정**(톱니바퀴) 버튼을 클릭한 다음 **모바일 앱** 을 클릭합니다. 모바일 앱 디자이너는 작업 레코더가 표시되는 것처럼 표시될 것입니다.
4.  **추가** 를 클릭하여 새 작업 영역을 만듭니다. 이 예에서는 작업 영역의 이름 **내 승인** 으로 지정합니다.
5.  설명을 입력합니다.
6.  작업 영역 색상을 선택합니다 작업 영역 색상은 이 작업 영역에 대한 모바일 환경의 전체 스타일에 사용됩니다.
7.  작업 영역의 아이콘을 선택합니다.
8.  **완료** 를 클릭합니다
9.  **작업 영역 게시** 를 클릭하여 변경 내용을 저장합니다

### <a name="vendor-invoices-assigned-to-me"></a>나에게 할당된 공급업체 송장

디자인해야 하는 첫 번째 모바일 페이지는 검토를 위해 사용자에게 할당된 송장 목록입니다. 이 모바일 페이지를 디자인하려면 **VendMobileInvoiceAssignedToMeListPage** 페이지를 사용합니다. 이 절차를 완료하기 전에 검토를 위해 하나 이상의 공급업체 송장이 지정되고 송장 라인에 두 개의 분포가 있는지 확인하세요. 이 설정은 이 시나리오의 요구 사항을 충족합니다.

1.  URL에서 메뉴 항목의 이름을 **VendMobileInvoiceAssignedToMeListPage** 로 대체하여 **지급 계정** 모듈에서 **나에게 할당된 보류 중인 공급업체 송장** 목록 페이지의 모바일 버전을 엽니다. 시스템에서 자신에 할당된 송장 수에 따라 이 페이지에 해당 송장이 표시됩니다. 특정 송장을 찾으려면 왼쪽에 있는 필터를 사용할 수 있습니다. 그러나 이 예에서는 특정 송장이 필요하지 않습니다. 모바일 페이지를 디자인할 수 있는 송장을 할당하기만 하면 됩니다. 사용 가능한 새 페이지는 공급업체 송장에 대한 모바일 시나리오 개발을 위해 특별히 설계되었습니다. 따라서 이러한 페이지를 사용해야 합니다. URL은 다음 URL과 비슷할 것이며 입력한 후 그림에 표시된 페이지가 열릴 것입니다. https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![나에게 할당된 보류 중인 공급업체 송장 페이지.](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  페이지 오른쪽 상단의 **설정**(톱니바퀴) 버튼을 클릭한 다음 **모바일 앱** 을 클릭합니다
3.  작업 영역을 선택하고 **편집** 을 클릭합니다
4.  **페이지 추가** 를 클릭하여 첫 번째 모바일 페이지를 만듭니다.
5.  **내 공급업체 송장** 과 같은 이름과 **검토를 위해 나에게 할당된 공급업체 송장** 과 같은 설명을 입력합니다.
6.  **완료** 를 클릭합니다.
7.  모바일 디자이너의 **필드** 탭에서 **필드 선택** 을 클릭합니다. 목록 페이지의 열이 다음 그림과 비슷해야 합니다. 

    [![나에게 할당된 보류 중인 공급업체 송장 페이지의 열.](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  모바일 페이지에서 사용자에게 표시되어야 하는 필수 열을 목록 페이지에서 추가합니다. 추가하는 순서대로 필드가 최종 사용자에게 표시됩니다. 필드의 순서를 변경하는 유일한 방법은 모든 필드를 다시 선택하는 것입니다. 이 시나리오의 요구 사항에는 다음 8개 필드가 필요합니다. 그러나 일부 사용자는 8개 필드는 모바일 디바이스에는 너무 많은 정보라고 생각할 수 있습니다. 따라서 모바일 목록 보기에서는 가장 중요한 필드만 표시합니다. 나머지 필드는 나중에 디자인할 세부 정보 보기에 표시됩니다. 지금은 다음 필드를 추가합니다. 이러한 열에서 더하기 기호(**+**)를 클릭하여 모바일 페이지에 추가합니다.
    - 공급업체 이름
    - 송장 합계
    - 송장 계정
    - 송장 번호
    - 송장 날짜

    필드를 추가한 후 모바일 페이지는 다음 그림과 비슷할 것입니다. 
    
    [![필드가 추가된 후 페이지.](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  나중에 워크플로 작업을 활성화할 수 있도록 지금 다음 열도 추가해야 합니다.
    - 완료 작업 표시
    - 위임 작업 표시
    - 회수 작업 표시
    - 거부 작업 표시
    - 요청 완료 작업 표시
    - 다시 제출 작업 표시

10. **완료** 를 클릭하여 편집 모드를 종료합니다.
11. **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다
12. **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다.
13. **송장** 아래의 지급 계정 매개 변수 양식에서 **보류 중인 공급업체 송장 목록에 송장 합계 표시** 를 활성화합니다. 이 매개 변수를 활성화하는 경우에만 송장 합계가 계산되어 보류 중인 공급업체 송장 목록 페이지에 표시됩니다. 이는 전제 조건인 핫픽스 3208224에 포함된 새로운 기능입니다.

### <a name="vendor-invoice-details"></a>공급업체 총상 세부 정보

모바일용 송장 세부 정보 페이지를 디자인하는 데는 **VendMobileInvoiceHeaderDetails** 페이지를 이용합니다. 이 페이지에는 시스템에 있는 송장의 수에 따라 가장 오래된 송장(가장 먼저 작성된 송장)이 표시됩니다. 특정 송장을 찾으려면 왼쪽에 있는 필터를 사용할 수 있습니다. 그러나 이 예에서는 특정 송장이 필요하지 않습니다. 모바일 페이지를 디자인하려면 약간의 송장 데이터가 필요합니다. 

[![워크플로 페이지.](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. URL에서 메뉴 항목의 이름을 **VendMobileInvoiceHeaderDetails** 로 대체하여 양식을 엽니다

2. **설정**(톱니바퀴) 버튼으로 모바일 디자이너를 엽니다.

3. **편집** 버튼을 클릭하여 작업 영역에서 편집 모드를 시작합니다.

4. 이전에 만든 **내 공급업체 송장** 페이지를 선택한 다음 **편집** 을 클릭합니다.

5. **필드** 탭에서 **그리드** 열 머리글을 클릭합니다.

6. **속성 &gt; 페이지 추가** 를 클릭합니다. **참고:** **그리드** 머리글을 클릭하고 페이지를 추가하면 세부 정보 페이지와의 관계가 자동으로 설정됩니다.

7. **송장 세부 정보** 와 같은 페이지 제목과 **송장 헤더 및 라인 세부 정보 보기** 와 같은 설명을 입력합니다.

8. **필드 선택** 을 클릭합니다. 필드는 추가하는 순서대로 최종 사용자에게 표시됩니다. 필드의 순서를 변경하는 유일한 방법은 모든 필드를 다시 선택하는 것입니다. 

9. 이 시나리오의 요구 사항에 따라 헤더에서 다음 필드를 추가합니다.
   - 공급업체 이름
   - 송장 합계
   - 송장 계정
   - 송장 번호
   - 송장 날짜
   - 송장 설명
   - 마감일
   - 송장 통화

10. 페이지의 라인 그리드에서 다음 필드를 추가합니다.
    - 조달 범주
    - 수량
    - 단가
    - 라인 순액
    - 1099 금액

11. 이전 두 단계의 모든 필드를 추가한 후 **완료** 를 클릭합니다. 페이지가 다음 그림과 비슷해야 합니다.
    
    [![추가된 필드를 보여주는 그림.](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. **완료** 를 클릭하여 편집 모드를 종료합니다.

13. **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다

14. **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다

### <a name="workflow-actions"></a>워크플로 작업

워크플로 작업을 추가하는 데는 **VendMobileInvoiceHeaderDetails** 페이지를 사용합니다. 이 페이지를 열려면 이전과 마찬가지로 URL의 메뉴 항목 이름을 바꿉니다. 그런 다음 **설정**(톱니바퀴) 버튼으로 모바일 디자이너를 엽니다. 다음 단계에 따라 세부 정보 페이지에 워크플로 작업을 추가합니다. 적절한 상태의 송장이 할당되어 있어야 디자인하려는 워크플로 작업을 사용할 수 있습니다.

#### <a name="record-workflow-actions"></a>워크플로 작업 기록
1.  **편집** 버튼을 클릭하여 작업 영역에서 편집 모드를 시작합니다.
2.  이전에 만든 **송장 세부 정보** 페이지를 선택한 다음 **편집** 을 클릭합니다.
3.  **작업** 탭에서 **작업 추가** 를 클릭합니다.
4.  **승인** 과 같은 작업 제목을 입력하고 **송장 승인** 과 같은 설명을 입력합니다. 여기에 입력하는 작업 제목은 모바일 앱에서 사용자에게 표시되는 작업의 이름이 됩니다.
5.  **완료** 를 클릭합니다.
6.  **필드 선택** 을 클릭합니다.
7.  **VendMobileInvoiceHeaderDetails** 페이지의 워크플로 프로세스를 진행하고 기록하려는 작업을 완료합니다. 코멘트 필드가 모바일 환경에도 포함되도록 이 프로세스 중에 워크플로 코멘트를 입력해야 합니다.
8.  워크플로 작업이 실행된 후 **완료** 를 클릭하여 필드 선택 작업을 완료합니다.
9.  **완료** 를 클릭하여 편집 모드를 종료합니다.
10. **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다
11. **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다
12. 필요한 모든 워크플로 작업을 기록하려면 이전 단계를 반복합니다. 

#### <a name="create-a-js-file"></a>.js 파일 만들기
1. 메모장 또는 Microsoft Visual Studio를 열고 다음 코드를 붙여넣습니다. 파일을 .js 파일로 저장합니다. 이 코드는 다음 작업을 합니다.
    - 이전에 모바일 목록 페이지에 추가한 추가 워크플로 관련 열을 숨깁니다. 앱이 컨텍스트에서 해당 정보를 갖고 다음 단계를 수행할 수 있도록 이러한 열을 추가했습니다.
    - 활성화된 워크플로 단계를 기반으로 해당 작업만 표시하는 논리를 적용합니다.

    > [!NOTE]
    > 코드에서 페이지 및 기타 컨트롤 이름은 작업 영역의 이름과 같아야 합니다.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  **논리** 탭을 선택하여 코드 파일을 작업 영역으로 업로드합니다
3.  **완료** 를 클릭하여 편집 모드를 종료합니다.
4.  **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다
5.  **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다

### <a name="vendor-invoice-attachments"></a>공급업체 송장 첨부 파일

1. 페이지 오른쪽 상단의 **설정**(톱니바퀴) 버튼을 클릭한 다음 **모바일 앱** 을 클릭합니다

2. **편집** 버튼을 클릭하여 작업 영역에서 편집 모드를 시작합니다.

3. 이전에 만든 <strong>송장 세부 정보</strong> 페이지를 선택한 다음 **편집**을 클릭합니다.

4. 아래와 같이 **문서 관리** 옵션을 **예** 로 설정합니다. **참고:** 모바일 장치에 첨부 파일을 표시해야 하는 요구 사항이 없는 경우 이 옵션을 기본 설정인 **아니요** 로 둘 수 있습니다.
   
   ![문서 관리.](./media/docmanagement-216x300.png)

5. **완료** 를 클릭하여 편집 모드를 종료합니다.

6. **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다

7. **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다

### <a name="vendor-invoice-line-distributions"></a>공급업체 송장 라인 분포

이 시나리오의 요구 사항은 라인 수준 분포만 있고 송장에는 항상 하나의 라인만 있는 것입니다. 이 시나리오는 간단하므로 모바일 디바이스의 사용자 환경도 사용자가 분포를 보기 위해 여러 수준을 드릴다운할 필요가 없을 정도로 간단해야 합니다. 공급업체 송장에는 송장 헤더의 모든 분포를 표시하는 옵션이 있습니다. 이 환경이 모바일 시나리오에 필요한 것입니다. 따라서 모바일 시나리오의 이 부분을 디자인하기 위해 **VendMobileInvoiceAllDistributionTree** 페이지를 사용합니다. 

> [!NOTE] 
> 요구 사항을 알면 시나리오를 디자인할 때 사용할 특정 페이지와 사용자의 모바일 환경을 정확히 최적화하는 방법을 결정하는 데 도움이 됩니다. 두 번째 시나리오에서는 해당 시나리오의 요구 사항이 다르므로 다른 페이지를 사용하여 분포를 표시합니다.

1.  이전과 마찬가지로 URL에서 메뉴 항목의 이름을 바꿉니다. 다음 그림과 비슷한 페이지가 표시될 것입니다.

    [![모든 분포 페이지.](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  **설정**(톱니바퀴) 버튼으로 모바일 디자이너를 엽니다.

3.  **편집** 버튼을 클릭하여 작업 영역에서 편집 모드를 시작합니다. **참고:** 두 개의 새 페이지가 자동으로 생성된 것을 볼 수 있습니다. 시스템에서 이러한 페이지를 만드는 이유는 이전 섹션에서 문서 관리를 설정했기 때문입니다. 이러한 새 페이지는 무시해도 됩니다.

4.  **페이지 추가** 를 클릭합니다.

5.  **회계 보기** 와 같은 페이지 제목과 **송장에 대한 회계 보기** 와 같은 설명을 입력합니다.

6.  **완료** 를 클릭합니다.

7.  **필드** 탭에서 **필드 선택** 을 클릭하고 분포 페이지에서 다음 필드를 선택한 다음 **완료** 를 클릭합니다.
    1.  금액
    2.  통화
    3.  원장 계정

    > [!NOTE] 
    > 분포 그리드에서 **설명** 열은 선택하지 않았는데, 이 시나리오의 요구 사항에 따라 총 금액이 분포 대상이 되는 유일한 금액이기 때문입니다. 따라서 사용자는 분포 대상 금액 유형을 결정하기 위해 다른 필드가 필요하지 않습니다. 그러나 다음 시나리오에서는 이 정보를 **사용** 하는데 해당 시나리오의 요구 사항은 다른 금액 유형에 분포(예: 판매세)가 있다고 지정하기 때문입니다.

8.  **완료** 를 클릭하여 편집 모드를 종료합니다.

9.  **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다

10. **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다

#### <a name="adding-navigation-to-view-accounting-page"></a>"회계 보기" 페이지에 탐색 추가

**회계 보기** 모바일 페이지는 우리가 지금까지 디자인한 모바일 페이지에 연결되어 있지 않습니다. 사용자는 모바일 디바이스의 **송장 세부 정보** 페이지에서 **계정 보기** 페이지로 이동할 수 있어야 하므로 **송장 세부 정보** 페이지에서 **계정 보기** 페이지로의 탐색을 제공해야 합니다. JavaScript를 사용한 추가 논리로 이 탐색을 설정합니다.

1.  앞에서 만든 .js 파일을 열고 다음 코드에서 강조 표시된 줄을 추가합니다. 이 코드는 두 가지 작업을 합니다.
    1.  사용자가 작업 공간에서 **계정 보기** 페이지로 직접 이동할 수 없도록 합니다.
    2.  **송장 세부 정보** 페이지에서 **회계 보기** 페이지로의 탐색 제어를 설정합니다.

    > [!NOTE] 
    > 코드에서 페이지 및 기타 컨트롤 이름은 작업 영역의 이름과 같아야 합니다.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  **논리** 탭을 선택하여 작업 영역에 코드 파일을 업로드하고 이전 코드를 덮어씁니다
3.  **완료** 를 클릭하여 편집 모드를 종료합니다.
4.  **뒤로** 를 클릭하고 **완료** 를 클릭하여 작업 영역을 종료합니다
5.  **작업 영역 게시** 를 클릭하여 작업 내용을 저장합니다

### <a name="validation"></a>유효성 검사

모바일 디바이스에서 앱을 열고 인스턴스에 연결합니다. 검토를 위해 공급업체 송장이 할당된 회사에 로그인합니다. 다음 작업을 수행할 수 있을 것입니다.

-   **내 승인** 작업 영역을 봅니다.
-   **내 승인** 작업 영역으로 드릴하고 **내 공급업체 송장** 페이지를 봅니다.
-   **내 공급업체 송장** 페이지로 드릴하고 할당된 송장 목록을 봅니다.
-   송장 중 하나로 드릴하고 송장 헤더 세부 정보와 라인 세부 정보를 봅니다.
-   세부 정보 페이지에서 첨부 파일에 대한 링크를 확인하고 이 링크를 사용하여 첨부 파일 목록으로 이동하여 첨부 파일을 봅니다.
-   세부 정보 페이지에서 **회계 보기** 페이지에 대한 링크를 보고 이 링크를 사용하여 분포 페이지로 이동하고 분포를 봅니다.
-   세부 정보 페이지 하단의 **작업** 메뉴를 클릭하고 워크플로 단계에 해당하는 워크플로 작업을 수행합니다.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Fabrikam에 대한 복잡한 송장 승인 시나리오 디자인
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오 특성</th>
<th>답변</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>사용자가 모바일 환경에서 송장 헤더의 어떤 필드를 어떤 순서로 보려고 합니까?</td>
<td><ol>
<li>공급업체 이름</li>
<li>송장 금액</li>
<li>송장 계정</li>
<li>송장 번호</li>
<li>송장 날짜</li>
<li>송장 설명</li>
<li>마감일</li>
<li>송장 통화</li>
</ol></td>
</tr>
<tr class="even">
<td>사용자가 모바일 환경에서 송장 라인의 어떤 필드를 어떤 순서로 보려고 합니까?</td>
<td><ol>
<li>조달 범주</li>
<li>수량</li>
<li>단가</li>
<li>라인 순액</li>
<li>1099 금액</li>
</ol></td>
</tr>
<tr class="odd">
<td>송장에는 몇 개의 송장 라인이 있습니까? 여기에 80-20 규칙을 적용하고 80%를 최적화합니다.</td>
<td>5</td>
</tr>
<tr class="even">
<td>사용자는 검토 중에 모바일 디바이스에서 회계 분포(송장 코딩)를 보려고 합니까?</td>
<td>예</td>
</tr>
<tr class="odd">
<td>송장 라인에 대한 회계 분포(총 금액, 판매세, 요금 등)는 몇 개나 있습니까? 여기에도 80-20 규칙을 적용합니다.</td>
<td>총 금액: 2 판매세: 2 요금: 2</td>
</tr>
<tr class="even">
<td>송장의 송장 헤더에도 회계 분포가 있습니까? 그렇다면 이러한 회계 분포를 디바이스에서 사용할 수 있어야 합니까?</td>
<td>사용하지 않음</td>
</tr>
<tr class="odd">
<td>사용자가 디바이스에서 송장의 첨부 파일을 보기 원합니까?</td>
<td>예</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>다음 단계

시나리오 2의 요구 사항에 따라 시나리오 1을 다음과 같이 변경할 수 있습니다. 이 섹션을 사용하여 모바일 앱 환경을 개선할 수 있습니다.

1.  시나리오 2에서는 더 많은 송장 라인이 예상되기 때문에 디자인을 다음과 같이 변경하면 모바일 디바이스에서 사용자 환경을 최적화하는 데 도움이 됩니다.
    1.  세부 사항 페이지에서 송장 라인을 보는 대신(시나리오 1의 방식) 사용자는 별도의 모바일 페이지에서 라인을 보도록 선택할 수 있습니다.
    2.  이 시나리오에는 둘 이상의 송장 라인이 예상되기 때문에 **VendMobileInvoiceAllDistributionTree** 페이지를 사용하여 모바일 분포 페이지를 디자인하는 경우(시나리오 1의 방식) 사용자가 라인을 분포와 연관시키는 것이 혼란스러울 수 있습니다. 따라서 **VendMobileInvoiceLineDistributionTree** 페이지를 사용하여 분포 페이지를 디자인합니다.
    3.  이상적으로는 분포가 이 시나리오의 송장 라인 컨텍스트에서 표시되어야 합니다. 따라서 사용자가 분포 페이지를 보기 위해 한 라인으로 드릴할 수 있도록 해야 합니다. 페이지 링크 기능을 사용하여 시나리오 1의 헤더 및 세부 정보 페이지에 대해 수행한 것처럼 드릴스루를 설정합니다.

2.  시나리오 2의 분포에 둘 이상의 금액 유형(판매세, 요금 등)이 예상되므로 금액 유형에 관한 설명을 표시하는 것이 좋습니다. (시나리오 1에서는 이 정보를 생략했습니다.)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
