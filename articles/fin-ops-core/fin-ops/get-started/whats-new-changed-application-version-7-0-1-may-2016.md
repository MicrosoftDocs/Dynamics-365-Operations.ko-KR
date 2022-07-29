---
title: Dynamics AX 애플리케이션 버전 7.0.1의 새로운 기능 또는 변경된 기능(2016년 5월)
description: 이 문서에서는 Microsoft Dynamics AX 애플리케이션 버전 7.0.1의 새로 추가되거나 변경된 기능에 관해 설명합니다. 이 버전은 2016년 5월에 릴리스되었으며 빌드 번호가 7.0.1265.23014입니다.
author: sericks007
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9a455ffbc4396ea4bf0e3df12e7acdcbfeaa5f5269dbe772848341ac0d22a5e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460813"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Dynamics AX 애플리케이션 버전 7.0.1의 새로운 기능 또는 변경된 기능(2016년 5월)

[!include [banner](../includes/banner.md)]

이 문서에서는 Microsoft Dynamics AX 애플리케이션 버전 7.0.1의 새로 추가되거나 변경된 기능에 관해 설명합니다. 이 버전은 2016년 5월에 릴리스되었으며 빌드 번호가 7.0.1265.23014입니다.

## <a name="electronic-reporting-er"></a>전자 보고(ER)

| 무엇을 할 수 있나요? | 중요한 이유? |
|------------------|------------------------|
| 사용자가 원하는 재무 차원을 선택할 수 있도록 전자 보고(ER) 보고서를 디자인하기 위한 런타임 대화 상자를 구성합니다. | 런타임에 ER 보고서를 실행하기 위한 대화 상자에서 사용자는 여러 재무 차원을 선택할 수 있습니다. 선택한 재무 차원의 세부 정보는 생성되는 전자 문서에 표시됩니다. |
| 원하는 데이터 소스에 대한 단일 매핑을 통해 ER 보고서를 설계하는 동안 여러 재무 차원에 대한 액세스를 구성합니다. | 동일한 ER 보고서 구성을 사용하여 사용자가 선택하거나 현재 법인 또는 인스턴스에 대해 구성된 재무 차원의 수에 관계없이 재무 차원의 세부 정보와 함께 거래 데이터를 표시하는 전자 문서를 생성할 수 있습니다. |
| OPENXML 워크시트 형식으로 생성된 전자 문서의 동적으로 생성된 열에 데이터를 입력하도록 ER 보고서를 구성합니다. | ER 보고서는 수평 복제 열을 통해 생성된 OPENXML 워크시트에 데이터를 입력할 수 있습니다. 따라서 동일한 ER 보고서 구성을 재사용하여 동적으로 생성된 열 수가 다른 전자 문서를 생성할 수 있습니다. |
| 형식의 출력 결과가 파일, 이메일 또는 아카이브(Microsoft SharePoint 폴더 또는 Microsoft Azure Storage)로 연결되도록 ER 대상을 구성합니다. | 이전에는 ER 구성을 실행할 때 파일을 저장하거나 열려면 사용자 작업이 필요하다는 메시지 상자가 나타났습니다. 이제 각 형식 구성 및 각 출력 구성 요소(폴더 또는 파일)에 대해 별도로 대상을 미리 구성할 수 있습니다. 적절한 액세스 권한이 있는 사용자는 런타임에 대상 설정을 수정할 수도 있습니다. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>POS – Microsoft Dynamics AX 소매

| 무엇을 할 수 있나요? | 중요한 이유? |
|------------------|------------------------|
| Google Chrome 브라우저를 사용하세요. | 이제 소매업체는 Chrome 브라우저에서 Cloud POS를 시작할 수 있으며 Microsoft Edge 및 Internet Explorer 버전의 클라우드 POS에서 사용 가능한 모든 기능을 경험할 수 있습니다. |

## <a name="financial-reporting"></a>재무 보고

| 무엇을 할 수 있나요? | 중요한 이유? |
|------------------|------------------------|
| 재무 보고 데이터 마트를 재구축합니다. | 환경 간에 Dynamics AX 데이터베이스를 변경하거나 환경에 다른 침입적인 변경을 수행하는 경우 재무 보고 데이터베이스를 다시 작성해야 할 수 있습니다. 이제 데이터베이스를 다시 빌드하기 위해 Windows PowerShell 스크립트가 제공됩니다. |
| 유효하지 않은 Report Designer 옵션은 더 이상 선택할 수 없습니다. | 시장 내 버전의 Management Reporter에서 사용된 여러 Report Designer 옵션은 이 버전의 Dynamics AX에 적용되지 않습니다. 이러한 옵션은 재무 보고서 디자인, 출력 및 연결과 관련되었습니다. 이러한 옵션은 사용자 오류를 방지하기 위해 재무 Report Designer에서 제거되었습니다. |

## <a name="financial-management"></a>재무 관리

| 무엇을 할 수 있나요? | 중요한 이유? |
|------------------|------------------------|
| 미지급금에 대한 긍정적인 지불 파일을 생성합니다. | 포지티브 페이 파일은 수표 사기를 예방하기 위해 생성될 수 있습니다. |

## <a name="warehouse-and-production"></a>창고 및 생산

<table>
<thead>
<tr>
<th>무엇을 할 수 있나요?</th>
<th>중요한 이유?</th>
</tr>
</thead>
<tbody>
<tr>
<td>특정 위치에서 제품 세트에 대한 작업 생성을 제어하는 창고 작업 정책을 정의합니다.</td>
<td>창고 프로세스에 작업이 항상 포함되는 것은 아닙니다. 새 창고 작업 정책을 정의하면 특정 위치에서 일련의 제품에 대한 원자재 피킹 및 완제품 보관을 위한 작업이 생성되는 것을 방지할 수 있습니다.</td>
</tr>
<tr>
<td>생산 출력 위치가 번호판 제어가 아님을 지정합니다.</td>
<td>제품 출력 위치가 번호판 제어가 아님을 지정할 수 있습니다. 예를 들어, 이 기능은 업스트림 생산 오더가 다운스트림 생산 오더의 생산 입력 위치 역할을 하는 위치에 직접 완료된 것으로 항목을 보고할 때 유용합니다.</td>
</tr>
<tr>
<td>동일한 항목의 제품 치수가 다른 항목을 포함하는 BOM을 지원합니다.</td>
<td>생산에서 하나 이상의 제품 치수를 사용할 때 동일한 품목의 다른 변형을 기반으로 품목을 생산하려는 상황이 있을 수 있습니다. 자세한 내용은 <a href="/archive/blogs/axmfg/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item">이 블로그</a>를 참조하세요.</td>
</tr>
<tr>
<td>BOM의 첫 번째 레벨에 원형 구조가 있는 생산 오더는 자재 자원 계획을 위한 BOM 레벨 계산에서 제외됩니다.</td>
<td>BOM 계층 구조에서 순환성을 유발하는 생산 주문의 경우 제품 변형에 올바른 BOM 수준을 할당할 수 없습니다.</td>
</tr>
<tr>
<td>자재 자원 계획 및 비용 계산을 위해 별도의 BOM 수준을 계산합니다.
<ul>
<li>자재 자원 계획의 경우 BOM 레벨은 새 <strong>요청 항목 수준</strong> 테이블에서 계산됩니다. 종료된 생산 오더는 계산에서 무시됩니다.</li>
<li>생산 비용 계산의 경우 BOM 수준은 <strong>InventTable</strong>에서 계산됩니다. 종료된 생산 오더는 계산에 포함됩니다.</li>
</ul>
</td>
<td>
<ul>
<li>예를 들어 마스터 계획 계획 스케줄링 및 전개와 같은 자재 자원 계획을 실행할 때 자재 자원 계획에 사용된 BOM 수준만 다시 계산하면 됩니다. 즉, 생산 원가 계산에 사용되는 BOM 수준을 계산할 필요가 없습니다.</li>
<li>예를 들어 재고 마감과 같은 원가 계산 작업을 실행할 때 생산 원가 계산에 사용된 BOM 수준만 다시 계산하면 됩니다.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>추가 리소스

[금융 및 운영 홈 페이지의 새로운 기능 또는 변경된 기능](whats-new-changed.md)

[신규 또는 업데이트된 작업 가이드(2016년 5월)](new-updated-task-guides-available-may-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]