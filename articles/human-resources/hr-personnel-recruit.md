---
title: 구직 후보자 모집
description: 이 항목에서는 Dynamics 365 Human Resources에서 후보자를 모집하는 방법을 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 77d37cba84fcd6fb8f93da79b10db2db91d91db0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452245"
---
# <a name="recruit-job-candidates"></a>구직 후보자 모집


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources는 모집 요청을 관리하도록 도와줍니다. 또한 구직자를 직원으로 원활하게 전환하도록 도와줍니다. 조직에서 별도의 모집 애플리케이션을 사용하는 경우 모집 프로세스에 다음 단계가 포함될 수 있습니다.

- Human Resources에 모집 요청을 입력합니다.
- 모집 애플리케이션에서 Human Resources의 후보자 추천을 받습니다.
- Human Resources에서 후보자 승인 프로세스를 완료합니다.

별도의 모집 애플리케이션을 사용하지 않는 경우 Human Resources에서 수동으로 후보자를 관리할 수도 있습니다.

> [!NOTE]
> 관리자나 개발자가 Human Resources를 타사 모집 애플리케이션과 통합하려면 [Dataverse 통합 구성](hr-admin-integration-common-data-service.md) 및 [Dataverse 가상 테이블 구성](hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요
>
> [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics)에서도 모집 통합 앱을 찾을 수 있습니다.
>
## <a name="enable-recruiting-requests"></a>모집 요청 활성화

Human Resources에서 모집 요청을 제출하려면 먼저 **Human Resources 공유 매개 변수** 에서 기능을 활성화해야 합니다.

1. **인사 관리** 작업 영역에서 **연결** 을 선택합니다.
2. **설정** 에서 **Human Resources 공유 매개 변수** 를 선택합니다.
3. **구인** 탭의 **구인** 에서 **구인 요청 활성화** 를 **예** 로 설정합니다.

## <a name="add-a-recruiting-request-location"></a>모집 요청 위치 추가

조직에 여러 위치가 있는 경우 요청자가 신입사원이 근무할 위치를 선택하도록 위치를 추가할 수 있습니다. 위치는 채용 공고에 포함됩니다.

1. 검색 창에 **모집 요청 위치** 를 입력합니다.
2. **새로 만들기** 를 선택합니다.
3. **모집 요청 위치** 필드에 위치 이름을 입력합니다.

    ![모집 요청 위치 추가.](./media/hr-recruit-0a-add-location.png)

4. **설명** 에 위치에 대한 설명을 입력합니다.
5. **위치** 에서 **추가** 를 선택합니다. **새 주소** 대화 상자가 나타나면 위치의 주소를 입력합니다.

    ![주소 입력.](./media/hr-recruit-0b-address.png)

6. **연락처 정보** 에서 위치의 연락처 정보를 입력합니다.
7. **저장** 을 선택합니다.

## <a name="add-a-recruiting-request"></a>모집 요청 추가

관리자는 Human Resources에서 모집 요청을 제출할 수 있습니다. 별도의 모집 애플리케이션을 사용하는 경우 이 단계를 완료하면 모집 요청이 전송되고 해당 애플리케이션에서 모집 프로세스가 시작됩니다. 그렇지 않으면 이 절차를 완료하여 자체 내부 모집 프로세스를 위한 워크플로를 시작하세요.

1. **직원 셀프 서비스** 를 선택합니다.
2. **내 팀** 탭을 선택합니다.
3. **모집 요청** 을 선택합니다.

    ![모집 요청 시작.](./media/hr-recruit-1-request-to-recruit.png)

4. **설정**, **직무**, **예상 시작 날짜** 필드를 입력합니다.

    ![모집 요청 완료.](./media/hr-recruit-2-request-to-recruit.png)

5. **계속** 을 선택합니다. 직위에 대한 모집 요청이 나타납니다.
6. **일반** 아래의 **모집자** 드롭다운에서 모집자를 선택한 다음 **모집 요청 위치** 드롭다운에서 위치를 선택합니다.
7. **직무** 에서 필요에 따라 정보를 변경한 다음 **직무에서 세부 정보 만들기** 를 선택합니다.

    ![직무에서 세부 정보 만들기.](./media/hr-recruit-3-create-details-from-job.png)

    나머지 모집 요청은 입력한 작업에 대한 기본 정보로 채워집니다.

8. **외부 설명** 에서 외부 공개용 직무 설명을 입력합니다.
9. **직위** 에서 **추가** 를 선택하고 이 모집 요청의 직위를 선택합니다.

    ![직위 추가.](./media/hr-recruit-4-select-position.png)

10. **기술** 에서 **추가** 를 선택한 다음 기술을 선택합니다.
11. **교육 요구 사항** 에서 **추가** 를 선택한 다음 **교육** 및 **교육 수준** 드롭다운에서 값을 선택합니다.

    ![교육 요구 사항 추가.](./media/hr-recruit-5-select-educational-requirements.png)

12. **설명** 에서 필요에 따라 설명을 추가합니다.
13. **보상** 의 **수준** 드롭다운에서 수준을 선택한 다음 필요에 따라 **하한 임계값**, **제어 지점** 및 **상한 임계값** 을 조정합니다.
14. 모집 요청이 완료되고 모집 프로세스를 시작할 준비가 되면 메뉴 모음에서 **활성화** 를 선택합니다.

    ![모집 요청 활성화.](./media/hr-recruit-6-activate-recruit-request.png)

15. **저장** 을 선택합니다.

## <a name="view-and-edit-your-recruiting-requests"></a>모집 요청 보기 및 편집

관리자가 자신의 요청을 보려면 다음 단계를 수행합니다.

1. **직원 셀프 서비스** 를 선택합니다.
2. **내 팀** 탭을 선택합니다.
3. **내 팀 정보** 에서 **모집 요청** 탭을 선택합니다.

    ![모집 요청 탭 선택.](./media/hr-recruit-7-recruiting-requests.png)

4. 모집 요청을 보거나 편집하려면 그리드에서 선택합니다.

HR 전문가가 모든 채용 요청을 보려면 다음을 수행합니다.

1. **인사 관리** 를 선택합니다.
2. **모집 요청** 을 선택합니다.

    ![인사 관리에서 모집 요청 보기.](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. 모집 요청을 보거나 편집하려면 그리드에서 선택합니다.

## <a name="add-or-edit-a-candidate-profile"></a>후보자 프로필 추가 또는 수정

조직에서 모집 요청을 관리하기 위해 다른 애플리케이션과 통합한 경우 모집 요청이 해당 애플리케이션으로 전달됩니다. 그런 다음 모집 애플리케이션이 후보자 정보를 Human Resources에 다시 보냅니다. 그렇지 않으면 내부 모집 프로세스에 따라 수동으로 후보자 정보를 입력할 수 있습니다.

1. **인사 관리** 를 선택합니다.
2. **연결** 을 선택합니다.
3. **모집** 에서 **후보자** 를 선택합니다.

    ![후보자 보기.](./media/hr-recruit-9-candidates.png)

4. 후보자를 추가하려면 **새로 만들기** 를 선택합니다. 기존 후보자를 편집하려면 목록에서 후보자를 선택한 다음 **편집** 을 선택합니다. 후보자 프로필이 나타납니다.
5. **후보자 요약** 에서 필요에 따라 후보자 정보를 입력하거나 편집합니다.
6. **모집 요청** 에서 후보자를 연결할 모집 요청을 선택합니다. 그런 다음 **예상 시작 날짜**, **고용 관리자**, **직위** 및 **설명 필드** 를 적절하게 작성합니다.

    ![모집 요청으로 연결.](./media/hr-recruit-10-link-to-recruiting-request.png)

7. 후보자 기록에 포함하려는 다음 영역의 모든 정보를 작성합니다.

    - **설명**
    - **전문 경험**
    - **연락처 정보**
    - **교육**
    - **기술**
    - **자격증**
    - **심사**

8. **저장** 을 선택합니다.

## <a name="hire-a-candidate"></a>후보자 채용

후보자를 채용할 준비가 되면 이 절차에 따라 후보자를 직원으로 전환합니다.

1. **후보자** 페이지에서 **채용** 을 선택합니다.

    ![후보자 채용.](./media/hr-recruit-11-hire.png)

2. **새 작업자 채용** 페이지의 **세부 정보** 에 모든 필드를 입력합니다.

    ![신입사원 세부 정보 입력.](./media/hr-recruit-12-hire-new-worker.png)

3. **직위 세부 정보** 에서 필요에 따라 정보를 확인하고 변경합니다.
4. **온보딩 검사 목록** 에서 이 직원과 관계가 있는 온보딩 검사 목록을 선택합니다.
5. **계속** 을 선택하여 직원 레코드를 만듭니다.

    > [!NOTE]
    > 후보자 레코드는 조직의 워크플로에 따라 직원 레코드가 되기 전에 추가 승인 단계를 거칠 수 있습니다.

## <a name="decide-not-to-hire-a-candidate"></a>후보자를 채용하지 않기로 결정

후보자를 채용하지 않기로 한 경우 이 절차에 따라 심사 과정에서 후보자를 제거합니다. 

1. **후보자** 페이지에서 **채용 안 함** 을 선택합니다.

    ![후보자를 채용하지 않음.](./media/hr-recruit-13-do-not-hire.png)

2. **사유 코드** 를 선택하고 설명을 추가합니다.
3. **확인** 을 선택합니다.

## <a name="dismiss-a-candidate"></a>후보자 제외

필요한 경우 채용 후 후보자를 제외할 수 있습니다. 예를 들어 후보자가 귀사의 제안을 거부하거나 첫날에 출근하지 않을 수 있습니다.

- **후보자** 페이지에서 **후보자 제외** 를 선택합니다.

    ![후보자 제외.](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>참고 항목

[Dataverse 가상 테이블 구성](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[인력 구성](hr-personnel-departments-jobs-positions.md)<br>
[직무 구성 요소 설정](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
