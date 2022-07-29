---
title: 재무 Report Designer의 보고서 정의
description: 이 문서에서는 보고서 정의에 대한 정보를 제공합니다.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fed19d541af1ef6a55f09127f08d73b1301eefb6369f6d76314463e18fb273c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460852"
---
# <a name="report-definitions-in-financial-report-designer"></a>재무 Report Designer의 보고서 정의

[!include [banner](../includes/banner.md)]

이 문서에서는 보고서 정의에 대한 정보를 제공합니다. 보고서 정의는 행 정의, 열 정의 및 선택적 보고 트리 정의를 사용하여 보고서를 작성하는 보고서 구성 요소(또는 빌딩 블록)입니다. 보고서 정의는 보고서를 사용자 지정하기 위한 옵션과 설정도 제공합니다. 

보고서 정의는 행 정의, 열 정의 및 선택적 보고 트리 정의를 사용하여 보고서를 작성하는 보고서 구성 요소(또는 빌딩 블록)입니다. 보고서 정의는 보고서를 사용자 지정하는 데 사용할 수 있는 옵션과 설정도 제공합니다. 행 정의와 열 정의를 정의한 후 보고서 정의에서 이들을 결합해야 합니다. 이 시점에서 상세 수준 및 보고 날짜와 같은 정의의 다른 측면도 정의합니다. 이후 보고서를 저장하고 생성할 수 있습니다. 재무 보고는 다음과 같은 세부 수준을 제공합니다.

- 재정적인
- 금융 및 계정
- 금융, 계정 및 거래

그러나 Microsoft Dynamics ERP 시스템에 데이터가 저장되는 방식에 따라 보고서에 트랜잭션 세부 정보가 표시되지 않을 수 있습니다.

## <a name="create-a-report-definition"></a>보고서 정의 만들기
1. Report Designer의 **파일** 메뉴에서 **새로 만들기** 를 클릭한 다음 **보고서 정의** 를 선택합니다.
2. **보고서**, **출력 및 배포**, **머리글 및 바닥글**, **설정** 탭에서 적절한 정보를 지정합니다.

## <a name="contents-of-a-report-definition"></a>보고서 정의의 내용
다음 표에서는 보고서 정의의 탭과 정보가 사용되는 방식에 대해 설명합니다.

<table>
<thead>
<tr>
<th>탭</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>보고서</td>
<td>보고서를 생성하거나, 보고서를 구성하거나, 기존 보고서를 수정합니다.</td>
</tr>
<tr>
<td>출력 및 배포</td>
<td>보고서의 출력 유형 및 대상을 변경합니다.</td>
</tr>
<tr>
<td>머리글 및 바닥글</td>
<td>보고서의 머리글과 바닥글을 정의하고 서식을 지정합니다. 예를 들어 머리글이나 바닥글에 텍스트나 이미지를 추가할 수 있습니다. 재무 보고는 이미지에 대해 .bmp, .jpg 및 .png 파일을 지원합니다. 상용구 코드를 추가하여 회사 이름, 보고서 이름 또는 페이지 번호와 같은 기타 정보를 삽입할 수도 있습니다.</td>
</tr>
<tr>
<td>설정</td>
<td>다음 설정과 같은 보고서 정의 설정을 지정합니다.
<ul>
<li>서식 및 반올림 금액</li>
<li>세부 보고서 형식 지정</li>
<li>보고 트리 형식 지정</li>
<li>예외 보고서 생성</li>
<li>통화 변환 지정</li>
<li>소계 및 필터 계정 세부 정보</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>추가 리소스

[재무보고](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]