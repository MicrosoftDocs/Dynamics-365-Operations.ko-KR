---
title: Excel에서 분개장 라인 및 문서 게시
description: 이 항목은 Microsoft Excel에서 일반 분개장의 라인을 입력하고 게시하는 방법을 설명합니다. 여기에는 입력하는 거래 유형에 따라 사용할 수 있는 다양한 템플릿에 관한 정보가 포함됩니다.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ad4d44030e49b9c07c0827e916d9b4f31fb54fce8b1121e9f69ea754e099591
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450256"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a>Excel에서 분개장 라인 및 문서 게시

[!include [banner](../includes/banner.md)]

이 항목은 Microsoft Excel에서 일반 분개장의 라인을 입력하고 게시하는 방법을 설명합니다. 여기에는 입력하는 거래 유형에 따라 사용할 수 있는 다양한 템플릿에 관한 정보가 포함됩니다.

사용자는 Microsoft Excel에서 재무 분개장 라인을 입력하고 게시할 수 있습니다. 사용자가 분개장을 만든 후 **Excel에서 라인 열기** 버튼은 사용 가능한 템플릿을 표시합니다. 템플릿은 특정 시나리오를 지원하도록 설계되었지만 분개장에서 모든 계정 유형 조합이 지원되는 것은 아닙니다. 다음 표에는 사용 가능한 템플릿과 지원되는 계정 유형이 나옵니다.

| 템플릿             | 지원되는 계정 유형 | 템플릿에 액세스하는 방법                                                          |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| 원장 분개장 라인     | 계정: 원장, 고객, 공급업체, 은행 상쇄 계정: 원장, 고객, 공급업체, 은행 회사 간이 지원됩니다.       | 일반 분개장                                                                         |
| 송장 등록         | 계정: 공급업체 상쇄 계정: 원장 회사 간은 지원되지 않습니다.                                                    | AP 송장 등록                                                                     |
| 송장 분개장          | 계정: 공급업체 상쇄 계정: 원장 회사 간이 지원됩니다.                                                      | AP 송장 분개장                                                                      |
| 공급업체 송장           |                                                                                                                         | 공급업체 송장                                                                          |
| 고객 송장 분개장 | 계정: 고객 상쇄 계정: 원장 회사 간이 지원됩니다.                                                     | 일반 분개장                                                                         |
| 자유 텍스트 송장        |                                                                                                                         | **자유 텍스트 송장** 페이지에서 **Excel에서 열기**(Microsoft Office 아이콘)를 클릭합니다. |
| 고정 자산 분개장     | 원장, 은행, 고객 또는 공급업체에 대한 자산 회사 간은 지원되지 않습니다.                                               | 고정 자산 분개장                                                                     |
| 공급업체 지불 분개장   | 계정: 공급업체 상쇄 계정: 원장, 은행 회사 간이 지원됩니다.                                                 | 공급업체 지불 분개장                                                                  |
| 고객 지불 분개장 | 계정: 고객 상쇄 계정: 원장, 은행 회사 간이 지원됩니다.                                               | 고객 지불 분개장                                                                |
| 프로젝트 경비 분개장  | 계정: 프로젝트, 원장, 고객, 공급업체, 은행 상쇄 계정: 프로젝트, 원장, 고객, 공급업체, 은행 회사 간이 지원됩니다. | 일반 분개장 경비(프로젝트 관리 및 회계 아래)                       |

라인이 게시되면 재무 분개장에 설정된 규칙을 준수하는지 확인하기 위해 유효성이 검사됩니다. 라인이 게시된 후 사용자는 Dynamics 365 Finance에서 전표를 편집하거나 게시할 수 있습니다. 

템플릿에 재무 차원을 추가하려면 추가 변경이 필요합니다. 추가 정보는 [Microsoft Excel 템플릿에 차원 추가](../../fin-ops-core/dev-itpro/financial/add-dimensions-excel-templates.md)를 참조하세요. 차원이 엔터티에 추가되면 Excel 디자이너에서 사용할 수 있으며 템플릿에 추가할 수 있습니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]