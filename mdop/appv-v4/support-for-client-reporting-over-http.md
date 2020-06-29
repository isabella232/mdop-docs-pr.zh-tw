---
title: 透過 HTTP 的用戶端報告支援
description: 透過 HTTP 的用戶端報告支援
author: dansimp
ms.assetid: 4a26ac80-1fb5-4c05-83de-4d06793f7bf2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4e1759bb4df39ac403e2837c4083275a8b3436f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800789"
---
# <span data-ttu-id="46fa1-103">透過 HTTP 的用戶端報告支援</span><span class="sxs-lookup"><span data-stu-id="46fa1-103">Support for Client Reporting over HTTP</span></span>


<span data-ttu-id="46fa1-104">App-V 用戶端的版本4.6 現在支援在將用戶端報告資料傳送到發佈伺服器時，使用 HTTP 通訊。</span><span class="sxs-lookup"><span data-stu-id="46fa1-104">Version 4.6 of the App-V client now supports the use of HTTP communication when sending client reporting data to the publishing server.</span></span> <span data-ttu-id="46fa1-105">此功能支援客戶已完成設定以收集及處理用戶端資料之自訂 HTTP （S）發佈伺服器的情況。</span><span class="sxs-lookup"><span data-stu-id="46fa1-105">This feature supports scenarios where a customer has implemented a custom HTTP(S) publishing server that is configured to collect and process client data.</span></span>

<span data-ttu-id="46fa1-106">如需有關 HTTP 發佈伺服器的詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="46fa1-106">For more information on HTTP publishing servers, see</span></span> <https://go.microsoft.com/fwlink/?LinkId=157426>

## <span data-ttu-id="46fa1-107">經由 HTTP 的用戶端報告</span><span class="sxs-lookup"><span data-stu-id="46fa1-107">Client Reporting over HTTP</span></span>


<span data-ttu-id="46fa1-108">當用戶端從發佈伺服器的發佈重新整理回應 XML 中收到「報告 =」 TRUE」屬性時，就會開始收集資料。</span><span class="sxs-lookup"><span data-stu-id="46fa1-108">The client starts collecting data when it receives a “REPORTING=”TRUE””attribute in the publishing refresh response XML from the publishing server.</span></span> <span data-ttu-id="46fa1-109">收到此屬性時，用戶端會將任何累計資料傳送至傳送發佈重新整理的發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="46fa1-109">When this attribute is received, the client sends any accumulated data to the publishing server that sent the publishing refresh.</span></span> <span data-ttu-id="46fa1-110">此處理程式的詳細資料如下所示：</span><span class="sxs-lookup"><span data-stu-id="46fa1-110">The details of this process are as follows:</span></span>

-   <span data-ttu-id="46fa1-111">用戶端會傳送 HTTP 取得要求給發佈伺服器以進行發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="46fa1-111">The client sends an HTTP GET request to the publishing server for a publishing refresh.</span></span> <span data-ttu-id="46fa1-112">此訊息的標頭包含「AppV-Op： Refresh」自訂標頭，自訂 HTTP （S）發行伺服器用來識別郵件類型。</span><span class="sxs-lookup"><span data-stu-id="46fa1-112">The header of this message contains an “AppV-Op:Refresh” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

-   <span data-ttu-id="46fa1-113">發佈伺服器接著會傳送包含「報告 = "TRUE"」值的發佈重新整理回應 XML。</span><span class="sxs-lookup"><span data-stu-id="46fa1-113">The publishing server then sends the publishing refresh response XML that contains a “REPORTING=”TRUE”” value.</span></span>

-   <span data-ttu-id="46fa1-114">用戶端接著會將 HTTP POST 要求傳送到發佈伺服器，以及自上次重新整理之後所收集的報告資料。</span><span class="sxs-lookup"><span data-stu-id="46fa1-114">The client then sends an HTTP POST request to the publishing server along with the reporting data that has been gathered since the previous refresh.</span></span> <span data-ttu-id="46fa1-115">此訊息的標頭包含「AppV-Op： Report」自訂標頭，自訂 HTTP （S）發佈伺服器會使用它來識別郵件類型。</span><span class="sxs-lookup"><span data-stu-id="46fa1-115">The header of this message contains an “AppV-Op:Report” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

<span data-ttu-id="46fa1-116">下列架構提供傳送至伺服器之套件和應用程式資料的特定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="46fa1-116">The following schema gives specific details of the package and the application data that is sent to the server.</span></span>

```xml
<?xml version="1.0"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:element name="CLIENT_DATA">
        <xs:complexType>
            <xs:all>
                <xs:element ref="PKG_LIST" minOccurs="1" maxOccurs="1"/>
                <xs:element ref="APP_RECORDS" minOccurs="1" maxOccurs="1"/>
            </xs:all>
            <!-- no regex for Ver because we want to allow tags like "Beta" -->
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Host" type="xs:token" use="required"/>
            <xs:attribute name="CacheSize" type="xs:nonNegativeInteger" use="required"/>
            <xs:attribute name="CacheUsed" type="xs:nonNegativeInteger" use="required"/>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_LIST">
        <xs:complexType>
            <xs:choice>
                <xs:element ref="PKG_DATA" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_DATA">
        <xs:complexType>
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Guid" type="xs:token" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="VerGuid" type="xs:token" use="required"/>
            <xs:attribute name="Source" type="xs:normalizedString" use="required"/>
            <xs:attribute name="PctCached" use="required">
                <xs:simpleType>
                    <xs:restriction base="xs:nonNegativeInteger">
                        <xs:minInclusive value="0"/>
                        <xs:maxInclusive value="100"/>
                    </xs:restriction>
                </xs:simpleType>
            </xs:attribute>
        </xs:complexType>
    </xs:element>

    <xs:element name="APP_RECORDS">
         <xs:complexType>
            <xs:choice>
                <xs:element ref="APP_RECORD" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
   </xs:element>

    <xs:element name="APP_RECORD">
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Server" type="xs:normalizedString" use="required"/>
            <xs:attribute name="User" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Launched" type="xs:dateTime" use="required"/>
            <xs:attribute name="Shutdown" type="xs:dateTime" use="optional"/>
    </xs:element>

</xs:schema>
```

 

 





