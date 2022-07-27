---
title: 해시 번호로 인쇄된 고객 송장 보관
description: 이 토픽에서는 인쇄된 고객 송장을 해시 번호와 함께 저장하기 위해 보관을 활성화하는 방법에 대해 설명합니다.
author: ilkond
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 093b1b8c516c0c659e7970d17d3f84b2ed0ccf8f
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "8450988"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>해시 번호로 인쇄된 고객 송장 보관

[!include [banner](../includes/banner.md)]

일부 국가에서는 일부 문서의 출력물과 함께 계산된 해시 번호를 시스템에 저장해야 하는 법적 요구 사항이 있습니다. 해시 번호는 당국에 보고하거나 감사 중에 사용할 수 있습니다.

이 토픽에서는 인쇄된 고객 송장을 해시 번호와 함께 저장하기 위해 보관을 구성하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>전제 조건

- **기능 관리** 작업 영역에서 **해시 번호로 인쇄된 고객 송장 보관** 기능을 켭니다. 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.
- **인쇄 관리** 에서 필요한 문서의 인쇄 가능한 형식을 구성합니다.

이 기능은 다음 문서에 적용됩니다.

**수취 계정**
- 고객 송장
- 고객 크레딧 노트
- 무료 텍스트 송장
- 자유 텍스트 대변표

**프로젝트 관리 및 회계**
- 프로젝트 송장
- 프로젝트 크레딧 노트

## <a name="configure-customer-master-data"></a>고객 마스터 데이터 구성
고객 데이터를 구성하고 인쇄된 송장을 첨부 파일로 자동 저장하는 기능을 켜려면 다음 단계를 완료하십시오.

1. **수취 계정** > **모든 고객** 으로 이동합니다. 
2. 고객을 선택하고 **송장 및 전달** 빠른 탭의 **E-INVOCE** 섹션, **eInvoice 첨부** 필드에서 **예** 를 선택합니다.

## <a name="print-invoices"></a>인보이스 인쇄
이전 절차에서 구성한 고객에 대한 무료 텍스트, 고객 및 프로젝트 송장 또는 크레딧 노트를 전기하고 인쇄할 수 있습니다.

인쇄된 인보이스의 **첨부 파일** 페이지를 엽니다. **첨부 파일** 빠른 탭의 **추가 세부 사항** 필드 그룹, **문서 해시 번호** 필드에서 인쇄된 인보이스에 대해 계산된 저장된 해시 번호를 찾습니다.

![첨부 파일 해시 번호.](media/attach-hash-num.jpg)

