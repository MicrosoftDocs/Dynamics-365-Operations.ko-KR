---
title: 비즈니스 문서 관리 개요
description: 이번에는 ER 프레임워크의 비즈니스 문서 관리 기능을 사용하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: faea9d4d9b3fc8f3f1474b6bb2a8dc31cdc22511
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460699"
---
# <a name="business-document-management-overview"></a>비즈니스 문서 관리 개요

[!include [banner](../includes/banner.md)]

비즈니스 사용자는 [전자 보고(ER)](general-electronic-reporting.md) 프레임워크를 사용하여 다양한 국가/지역의 법적 요구 사항에 따라 아웃바운드 문서 형식을 구성합니다. 사용자는 생성된 문서에 배치할 애플리케이션 데이터를 지정하기 위해 데이터 흐름을 정의할 수도 있습니다. ER 프레임워크는 미리 정의된 템플릿을 사용하여 Microsoft Office 형식(Excel 통합 문서 또는 Word 문서)으로 아웃바운드 문서를 생성합니다. 템플릿은 필수 문서가 생성되는 동안 구성된 데이터 흐름에 따라 필수 데이터로 채워집니다. 구성된 각 형식을 ER 솔루션의 일부로 게시하여 특정 아웃바운드 문서를 생성할 수 있습니다. 이는 다른 아웃바운드 문서를 생성하는 데 사용할 수 있는 템플릿을 포함할 수 있는 ER 형식 구성으로 표시됩니다. 비즈니스 사용자는 이 프레임워크를 사용하여 필요한 비즈니스 문서를 관리할 수 있습니다.

**비즈니스 문서 관리** 는 ER 프레임워크 위에 구축되며 비즈니스 사용자가 Microsoft 365 서비스 또는 적절한 Microsoft Office 데스크탑 애플리케이션을 사용하여 비즈니스 문서 템플릿을 편집할 수 있도록 합니다. 문서 편집에는 비즈니스 문서 디자인 변경 및 소스 코드 변경 및 새로운 배포 없이 추가 데이터에 대한 자리 표시자 추가가 포함될 수 있습니다. 비즈니스 문서 템플릿을 업데이트하는 데 ER 프레임워크에 대한 지식이 필요하지 않습니다.

> [!NOTE]
> 비즈니스 문서 관리를 사용하면 주문, 송장 등과 같은 비즈니스 문서를 생성하는 데 사용되는 템플릿을 수정할 수 있습니다. 템플릿이 수정되고 새 버전이 게시되었지만 이 버전은 필요한 비즈니스를 생성하는 데 사용됩니다. 서류. 비즈니스 문서 관리는 이미 생성된 비즈니스 문서를 수정하는 데 사용할 수 없습니다.

## <a name="supported-deployments"></a>지원되는 배포

현재 비즈니스 문서 관리 기능은 클라우드 배포용으로만 구현되어 있습니다. 이 기능이 온 프레미스 배포에 중요한 경우 [Ideas](https://experience.dynamics.com/ideas/) 사이트에서 피드백을 제공하여 알려주십시오.

## <a name="supported-microsoft-office-applications"></a>지원되는 Microsoft Office 애플리케이션

Microsoft Office 데스크톱 애플리케이션을 사용하여 Excel 또는 Word 형식의 템플릿 편집에 비즈니스 문서 관리를 사용하려면 Microsoft Office 2010 이상이 설치되어 있어야 합니다. 이는 클라우드 및 온프레미스 배포에서 지원됩니다.

Microsoft 365 애플리케이션을 사용하여 Excel 또는 Word 형식의 템플릿 편집에 비즈니스 문서 관리를 사용하려면 웹용 Microsoft 365 Office 구독이 있어야 합니다. 이는 클라우드 배포에서 지원됩니다.

## <a name="business-document-availability"></a>비즈니스 문서 가용성

2019년 10월 릴리스에 대해 계획된 모든 보고서의 전체 목록은 [Word 및 Excel에서 보고하는 구성 가능한 비즈니스 문서](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details)를 참조하십시오.

2020년 10월 릴리스에 대해 계획된 모든 보고서의 전체 목록은 [구성 가능한 비즈니스 문서 – Word 템플릿](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates)을 참조하십시오.

향후 릴리스에서 더 많은 보고서를 사용할 수 있습니다. 추가 보고서에 대한 특별 알림은 별도로 발송됩니다. 현재 사용 가능한 보고서 목록을 검토하는 방법을 알아보려면 아래의 [구성 가능한 비즈니스 문서를 지원하기 위해 재무에서 릴리스된 ER 구성 목록](#list-of-configurations-cbd) 섹션을 참조하십시오.

이 기능에 대해 자세히 알아보려면 이 항목의 예시를 완료하십시오.

## <a name="configure-er-parameters"></a>ER 매개 변수 구성

비즈니스 문서 관리는 ER 프레임워크 위에 구축되므로 비즈니스 문서 관리 작업을 시작하려면 ER 매개 변수를 구성해야 합니다. 이렇게 하려면 [전자 보고(ER) 프레임워크 구성](electronic-reporting-er-configure-parameters.md)에 설명된 대로 ER 매개 변수를 설정해야 합니다. 또한 구성 제공자 생성에 설명된 대로 [새 구성 제공자를 추가하고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)해야 합니다.

![응급실 작업실.](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>응급실 솔루션 가져오기

이 절차의 예시에서는 샘플 ER 구성이 사용됩니다. Dynamics 365 Finance 비즈니스 문서 관리를 사용하여 편집할 수 있는 비즈니스 문서 템플릿이 포함된 ER 구성을 의 현재 인스턴스로 가져와야 합니다. 이 절차를 완료하려면 다음 파일을 다운로드한 후 로컬에 저장합니다.

**샘플 ER 고객 송장 솔루션**

| 파일                                      | 콘텐츠 |
|-------------------------------------------|---------|
| 고객 송장 model.version.2.xml    | [ER 데이터 모델 구성](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| 고객 FTI 보고서(GER).version.2.3.xml | [무료 텍스트 송장 ER 형식 구성](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**샘플 ER 지급 수표 솔루션**

| 파일                                     | 콘텐츠 |
|------------------------------------------|---------|
| cheques.version.10.xml용 모델         | [ER 데이터 모델 구성](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| format.version.10.9.xml 인쇄 확인 | [결제 확인 ER 형식 구성](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**샘플 ER 대외 무역 솔루션**

| 파일                             | 콘텐츠 |
|----------------------------------|---------|
| Intrastat model.version.1.xml    | [ER 데이터 모델 구성](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| 통계 내 보고서.version.1.9.xml | [Intrastat 제어 보고서 ER 형식 구성](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

다음 절차에 따라 각 파일을 가져옵니다. 해당 ER *형식* 구성을 가져오기 전에 위의 표에 있는 각 ER 솔루션의 ER *데이터 모델* 구성을 가져옵니다.

1. **조직 관리** \> **전자 보고** \> **구성** 페이지를 엽니다.
2. 페이지 상단에서 **Exchange** 를 선택합니다.
3. **XML 파일에서 로드** 를 선택합니다.
4. **찾아보기** 를 선택하여 필요한 XML 파일을 로드합니다.
5. **확인** 을 선택하여 구성 가져오기를 확인합니다.

![구성 가져오기를 확인하는 ER 구성 페이지.](./media/BDM-Overview-ERSolutions.png)

또는 Microsoft Dynamics LCS(Lifecycle Service)에서 공식적으로 게시된 ER 형식 구성을 가져올 수 있습니다. 예를 들어, 이 절차를 완료하기 위해 최신 버전의 **자유 텍스트 송장(Excel)** ER 형식 구성을 가져올 수 있습니다. 해당 ER 데이터 모델 및 ER 모델 매핑 구성을 자동으로 가져옵니다.

![LCS 공유 자산 라이브러리 콘텐츠 페이지.](./media/BDM-Overview-SharedAssetLibrary.png)

ER 구성 가져오기에 대한 자세한 내용은 [ER 구성 수명 주기 관리](general-electronic-reporting-manage-configuration-lifecycle.md)를 참조하십시오.

## <a name="enable-business-document-management"></a>비즈니스 문서 관리 활성화

비즈니스 문서 관리를 시작하려면 **기능 관리** 작업 영역을 열고 **비즈니스 문서 관리** 기능을 활성화해야 합니다.

모든 법인에 대해 비즈니스 문서 관리 함수를 활성화하려면 다음 절차를 따르십시오.

1. **기능 관리** 작업 영역을 엽니다.
2. **새로 만들기** 탭의 목록에서 **비즈니스 문서 관리** 기능을 선택합니다.
3. **지금 활성화** 를 선택하여 선택한 기능을 켭니다.
4. 새 기능에 액세스하려면 페이지를 새로고침하십시오.

> [!NOTE]
> 비즈니스 문서 관리에서 새 문서 사용자 인터페이스를 사용하는 방법에 대한 자세한 내용은 [비즈니스 문서 관리에서 새 문서 사용자 인터페이스](er-business-document-management-new-template-ui.md)를 참조하십시오.

![기능 관리 작업 공간.](./media/BDM-Overview-FMEnabling.png)

새 기능 활성화에 대한 자세한 내용은 [기능 관리 개요](../../fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하십시오.

## <a name="configure-parameters"></a>매개 변수 구성

다음 섹션의 정보를 사용하여 비즈니스 문서 관리를 위한 기본 매개 변수를 설정하십시오.

### <a name="prerequisites-for-parameter-setup"></a>매개 변수 설정을 위한 전제 조건

비즈니스 문서 관리를 설정하기 전에 문서 관리 프레임워크에서 필요한 문서 유형을 설정해야 합니다. 이 문서 유형은 ER 보고서의 템플릿으로 사용되는 Office 형식(Excel 및 Word)의 문서를 임시로 저장하는 데 사용됩니다. 임시 저장소 템플릿은 Office 데스크톱 애플리케이션을 사용하여 편집할 수 있습니다.

이 문서 유형의 경우 다음 속성 값을 선택해야 합니다.

| 속성 이름 | 속성 값 |
|----------------|-----------------|
| 클래스          | 파일 첨부     |
| 그룹          | 파일            |
| 위치       | SharePoint      |

필수 문서 관리 매개 변수 및 문서 유형을 설정하는 방법에 대한 정보는 [문서 관리 구성](../../fin-ops/organization-administration/configure-document-management.md)을 참조하십시오.

![문서 관리 문서 유형을 설정합니다.](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>매개 변수 설정

기본 **비즈니스 문서 관리** 매개 변수는 비즈니스 문서 매개 변수 페이지에서 설정할 수 있습니다. 특정 사용자만 페이지에 액세스할 수 있습니다. 여기에는 다음이 포함됩니다.

- **시스템 관리자** 역할에 할당된 사용자입니다.
- 업무를 수행하도록 구성된 역할에 할당된 사용자, **비즈니스 문서 관리 매개 변수 유지 관리**(AOT 이름 **ERBDMaintainParameters**).

다음 절차를 사용하여 모든 법인에 대한 기본 매개 변수를 설정합니다.

1. **비즈니스 문서 매개 변수** 페이지에 대한 액세스 권한이 있는 사용자로 로그인합니다.
2. **조직 관리** \> **전자 보고** \> **비즈니스 문서 관리** \> **비즈니스 문서 매개 변수** 로 이동합니다.
3. **비즈니스 문서 매개 변수** 페이지의 **첨부** 탭에 있는 **SharePoint 문서 유형** 필드에서 Office 데스크톱 애플리케이션을 사용하여 템플릿을 편집하는 동안 Office 형식으로 템플릿을 임시로 저장하는 데 사용해야 하는 문서 유형을 정의합니다. 

> [!NOTE]
> SharePoint 위치를 사용하여 구성된 문서 유형만 이 매개 변수에 사용할 수 있습니다.

![비즈니스 문서 관리 매개 변수 설정.](./media/BDM-Overview-BDMSetting.png)

선택한 문서 유형은 회사별로 다르며 사용자가 선택한 문서 유형이 구성된 회사에서 비즈니스 문서 관리 작업을 할 때 사용됩니다. 사용자가 다른 회사에서 비즈니스 문서 관리로 작업할 때 이 회사에 대해 구성되지 않은 경우 선택한 동일한 문서 유형이 사용됩니다. 문서 유형이 구성되면 **SharePoint 문서 유형** 필드에서 선택한 유형 대신 사용됩니다.

> [!NOTE]
> **SharePoint 문서 유형** 매개 변수는Microsoft Excel  는 Word를 사용하여 편집할 수 있는 템플릿의 임시 저장소로 SharePoint 폴더를 정의합니다. 템플릿 편집에 이러한 Office 데스크톱 애플리케이션을 사용하려는 경우 이 매개 변수를 설정해야 합니다. 자세한 내용은 [Office 데스크톱 애플리케이션에서 템플릿 편집](#EditInOfficeDesktopApp)을 참조하십시오. Microsoft 365의 함수만 사용하여 템플릿을 수정하려는 경우 이 매개 변수를 비워 둘 수 있습니다. 자세한 내용은 [Microsoft 365에서 템플릿 편집](#EditInOffice365)을 참조하십시오.

## <a name="configure-access-permissions"></a>액세스 권한 구성

기본적으로 비즈니스 문서 관리 권한에 대한 액세스가 활성화되지 않은 경우 비즈니스 문서 관리 작업 영역에 대한 액세스 권한이 있는 모든 사용자는 사용 가능한 모든 ER 솔루션 템플릿을 볼 수 있습니다. 비즈니스 문서 관리 작업 공간은 ER 형식 구성에 있고 **비즈니스 문서 유형** 태그로 표시된 템플릿만 표시합니다.

![비즈니스 문서 유형 태그가 있는 ER 구성 페이지.](./media/BDM-Overview-ERFormatTags.png)

비즈니스 문서 관리 작업 영역에서 사용할 수 있는 템플릿 목록은 액세스 권한을 구성하여 제한할 수 있습니다. 이는 다양한 템플릿을 사용하여 다양한 비즈니스 도메인(함수 영역)에 대한 비즈니스 문서를 생성하고 특정 사용자가 비즈니스 문서 관리 작업 공간에서 편집하기 위해 다른 템플릿에 액세스하도록 허용하려는 경우 중요할 수 있습니다.

업무 문서 관리 접근 권한은 **접근 권한의 Configurator** 에서 설정할 수 있습니다. 다음 사용자만 페이지에 액세스할 수 있습니다.

- **시스템 관리자** 역할에 할당된 사용자입니다.
- 의무를 수행하도록 구성된 다른 역할에 할당된 사용자는 **편집을 위해 비즈니스 문서 템플릿에 액세스할 수 있는 권한** 을 구성합니다(AOT 이름 **ERBDTemplatesSecurity**).

다음 절차를 사용하여 모든 법인에 대한 액세스 비즈니스 문서 관리 권한을 설정하십시오.

1. **액세스 권한 페이지의 구성자** 에 대한 액세스 권한이 있는 사용자로 로그인합니다.
2. **조직관리** 로 이동 \> **전자보고** \> **업무문서 관리** \> **접근권한을 관리** 합니다.

    비즈니스 문서 관리에 대한 액세스 권한 사용이 현재 활성화되어 있지 않음을 알리는 알림에 주의하십시오.

    ![비즈니스 문서 관리 액세스 권한 페이지의 구성자.](./media/BDM-Overview-TemplatesAccess1.png)

    이 설정을 사용하면 **비즈니스 문서 템플릿 관리**(AOT 이름 **ERBDManageTemplates**) 임무를 수행하도록 구성된 보안 역할에 할당된 모든 사용자가 비즈니스 문서 관리 작업 공간을 열고 사용 가능한 템플릿을 편집할 수 있습니다.

    다음 그래픽은 AR 사무원 역할에 할당된 사용자를 위해 **비즈니스 문서 관리** 작업 공간에서 사용할 수 있는 것을 보여줍니다. 현재 액세스 권한 설정을 통해 사용자는 송장 발행, 규제 보고 및 지급을 포함한 다양한 함수 영역에서 비즈니스 문서 템플릿을 편집할 수 있습니다.

    ![미수금 사무원을 위한 비즈니스 문서 관리 작업 공간 페이지입니다.](./media/BDM-Overview-TemplatesForAlice1.png)

3. **액세스 권한 구성자** 페이지에서 **액세스 권한 설정** 을 선택합니다.
4. **템플릿 편집을 위한 액세스 권한 설정** 대화 상자에서 **구성된 액세스 권한 적용 옵션** 을 활성화합니다.
5. **확인** 을 선택하여 비즈니스 문서 관리 액세스 권한이 활성화되었는지 확인합니다.

    ![비즈니스 문서 관리 액세스 권한을 확인합니다.](./media/BDM-Overview-TemplatesAccess2.png)

6. **추가** 를 선택하여 비즈니스 문서 관리 템플릿에 액세스할 수 있는 권한을 구성해야 하는 새 비즈니스 역할을 입력합니다.
7. **보안 역할** 대화 상자에서 **미수금 담당자** 역할을 선택한 다음 **확인** 을 선택하여 역할 선택을 확인합니다.
8. **구성의 태그당 액세스 권한** 탭에서 **새로 만들기** 를 선택합니다.
9. **태그 유형** 필드에서 **함수 영역** 을 선택하고 **ID** 필드에서 **송장 발행** 을 선택하십시오.
10. 선택한 역할에 대해 구성된 액세스 권한을 저장하려면 **저장** 을 선택합니다.

    현재 설정은 **미수금 사무원** 역할에 할당되고 업무를 수행하는 모든 사용자에 대해 **비즈니스 문서 템플릿 관리**(AOT 이름 **ERBDManageTemplates**), 함수 영역 태그에 대한 **송장 발행** 값이 있는 ER 형식 구성 템플릿을 사용할 수 있음을 의미합니다. **비즈니스 문서 관리** 작업 공간에서 편집하십시오.

11. 현재 페이지의 오른쪽에서 **관련 정보** 창을 전환합니다. **관련 정보** 창은 **미수금 사무원** 역할에 할당된 사용자가 사용할 수 있는 ER 구성 템플릿을 포함하여 구성된 액세스 권한이 적용되는 방법을 보여줍니다.

    ![액세스 권한 페이지의 구성자에 있는 관련 정보 창입니다.](./media/BDM-Overview-TemplatesAccess3.png)

12. **구성별 액세스 권한** 탭에서 **추가** 옵션을 선택합니다.
13. **구성 선택** 대화 상자에서 **Intrastat 보고서** ER 형식 구성을 표시합니다.
14. **확인** 을 선택하여 선택한 구성의 항목을 확인한 다음 **저장** 을 선택하여 선택한 역할에 대해 구성된 액세스 권한을 저장합니다.

현재 설정은 **미수금 사무원** 역할에 할당되고 의무를 수행하는 모든 사용자가 **비즈니스 문서 템플릿 관리**(AOT 이름 **ERBDManageTemplates**)를 수행하는 경우 비즈니스 문서 관리 작업 공간에서 다음 템플릿을 편집할 수 있음을 의미합니다.

- **함수 영역** 태그에 대한 **송장 발행** 값이 있는 템플릿.
- **구성별 액세스 권한** 탭에 나열된 **ER 형식 구성의 템플릿**(이 예시에서 법정 보고 도메인의 **Intrastat 보고서** 형식 구성의 템플릿).

![액세스 권한 페이지의 구성자에서 액세스 권한 FastTabs.](./media/BDM-Overview-TemplatesAccess4.png)

다음 그래픽은 **미수금 사무원** 역할에 할당된 사용자에게 비즈니스 문서 관리 작업 공간이 제공하는 것을 보여줍니다. 현재 비즈니스 문서 관리 액세스 권한 설정을 사용하여 사용자는 **송장 발행** 도메인 및 **Intrastat 보고서** ER 형식 구성에서 비즈니스 문서 템플릿을 편집할 수 있습니다. **미수금 사무원** 역할은 **결제** 도메인의 템플릿에 액세스할 수 없습니다.

![비즈니스 문서 관리 작업 영역 페이지에서 비즈니스 문서 템플릿을 편집합니다.](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> **구성 규칙별 액세스 권한** 은 ER 형식 구성의 고유 식별 ID를 사용하여 저장됩니다. 이는 규칙을 참조하는 ER 구성이 삭제될 때 이러한 규칙이 삭제되지 않음을 의미합니다. 삭제된 구성을 이 인스턴스로 다시 가져오면 이러한 규칙이 해당 구성을 다시 참조합니다. 삭제된 구성을 다시 가져온 후 규칙을 다시 설정할 필요가 없습니다.

## <a name="use-business-document-management-to-edit-templates"></a>비즈니스 문서 관리를 사용하여 템플릿 편집

비즈니스 사용자는 비즈니스 문서 관리 작업 영역에서 편집하기 위해 비즈니스 문서 템플릿에 액세스할 수 있습니다. 다음 사용자만 비즈니스 문서 관리 작업 영역에 액세스할 수 있습니다.

- 역할에 할당된 사용자, **시스템 관리자**.
- 업무를 수행하도록 구성된 역할에 할당된 사용자, **비즈니스 문서 템플릿 관리**(AOT 이름 **ERBDManageTemplates**).

다음 절차를 사용하여 비즈니스 문서 관리 작업 영역에서 자유 텍스트 송장 템플릿을 편집합니다. 이 절차를 완료하기 전에 이 항목의 이전 절차를 모두 완료해야 합니다.

1. 비즈니스 문서 관리 작업 영역에 대한 액세스 권한이 있는 사용자로 로그인합니다.
2. 비즈니스 문서 관리 작업 영역을 엽니다.

**기능 관리** 작업 영역에서 **비즈니스 문서 관리에 대한 Office와 같은 UI 환경** 이 꺼져 있으면 **비즈니스 문서 관리** 작업 영역의 기본 그리드에 다음 템플릿이 표시됩니다.

- ER 구성 제공자가 소유한 템플릿(즉, 현재 **전자 보고** 작업 영역에서 활성으로 표시된 제공자). 이러한 템플릿 중 하나를 선택한 후 **템플릿 편집** 을 선택하여 템플릿을 시작하거나 계속 편집할 수 있습니다.
- 다른 ER 구성 공급자가 소유한 템플릿입니다. 이러한 템플릿 중 하나를 선택한 후 **새 문서** 를 선택하여 ER 구성 공급자가 소유한 복사본을 만든 다음 복사본 편집을 시작할 수 있습니다.

![비즈니스 문서 관리 작업 영역 페이지의 템플릿 목록입니다.](./media/BDM-Overview-EditingTemplate1.png)

**템플릿** 탭에는 선택한 템플릿의 내용이 표시됩니다. **세부 정보** 탭을 선택하여 선택한 템플릿의 세부 정보와 이 템플릿이 있는 ER 형식 구성의 세부 정보를 검토합니다. 모든 템플릿의 상태는 **게시됨** 이고 **개정** 열에는 세부 정보가 포함되어 있지 않습니다. 이는 이러한 템플릿이 현재 편집되고 있지 않음을 의미합니다.

**기능 관리** 작업 영역에서 **비즈니스 문서 관리에 대한 Office와 같은 UI 환경** 이 켜져 있는 경우 **비즈니스 문서 관리** 작업 영역의 기본 그리드에는 ER 구성 공급자(즉, 현재 표시된 공급자가 소유한 템플릿이 표시됩니다. **전자 보고** 작업 공간에서 활성화됨). 이러한 템플릿 중 하나를 선택한 후 **템플릿 편집** 을 선택하여 템플릿을 시작하거나 계속 편집할 수 있습니다.

다른 ER 구성 공급자가 소유한 템플릿으로 작업하려면 **새 문서** 를 선택하여 ER 공급자가 소유한 템플릿의 복사본을 만듭니다. 이후 사본 편집을 시작할 수 있습니다. 자세한 내용은 [비즈니스 문서 관리의 새 문서 사용자 인터페이스](er-business-document-management-new-template-ui.md)를 참조하십시오.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>구성 공급자가 소유한 템플릿 편집 시작

1. 비즈니스 문서 관리 작업 영역의 목록에서 **수표 인쇄 형식** 템플릿을 선택합니다.
2. **세부 정보** 탭을 선택합니다.

![비즈니스 문서 관리 작업 영역 페이지, 세부 정보 탭.](./media/BDM-Overview-EditingTemplate2.png)

**템플릿 편집** 옵션은 선택한 템플릿에 사용할 수 있습니다. 이 옵션은 활성 ER 구성 공급자(이 예시에서는 **Litware, Inc.**)가 소유한 ER 형식 구성의 템플릿에 대해 항상 사용할 수 있습니다. **템플릿 편집** 을 선택하면 기본 ER 형식 구성의 초안 버전에 있는 기존 템플릿을 편집할 수 있습니다.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>다른 제공자가 소유한 템플릿 편집 시작

1. 비즈니스 문서 관리 작업 영역에서 템플릿으로 사용할 문서를 선택합니다.

    ![비즈니스 문서 관리 작업 영역 페이지에서 문서를 선택합니다.](./media/BDM-Overview-EditingTemplate3.png)

2. **새 문서** 를 선택하고 필요한 경우 **제목** 필드에서 편집 가능한 템플릿의 제목을 변경합니다. 텍스트는 자동으로 생성되는 ER 형식 구성의 이름을 지정하는 데 사용됩니다. 편집된 템플릿을 포함할 이 구성의 초안 버전(**고객 FTI 보고서(GER) 사본**)은 현재 사용자에 대해 이 ER 형식을 실행하도록 자동으로 표시됩니다. 동시에 기본 ER 형식 구성의 수정되지 않은 원본 템플릿을 사용하여 다른 사용자에 대해 이 ER 형식을 실행합니다.
3. **이름** 필드에서 자동으로 생성될 편집 가능한 템플릿의 첫 번째 개정 이름을 변경합니다.
4. **주석** 필드에서 편집 가능한 템플릿의 자동 생성 개정에 대한 주석을 변경합니다.
5. **확인** 을 선택하여 편집 프로세스의 시작을 확인합니다.

![새 템플릿을 만들려면 편집 프로세스의 시작을 확인하십시오.](./media/BDM-Overview-EditingTemplate4.png)

공급자가 없으면 생성하도록 제안됩니다. 활성 공급자가 없는 경우 활성화를 위해 선택하도록 제안됩니다.

공급자를 만들려면 **이름** 필드에서 공급자 이름을 변경하고 **인터넷 주소** 필드에서 새 공급자의 인터넷 주소를 업데이트한 다음 **확인** 을 선택하여 확인합니다.

   ![BDM에서 새 공급자를 만듭니다.](./media/bdm_create_provider.png)

기존 공급자를 활성화하려면 **구성 공급자** 필드에서 공급자 이름을 선택하고 **확인** 을 선택하여 공급자를 활성으로 설정합니다.

   ![BDM에서 공급자를 활성화합니다.](./media/bdm_choose_provider.png)

> [!NOTE]
> 각 BDM 템플릿은 공급자를 구성 작성자로 참조합니다. 이것이 템플릿에 활성 공급자가 필요한 이유입니다.


**새 문서** 옵션은 현재 및 개정이 없는 다른 공급자(이 예시에서는 Microsoft)에서 제공하는 ER 형식 구성의 템플릿에 대해 항상 사용할 수 있습니다. 편집된 템플릿은 자동으로 생성되는 새로운 ER 형식 구성에 저장됩니다.



### <a name="start-editing-a-template"></a>템플릿 편집 시작

1. 선택한 템플릿에서 **문서 편집** 을 선택합니다.
2. **이름** 필드에서 자동으로 생성될 편집 가능한 템플릿의 첫 번째 개정 이름을 변경합니다.
3. **주석** 필드에서 편집 가능한 템플릿의 자동 생성 개정에 대한 비고를 변경합니다.

    ![비즈니스 문서 관리 작업 공간 페이지에서 템플릿 편집.](./media/BDM-Overview-EditingTemplate5.png)

4. **확인** 을 선택하여 편집 프로세스의 시작을 확인합니다.

**BDM 템플릿 편집기** 페이지가 열립니다. 선택한 템플릿은 Microsoft 365을(를) 사용하여 온라인 편집에 사용할 수 있습니다.

![비즈니스 문서 관리 템플릿 편집기 페이지입니다.](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>템플릿 편집 Microsoft 365

Microsoft 365를 사용하여 템플릿을 수정할 수 있습니다. 예를 들어 Office online에서 템플릿 머리글의 필드 프롬프트 글꼴을 **일반** 에서 **굵게** 변경합니다. 이러한 변경 사항은 기본 템플릿의 저장소(기본적으로 Azure Blob 저장소)에 저장된 편집 가능한 템플릿에 자동으로 저장됩니다. 이것은 ER 프레임워크에 대해 구성됩니다.

![비즈니스 문서 관리 템플릿 편집기 페이지의 템플릿 헤더에서 글꼴을 굵게 변경합니다.](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>Office 데스크톱 애플리케이션에서 템플릿 편집

> [!NOTE]
> 이 함수은 **SharePoint 문서 유형** 매개 변수가 올바르게 구성된 경우에만 사용할 수 있습니다. 자세한 내용은 [매개 변수 구성](#SetupBdmParameters)을 참조하십시오.

1. Office 데스크톱 애플리케이션(이 예시에서는 Excel)의 함수를 사용하여 템플릿을 수정하려면 **데스크톱 앱에서 열기** 옵션을 선택합니다. 편집 가능한 템플릿은 영구 저장소에서 비즈니스 문서 관리 매개 변수에 SharePoint 폴더로 구성된 임시 저장소로 복사됩니다.
2. Office 데스크톱 Excel 애플리케이션의 임시 파일 저장소에서 템플릿을 열 것인지 확인합니다.

    ![데스크톱 Excel 애플리케이션에서 열린 템플릿입니다.](./media/BDM-Overview-EditingLayout3.png)

3. 템플릿을 수정합니다. 예를 들어, 색상을 **검정색** 에서 **파란색** 으로 업데이트하여 템플릿 헤더에서 필드 프롬프트의 글꼴을 변경합니다.

    ![데스크톱 Excel 애플리케이션을 사용하여 템플릿 헤더의 글꼴 색상을 수정합니다.](./media/BDM-Overview-EditingLayout4.png)

4. 템플릿 변경 사항을 임시 저장소에 저장하려면 Excel 데스크톱 애플리케이션에서 **저장** 을 선택합니다.

    ![데스크톱 Excel 애플리케이션을 사용하여 비즈니스 문서 관리 템플릿 편집기 페이지에 변경 사항을 저장합니다.](./media/BDM-Overview-EditingLayout5.png)

5. Excel 데스크톱 애플리케이션을 닫습니다.
6. 임시 템플릿 저장소를 영구 템플릿 저장소와 동기화하려면 **저장된 복사본 동기화** 를 선택합니다.

> [!NOTE]
> 임시 파일 저장소에 있는 편집 가능한 템플릿의 복사본은 템플릿 편집의 현재 세션 동안만 유지됩니다. **BDM 템플릿 편집기** 페이지를 닫아 이 세션을 마치면 이 복사본이 삭제됩니다. 임시 파일 저장소에서 템플릿을 조정하고 **저장된 복사본 동기화** 를 선택하지 않은 경우 **BDM 템플릿 편집기** 페이지를 닫으려고 하면 도입된 변경 사항을 저장할 것인지 묻는 메시지가 표시됩니다. 템플릿에 대한 변경 사항을 영구 파일 위치에 저장하려면 **예** 를 선택합니다.

### <a name="validate-a-template"></a>템플릿 유효성 검사

1. **BDM 템플릿 편집기** 페이지에서 **문제 확인** 을 선택하여 기본 ER 형식 구성에 대해 수정된 템플릿의 유효성을 검사합니다. 권장 사항(있는 경우)에 따라 기본 ER 형식 구성의 형식 구조와 템플릿을 정렬합니다.
2. 편집 가능한 템플릿과 정렬되어야 하는 기본 ER 형식 구성에서 형식의 현재 구조를 보려면 **형식 표시** 를 선택합니다. 
3. **형식 숨기기** 를 선택하여 창을 닫습니다.

    ![BDM BDM 템플릿 편집기 페이지.](./media/BDM-Overview-EditingTemplate6.png)

4. **BDM 템플릿 편집기** 페이지를 닫습니다.

업데이트된 템플릿은 **템플릿** 탭에 표시됩니다. 편집된 템플릿의 상태는 이제 **초안** 이고 현재 개정은 더 이상 비어 있지 않습니다. 이것은 이 템플릿의 편집 프로세스가 시작되었음을 의미합니다.

![비즈니스 문서 관리 작업 영역 페이지에서 업데이트된 템플릿을 봅니다.](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>수정된 템플릿 테스트 

1. 애플리케이션에서 **USMF** 라는 회사로 변경합니다.
2. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
3. **FTI-00000002** 송장을 선택한 다음 **인쇄 관리** 를 선택합니다.
4. **모듈 - 미수금** \> **문서** \> **자유 텍스트 송장** \> **원본 문서** 레벨을 선택하여 처리할 송장의 범위를 지정합니다.
5. **보고서 형식** 필드에서 지정된 문서 수준에 대한 **고객 FTI 보고서(GER) 복사** ER 형식을 선택합니다.

    ![인쇄 관리 설정 페이지입니다.](./media/BDM-Overview-TestRun1.png)

6. **Esc** 키를 눌러 현재 페이지를 닫습니다.
7. **인쇄** 를 선택한 다음 **선택됨** 을 선택합니다.
8. 문서를 다운로드하고 Excel 데스크톱 애플리케이션을 사용하여 엽니다.

![무료 텍스트 송장 페이지.](./media/BDM-Overview-TestRun2.png)

수정된 템플릿은 선택한 항목에 대한 자유 텍스트 송장 보고서를 생성하는 데 사용됩니다. 템플릿에 도입한 변경 사항이 이 보고서에 어떤 영향을 미치는지 분석하기 위해 다른 애플리케이션 세션에서 템플릿을 수정한 직후에 한 애플리케이션 세션에서 이 보고서를 실행할 수 있습니다.

### <a name="create-an-alternative-template-revision"></a>대체 템플릿 개정 만들기

1. **BDM 템플릿 편집기** 페이지를 열고 **고객 FTI 보고서(GER) 복사** 템플릿을 선택합니다.
2. **개정** 탭에서 **새로 만들기** 를 선택합니다.
3. 필요한 경우 **이름** 필드에서 두 번째 개정의 이름을 변경하고 현재 활성화된 첫 번째 개정을 기반으로 합니다.
4. 필요한 경우 **주석** 필드에서 편집 가능한 템플릿의 자동 생성 개정에 대한 비고를 변경합니다.

    ![비즈니스 문서 관리 작업 영역 페이지에서 템플릿에 대한 개정판을 만듭니다.](./media/BDM-Overview-AddRevision.png)

    영구 템플릿 저장소에 저장된 템플릿의 새 버전을 만들었습니다. 이제 현재 활성으로 선택된 두 번째 개정의 템플릿을 계속 편집할 수 있습니다.

5. 첫 번째 개정을 선택한 다음 **활성으로 설정** 을 선택합니다. 언제든지 템플릿의 해당 개정으로 돌아가려면 다른 개정을 활성으로 선택할 수 있습니다.
6. 두 번째 개정을 선택한 다음 **삭제** 를 선택합니다.
7. **예** 를 선택하여 부하 삭제를 확인합니다. 더 이상 필요하지 않은 비활성 개정을 삭제할 수 있습니다.

### <a name="delete-a-modified-template"></a>수정된 템플릿 삭제

1. **BDM 템플릿 편집기** 페이지에서 **템플릿** 탭을 선택합니다.
2. **삭제** 를 선택합니다.
3. **확인** 을 선택하여 삭제를 확인하면 수정된 템플릿이 포함된 **고객 FTI 보고서(GER) 복사** ER 형식이 삭제됩니다. 다른 옵션을 탐색하려면 **취소** 를 선택하십시오.

### <a name="revoke-changes-of-template"></a>템플릿 변경 취소

현재 활성 공급자가 소유한 ER 형식에서 템플릿을 편집할 때 템플릿에 도입된 변경 사항을 취소할 수 있는 옵션이 제공됩니다.

![비즈니스 문서 관리 작업 영역 페이지에서 템플릿에 대한 변경 사항을 거부합니다.](./media/BDM-Overview-RevokeChanges.png)

1. **BDM 템플릿 편집기** 페이지에서 **템플릿** 탭을 선택합니다.
2. **실행 취소** 를 선택합니다.
3. **확인** 을 선택하여 템플릿에 적용된 변경 사항을 취소하면 수정된 템플릿이 원래 템플릿으로 대체되고 모든 변경 사항이 제거됩니다. 템플릿 변경을 취소하면 템플릿을 삭제할 수 있습니다. 다른 옵션을 탐색하려면 **취소** 를 선택하십시오.

### <a name="publish-a-modified-template"></a>수정된 템플릿 게시

1. **BDM 템플릿 편집기** 페이지의 **템플릿** 탭에서 **게시** 를 선택합니다.
2. **확인** 을 선택하여 게시를 확인하면 수정된 템플릿이 포함된 파생된 **고객 FTI 보고서(GER) 복사** ER 형식의 초안 버전이 완료된 것으로 표시됩니다. 수정된 템플릿은 다른 사용자가 사용할 수 있게 됩니다. 이 ER 형식의 완성된 버전은 템플릿의 마지막 활성 버전만 유지합니다. 다른 수정본은 삭제됩니다. 다른 옵션을 탐색하려면 **취소** 를 선택하십시오.

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>문서 편집을 선택했는데 Finance의 BDM 템플릿 편집기 페이지로 이동하지 않고 Microsoft 365 웹페이지로 이동했습니다.

이 문제는 Microsoft 365 리디렉션과 관련된 알려진 문제입니다. 처음 Microsoft 365 로그인할 때 발생합니다. 이 문제를 해결하려면 브라우저에서 **뒤로** 를 선택하여 이전 페이지로 돌아갑니다.

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>첫 번째 애플리케이션 세션에서 템플릿을 편집하는 방법과 Microsoft 365 두 번째 애플리케이션 세션에서 템플릿을 사용하고 템플릿을 조정하여 내 변경 사항이 생성된 비즈니스 문서에 어떤 영향을 미치는지 확인하는 방법을 이해합니다. Office 데스크톱 애플리케이션을 같은 방식으로 사용할 수 있습니까?

그래 넌 할 수 있어. 첫 번째 애플리케이션 세션에서 **데스크톱 앱에서 열기** 를 선택합니다. 템플릿은 임시 파일 저장소에 저장되고 Office 데스크톱 애플리케이션에서 열립니다. 다음으로 다음 단계를 완료하여 생성된 비즈니스 문서에서 템플릿 변경 사항을 미리 봅니다.

1. Office 데스크톱 애플리케이션을 사용하여 템플릿을 변경합니다.
2. Office 데스크톱 애플리케이션에서 **저장** 을 선택합니다.
3. 첫 번째 애플리케이션 세션의 **BDM 템플릿 편집기** 페이지에서 **저장된 복사본 동기화** 를 선택합니다.
4. 두 번째 애플리케이션 세션에서 이 템플릿 ER 형식을 실행합니다.

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>데스크탑 앱에서 열기를 선택하면 다음 오류 메시지가 나타납니다. "값은 null일 수 없습니다. 매개 변수 이름: externalId." 이 문제를 해결하려면 어떻게 해야 합니까?

이 인스턴스를 배포하는 데 사용된 Azure AD 도메인과 다른 도메인 Azure AD 앱의 현재 인스턴스에 로그인했을 가능성이 큽니다. Office 데스크톱 애플리케이션을 사용하여 편집할 수 있도록 템플릿을 저장하는 데 사용되는 SharePoint 서비스는 동일한 도메인에 속하므로 SharePoint 서비스에 액세스할 수 있는 권한이 없습니다. 이 문제를 해결하려면 올바른 Azure AD 도메인을 가진 사용자의 자격 증명을 사용하여 현재 인스턴스에 로그인합니다.

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 개요](general-electronic-reporting.md)

[ER OPENXML 형식의 보고서 생성을 위한 구성 설계(2016년 11월)](tasks/er-design-reports-openxml-2016-11.md)

[Word 형식으로 보고서를 생성하도록 ER 구성 설계](tasks/er-design-configuration-word-2016-11.md)

[ER을 사용하여 생성한 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md)

[데이터를 가져오도록 전자 보고(ER) 구성 Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>구성 가능한 비즈니스 문서를 지원하기 위해 Finance에서 릴리스된 ER 구성 목록

재무용 ER 구성 [목록](general-electronic-reporting.md#list-of-configurations)은 지속적으로 업데이트됩니다. [글로벌 리포지토리](er-download-configurations-global-repo.md)를 열어 현재 지원되는 ER 구성 목록을 검토합니다. 글로벌 리포지토리를 [필터링](../../../finance/localizations/enhanced-filtering-global-repo.md)하여 구성 가능한 비즈니스 문서를 지원하는 데 사용되는 ER 구성 목록을 검토할 수 있습니다.

![구성 리포지토리 페이지에서 글로벌 리포지토리의 콘텐츠 필터링.](./media/bdm-overview-filterglobalrepo.gif)

다음 표는 구성 가능한 비즈니스 문서를 지원하고 2020년 12월까지 Finance에서 릴리스된 ER 구성 목록을 보여줍니다.

| 데이터 모델 구성    | 형식 구성                           |
|-----------------------------|-------------------------------------------------|
| 선하증권 모델        | 선하증권(Excel)                          |
|                             | 선하증권(Word)                           |
| 원산지 증명서 모델 | 원산지증명서(엑셀)                   |
|                             | 원산지 증명서(Word)                    |
| 송장 모델               | 고객 차변 및 대변 메모(Excel)          |
|                             | 고객 차변 및 대변 메모(Word)           |
|                             | 무료 텍스트 송장(Excel)                       |
|                             | 무료 텍스트 송장(Excel)(BH)                  |
|                             | 무료 텍스트 송장(FR)(Excel)                  |
|                             | 무료 텍스트 송장(LT)(Excel)                  |
|                             | 무료 텍스트 송장(LV)(Excel)                  |
|                             | 무료 텍스트 송장(PL)(Excel)                  |
|                             | 무료 텍스트 송장(CZ)(Excel)                  |
|                             | 무료 텍스트 송장(EE)(Excel)                  |
|                             | 무료 텍스트 송장(HU)(Excel)                  |
|                             | 무료 텍스트 송장(TH)(Excel)                  |
|                             | 무료 텍스트 송장(Word)                        |
|                             | 프로젝트 계약 항목(Excel)             |
|                             | 프로젝트 계약 항목(CZ)(Excel)        |
|                             | 프로젝트 계약 항목(Excel)(BH)        |
|                             | 프로젝트 계약 항목(HU)(Excel)        |
|                             | 프로젝트 계약 항목(LT)(Excel)        |
|                             | 프로젝트 계약 항목(PL)(Excel)        |
|                             | 프로젝트 계약 항목(Word)              |
|                             | 프로젝트 고객 유지 릴리스(Excel)      |
|                             | 프로젝트 고객 유지 릴리스(CZ)(Excel) |
|                             | 프로젝트 고객 유지 릴리스(HU)(Excel) |
|                             | 프로젝트 고객 유지 릴리스(LT)(Excel) |
|                             | 프로젝트 고객 유지 릴리스(PL)(Excel) |
|                             | 프로젝트 고객 유지 릴리스(TH)(Excel) |
|                             | 프로젝트 고객 유지 릴리스(Word)       |
|                             | 프로젝트 송장(Excel)                         |
|                             | 프로젝트 송장(Word)                          |
|                             | 프로젝트 송장(AE)(Excel)                    |
|                             | 프로젝트 송장(CZ)(Excel)                    |
|                             | 프로젝트 송장(Excel)(BH)                    |
|                             | 프로젝트 송장(HU)(Excel)                    |
|                             | 프로젝트 송장(JP)(Excel)                    |
|                             | 프로젝트 송장(LT)(Excel)                    |
|                             | 프로젝트 송장(PL)(Excel)                    |
|                             | 프로젝트 송장(TH)(Excel)                    |
|                             | 프로젝트 송장 가득 참(MY)(Excel)               |
|                             | 프로젝트 송장 단순(MY)(Excel)             |
|                             | 프로젝트 관리 송장(Excel)                  |
|                             | 프로젝트 관리 송장(CZ)(Excel)             |
|                             | 프로젝트 관리 송장(Excel)(BH)             |
|                             | 프로젝트 관리 송장(HU)(Excel)             |
|                             | 프로젝트 관리 송장(JP)(Excel)             |
|                             | 프로젝트 관리 송장(LT)(Excel)             |
|                             | 프로젝트 관리 송장(PL)(Excel)             |
|                             | 프로젝트 관리 송장(Word)                   |
|                             | 선불 송장 구매(Excel)                |
|                             | 구매 사전 송장(Word)                 |
|                             | 판매 선지급 송장(Excel)                   |
|                             | 판매 선지급 송장(Word)                    |
|                             | 판매 선지급 송장(PL)(Excel)              |
|                             | 판매 송장(엑셀)                           |
|                             | 판매 송장(Excel)(BH)                      |
|                             | 판매 송장(Excel)(CZ)                      |
|                             | 판매 송장(Excel)(EE)                      |
|                             | 판매 송장(Excel)(FR)                      |
|                             | 판매 송장(Excel)(HU)                      |
|                             | 판매 송장(Excel)(IN)                      |
|                             | 판매 송장(Excel)(LT)                      |
|                             | 판매 송장(엑셀)(LV)                      |
|                             | 판매 송장(Excel)(PL)                      |
|                             | 판매 송장(엑셀) (TH)                      |
|                             | 판매 송장(Word)                            |
|                             | TMS 상업 송장(Excel)                  |
|                             | TMS 상업 송장(Word)                   |
|                             | 공급 업체 송장 문서(Excel)                 |
|                             | 공급 업체 송장 문서(CZ)(Excel)            |
|                             | 공급 업체 송장 문서(HU)(Excel)            |
|                             | 공급 업체 송장 문서(IN)(Excel)            |
|                             | 공급 업체 송장 문서(LT)(Excel)            |
|                             | 공급 업체 송장 문서(LV)(Excel)            |
|                             | 공급 업체 송장 문서(MY)(Excel)            |
|                             | 공급 업체 송장 문서(Word)                  |
| 주문 모델                 | 계약 확인(엑셀)                  |
|                             | 계약 확인(Word)                   |
|                             | 구매계약 확인(엑셀)         |
|                             | 구매 계약 확인(Word)          |
|                             | 구매 주문(엑셀)                          |
|                             | 구매 주문서(CZ)(Excel)                     |
|                             | 구매 주문 조회(CZ)(Excel)             |
|                             | 구매 주문서(HU)(Excel)                     |
|                             | 구매 주문 조회(HU) (Excel)             |
|                             | 구매 주문서(Word)                           |
|                             | 발주문의(엑셀)                  |
|                             | 구매 주문 조회(Word)                   |
|                             | 판매 주문 확인(Excel)                |
|                             | 판매 주문 확인(CZ)(Excel)           |
|                             | 판매 주문 확인(HU) (Excel)           |
|                             | 판매 주문 확인(Word)                 |
| 패킹리스트 모델          | 용기 내용물(엑셀)                      |
|                             | 컨테이너 내용(Word)                       |
|                             | 목록 로드(Excel)                               |
|                             | 로드 목록(Word)                                |
|                             | 선택 목록(Excel)                            |
|                             | 선택 목록(CZ)(Excel)                       |
|                             | 선택 목록(Word)                             |
|                             | 생산 선택 목록(Excel)                    |
|                             | 프로덕션 선택 목록(Word)                     |
|                             | 로드에 대한 배송 선택 목록(Excel)             |
|                             | 로드에 대한 배송 선택 목록(Word)              |
|                             | 배송을 위한 배송 선택 목록(Excel)         |
|                             | 배송을 위한 배송 선택 목록(Word)          |
|                             | 웨이브의 배송 선택 목록(Excel)             |
|                             | 웨이브(Word)의 배송 선택 목록              |
| 지급 모델               | 고객 결제 상담(엑셀)                 |
|                             | 고객 지급 조언(Word)                  |
|                             | 공급 업체 지급 조언(Excel)                   |
|                             | 공급 업체 지급 조언(Word)                    |
| 인용 모델             | 프로젝트 견적(엑셀)                       |
|                             | 프로젝트 견적(Word)                        |
|                             | 견적요청(엑셀)                   |
|                             | 견적요청 (Accept) (Excel)          |
|                             | 견적요청 (Accept) (Word)           |
|                             | 견적요청(거부) (엑셀)          |
|                             | 견적요청 (거부) (Word)           |
|                             | 견적요청(반품) (엑셀)          |
|                             | 견적요청 (Return) (Word)           |
|                             | 견적요청(Word)                    |
|                             | 판매 견적(엑셀)                         |
|                             | 판매 견적(CZ)(Excel)                    |
|                             | 판매 견적(HU)(Excel)                    |
|                             | 판매 견적(Word)                          |
|                             | 판매 견적 확인(Excel)            |
|                             | 판매 견적 확인(Word)             |
| 조정 모델        | 고객 계정 명세서, Ext(Excel)             |
|                             | 고객 계정 명세서, Ext(CN)(Excel)        |
|                             | 고객 계정 명세서, Ext(Word)              |
|                             | 고객 계정 명세서, 프랑스(Excel)          |
| 알림 모델              | 컬렉션 레터 노트(Excel)                  |
|                             | 컬렉션 레터 노트(CN)(Excel)             |
|                             | 컬렉션 레터 노트(Word)                   |
|                             | 고객 관심 메모(Excel)                  |
|                             | 고객 관심 메모(Word)                   |
| 운송장 모델               | 로드텐더(엑셀)                             |
|                             | 로드 텐더(Word)                              |
|                             | 구매 주문 포장 전표(Excel)             |
|                             | 구매 주문서 포장 전표(CZ)(Excel)        |
|                             | 구매 주문서 포장 전표(Word)              |
|                             | 경로(엑셀)                                   |
|                             | 경로(단어)                                    |
|                             | 판매 주문 포장 전표(Excel)                |
|                             | 판매 주문 포장 전표(CZ)(Excel)           |
|                             | 판매 주문 포장 전표(LT)(Excel)           |
|                             | 판매 주문 포장 전표(PL)(Excel)           |
|                             | 판매 주문 포장 전표(Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
