---
title: Finance Insights 구성 - 버전 10.0.20 이상
description: 이 토픽에서는 버전 10.0.20 이상의 Finance Insights에서 사용할 수 있는 기능을 사용하도록 시스템을 구성하는 방법에 대해 설명합니다.
author: ShivamPandey-msft
ms.date: 06/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex,nofollow
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: cea6258d3a99ba33e73acd2508ec7b6c11d15859
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451507"
---
# <a name="configuration-for-finance-insights---version-10020-and-later"></a>Finance Insights 구성 - 버전 10.0.20 이상

[!include [banner](../includes/banner.md)]



Finance insights는 Microsoft Dynamics 365 Finance의 기능을 Dataverse, Azure 및 AI Builder와 결합하여 조직에 강력한 예측 도구를 제공합니다. 이 토픽에서는 시스템이 Finance Insights에서 사용할 수 있는 기능을 사용할 수 있도록 Dynamics 365 Finance 버전 10.0.20을 구성하는 방법에 대해 설명합니다.

> [!NOTE]
> 이 토픽에서 설명하는 구성 단계는 Finance 버전 10.0.20 이상에만 적용됩니다. '버전 10.0.19 이하에서 Finance insights를 설정하려면 [Finance insights 구성 - 버전 10.0.19까지](configure-for-fin-insites.md)를 참조하세요.

## <a name="deploy-finance"></a>Finance 배포

환경을 배포하는 순서는 다음과 같습니다.

1. Microsoft Dynamics Lifecycle Services(LCS)에서 Finance 환경을 생성하거나 업데이트합니다. 환경에는 금융 및 운영 앱의 앱 버전 10.0.20 이상이 필요합니다.
2. 환경은 샌드박스의 고가용성(HA) 환경이어야 합니다. (이 유형의 환경은 Tier-2 환경이라고도 합니다.) 자세한 내용은 [환경 계획](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)을 참조하십시오.
3. 샌드박스 환경에서 Finance insights를 구성하는 경우 예측이 작동하도록 프로덕션 데이터를 해당 환경에 복사해야 할 수 있습니다. 예측 모델은 예측을 구축하기 위해 다년간의 데이터를 사용합니다. Contoso 데모 데이터에는 예측 모델을 적절하게 훈련시키기에 충분한 기록 데이터가 포함되어 있지 않습니다. 

## <a name="configure-dataverse"></a>Dataverse 구성

Finance insights용으로 Dataverse를 구성하려면 다음 단계를 따르십시오.

1. LCS에서 환경 페이지를 열고 **Power Platform 통합** 섹션이 이미 설정되어 있는지 확인합니다.

    - 이미 설정되어 있는 경우 Finance 환경에 연결된 Dataverse 환경 이름이 나열되어야 합니다.
    - 아직 설정되지 않은 경우 다음 단계를 따르세요.

        1. **Power Platform 통합** 섹션에서 **설정** 을 선택합니다. 환경 설정에는 최대 1시간이 소요될 수 있습니다.
        2. Dataverse 환경이 성공적으로 설정되면 Finance 환경에 연결된 Dataverse 환경 이름이 나열되어야 합니다.

        > [!NOTE]
        > 환경 설정을 완료한 후 **앱용 CDS 연결** 을 선택하지 **마십시오**. Finance insights에는 이 버튼이 필요하지 않습니다. 선택하면 LCS에서 필요한 환경 추가 기능을 구성할 수 없습니다.

## <a name="configure-azure"></a>Azure 구성

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Azure Cloud Shell을 사용하여 Finance insights Data Lake 리소스 설정

# <a name="use-a-windows-powershell-script"></a>[Windows PowerShell 스크립트 사용](#tab/use-a-powershell-script)

[Azure Data Lake로 내보내기 구성](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md)에 설명된 Azure 리소스를 쉽게 설정할 수 있도록 Windows PowerShell 스크립트를 제공하고 있습니다. 수동으로 설정하려면 이 절차를 건너뛰고 대신 [수동 설정](#manual-setup) 섹션의 절차를 완료하십시오.

> [!NOTE]
> 다음 절차에 따라 Windows PowerShell 스크립트를 실행합니다. Azure CLI에서 **시도하기** 옵션을 사용하거나 컴퓨터에서 스크립트를 실행하는 경우 설정이 작동하지 않을 수 있습니다.

다음 단계에 따라 Windows PowerShell 스크립트를 사용하여 Azure를 구성합니다. Azure 리소스 그룹, Azure 리소스 및 Azure AD 애플리케이션을 만들 수 있는 권한이 있어야 합니다. 필요한 권한에 대한 정보는 [Azure AD 권한 확인](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app)을 참조하십시오.

1. [Azure portal](https://portal.azure.com)에서 대상 Azure 구독으로 이동합니다.
2. **검색** 필드 오른쪽에서 **Cloud Shell** 을 선택합니다.
3. **PowerShell** 을 선택합니다.
4. 스토리지를 만들라는 메시지가 표시되면 스토리지를 만듭니다.
5. **Azure CLI** 탭에서 **복사** 를 선택합니다.
6. 메모장에서 새 파일을 열고 Windows PowerShell 스크립트를 붙여넣습니다.
7. 파일을 **ConfigureDataLake.ps1** 로 저장합니다.
8. Cloud Shell에서 업로드 메뉴 옵션을 사용하여 Windows PowerShell 스크립트를 세션에 업로드합니다.
9. **.\ConfigureDataLake.ps1** 스크립트를 실행합니다.
10. 메시지에 따라 스크립트를 실행합니다.
11. 스크립트 출력의 정보를 사용하여 LCS에 Data Lake로 내보내기 추가 기능을 설치합니다.

### <a name="manual-setup"></a>수동 설정

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Azure AD 테넌트에 애플리케이션 추가

1. [Azure portal](https://portal.azure.com)에서 **Azure Active Directory** 로 이동합니다.
2. **관리 \> 엔터프라이즈 애플리케이션** 을 선택합니다.
3. 앱 ID로 다음 애플리케이션을 검색합니다.

    | 응용 프로그램                              | 앱 ID                               |
    |------------------------------------------|--------------------------------------|
    | Microsoft Dynamics ERP 마이크로 서비스     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | Microsoft Dynamics ERP 마이크로 서비스 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | AI Builder 권한 부여 서비스         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

앞의 애플리케이션을 찾을 수 없으면 다음 단계를 시도하십시오.

1. 로컬 컴퓨터의 **시작** 메뉴에서 **powershell** 을 검색합니다.
2. **Windows PowerShell** 을 길게 누른(또는 오른쪽 클릭) 다음 **관리자 권한으로 실행** 을 선택합니다.
3. 다음 명령을 실행하여 **AzureAD** 모듈을 설치합니다.

    `Install-Module -Name AzureAD`

4. 계속하기 위해 NuGet 공급자가 필요한 경우 **Y** 를 선택하여 설치하세요.
5. "신뢰할 수 없는 저장소" 메시지가 표시되면 **Y** 를 선택하여 계속합니다.
6. 추가해야 하는 각 애플리케이션에 대해 다음 명령을 실행하여 애플리케이션을 Azure AD에 추가합니다. 메시지가 표시되면 Azure AD 관리자로 로그인합니다.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Azure 리소스 만들기

> [!NOTE]
> Dataverse 환경이 있는 동일한 Azure AD 인스턴스에서 다음 리소스를 만들어야 합니다. 다른 Azure AD 인스턴스의 리소스는 사용할 수 없습니다.

1. 스토리지 계정 만들기:

    1. [Azure portal](https://portal.azure.com)에서 스토리지 계정을 만듭니다.
    2. **스토리지 계정 만들기** 대화 상자에서 다음 필드를 설정합니다.

        - **위치** – 환경이 위치한 데이터 센터를 선택하십시오.
        - **성능** – **표준** 을 선택하는 것이 좋습니다.
        - **계정 종류** – **StorageV2** 를 선택해야 합니다.

    3. **고급 옵션** 대화 상자에서 **Data Lake storage Gen2** 옵션에 대해 **계층 구조 네임스페이스** 기능 아래에서 **활성화** 를 선택합니다. 이 기능을 활성화하지 않으면 금융 및 운영 앱이 Power BI 데이터 흐름과 같은 서비스를 사용하여 작성하는 데이터를 사용할 수 없습니다.
    4. **검토하고 만들기** 를 선택합니다. 배포가 완료되면 새 리소스가 Azure Portal에 표시됩니다.
    5. 생성한 스토리지 계정으로 이동합니다.
    6. 왼쪽 메뉴에서 **액세스 키** 를 선택합니다.
    7. 스토리지 계정의 이름을 복사하여 저장합니다. 나중에 키 자격 증명 모음 암호를 설정할 때 이 값을 제공해야 합니다.

2. 키 자격 증명 모음 만들기:

    1. [Azure portal](https://portal.azure.com)에서 키 자격 증명 모음을 만듭니다.
    2. **키 자격 증명 모음 만들기** 대화 상자의 **위치** 필드에서 환경이 위치한 데이터 센터를 선택합니다.
    3. 키 자격 증명 모음을 만든 후 **Key Vault 개요** 로 이동하여 DNS 이름을 복사하여 저장합니다. 나중에 Data Lake 추가 기능을 설정할 때 이 값을 제공해야 합니다.

3. Azure AD 애플리케이션을 만들고 등록합니다.

    1. [Azure portal](https://portal.azure.com)에서 **Azure Active Directory** 로 이동한 후 **앱 등록** 을 선택합니다.
    2. **새 애플리케이션 등록** 을 선택하고 다음 필드를 설정합니다.

        - **이름** – 앱의 이름을 입력합니다.
        - **애플리케이션 유형** - **웹 API** 를 선택합니다.
        - **리디렉션 URI 설정** – Dynamics 365 인스턴스의 URL(예: `https://yourdynamicsinstance.dynamics.com/auth`)을 입력합니다.

    3. 방금 만든 앱으로 이동하여 **애플리케이션(클라이언트) ID** 값을 복사하여 저장합니다. 나중에 키 자격 증명 모음 암호를 설정할 때 이 값을 제공해야 합니다.
    4. **API 권한** 으로 이동하여 다음 단계를 따르세요.

        1. **권한 추가** 를 선택합니다.
        2. **Azure Key vault** 를 선택합니다.
        3. 위임된 권한을 선택한 후 **user\_impersonation** 을 선택합니다.
        4. **권한 추가** 를 선택합니다.

    5. 앱 메뉴에서 **인증서 \& 암호** 를 선택한 후 다음 단계에 따라 Key Vault 암호를 만듭니다.

        1. **새 클라이언트 암호** 를 선택합니다..
        2. **키 설명** 필드에 이름을 입력합니다.
        3. 기간을 선택한 후 **추가** 를 선택합니다. **값** 필드에 암호가 생성됩니다.
        4. 클라이언트 암호 값을 복사하여 저장합니다. 나중에 키 자격 증명 모음 암호를 설정할 때 이 값을 제공해야 합니다.

4. Key Vault 암호 만들기:

    1. 이전에 만든 키 자격 증명 모음으로 이동하여 **암호** 을 선택합니다.
    2. 다음 테이블의 각 암호 이름에 대해 다음 단계를 따르십시오.

        1. **생성/가져오기** 를 선택합니다.
        2. **암호 만들기** 대화 상자의 **업로드 옵션** 필드에서 **수동** 을 선택합니다.
        3. 테이블에서 암호 이름과 값을 만듭니다.
        4. **활성화됨** 을 선택한 다음 **만들기** 를 선택합니다. 암호가 만들어지고 Key Vault에 추가됩니다.

        | 암호 이름                       | 암호 값                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | 앞서 만든 애플리케이션의 앱 ID입니다.                                      |
        | app-secret                        | 앞서 저장한 클라이언트 암호입니다.                                                    |
        | storage-account-name              | **storageaccount1** 과 같이 앞서 만든 스토리지 계정의 이름입니다.       |

5. 키 자격 증명 모음에 액세스할 수 있도록 애플리케이션에 권한 부여:

    1. [Azure portal](https://portal.azure.com)에서 앞서 만든 키 자격 증명 모음를 엽니다.
    2. 액세스 정책을 선택합니다.
    3. 다음 테이블의 각 애플리케이션에 대해 다음 단계를 따르십시오.

        1. **액세스 정책 추가** 를 선택하여 액세스 정책을 만듭니다.
        2. **암호 권한** 필드의 테이블에서 권한을 선택합니다.
        3. **보안 주체 선택** 필드의 테이블에서 애플리케이션 표시 이름을 검색합니다.
        4. **선택** 을 선택합니다.
        5. **추가** 를 선택합니다.
        6. **저장** 을 선택합니다.

        | 응용 프로그램                                              | 사용 권한 |
        |----------------------------------------------------------|-------------|
        | 생성한 새 애플리케이션의 표시 이름 | 가져오기, 리스트   |
        | **Microsoft Dynamics ERP 마이크로 서비스**                 | 가져오기, 리스트   |

6. 스토리지 계정에 액세스하기 위한 역할 할당:

    1. [Azure portal](https://portal.azure.com)에서 앞서 만든 스토리지 계정을 엽니다.
    2. **Access Control(IAM)** 을 선택한 후 **역할 할당** 을 선택합니다.
    3. **추가, 역할 할당 추가** 를 선택합니다.
    4. 다음 테이블의 각 애플리케이션에 대해 다음 단계를 따르십시오.

        1. 테이블에서 역할을 선택합니다.
        2. **Azure AD 사용자, 그룹 또는 서비스 주체** 로 설정된 **액세스 권한 할당** 필드를 그대로 둡니다.
        3. **선택** 필드에 테이블의 애플리케이션을 입력합니다.
        4. **저장** 을 선택합니다.

        | 응용 프로그램                                              | 역할                        |
        |----------------------------------------------------------|-----------------------------|
        | 생성한 새 애플리케이션의 표시 이름 | 담당자                       |
        | 생성한 새 애플리케이션의 표시 이름 | 기여자                 |
        | 생성한 새 애플리케이션의 표시 이름 | 스토리지 계정 Contributor |
        | 생성한 새 애플리케이션의 표시 이름 | Storage Blob 데이터 담당자     |
        | **AI Builder 권한 부여 서비스**                     | Storage Blob 데이터 Reader    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a>Data Lake로 내보내기 추가 기능 구성

다음 단계에 따라 LCS를 사용하여 환경에 Data Lake로 내보내기 추가 기능을 추가합니다.

1. LCS에 로그인한 후, 페이지 우측의 환경 이름에서 **전체 세부 정보** 를 선택합니다.
2. **환경 추가 기능** 섹션에서 **새 추가 기능 설치** 를 선택합니다.
3. **Data Lake로 내보내기** 추가 기능을 선택합니다.
4. 다음 값을 입력합니다.

    | 값                                                              | 설명 |
    |--------------------------------------------------------------------|-------------|
    | Key Vault가 위치한 Azure 구독의 테넌트 ID | 스토리지 계정, 앱 및 키 자격 증명 모음이 위치한 테넌트 ID입니다. 이 값을 얻으려면 [Azure portal](https://portal.azure.com)을 열고 **Azure Active Directory** 로 이동하여 **테넌트 ID** 값을 복사합니다. |
    | Key Vault의 DNS 이름 제공                             | 키 자격 증명 모음의 DNS 이름(예: `https://customkeyvault.vault.azure.net/`)입니다. |
    | 스토리지 계정의 이름이 포함된 암호 제공   | **storage-account-name** |
    | Data Lake에 액세스하는 데 사용할 앱 ID의 암호 이름          | **app-id** |
    | 앱 클라이언트 암호의 암호 이름                                  | **app-secret** |

5. 약관에 동의한 후 **설치** 를 선택합니다.

몇 분 안에 추가 기능이 설치됩니다.

## <a name="configure-the-finance-insights-add-in"></a>Finance insights 추가 기능 구성

> [!NOTE]
> 이전에 인사이트 가져오기 추가 기능을 설치한 경우 다음 절차를 완료하기 전에 제거하십시오.

Finance insights 추가 기능을 설치하려면 다음 단계를 따르십시오.

1. LCS에 로그인한 후, 페이지 우측의 환경 이름에서 **전체 세부 정보** 를 선택합니다.
2. **환경 추가 기능** 섹션에서 **새 추가 기능 설치** 를 선택합니다.
3. **Finance insights** 추가 기능을 선택합니다.
4. 약관에 동의한 후 **설치** 를 선택합니다.

추가 기능을 설치하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="feedback-and-support"></a>피드백 및 지원

피드백 제공에 관심이 있거나 지원이 필요한 경우 [Finance Insights](mailto:fiap@microsoft.com)로 이메일을 보내주세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
