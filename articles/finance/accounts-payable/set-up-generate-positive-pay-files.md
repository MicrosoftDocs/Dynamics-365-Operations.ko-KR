---
title: 플러스 급여 파일 설정 및 생성
description: 이 항목에서는 플러스 급여를 설정하고 플러스 급여 파일을 생성하는 방법을 설명합니다.
author: panolte
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 992c73b1ba1f461542873a7df97f1539b99fc015c3e6ef090993e90212993851
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450385"
---
# <a name="set-up-and-generate-positive-pay-files"></a>플러스 급여 파일 설정 및 생성

[!include [banner](../includes/banner.md)]

이 항목에서는 플러스 급여를 설정하고 플러스 급여 파일을 생성하는 방법을 설명합니다. 

은행에 제공되는 전자 수표 목록을 생성하려면 플러스 급여를 설정하세요. 그런 다음 은행에 수표가 제시되면 은행은 이를 수표 목록과 비교합니다. 이 수표가 목록의 수표와 일치하면 은행이 해당 수표를 지웁니다. 수표가 목록의 수표와 일치하지 않으면 은행은 검토를 위해 수표를 보관합니다.

## <a name="security-for-positive-pay-files"></a>플러스 급여 파일에 대한 보안
포지티브 페이 파일에는 수취인 및 수표 금액에 대한 중요한 정보가 포함될 수 있습니다. 따라서 파일이 생성된 시점부터 은행에서 파일을 받을 때까지 적절한 보안 조치를 사용해야 합니다. 플러스 급여 파일은 웹 브라우저에서 지정한 위치에 다운로드됩니다. 플러스 급여 파일에는 중요한 정보가 포함될 수 있으므로 권한이 있는 사용자만 Microsoft Dynamics 365 Finance에서 이 정보를 만들고 볼 수 있는 액세스 권한을 갖는 것이 중요합니다. 다음 표를 사용하여 필요한 권한을 결정하세요.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>작업</th>
<th>권한</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>은행 계좌</strong> 목록 페이지 또는 <strong>은행 계좌</strong> 페이지에서 플러스 급여 파일을 생성합니다.</td>
<td><ul>
<li><strong>은행 플러스 급여 정보 유지</strong>(BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong>(BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>플러스 급여 파일 생성</strong> 페이지에서 여러 법인 및 은행 계좌에 대한 플러스 급여 파일을 생성합니다.</td>
<td><ul>
<li><strong>은행 플러스 급여 정보 유지</strong>(BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong>(BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>플러스 급여 파일 요약</strong> 페이지에서 플러스 급여 파일을 봅니다.</td>
<td><strong>여러 법인에 대한 은행 플러스 급여 정보 보기</strong>(BankPositivePayView)</td>
</tr>
<tr class="even">
<td><strong>플러스 급여 파일 요약</strong> 페이지에서 은행 플러스 급여 파일을 확인합니다.</td>
<td><strong>플러스 급여 파일 확인</strong>(BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td><strong>플러스 급여 파일 요약</strong> 페이지에서 은행 플러스 급여 파일을 회수합니다.</td>
<td><strong>플러스 급여 파일 회수</strong>(BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>플러스 급여 형식 설정
포지티브 페이 파일은 데이터 엔터티를 사용하여 생성됩니다. 플러스 급여 파일을 생성하기 전에 수표 정보를 은행과 통신할 수 있는 형식으로 변환하는 데 사용할 변환 입력 형식을 설정해야 합니다. **플러스 급여 형식** 페이지에서 파일 형식 식별자와 설명을 만들 수 있습니다. 변환 입력 형식은 XML 유형이어야 합니다. 특정 형식은 사용 중인 변환 파일에 따라 다릅니다. 예를 들어 제공된 샘플 XSLT(Extensible Stylesheet Language Transformations) 파일은 **XML-Element** 형식을 사용합니다. **변환에 사용할 파일 업로드** 작업을 사용하여 은행에서 요구하는 형식에 대한 변환 파일의 위치를 지정합니다.

## <a name="example-xslt-file-for-positive-pay-file"></a>예: 플러스 급여 파일에 대한 XSLT 파일

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
  <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:value-of select="'
'" />
    <Document>
      <xsl:value-of select="'
'" />
      <!--Header Begin-->
      <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
      <xsl:value-of select="'
'" />
      <!--Header End-->
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
        <!--Cheque Detail begin-->
        <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
            <xsl:value-of select='string("Yes")'/>
          </xsl:when>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
            <xsl:value-of select='string("No")'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='string(" ")'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("Payment")'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='CHEQUENUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='AMOUNTCUR/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("BOA-#1812")'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
            <xsl:value-of select='VENDGROUP/text()'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='CUSTGROUP/text()'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="'
'" />
      </xsl:for-each>
    </Document>
  </xsl:template>
</xsl:stylesheet>
```

> [!NOTE]
> XSLT의 XML 이름은 XML의 노드 대/소문자와 일치해야 합니다. XSLT 및 XML 파일은 모두 대/소문자를 구분합니다. 

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>은행 계좌에 플러스 급여 형식 할당
플러스 급여 정보를 생성하려는 각 은행 계좌에 대해 이전 섹션에서 지정한 플러스 급여 형식을 할당해야 합니다. **은행 계좌** 페이지에서 은행 계좌에 해당하는 플러스 급여 형식을 선택합니다. **플러스 급여 시작 날짜** 필드에서 플러스 급여 파일을 생성할 처음 날짜를 입력합니다. 이 필드에 날짜를 입력하는 것이 중요합니다. 그렇지 않으면 생성한 첫 번째 플러스 급여 파일에는 이 은행 계좌에 대해 생성된 모든 수표가 포함됩니다.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>플러스 급여 파일에 대한 일련 번호 지정
각 플러스 급여 파일에는 고유 번호가 있어야 합니다. **현금 및 은행 관리 매개 변수** 페이지의 **번호 시퀀스** 탭을 사용하여 플러스 급여 파일에 대한 번호 시퀀스를 생성합니다.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>단일 은행 계좌에 대한 플러스 급여 파일 생성
단일 법인 및 단일 은행 계좌에 대한 플러스 급여 파일을 생성할 수 있습니다. 동시에 여러 법인 및 은행 계좌에 대한 플러스 급여 파일을 생성하는 방법에 대한 정보는 다음 섹션을 참조하세요. 단일 법인 및 단일 은행 계좌에 대한 플러스 급여 파일을 생성하려면 **은행 계좌** 페이지에서 **플러스 급여 파일 생성** 대화 상자를 엽니다. **마감 날짜** 필드에 플러스 급여 파일에 포함할 마지막 확인 날짜를 입력합니다. 이 수표 날짜가 끝날 때까지 플러스 급여 파일에 포함되지 않은 모든 수표가 파일에 포함됩니다.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>여러 은행 계좌에 대한 플러스 급여 파일 생성
여러 은행 계좌에 대한 플러스 급여 파일을 생성하려면 **플러스 급여 파일 생성** 정기 작업을 사용합니다. 파일에 대한 플러스 급여 형식을 선택하고 모든 법인에 대해 파일을 생성할지 아니면 선택한 법인에 대해 파일을 생성할지 지정합니다. 지정된 플러스 급여 형식을 사용하는 모든 은행 계좌 또는 선택한 은행 계좌에 대해 플러스 급여 파일을 생성할 수도 있습니다. **마감 날짜** 필드에 플러스 급여 파일에 포함할 마지막 확인 날짜를 입력합니다. 이 수표 날짜가 끝날 때까지 플러스 급여 파일에 포함되지 않은 모든 수표가 파일에 포함됩니다.

## <a name="view-the-results-of-positive-pay-file-generation"></a>플러스 급여 파일 생성 결과 보기
플러스 급여 파일이 생성된 후 **플러스 급여 파일 요약** 페이지에서 결과를 볼 수 있습니다 개별 수표의 세부 정보를 보려면 **플러스 급여 파일** 세부 정보 페이지를 사용하세요.

## <a name="confirm-a-positive-pay-file"></a>플러스 급여 파일 확인
포지티브 페이 파일에 나열된 수표가 지불되면 은행으로부터 확인 번호를 받게 됩니다. 그런 다음 플러스 급여 파일을 확인할 수 있습니다. **플러스 급여 파일 요약** 페이지에서 상태가 **생성됨** 인 플러스 급여 파일을 선택한 다음 **확인 입력** 작업을 선택합니다. 플러스 급여 파일을 확인하면 은행에서 받은 확인 번호가 기록됩니다.

## <a name="recall-a-positive-pay-file"></a>플러스 급여 파일 회수
포지티브 페이 파일을 변경해야 하는 경우 리콜할 수 있습니다. **플러스 급여 파일 요약** 페이지에서 상태가 **생성됨** 인 플러스 급여 파일을 선택한 다음 **회수** 작업을 선택합니다. 플러스 급여 파일의 각 수표에 대해 해당 수표가 플러스 급여 파일에 포함되었는지를 나타내는 필드가 재설정됩니다. 그런 다음 회수된 수표가 포함된 새 플러스 급여 파일을 만들 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
