---
title: TaxTrans의 잘못된 필드 값
description: 이 항목에서는 TaxTrans의 잘못된 필드 값 문제를 해결하기 위한 정보를 제공합니다.
author: EricWangChen
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 00424d98d5ff99123edf42ee19919d149e7a6abc
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "8450985"
---
# <a name="incorrect-field-value-in-taxtrans"></a>TaxTrans의 잘못된 필드 값

[!include [banner](../includes/banner.md)]

**TaxTrans** 의 필드 값이 잘못된 경우 이 항목의 정보를 사용하여 문제를 해결해 보세요.

## <a name="overview-of-values"></a>값 개요
다음 목록에서 **TaxTrans**, **TaxUncommitted**, **TmpTaxWorkTrans** 는 비슷한 데이터 세트지만 다른 방식으로 작동합니다.

  - **TaxTrans** 는 데이터베이스에 지속되는 최종 게시된 세금 거래 결과입니다.
  - **TaxUncommitted** 는 데이터베이스에 유지(해당되는 경우)되는 중간 계산된 세금 결과이며 나중에 게시할 때 사용됩니다.
  - **TmpTaxWorkTrans** 는 메모리 내 테이블(테이블 유형 = InMemory)에 있는 임시 계산된 세금 결과입니다.

잘못된 **TaxTrans** 열의 근본 원인을 찾았으면 잘못된 **TaxUncommitted** 또는 **TmpTaxWorkTrans** 열의 근본 원인도 찾은 것입니다. 이는 이러한 세 열이 서로 복사되기 때문입니다.

일반적으로 세금 계산 중에 **TmpTaxWorkTrans** 가 생성된 다음 해당하는 경우 **TaxUncommitted** 가 생성됩니다. **TaxTrans** 는 세금 게시 중 생성됩니다.


## <a name="add-breakpoints"></a>중단점 추가
중단점을 추가하려면 다음 단계를 완료합니다. 

1. 확장을 추가하고 아래와 같이 확장에 *insert()* 및 *update()* 에 중단점을 추가합니다.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. 또는 **TaxUncommitted** 가 포함되지 않은 경우 중단점을 직접 추가할 수 있습니다.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>재현 및 디버그

중단점을 설정한 후 디버깅하는 동안 모든 데이터 지속성 변경 사항을 볼 수 있습니다. **TaxTrans**, **TaxUncommitted** 또는 **TmpTaxWorkTrans** 열이 잘못된 근본 원인을 찾으려면 다음 항목을 검토하고 확인하세요.

- 열이 올바른 마지막 중단점.
- 열이 잘못된 첫 번째 중단점.
- 그 두 중단점 사이에서 일어나는 일.

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인
이전 섹션의 단계를 완료했지만 문제를 해결할 수 없는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정 항목이 없으면 Microsoft 지원에 문의하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

