---
title: 기준 계획 홈 페이지
description: 기준 계획을 통해 회사는 회사 목표를 달성하기 위한 원재료 및 용량에 대한 미래의 필요성을 결정하고 균형을 맞출 수 있습니다.
author: ChristianRytt
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7dd25fdd1549fb2fddff57dc2d9cf8762cfd6823
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2021
ms.locfileid: "8447370"
---
# <a name="master-planning-home-page"></a>기준 계획 홈 페이지

[!include [banner](../includes/banner.md)]

기본적으로 기준 계획을 통해 회사는 회사 목표를 달성하기 위한 원재료 및 용량에 대한 미래의 필요성을 결정하고 균형을 맞출 수 있습니다. 기준 계획은 다음을 평가합니다.

- 현재 사용 가능한 원자재와 용량은 무엇입니까?
- 생산을 완료하는 데 필요한 원자재와 용량은 무엇입니까? 예를 들어, 생산을 완료하기 전에 제조, 구매, 이전 또는 안전 재고로 확보해야 하는 항목입니다.

기준 계획에서는 이 정보를 사용하여 요구 사항을 계산하고 계획 주문을 생성합니다.

세 가지 주요 계획 프로세스는 다음과 같습니다.

- **기준 계획** - 기준 계획은 순 소요량을 계산합니다. 이는 실제 현재 주문을 기반으로 하며 회사가 단기적으로 매일 재고 보충을 제어할 수 있도록 합니다. 그것을 설명하는 또 다른 용어는 *순 요구 사항 계획* 입니다. 자세한 내용은 [기준 계획 개요](master-plans.md)를 참조하세요.

- **예측 계획** - 예측 일정은 총 소요량을 계산합니다. 이는 미래 예측(또는 예측)을 기반으로 하며 기업이 자재 및 용량에 대한 장기 계획을 수행할 수 있도록 합니다. 자세한 내용은 [수요 예측 개요](introduction-demand-forecasting.md)를 참조하세요.

- **기업간 기준 계획** - 본지사 기준 계획은 법인 전체의 순 소요량을 계산합니다. 기업 간의 수요와 공급을 단기적으로 확정된 수요와 공급뿐만 아니라 장기적으로 계획된(아직 확정되지 않은) 수요와 공급으로 연결합니다. 자세한 내용은 [기업간 계획](planning-optimization/Intercompany-planning.md)울 참조하세요.

회사는 계획의 결과를 변경할 수 있습니다. 재생, 순 변경 또는 둘 다를 실행할 수 있습니다. 재생 계획은 모든 요구 사항을 업데이트하지만 순 변경 계획은 마지막 일정 실행 이후에 들어온 새 요구 사항이 있는 항목에 대한 계획만 업데이트합니다.

기준 일정 계획에는 일반적으로 1주일에서 6개월까지의 단기가 포함됩니다. 기준 계획 모듈은 현재 수요(순 소요량)를 충족할 공급(자재) 및 용량(자원) 요구 사항을 결정합니다. 대부분의 회사에서 이것은 수령할 제품 중 가장 긴 누적 리드 타임을 포함하도록 확장됩니다.

## <a name="learning-map"></a>학습 맵

다음 학습 맵은 기준 계획 모듈의 프레임워크를 구성하는 주요 개념과 작업을 보여줍니다. [빠른 링크](#quick-links) 섹션에 있는 링크를 클릭하여 모듈을 사용하는 방법을 배우십시오.

[![기준 계획을 위한 학습 맵.](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>빠른 연결

- [기준 계획 개요](master-plans.md)  
- [제약 있는 계획 생성](./tasks/constrained-plan.md)
- [부산물에 대한 자재 계획 작성](./tasks/create-material-plan-co-products.md)
- [기준 계획 및 다중 사이트 기능 개요](master-plan-multisite-functionality.md)
- [회사 간 계획 생성](./tasks/create-intercompany-plan.md)
- [수요 예측 개요](introduction-demand-forecasting.md)
- [예측 감소 키](reduction-keys.md)

## <a name="additional-resources"></a>추가 리소스

### <a name="roadmaps"></a>로드맵

[Microsoft Dynamics 365 로드맵](https://roadmap.dynamics.com/)으로 이동하여 어떤 새로운 기능이 출시되었고 어떤 새로운 기능이 개발 중인지 확인하세요.

### <a name="blogs"></a>블로그

[Dynamics AX Manufacturing R&D Team 블로그](/archive/blogs/axmfg/) 및 [Dynamics AX R&D Team의 의 Supply Chain Management 블로그](https://blogs.msdn.microsoft.com/dynamicsaxscm)에서 기준 계획 및 기타 솔루션에 대한 의견, 뉴스 및 기타 정보를 찾을 수 있습니다.

### <a name="task-guides"></a>작업 가이드

추가 도움말은 작업 가이드로 사용할 수 있습니다. 작업 가이드에 액세스하려면 아무 페이지에서나 **도움말** 버튼을 클릭합니다.

### <a name="webinars"></a>웨비나

[수요 예측에 Azure 기계 학습 사용](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>기술 회의 녹음

- [수요 예측 기능 확장](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
- [기준 계획 - 성능 문제 해결을 위한 팁 및 요령](https://youtu.be/7v8BPmEs9Dg)
- [MRP 성능 조정](https://youtu.be/RLXybx20B5o)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]