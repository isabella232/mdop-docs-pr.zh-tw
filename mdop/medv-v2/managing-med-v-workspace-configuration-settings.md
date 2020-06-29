---
title: 管理 MED-V 工作區組態設定
description: 管理 MED-V 工作區組態設定
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811588"
---
# <span data-ttu-id="768fb-103">管理 MED-V 工作區組態設定</span><span class="sxs-lookup"><span data-stu-id="768fb-103">Managing MED-V Workspace Configuration Settings</span></span>


<span data-ttu-id="768fb-104">Microsoft 企業版桌面虛擬化（MED-V）2.0 儲存其在註冊表中的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 stores its configuration settings in the registry.</span></span> <span data-ttu-id="768fb-105">我們在這裡提供的有關登錄的資訊可協助您更好地管理 MED-V 服務。</span><span class="sxs-lookup"><span data-stu-id="768fb-105">The information we include here about the registry may help you better manage your MED-V services.</span></span>

<span data-ttu-id="768fb-106">在尋找結果設定值時，MED-V 會使用下列搜尋路徑：</span><span class="sxs-lookup"><span data-stu-id="768fb-106">MED-V uses the following search path when looking for the resultant settings values:</span></span>

<span data-ttu-id="768fb-107">MED-V 會先在電腦原則中尋找。</span><span class="sxs-lookup"><span data-stu-id="768fb-107">MED-V first looks in the machine policy.</span></span>

<span data-ttu-id="768fb-108">如果找不到這個值，MED-V 就會在使用者原則中尋找。</span><span class="sxs-lookup"><span data-stu-id="768fb-108">If the value is not found, MED-V looks in the user policy.</span></span>

<span data-ttu-id="768fb-109">如果找不到這個值，MED-V 會在 HKEY \ _LOCAL \ _MACHINE \\System hive）中尋找。</span><span class="sxs-lookup"><span data-stu-id="768fb-109">If the value is not found, MED-V looks in the HKEY\_LOCAL\_MACHINE\\System hive.</span></span>

<span data-ttu-id="768fb-110">如果找不到這個值，MED-V 會在 HKEY \ _CURRENT 使用者登錄配置儲存格中尋找。</span><span class="sxs-lookup"><span data-stu-id="768fb-110">If the value is not found, MED-V looks in the HKEY\_CURRENT USER registry hive.</span></span>

<span data-ttu-id="768fb-111">如果仍找不到該值，MED-V 會使用預設值。</span><span class="sxs-lookup"><span data-stu-id="768fb-111">If the value is still not found, MED-V uses the default.</span></span>

<span data-ttu-id="768fb-112">一般的最佳做法是在 HKEY \ _LOCAL \ _MACHINE \\System hive 或電腦原則中設定值。</span><span class="sxs-lookup"><span data-stu-id="768fb-112">A general best practice is to set the value in the HKEY\_LOCAL\_MACHINE\\System hive or in the machine policy.</span></span> <span data-ttu-id="768fb-113">但如果您想讓使用者能夠設定特定設定，您應該將它保留下來。</span><span class="sxs-lookup"><span data-stu-id="768fb-113">But if you want the end user to be able to configure a particular setting, then you should leave it out.</span></span>

**<span data-ttu-id="768fb-114">注意</span><span class="sxs-lookup"><span data-stu-id="768fb-114">Note</span></span>**  
<span data-ttu-id="768fb-115">在您部署 MED-V 工作區之前，您可以使用 [腳本編輯器] 來變更 MED-V 工作區包裝程式所建立的 Windows PowerShell 腳本（ps1 檔案）。</span><span class="sxs-lookup"><span data-stu-id="768fb-115">Before you deploy your MED-V workspaces, you can use a script editor to change the Windows PowerShell script (.ps1 file) that the MED-V workspace packager created.</span></span> <span data-ttu-id="768fb-116">如需詳細資訊，請參閱[使用 Windows PowerShell 配置高級設定](configuring-advanced-settings-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="768fb-116">For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).</span></span>

<span data-ttu-id="768fb-117">部署 MED-V 工作區之後，您可以透過編輯登錄專案來變更某些 MED-V 設定設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-117">After you have deployed your MED-V workspaces, you can change certain MED-V configuration settings by editing the registry entries.</span></span>



<span data-ttu-id="768fb-118">本節列出所有可設定的 MED-V 登錄機碼，並說明其用法。</span><span class="sxs-lookup"><span data-stu-id="768fb-118">This section lists all the configurable MED-V registry keys and explains their uses.</span></span>

## <span data-ttu-id="768fb-119">診斷金鑰</span><span class="sxs-lookup"><span data-stu-id="768fb-119">Diagnostics Key</span></span>


<span data-ttu-id="768fb-120">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics 金鑰有關之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-120">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="768fb-121">名稱</span><span class="sxs-lookup"><span data-stu-id="768fb-121">Name</span></span> </th>
<th align="left"><span data-ttu-id="768fb-122">類型</span><span class="sxs-lookup"><span data-stu-id="768fb-122">Type</span></span> </th>
<th align="left"><span data-ttu-id="768fb-123">資料/預設值</span><span class="sxs-lookup"><span data-stu-id="768fb-123">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="768fb-124">描述</span><span class="sxs-lookup"><span data-stu-id="768fb-124">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-125">EventLogLevel</span><span class="sxs-lookup"><span data-stu-id="768fb-125">EventLogLevel</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-126">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-126">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-127">預設值 = 3</span><span class="sxs-lookup"><span data-stu-id="768fb-127">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-128">記錄在事件記錄檔中的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="768fb-128">The type of information that is logged in the event log.</span></span> <span data-ttu-id="768fb-129">階層包括下列專案：0（無）、1（錯誤）、2（警告）、3（資訊）、4（調試）。</span><span class="sxs-lookup"><span data-stu-id="768fb-129">Levels include the following: 0 (None), 1 (Error), 2 (Warning), 3 (Information), 4 (Debug).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="768fb-130">Fts 鍵</span><span class="sxs-lookup"><span data-stu-id="768fb-130">Fts Key</span></span>


<span data-ttu-id="768fb-131">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Fts 金鑰有關之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-131">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Fts key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="768fb-132">名稱</span><span class="sxs-lookup"><span data-stu-id="768fb-132">Name</span></span></th>
<th align="left"><span data-ttu-id="768fb-133">類型</span><span class="sxs-lookup"><span data-stu-id="768fb-133">Type</span></span></th>
<th align="left"><span data-ttu-id="768fb-134">資料/預設值</span><span class="sxs-lookup"><span data-stu-id="768fb-134">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="768fb-135">描述</span><span class="sxs-lookup"><span data-stu-id="768fb-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-136">AddUserToAdminGroupEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-136">AddUserToAdminGroupEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-137">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-137">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-138">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-138">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-139">設定第一次設定是否會自動將使用者新增到管理員&#39;s 群組。</span><span class="sxs-lookup"><span data-stu-id="768fb-139">Configures whether first time setup automatically adds the end user to the administrator&#39;s group.</span></span> <span data-ttu-id="768fb-140">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-140">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-141">0 = false：第一次設定不會自動將最終使用者新增到管理員&#39;s 群組。</span><span class="sxs-lookup"><span data-stu-id="768fb-141">0 = false: First time setup does not automatically add the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-142">1 = true：第一次設定會自動將最終使用者新增到管理員&#39;s 群組。</span><span class="sxs-lookup"><span data-stu-id="768fb-142">1 = true: First time setup automatically adds the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-143">ComputerNameMask</span><span class="sxs-lookup"><span data-stu-id="768fb-143">ComputerNameMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-144">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-144">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-145">MEDV\*</span><span class="sxs-lookup"><span data-stu-id="768fb-145">MEDV\*</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-146">用來建立來賓虛擬機器&#39;s 電腦名稱稱的電腦名稱稱遮罩。</span><span class="sxs-lookup"><span data-stu-id="768fb-146">The computer name mask that is used to create the guest virtual machine&#39;s computer name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-147">遮罩可以包含% username% 標籤，以插入使用者名稱作為電腦名稱稱的一部分。</span><span class="sxs-lookup"><span data-stu-id="768fb-147">The mask can contain a %username% tag to insert the username as part of the computer name.</span></span> <span data-ttu-id="768fb-148">同樣地，% hostname% 標籤會插入主機電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="768fb-148">Likewise, the %hostname% tag inserts the name of the host computer.</span></span></p>
<p><span data-ttu-id="768fb-149">&quot; # &quot; 遮罩中的每個字元都會以亂數字取代。</span><span class="sxs-lookup"><span data-stu-id="768fb-149">Every &quot;#&quot; character in the mask is replaced by a random digit.</span></span> <span data-ttu-id="768fb-150">遮罩末端的星號（\*）字元會以隨機的字母數位字元取代。</span><span class="sxs-lookup"><span data-stu-id="768fb-150">An asterisk (\*) character at the end of the mask is replaced by random alphanumeric characters.</span></span></p>
<p><span data-ttu-id="768fb-151">您可以使用方括弧來捕獲% hostname% 與% username% 的特定字元數。</span><span class="sxs-lookup"><span data-stu-id="768fb-151">A specific number of characters from %hostname% and %username% can be captured by using square brackets.</span></span> <span data-ttu-id="768fb-152">例如， &quot; % username% [3] &quot; 會使用使用者名稱的前三個字元。</span><span class="sxs-lookup"><span data-stu-id="768fb-152">For example, &quot;%username%[3]&quot; would use the first three characters of the username.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-153">DeleteVMStateTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-153">DeleteVMStateTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-154">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-154">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-155">預設值 = 90</span><span class="sxs-lookup"><span data-stu-id="768fb-155">Default=90</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-156">第一次安裝程式嘗試刪除虛擬機器時的超時值（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-156">The time-out value, in seconds, when first time setup tries to delete the virtual machine.</span></span> <span data-ttu-id="768fb-157">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-157">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-158">DetachVfdTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-158">DetachVfdTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-160">預設 = 120</span><span class="sxs-lookup"><span data-stu-id="768fb-160">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-161">第一次安裝程式嘗試從虛擬機器分離虛擬磁碟磁片時的超時值（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-161">The time-out value, in seconds, when first time setup tries to detach the virtual floppy disk from the virtual machine.</span></span> <span data-ttu-id="768fb-162">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-162">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-163">DialogUrl</span><span class="sxs-lookup"><span data-stu-id="768fb-163">DialogUrl</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-164">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-164">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-165">連結至內部網頁的可自訂 URL，且會在第一次顯示設定對話方塊訊息時顯示。</span><span class="sxs-lookup"><span data-stu-id="768fb-165">Customizable URL that links to internal webpage and is displayed by first time setup dialog messages.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-166">ExplorerTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-166">ExplorerTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-167">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-167">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-168">預設 = 900</span><span class="sxs-lookup"><span data-stu-id="768fb-168">Default=900</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-169">第一次安裝程式等待 Windows Explorer 的超時值（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-169">The time-out value, in seconds, that first time setup waits for Windows Explorer.</span></span> <span data-ttu-id="768fb-170">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-170">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-171">FailureDialogMsg</span><span class="sxs-lookup"><span data-stu-id="768fb-171">FailureDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-172">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-172">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-173">在資源檔中找到郵件</span><span class="sxs-lookup"><span data-stu-id="768fb-173">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-174">可自訂的訊息，在第一次設定無法完成時顯示給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-174">Customizable message that is displayed to the end user when first time setup cannot be completed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-175">GiveUserGroupRightsMaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="768fb-175">GiveUserGroupRightsMaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-176">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-176">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-177">預設值 = 3</span><span class="sxs-lookup"><span data-stu-id="768fb-177">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-178">MED-V 嘗試給予使用者群組權利的最大次數。</span><span class="sxs-lookup"><span data-stu-id="768fb-178">The maximum number of times that MED-V tries to give an end user group rights.</span></span> <span data-ttu-id="768fb-179">超過指定的 retry 值，且不能成功給予使用者群組許可權，可能會導致虛擬電腦的準備失敗，並服從 MaxRetryCount 值。</span><span class="sxs-lookup"><span data-stu-id="768fb-179">Exceeding the specified retry value without being able to successfully give an end user group rights most likely causes a virtual machine preparation failure that is then subject to the MaxRetryCount value.</span></span> <span data-ttu-id="768fb-180">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-180">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-181">GiveUserGroupRightsTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-181">GiveUserGroupRightsTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-182">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-182">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-183">預設值 = 300</span><span class="sxs-lookup"><span data-stu-id="768fb-183">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-184">提供使用者群組權力的超時值（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-184">The time-out value, in seconds, when giving a user group rights.</span></span> <span data-ttu-id="768fb-185">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-185">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-186">LogFilePaths</span><span class="sxs-lookup"><span data-stu-id="768fb-186">LogFilePaths</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-187">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-187">MULTI_SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-188">在第一次設定期間，由 MED-V 收集的記錄檔路徑清單。</span><span class="sxs-lookup"><span data-stu-id="768fb-188">A list of the log file paths that MED-V collects during first time setup.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-189">MaxPostponeTime</span><span class="sxs-lookup"><span data-stu-id="768fb-189">MaxPostponeTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-190">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-190">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-191">預設 = 120</span><span class="sxs-lookup"><span data-stu-id="768fb-191">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-192">一次最多可由最終使用者推遲設定的最大小時數。</span><span class="sxs-lookup"><span data-stu-id="768fb-192">The maximum number of hours that first time setup can be postponed by the end user.</span></span> <span data-ttu-id="768fb-193">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-193">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-194">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="768fb-194">MaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-195">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-195">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-196">預設值 = 3</span><span class="sxs-lookup"><span data-stu-id="768fb-196">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-197">如果每次嘗試都在軟體錯誤以外的失敗時間結束，則 MED-V 會嘗試準備虛擬機器的最大次數。</span><span class="sxs-lookup"><span data-stu-id="768fb-197">The maximum number of times that MED-V tries to prepare a virtual machine if each attempt ends in a failure other than a software error.</span></span> <span data-ttu-id="768fb-198">當虛擬機器準備失敗且超過設定的第一次重試次數時，MED-V 會通知最終使用者發生失敗，且不會提供重試選項。</span><span class="sxs-lookup"><span data-stu-id="768fb-198">When virtual machine preparation fails and the number of first time setup retries is exceeded, then MED-V informs the end user about the failure and does not give the option to retry.</span></span> <span data-ttu-id="768fb-199">每次啟動 MED-V 時，都會重新設定計數。</span><span class="sxs-lookup"><span data-stu-id="768fb-199">The count is re-set every time that MED-V is started.</span></span> <span data-ttu-id="768fb-200">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-200">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-201">模式</span><span class="sxs-lookup"><span data-stu-id="768fb-201">Mode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-202">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-202">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-203">預設 = 無人參與</span><span class="sxs-lookup"><span data-stu-id="768fb-203">Default=Unattended</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-204">配置第一次設定與使用者互動的方式。</span><span class="sxs-lookup"><span data-stu-id="768fb-204">Configures how first time setup interacts with the user.</span></span> <span data-ttu-id="768fb-205">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="768fb-205">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-206">上月.</span><span class="sxs-lookup"><span data-stu-id="768fb-206">Attended.</span></span></strong> <span data-ttu-id="768fb-207">最終使用者必須在第一次設定期間輸入資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-207">The end user must enter information during first time setup.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="768fb-208">注意</span><span class="sxs-lookup"><span data-stu-id="768fb-208">Note</span></span></strong><br/><p><span data-ttu-id="768fb-209">如果您建立了 Sysprep.inf 檔案，讓迷你安裝程式需要使用者輸入才能完成，則您必須選取 [ <strong> 有人值守 </strong> ] 模式，否則可能會在第一次設定期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="768fb-209">If you created the Sysprep.inf file so that Mini-Setup requires user input to complete, then you must select <strong>Attended</strong> mode or problems might occur during first time setup.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-210">無人參與 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-210">Unattended</strong>.</span></span> <span data-ttu-id="768fb-211">在第一次設定期間，虛擬機器不會顯示給最終使用者，但在第一次啟動安裝程式之前，系統會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-211">The virtual machine is not shown to the end user during first time setup, but the end user is prompted before first time setup starts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-212">[無提示] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-212">Silent</strong>.</span></span> <span data-ttu-id="768fb-213">在第一次設定期間，不會向最終使用者顯示虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="768fb-213">The virtual machine is not shown to the end user at all during first time setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-214">NonInteractiveRetryTimeoutInc</span><span class="sxs-lookup"><span data-stu-id="768fb-214">NonInteractiveRetryTimeoutInc</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-215">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-215">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-216">預設 = 15</span><span class="sxs-lookup"><span data-stu-id="768fb-216">Default=15</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-217">當重新嘗試安裝程式時，第一次必須在第一次設定互動式模式時完成設定的超時值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-217">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode when re-attempting setup.</span></span> <span data-ttu-id="768fb-218">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-218">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-219">NonInteractiveTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-219">NonInteractiveTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-220">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-220">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-221">預設值 = 45</span><span class="sxs-lookup"><span data-stu-id="768fb-221">Default=45</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-222">第一次設定在第一次設定互動式模式時必須完成的超時值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-222">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode.</span></span> <span data-ttu-id="768fb-223">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-223">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-224">PostponeUtcDateTimeLimit</span><span class="sxs-lookup"><span data-stu-id="768fb-224">PostponeUtcDateTimeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-225">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-225">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-226">第一次設定可延後的日期及時間（以 UTC 日期時間格式表示）。</span><span class="sxs-lookup"><span data-stu-id="768fb-226">The date and time, in UTC DateTime format, that first time setup can be postponed.</span></span> <span data-ttu-id="768fb-227">&quot; &quot; 使用24小時制標準，以 [YYYY-mm-dd hh： MM] 的格式輸入。</span><span class="sxs-lookup"><span data-stu-id="768fb-227">Enter in the format &quot;yyyy-MM-dd hh:mm&quot; with hours specified by using the 24-hour clock standard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-228">RetryDialogMsg</span><span class="sxs-lookup"><span data-stu-id="768fb-228">RetryDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-229">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-229">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-230">在資源檔中找到郵件</span><span class="sxs-lookup"><span data-stu-id="768fb-230">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-231">可自訂的訊息，在第一次安裝程式必須重新嘗試設定時，會顯示給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-231">Customizable message that is displayed to the end user when first time setup must re-attempt setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-232">SetComputerNameEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-232">SetComputerNameEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-233">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-233">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-234">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-234">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-235">設定來賓中 Sysprep.inf 檔案的 [UserData] 區段下的 ComputerName 專案是否應該根據指定的 ComputerNameMask 進行更新。</span><span class="sxs-lookup"><span data-stu-id="768fb-235">Configures whether the ComputerName entry under the [UserData] section of the Sysprep.inf file in the guest should be updated according to the specified ComputerNameMask.</span></span>   <span data-ttu-id="768fb-236">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-236">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-237">0 = false： Sysprep.inf 檔案中的 ComputerName 專案不會根據 ComputerNameMask 進行更新。</span><span class="sxs-lookup"><span data-stu-id="768fb-237">0 = false: The ComputerName entry in the Sysprep.inf file is not updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-238">1 = true： Sysprep.inf 檔案中的 ComputerName 專案會根據 ComputerNameMask 進行更新。</span><span class="sxs-lookup"><span data-stu-id="768fb-238">1 = true: The ComputerName entry in the Sysprep.inf file is updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-239">SetJoinDomainEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-239">SetJoinDomainEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-240">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-240">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-241">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-241">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-242">設定來賓中 Sysprep.inf 檔案的 [身分識別] 區段下的 [JoinDomain] 設定是否應該更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-242">Configures whether the JoinDomain setting under the [Identification] section of the Sysprep.inf file in the guest should be updated to match the settings on the host.</span></span>  <span data-ttu-id="768fb-243">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-243">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-244">0 = false： Sysprep.inf 檔案中的 JoinDomain 設定不會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-244">0 = false: The JoinDomain setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-245">1 = true： Sysprep.inf 檔案中的 JoinDomain 設定會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-245">1 = true: The JoinDomain setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-246">SetMachineObjectOUEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-246">SetMachineObjectOUEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-247">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-247">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-248">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-248">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-249">設定來賓中 Sysprep.inf 檔案的 [身分識別] 區段下的 [MachineObjectOU] 設定是否已更新，以符合主機。</span><span class="sxs-lookup"><span data-stu-id="768fb-249">Configures whether the MachineObjectOU setting under the [Identification] section of the Sysprep.inf file in the guest is updated to match the host.</span></span>  <span data-ttu-id="768fb-250">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-250">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-251">0 = false： Sysprep.inf 檔案中的 MachineObjectOU 設定不會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-251">0 = false: The MachineObjectOU setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-252">1 = true： Sysprep.inf 檔案中的 MachineObjectOU 設定會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-252">1 = true: The MachineObjectOU setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-253">SetRegionalSettingsEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-253">SetRegionalSettingsEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-254">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-254">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-255">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-255">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-256">設定來賓中 Sysprep.inf 檔案的 [RegionalSettings] 區段下的設定是否已更新，以符合主機的需要。</span><span class="sxs-lookup"><span data-stu-id="768fb-256">Configures whether the settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span>  <span data-ttu-id="768fb-257">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-257">0 = false; 1 = true.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="768fb-258">注意</span><span class="sxs-lookup"><span data-stu-id="768fb-258">Note</span></span></strong><br/><p><span data-ttu-id="768fb-259">根據預設，來賓中的時區設定總是與主機中的時區設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="768fb-259">By default, the setting for TimeZone in the guest is always synchronized with the TimeZone setting in the host.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-260">0 = false：來賓中 Sysprep.inf 檔案之 [RegionalSettings] 區段下的設定不會更新以符合主機。</span><span class="sxs-lookup"><span data-stu-id="768fb-260">0 = false: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are not updated to match the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-261">1 = true：來賓中 Sysprep.inf 檔案之 [RegionalSettings] 區段下的設定會更新，以符合主機的需要。</span><span class="sxs-lookup"><span data-stu-id="768fb-261">1 = true: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-262">SetUserDataEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-262">SetUserDataEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-263">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-263">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-264">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-264">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-265">設定來賓中 Sysprep.inf 檔案的 [UserData] 區段下的 [FullName] 和 [OrgName] 設定是否已更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-265">Configures whether the FullName and the OrgName settings under the [UserData] section of the Sysprep.inf file in the guest are updated to match the settings on the host.</span></span>  <span data-ttu-id="768fb-266">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-266">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-267">0 = false： Sysprep.inf 檔案中的 [FullName] 和 [OrgName] 設定不會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-267">0 = false: The FullName and OrgName settings in the Sysprep.inf file are not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-268">1 = true： Sysprep.inf 檔案中的 [FullName] 和 [OrgName] 設定會更新，以符合主機上的設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-268">1 = true: The FullName and OrgName settings in the Sysprep.inf file are updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-269">StartDialogMsg</span><span class="sxs-lookup"><span data-stu-id="768fb-269">StartDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-270">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-270">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-271">在資源檔中找到郵件</span><span class="sxs-lookup"><span data-stu-id="768fb-271">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-272">可自訂的訊息，在第一次設定準備開始時顯示給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-272">Customizable message that is displayed to the end user when first time setup is ready to start.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-273">TaskCancelTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-273">TaskCancelTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-274">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-275">預設 = 30</span><span class="sxs-lookup"><span data-stu-id="768fb-275">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-276">"超時值] （以秒為單位），在第一次安裝程式等待來自虛擬機器的回應以進行取消操作時。</span><span class="sxs-lookup"><span data-stu-id="768fb-276">The time-out value, in seconds, that first time setup waits for a response from the virtual machine for a Cancel operation.</span></span> <span data-ttu-id="768fb-277">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-277">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-278">TaskVMTurnOffTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-278">TaskVMTurnOffTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-279">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-279">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-280">預設值 = 60</span><span class="sxs-lookup"><span data-stu-id="768fb-280">Default=60</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-281">第一次安裝程式等到虛擬機器關閉時，的超時值（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-281">The time-out value, in seconds, that first time setup waits for the virtual machine to shut down.</span></span> <span data-ttu-id="768fb-282">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-282">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-283">UpgradeTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-283">UpgradeTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-284">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-284">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-285">預設 = 600</span><span class="sxs-lookup"><span data-stu-id="768fb-285">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-286">嘗試升級 MED-V 來賓代理軟體超時前的時間（以秒為單位）。範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-286">The time, in seconds, before an attempted upgrade of the MED-V Guest Agent software times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="768fb-287">UserExperience 鍵</span><span class="sxs-lookup"><span data-stu-id="768fb-287">UserExperience Key</span></span>


<span data-ttu-id="768fb-288">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience 金鑰和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\UserExperience 金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-288">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\UserExperience key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="768fb-289">名稱</span><span class="sxs-lookup"><span data-stu-id="768fb-289">Name</span></span></th>
<th align="left"><span data-ttu-id="768fb-290">類型</span><span class="sxs-lookup"><span data-stu-id="768fb-290">Type</span></span></th>
<th align="left"><span data-ttu-id="768fb-291">資料/預設值</span><span class="sxs-lookup"><span data-stu-id="768fb-291">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="768fb-292">描述</span><span class="sxs-lookup"><span data-stu-id="768fb-292">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-293">AppPublishingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-293">AppPublishingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-294">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-294">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-295">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-295">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-296">配置是否已啟用從來賓到主機的應用程式發佈。</span><span class="sxs-lookup"><span data-stu-id="768fb-296">Configures whether application publication from the guest to the host is enabled.</span></span>  <span data-ttu-id="768fb-297">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-297">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-298">0 = false：停用來賓向主機發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="768fb-298">0 = false: Disables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-299">1 = true：啟用從來賓到主機的應用程式發佈。</span><span class="sxs-lookup"><span data-stu-id="768fb-299">1 = true: Enables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-300">AudioSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-300">AudioSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-301">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-301">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-302">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-302">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-303">設定是否已啟用在來賓與主機之間共用音訊 i/o 裝置的功能。</span><span class="sxs-lookup"><span data-stu-id="768fb-303">Configures whether the sharing of the audio I/O device between the guest and the host is enabled.</span></span>  <span data-ttu-id="768fb-304">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-304">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-305">0 = false：停用來賓與主機之間的音訊 i/o 裝置共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-305">0 = false: Disables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-306">1 = true：啟用在來賓與主機之間共用音訊 i/o 裝置。</span><span class="sxs-lookup"><span data-stu-id="768fb-306">1 = true: Enables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-307">ClipboardSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-307">ClipboardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-308">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-308">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-309">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-309">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-310">設定是否啟用 [在來賓與主機之間共用剪貼簿]。</span><span class="sxs-lookup"><span data-stu-id="768fb-310">Configures whether the sharing of the Clipboard between the guest and the host is enabled.</span></span>  <span data-ttu-id="768fb-311">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-311">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-312">0 = false：停用來賓與主機之間的剪貼簿共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-312">0 = false: Disables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-313">1 = true：啟用來賓與主機之間的剪貼簿共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-313">1 = true: Enables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-314">DialogTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-314">DialogTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-315">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-315">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-316">預設值 = 300</span><span class="sxs-lookup"><span data-stu-id="768fb-316">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-317">第一次設定開始對話方塊超時之前的時間（以秒為單位）。範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-317">The time, in seconds, before the first time setup Start Dialog times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-318">HideVmTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-318">HideVmTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-319">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-319">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-320">預設 = 30</span><span class="sxs-lookup"><span data-stu-id="768fb-320">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-321">超時值（以分鐘為單位），在長時間登錄嘗試中，全螢幕虛擬機器視窗會隱藏在最終使用者中。</span><span class="sxs-lookup"><span data-stu-id="768fb-321">The time-out value, in minutes, that the full-screen virtual machine window is hidden from the end user during a long logon attempt.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-322">LogonStartEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-322">LogonStartEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-323">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-323">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-324">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-324">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-325">設定使用者登入桌面或第一次來賓應用程式啟動時，是否應啟動來賓。</span><span class="sxs-lookup"><span data-stu-id="768fb-325">Configures whether the guest should be started when the end user logs on to the desktop or when the first guest application is started.</span></span>  <span data-ttu-id="768fb-326">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-326">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-327">0 = false：啟動第一個來賓應用程式時，會啟動來賓。</span><span class="sxs-lookup"><span data-stu-id="768fb-327">0 = false: The guest is started when the first guest application is started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-328">1 = true：當使用者登入桌面時，就會啟動來賓。</span><span class="sxs-lookup"><span data-stu-id="768fb-328">1 = true: The guest is started when the end user logs on to the desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-329">PrinterSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-329">PrinterSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-330">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-330">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-331">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-331">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-332">設定來賓與主機之間的印表機共用是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="768fb-332">Configures whether the sharing of printers between the guest and the host is enabled.</span></span>  <span data-ttu-id="768fb-333">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-333">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-334">0 = false：停用來賓與主機之間的印表機共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-334">0 = false: Disables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-335">1 = true：啟用來賓與主機之間的印表機共用功能。</span><span class="sxs-lookup"><span data-stu-id="768fb-335">1 = true: Enables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-336">RebootAbsoluteDelayTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-336">RebootAbsoluteDelayTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-337">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-337">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-338">預設 = 1440</span><span class="sxs-lookup"><span data-stu-id="768fb-338">Default=1440</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-339">第一次安裝程式等待重新開機的超時值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="768fb-339">The time-out value, in minutes, that first time setup waits for a restart.</span></span> <span data-ttu-id="768fb-340">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-340">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-341">RedirectUrls</span><span class="sxs-lookup"><span data-stu-id="768fb-341">RedirectUrls</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-342">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-342">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-343">指定的 URL 清單</span><span class="sxs-lookup"><span data-stu-id="768fb-343">Specified URL list</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-344">指定要從主機重新導向至來賓的 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="768fb-344">Specifies a list of URLs to be redirected from the host to the guest.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-345">SmartCardLogonEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-345">SmartCardLogonEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-346">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-346">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-347">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-347">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-348">設定智慧卡是否可以用來向 MED-V 驗證使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-348">Configures whether smart cards can be used to authenticate users to MED-V.</span></span> <span data-ttu-id="768fb-349">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-349">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-350">0 = false：不讓智慧卡驗證最終使用者至 MED-V。</span><span class="sxs-lookup"><span data-stu-id="768fb-350">0 = false: Does not let Smart Cards authenticate end users to MED-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-351">1 = true：讓智慧卡向 MED-V 驗證最終使用者。</span><span class="sxs-lookup"><span data-stu-id="768fb-351">1 = true: Lets Smart Cards authenticate end users to MED-V.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="768fb-352">重要</span><span class="sxs-lookup"><span data-stu-id="768fb-352">Important</span></span></strong><br/><p><span data-ttu-id="768fb-353">如果 SmartCardLogonEnabled 和 CredentialCacheEnabled 都已啟用，SmartCardLogonEnabled 會覆寫 CredentialCacheEnabled。</span><span class="sxs-lookup"><span data-stu-id="768fb-353">If SmartCardLogonEnabled and CredentialCacheEnabled are both enabled, SmartCardLogonEnabled overrides CredentialCacheEnabled.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-354">SmartCardSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-354">SmartCardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-356">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-356">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-357">設定來賓與主機之間的智慧卡共用是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="768fb-357">Configures whether the sharing of Smart Cards between the guest and the host is enabled.</span></span>  <span data-ttu-id="768fb-358">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-358">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-359">0 = false：停用來賓與主機之間的智慧卡共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-359">0 = false: Disables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-360">1 = true：啟用來賓與主機之間的智慧卡共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-360">1 = true: Enables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-361">USBDeviceSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-361">USBDeviceSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-363">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-363">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-364">設定來賓與主機之間的 USB 裝置共用是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="768fb-364">Configures whether the sharing of USB devices between the guest and the host is enabled.</span></span>  <span data-ttu-id="768fb-365">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-365">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-366">0 = false：停用來賓與主機之間的 USB 裝置共用。</span><span class="sxs-lookup"><span data-stu-id="768fb-366">0 = false: Disables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-367">1 = true：啟用來賓與主機之間的 USB 裝置共用功能。</span><span class="sxs-lookup"><span data-stu-id="768fb-367">1 = true: Enables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="768fb-368">VM 金鑰</span><span class="sxs-lookup"><span data-stu-id="768fb-368">VM Key</span></span>


<span data-ttu-id="768fb-369">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\VM 金鑰和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\VM 金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-369">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\VM key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\VM key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="768fb-370">名稱</span><span class="sxs-lookup"><span data-stu-id="768fb-370">Name</span></span></th>
<th align="left"><span data-ttu-id="768fb-371">類型</span><span class="sxs-lookup"><span data-stu-id="768fb-371">Type</span></span></th>
<th align="left"><span data-ttu-id="768fb-372">資料/預設值</span><span class="sxs-lookup"><span data-stu-id="768fb-372">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="768fb-373">描述</span><span class="sxs-lookup"><span data-stu-id="768fb-373">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-374">CloseAction</span><span class="sxs-lookup"><span data-stu-id="768fb-374">CloseAction</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-375">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-375">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-376">預設 = 休眠</span><span class="sxs-lookup"><span data-stu-id="768fb-376">Default=HIBERNATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-377">虛擬機器在執行的最後一個應用程式關閉之後所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="768fb-377">The action that the virtual machine performs after the last application that is running is closed.</span></span> <span data-ttu-id="768fb-378">如果啟用 LogonStartEnabled 值，則會忽略此設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-378">This setting is ignored if the LogonStartEnabled value is enabled.</span></span> <span data-ttu-id="768fb-379">可能的選項如下所示：</span><span class="sxs-lookup"><span data-stu-id="768fb-379">Possible options are as follows:</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-380">[休眠] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-380">HIBERNATE</strong> .</span></span> <span data-ttu-id="768fb-381">這個選項會釋放虛擬機器所使用的所有物理資源，例如記憶體和 CPU，並儲存所有執行的應用程式和作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="768fb-381">This option releases all physical resources that the virtual machine is using, such as memory and CPU, and saves the state of all running applications and operations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-382">關閉 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-382">SHUTDOWN</strong> .</span></span> <span data-ttu-id="768fb-383">這個選項會安全地關閉客體作業系統，然後釋放虛擬機器所使用的所有物理資源，例如記憶體和 CPU。</span><span class="sxs-lookup"><span data-stu-id="768fb-383">This option shuts down the guest operating system safely and then releases all physical resources that the virtual machine is using, such as memory and CPU.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-384">關閉 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-384">TURN-OFF</strong>.</span></span> <span data-ttu-id="768fb-385">這個選項可能會造成資料遺失，因為它與關閉電源按鈕或在物理電腦上拉出電源線一樣。</span><span class="sxs-lookup"><span data-stu-id="768fb-385">This option can cause data loss because it is the same as turning off the power button or pulling out the power cord on a physical computer.</span></span> <span data-ttu-id="768fb-386">只有在您無法使用其他兩個選項時，才能使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="768fb-386">Use this option only if you cannot use one of the other two options.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-387">GuestMemFromHostMem</span><span class="sxs-lookup"><span data-stu-id="768fb-387">GuestMemFromHostMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-388">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-388">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-389">378、512、1024、1536、2048</span><span class="sxs-lookup"><span data-stu-id="768fb-389">378, 512, 1024, 1536, 2048</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-390">來賓的記憶體（MB）值清單。</span><span class="sxs-lookup"><span data-stu-id="768fb-390">A list of memory (MB) values for the guest.</span></span> <span data-ttu-id="768fb-391">這個值是用來判斷來賓可以使用多少 RAM。</span><span class="sxs-lookup"><span data-stu-id="768fb-391">This value is used to determine how much RAM is available to the guest.</span></span> <span data-ttu-id="768fb-392">結合 HostMemToGuestMem，就會建立查閱表格，判斷要在來賓虛擬機器上配置多少 RAM。</span><span class="sxs-lookup"><span data-stu-id="768fb-392">Combined with HostMemToGuestMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="768fb-393">可能的值可能是從128到3712。</span><span class="sxs-lookup"><span data-stu-id="768fb-393">Possible values can be from 128 to 3712.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-394">GuestUpdateDuration</span><span class="sxs-lookup"><span data-stu-id="768fb-394">GuestUpdateDuration</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-396">預設 = 240</span><span class="sxs-lookup"><span data-stu-id="768fb-396">Default=240</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-397">MED-V 應該讓來賓保持訪客喚醒以進行自動更新，從在 GuestUpdateTime 值中指定的時間開始。</span><span class="sxs-lookup"><span data-stu-id="768fb-397">The number of minutes that MED-V should keep the guest awake for automatic updating, starting at the time specified in the GuestUpdateTime value.</span></span> <span data-ttu-id="768fb-398">範圍 = 0 至1440。</span><span class="sxs-lookup"><span data-stu-id="768fb-398">Range = 0 to 1440.</span></span> <span data-ttu-id="768fb-399">將此值設定為零（0）會停用來賓修補功能。</span><span class="sxs-lookup"><span data-stu-id="768fb-399">Setting this value to zero (0) disables the guest patching functionality.</span></span></p>
<p><span data-ttu-id="768fb-400">如需有關來賓修補程式以進行自動更新的詳細資訊，請參閱 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作區的自動更新 </a> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-400">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-401">GuestUpdateTime</span><span class="sxs-lookup"><span data-stu-id="768fb-401">GuestUpdateTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-402">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-402">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-403">預設值 = 00：00</span><span class="sxs-lookup"><span data-stu-id="768fb-403">Default=00:00</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-404">MED-V 應該使用24小時制的標準，將訪客喚醒以進行自動更新。</span><span class="sxs-lookup"><span data-stu-id="768fb-404">The hour and minute each day when MED-V should wake up the guest for automatic updating, by using the 24-hour clock standard.</span></span> <span data-ttu-id="768fb-405">以 HH： MM 格式指定時間</span><span class="sxs-lookup"><span data-stu-id="768fb-405">Specify the time in the format HH:MM</span></span>  </p>
<p><span data-ttu-id="768fb-406">如需有關來賓修補程式以進行自動更新的詳細資訊，請參閱 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作區的自動更新 </a> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-406">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-407">HostMemToGuestMem</span><span class="sxs-lookup"><span data-stu-id="768fb-407">HostMemToGuestMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-408">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-408">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-409">1024、2048、4096、8192、16384</span><span class="sxs-lookup"><span data-stu-id="768fb-409">1024, 2048, 4096, 8192, 16384</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-410">來賓的記憶體（MB）值清單，由主機上可用的 RAM 決定。</span><span class="sxs-lookup"><span data-stu-id="768fb-410">A list of memory (MB) values for the guest, determined by the RAM available on the host.</span></span> <span data-ttu-id="768fb-411">結合 GuestMemFromHostMem，就會建立查閱表格，判斷要在來賓虛擬機器上配置多少 RAM。</span><span class="sxs-lookup"><span data-stu-id="768fb-411">Combined with GuestMemFromHostMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="768fb-412">可能的值可能是從1024到16384。</span><span class="sxs-lookup"><span data-stu-id="768fb-412">Possible values can be from 1024 to 16384.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-413">HostMemToGuestMemCalcEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-413">HostMemToGuestMemCalcEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-414">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-414">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-415">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-415">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-416">設定為來賓指派的記憶體是否是從主機上的記憶體計算而來。</span><span class="sxs-lookup"><span data-stu-id="768fb-416">Configures whether the memory allocated for the guest is calculated from the memory present on the host.</span></span>  <span data-ttu-id="768fb-417">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-417">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-418">0 = false：為來賓指派的記憶體不會從主機上的記憶體計算。</span><span class="sxs-lookup"><span data-stu-id="768fb-418">0 = false: The memory allocated for the guest is not calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-419">1 = true：為來賓指派的記憶體是從主機上的記憶體計算而來。</span><span class="sxs-lookup"><span data-stu-id="768fb-419">1 = true: The memory allocated for the guest is calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-420">記憶體</span><span class="sxs-lookup"><span data-stu-id="768fb-420">Memory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-421">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-421">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-422">預設值 = 512</span><span class="sxs-lookup"><span data-stu-id="768fb-422">Default=512</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-423">應該為來賓虛擬機器指派的 RAM （MB）。</span><span class="sxs-lookup"><span data-stu-id="768fb-423">The RAM (MB) that should be allocated for the guest virtual machine.</span></span> <span data-ttu-id="768fb-424">如果啟用 HostMemToGuestMemEnabled 設定，則會忽略此設定。</span><span class="sxs-lookup"><span data-stu-id="768fb-424">This setting is ignored if the HostMemToGuestMemEnabled setting is enabled.</span></span> <span data-ttu-id="768fb-425">範圍 = 128 至2048。</span><span class="sxs-lookup"><span data-stu-id="768fb-425">Range=128 to 2048.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-426">MultiUserEnabled</span><span class="sxs-lookup"><span data-stu-id="768fb-426">MultiUserEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-427">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-427">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-428">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="768fb-428">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-429">設定多個使用者是否共用同一個 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="768fb-429">Configures whether multiple users share the same MED-V workspace.</span></span>  <span data-ttu-id="768fb-430">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="768fb-430">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-431">0 = false：多個使用者不共用同一個 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="768fb-431">0 = false: Multiple users do not share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-432">1 = true：多個使用者共用同一個 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="768fb-432">1 = true: Multiple users share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="768fb-433">NetworkingMode</span><span class="sxs-lookup"><span data-stu-id="768fb-433">NetworkingMode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-434">SZ</span><span class="sxs-lookup"><span data-stu-id="768fb-434">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-435">預設 = NAT</span><span class="sxs-lookup"><span data-stu-id="768fb-435">Default=NAT</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-436">來賓上所用的網路連線類型。</span><span class="sxs-lookup"><span data-stu-id="768fb-436">The kind of network connection used on the guest.</span></span> <span data-ttu-id="768fb-437">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="768fb-437">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-438">已橋接 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-438">Bridged</strong>.</span></span> <span data-ttu-id="768fb-439">MED-V 有自己的網路位址，通常是透過 DHCP 取得的。</span><span class="sxs-lookup"><span data-stu-id="768fb-439">MED-V has its own network address, typically obtained through DHCP.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="768fb-440">NAT </strong> 。</span><span class="sxs-lookup"><span data-stu-id="768fb-440">NAT</strong>.</span></span> <span data-ttu-id="768fb-441">MED-V 使用網路位址轉譯（NAT）來共用主機&#39;s IP 以進行外寄通訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-441">MED-V uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-442">TaskTimeout</span><span class="sxs-lookup"><span data-stu-id="768fb-442">TaskTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-443">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-443">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-444">預設 = 600</span><span class="sxs-lookup"><span data-stu-id="768fb-444">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-445">一般超時值（以秒為單位），即由 MED-V 等待完成工作，例如重新開機及關閉。</span><span class="sxs-lookup"><span data-stu-id="768fb-445">A general time-out value, in seconds, that MED-V waits for a task to be completed, such as restarting and shutting down.</span></span> <span data-ttu-id="768fb-446">範圍 = 0 至2147483647。</span><span class="sxs-lookup"><span data-stu-id="768fb-446">Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="768fb-447">來賓註冊設定</span><span class="sxs-lookup"><span data-stu-id="768fb-447">Guest Registry Settings</span></span>


<span data-ttu-id="768fb-448">本節列出可設定的 MED-V 來賓登錄機碼，並說明其用法。</span><span class="sxs-lookup"><span data-stu-id="768fb-448">This section lists the configurable MED-V guest registry keys and explains their uses.</span></span>

### <span data-ttu-id="768fb-449">v2</span><span class="sxs-lookup"><span data-stu-id="768fb-449">v2</span></span>

<span data-ttu-id="768fb-450">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ 金鑰相關聯之來賓登錄值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="768fb-450">The following table provides information about the guest registry value associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\ key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="768fb-451">名稱</span><span class="sxs-lookup"><span data-stu-id="768fb-451">Name</span></span> </th>
<th align="left"><span data-ttu-id="768fb-452">類型</span><span class="sxs-lookup"><span data-stu-id="768fb-452">Type</span></span> </th>
<th align="left"><span data-ttu-id="768fb-453">資料/預設值</span><span class="sxs-lookup"><span data-stu-id="768fb-453">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="768fb-454">描述</span><span class="sxs-lookup"><span data-stu-id="768fb-454">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="768fb-455">EnableGPWorkarounds</span><span class="sxs-lookup"><span data-stu-id="768fb-455">EnableGPWorkarounds</span></span></p></td>
<td align="left"><p><span data-ttu-id="768fb-456">DWORD</span><span class="sxs-lookup"><span data-stu-id="768fb-456">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-457">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="768fb-457">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="768fb-458">配置 MED-V 處理金鑰 BufferPolicyReads 和 GroupPolicyMinTransferRate 的方式。</span><span class="sxs-lookup"><span data-stu-id="768fb-458">Configures how MED-V handles the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="768fb-459">根據預設，MED-V 會依以下方式設定這些金鑰：</span><span class="sxs-lookup"><span data-stu-id="768fb-459">By default, MED-V sets these keys as follows:</span></span></p>
<p><span data-ttu-id="768fb-460">BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0。</span><span class="sxs-lookup"><span data-stu-id="768fb-460">BufferPolicyReads=1 and GroupPolicyMinTransferRate=0.</span></span></p>
<p><span data-ttu-id="768fb-461">如果您不想要 MED-V 變更 BufferPolicyReads 和 GroupPolicyMinTransferRate 的預設設定，請視需要建立 EnableGPWorkarounds 金鑰（如果有必要的話），並將該金鑰設定為零。</span><span class="sxs-lookup"><span data-stu-id="768fb-461">Create the EnableGPWorkarounds  key, if it is necessary, and set the key to zero if you do not want MED-V to change the default settings of BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="768fb-462">注意</span><span class="sxs-lookup"><span data-stu-id="768fb-462">Note</span></span></strong><br/><p><span data-ttu-id="768fb-463">如果您的 MED-V 工作區是在 NAT 模式下執行，EnableGPWorkarounds 會影響登錄機碼 BufferPolicyReads 和 GroupPolicyMinTransferRate。</span><span class="sxs-lookup"><span data-stu-id="768fb-463">If your MED-V workspace is running in NAT mode, EnableGPWorkarounds affects the registry keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span> <span data-ttu-id="768fb-464">如果您的 MED-V 工作區是以橋接模式執行，EnableGPWorkarounds 只會影響登錄機碼 BufferPolicyReads。</span><span class="sxs-lookup"><span data-stu-id="768fb-464">If your MED-V workspace is running in BRIDGED mode, EnableGPWorkarounds only affects the registry key BufferPolicyReads.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="768fb-465">1 = true： MED-V 會將鍵設定為 BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0 （如果在 NAT 模式下執行），或僅 BufferPolicyReads = 1 （如果以橋接模式執行）。</span><span class="sxs-lookup"><span data-stu-id="768fb-465">1=true: MED-V sets the keys BufferPolicyReads=1 and GroupPolicyMinTransferRate=0 (if running in NAT mode) or just BufferPolicyReads=1 (if running in BRIDGED mode).</span></span></p>
<p><span data-ttu-id="768fb-466">0 = false： MED-V 不會對金鑰 BufferPolicyReads 和 GroupPolicyMinTransferRate 進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="768fb-466">0=false: MED-V does not make any changes to the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="768fb-467">相關主題</span><span class="sxs-lookup"><span data-stu-id="768fb-467">Related topics</span></span>


[<span data-ttu-id="768fb-468">管理 MED-V 工作區應用程式</span><span class="sxs-lookup"><span data-stu-id="768fb-468">Manage MED-V Workspace Applications</span></span>](manage-med-v-workspace-applications.md)

[<span data-ttu-id="768fb-469">管理 MED-V URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="768fb-469">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)

[<span data-ttu-id="768fb-470">管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="768fb-470">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)









