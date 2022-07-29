---
title: 전자 보고(ER) 확장 형식 조회
description: 이번에는 필요한 형식이 전역 리포지토리에 저장된 경우 ER 형식 조회에서 ER 형식 참조를 설정하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2b69ba1b3b27f447b58cf98b1140a481b01b735a
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460947"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>사용자가 글로벌 리포지토리에서 형식을 조회하는 ER 형식 참조를 설정할 수 있습니다.

[!include [banner](../includes/banner.md)]

[전자 보고](general-electronic-reporting.md)(ER) 프레임워크를 사용하여 다양한 국가/지역의 법적 요구 사항에 따라 아웃바운드 문서의 형식을 구성할 수 있습니다. 또한 ER 프레임워크를 사용하여 인바운드 문서 구문 분석을 위한 형식을 구성하고 해당 문서의 정보를 사용하여 애플리케이션 데이터를 추가하거나 업데이트할 수 있습니다. 이러한 각 형식은 특정 비즈니스 프로세스의 일부로 인바운드 또는 아웃바운드 비즈니스 문서를 처리하기 위해 Dynamics 365 Finance 인스턴스에서 사용할 수 있습니다.

일반적으로 특정 비즈니스 프로세스에서 사용해야 하는 ER 형식을 지정해야 합니다. 그렇게 하려면 비즈니스 프로세스별 매개 변수의 일부로 구성된 조회 필드에서 단일 ER 형식을 선택하십시오. 이러한 조회 필드는 일반적으로 ER 프레임워크의 적절한 API를 사용하여 구현됩니다. 자세한 내용은 [ER 프레임워크 API - 형식 매핑 조회를 표시하는 코드](er-apis-app73.md#code-to-display-a-format-mapping-lookup)를 참조하십시오.

예를 들어, [대외 무역 매개 변수](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters)를 구성할 때 Intrastat 선언 및 Intrastat 선언 제어 보고서를 생성하는 데 사용할 개별 ER 형식에 대한 참조를 설정해야 합니다. 아래 스크린샷은 **해외 무역 매개 변수** 페이지에서 ER 형식 조회 필드가 어떻게 보이는지 보여줍니다.

현재 Finance 인스턴스에 Intrastat 비즈니스 프로세스 관련 ER 형식이 없는 경우 이 조회 필드는 비어 있습니다.

[![대외 무역 매개 변수 페이지, 보고서 형식 매핑 필드가 비어 있습니다.](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

현재 Finance 인스턴스에 Intrastat 비즈니스 프로세스 관련 ER 형식이 포함된 경우 이 조회 필드는 ER 형식을 제공합니다.

[![대외 무역 매개 변수 페이지, 옵션이 있는 보고서 형식 매핑 필드.](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

이 조회는 현재 Finance 인스턴스로 이미 가져온 ER 형식만 제공합니다. ER 솔루션을 현재 Finance 인스턴스로 [가져오려면](./tasks/er-import-configuration-lifecycle-services.md) ER 형식을 포함하는 ER 솔루션의 [수명 주기](general-electronic-reporting-manage-configuration-lifecycle.md)를 지원하는 ER 프레임워크의 적절한 함수를 실행할 수 있는 권한이 있어야 합니다.

Finance 버전 10.0.9(2020년 4월 릴리스)부터 ER 프레임워크 API를 사용하여 구현되는 ER 형식 조회의 사용자 인터페이스가 확장되었습니다. 형식 선택 구성 FastTab에서 **기존 ER 형식을 계속 선택** 할 수 있습니다. 또한 확장된 조회는 글로벌 리포지토리(GR)를 검색하여 특정 ER 형식을 찾는 새로운 옵션을 제공합니다. **GR의 모든 ER 형식은 글로벌 저장소** FastTab에서 가져오기에서 제공됩니다.

[![해외 무역 매개 변수 페이지, 글로벌 저장소 FastTab에서 가져오기.](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

**형식 선택 구성** FastTab과 유사하게 **글로벌 리포지토** 리 FastTab에서 가져오기는 이 조회 필드에서 ER 형식이 선택된 비즈니스 프로세스에 적용 가능한 ER 형식만 표시합니다. 이 예시에서 Intrastat 선언의 생성. ER 형식은 회사 국가 컨텍스트에 따라 사용자가 현재 로그인한 회사에 적용됩니다.

**글로벌 리포지토리에서 가져오기** FastTab에서 ER 형식을 선택하면 선택한 ER 형식 [구성](general-electronic-reporting.md#Configuration)을 GR에서 현재 Finance 인스턴스로 가져옵니다.

[![대외 무역 매개 변수 페이지, 처리 작업 참고.](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

이후 가져오기가 성공적으로 완료되면 가져온 ER 형식에 대한 참조가 이 조회 필드에 저장됩니다. GR에 처음 액세스하는 경우 제공된 링크를 따라 GR 저장소에 대한 액세스를 관리하는 데 사용되는 [RCS(Regulatory Configuration Service)](https://aka.ms/rcs)에 가입해야 합니다.

[![해외 무역 매개 변수 페이지, RCS 가입 링크.](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

기본적으로 **글로벌 리포지토리에서 가져오기** FastTab은 성능 향상을 위해 GR 콘텐츠를 기반으로 자동 생성되는 임시 저장소의 ER 형식 목록을 제공합니다. 이는 **글로벌 리포지토리에서 가져오기** FastTab을 처음 열 때 발생하며 몇 초가 걸릴 수 있습니다.

**글로벌 리포지토리에서 가져오기** FastTab에 필요한 ER 형식이 표시되지 않지만 이 ER 형식이 GR에 저장되어 있다고 확신하는 경우 **동기화** 옵션을 선택합니다. 이 옵션은 임시 저장소를 업데이트하고 GR의 현재 내용과 동기화합니다.

## <a name="feature-activation"></a>기능 활성화

이 함수의 가용성은 **함수 관리에서 전역 리포지토리를 조회** 할 수 있는 ER 형식 구성의 **확장 조회** 함수에 의해 제어됩니다. 이 기능은 기본적으로 활성화되어 있습니다.

[![기능 관리 페이지.](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>보안 고려 사항

**구성 리포지토리 유지 관리**(**ERMaintainSolutionRepositories**) 권한은 글로벌 리포지토리 FastTab에서 **가져오기가 활성화된 ER 형식** 조회를 여는 사용자의 GR 액세스를 제어합니다. 사용자가 ER 형식 조회에서 GR 콘텐츠에 액세스할 수 있도록 하려면 **ERMaintainSolutionRepositories** 권한을 사용자에게 직접 부여하거나 이미 할당된 역할 및 의무를 사용하여 보안 설정을 변경해야 합니다.

다음 스크린샷은 **회계사** 역할에 할당된 사용자에게 이 권한을 부여하는 방법을 보여줍니다. 이 역할을 통해 사용자는 **대외 무역 매개 변수** 를 구성하고 대외 무역 매개 변수 페이지의 **파일 형식 매핑** 및 **보고서 형식 매핑** 필드에서 ER 형식에 대한 참조를 설정할 수 있습니다.

[![보안 구성 페이지.](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>한계

ER 형식 조회에서 GR에 대한 액세스는 현재 아웃바운드 문서를 생성하는 데 사용되는 ER 형식 선택에 대해서만 지원됩니다.

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>ER 형식 조회에서 글로벌 리포지토리에 액세스할 수 없는 이유는 무엇입니까?

**기능 관리** 페이지에서 **글로벌 리포지토리 기능을 조회할 수 있도록 ER 형식 구성** 의 확장 조회를 활성화했지만 사용자가 **글로벌 리포지토리** FastTab에서 가져오기에서 ER 형식을 볼 수 없고 **동기화** 옵션이 표시되지만 비활성화되어 있는지 확인하십시오. **구성 리포지토리 유지 관리**(**ERMaintainSolutionRepositories**) 권한이 사용자에게 부여되었습니다. 이 권한을 받으려면 시스템 관리자에게 문의하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [전자 보고(ER) 프레임워크 API](er-apis-app73.md)
- [전자 보고(ER) 구성 수명 주기 관리](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
