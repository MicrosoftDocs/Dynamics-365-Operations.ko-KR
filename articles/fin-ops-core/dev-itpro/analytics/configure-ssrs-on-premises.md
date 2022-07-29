---
title: 온 프레미스 배포를 위한 SQL Server Reporting Services 구성
description: 이번에는 온 프레미스 배포를 위한 SQL Server Reporting Services(SSRS) 구성에 대한 정보를 제공합니다.
author: PeterRFriis
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 3853158afdab545dacda996c984b265eb8947db7f90faf80319841eb01c14910
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460979"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>온 프레미스 배포를 위한 SQL Server Reporting Services 구성

[!include [banner](../includes/banner.md)]

이 항목의 단계를 사용하여 Microsoft Dynamics 365 Finance + Operations (on-premises) 배포에 대해 SQL Server Reporting Services(SSRS)를 구성합니다.

1. 보고 서비스 구성 관리자 애플리케이션을 엽니다.
2. 현재 컴퓨터의 이름이어야 하는 기본 **서버 이름** 과 **보고서 서버 인스턴스** 인 **MSSQLSERVER** 를 그대로 둡니다.
3. **연결** 을 클릭합니다.

    [![보고 서비스 구성 연결 중.](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. **서비스 계정** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인합니다.

    [![서비스 계정 탭.](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. **웹 서비스 URL** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인하십시오.

    [![웹 서비스 URL 탭.](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. **데이터베이스** 탭을 클릭하고 **데이터베이스 이름** 및 **자격 증명 설정** 이 다음 그림과 일치하는지 확인합니다.

    > [!NOTE]
    > 새 데이터베이스를 생성해야 합니다. 이렇게 하려면 **데이터베이스 변경** 을 클릭한 다음 새 데이터베이스 이름이 다음과 같은지 확인합니다. **DynamicsAxReportServer**.

    [![데이터베이스 탭.](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. **Web Portal URL** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인하십시오.

    > [!NOTE]
    > 포털을 만들고 올바르게 구성하려면 **적용** 을 클릭해야 합니다.

    [![웹 포털 URL 탭.](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    포털이 구성된 후 **웹 포털** 탭은 다음 그래픽과 일치합니다.

    [![웹 포털 탭.](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. 보고서 URL을 클릭하여 SQL Server Reporting Services 웹 포털을 봅니다.
9. 포털에 있을 때 **Dynamics** 라는 새 폴더를 만듭니다.

    [![다이나믹 폴더.](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. **Reporting Services 구성 관리자** 에서 **전자 메일 설정** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인합니다.

    [![이메일 설정 탭.](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. **실행 계정** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인하십시오.

    [![실행 계정 탭.](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    **암호화 키** 탭에서 기본 설정을 변경하지 마십시오.

    [![암호화 키 탭.](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. **구독 설정** 탭을 클릭하고 설정이 다음 그래픽과 일치하는지 확인합니다.

    [![구독 설정 탭.](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    **수평 확장 배포** 탭에서 기본 설정을 변경하지 마십시오.

    [![확장 배포 탭.](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    **Power BI 통합** 탭에서 기본 설정을 변경하지 마십시오.

    [![Power BI 통합 탭.](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. **끝내기** 를 클릭하여 **보고 서비스 구성 관리자** 를 닫습니다.

    [![보고 서비스 구성 관리자를 닫습니다.](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
