---
title: 規劃從舊版進行移轉
description: 規劃從舊版進行移轉
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800917"
---
# <span data-ttu-id="248d3-103">規劃從舊版進行移轉</span><span class="sxs-lookup"><span data-stu-id="248d3-103">Planning for Migration from Previous Versions</span></span>


<span data-ttu-id="248d3-104">在嘗試升級至 Microsoft Application Virtualization 4.5 或更新版本之前，必須先將4.1 之前的任何版本升級至4.1 版本。</span><span class="sxs-lookup"><span data-stu-id="248d3-104">Before attempting to upgrade to Microsoft Application Virtualization4.5 or later versions, any version prior to4.1 must be upgraded to version4.1.</span></span> <span data-ttu-id="248d3-105">您應該先規劃升級用戶端，然後再升級伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="248d3-105">You should plan to upgrade your clients first, and then upgrade the server components.</span></span> <span data-ttu-id="248d3-106">已升級到4.5 的用戶端將會繼續與尚未升級的 Application Virtualization 伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="248d3-106">Clients that have been upgraded to4.5 will continue to work with Application Virtualization servers that have not yet been upgraded.</span></span> <span data-ttu-id="248d3-107">已升級為4.5 的伺服器不支援舊版用戶端。</span><span class="sxs-lookup"><span data-stu-id="248d3-107">Earlier versions of the client are not supported on servers that have been upgraded to4.5.</span></span> <span data-ttu-id="248d3-108">如需升級系統元件的詳細資訊，請參閱[應用程式虛擬化部署和升級考慮](application-virtualization-deployment-and-upgrade-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="248d3-108">For more information about upgrading the system components, see [Application Virtualization Deployment and Upgrade Considerations](application-virtualization-deployment-and-upgrade-considerations.md).</span></span>

<span data-ttu-id="248d3-109">若要協助確保順利進行遷移，請依照下列順序升級應用程式虛擬化系統元件：</span><span class="sxs-lookup"><span data-stu-id="248d3-109">To help ensure a successful migration, the Application Virtualization system components should be upgraded in the following order:</span></span>

1.  **<span data-ttu-id="248d3-110">Microsoft Application Virtualization 用戶端。</span><span class="sxs-lookup"><span data-stu-id="248d3-110">Microsoft Application Virtualization Clients.</span></span>** <span data-ttu-id="248d3-111">如需逐步升級指示，請參閱[如何升級應用程式虛擬化用戶端](how-to-upgrade-the-application-virtualization-client.md)。</span><span class="sxs-lookup"><span data-stu-id="248d3-111">For step-by-step upgrade instructions, see [How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md).</span></span>

2.  **<span data-ttu-id="248d3-112">Microsoft Application Virtualization 伺服器和資料庫。</span><span class="sxs-lookup"><span data-stu-id="248d3-112">Microsoft Application Virtualization Servers and Database.</span></span>** <span data-ttu-id="248d3-113">如需逐步升級指示，請參閱[如何升級伺服器與系統元件](how-to-upgrade-the-servers-and-system-components.md)。</span><span class="sxs-lookup"><span data-stu-id="248d3-113">For step-by-step upgrade instructions, see [How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md).</span></span>

    <span data-ttu-id="248d3-114">**記事** 如果您有多個伺服器共用應用程式虛擬化資料庫的存取權，所有這些伺服器都必須在資料庫升級時離線。</span><span class="sxs-lookup"><span data-stu-id="248d3-114">**Note** If you have more than one server sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="248d3-115">您應該遵循資料庫升級的一般業務做法，但強烈建議您在測試伺服器上先使用資料庫的備份複本來測試資料庫升級。</span><span class="sxs-lookup"><span data-stu-id="248d3-115">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="248d3-116">接著，您應該選取其中一個伺服器進行第一次升級，這會升級資料庫架構。</span><span class="sxs-lookup"><span data-stu-id="248d3-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="248d3-117">成功升級生產資料庫之後，您就可以升級其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="248d3-117">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

     

3.  **<span data-ttu-id="248d3-118">Microsoft Application Virtualization 管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="248d3-118">Microsoft Application Virtualization Management Web Service.</span></span>** <span data-ttu-id="248d3-119">此步驟僅適用于管理 Web 服務位於個別伺服器上，這會要求您在該個別伺服器上執行伺服器安裝程式，以升級 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="248d3-119">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Web service.</span></span> <span data-ttu-id="248d3-120">否則，先前的伺服器升級步驟會自動升級管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="248d3-120">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span>

4.  **<span data-ttu-id="248d3-121">Microsoft Application Virtualization 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="248d3-121">Microsoft Application Virtualization Management Console.</span></span>** <span data-ttu-id="248d3-122">此步驟僅適用于管理主控台位於不同的電腦上，這會要求您在該個別電腦上執行伺服器安裝程式，以升級主機。</span><span class="sxs-lookup"><span data-stu-id="248d3-122">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="248d3-123">否則，先前的伺服器升級步驟將會升級管理主控台。</span><span class="sxs-lookup"><span data-stu-id="248d3-123">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span>

5.  **<span data-ttu-id="248d3-124">Microsoft Application Virtualization 排序器。</span><span class="sxs-lookup"><span data-stu-id="248d3-124">Microsoft Application Virtualization Sequencer.</span></span>** <span data-ttu-id="248d3-125">如需逐步指示，請參閱[如何安裝應用程式虛擬化排序](how-to-install-the-application-virtualization-sequencer.md)器。</span><span class="sxs-lookup"><span data-stu-id="248d3-125">For step-by-step instructions, see [How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md).</span></span> <span data-ttu-id="248d3-126">在版本4.2 中排序的任何虛擬應用程式套件，都不需要重新排序，就能與版本4.5 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="248d3-126">Any virtual application packages sequenced in version4.2 will not have to be re-sequenced for use with version4.5.</span></span> <span data-ttu-id="248d3-127">不過，如果您想要套用預設的存取控制清單（Acl）或產生 Windows 安裝程式檔案，您應該考慮將虛擬套件升級為 Microsoft Application Virtualization 4.5 格式。</span><span class="sxs-lookup"><span data-stu-id="248d3-127">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization4.5 format if you would like to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="248d3-128">這是一個簡單的程式，只需要使用4.5 排序器開啟並儲存現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="248d3-128">This is a simple process and requires only that the existing virtual application package be opened and saved with the4.5 Sequencer.</span></span> <span data-ttu-id="248d3-129">您可以使用應用程式虛擬化排序器命令列介面自動化這種做法。</span><span class="sxs-lookup"><span data-stu-id="248d3-129">This can be automated by using the Application Virtualization Sequencer command-line interface.</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="248d3-130">App-v 4.6 用戶端套件支援</span><span class="sxs-lookup"><span data-stu-id="248d3-130">App-V4.6 Client Package Support</span></span>


<span data-ttu-id="248d3-131">您可以將在早期版本的 App-v 中建立的套件部署到 App-v 4.6 用戶端。</span><span class="sxs-lookup"><span data-stu-id="248d3-131">You can deploy packages created in previous versions of App-V to App-V4.6 Clients.</span></span> <span data-ttu-id="248d3-132">不過，您必須修改相關的 **.osd**檔案，讓它包含適當的作業系統和晶片架構資訊。</span><span class="sxs-lookup"><span data-stu-id="248d3-132">However, you must modify the associated **.osd** file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="248d3-133">使用下列值。</span><span class="sxs-lookup"><span data-stu-id="248d3-133">Use the following values.</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="248d3-134">OS 值</span><span class="sxs-lookup"><span data-stu-id="248d3-134">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-135">&lt;OS 值 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-135">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-136">&lt;OS 值 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-136">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-137">&lt;OS 值 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-137">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-138">&lt;OS 值 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-138">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-139">&lt;OS 值 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-139">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-140">&lt;OS 值 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-140">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-141">&lt;OS 值 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-141">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-142">&lt;OS 值 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-142">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-143">&lt;OS 值 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-143">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-144">&lt;OS 值 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-144">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-145">&lt;OS 值 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="248d3-145">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="248d3-146">若要執行新建立的32位套件，您必須在執行32位作業系統的電腦上，依已安裝 App-v 4.6 Sequencer 的方式來排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="248d3-146">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V4.6 Sequencer installed.</span></span> <span data-ttu-id="248d3-147">當您將應用程式排序之後，請在 Sequencer 主控台中，選取 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。</span><span class="sxs-lookup"><span data-stu-id="248d3-147">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="248d3-148">**重要** 在執行64位作業系統的電腦上，必須將已排序的應用程式部署到執行64位作業系統的電腦上。</span><span class="sxs-lookup"><span data-stu-id="248d3-148">**Important** Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="248d3-149">使用 App-v 4.6 Sequencer 來建立的新32位套件將無法在執行 App-v 4.5 用戶端的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="248d3-149">New 32-bit packages created by using the App-V4.6 Sequencer will not run on computers running the App-V 4.5 Client.</span></span>

 

<span data-ttu-id="248d3-150">若要在 App-V 4.6 用戶端上執行新的64位套件，您必須在執行 App-v 4.6 Sequencer 的電腦上，並在執行64位作業系統的電腦上對應用程式進行排序。</span><span class="sxs-lookup"><span data-stu-id="248d3-150">To run new 64-bit packages on the App-V4.6 Client, you must sequence the application on a computer running the App-V4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="248d3-151">當您將應用程式排序之後，請在 Sequencer 主控台中，選取 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。</span><span class="sxs-lookup"><span data-stu-id="248d3-151">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="248d3-152">下表列出哪些用戶端版本會使用各種不同版本的排序器來執行建立的套件。</span><span class="sxs-lookup"><span data-stu-id="248d3-152">The following table lists which client versions will run packages created by using the various versions of the Sequencer.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="248d3-153">使用 App-v 4.2 Sequencer 排序</span><span class="sxs-lookup"><span data-stu-id="248d3-153">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="248d3-154">使用 App-v 4.5 Sequencer 排序</span><span class="sxs-lookup"><span data-stu-id="248d3-154">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="248d3-155">使用32位 App-v-V 4.6 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="248d3-155">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="248d3-156">使用64位 App-v-V 4.6 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="248d3-156">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="248d3-157">使用32位 4.6 App-v Sequencer 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="248d3-157">Sequenced by using the 32-bit App-V 4.6 SP1 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="248d3-158">使用64位 4.6 App-v Sequencer 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="248d3-158">Sequenced by using the 64-bit App-V 4.6 SP1 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-159">4.2 用戶端</span><span class="sxs-lookup"><span data-stu-id="248d3-159">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-160">是</span><span class="sxs-lookup"><span data-stu-id="248d3-160">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-161">否</span><span class="sxs-lookup"><span data-stu-id="248d3-161">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-162">否</span><span class="sxs-lookup"><span data-stu-id="248d3-162">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-163">否</span><span class="sxs-lookup"><span data-stu-id="248d3-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-164">否</span><span class="sxs-lookup"><span data-stu-id="248d3-164">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-165">否</span><span class="sxs-lookup"><span data-stu-id="248d3-165">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-166">4.5 用戶端¹</span><span class="sxs-lookup"><span data-stu-id="248d3-166">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-167">是</span><span class="sxs-lookup"><span data-stu-id="248d3-167">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-168">是</span><span class="sxs-lookup"><span data-stu-id="248d3-168">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-169">否</span><span class="sxs-lookup"><span data-stu-id="248d3-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-170">否</span><span class="sxs-lookup"><span data-stu-id="248d3-170">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-171">否</span><span class="sxs-lookup"><span data-stu-id="248d3-171">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-172">否</span><span class="sxs-lookup"><span data-stu-id="248d3-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-173">4.6 用戶端（32位）</span><span class="sxs-lookup"><span data-stu-id="248d3-173">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-174">是</span><span class="sxs-lookup"><span data-stu-id="248d3-174">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-175">是</span><span class="sxs-lookup"><span data-stu-id="248d3-175">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-176">是</span><span class="sxs-lookup"><span data-stu-id="248d3-176">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-177">不可以</span><span class="sxs-lookup"><span data-stu-id="248d3-177">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-178">是</span><span class="sxs-lookup"><span data-stu-id="248d3-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-179">不可以</span><span class="sxs-lookup"><span data-stu-id="248d3-179">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-180">4.6 用戶端（64位）</span><span class="sxs-lookup"><span data-stu-id="248d3-180">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-181">是</span><span class="sxs-lookup"><span data-stu-id="248d3-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-182">是</span><span class="sxs-lookup"><span data-stu-id="248d3-182">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-183">是</span><span class="sxs-lookup"><span data-stu-id="248d3-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-184">是</span><span class="sxs-lookup"><span data-stu-id="248d3-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-185">是</span><span class="sxs-lookup"><span data-stu-id="248d3-185">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-186">是</span><span class="sxs-lookup"><span data-stu-id="248d3-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="248d3-187">4.6 SP1 用戶端</span><span class="sxs-lookup"><span data-stu-id="248d3-187">4.6 SP1 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-188">是</span><span class="sxs-lookup"><span data-stu-id="248d3-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-189">是</span><span class="sxs-lookup"><span data-stu-id="248d3-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-190">是</span><span class="sxs-lookup"><span data-stu-id="248d3-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-191">不可以</span><span class="sxs-lookup"><span data-stu-id="248d3-191">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-192">是</span><span class="sxs-lookup"><span data-stu-id="248d3-192">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-193">不可以</span><span class="sxs-lookup"><span data-stu-id="248d3-193">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="248d3-194">4.6 SP1 用戶端（64位）</span><span class="sxs-lookup"><span data-stu-id="248d3-194">4.6 SP1 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-195">是</span><span class="sxs-lookup"><span data-stu-id="248d3-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-196">是</span><span class="sxs-lookup"><span data-stu-id="248d3-196">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-197">是</span><span class="sxs-lookup"><span data-stu-id="248d3-197">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-198">是</span><span class="sxs-lookup"><span data-stu-id="248d3-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-199">是</span><span class="sxs-lookup"><span data-stu-id="248d3-199">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="248d3-200">是</span><span class="sxs-lookup"><span data-stu-id="248d3-200">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="248d3-201">¹適用于 App-V 4.5 用戶端的所有版本，包括 App-v 4.5、App-v 4.5 CU1 和 App-v 4.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="248d3-201">¹Applies to all versions of the App-V4.5 Client, including App-V4.5, App-V4.5CU1 and App-V4.5 SP1.</span></span>

## <span data-ttu-id="248d3-202">其他遷移考慮</span><span class="sxs-lookup"><span data-stu-id="248d3-202">Additional Migration Considerations</span></span>


<span data-ttu-id="248d3-203">App-v 4.5 排序器的其中一個功能是，可以建立 Windows 安裝程式檔案（.msi）作為虛擬應用程式套件與電子軟體發佈（ESD）系統（例如 Microsoft 端點設定管理員）的控制點。</span><span class="sxs-lookup"><span data-stu-id="248d3-203">One of the features of the App-V4.5 Sequencer is the ability to create Windows Installer files (.msi) as control points for virtual application package interoperability with electronic software distribution (ESD) systems such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="248d3-204">以 .msi 工具所建立的舊版 Windows 安裝程式檔案，這些檔案是在隨後升級到4.5 的 App-v 或4.2 用戶端上安裝，不過這些檔案無法在4.5 用戶端上安裝。</span><span class="sxs-lookup"><span data-stu-id="248d3-204">Previous Windows Installer files created with the .msi tool for Application Virtualization that were installed on a App-V4.1 or4.2 Client that is subsequently upgraded to4.5 continue to work, although they cannot be installed on the4.5 Client.</span></span> <span data-ttu-id="248d3-205">不過，除非在4.5 排序器中升級，否則無法移除或升級它們。</span><span class="sxs-lookup"><span data-stu-id="248d3-205">However, they cannot be removed or upgraded unless they are upgraded in the4.5 Sequencer.</span></span> <span data-ttu-id="248d3-206">原始的4.5 虛擬應用程式套件必須在4.5 排序器中開啟，然後另存為 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="248d3-206">The original pre-4.5 virtual application package would need to be opened in the4.5 Sequencer and then saved as a Windows Installer File.</span></span>

<span data-ttu-id="248d3-207">**記事** 如果 App-v 4.2 用戶端已升級到4.5，就可以使用腳本做為因應措施，在4.5 用戶端上保留4.2 套件，並允許管理它們。</span><span class="sxs-lookup"><span data-stu-id="248d3-207">**Note** If the App-V4.2 Client has already been upgraded to4.5, it is possible to use script as a workaround to preserve the4.2 packages on4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="248d3-208">此腳本必須將兩個檔案（msvcp71.dll 和 msvcr71.dll）複製到 App V 安裝資料夾，並在登錄機碼 \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\] 下設定下列登錄機碼值：</span><span class="sxs-lookup"><span data-stu-id="248d3-208">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

<span data-ttu-id="248d3-209">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="248d3-209">"ClientVersion"="4.2.1.20"</span></span>

<span data-ttu-id="248d3-210">"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" （全域可寫位置）</span><span class="sxs-lookup"><span data-stu-id="248d3-210">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>

 

<span data-ttu-id="248d3-211">當您嘗試在 App-v 4.6 用戶端上執行應用程式時，由 App-v 4.5 Sequencer 產生的 Windows Installer 檔案會顯示錯誤訊息「此套件需要 Microsoft Application Virtualization 用戶端4.5 或更新版本」。</span><span class="sxs-lookup"><span data-stu-id="248d3-211">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when you try to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="248d3-212">使用 App-v 4.5 SP1 排序器或 App-v 4.6 排序器開啟舊的套件，並為套件產生新的 .msi。</span><span class="sxs-lookup"><span data-stu-id="248d3-212">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi for the package.</span></span>

<span data-ttu-id="248d3-213">已建立並儲存的任何4.2 報告將在伺服器升級為4.5 時覆蓋。</span><span class="sxs-lookup"><span data-stu-id="248d3-213">Any4.2 reports that were created and saved will be overwritten when the server is upgraded to4.5.</span></span> <span data-ttu-id="248d3-214">如果您需要保留這些報告，您必須儲存位於伺服器的 SoftGrid 管理主控台資料夾中的 SftMMC 檔案備份複本，然後使用該複本來取代升級期間安裝的新 SftMMC。</span><span class="sxs-lookup"><span data-stu-id="248d3-214">If you need to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

<span data-ttu-id="248d3-215">如需從舊版升級的其他資訊，請參閱[升級至 Microsoft Application Virtualization 4.5 常見問題](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="248d3-215">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <span data-ttu-id="248d3-216">相關主題</span><span class="sxs-lookup"><span data-stu-id="248d3-216">Related topics</span></span>


[<span data-ttu-id="248d3-217">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="248d3-217">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





