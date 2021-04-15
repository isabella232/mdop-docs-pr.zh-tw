---
title: 使用群組原則物件來配置 UE-V 2.x
description: 使用群組原則物件來配置 UE-V 2.x
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494058"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a><span data-ttu-id="3bf46-103">使用群組原則物件來配置 UE-V 2.x</span><span class="sxs-lookup"><span data-stu-id="3bf46-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="3bf46-104">某些 Microsoft 使用者體驗虛擬化 (UE-V) 2.0、2.1 和 2.1 SP1 群組原則設定可以定義電腦，也可以定義其他群組原則設定給使用者。</span><span class="sxs-lookup"><span data-stu-id="3bf46-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="3bf46-105">若要瞭解如何安裝 UE-V 群組原則 ADMX 檔案，請參閱安裝 [UE-V 2 群組原則 ADMX 範本](https://technet.microsoft.com/library/dn458891.aspx#admx)。</span><span class="sxs-lookup"><span data-stu-id="3bf46-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="3bf46-106">您可以針對 UE-V 設定下列策略設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="3bf46-107">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3bf46-108">群組原則設定名稱</span><span class="sxs-lookup"><span data-stu-id="3bf46-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="3bf46-109">Target</span><span class="sxs-lookup"><span data-stu-id="3bf46-109">Target</span></span></th>
<th align="left"><span data-ttu-id="3bf46-110">群組原則設定描述</span><span class="sxs-lookup"><span data-stu-id="3bf46-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="3bf46-111">設定選項</span><span class="sxs-lookup"><span data-stu-id="3bf46-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-112">設定同步處理方法</span><span class="sxs-lookup"><span data-stu-id="3bf46-112">Configure Sync Method</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-113">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-114">您可以使用此群組原則設定來設定使用者體驗虛擬化 (UE-V) 同步提供者功能。</span><span class="sxs-lookup"><span data-stu-id="3bf46-114">By using this Group Policy setting, you can configure whether User Experience Virtualization (UE-V) uses the sync provider feature.</span></span> <span data-ttu-id="3bf46-115">此策略設定也可讓您在延遲使用者設定輸入時顯示通知。</span><span class="sxs-lookup"><span data-stu-id="3bf46-115">This policy setting also lets you enable a notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-116">啟用此設定以設定 UE-V 代理程式不使用同步處理提供者，或使用外部同步處理引擎。</span><span class="sxs-lookup"><span data-stu-id="3bf46-116">Enable this setting to configure the UE-V agent not to use the sync provider, or to use the external synchronization engine.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-117">連上 IT 連結文字</span><span class="sxs-lookup"><span data-stu-id="3bf46-117">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-118">僅適用于電腦</span><span class="sxs-lookup"><span data-stu-id="3bf46-118">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-119">此群組原則設定會指定公司設定中心中連絡人 IT URL 超連結的文字。</span><span class="sxs-lookup"><span data-stu-id="3bf46-119">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-120">如果您啟用此群組原則設定，公司設定中心會在連絡人 IT URL 的連結中顯示指定的文字。</span><span class="sxs-lookup"><span data-stu-id="3bf46-120">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-121">與 IT URL 聯繫</span><span class="sxs-lookup"><span data-stu-id="3bf46-121">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-122">僅適用于電腦</span><span class="sxs-lookup"><span data-stu-id="3bf46-122">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-123">此群組原則設定會指定公司設定中心中連絡人 IT 連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="3bf46-123">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-124">如果您啟用這項設定，公司設定中心會連至指定的 URL 連至 IT 文字。</span><span class="sxs-lookup"><span data-stu-id="3bf46-124">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="3bf46-125">連結可以是任何標準通訊協定，例如 HTTP 或 mailto。</span><span class="sxs-lookup"><span data-stu-id="3bf46-125">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-126">第一次使用通知</span><span class="sxs-lookup"><span data-stu-id="3bf46-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-127">僅適用于電腦</span><span class="sxs-lookup"><span data-stu-id="3bf46-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-128">此群組原則設定可在 UE-V 出現時，通知區域中顯示的通知</span><span class="sxs-lookup"><span data-stu-id="3bf46-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="3bf46-129">代理程式第一次執行。</span><span class="sxs-lookup"><span data-stu-id="3bf46-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-130">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="3bf46-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-131">同步之前，先 Ping 設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="3bf46-131">Ping the settings storage location before sync</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-132">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-133">此策略設定可讓 UE-V 同步處理提供者的設定在嘗試同步處理設定之前，先 ping 設定儲存路徑，以驗證連接。</span><span class="sxs-lookup"><span data-stu-id="3bf46-133">This policy setting allows configuration of the UE-V sync provider to ping the settings storage path before attempting to sync settings in order to verify the connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-134">啟用或停用此群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-134">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-135">設定套件大小警告閾值</span><span class="sxs-lookup"><span data-stu-id="3bf46-135">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-136">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-136">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-137">此群組原則設定可讓您設定 UE-V Agent，以在設定套件檔案大小達到定義的臨界值時報告。</span><span class="sxs-lookup"><span data-stu-id="3bf46-137">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-138">指定以 KB 為單位設定套件大小 (閾值) 。</span><span class="sxs-lookup"><span data-stu-id="3bf46-138">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="3bf46-139">根據預設，UE-V Agent 沒有封裝檔案大小閾值。</span><span class="sxs-lookup"><span data-stu-id="3bf46-139">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-140">設定儲存路徑</span><span class="sxs-lookup"><span data-stu-id="3bf46-140">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-141">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-141">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-142">此群組原則設定會設定要儲存使用者設定的位置。</span><span class="sxs-lookup"><span data-stu-id="3bf46-142">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-143">在 UNC 中輸入通用命名慣例 (UNC) 路徑和變數，例如 \Server\SettingsShare%username%%。</span><span class="sxs-lookup"><span data-stu-id="3bf46-143">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-144">設定範本目錄路徑</span><span class="sxs-lookup"><span data-stu-id="3bf46-144">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-145">僅適用于電腦</span><span class="sxs-lookup"><span data-stu-id="3bf46-145">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-146">此群組原則設定會設定自訂設定位置範本的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3bf46-146">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="3bf46-147">此策略設定也會設定是否要使用目錄取代以 UE-V Agent 安裝的預設 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="3bf46-147">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-148">在 UNC 路徑中 (通用) ，例如 \Server\TemplateShare 或電腦中的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="3bf46-148">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="3bf46-149">選取核取方塊以取代預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="3bf46-149">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-150">在計量計費的連接上同步設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-150">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-151">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-151">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-152">此群組原則設定會定義 UE-V 是否以計量計費連接同步設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-152">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-153">根據預設，UE-V Agent 不會以計量計費連接同步設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-153">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-154">即使漫遊時，也使用計量計費連接同步設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-154">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-155">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-155">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-156">此群組原則設定會定義 UE-V 是否同步處理家用提供者網路外部的計量計費連接設定，例如資料連線在漫遊模式中時。</span><span class="sxs-lookup"><span data-stu-id="3bf46-156">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-157">根據預設，UE-V 不會在漫遊模式中，以計量計費連接同步設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-157">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-158">同步處理超時</span><span class="sxs-lookup"><span data-stu-id="3bf46-158">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-159">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-159">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-160">此群組原則設定會設定電腦在從遠端設定位置中取回使用者設定時，在延遲前等待的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="3bf46-160">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="3bf46-161">如果遠端儲存位置無法使用，且使用者不使用同步處理提供者，應用程式啟動會延遲這麼多毫秒。</span><span class="sxs-lookup"><span data-stu-id="3bf46-161">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-162">指定偏好的同步處理時間，以毫秒為單位。</span><span class="sxs-lookup"><span data-stu-id="3bf46-162">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="3bf46-163">預設值為 2000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="3bf46-163">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-164">同步 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-164">Synchronize Windows settings</span></span> </p></td>
<td align="left"><p><span data-ttu-id="3bf46-165">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-165">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-166">此群組原則設定會設定 Windows 設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="3bf46-166">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-167">選取電腦之間同步的 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-167">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="3bf46-168">根據預設，Windows 主題、桌面設定和輕鬆存取設定會同步設定于相同作業系統版本的電腦之間。</span><span class="sxs-lookup"><span data-stu-id="3bf46-168">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-169">工作列圖示</span><span class="sxs-lookup"><span data-stu-id="3bf46-169">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-170">僅適用于電腦</span><span class="sxs-lookup"><span data-stu-id="3bf46-170">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-171">此群組原則設定會啟用 UE-V 工作列圖示。</span><span class="sxs-lookup"><span data-stu-id="3bf46-171">This Group Policy setting enables the UE-V tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-172">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="3bf46-172">The default is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-173">使用使用者體驗虛擬化 (UE-V) </span><span class="sxs-lookup"><span data-stu-id="3bf46-173">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-174">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-174">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-175">此群組原則設定可讓您啟用或停用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="3bf46-175">This Group Policy setting lets you enable or disable UE-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-176">啟用或停用此群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-176">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-177">VDI 組組</span><span class="sxs-lookup"><span data-stu-id="3bf46-177">VDI Configuration</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-178">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-178">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-179">此策略設定會針對在集中式 VDI 環境中執行的電腦設定 UE-V 卷回信息的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3bf46-179">This policy setting configures the synchronization of UE-V rollback information for computers running in a pooled VDI environment.</span></span> <span data-ttu-id="3bf46-180">如果啟用此策略，UE-V 復原狀態會複製到登出時設定儲存位置，登入時還原。</span><span class="sxs-lookup"><span data-stu-id="3bf46-180">If this policy is enabled, the UE-V rollback state is copied to the settings storage location on logout and restored on login.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-181">啟用或停用此群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-181">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="3bf46-182">注意</span><span class="sxs-lookup"><span data-stu-id="3bf46-182">Note</span></span>**  
<span data-ttu-id="3bf46-183">此外，許多桌面應用程式和 Windows 應用程式都提供群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-183">In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="3bf46-184">您可以使用這些設定來啟用或停用特定應用程式的設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="3bf46-184">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="3bf46-185">Windows App 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-185">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3bf46-186">群組原則設定名稱</span><span class="sxs-lookup"><span data-stu-id="3bf46-186">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="3bf46-187">Target</span><span class="sxs-lookup"><span data-stu-id="3bf46-187">Target</span></span></th>
<th align="left"><span data-ttu-id="3bf46-188">群組原則設定描述</span><span class="sxs-lookup"><span data-stu-id="3bf46-188">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="3bf46-189">設定選項</span><span class="sxs-lookup"><span data-stu-id="3bf46-189">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-190">請勿同步 Windows App</span><span class="sxs-lookup"><span data-stu-id="3bf46-190">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-191">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-191">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-192">此群組原則設定會定義 UE-V Agent 是否同步 Windows 應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-192">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-193">預設為同步 Windows App。</span><span class="sxs-lookup"><span data-stu-id="3bf46-193">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3bf46-194">Windows 應用程式清單</span><span class="sxs-lookup"><span data-stu-id="3bf46-194">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-195">電腦與使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-195">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-196">此設定會列出 Windows App 的家庭套件名稱，並明確列出 UE-V 是否同步處理該應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-196">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-197">您可以使用此設定來指定應用程式設定永遠不會由 UE-V 同步，即使所有其他 Windows 應用程式的設定已同步。</span><span class="sxs-lookup"><span data-stu-id="3bf46-197">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3bf46-198">同步未列出的 Windows App</span><span class="sxs-lookup"><span data-stu-id="3bf46-198">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-199">電腦與使用者</span><span class="sxs-lookup"><span data-stu-id="3bf46-199">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-200">此群組原則設定會定義 Windows App 清單中未明確列出的 Windows App UE-V Agent 的預設設定同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="3bf46-200">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3bf46-201">根據預設，UE-V Agent 只會同步顯示于 Windows 應用程式清單中的 Windows App 設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-201">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3bf46-202">有關同步化 Windows 應用程式的資訊，請參閱 [Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="3bf46-202">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="3bf46-203">設定電腦目標群組策略設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-203">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="3bf46-204">在做為網域控制站的電腦上，使用群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 來管理 UE-V 電腦的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-204">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="3bf46-205">流覽至 **電腦群組**組，選取 [ **策略**>、選取 **[系統管理範本**>、按一下 **[Windows 元件**，然後選取 **Microsoft 使用者體驗虛擬化**>。</span><span class="sxs-lookup"><span data-stu-id="3bf46-205">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="3bf46-206">選取要編輯的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-206">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="3bf46-207">設定使用者目標群組策略設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-207">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="3bf46-208">使用網域控制站電腦上 Microsoft 桌面優化套件 (MDOP) 中的群組原則管理主控台 (GPMC) 或進位群組原則管理 (AGPM) 工具來管理 UE-V 的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-208">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="3bf46-209">流覽至 **[使用者組**配置>、選取 [ **策略**、 **選取系統管理範本**、按一下 **Windows 元件**，然後選取 Microsoft **使用者體驗虛擬化**。」。</span><span class="sxs-lookup"><span data-stu-id="3bf46-209">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="3bf46-210">選取已編輯的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-210">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="3bf46-211">UE-V Agent 會使用下列優先順序順序來決定同步處理。</span><span class="sxs-lookup"><span data-stu-id="3bf46-211">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="3bf46-212">UE-V 設定優先順序順序</span><span class="sxs-lookup"><span data-stu-id="3bf46-212">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="3bf46-213">由群組原則設定管理的使用者目標設定 - 這些設定設定會依據群組原則儲存在登錄金鑰中，位於 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 下的群組原則。</span><span class="sxs-lookup"><span data-stu-id="3bf46-213">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="3bf46-214">由群組原則設定管理的電腦目標設定 - 這些設定設定會依據群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ，</span><span class="sxs-lookup"><span data-stu-id="3bf46-214">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="3bf46-215">目前使用者使用 Windows PowerShell 或 Windows 管理工具 (WMI) 定義的設定設定 - 這些設定設定是由 UE-V Agent 在此登錄位置下儲存 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ：.</span><span class="sxs-lookup"><span data-stu-id="3bf46-215">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="3bf46-216">使用 Windows PowerShell 或 WMI 為電腦定義的設定設定。</span><span class="sxs-lookup"><span data-stu-id="3bf46-216">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="3bf46-217">這些設定設定是由 UE-V Agent 在此註冊表位置下儲存： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` .</span><span class="sxs-lookup"><span data-stu-id="3bf46-217">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="3bf46-218">**有 UE-V 的建議嗎**？</span><span class="sxs-lookup"><span data-stu-id="3bf46-218">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="3bf46-219">在這裡新增或投票支援 [建議](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。</span><span class="sxs-lookup"><span data-stu-id="3bf46-219">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="3bf46-220">**有 UE-V 問題嗎**？</span><span class="sxs-lookup"><span data-stu-id="3bf46-220">**Got a UE-V issue**?</span></span> <span data-ttu-id="3bf46-221">使用 [UE-V TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="3bf46-221">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3bf46-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="3bf46-222">Related topics</span></span>


[<span data-ttu-id="3bf46-223">管理 UE-V 2.x</span><span class="sxs-lookup"><span data-stu-id="3bf46-223">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="3bf46-224">管理 UE-V 2.x 的設定</span><span class="sxs-lookup"><span data-stu-id="3bf46-224">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
