---
title: 생성된 문서의 사용자 지정 저장 위치 지정
description: 이번에는 전자 보고(ER) 형식이 생성하는 문서의 저장 위치 목록을 확장하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 61a1e46497d650e2c063a5fe7537d17cf7aa1828a5a4504bb781e84aeb88f04a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460867"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>생성된 문서의 사용자 지정 저장 위치 지정

[!include[banner](../includes/banner.md)]

전자 보고(ER) 프레임워크의 API(응용 프로그래밍 인터페이스)를 사용하면 ER 형식이 생성하는 문서의 저장 위치 목록을 확장할 수 있습니다. 이 항목에는 사용자 지정 저장 위치를 추가하기 위해 완료해야 하는 주요 작업에 대한 개요가 포함되어 있습니다.

## <a name="prerequisites"></a>전제 조건

연속 빌드를 지원하는 토폴로지를 배포해야 합니다. (자세한 내용은 [지속적인 빌드 및 테스트 자동화를 지원하는 토폴로지 배포](/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation)를 참조하십시오.) 다음 역할 중 하나에 대해 이 토폴로지에 대한 액세스 권한이 있어야 합니다.

- 전자 보고 개발자
- 전자 보고 기능 컨설턴트
- 시스템 관리자

또한 이 토폴로지의 개발 환경에 대한 액세스 권한이 있어야 합니다.

## <a name="create-or-import-an-er-format-configuration"></a>ER 형식 구성 생성 또는 가져오기

[현재 토폴로지에서 새 ER 형식을 만들어 사용자 지정](tasks/er-format-configuration-2016-11.md) 저장 위치를 추가하려는 문서를 생성합니다. 또는 [기존 ER 형식을 이 토폴로지로 가져옵니다](general-electronic-reporting-manage-configuration-lifecycle.md).

![형식 디자이너 페이지.](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> 작성하거나 가져오는 ER 형식에는 다음 형식 요소 중 하나 이상이 포함되어야 합니다.
>
> - 파일
> - 폴더
> - 합병
> - 첨부 파일

## <a name="create-a-new-document-type"></a>새 문서 유형 만들기

ER 형식이 생성하는 문서가 라우팅되는 방식을 지정하려면 [전자 보고(ER) 대상을 구성](electronic-reporting-destinations.md)해야 합니다. 생성된 문서를 파일로 저장하도록 구성된 각 ER 대상에서 문서 관리 프레임워크의 문서 유형을 지정해야 합니다. 다양한 문서 유형을 사용하여 다양한 ER 형식이 생성하는 문서를 라우팅할 수 있습니다.

1. 이전에 만들거나 가져온 ER 형식에 대한 새 [문서 유형](../../fin-ops/organization-administration/configure-document-management.md)을 추가합니다. 다음 그림에서 문서 유형은 **FileX** 입니다.
2. 이 문서 유형을 다른 문서 유형과 구별하려면 이름에 특정 키워드를 포함하십시오. 예를 들어, 다음 그림에서 이름은 **(LOCAL) 폴더** 입니다.
3. **클래스** 필드에서 **파일 첨부** 를 지정하십시오.
4. **그룹** 필드에서 **파일** 을 지정하십시오.

![문서 유형 페이지.](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> 문서 유형은 회사별로 다릅니다. 여러 회사에서 대상이 구성된 ER 형식을 사용하려면 각 회사에서 별도의 문서 유형을 구성해야 합니다.

## <a name="review-source-code"></a>소스 코드 검토

**ERDocuManagement** 클래스의 **insertFile()** 메소드 코드를 검토하십시오. 생성된 파일이 기록에 첨부되는 동안 **AttachingFile()** 이벤트가 발생합니다.


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

**AttachingFile()** 이벤트는 다음 ER 대상이 처리될 때 발생합니다.

- **아카이브** – 이 대상이 사용되면 실행되는 ER 형식에 대한 새 기록이 ERFormatMappingRunJobTable 테이블에 생성됩니다. 이 기록의 **Archived** 필드는 **False** 로 설정됩니다. ER 형식이 성공적으로 실행되면 생성된 문서가 이 기록에 첨부되고 **AttachingFile()** 이벤트가 발생합니다. 이 ER 대상에서 선택한 문서 유형에 따라 첨부 파일의 저장 위치가 결정됩니다(Microsoft Azure Storage 또는 Microsoft SharePoint 폴더).
- **작업 아카이브** – 이 대상이 사용되면 실행되는 ER 양식에 대한 새 기록이 ERFormatMappingRunJobTable 테이블에 생성됩니다. 이 기록의 **Archived** 필드는 **True** 로 설정됩니다. ER 형식이 성공적으로 실행되면 생성된 문서가 이 기록에 첨부되고 **AttachingFile()** 이벤트가 발생합니다. ER 매개 변수에 구성된 문서 유형에 따라 첨부 파일(Azure Storage 또는 SharePoint 폴더)의 저장 위치가 결정됩니다.

![전자 보고 매개 변수 페이지.](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>ER 대상 구성

1. 생성하거나 가져온 ER 형식의 앞에서 언급한 요소(파일, 폴더, 병합 또는 첨부 파일) 중 하나에 대해 보관 대상을 구성합니다. 지침은 [ER 구성 대상](/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11)을 참조하십시오.
2. 구성된 대상에 대해 이전에 추가한 문서 유형을 사용하십시오. (이 항목의 예시에서 문서 유형은 **FileX** 입니다.)

![대상 설정 대화 상자.](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>소스 코드 수정

1. Microsoft Visual Studio 프로젝트에 새 클래스를 추가하고 앞에서 언급한 **AttachingFile()** 이벤트를 구독하는 코드를 작성합니다. (사용되는 확장성 패턴에 대한 자세한 내용은 [EventHandlerResult를 사용하여 응답](/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result)을 참조하십시오.) 예를 들어 새 클래스에서 다음 작업을 수행하는 코드를 작성합니다.

    1. AOS(Application Object Server) 서비스를 실행하는 서버의 로컬 파일 시스템 폴더에 생성된 파일을 저장합니다.
    2. 파일이 ER 실행 작업 로그의 기록에 첨부되는 동안 새 문서 유형(예: 이름에 '(LOCAL)' 키워드가 있는 **FileX** 유형)이 사용되는 경우에만 생성된 파일을 저장하십시오.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. 프로젝트를 다시 빌드하십시오.

## <a name="run-the-er-format-that-you-created-or-imported"></a>생성하거나 가져온 ER 형식을 실행합니다.

1. 생성하거나 가져온 ER 형식을 실행합니다.
2. **조직 관리 \> 전자 보고 \> 전자 보고 작업** 으로 이동합니다. 이 실행 작업에 대해 생성되었으며 생성된 파일이 첨부된 기록을 찾습니다.
3. 로컬 **C:\\0** 폴더를 탐색하여 동일한 생성 파일을 찾습니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 대상](electronic-reporting-destinations.md)
- [확장성 홈페이지](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]