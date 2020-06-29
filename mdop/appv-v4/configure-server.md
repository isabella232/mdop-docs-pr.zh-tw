---
title: CONFIGURE SERVER
description: CONFIGURE SERVER
author: dansimp
ms.assetid: c916eddd-74f2-46e4-953d-120b23284e37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7757f281ec57645d20367056ba0013ef476a91a1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809075"
---
# <span data-ttu-id="6728f-103">CONFIGURE SERVER</span><span class="sxs-lookup"><span data-stu-id="6728f-103">CONFIGURE SERVER</span></span>


<span data-ttu-id="6728f-104">讓使用者能夠變更伺服器的設定;未指定的任何設定將不會被修改。</span><span class="sxs-lookup"><span data-stu-id="6728f-104">Enables a user to change the setup of a server; any settings not specified will not be modified.</span></span>

`SFTMIME CONFIGURE SERVER:server-name [/NAME display-name] [/HOST hostname]                 [/PORT port] [/PATH path] [/TYPE {HTTP|RTSP}]                 [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6728f-105">參數</span><span class="sxs-lookup"><span data-stu-id="6728f-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="6728f-106">描述</span><span class="sxs-lookup"><span data-stu-id="6728f-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-107">伺服器： &lt; 伺服器-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="6728f-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-108">發佈伺服器的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6728f-108">The display name for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6728f-109">/NAME &lt; 顯示名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="6728f-109">/NAME &lt;display-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-110">伺服器的新顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6728f-110">New display name for the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-111">/HOST &lt; 主機名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="6728f-111">/HOST &lt;hostname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-112">發佈伺服器的主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6728f-112">The host name or IP address for the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6728f-113">/PORT &lt; 埠&gt;</span><span class="sxs-lookup"><span data-stu-id="6728f-113">/PORT &lt;port&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-114">發佈伺服器所偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="6728f-114">The port on which the publishing server listens.</span></span> <span data-ttu-id="6728f-115">預設值為80（適用于一般 HTTP 伺服器）、使用增強安全性的443（適用于一般應用程式虛擬化伺服器的554），以及使用增強安全性的伺服器322。</span><span class="sxs-lookup"><span data-stu-id="6728f-115">Defaults to 80 for normal HTTP servers, 443 for HTTP servers using enhanced security, 554 for normal Application Virtualization Servers, and 322 for servers using enhanced security.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-116">/PATH &lt; 路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="6728f-116">/PATH &lt;path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-117">發佈要求中使用之 URL 的路徑部分。</span><span class="sxs-lookup"><span data-stu-id="6728f-117">The path portion of the URL used in a publishing request.</span></span> <span data-ttu-id="6728f-118">如果 TYPE 參數設定為 RTSP，則路徑是選擇性的且預設為 &quot; / &quot; 。</span><span class="sxs-lookup"><span data-stu-id="6728f-118">If the TYPE parameter is set to RTSP, the path is optional and defaults to &quot;/&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6728f-119">/TYPE</span><span class="sxs-lookup"><span data-stu-id="6728f-119">/TYPE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-120">指出發佈伺服器是 Web 服務器（ &quot; HTTP &quot; ）或應用程式虛擬化伺服器（ &quot; RTSP &quot; ）。</span><span class="sxs-lookup"><span data-stu-id="6728f-120">Indicates whether the publishing server is a Web server (&quot;HTTP&quot;) or an Application Virtualization Server (&quot;RTSP&quot;).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-121">/REFRESH</span><span class="sxs-lookup"><span data-stu-id="6728f-121">/REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-122">如果設定為 [開啟]，則在使用者登入時，發佈資訊將會重新整理。</span><span class="sxs-lookup"><span data-stu-id="6728f-122">If set to ON, publishing information will be refreshed when the user logs in.</span></span> <span data-ttu-id="6728f-123">預設為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="6728f-123">Defaults to ON.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6728f-124">/SECURE</span><span class="sxs-lookup"><span data-stu-id="6728f-124">/SECURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-125">如果存在，則表示應該建立與 [發佈伺服器] 的 [增強安全性] 的連線。</span><span class="sxs-lookup"><span data-stu-id="6728f-125">If present, indicates that a connection with enhanced security should be established to the publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-126">/LOG</span><span class="sxs-lookup"><span data-stu-id="6728f-126">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-127">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="6728f-127">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6728f-128">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="6728f-128">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-129">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="6728f-129">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-130">/GUI</span><span class="sxs-lookup"><span data-stu-id="6728f-130">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-131">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="6728f-131">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6728f-132">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="6728f-132">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6728f-133">/LOGU</span><span class="sxs-lookup"><span data-stu-id="6728f-133">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="6728f-134">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="6728f-134">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6728f-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="6728f-135">Related topics</span></span>


[<span data-ttu-id="6728f-136">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="6728f-136">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





