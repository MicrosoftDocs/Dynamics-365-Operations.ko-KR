---
title: Dynamics 365 Supply Chain Management 10.0.6의 새로운 기능 또는 변경된 기능(2019년 11월)
description: 이 토픽에서는 Dynamics 365 Supply Chain Management 10.0.6의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 87bcda25b89135e052a5a883b816ea0bb430479a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448153"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Dynamics 365 Supply Chain Management 10.0.6의 새로운 기능 또는 변경된 기능(2019년 11월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 10.0.6의 새로 추가되거나 변경된 기능에 관해 설명합니다. 이 버전의 빌드 번호는 10.0.234입니다. 일반 공급 날짜는 11월이지만 새 기능은 10월에 조기 릴리스될 수 있습니다. 버전 10.0.6에 대한 자세한 내용은 [추가 리소스](whats-new-scm-10-0-6.md#additional-resources)를 참조하세요.

## <a name="product-configuration-models-v2-data-entity"></a>제품 구성 모델 V2 데이터 엔터티

"제품 구성 모델" 데이터 엔터티에 대한 두 번째 버전이 출시되었습니다("제품 구성 모델 V2"라고 함). 기본 템플릿 "418-제품 구성 모델"도 가져오기/내보내기 프레임워크 템플릿에서 새로운 "제품 구성 모델 V2" 데이터 엔터티를 사용하도록 해야 합니다. 템플릿은 자동 업데이트되지 않으므로 기본값에서 템플릿을 수동으로 로드해야 합니다. V2 엔터티는 인라인이 아닌 첨부 파일에 하나의 행을 별도의 파일로 내보냄으로써 V1 엔터티의 크기 제한을 해결합니다. 
 
이 변경 사항을 적용하려면 어떻게 해야 합니까?
-    V1 엔티티가 더 이상 사용되지 않으므로 V1에서 V2로 마이그레이션을 시작해야 합니다. "418-제품 구성 모델" 템플릿을 사용하는 경우 "기본 템플릿 로드" 단추를 클릭하고 "418 – 제품 구성 모델" 템플릿을 다시 로드할 수 있습니다.
-    기존 시스템과의 호환성을 유지해야 하는 경우 통합을 새 템플릿으로 이동할 때까지 지금은 기존 템플릿 및 (사용되지 않는) V1 엔터티를 계속 사용할 수 있습니다. 

## <a name="feature-management-enhancements"></a>기능 관리 개선 사항
이제 기능 관리를 통해 기본적으로 모든 새 기능을 활성화하고, 기능을 활성화하려면 확인이 필요하며, 아직 활성화되지 않은 모든 기능을 활성화할 수 있습니다. 


## <a name="purchase-agreement-responsible-party"></a>구매 계약 담당자
이제 구매 계약 분류 양식과 그에 따른 구매 계약에서 1차 및 2차 책임 당사자를 정의할 수 있습니다.  이렇게 하면 계약을 감독하는 사용자에게 액세스할 수 있습니다.

## <a name="rfq-link-on-the-purchase-order-line"></a>구매 주문 라인의 RFQ 링크
구매 주문 라인에서 해당 RFQ 라인으로 다시 참조 링크를 추가하여 사용자가 견적 문서에 대한 지원 요청을 쉽게 제공받을 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

### <a name="bug-fixes"></a>버그 수정
10.0.6의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7)를 참조하세요.

### <a name="platform-update-30"></a>플랫폼 업데이트 30
Microsoft Dynamics 365 Supply Chain Management 10.0.6에는 플랫폼 업데이트 30이 포함됩니다. 플랫폼 업데이트 30에 대한 자세한 내용은 [플랫폼 업데이트 30의 새로운 기능 또는 변경된 사항](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md)을 참조하세요.

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: 2019 릴리스 웨이브 2 계획
비즈니스 앱 또는 플랫폼에서 예정된 기능과 최근에 출시된 기능이 궁금하신가요?

[Dynamics 365: 2019 릴리스 웨이브 2 계획](/dynamics365-release-plan/2019wave2/)을 확인하세요. 계획에 사용할 수 있는 단일 문서에 모든 세부 사항을 처음부터 끝까지, 위에서 아래로 캡처했습니다.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>제거 및 사용되지 않는 Supply Chain Management 기능

[Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목은 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

제품에서 기능이 제거되기 전에, 지원 중단 알림은 제거 12개월 전에 [Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목에 공지됩니다.

컴파일 시간에만 영향을 미치지만 샌드박스 및 프로덕션 환경과 바이너리 호환되는 호환성이 손상되는 변경의 경우 사용 중단 시간은 12개월 미만입니다. 일반적으로 컴파일러에 대해 수행해야 하는 기능 업데이트입니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]