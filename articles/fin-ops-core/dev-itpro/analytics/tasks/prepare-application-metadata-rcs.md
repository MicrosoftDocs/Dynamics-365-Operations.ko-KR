---
title: RCS에서 사용할 애플리케이션 메타데이터 준비
description: 이 항목에서는 애플리케이션 메타데이터가 포함된 새 보고 구성을 만드는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71a33a69796b31c456bfcc5abbb3b18bcb1064be65c1c58b36656a9cebfbf47d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460878"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a>RCS에서 사용할 애플리케이션 메타데이터 준비
[!include [banner](../../includes/banner.md)]

다음 단계는 시스템 관리자 또는 전자 보고 개발자 역할이 있는 사용자가 애플리케이션에 대한 메타데이터를 포함하며 Regulatory Configuration Service(RCS)에서 ER 모델 매핑 구성을 설계하는 데 사용되는 새로운 전자 보고(ER) 구성을 생성하는 방법을 보여줍니다. 이 구성은 대외 무역 거래에 액세스하기 위해 샘플 ER 모델 매핑 구성을 디자인하는 데 사용됩니다. 이 예에서는 샘플 회사인 Litware, Inc.에 대한 구성을 생성합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다. 이러한 단계를 완료하려면 RCS에서 [구성 공급자를 만들고 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md) 토픽의 절차를 완료해야 합니다.

## <a name="prerequisites"></a>전제 조건
1.    **조직 관리** > **작업 영역** > **전자 보고** 로 이동합니다. 
2.    샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 **활성** 으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 [구성 공급자 만들기](er-configuration-provider-mark-it-active-2016-11.md) 절차의 단계를 완료하고 활성으로 표시합니다. 
3.    **메타데이터 구성** 을 클릭합니다. 
4.    RCS를 사용하여 대외 무역 비즈니스 도메인의 정보가 포함된 전자 문서를 생성하는 데 사용할 금융 및 운영 응용 프로그램에 대한 ER 솔루션을 설계한다고 가정합니다. ER 데이터 모델과 필수 데이터 소스 간의 매핑을 지정하려면 RCS에서 금융 및 운영 애플리케이션의 메타데이터에 액세스할 수 있어야 합니다. 따라서 ER 솔루션 설계의 일부로 선택한 비즈니스 도메인에 대한 ER 보고서를 생성하는 데 현재 필요한 모든 메타데이터가 포함된 새 ER 메타데이터 구성을 구성해야 합니다. 

## <a name="add-metadata-configuration"></a>메타데이터 구성 추가 
1.    **구성 만들기** 를 클릭하여 드롭 대화 상자를 엽니다. 
2.    **이름** 필드에 '대외 무역 메타데이터'를 입력합니다. 
3.    **구성 만들기** 를 클릭합니다. 
4.    **디자이너** 를 클릭합니다. 
5.    **추가** 를 클릭합니다. 
  
> [!NOTE]
> 전체 애플리케이션이나 선택한 모델 또는 선택한 모듈에 대한 모든 메타데이터를 선택할 수 있습니다. 이 경우 레코드 테이블, 열거형 및 확장 데이터 유형과 같은 메타데이터가 자동으로 추가됩니다. 추가 유형의 메타데이터가 필요한 경우 수동으로 추가해야 합니다. 
 
메타데이터 항목을 수동으로 선택하여 해외 무역 거래와 관련된 메타데이터를 추가합니다. 
  
6.    **데이터 원본 추가** 를 클릭합니다. 
7.    **테이블 레코드** 를 클릭합니다. 
8.    빠른 필터를 사용하여 값이 'Intrastat'인 **이름** 필드를 필터링합니다. 
9.    **Intrastat** 테이블 레코드를 선택합니다. 
10.    **확인** 을 클릭합니다.
  
Intrastat 레코드 테이블에 대한 메타데이터 정보를 추가했습니다. 
  
11.    트리에서 **테이블 레코드 Intrastat**\>**관계** 를 확장합니다. 
12.    트리에서 **테이블 레코드 Intrastat**\>**관계\IntrastatCommodity(테이블 레코드 EcoResCategory)** 를 선택합니다.     
13.    **메타데이터 추가** 를 클릭합니다. 
  
> [!NOTE]
> 선택한 레코드 테이블에 필요한 관계에 대한 메타데이터는 수동으로 추가해야 합니다. 
  
16.    **데이터 원본 추가** 를 클릭합니다. 
17.    **열거** 를 클릭합니다. 
18.    빠른 필터를 사용하여 값이 'IntrastatDirection'인 **이름** 필드를 필터링합니다. 
19.    **IntrastatDirection 열거** 레코드를 선택합니다. 
20.    **확인** 을 클릭합니다. 
21.    **저장** 을 클릭합니다.  
22.    페이지를 닫습니다. 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a>메타데이터 구성의 초안 버전을 완료합니다
1.    **상태 변경** 을 클릭합니다. 
2.    **완료** 를 클릭합니다. 
3.    **확인** 을 클릭합니다. 
4.    완성된 버전 **1** 을 선택합니다. 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a>애플리케이션에서 완료된 메타데이터 구성 버전을 XML 파일로 내보냅니다
1.    **교환** 을 클릭합니다. 
2.    **XML 파일로 내보내기** 를 클릭합니다. 
3.    **확인** 을 클릭합니다. 
    
생성된 ER 메타데이터 구성은 XML 파일로 저장되어 RCS로 가져올 수 있으며 대외 무역 비즈니스 도메인에 대한 메타데이터에 대한 정보 소스로 사용할 수 있습니다. 이 정보를 기반으로 애플리케이션 메타데이터와 ER 데이터 모델 간의 매핑을 지정할 수 있습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]