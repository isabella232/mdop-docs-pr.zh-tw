---
title: 使用群組原則物件設定 UE-V 2. x
description: 使用群組原則物件設定 UE-V 2. x
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
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810545"
---
# <span data-ttu-id="a3175-103">使用群組原則物件設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="a3175-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="a3175-104">部分 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 群組原則設定可為電腦定義，而其他群組原則設定則可以為使用者定義。</span><span class="sxs-lookup"><span data-stu-id="a3175-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="a3175-105">如需如何安裝 UE-V 群組原則 ADMX 檔案的相關資訊，請參閱[安裝 ue-v 2 群組原則 Admx 範本](https://technet.microsoft.com/library/dn458891.aspx#admx)。</span><span class="sxs-lookup"><span data-stu-id="a3175-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="a3175-106">您可以針對 UE-V 設定下列原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="a3175-107">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="a3175-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3175-108">群組原則設定名稱</span><span class="sxs-lookup"><span data-stu-id="a3175-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="a3175-109">Target</span><span class="sxs-lookup"><span data-stu-id="a3175-109">Target</span></span></th>
<th align="left"><span data-ttu-id="a3175-110">群組原則設定描述</span><span class="sxs-lookup"><span data-stu-id="a3175-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="a3175-111">設定選項</span><span class="sxs-lookup"><span data-stu-id="a3175-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-112">聯繫 IT 連結文字</span><span class="sxs-lookup"><span data-stu-id="a3175-112">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-113">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="a3175-113">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-114">這個群組原則設定會指定公司設定中心中的 [連絡人 IT URL] 超連結的文字。</span><span class="sxs-lookup"><span data-stu-id="a3175-114">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-115">如果您啟用此群組原則設定，[公司設定中心] 會在連結中顯示指定的文字，以取得連絡人的連絡人 URL。</span><span class="sxs-lookup"><span data-stu-id="a3175-115">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-116">聯繫 IT URL</span><span class="sxs-lookup"><span data-stu-id="a3175-116">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-117">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="a3175-117">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-118">這個群組原則設定會指定 [公司設定] 中心中的 [連絡人 IT] 連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="a3175-118">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-119">如果您啟用此設定，公司設定中心就會與它相關的文字連結至指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="a3175-119">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="a3175-120">連結可以是任何標準通訊協定，例如 HTTP 或 mailto。</span><span class="sxs-lookup"><span data-stu-id="a3175-120">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-121">請勿使用同步處理提供者</span><span class="sxs-lookup"><span data-stu-id="a3175-121">Do not use the sync provider</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-122">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-122">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-123">您可以使用此群組原則設定，設定 UE-V 是否使用同步處理提供程式功能。</span><span class="sxs-lookup"><span data-stu-id="a3175-123">By using this Group Policy setting, you can configure whether UE-V uses the sync provider feature.</span></span> <span data-ttu-id="a3175-124">您也可以使用此原則設定，讓您在使用者的匯入設定延遲時，顯示通知。</span><span class="sxs-lookup"><span data-stu-id="a3175-124">This policy setting also lets you enable notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-125">啟用此設定以設定 UE-V Agent 不使用同步處理提供者。</span><span class="sxs-lookup"><span data-stu-id="a3175-125">Enable this setting to configure the UE-V Agent not to use the sync provider.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-126">第一次使用通知</span><span class="sxs-lookup"><span data-stu-id="a3175-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-127">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="a3175-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-128">這個群組原則設定可讓您在 UE-V 時顯示的通知區域中的通知</span><span class="sxs-lookup"><span data-stu-id="a3175-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="a3175-129">代理程式第一次執行。</span><span class="sxs-lookup"><span data-stu-id="a3175-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-130">預設值為 [已啟用]。</span><span class="sxs-lookup"><span data-stu-id="a3175-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-131">漫遊 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="a3175-131">Roam Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-132">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-133">這個群組原則設定會配置 Windows 設定的同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3175-133">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-134">選取 [在電腦之間同步處理的 Windows 設定]。</span><span class="sxs-lookup"><span data-stu-id="a3175-134">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="a3175-135">根據預設，Windows 主題、[桌面設定] 和 [輕鬆存取設定] 會在相同作業系統版本的電腦之間同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-135">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-136">設定套件大小警告閾值</span><span class="sxs-lookup"><span data-stu-id="a3175-136">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-137">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-137">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-138">此群組原則設定可讓您設定 UE-V Agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="a3175-138">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-139">指定設定套件大小的喜好閾值（KB）。</span><span class="sxs-lookup"><span data-stu-id="a3175-139">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="a3175-140">根據預設，UE-V Agent 沒有套件檔案大小閾值。</span><span class="sxs-lookup"><span data-stu-id="a3175-140">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-141">設定儲存路徑</span><span class="sxs-lookup"><span data-stu-id="a3175-141">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-142">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-142">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-143">這個群組原則設定會配置要儲存使用者設定的位置。</span><span class="sxs-lookup"><span data-stu-id="a3175-143">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-144">輸入通用命名慣例（UNC）路徑和變數，例如 \Server\SettingsShare%username%。</span><span class="sxs-lookup"><span data-stu-id="a3175-144">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-145">設定範本目錄路徑</span><span class="sxs-lookup"><span data-stu-id="a3175-145">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-146">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="a3175-146">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-147">這個群組原則設定會配置自訂設定位置範本的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="a3175-147">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="a3175-148">此原則設定也會配置是否要使用目錄來取代與 UE-V Agent 一起安裝的預設 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="a3175-148">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-149">在電腦上輸入通用命名慣例（UNC）路徑，例如 \Server\TemplateShare 或資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="a3175-149">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="a3175-150">選取要取代預設 Microsoft 範本的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a3175-150">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-151">在計量付費連線上同步處理設定</span><span class="sxs-lookup"><span data-stu-id="a3175-151">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-152">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-152">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-153">此群組原則設定會定義 UE-V 是否要同步處理通過計量付費連線的設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-153">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-154">根據預設，UE-V Agent 不會在計量付費連線上同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-154">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-155">即使在漫遊時也能在計量付費連線上同步處理設定</span><span class="sxs-lookup"><span data-stu-id="a3175-155">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-156">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-156">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-157">這個群組原則設定會定義 UE-V 是否與家用提供者網路以外的計量付費連線同步處理設定，例如，當資料連線處於漫遊模式時。</span><span class="sxs-lookup"><span data-stu-id="a3175-157">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-158">根據預設，UE-V 不會在處於漫遊模式時，透過計量付費連線同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-158">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-159">同步處理超時</span><span class="sxs-lookup"><span data-stu-id="a3175-159">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-160">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-160">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-161">這個群組原則設定會設定電腦從遠端設定位置中檢索使用者設定時，等待超時的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="a3175-161">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="a3175-162">如果遠端儲存位置無法使用，且使用者不使用同步處理提供者，應用程式的啟動會延遲數毫秒。</span><span class="sxs-lookup"><span data-stu-id="a3175-162">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-163">指定最佳同步處理超時（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="a3175-163">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="a3175-164">預設值為2000毫秒。</span><span class="sxs-lookup"><span data-stu-id="a3175-164">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-165">[工作列] 圖示</span><span class="sxs-lookup"><span data-stu-id="a3175-165">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-166">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="a3175-166">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-167">此群組原則設定會啟用使用者體驗虛擬化（UE-V）工作列圖示。</span><span class="sxs-lookup"><span data-stu-id="a3175-167">This Group Policy setting enables the User Experience Virtualization (UE-V) tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-168">預設值為 [已啟用]。</span><span class="sxs-lookup"><span data-stu-id="a3175-168">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-169">使用使用者體驗虛擬化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="a3175-169">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-170">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-170">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-171">這個 [群組原則] 設定可讓您啟用或停用使用者體驗虛擬化（UE-V）。</span><span class="sxs-lookup"><span data-stu-id="a3175-171">This Group Policy setting lets you enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-172">啟用或停用此群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-172">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a3175-173">**記事** 此外，有許多桌面應用程式和 Windows 應用程式都可以使用群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-173">**Note** In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="a3175-174">您可以使用這些設定來啟用或停用特定應用程式的設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3175-174">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="a3175-175">Windows 應用程式群組原則設定</span><span class="sxs-lookup"><span data-stu-id="a3175-175">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3175-176">群組原則設定名稱</span><span class="sxs-lookup"><span data-stu-id="a3175-176">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="a3175-177">Target</span><span class="sxs-lookup"><span data-stu-id="a3175-177">Target</span></span></th>
<th align="left"><span data-ttu-id="a3175-178">群組原則設定描述</span><span class="sxs-lookup"><span data-stu-id="a3175-178">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="a3175-179">設定選項</span><span class="sxs-lookup"><span data-stu-id="a3175-179">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-180">不要同步處理 Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="a3175-180">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-181">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-181">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-182">此群組原則設定會定義 UE-V Agent 是否同步處理 Windows 應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-182">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-183">預設是同步處理 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3175-183">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3175-184">Windows 應用程式清單</span><span class="sxs-lookup"><span data-stu-id="a3175-184">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-185">電腦與使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-185">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-186">此設定會列出 Windows 應用程式的家庭套件名稱，並明確指出 UE-V 是否要同步處理該 app 的設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-186">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-187">您可以使用這個設定來指定 app 的設定永遠不會由 UE-V 進行同步處理，即使已同步處理所有其他 Windows 應用程式的設定也一樣。</span><span class="sxs-lookup"><span data-stu-id="a3175-187">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3175-188">同步未列出的 Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="a3175-188">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-189">電腦與使用者</span><span class="sxs-lookup"><span data-stu-id="a3175-189">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-190">這個群組原則設定會定義 windows 應用程式的 UE-V Agent 的預設設定同步處理行為，該 app 未明確列出在 Windows 應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="a3175-190">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3175-191">根據預設，UE-V Agent 只會同步處理包含在 Windows 應用程式清單中的那些 Windows 應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-191">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a3175-192">如需有關同步處理 Windows 應用程式的詳細資訊，請參閱[Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="a3175-192">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="a3175-193">設定以電腦為目標的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="a3175-193">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="a3175-194">在電腦上使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM），作為網網域控制站，以管理 UE-V 電腦的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-194">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="a3175-195">流覽至 [**電腦**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。</span><span class="sxs-lookup"><span data-stu-id="a3175-195">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="a3175-196">選取要編輯的 [群組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-196">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="a3175-197">設定以使用者為目標的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="a3175-197">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="a3175-198">在網網域控制站電腦上的 Microsoft 桌面優化套件（MDOP）中，使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）工具來管理 UE-V 的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-198">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="a3175-199">流覽至 [**使用者**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。</span><span class="sxs-lookup"><span data-stu-id="a3175-199">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="a3175-200">選取已編輯的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-200">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="a3175-201">UE-V Agent 會使用下列優先順序順序來判斷同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3175-201">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="a3175-202">UE-V 設定的優先順序順序</span><span class="sxs-lookup"><span data-stu-id="a3175-202">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="a3175-203">由群組原則設定所管理的使用者設定目標設定-這些設定的設定會依群組原則儲存在登錄機碼中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="a3175-203">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="a3175-204">由群組原則設定所管理的電腦設定目標設定-這些設定的設定會依群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="a3175-204">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="a3175-205">由目前使用者使用 Windows PowerShell 或 Windows 管理工具（WMI）所定義的設定設定，這些設定設定是由 UE-V Agent 儲存在此登錄位置： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="a3175-205">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="a3175-206">使用 Windows PowerShell 或 WMI 為電腦定義的配置設定。</span><span class="sxs-lookup"><span data-stu-id="a3175-206">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="a3175-207">UE-V Agent 會將這些設定設定儲存在此登錄位置： `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="a3175-207">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="a3175-208">**為 ue-v 提供建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a3175-208">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="a3175-209">在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a3175-209">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="a3175-210">是否**有 ue-v 問題**？</span><span class="sxs-lookup"><span data-stu-id="a3175-210">**Got a UE-V issue**?</span></span> <span data-ttu-id="a3175-211">使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="a3175-211">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="a3175-212">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3175-212">Related topics</span></span>


[<span data-ttu-id="a3175-213">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="a3175-213">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="a3175-214">管理 UE-V 2.x 的設定</span><span class="sxs-lookup"><span data-stu-id="a3175-214">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





