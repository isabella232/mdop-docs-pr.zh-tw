---
title: ADD SERVER
description: ADD SERVER
author: dansimp
ms.assetid: 4be2ac2e-a410-4711-9f84-f305393c8fa7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e15a5943b40e14b2f9031bf8b3ddffa693e32dea
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802397"
---
# <span data-ttu-id="c85c6-103">ADD SERVER</span><span class="sxs-lookup"><span data-stu-id="c85c6-103">ADD SERVER</span></span>


<span data-ttu-id="c85c6-104">新增發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="c85c6-104">Adds a publishing server.</span></span>

`SFTMIME ADD SERVER:server-name /HOST hostname /TYPE {HTTP|RTSP}                 /PATH path [/PORT port] [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c85c6-105">參數</span><span class="sxs-lookup"><span data-stu-id="c85c6-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c85c6-106">描述</span><span class="sxs-lookup"><span data-stu-id="c85c6-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-107">伺服器： &lt; 伺服器-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="c85c6-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-108">發佈伺服器的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="c85c6-108">The display name for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c85c6-109">/HOST &lt; 主機名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="c85c6-109">/HOST &lt;hostname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-110">發佈伺服器的主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c85c6-110">The host name or IP address for the publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-111">/TYPE {HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="c85c6-111">/TYPE {HTTP|RTSP}</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-112">指出發佈伺服器是 Web 服務器（ &quot; HTTP &quot; ）或應用程式虛擬化伺服器（ &quot; RTSP &quot; ）。</span><span class="sxs-lookup"><span data-stu-id="c85c6-112">Indicates whether the publishing server is a Web server (&quot;HTTP&quot;) or an Application Virtualization Server (&quot;RTSP&quot;).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c85c6-113">/PORT &lt; 埠&gt;</span><span class="sxs-lookup"><span data-stu-id="c85c6-113">/PORT &lt;port&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-114">發佈伺服器所偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="c85c6-114">The port on which the publishing server listens.</span></span> <span data-ttu-id="c85c6-115">預設值為80（適用于一般 HTTP 伺服器）、使用增強安全性的443（適用于一般應用程式虛擬化伺服器的554），以及使用增強安全性的伺服器322。</span><span class="sxs-lookup"><span data-stu-id="c85c6-115">Defaults to 80 for normal HTTP servers, 443 for HTTP servers using enhanced security, 554 for normal Application Virtualization Servers, and 322 for servers using enhanced security.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-116">/PATH &lt; 路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="c85c6-116">/PATH &lt;path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-117">發佈要求中使用之 URL 的路徑部分。</span><span class="sxs-lookup"><span data-stu-id="c85c6-117">The path portion of the URL used in a publishing request.</span></span> <span data-ttu-id="c85c6-118">如果 TYPE 參數設定為 RTSP，則路徑是選擇性的且預設為 &quot; / &quot; 。</span><span class="sxs-lookup"><span data-stu-id="c85c6-118">If the TYPE parameter is set to RTSP, the path is optional and defaults to &quot;/&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c85c6-119">/REFRESH</span><span class="sxs-lookup"><span data-stu-id="c85c6-119">/REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-120">如果設定為 [開啟]，則在使用者登入時，發佈資訊將會重新整理。</span><span class="sxs-lookup"><span data-stu-id="c85c6-120">If set to ON, publishing information will be refreshed when the user logs in.</span></span> <span data-ttu-id="c85c6-121">預設為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="c85c6-121">Defaults to ON.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-122">/SECURE</span><span class="sxs-lookup"><span data-stu-id="c85c6-122">/SECURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-123">如果存在，則表示應該建立與 [發佈伺服器] 的 [增強安全性] 的連線。</span><span class="sxs-lookup"><span data-stu-id="c85c6-123">If present, indicates that a connection with enhanced security should be established to the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c85c6-124">/LOG</span><span class="sxs-lookup"><span data-stu-id="c85c6-124">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-125">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c85c6-125">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-126">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="c85c6-126">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-127">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="c85c6-127">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c85c6-128">/GUI</span><span class="sxs-lookup"><span data-stu-id="c85c6-128">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-129">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="c85c6-129">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c85c6-130">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="c85c6-130">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c85c6-131">/LOGU</span><span class="sxs-lookup"><span data-stu-id="c85c6-131">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="c85c6-132">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c85c6-132">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c85c6-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="c85c6-133">Related topics</span></span>


[<span data-ttu-id="c85c6-134">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="c85c6-134">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





