---
title: 如何設定應用程式封裝擷取的用戶端
description: 如何設定應用程式封裝擷取的用戶端
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801573"
---
# <span data-ttu-id="9905c-103">如何設定應用程式封裝擷取的用戶端</span><span class="sxs-lookup"><span data-stu-id="9905c-103">How to Configure the Client for Application Package Retrieval</span></span>


<span data-ttu-id="9905c-104">當用戶端是使用應用程式虛擬化（App-v）管理伺服器（其發佈伺服器）進行設定時，預設會在下次發佈重新整理週期中，用戶端從伺服器針對使用者有權使用的每個套件從已開啟的軟體描述項（OSD）和套件資訊清單檔案中進行檢索。</span><span class="sxs-lookup"><span data-stu-id="9905c-104">When the client is configured with an Application Virtualization (App-V) Management Server as its publishing server, by default at the next publishing refresh cycle, the client retrieves from the server the Open Software Descriptor (OSD) and package manifest files for each package that the user is authorized to use.</span></span> <span data-ttu-id="9905c-105">用戶端會使用在這些檔案中定義的套件來源資訊來決定哪裡可以找到套件內容、圖示及檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="9905c-105">The client uses the package source information that is defined in these files to determine where to find the package content, icons, and file type associations.</span></span>

<span data-ttu-id="9905c-106">如果您想要用戶端從本機 App-v 流式處理伺服器或其他替代來源（例如 Web 服務器或檔案伺服器）取得套件內容（SFT 檔案），而不是從 App-v 管理伺服器，您可以將電腦上的 ApplicationSourceRoot 登錄項值設定為指向其他伺服器上的本機內容共用。</span><span class="sxs-lookup"><span data-stu-id="9905c-106">If you want the client to obtain the package content (SFT file) from a local App-V Streaming Server or other alternate source such as a Web server or file server, instead of from the App-V Management Server, you can configure the ApplicationSourceRoot registry key value on the computer to point to the local content share on the other server.</span></span> <span data-ttu-id="9905c-107">OSD 檔案仍會定義封裝內容的原始來源路徑。</span><span class="sxs-lookup"><span data-stu-id="9905c-107">The OSD file still defines the original source path for the package content.</span></span> <span data-ttu-id="9905c-108">但用戶端會使用 ApplicationSourceRoot 設定的值來代替在 OSD 檔案的內容路徑中指定的伺服器和共用。</span><span class="sxs-lookup"><span data-stu-id="9905c-108">However the client uses the value of the ApplicationSourceRoot setting in place of the server and share that are specified in the content path in the OSD file.</span></span> <span data-ttu-id="9905c-109">這會重新導向用戶端，以從另一個伺服器中取得內容。</span><span class="sxs-lookup"><span data-stu-id="9905c-109">This redirects the client to retrieve the content from the other server.</span></span>

<span data-ttu-id="9905c-110">如果您想要在封裝資訊清單檔案或發佈伺服器傳送的路徑中覆寫這些設定，您也可以設定 OSDSourceRoot 和 IconSourceRoot 登錄機碼的值。</span><span class="sxs-lookup"><span data-stu-id="9905c-110">You can also configure the OSDSourceRoot and IconSourceRoot registry key values if you want to override those settings in the package manifest file or in the paths sent by a publishing server.</span></span> <span data-ttu-id="9905c-111">OSDSourceRoot 會在發佈期間指定應用程式套件的 OSD 檔案檢索源位置。</span><span class="sxs-lookup"><span data-stu-id="9905c-111">The OSDSourceRoot specifies a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="9905c-112">IconSourceRoot 指定發佈期間應用程式套件的圖示檢索來源位置。</span><span class="sxs-lookup"><span data-stu-id="9905c-112">The IconSourceRoot specifies a source location for icon retrieval for an application package during publication.</span></span>

**<span data-ttu-id="9905c-113">注意</span><span class="sxs-lookup"><span data-stu-id="9905c-113">Note</span></span>**  
-   <span data-ttu-id="9905c-114">IconSourceRoot 和 OSDSourceRoot 設定會覆寫封裝資訊清單檔案中的值，因此如果您嘗試使用 Windows 安裝程式（.msi）檔方法來部署套件，則它也會覆寫該 .msi 檔案中包含的套件資訊清單檔案中的值。</span><span class="sxs-lookup"><span data-stu-id="9905c-114">The IconSourceRoot and OSDSourceRoot settings override the values in the package manifest file, so if you try to deploy a package by using the Windows Installer (.msi) file method, it will also override the values in the package manifest file that is contained within that .msi file.</span></span>

-   <span data-ttu-id="9905c-115">在發佈與 HTTP （S）資料流程作業期間，App-v 4.5 SP1 用戶端會使用在使用者電腦上的 Internet Explorer 中設定的 proxy 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="9905c-115">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>



**<span data-ttu-id="9905c-116">設定 ApplicationSourceRoot 登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="9905c-116">To configure the ApplicationSourceRoot registry key value</span></span>**

-   <span data-ttu-id="9905c-117">使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 ApplicationSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="9905c-117">Configure the ApplicationSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="9905c-118">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="9905c-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot</span></span>

    <span data-ttu-id="9905c-119">通用命名慣例（UNC）路徑的正確格式為**\\\\computername\\sharefolder\\\ [folder \] \ [\\]**，其中**資料夾**是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="9905c-119">The correct format for the Universal Naming Convention (UNC) path is **\\\\computername\\sharefolder\\\[folder\]\[\\\]**, where **folder** is optional.</span></span> <span data-ttu-id="9905c-120">**Computername**可以是完整的功能變數名稱（FQDN）或 IP 位址，而**sharefolder**可以是磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="9905c-120">The **computername** can be a Fully Qualified Domain Name (FQDN) or an IP address, and **sharefolder** can be a drive letter.</span></span> <span data-ttu-id="9905c-121">只會取代 OSD 路徑的**\\\\computername\\sharedfolder**或磁片磁碟機盤符部分。</span><span class="sxs-lookup"><span data-stu-id="9905c-121">Only the **\\\\computername\\sharedfolder** or drive letter portion of the OSD path is replaced.</span></span>

    <span data-ttu-id="9905c-122">URL 路徑的正確格式為**protocol：/path\： \ [port \] \ [] \ [/\]**，其中**port**和**path**是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="9905c-122">The correct format for the URL path is **protocol://servername:\[port\]\[/path\]\[/\]**, where **port** and **path** are optional.</span></span> <span data-ttu-id="9905c-123">如果未指定**port** ，則會使用通訊協定的預設埠。</span><span class="sxs-lookup"><span data-stu-id="9905c-123">If **port** is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="9905c-124">只會取代 OSD URL 中的**通訊協定：//server：埠**部分。</span><span class="sxs-lookup"><span data-stu-id="9905c-124">Only the **protocol://server:port** portion of the OSD URL is replaced.</span></span>

    **<span data-ttu-id="9905c-125">重要</span><span class="sxs-lookup"><span data-stu-id="9905c-125">Important</span></span>**  
    <span data-ttu-id="9905c-126">ApplicationSourceRoot 定義中不支援環境變數。</span><span class="sxs-lookup"><span data-stu-id="9905c-126">Environment variables are not supported in the ApplicationSourceRoot definition.</span></span>



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**<span data-ttu-id="9905c-127">若要設定 OSDSourceRoot 值</span><span class="sxs-lookup"><span data-stu-id="9905c-127">To configure the OSDSourceRoot value</span></span>**

-   <span data-ttu-id="9905c-128">使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 OSDSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="9905c-128">Configure the OSDSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="9905c-129">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot</span><span class="sxs-lookup"><span data-stu-id="9905c-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot</span></span>

    <span data-ttu-id="9905c-130">OSDSourceRoot 的可接受格式包括 UNC 路徑和 Url，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="9905c-130">Acceptable formats for the OSDSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="9905c-131">**\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或\*\* &lt; drive &gt; ： \\foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="9905c-131">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="9905c-132">**http://computername/productivity/** 或**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="9905c-132">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

**<span data-ttu-id="9905c-133">若要設定 IconSourceRoot 值</span><span class="sxs-lookup"><span data-stu-id="9905c-133">To configure the IconSourceRoot value</span></span>**

-   <span data-ttu-id="9905c-134">使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 IconSourceRoot：</span><span class="sxs-lookup"><span data-stu-id="9905c-134">Configure the IconSourceRoot in the following registry key value with either a UNC path or a URL:</span></span>

    <span data-ttu-id="9905c-135">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="9905c-135">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot</span></span>

    <span data-ttu-id="9905c-136">IconSourceRoot 的可接受格式包括 UNC 路徑和 Url，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="9905c-136">Acceptable formats for the IconSourceRoot include UNC paths and URLs, as in the following example:</span></span>

    <span data-ttu-id="9905c-137">**\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或\*\* &lt; drive &gt; ： \\foldername\*\*</span><span class="sxs-lookup"><span data-stu-id="9905c-137">**\\\\computername\\sharefolder\\resource** or **\\\\computername\\content** or **&lt;drive&gt;:\\foldername**</span></span>

    <span data-ttu-id="9905c-138">**http://computername/productivity/** 或**https://computername/productivity/**</span><span class="sxs-lookup"><span data-stu-id="9905c-138">**http://computername/productivity/** or **https://computername/productivity/**</span></span>

## <span data-ttu-id="9905c-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="9905c-139">Related topics</span></span>


[<span data-ttu-id="9905c-140">如何使用命令列設定 App-V 用戶端登錄設定</span><span class="sxs-lookup"><span data-stu-id="9905c-140">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









