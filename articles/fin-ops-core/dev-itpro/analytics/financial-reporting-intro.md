---
title: 재무 보고
description: 재무 보고를 통해 재무 및 비즈니스 전문가는 재무 제표를 작성, 유지 관리, 배포 및 볼 수 있습니다.
author: aprilolson
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.custom:
- "68813"
- intro-internal
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 20e2b4cb2b68500eeee06f1be5d95fc2cbab246f43b5e4a0e83eca7a8be53005
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460665"
---
# <a name="financial-reporting"></a>재무 보고

[!include [banner](../includes/banner.md)]

애플리케이션용 재무 보고를 통해 재무 및 비즈니스 전문가는 재무 제표를 작성, 유지 관리, 배포 및 볼 수 있습니다. 다양한 유형의 보고서를 효율적으로 디자인할 수 있도록 기존의 보고 제약 조건을 뛰어넘습니다.

재무 보고에는 차원 지원이 포함됩니다. 따라서 계정 세그먼트 또는 차원을 즉시 사용할 수 있습니다. 추가 도구나 구성 단계가 필요하지 않습니다.

## <a name="financial-reporting-setup"></a>재무 보고 설정
**재무 보고 설정** 페이지에는 시스템의 모든 재무 차원 목록이 있습니다. **총계정원장** \> **원장 설정** \> **재무 보고 설정**.

**재무 보고 설정** 페이지에는 재무 보고에서 보고하는 데이터를 결정하는 두 개의 섹션이 있습니다.

- **차원 탭** - 회사마다 차원과 계정 구조가 다르기 때문에 사용자가 보고서에서 모든 재무 차원을 보려는 순서를 결정할 방법이 없습니다. 이 페이지에서는 재무 보고에서 보고서를 작성하고 볼 때 재무 차원을 표시할 순서를 설정할 수 있습니다.
- **특성 탭** 에서는 필터링 및 보고서 디자인을 위한 속성으로 **공급업체** 및 **고객** 을 사용할지 여부를 선택할 수 있습니다. 공급업체 및 고객에 대한 보고는 거래를 게시할 때 단일 바우처에 여러 공급업체 또는 고객을 입력하지 않는 경우에만 가치가 있습니다. 공급업체 및/또는 고객을 선택하면 통합에 추가 시간이 추가됩니다.

## <a name="financial-reporting-components"></a>재무 보고 구성 요소
재무 보고의 다음 구성 요소를 사용하면 보고서를 쉽게 만들고, 보고, 예약할 수 있습니다.

| 구성 요소        | 함수 | 추가 정보 |
|------------------|-----------|------------------------|
| Report Designer  | 보고서를 정의하고 생성하기 위해 결합할 수 있는 보고서 구성 요소를 만듭니다. 보고서 마법사는 경험이 부족한 사용자에게 디자인 프로세스를 안내합니다. 고급 사용자는 새 보고서 구성 요소를 만들거나 요구 사항에 맞게 기존 구성 요소를 수정할 수 있습니다. | |
| 보고 일정 | 정기적으로 생성되도록 단일 보고서 또는 보고서 그룹을 예약합니다. | [재무 보고서 생성](generate-financial-report.md) |

## <a name="features"></a>기능
<table>
<thead>
<tr>
<th>기능</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>보고서 디자인 유연성</td>
<td>Report Designer는 보고서를 디자인할 때 다음과 같은 보고 옵션을 제공합니다.
<ul>
<li>차원 조합을 저장하고 여러 보고서에 차원을 재사용합니다.</li>
<li>차원 설명의 형식 지정 및 표시 방법을 제어합니다.</li>
<li>보고서 구성 요소에서 생략된 계정 또는 차원을 식별합니다.</li>
<li>롤링 예측을 위한 형식 헤더.</li>
</ul>
</td>
</tr>
<tr>
<td>재무 보고서 협업</td>
<td>다음 기능은 보고서 생성 및 배포를 관리하는 데 도움이 됩니다.
<ul>
<li>보고서가 매일, 매주, 매월 또는 매년 자동으로 생성되도록 일정을 잡습니다.</li>
<li>디지털 서명을 통해 더 나은 문서 보안을 제공하는 읽기 전용 XPS 형식으로 내보냅니다.</li>
<li>Microsoft Excel 워크시트로 내보내기.</li>
<li>보고서를 공유하기 위해 보고서에 대한 링크가 포함된 이메일 메시지를 만들 수 있습니다.</li>
</ul>
</td>
</tr>
<tr>
<td>대화형 보고서 보기</td>
<td>대화형 기능을 사용하면 다음 작업을 수행할 수 있습니다.
<ul>
<li>보고 있는 보고서의 보고서 날짜를 변경합니다.</li>
<li>보고 있는 보고서의 통화를 변경합니다.</li>
<li>요약 보기 또는 세부 보기에서 보고서를 봅니다.</li>
<li>보고서 콘텐츠를 특정 차원 또는 차원 조합으로 제한하려면 차원 필터를 추가합니다.</li>
<li>보고서 콘텐츠를 특정 특성 또는 특성 조합으로 제한하려면 특성 필터를 추가합니다.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>추가 리소스
[재무 보고서 생성](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]