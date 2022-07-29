---
title: 연결된 애플리케이션을 사용하여 애플리케이션 메타데이터에 액세스
description: 이 항목의 단계에서는 Regulatory Configuration Service 사용자가 메타데이터를 사용하여 새로운 전자 보고 모델 매핑을 설계할 수 있는 방법을 설명합니다.
author: NickSelin
ms.date: 06/29/2019
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
ms.openlocfilehash: 6d99ca41a9a24ef8ac0fe31e703cad79d41216fa726fa1d354ac19db90706954
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460725"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>연결된 애플리케이션을 사용하여 애플리케이션 메타데이터에 액세스

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할의 RCS(Regulatory Configuration Service) 사용자가 재무 및 운영의 메타데이터를 사용하여 새로운 전자 보고(ER) 모델 매핑을 설계할 수 있는 방법을 설명합니다. 애플리케이션 메타데이터는 RCS 연결 애플리케이션을 사용하여 온라인으로 액세스됩니다. 샘플 ER 모델 매핑은 해외 무역 거래에 액세스하도록 구성됩니다. 이 단계를 완료하려면 [RCS에서 먼저 구성 공급자 생성 및 활성으로 표시](er-configuration-provider-mark-it-active-2016-11.md) 항목의 단계를 완료해야 합니다. [ER 구성을 사용하여 애플리케이션 메타데이터 액세스](access-application-metadata-er-configuration.md) 항목의 단계를 완료하지 않은 경우 [전자 보고 예시](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip)를 다운로드하고 다음 ER 구성을 저장합니다. 대외 무역 메타데이터.xml; 대외 무역 model.xml; 대외 무역 mapping.xml을 입력한 다음 절차의 단계를 완료합니다.

## <a name="prerequisites"></a>전제 조건
1. **조직 관리 작업 공간** > **전자 보고** 로 이동합니다. 
2. 샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 **활성** 으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 [구성 공급자 만들기](er-configuration-provider-mark-it-active-2016-11.md) 절차의 단계를 완료하고 활성으로 표시합니다. 

## <a name="get-required-er-configurations"></a>필요한 ER 구성 가져오기
1. **보고 구성** 을 클릭합니다. 
2. [ER 구성 절차를 사용하여 Access 애플리케이션 메타데이터](access-application-metadata-er-configuration.md)의 단계를 이미 완료했다면 현재 RCS 인스턴스에 필요한 모든 ER 구성(외국 무역 메타데이터, 모델 및 매핑 구성)이 이미 있는 것입니다. 이 하위 작업의 나머지 단계를 모두 건너뛸 수 있습니다. 
3. **교환** 을 클릭합니다. 
4. **XML 파일에서 로드** 를 클릭합니다. 
5. **찾아보기** 를 클릭하고 **대외 무역 메타데이터.xml** 파일을 선택하십시오. 
6. **확인** 을 클릭합니다. 
7. **교환** 을 클릭합니다. 
8. **XML 파일에서 로드** 를 클릭합니다. 
9. **찾아보기** 를 클릭하고 **대외 무역 model.xml** 파일을 선택하십시오. 
10. **확인** 을 클릭합니다. 
11. **교환** 을 클릭합니다. 
12. **XML 파일에서 로드** 를 클릭합니다. 
13. **찾아보기** 를 클릭하고 **대외 무역 mapping.xml** 파일을 선택하십시오. 
14. **확인** 을 클릭합니다. 

## <a name="register-a-connected-application"></a>연결된 애플리케이션 등록
1. 페이지를 닫습니다. 
2. 페이지를 닫습니다. 
3. **조직 관리 작업 공간** > **전자 보고** 로 이동합니다. 
4. **연결된 애플리케이션** 을 클릭합니다. 
5. 구성된 애플리케이션이 Azure 기반이고 현재 RCS 사용자가 액세스할 수 있는지 확인합니다. 또한 현재 RCS 사용자는 선택한 애플리케이션에 대한 액세스 권한이 있어야 하며 애플리케이션의 메타데이터에 액세스할 수 있는 권한을 부여하는 역할을 수행하는 이 애플리케이션의 사용자로 등록되어 있어야 합니다. 
6. **새로 만들기** 를 클릭합니다. 
7. **이름** 필드에 'MyConnectedApp'을 입력합니다. 
8. **애플리케이션** 필드에 'https:// mycompany.operations.dynamics.com'을 입력합니다. 
9. **테넌트** 필드에 'mycompany.onmicrosoft.com'을 입력합니다. 
10. **저장** 을 클릭합니다. 
11. 구성된 애플리케이션에 대한 연결을 확인할 때 **원격 애플리케이션에 연결** 페이지에서 **선택한 원격 애플리케이션에 연결하려면 여기를 클릭하십시오** 링크를 클릭합니다. 
12. **연결 확인** 을 클릭합니다. 
13. **닫기** 를 클릭합니다. 
14. 연결 유효성 검사가 성공하면 현재 그리드에 구성된 애플리케이션에 대한 버전 및 테넌트 세부 정보가 업데이트됩니다. 

## <a name="review-existing-model-mapping-configuration"></a>기존 모델 매핑 구성 검토
1. 페이지를 닫습니다. 
2. **보고 구성** 을 클릭합니다. 
3. 트리에서 **대외 무역 모델** 을 확장합니다. 
4. 트리에서 **대외 무역 모델\대외 무역 매핑** 을 선택합니다. 
5. **전제 조건** 섹션을 확장합니다. 

    > [!NOTE]
    > 현재 이 매핑은 메타데이터 구성을 나타냅니다. 이 모델 매핑이 설계되는 동안 이 구성의 애플리케이션 메타데이터가 제공됩니다. 

6. **디자이너** 를 클릭합니다. 
7. **디자이너** 를 클릭합니다. 
8. 트리에서 **Dynamics 365 for Operations\Table 기록** 를 선택합니다. 
9. **루트 추가** 를 클릭합니다. 
10. **테이블** 필드에 값을 입력하거나 선택합니다. 

    > [!NOTE]
    > 현재 이 매핑은 메타데이터 구성을 나타냅니다. 이 모델 매핑이 설계되는 동안 이 구성의 애플리케이션 메타데이터가 제공됩니다. 

11. **취소** 를 클릭합니다. 
12. 페이지를 닫습니다. 
13. 페이지를 닫습니다. 

## <a name="assign-connected-application-to-model-mapping"></a>연결된 애플리케이션을 모델 매핑에 할당 
1. **편집** 을 클릭합니다. 
2. **MyConnectedApp** 애플리케이션을 선택합니다. 

    > [!NOTE]
    > 현재 이 매핑은 선택한 연결된 애플리케이션의 메타데이터를 참조합니다. 동일한 매핑이 메타데이터 구성과 연결된 애플리케이션을 동시에 참조하는 경우 연결된 애플리케이션의 메타데이터가 사용됩니다. 

3. **디자이너** 를 클릭합니다. 
4. **디자이너** 를 클릭합니다. 
5. 트리에서 **Dynamics 365 for Operations\Table 기록** 를 선택합니다. 
6. **루트 추가** 를 클릭합니다. 
7. **테이블** 필드에 값을 입력하거나 선택합니다. 

    > [!NOTE]
    > 이 매핑이 할당된 연결된 애플리케이션의 모든 메타데이터를 사용하므로 이제 두 개 이상의 애플리케이션 테이블이 제공되었습니다. 

8. **취소** 를 클릭합니다. 
9. **확인** 을 클릭합니다. 

    > [!NOTE]
    > 이 매핑에 할당된 연결된 애플리케이션의 메타데이터 세부 정보를 사용하여 설명된 데이터 원본 항목과 데이터 모델의 요소를 성공적으로 바인딩했습니다. 

10. 페이지를 닫습니다. 
11. 페이지를 닫습니다. 

다른 버전 애플리케이션의 메타데이터를 사용하여 이 모델 매핑을 평가해야 하는 경우 연결된 다른 애플리케이션을 등록하고 이 모델 매핑에 할당하고 새 메타데이터에 대해 유효성을 검사합니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
