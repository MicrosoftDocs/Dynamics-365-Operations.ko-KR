---
title: Base64StringToContainer ER 함수
description: 이번에는 Base64StringToContainer 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3e813c628bfe783fb8e93fc5d7e8b275405245c42710f9ea691d4c06afff0d84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8461003"
---
# <a name="base64stringtocontainer-er-function"></a>Base64StringToContainer ER 함수

[!include [banner](../includes/banner.md)]

이 `BASE64STRINGTOCONTAINER` [함수](er-formula-language.md#Functions)는 *스트링* 유형의 지정된 입력을 *[Container](er-functions-category-container.md)* 유형의 데이터 항목으로 변환합니다.

## <a name="syntax"></a>구문

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>인수

`input`: *스트링*

*스트링* 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*다음 포함*

블롭(BLOB) 형식의 결과 이진 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

입력 스트링이 바이너리-텍스트 인코딩 체계의 올바른 Base64 그룹을 제공하지 않으면 '매개 변수가 유효하지 않습니다' 예외가 발생합니다.

## <a name="example"></a>예시

모델 매핑에서 다음 데이터 소스를 정의합니다.

- **DocuTypeGroup** 애플리케이션 열거를 참조하는 *Dynamics 365 for Operations / 열거* 유형의 루트 **DocuTypeGroupEnum** 데이터 소스
- **CustTable** 애플리케이션 테이블을 참조하는 *Dynamics 365 for Operations / 테이블 기록* 유형의 루트 **고객** 데이터 소스
- 다음과 같은 방식으로 구성된 *계산된 필드* 유형의 **\#미디어** 데이터 소스:

    - **Customer** 데이터 원본의 하위 데이터 원본으로 추가됩니다.
    - 표현식이 포함되어 있습니다 `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- 다음과 같은 방식으로 구성된 *계산된 필드* 유형의 **\#MediaAsBase** 64스트링 데이터 소스:

    - **Customer.'\#Media'** 데이터 소스의 하위 데이터 소스로 추가됩니다.
    - `Customer.'#Media'.'getFileContentAsBase64String()'` 표현식이 포함되어 있습니다.

- 다음과 같이 구성된 *계산된 필드* 유형의 **\#BlobFomBase64** 데이터 소스:

    - **Customer.'\#Media'** 데이터 소스의 하위 데이터 소스로 추가됩니다.
    - `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'` 표현식이 포함되어 있습니다.

이 예시에서 **\#MediaAsBase64String** 데이터 소스는 현재 미디어 첨부 파일의 바이너리 콘텐츠를 바이너리-텍스트 인코딩 체계의 Base64 그룹을 나타내는 텍스트로 인코딩합니다. **\#BlobFomBase64** 데이터 소스는 Base64 스트링을 디코딩하고 BLOB 형식의 이진 값을 반환합니다.

![ER 모델 매핑 디자이너 페이지의 샘플 데이터 소스.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>추가 리소스

[컨테이너 함수](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
