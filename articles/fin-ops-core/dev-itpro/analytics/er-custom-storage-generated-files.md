---
title: 생성된 문서의 사용자 지정 저장 위치 지정
description: 이번에는 전자 보고(ER) 형식으로 생성된 문서의 저장 위치 목록을 확장하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 337e760f28161721d886c7bbec09b5ff8dbfad45
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8460996"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>생성된 문서의 사용자 지정 저장 위치 지정

[!include[banner](../includes/banner.md)]

전자 보고(ER) 프레임워크의 API(응용 프로그래밍 인터페이스)를 사용하면 ER 형식이 생성하는 문서의 저장 위치 목록을 확장할 수 있습니다. 이번에는 ER 대상을 생성하는 작업을 기본 대상 팩토리에 위임한 다음 자체 대상 논리가 있는 사용자 지정 클래스를 구현하여 생성된 문서에 대한 사용자 지정 저장 위치를 추가하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>전제 조건

연속 빌드를 지원하는 토폴로지를 배포합니다. 자세한 내용은 [지속적인 빌드 및 테스트 자동화를 지원하는 토폴로지 배포](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)를 참조하십시오. 다음 역할 중 하나에 대해 이 토폴로지에 대한 액세스 권한이 있어야 합니다.

- 전자 보고 개발자
- 전자 보고 기능 컨설턴트
- 시스템 관리자

또한 이 토폴로지의 개발 환경에 대한 액세스 권한이 있어야 합니다.

이 주제의 모든 작업은 **USMF** 회사에서 완료할 수 있습니다.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>고정 자산 롤포워드 ER 형식 가져오기

사용자 지정 저장 위치를 추가하려는 문서를 생성하려면 **고정 자산 롤포워드** ER 형식 구성을 현재 토폴로지로 [가져오십시오](er-download-configurations-global-repo.md).

![구성 리포지토리 페이지입니다.](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>고정 자산 롤포워드 보고서 실행

1. **고정 자산** \> **조회 및 보고** 로 이동 \> **거래 보고서** \> **고정 자산 롤포워드**.
2. **시작 날짜** 필드에 **2017년 1월 1일**(2017년 1월 1일)을 입력합니다.
3. **종료 날짜** 필드에 **2017년 1월 31일**(2017년 1월 31일)을 입력합니다.
4. **통화 필드** 에서 **회계 통화** 를 선택합니다.
5. **형식 매핑** 필드에서 **고정 자산 롤포워드** 를 선택합니다.
6. **확인** 을 선택합니다.

![고정 자산 롤포워드 보고서에 대한 런타임 대화 상자입니다.](./media/er-custom-storage-generated-files-runtime-dialog.png)

Microsoft Excel에서 생성되어 다운로드할 수 있는 아웃바운드 문서를 검토합니다. 이 동작은 [대상이](electronic-reporting-destinations.md) 구성되지 않고 대화형 모드에서 실행되는 ER 형식의 [기본 동작](electronic-reporting-destinations.md#default-behavior)입니다.

## <a name="review-the-source-code"></a>소스 코드 검토

`AssetRollForwardService` 클래스의 `generateReportByGER()` 메서드 코드를 검토합니다. 이 `Run()` 메서드는 ER 프레임워크를 호출하고 **고정 자산 롤포워드** 보고서를 생성하는 데 사용됩니다.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>소스 코드 수정

1. Visual Studio 프로젝트에서 새 클래스를 추가하고(이 예시에서는 `AssetRollForwardDestination`) 생성된 **고정 자산 롤포워드** 보고서에 대한 사용자 지정 대상을 구현하는 코드를 작성합니다.

    - 이 `new()` 메서드는 원래 ER 대상 개체와 생성된 보고서를 저장해야 하는 사용자 지정 위치를 지정하는 애플리케이션 논리 기반 매개 변수를 가져오도록 설계되었습니다. 이 예시에서 사용자 지정 위치는 AOS(Application Object Server) 서비스를 실행하는 서버의 로컬 파일 시스템 폴더 이름입니다.
    - 생성된 문서를 AOS 서비스를 실행하는 서버의 로컬 파일 시스템 폴더에 저장하는 `saveFile()` 방식이다.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. Visual Studio 프로젝트에서 새 클래스(이 예시에서는 `AssetRollForwardDestinationFactory`)를 추가하고 대상 생성을 기본 대상 팩토리에 위임하는 사용자 지정 대상 팩토리를 설정하고 파일 대상을 자신의 대상으로 래핑하는 코드를 작성합니다.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. 기존 `AssetRollForwardService` 클래스를 수정하고 보고서 실행기에 대한 사용자 지정 대상 팩토리를 설정하는 코드를 작성합니다. 사용자 지정 대상 팩터리를 구성할 때 대상 폴더를 지정하는 애플리케이션 기반 매개 변수가 전달됩니다. 이러한 방식으로 해당 대상 폴더는 생성된 파일을 저장하는 데 사용됩니다.

    > [!NOTE] 
    > 지정된 폴더(이 예시에서는 **c:\\0**)가 AOS 서비스를 실행하는 서버의 로컬 파일 시스템에 있는지 확인하십시오. 그렇지 않으면 런타임에 [DirectoryNotFoundException](/dotnet/api/system.io.directorynotfoundexception) 예외가 발생합니다.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. 프로젝트를 다시 빌드하십시오.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>고정 자산 롤포워드 보고서 다시 실행

1. **고정 자산** \> **조회 및 보고** 로 이동 \> **거래 보고서** \> **고정 자산 롤포워드**.
2. **시작 날짜** 필드에 **2017년 1월 1일** 을 입력합니다.
3. **종료 날짜** 필드에 **2017년 1월 31** 일을 입력합니다.
4. **통화 필드** 에서 **회계 통화** 를 선택합니다.
5. **형식 매핑** 필드에서 **고정 자산 롤포워드** 를 선택합니다.
6. **확인** 을 선택합니다.
7. 로컬 **C:\\0** 폴더를 찾아 생성된 파일을 찾습니다.

> [!NOTE]
> 이 예시의 `originDestination` 개체에서 `AssetRollForwardDestination` 개체가 사용되지 않기 때문에 ER 형식 [대상](electronic-reporting-destinations.md)에 대한 구성은 런타임에 무시됩니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 대상](electronic-reporting-destinations.md)
- [확장성 홈페이지](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]