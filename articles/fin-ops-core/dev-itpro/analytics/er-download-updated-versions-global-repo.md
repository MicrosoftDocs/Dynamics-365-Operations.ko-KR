---
title: 업데이트된 버전의 ER 구성 가져오기
description: 이 주제에서는 구성 서비스의 글로벌 리포지토리에서 업데이트된 버전의 전자 보고(ER) 구성을 가져오는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 712bccbd48775cadc069ef5e8a04f9aae3c9f223137bcd394ff1815a720393b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460946"
---
# <a name="import-updated-versions-of-er-configurations"></a>업데이트된 버전의 ER 구성 가져오기

[!include [banner](../includes/banner.md)]

전자 보고(ER) [리포지토리](general-electronic-reporting.md#Repository)는 [ER 구성](general-electronic-reporting.md#Configuration)을 공유하는 데 사용됩니다. 다른 리포지토리에서 Microsoft Dynamics 365 Finance 인스턴스로 ER 구성을 [가져올](download-electronic-reporting-configuration-lcs.md) 수 있습니다. ER 구성을 가져올 때 [구성 공급자](general-electronic-reporting.md#Provider)는 공유할 수 있도록 새 [버전](general-electronic-reporting.md#component-versioning) 리포지토리를 게시할 수 있습니다.

이번에는 구성 서비스의 글로벌 리포지토리에서 업데이트된 버전의 ER 구성을 가져오는 방법에 대해 설명합니다. 자세한 내용은 [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, 구성 서비스](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration)를 참조하십시오.

## <a name="review-the-available-updated-versions"></a>사용 가능한 업데이트 버전 검토

1. 다음 역할 중 하나를 사용하여 재무에 로그인합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 버전 업데이트 가져오기** 를 선택합니다.

    ![현지화 구성 페이지.](./media/er-download-updated-versions-global-repo1.png)

4. **전자 보고 구성 버전 업데이트 가져오기** 대화 상자의 **실행 모드** 필드에서 **사용 가능한 업데이트만 표시** 를 선택합니다. 이후 **확인** 을 선택합니다. 

    ![실행 모드 필드는 사용 가능한 업데이트만 표시로 설정됩니다.](./media/er-download-updated-versions-global-repo2.png)

5. 받은 메시지를 검토합니다. 이러한 메시지는 현재 Finance 인스턴스의 ER 구성 및 글로벌 리포지토리의 내용과 비교하는 방법에 대한 다음 정보를 제공합니다.

    - 총 ER 구성 수
    - 글로벌 리포지토리에 없는 ER 구성
    - 현재 Finance 인스턴스에서 이미 최신 버전을 사용할 수 있는 ER 구성(이 ER 구성의 전체 목록을 보려면 **메시지 세부 정보** 링크를 선택하십시오.)

        ![다음 구성의 최신 버전은 이미 가져온 메시지 및 메시지 세부정보입니다.](./media/er-download-updated-versions-global-repo3.png)

    - 글로벌 리포지토리에서 최신 버전을 사용할 수 있고 현재 Finance 인스턴스로 가져올 수 있는 ER 구성(이 ER 구성의 전체 목록을 보려면 **메시지 세부 정보** 링크를 선택하십시오.)

        ![사용 가능한 업데이트 메시지 및 메시지 세부 정보](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>사용 가능한 업데이트 버전 가져오기

1. 다음 역할 중 하나를 사용하여 재무에 로그인합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 버전 업데이트 가져오기** 를 선택합니다.
4. **전자 보고 구성 버전 업데이트 가져오기** 대화 상자의 **실행 모드** 필드에서 **최신 업데이트 가져오기** 를 선택하여 글로벌 리포지토리에서 현재 Finance 인스턴스로 ER 구성의 최신 버전을 가져옵니다.
5. 가져오기를 위한 **일괄 작업** 을 예약하려면 **백그라운드** FastTab에서 실행에서 일괄 처리 옵션을 **예** 로 설정합니다. 가져오기를 주기적으로 반복하려면 필요한 반복을 구성합니다.

    ![최신 업데이트 가져오기로 설정된 실행 모드 필드.](./media/er-download-updated-versions-global-repo5.png)

6. **확인** 을 선택합니다.
7. 가져온 구성 버전을 알아보려면 다음 단계 중 하나를 따르십시오.

    - 일괄 작업을 사용하는 대신 대화식으로 가져오기를 실행하는 경우 수신 메시지를 검토하십시오.

        ![대화형 가져오기 실행 중에 받은 메시지입니다.](./media/er-download-updated-versions-global-repo6.png)

    - 가져오기를 일괄 처리 모드로 실행하는 경우 다음 단계를 따르십시오.

        1. **일반** \> **문의** \> **일괄 작업** \> **내 일괄 작업** 으로 이동합니다.
        2. **전자 보고 구성 버전 업데이트 가져오기** 작업을 찾아 선택한 다음 작업 창의 **일괄 작업** 탭에서 **일괄 작업 기록** 을 선택하여 작업 기록을 봅니다.
        3. **일괄 작업 기록** 페이지에서 **로그** 를 선택합니다. 이후 수신한 메시지에서 **메시지 세부 사항** 링크를 선택하여 작업 로그를 보십시오.

        ![작업 로그.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> 가져온 버전을 즉시 사용할 수 있으므로 글로벌 리포지토리에서 직접 프로덕션 환경으로 ER 구성의 업데이트된 버전을 가져오기 위해 반복 배치 작업을 예약하지 않는 것이 좋습니다. 대신 이 접근 방식을 사용하여 ER 구성 버전을 샌드박스 환경에 배포합니다. 이후 프로덕션 환경에 배포하기 전에 샌드박스 환경에서 평가할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 개요](general-electronic-reporting.md)
- [구성 서비스의 글로벌 저장소에서 ER 구성 다운로드](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]