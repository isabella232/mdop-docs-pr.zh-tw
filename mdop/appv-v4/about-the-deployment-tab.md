---
title: 關於部署索引標籤
description: 關於部署索引標籤
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802426"
---
# <span data-ttu-id="d8c08-103">關於部署索引標籤</span><span class="sxs-lookup"><span data-stu-id="d8c08-103">About the Deployment Tab</span></span>


<span data-ttu-id="d8c08-104">使用應用程式虛擬化 Sequencer 主控台中的 [**部署**] 索引標籤，來變更您要順序的應用程式的資訊。</span><span class="sxs-lookup"><span data-stu-id="d8c08-104">Use the **Deployment** tab in the Application Virtualization Sequencer Console to change the information for an application you are about to sequence.</span></span> <span data-ttu-id="d8c08-105">此索引標籤包含下列元素。</span><span class="sxs-lookup"><span data-stu-id="d8c08-105">This tab contains the following elements.</span></span>

## <span data-ttu-id="d8c08-106">伺服器 URL</span><span class="sxs-lookup"><span data-stu-id="d8c08-106">Server URL</span></span>


<span data-ttu-id="d8c08-107">使用**伺服器 URL**控制項來指定虛擬應用程式伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="d8c08-107">Use the **Server URL** controls to specify the virtual application server configuration settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8c08-108">控制項</span><span class="sxs-lookup"><span data-stu-id="d8c08-108">Control</span></span></th>
<th align="left"><span data-ttu-id="d8c08-109">描述</span><span class="sxs-lookup"><span data-stu-id="d8c08-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8c08-110">通訊協定</span><span class="sxs-lookup"><span data-stu-id="d8c08-110">Protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-111">可讓您選取將已排序之應用程式套件從虛擬應用程式伺服器串流到應用程式虛擬化桌面用戶端的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d8c08-111">Enables you to select the protocol that will stream the sequenced application package from a virtual application server to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="d8c08-112">提供下列通訊協定：</span><span class="sxs-lookup"><span data-stu-id="d8c08-112">The following protocols are available:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="d8c08-113">RTSP </strong> ：預設，它會指定即時資料流通訊協定控制啟用虛擬化的應用程式的交換。</span><span class="sxs-lookup"><span data-stu-id="d8c08-113">RTSP</strong>—The default, it specifies that the Real-Time Streaming Protocol controls the exchange of virtualization-enabled applications.</span></span></p></li>
<li><p><strong><span data-ttu-id="d8c08-114">RTSPS </strong> -指定具有傳輸層安全性的即時資料流通訊協定會控制已排序之應用程式套件的交換。</span><span class="sxs-lookup"><span data-stu-id="d8c08-114">RTSPS</strong>—Specifies that the Real-Time Streaming Protocol with Transport Layer Security controls the exchange of a sequenced application package.</span></span></p></li>
<li><p><strong><span data-ttu-id="d8c08-115">[檔案] </strong> —指定已排序的應用程式將從檔案共用傳送。</span><span class="sxs-lookup"><span data-stu-id="d8c08-115">File</strong>—Specifies that the sequenced application will be streamed from a file share.</span></span></p></li>
<li><p><strong><span data-ttu-id="d8c08-116">HTTPS </strong> ：指定安全的超文字傳輸通訊協定控制套件的交換。</span><span class="sxs-lookup"><span data-stu-id="d8c08-116">HTTPS</strong>—Specifies that Secure Hypertext Transport Protocol controls the exchange of a package.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d8c08-117">主機</span><span class="sxs-lookup"><span data-stu-id="d8c08-117">Hostname</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-118">可讓您在虛擬應用程式伺服器群組的前面，選取虛擬應用程式伺服器或負載平衡器，以將軟體套件傳輸到應用程式虛擬化桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="d8c08-118">Enables you to select the virtual application server or the load balancer in front of a group of virtual application servers that will stream the software package to an Application Virtualization Desktop Client.</span></span> <span data-ttu-id="d8c08-119">您必須完成這個專案，才能建立已排序的應用程式套件，但您可以從預設的% SFT_SOFTGRIDSERVER% 環境變數變更為虛擬應用程式伺服器的實際主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8c08-119">You must complete this item to create a sequenced application package, but you can change from the default %SFT_SOFTGRIDSERVER% environment variable to the actual hostname or IP address of a virtual application server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d8c08-120">注意</span><span class="sxs-lookup"><span data-stu-id="d8c08-120">Note</span></span></strong><br/><p><span data-ttu-id="d8c08-121">如果您選擇不指定靜態主機名稱或 IP 位址，在每個應用程式的虛擬化桌面用戶端上，您必須設定一個名為 SFT_SOFTGRIDSERVER 的環境變數。</span><span class="sxs-lookup"><span data-stu-id="d8c08-121">If you choose not to specify a static hostname or IP address, on each Application Virtualization Desktop Client you must set up an environment variable called SFT_SOFTGRIDSERVER.</span></span> <span data-ttu-id="d8c08-122">其值必須是此用戶端&#39;s 應用程式來源的虛擬應用程式伺服器或負載平衡器的主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8c08-122">Its value must be the hostname or IP address of the virtual application server or load balancer that is this client&#39;s source of applications.</span></span> <span data-ttu-id="d8c08-123">您應該將這個環境變數設為系統變數，而不是使用者變數。</span><span class="sxs-lookup"><span data-stu-id="d8c08-123">You should make this environment variable a system variable rather than a user variable.</span></span> <span data-ttu-id="d8c08-124">您必須先關閉並開啟此變數，才能在這台電腦上執行的任何應用程式虛擬化桌面用戶端會話，以讓繼續進行的會話知道其新的應用程式來源。</span><span class="sxs-lookup"><span data-stu-id="d8c08-124">Any Application Virtualization Desktop Client session that is running on this computer during your assignment of this variable must be closed and then opened so that the resumed session will be aware of its new application source.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8c08-125">連接埠</span><span class="sxs-lookup"><span data-stu-id="d8c08-125">Port</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-126">可讓您指定虛擬應用程式伺服器或負載平衡器在哪個埠上偵聽應用程式虛擬化桌面用戶端的&#39;s 要求。</span><span class="sxs-lookup"><span data-stu-id="d8c08-126">Enables you to specify the port on which the virtual application server or the load balancer will listen for an Application Virtualization Desktop Client&#39;s request for the package.</span></span> <span data-ttu-id="d8c08-127">此資訊是建立套件所必需的，但您可以變更它。</span><span class="sxs-lookup"><span data-stu-id="d8c08-127">This information is required to create a package, but you can change it.</span></span> <span data-ttu-id="d8c08-128">預設埠是554。</span><span class="sxs-lookup"><span data-stu-id="d8c08-128">The default port is 554.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d8c08-129">路徑</span><span class="sxs-lookup"><span data-stu-id="d8c08-129">Path</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-130">可讓您指定儲存軟體套件並將其流入的虛擬應用程式伺服器上的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="d8c08-130">Enables you to specify the relative path on the virtual application server where the software package is stored and from which it will be streamed.</span></span> <span data-ttu-id="d8c08-131">如果 SFT 檔案將儲存在內容子目錄中，則需要此資訊才能建立套件;否則，不需要此資訊。</span><span class="sxs-lookup"><span data-stu-id="d8c08-131">This information is required to create a package if the SFT file will be stored in a subdirectory of CONTENT; otherwise, this information is not required.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d8c08-132">作業系統</span><span class="sxs-lookup"><span data-stu-id="d8c08-132">Operating Systems</span></span>


<span data-ttu-id="d8c08-133">使用**作業系統**控制項來指定應用程式的作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="d8c08-133">Use the **Operating Systems** controls to specify the application's operating system requirements.</span></span> <span data-ttu-id="d8c08-134">如果應用程式虛擬化桌面用戶端無法支援任何選定的作業系統，應用程式將無法啟動。</span><span class="sxs-lookup"><span data-stu-id="d8c08-134">If an Application Virtualization Desktop Client cannot support any of the selected operating systems, the application will not start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8c08-135">控制項</span><span class="sxs-lookup"><span data-stu-id="d8c08-135">Controls</span></span></th>
<th align="left"><span data-ttu-id="d8c08-136">描述</span><span class="sxs-lookup"><span data-stu-id="d8c08-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8c08-137">可用的作業系統</span><span class="sxs-lookup"><span data-stu-id="d8c08-137">Available Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-138">顯示可支援套件中應用程式的作業系統清單。</span><span class="sxs-lookup"><span data-stu-id="d8c08-138">Displays a list of operating systems that can support the applications in the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d8c08-139">選取的作業系統</span><span class="sxs-lookup"><span data-stu-id="d8c08-139">Selected Operating Systems</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-140">顯示支援套件中應用程式的選取作業系統清單。</span><span class="sxs-lookup"><span data-stu-id="d8c08-140">Displays a list of selected operating systems that support the applications in the package.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d8c08-141">輸出選項</span><span class="sxs-lookup"><span data-stu-id="d8c08-141">Output Options</span></span>


<span data-ttu-id="d8c08-142">使用**輸出選項**控制項來指定要安裝之應用程式的輸出選項。</span><span class="sxs-lookup"><span data-stu-id="d8c08-142">Use the **Output Options** controls to specify the output options for the application to be installed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8c08-143">控制項</span><span class="sxs-lookup"><span data-stu-id="d8c08-143">Control</span></span></th>
<th align="left"><span data-ttu-id="d8c08-144">說明</span><span class="sxs-lookup"><span data-stu-id="d8c08-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8c08-145">壓縮演算法</span><span class="sxs-lookup"><span data-stu-id="d8c08-145">Compression Algorithm</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-146">用來選取壓縮 SFT 檔案以在網路上傳輸的方法。</span><span class="sxs-lookup"><span data-stu-id="d8c08-146">Use to select the method for compressing the SFT file for streaming across a network.</span></span> <span data-ttu-id="d8c08-147">選取下列其中一個壓縮方法：</span><span class="sxs-lookup"><span data-stu-id="d8c08-147">Select one of the following compression methods:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="d8c08-148">[已壓縮] </strong> ：指定將 SFT 檔案壓縮為 <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> ZLIB </a> 格式。</span><span class="sxs-lookup"><span data-stu-id="d8c08-148">Compressed</strong>—Specifies that the SFT file be compressed in the <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)">ZLIB</a> format.</span></span></p></li>
<li><p><strong><span data-ttu-id="d8c08-149">未壓縮 </strong> （預設值）; 指定不壓縮 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8c08-149">Not Compressed</strong>—The default; specifies that the SFT file not be compressed.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d8c08-150">強制執行安全性描述項</span><span class="sxs-lookup"><span data-stu-id="d8c08-150">Enforce Security Descriptors</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-151">選取以在將套件部署到用戶端之後，強制執行該應用程式的安全描述項。</span><span class="sxs-lookup"><span data-stu-id="d8c08-151">Select to enforce security descriptors of the applications in the package after it is deployed to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8c08-152">產生 Microsoft Windows Installer （MSI）套件</span><span class="sxs-lookup"><span data-stu-id="d8c08-152">Generate Microsoft Windows Installer (MSI) Package</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8c08-153">選取以使用 Windows 安裝程式來安裝或部署已排序的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="d8c08-153">Select to install or deploy a sequenced application package with the Windows Installer.</span></span> <span data-ttu-id="d8c08-154">如果您使用 sequencer 進行任何變更，則 Windows Installer 檔案不會包含這些變更。</span><span class="sxs-lookup"><span data-stu-id="d8c08-154">If you have made any changes using the sequencer the changes will not be included with the Windows Installer file.</span></span> <span data-ttu-id="d8c08-155">Windows Installer 檔案將永遠會使用儲存在硬碟上的 sft 檔案來建立。</span><span class="sxs-lookup"><span data-stu-id="d8c08-155">The Windows Installer file will always be created using the .sft file saved on the hard disk.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d8c08-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="d8c08-156">Related topics</span></span>


[<span data-ttu-id="d8c08-157">如何變更部署內容</span><span class="sxs-lookup"><span data-stu-id="d8c08-157">How to Change Deployment Properties</span></span>](how-to-change-deployment-properties.md)

[<span data-ttu-id="d8c08-158">排序器主控台</span><span class="sxs-lookup"><span data-stu-id="d8c08-158">Sequencer Console</span></span>](sequencer-console.md)









