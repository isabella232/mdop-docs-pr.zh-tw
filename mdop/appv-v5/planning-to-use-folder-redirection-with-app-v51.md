---
title: 規劃搭配 App-V 使用資料夾重新導向
description: 規劃搭配 App-V 使用資料夾重新導向
author: dansimp
ms.assetid: 6bea9a8f-a915-4d7d-be67-ef1cca1398ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 507aef186579da0efdb3af7b6e1088a5e725ad70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800330"
---
# <span data-ttu-id="48fd2-103">規劃搭配 App-V 使用資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="48fd2-103">Planning to Use Folder Redirection with App-V</span></span>


<span data-ttu-id="48fd2-104">Microsoft Application Virtualization （App-v）5.1 支援使用 [資料夾重新導向]，這項功能可讓使用者和系統管理員將資料夾路徑重新導向至新的位置。</span><span class="sxs-lookup"><span data-stu-id="48fd2-104">Microsoft Application Virtualization (App-V) 5.1 supports the use of folder redirection, a feature that enables users and administrators to redirect the path of a folder to a new location.</span></span>

<span data-ttu-id="48fd2-105">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="48fd2-105">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="48fd2-106">使用資料夾重新導向的需求</span><span class="sxs-lookup"><span data-stu-id="48fd2-106">Requirements for using folder redirection</span></span>](#bkmk-folder-redir-reqs)

-   [<span data-ttu-id="48fd2-107">如何設定要與 App-v 搭配使用的資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="48fd2-107">How to configure folder redirection for use with App-V</span></span>](#bkmk-folder-redir-cfg)

-   [<span data-ttu-id="48fd2-108">資料夾重新導向如何與 App-v 搭配使用</span><span class="sxs-lookup"><span data-stu-id="48fd2-108">How folder redirection works with App-V</span></span>](#bkmk-folder-redir-works)

-   [<span data-ttu-id="48fd2-109">資料夾重新導向概述</span><span class="sxs-lookup"><span data-stu-id="48fd2-109">Overview of folder redirection</span></span>](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a><span data-ttu-id="48fd2-110">使用資料夾重新導向的需求與不受支援的案例</span><span class="sxs-lookup"><span data-stu-id="48fd2-110">Requirements and unsupported scenarios for using folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="48fd2-111">需求</span><span class="sxs-lookup"><span data-stu-id="48fd2-111">Requirements</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-112">若要使用% AppData% 資料夾重新導向，您必須：</span><span class="sxs-lookup"><span data-stu-id="48fd2-112">To use %AppData% folder redirection, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="48fd2-113">擁有 AppData 虛擬檔案系統（VFS）資料夾的 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="48fd2-113">Have an App-V package that has an AppData virtual file system (VFS) folder.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-114">[啟用資料夾重新導向]，並將使用者的資料夾重新導向至共用資料夾（通常是網路資料夾）。</span><span class="sxs-lookup"><span data-stu-id="48fd2-114">Enable folder redirection and redirect users’ folders to a shared folder, typically a network folder.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-115">在下列兩種情況下或兩者皆能漫遊：</span><span class="sxs-lookup"><span data-stu-id="48fd2-115">Roam both or neither of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="48fd2-116">[%Appdata%\Microsoft\AppV\Client\Catalog] 下的檔案</span><span class="sxs-lookup"><span data-stu-id="48fd2-116">Files under %appdata%\Microsoft\AppV\Client\Catalog</span></span></p></li>
<li><p><span data-ttu-id="48fd2-117">[HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages] 下的 [登錄] 設定</span><span class="sxs-lookup"><span data-stu-id="48fd2-117">Registry settings under HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages</span></span></p>
<p><span data-ttu-id="48fd2-118">如需詳細資訊，請參閱 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> 應用程式發佈與用戶端互動 </a> 。</span><span class="sxs-lookup"><span data-stu-id="48fd2-118">For more detail, see <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)">Application Publishing and Client Interaction</a>.</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="48fd2-119">確保登入執行 App-v 5.0 SP2 或更新版本用戶端之電腦的每位使用者都可以使用下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="48fd2-119">Ensure that the following folders are available to each user who logs into the computer that is running the App-V 5.0 SP2 or later client:</span></span></p>
<ul>
<li><p><span data-ttu-id="48fd2-120">% AppData% 已設定為想要的網路位置（有或不 <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> 支援離線檔案 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="48fd2-120">%AppData% is configured to the desired network location (with or without <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)">Offline Files</a> support).</span></span></p></li>
<li><p><span data-ttu-id="48fd2-121">% LocalAppData% 已設定為想要的本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="48fd2-121">%LocalAppData% is configured to the desired local folder.</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="48fd2-122">不支援的案例</span><span class="sxs-lookup"><span data-stu-id="48fd2-122">Unsupported scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="48fd2-123">將% LocalAppData% 設定為網路磁碟機。</span><span class="sxs-lookup"><span data-stu-id="48fd2-123">Configuring %LocalAppData% as a network drive.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-124">針對多位使用者將 [開始] 功能表重新導向到單一資料夾。</span><span class="sxs-lookup"><span data-stu-id="48fd2-124">Redirecting the Start menu to a single folder for multiple users.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-125">如果是漫遊 AppData （% AppData%）已重新導向至無法使用的網路共用，App-v 應用程式將無法啟動，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48fd2-125">If roaming AppData (%AppData%) is redirected to a network share that is not available, App-V applications will fail to launch as follows:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="48fd2-126">App-V 版本</span><span class="sxs-lookup"><span data-stu-id="48fd2-126">App-V version</span></span></th>
<th align="left"><span data-ttu-id="48fd2-127">案例描述</span><span class="sxs-lookup"><span data-stu-id="48fd2-127">Scenario description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="48fd2-128">在 app-v 5.0 的 app-V 5.0 SP2 加上修復程式</span><span class="sxs-lookup"><span data-stu-id="48fd2-128">In App-V 5.0 through App-V 5.0 SP2 plus hotfixes</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-129">無論是否已啟用 [離線檔案]，都不會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="48fd2-129">This failure will occur regardless of whether Offline Files is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="48fd2-130">在 App-V 5.0 SP3 及更新版本中</span><span class="sxs-lookup"><span data-stu-id="48fd2-130">In App-V 5.0 SP3 and later</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-131">如果已為離線檔案啟用無法使用的網路共用，App-v 應用程式將會順利啟動。</span><span class="sxs-lookup"><span data-stu-id="48fd2-131">If the unavailable network share has been enabled for Offline Files, the App-V application will start successfully.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a><span data-ttu-id="48fd2-132">如何設定要與 App-v 搭配使用的資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="48fd2-132">How to configure folder redirection for use with App-V</span></span>


<span data-ttu-id="48fd2-133">[資料夾重新導向] 可套用至不同的資料夾，例如 [桌面]、[我的檔]、[我的圖片] 等等。不過，影響 App-v 應用程式使用的唯一資料夾是使用者的 [漫遊 AppData] 資料夾（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="48fd2-133">Folder redirection can be applied to different folders, such as Desktop, My Documents, My Pictures, etc. However, the only folder that impacts the use of App-V applications is the user’s roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="48fd2-134">您可以將資料夾重新導向套用到任何其他支援的資料夾，而不會影響 App-v。</span><span class="sxs-lookup"><span data-stu-id="48fd2-134">You can apply folder redirection to any other supported folders without impacting App-V.</span></span>

## <a href="" id="bkmk-folder-redir-works"></a><span data-ttu-id="48fd2-135">資料夾重新導向如何與 App-v 搭配使用</span><span class="sxs-lookup"><span data-stu-id="48fd2-135">How folder redirection works with App-V</span></span>


<span data-ttu-id="48fd2-136">下表說明當% AppData% 重新導向至網路時，資料夾重新導向的運作方式，以及您符合本文前面所列的需求。</span><span class="sxs-lookup"><span data-stu-id="48fd2-136">The following table describes how folder redirection works when %AppData% is redirected to a network and when you have met the requirements listed earlier in this article.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="48fd2-137">虛擬環境狀態</span><span class="sxs-lookup"><span data-stu-id="48fd2-137">Virtual environment state</span></span></th>
<th align="left"><span data-ttu-id="48fd2-138">發生的動作</span><span class="sxs-lookup"><span data-stu-id="48fd2-138">Action that occurs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="48fd2-139">虛擬環境啟動時</span><span class="sxs-lookup"><span data-stu-id="48fd2-139">When the virtual environment starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-140">虛擬檔案系統（VFS） AppData 資料夾會對應到本機 AppData 資料夾（% LocalAppData%）而不是使用者的漫遊 AppData 資料夾（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="48fd2-140">The virtual file system (VFS) AppData folder is mapped to the local AppData folder (%LocalAppData%) instead of to the user’s roaming AppData folder (%AppData%).</span></span></p>
<ul>
<li><p><span data-ttu-id="48fd2-141">LocalAppData 包含使用者的 [漫遊 AppData] 資料夾的本機快取，以供使用中的套件。</span><span class="sxs-lookup"><span data-stu-id="48fd2-141">LocalAppData contains a local cache of the user’s roaming AppData folder for the package in use.</span></span> <span data-ttu-id="48fd2-142">本機快取位於：</span><span class="sxs-lookup"><span data-stu-id="48fd2-142">The local cache is located under:</span></span></p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p><span data-ttu-id="48fd2-143">使用者的 [漫遊 AppData] 資料夾中的最新資料會複製到並取代本機快取中目前的資料。</span><span class="sxs-lookup"><span data-stu-id="48fd2-143">The latest data from the user’s roaming AppData folder is copied to and replaces the data currently in the local cache.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-144">虛擬環境執行時，資料會繼續儲存到本機快取。</span><span class="sxs-lookup"><span data-stu-id="48fd2-144">While the virtual environment is running, data continues to be saved to the local cache.</span></span> <span data-ttu-id="48fd2-145">資料只會在% LocalAppData% 中提供，而且不會移動或與% AppData% 進行同步處理，直到最終使用者關閉電腦為止。</span><span class="sxs-lookup"><span data-stu-id="48fd2-145">Data is served only out of %LocalAppData% and is not moved or synchronized with %AppData% until the end user shuts down the computer.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-146">使用使用者內容（而非系統內容）來建立 AppData 資料夾的專案。</span><span class="sxs-lookup"><span data-stu-id="48fd2-146">Entries to the AppData folder are made using the user context, not the system context.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="48fd2-147">注意</span><span class="sxs-lookup"><span data-stu-id="48fd2-147">Note</span></span></strong><br/><p><span data-ttu-id="48fd2-148">App-V 用戶端的資料夾重新導向有時無法將檔案從% AppData% 移到% LocalAppData%。</span><span class="sxs-lookup"><span data-stu-id="48fd2-148">The App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%.</span></span> <span data-ttu-id="48fd2-149">請參閱 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> app-v 5.0 SP2 的版本資訊 </a> 。</span><span class="sxs-lookup"><span data-stu-id="48fd2-149">See <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)">Release Notes for App-V 5.0 SP2</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="48fd2-150">當虛擬環境關閉時</span><span class="sxs-lookup"><span data-stu-id="48fd2-150">When the virtual environment shuts down</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-151">AppData （漫遊）中的本機快取資料會壓縮並複製到% AppData% 中的「實際」漫遊 AppData 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="48fd2-151">The local cached data in AppData (roaming) is zipped up and copied to the “real” roaming AppData folder in %AppData%.</span></span> <span data-ttu-id="48fd2-152">時間戳記（表示最近已知上傳）在下列情況下會同時儲存為登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="48fd2-152">A time stamp, which indicates the last known upload, is simultaneously saved as a registry key under:</span></span></p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p><span data-ttu-id="48fd2-153">為了提供冗余，App-v 會將壓縮資料的三個最新複本保留在% AppData% 下。</span><span class="sxs-lookup"><span data-stu-id="48fd2-153">To provide redundancy, App-V keeps the three most recent copies of the compressed data under %AppData%.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a><span data-ttu-id="48fd2-154">資料夾重新導向概述</span><span class="sxs-lookup"><span data-stu-id="48fd2-154">Overview of folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="48fd2-155">用途</span><span class="sxs-lookup"><span data-stu-id="48fd2-155">Purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-156">讓使用者能夠使用已重新導向至另一個資料夾的檔案，就像檔案仍在本機磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="48fd2-156">Enables end users to work with files, which have been redirected to another folder, as if the files still existed on the local drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="48fd2-157">描述</span><span class="sxs-lookup"><span data-stu-id="48fd2-157">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-158">[資料夾重新導向] 可讓使用者和系統管理員將資料夾的路徑重新導向至網路位置。</span><span class="sxs-lookup"><span data-stu-id="48fd2-158">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="48fd2-159">該資料夾中的檔可供來自網路上任何電腦的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="48fd2-159">The documents in the folder are available to the user from any computer on the network.</span></span></p>
<ul>
<li><p><span data-ttu-id="48fd2-160">[資料夾重新導向] 可讓使用者和系統管理員將資料夾的路徑重新導向至網路位置。</span><span class="sxs-lookup"><span data-stu-id="48fd2-160">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="48fd2-161">該資料夾中的檔可供來自網路上任何電腦的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="48fd2-161">The documents in the folder are available to the user from any computer on the network.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-162">新位置可以是本機電腦上的資料夾，或是共用網路上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="48fd2-162">The new location can be a folder on the local computer or a folder on a shared network.</span></span></p></li>
<li><p><span data-ttu-id="48fd2-163">[資料夾重新導向] 會立即更新檔案，而漫遊資料通常是在使用者登入或登出時進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="48fd2-163">Folder redirection updates the files immediately, whereas roaming data is typically synchronized when the user logs in or logs off.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="48fd2-164">用法範例</span><span class="sxs-lookup"><span data-stu-id="48fd2-164">Usage example</span></span></p></td>
<td align="left"><p><span data-ttu-id="48fd2-165">您可以將 [檔] 資料夾重新導向至網路位置，這通常會儲存在電腦&#39;s 本機硬碟上。</span><span class="sxs-lookup"><span data-stu-id="48fd2-165">You can redirect the Documents folder, which is usually stored on the computer&#39;s local hard disk, to a network location.</span></span> <span data-ttu-id="48fd2-166">使用者可以從網路上的任何電腦存取資料夾中的檔。</span><span class="sxs-lookup"><span data-stu-id="48fd2-166">The user can access the documents in the folder from any computer on the network.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="48fd2-167">更多資源</span><span class="sxs-lookup"><span data-stu-id="48fd2-167">More resources</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)"><span data-ttu-id="48fd2-168">資料夾重新導向概述</span><span class="sxs-lookup"><span data-stu-id="48fd2-168">Folder redirection overview</span></span></a></p></td>
</tr>
</tbody>
</table>
















