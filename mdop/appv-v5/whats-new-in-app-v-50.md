---
title: APP-V 5.0 的新功能
description: APP-V 5.0 的新功能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800289"
---
# <span data-ttu-id="4c9ad-103">APP-V 5.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="4c9ad-103">What's New in App-V 5.0</span></span>


<span data-ttu-id="4c9ad-104">本節適用于已熟悉 App-v 的使用者，並且想要知道 App-V 5.0 中已變更的內容（如果您還不熟悉 App-v），請先閱讀[針對 app-v 5.0 的規劃規劃](planning-for-app-v-50-rc.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="4c9ad-105">標準功能的變更</span><span class="sxs-lookup"><span data-stu-id="4c9ad-105">Changes in Standard Functionality</span></span>


<span data-ttu-id="4c9ad-106">下列各節包含 App-v 5.0 標準功能變更的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-106">The following sections contain information about the changes in standard functionality for App-V 5.0.</span></span>

### <span data-ttu-id="4c9ad-107">支援的作業系統變更</span><span class="sxs-lookup"><span data-stu-id="4c9ad-107">Changes to Supported Operating Systems</span></span>

<span data-ttu-id="4c9ad-108">如需詳細資訊，請參閱[App-V 5.0 支援的](app-v-50-supported-configurations.md)設定。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-108">For more information, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

## <span data-ttu-id="4c9ad-109">排序器的變更</span><span class="sxs-lookup"><span data-stu-id="4c9ad-109">Changes to the sequencer</span></span>


<span data-ttu-id="4c9ad-110">下列各節包含 App-v 5.0 排序器中變更的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-110">The following sections contain information about the changes in the App-V 5.0 sequencer.</span></span>

### <span data-ttu-id="4c9ad-111">排序器的特定變更</span><span class="sxs-lookup"><span data-stu-id="4c9ad-111">Specific change to the sequencer</span></span>

<span data-ttu-id="4c9ad-112">下表顯示有關 App-v 5.0 sequencer 所做的變更的相關資訊</span><span class="sxs-lookup"><span data-stu-id="4c9ad-112">The following table displays information about what has changed with the App-V 5.0 sequencer</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4c9ad-113">Sequencer 功能</span><span class="sxs-lookup"><span data-stu-id="4c9ad-113">Sequencer Feature</span></span></th>
<th align="left"><span data-ttu-id="4c9ad-114">App-v 5.0 Sequencer 功能</span><span class="sxs-lookup"><span data-stu-id="4c9ad-114">App-V 5.0 Sequencer Functionality</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-115">重新開機處理</span><span class="sxs-lookup"><span data-stu-id="4c9ad-115">Reboot processing</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-116">當應用程式提示重新開機時，您應該允許應用程式重新開機執行排序器的電腦。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-116">When an application prompts for a restart, you should allow the application to restart the computer running the sequencer.</span></span> <span data-ttu-id="4c9ad-117">執行排序器的電腦將會重新開機，且 sequencer 將會在 [監視] 模式中繼續。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-117">The computer running the sequencer will restart and the sequencer will resume in monitoring mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-118">指定虛擬應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="4c9ad-118">Specifying the virtual application directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-119">虛擬應用程式目錄是強制性參數。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-119">Virtual Application Directory is a mandatory parameter.</span></span> <span data-ttu-id="4c9ad-120">為了獲得最佳結果，它應該符合應用程式安裝程式的安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-120">For best results, it should match the installation directory of the application installer.</span></span> <span data-ttu-id="4c9ad-121">這會產生更佳的效能和應用程式相容性。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-121">This results in more optimal performance and application compatibility.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-122">編輯快速鍵/FTAs</span><span class="sxs-lookup"><span data-stu-id="4c9ad-122">Editing shortcuts/FTAs</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-123">[快捷方式/FTA] 頁面位於 <strong> [ </strong> 排序嚮導] 完成後的 [高級編輯] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-123">The Shortcuts/FTA page is on the <strong>Advanced</strong> editing page after the sequencing wizard has completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-124">變更歷程記錄索引標籤</span><span class="sxs-lookup"><span data-stu-id="4c9ad-124">Change History Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-125">App-V 5.0 已移除 [變更記錄] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-125">The Change History tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-126">OSD 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4c9ad-126">OSD Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-127">已移除 App-v 5.0 的 [OSD] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-127">The OSD tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-128">虛擬服務索引標籤</span><span class="sxs-lookup"><span data-stu-id="4c9ad-128">Virtual Services Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-129">App-V 5.0 已移除 [虛擬服務] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-129">The virtual services tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-130">[檔案/虛擬檔案系統] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="4c9ad-130">Files/Virtual File System Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-131">這些索引標籤會結合，並可讓您修改套件檔案。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-131">These tabs are combined and allow you to modify package files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-132">部署索引標籤</span><span class="sxs-lookup"><span data-stu-id="4c9ad-132">Deployment Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-133">在套件中，沒有更長的選項可供您設定伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-133">There are no longer options to configure the server URL in the packages.</span></span> <span data-ttu-id="4c9ad-134">您應該使用部署設定或管理伺服器來立即進行設定。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-134">You should configure this now using deployment configuration, or the management server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-135">封裝轉換器工具</span><span class="sxs-lookup"><span data-stu-id="4c9ad-135">Package Converter Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-136">您現在可以使用 PowerShell 來轉換在先前版本中建立的套件。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-136">You can now use PowerShell to convert packages created in previous versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-137">附加元件/中介軟體</span><span class="sxs-lookup"><span data-stu-id="4c9ad-137">Add-on/Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-138">您可以在排序附加元件或中介軟體應用程式時，展開上層套件。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-138">You can expand parent packages when you are sequencing an Add-On or Middleware application.</span></span> <span data-ttu-id="4c9ad-139">附加元件和中介軟體套件必須使用 App-v 5.0 中的連線群組進行連線。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-139">Add-ons and Middleware packages must be connected using connection groups in App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-140">檔案輸出</span><span class="sxs-lookup"><span data-stu-id="4c9ad-140">Files output</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-141">下列檔案是使用 App-v 5.0、Windows Installer （.msi）、appv、部署配置、使用者設定及 Report.XML 建立。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-141">The following files are created with App-V 5.0, Windows Installer (.msi), .appv, deployment configuration, user configuration, and the Report.XML.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-142">壓縮/安全性描述項/MSI 套件</span><span class="sxs-lookup"><span data-stu-id="4c9ad-142">Compression/Security descriptors/MSI packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-143">壓縮和建立 Windows 安裝程式（.msi）檔案在所有套件中都是自動的，而且您不能再覆寫安全描述項。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-143">Compression and the creation of a Windows Installer (.msi) file are automatic for all packages and you can no longer override security descriptors.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-144">[工具]/[選項]</span><span class="sxs-lookup"><span data-stu-id="4c9ad-144">Tools / Options</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-145">[診斷程式] 視窗已移除，以及幾個其他設定。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-145">The Diagnostics window has been removed as well as several other settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-146">安裝磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4c9ad-146">Installation Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-147">安裝應用程式時，已不再需要安裝磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-147">An installation drive is no longer required when you install an application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c9ad-148">OOS 串流</span><span class="sxs-lookup"><span data-stu-id="4c9ad-148">OOS Streaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c9ad-149">如果未執行任何資料流程優化，則在執行 App-v 5.0 用戶端的電腦要求資料包啟動前，套件會以資料流程的方式發生故障。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-149">If no stream optimization is performed, packages are stream faulted when they are requested by computers running the App-V 5.0 client until they can launch.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c9ad-150">問： &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="4c9ad-150">Q:&lt;/p&gt;</span></span></td>
<td align="left"><p><span data-ttu-id="4c9ad-151">App-v 5.0 使用原生檔案系統，不再需要 Q:。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-151">App-V 5.0 uses the native file system and no longer requires a Q:.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4c9ad-152">排序錯誤偵測</span><span class="sxs-lookup"><span data-stu-id="4c9ad-152">Sequencing error detection</span></span>


<span data-ttu-id="4c9ad-153">App-v 5.0 排序器可以在排序期間檢測一般的順序問題。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-153">The App-V 5.0 sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="4c9ad-154">[順序] 嚮導末端的 [**安裝報告**] 頁面會根據問題的嚴重性，顯示分類為**錯誤**、**警告**及**資訊**的診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-154">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="4c9ad-155">若要顯示事件的詳細資訊，請按兩下您要在報表中查看的專案。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-155">To display more detailed information about an event, double-click the item you want to review in the report.</span></span> <span data-ttu-id="4c9ad-156">先後順序問題，以及如何解決問題的相關建議。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-156">The sequencing issues, as well as suggestions about how to resolve the issues are displayed.</span></span> <span data-ttu-id="4c9ad-157">當您完成建立套件時，系統準備報告和安裝報告中的資訊都會匯總。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-157">Information from the system preparation report and the installation report are summarized when you have finished creating a package.</span></span> <span data-ttu-id="4c9ad-158">下列清單顯示報表中可用的問題類型：</span><span class="sxs-lookup"><span data-stu-id="4c9ad-158">The following list displays the types of issues available in the report:</span></span>

-   <span data-ttu-id="4c9ad-159">已排除的檔案。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-159">Excluded files.</span></span>

-   <span data-ttu-id="4c9ad-160">驅動程式資訊。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-160">Driver information.</span></span>

-   <span data-ttu-id="4c9ad-161">COM + 系統差異。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-161">COM+ system differences.</span></span>

-   <span data-ttu-id="4c9ad-162">並列（SxS）衝突。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-162">Side-by-side (SxS) conflicts.</span></span>

-   <span data-ttu-id="4c9ad-163">命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-163">Shell Extensions.</span></span>

-   <span data-ttu-id="4c9ad-164">不支援服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-164">Information about unsupported services.</span></span>

-   <span data-ttu-id="4c9ad-165">封鎖.</span><span class="sxs-lookup"><span data-stu-id="4c9ad-165">DCOM.</span></span>

## <span data-ttu-id="4c9ad-166">連線群組</span><span class="sxs-lookup"><span data-stu-id="4c9ad-166">Connection Groups</span></span>


<span data-ttu-id="4c9ad-167">先前稱為「**動態套件組合**」的 app-v 功能現在稱為 app-v 5.0 中的連線**群組**。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-167">The App-V feature formerly known as **Dynamic Suite Composition** is now referred to as **Connection Groups** in App-V 5.0.</span></span> <span data-ttu-id="4c9ad-168">如需有關使用連接群組的詳細資訊，請參閱[管理連線群組](managing-connection-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-168">For more information about using Connection Groups see [Managing Connection Groups](managing-connection-groups.md).</span></span>

## <span data-ttu-id="4c9ad-169">授權與測定功能</span><span class="sxs-lookup"><span data-stu-id="4c9ad-169">Licensing and Metering Functionality</span></span>


<span data-ttu-id="4c9ad-170">應用程式和授權功能已在 App-v 5.0 中移除。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-170">The application and licensing functionality has been removed in App-V 5.0.</span></span> <span data-ttu-id="4c9ad-171">您環境中實際的授權位置，取決於相關授權條款所授的特定軟體標題授權和使用權利。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-171">The actual license positions in your environment depend on the specific software title license and usage rights granted by the associated license terms.</span></span>

## <span data-ttu-id="4c9ad-172">檔案和應用程式快取</span><span class="sxs-lookup"><span data-stu-id="4c9ad-172">File and Application Cache</span></span>


<span data-ttu-id="4c9ad-173">App-v 5.0 沒有可用的檔案或應用程式快取。</span><span class="sxs-lookup"><span data-stu-id="4c9ad-173">There is no file or application cache available with App-V 5.0.</span></span>






## <span data-ttu-id="4c9ad-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="4c9ad-174">Related topics</span></span>


[<span data-ttu-id="4c9ad-175">關於 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="4c9ad-175">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





