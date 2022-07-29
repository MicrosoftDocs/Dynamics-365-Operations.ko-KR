---
title: 전자 보고(ER)의 회사 간 데이터 소스
description: 이번에는 전자 보고(ER)에서 회사 간 데이터 소스를 사용하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, ERFormatMappingLegalEntityFilterTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: cfa6e61879618aede466bde3eafe582be36301e8a1609511b7e3bc3fe65ccfce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460865"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>전자 보고(ER)의 회사 간 데이터 소스

[!include[banner](../includes/banner.md)]

전자 보고(ER) 형식을 설계하여 다양한 형식의 발신 문서를 생성할 수 있습니다. 문서가 생성되면 ER 형식은 해당 ER 모델 매핑에 구성된 데이터 소스를 호출합니다. 기록 검색을 위해 애플리케이션 테이블에 대한 액세스를 구성하려면 **테이블 기록** 유형의 ER 데이터 소스를 사용할 수 있습니다. 접근하는 테이블이 공유 테이블(즉, 회사 식별자 없이 데이터가 저장되는 테이블)인 경우 이 데이터 소스는 모든 기록을 반환합니다. 접근하는 테이블이 회사 종속 테이블(즉, 회사별로 데이터가 저장되는 테이블)인 경우 이 데이터 소스는 현재 회사에 대해 저장된 기록(즉, ER 형식이 지정된 회사 컨텍스트)만 반환합니다. 에서 실행 중입니다.

이제 모델 매핑에서 **테이블 기록** 유형의 모든 데이터 원본을 회사 간 데이터 원본으로 표시할 수 있습니다. 따라서 **테이블 기록** 유형의 데이터 소스를 사용하여 애플리케이션 테이블의 회사 간 데이터에 액세스할 수 있습니다.

데이터 소스를 회사 간으로 표시하면 다음 동작이 발생합니다.

- CompanyInfo를 제외한 모든 공유 테이블을 참조하는 데이터 소스의 경우 데이터 소스는 참조된 테이블에 있는 모든 기록을 반환합니다. 
- CompanyInfo 테이블을 참조하는 데이터 원본의 경우 CompanyInfo가 공유 테이블이더라도 데이터 원본은 정의된 범위에서 회사 식별자가 포함된 기록을 반환합니다.
- 모든 회사 종속 테이블의 경우 데이터 소스는 정의된 범위의 회사 식별자를 포함하는 참조된 테이블의 기록을 반환합니다.

시스템 쿼리 대화 상자에서 회사 간으로 표시된 데이터 원본에 대해 **쿼리 요청** 옵션이 켜져 있으면 **회사 범위** 탭에 포함할 하나 이상의 회사를 수동으로 선택할 수 있습니다.

> [!IMPORTANT]
> 다른 필터와 마찬가지로 회사 필터는 ER 형식을 실행할 때 쿼리에 대해 마지막으로 사용된 값으로 유지됩니다. 데이터 소스에 대한 회사 간 값을 변경하는 경우 필터가 자동으로 변경되지 않습니다. 다른 데이터 소스에 대해 다른 회사 간 값을 사용하려면 해당 사용자별 선택 항목을 삭제하십시오.

회사 간으로 표시된 모든 데이터 소스에 대해 ER 표현식에서 **FILTER** 및 **WHERE** 함수를 사용하여 원하는 기록을 선택할 수 있습니다. **dataAreaID** 필드는 회사 식별자로도 사용할 수 있습니다. 현재 **dataAreaID** 필드는 **FILTER** 함수를 사용할 때 다음 유형의 조건으로 제한됩니다.

- 단일 **dataAreaID** 필드 비교가 있는 조건만 지원됩니다.
- 기록 목록 항목에 의존하지 않는 표현식이 있는 비교만 허용됩니다.

따라서 다음 표현식이 유효합니다.

```ER Expression
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

기본적으로 범위에는 현재 애플리케이션의 모든 회사가 포함됩니다. 단, 제한될 수 있습니다. 단일 ER 형식에 대한 회사 간 데이터 액세스 범위를 제한하려면 형식에 특정 조직 계층을 할당합니다. ER 형식에 대해 계층이 정의되면 형식이 회사 간 데이터 소스를 호출하더라도 할당된 계층에 표시된 법인에 대한 기록만 반환됩니다. 더 이상 존재하지 않는 계층 구조에 대한 참조가 ER 형식에 대해 정의되면 기본 범위가 적용되고 형식은 회사 간 데이터 소스를 호출합니다. 이 경우 모든 애플리케이션 회사에 대한 기록이 반환됩니다.

단일 ER 형식 조직 계층에 할당된 **초안 사용** 옵션이 켜져 있으면 이 계층의 초안 버전에 있는 법인이 회사 간 데이터 소스의 범위를 식별하는 데 사용됩니다. 초안 버전이 존재하지 않는 경우 이 조직 계층의 마지막으로 게시된 버전의 법인이 이를 위해 사용됩니다.

단일 ER 형식 조직 계층에 할당된 **초안 사용** 옵션이 꺼져 있으면 이 조직 계층의 마지막으로 게시된 버전의 법인이 회사 간 데이터 소스의 범위를 식별하는 데 사용됩니다. 조직 계층의 날짜 효율성은 아직 ER 프레임워크에서 지원되지 않습니다.

계층 구조는 ER 작업 공간에서 액세스할 수 있는 특정 페이지의 형식에 할당하거나 **조직 관리 \> 전자 보고 \> 형식** 메뉴 항목에 대한 법인 필터를 사용하여 할당할 수 있습니다. 페이지에 액세스하려면 형식 권한을 위한 **법인 필터 유지** 관리(ERMaintainFormatMappingLegalEntityFilters)가 사용자에게 부여되어야 합니다. 사용자가 시스템 쿼리 대화 상자에서 수동으로 지정할 수 있는 제한 외에 형식에 대한 계층 기반 법인의 범위 제한이 적용됩니다. 이러한 제한의 교차는 형식이 실행될 때 사용됩니다.

이 기능에 대해 자세히 알아보려면 7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677) 비즈니스 프로세스의 일부인 **회사 간 모드에서 회사 종속 테이블의 ER 액세스 기록** 작업 가이드를 재생하십시오. [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=874684)에서 다운로드합니다. 이 작업 가이드는 회사 간 모드에서 애플리케이션 테이블에 액세스하기 위해 ER 모델 매핑 및 ER 형식을 구성하는 프로세스를 안내합니다.

작업 가이드를 완료하려면 다음 파일을 다운로드하십시오.

- [ER 모델 구성 - CrossCompanyDataAccessModel.xml](https://download.microsoft.com/download/4/2/5/4258f891-7054-4821-aedd-3721ba25fdd5/CrossCompanyDataAccessModel.xml)
- [ER 형식 구성 - CrossCompanyDataAccessFormat.xml](https://download.microsoft.com/download/3/2/1/321deb75-3ba9-4323-99bf-207a52c60b5c/CrossCompanyDataAccessFormat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
