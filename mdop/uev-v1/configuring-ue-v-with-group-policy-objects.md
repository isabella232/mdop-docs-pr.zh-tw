---
title: 使用群組原則物件來設定 UE-V
description: 使用群組原則物件來設定 UE-V
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811912"
---
# <span data-ttu-id="dadbe-103">使用群組原則物件來設定 UE-V</span><span class="sxs-lookup"><span data-stu-id="dadbe-103">Configuring UE-V with Group Policy Objects</span></span>


<span data-ttu-id="dadbe-104">部分 Microsoft 使用者體驗虛擬化（UE-V）群組原則設定可以為電腦定義，而其他人可以為使用者定義。</span><span class="sxs-lookup"><span data-stu-id="dadbe-104">Some Microsoft User Experience Virtualization (UE-V) Group Policy settings can be defined for computers and others can be defined for users.</span></span> <span data-ttu-id="dadbe-105">UE-V agent 設定原則設定可以針對電腦或使用者進行定義。</span><span class="sxs-lookup"><span data-stu-id="dadbe-105">UE-V agent configuration policy settings can be defined for computers or users.</span></span> <span data-ttu-id="dadbe-106">如需如何安裝 UE-V 群組原則 ADMX 檔案的相關資訊，請參閱[安裝 Ue-v 群組原則 Admx 範本](installing-the-ue-v-group-policy-admx-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="dadbe-106">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V Group Policy ADMX Templates](installing-the-ue-v-group-policy-admx-templates.md).</span></span>

<span data-ttu-id="dadbe-107">您可以針對 UE-V 設定下列原則設定：</span><span class="sxs-lookup"><span data-stu-id="dadbe-107">The following policy settings can be configured for UE-V:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="dadbe-108">原則設定名稱</span><span class="sxs-lookup"><span data-stu-id="dadbe-108">Policy setting name</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="dadbe-109">Target</span><span class="sxs-lookup"><span data-stu-id="dadbe-109">Target</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="dadbe-110">原則設定描述</span><span class="sxs-lookup"><span data-stu-id="dadbe-110">Policy setting description</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="dadbe-111">設定選項</span><span class="sxs-lookup"><span data-stu-id="dadbe-111">Configuration options</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dadbe-112">使用使用者體驗虛擬化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="dadbe-112">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-113">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-114">此原則設定可讓您啟用或停用使用者體驗虛擬化（UE-V）。</span><span class="sxs-lookup"><span data-stu-id="dadbe-114">This policy setting allows you to enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-115">啟用或停用此原則設定。</span><span class="sxs-lookup"><span data-stu-id="dadbe-115">Enable or disable this policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dadbe-116">設定儲存路徑</span><span class="sxs-lookup"><span data-stu-id="dadbe-116">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-117">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-117">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-118">此原則設定會配置將儲存使用者設定的位置。</span><span class="sxs-lookup"><span data-stu-id="dadbe-118">This policy setting configures where the user settings will be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-119">提供通用命名慣例（UNC）路徑和變數，例如 \Server\SettingsShare%username%。</span><span class="sxs-lookup"><span data-stu-id="dadbe-119">Provide a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dadbe-120">設定範本目錄路徑</span><span class="sxs-lookup"><span data-stu-id="dadbe-120">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-121">僅限電腦</span><span class="sxs-lookup"><span data-stu-id="dadbe-121">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-122">此原則設定會配置自訂設定位置範本的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="dadbe-122">This policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="dadbe-123">此原則設定也會配置是否要使用該目錄來取代與 UE-V agent 一起安裝的預設 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="dadbe-123">This policy setting also configures whether the catalog will be used to replace the default Microsoft templates that are installed with the UE-V agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-124">提供通用命名慣例（UNC）路徑，例如 \Server\TemplateShare 或電腦上的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="dadbe-124">Provide a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p></p>
<p><span data-ttu-id="dadbe-125">選取要取代預設 Microsoft 範本的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-125">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dadbe-126">請勿使用離線檔案</span><span class="sxs-lookup"><span data-stu-id="dadbe-126">Do not use Offline Files</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-127">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-127">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-128">此原則設定可讓您設定 UE-V 是否會使用 Windows 離線檔案功能。</span><span class="sxs-lookup"><span data-stu-id="dadbe-128">This policy setting allows you to configure whether UE-V will use the Windows Offline Files feature.</span></span> <span data-ttu-id="dadbe-129">此原則設定也可讓您在 [匯入使用者設定] 延遲時啟用通知。</span><span class="sxs-lookup"><span data-stu-id="dadbe-129">This policy setting also allows you to enable notification to occur when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-130">若要設定 UE-V Agent 不使用離線檔案，請啟用此設定。</span><span class="sxs-lookup"><span data-stu-id="dadbe-130">To configure the UE-V Agent to not use offline files, enable this setting.</span></span></p>
<p></p>
<p><span data-ttu-id="dadbe-131">指定當設定匯入延遲時，是否應給予通知。</span><span class="sxs-lookup"><span data-stu-id="dadbe-131">Specify if notifications should be given when settings import is delayed.</span></span></p>
<p></p>
<p><span data-ttu-id="dadbe-132">指定通知出現前要等待的時間長度（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="dadbe-132">Specify the length of time in seconds to wait before the notification appears.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dadbe-133">同步處理超時</span><span class="sxs-lookup"><span data-stu-id="dadbe-133">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-134">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-134">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-135">此原則設定會設定在從遠端設定位置檢索使用者設定時，電腦在超時之前等待的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="dadbe-135">This policy setting configures the number of milliseconds that the computer waits before a timeout when retrieving user settings from the remote settings location.</span></span> <span data-ttu-id="dadbe-136">如果 [遠端儲存位置] 無法使用，應用程式啟動會延遲數毫秒。</span><span class="sxs-lookup"><span data-stu-id="dadbe-136">If the remote storage location is unavailable, the application launch is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-137">指定最佳同步處理超時（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="dadbe-137">Specify the preferred synchronization timeout in milliseconds.</span></span> <span data-ttu-id="dadbe-138">2000毫秒的預設值。</span><span class="sxs-lookup"><span data-stu-id="dadbe-138">The default value of 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dadbe-139">套件大小警告閾值</span><span class="sxs-lookup"><span data-stu-id="dadbe-139">Package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-140">電腦和使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-140">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-141">此原則設定可讓您設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="dadbe-141">This policy setting allows you to configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-142">已指定設定套件大小的喜好閾值（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="dadbe-142">Specified the preferred threshold for settings package sizes in kilobytes.</span></span></p>
<p><span data-ttu-id="dadbe-143">根據預設，UE-V agent 沒有套件檔案大小閾值。</span><span class="sxs-lookup"><span data-stu-id="dadbe-143">By default, the UE-V agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dadbe-144">漫遊應用程式設定</span><span class="sxs-lookup"><span data-stu-id="dadbe-144">Roaming Application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-145">僅限使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-145">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-146">此原則設定會配置應用程式的使用者設定的漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-146">This policy setting configures the roaming of user settings of applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-147">選取哪些 Windows 設定將在電腦之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-147">Select which Windows settings will roam between computers.</span></span></p>
<p><span data-ttu-id="dadbe-148">根據預設，由 UE-V 提供的應用程式的使用者設定範本是在電腦之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-148">By default, the user settings of applications with settings template provided by UE-V are roamed between computers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dadbe-149">漫遊 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="dadbe-149">Roaming Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-150">僅限使用者</span><span class="sxs-lookup"><span data-stu-id="dadbe-150">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-151">此原則設定會配置 Windows 設定的漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-151">This policy setting configures the roaming of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="dadbe-152">選取哪些應用程式將在電腦之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-152">Select which applications will roam between computers.</span></span></p>
<p><span data-ttu-id="dadbe-153">根據預設，Windows 主題是在相同作業系統版本的電腦之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-153">By default, Windows themes are roamed between computers of the same operating system version.</span></span> <span data-ttu-id="dadbe-154">Windows 桌面設定和 [輕鬆存取] 設定不是漫遊。</span><span class="sxs-lookup"><span data-stu-id="dadbe-154">Windows desktop settings and Ease of Access settings are not roamed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="dadbe-155">設定以電腦為目標的原則</span><span class="sxs-lookup"><span data-stu-id="dadbe-155">To configure computer-targeted policies</span></span>**

1.  <span data-ttu-id="dadbe-156">在管理 UE-V 電腦之群組原則的網網域控制站電腦上，使用 [群組原則管理主控台] （GPMC）或 [高級群組原則管理] （AGPM）。</span><span class="sxs-lookup"><span data-stu-id="dadbe-156">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the domain controller computer that manages Group Policy for UE-V computers.</span></span> <span data-ttu-id="dadbe-157">流覽至 [**電腦**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。</span><span class="sxs-lookup"><span data-stu-id="dadbe-157">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="dadbe-158">選取要編輯的原則設定。</span><span class="sxs-lookup"><span data-stu-id="dadbe-158">Select the policy setting to be edited.</span></span>

**<span data-ttu-id="dadbe-159">設定以使用者為目標的原則</span><span class="sxs-lookup"><span data-stu-id="dadbe-159">To configure user-targeted policies</span></span>**

1.  <span data-ttu-id="dadbe-160">在管理 UE-V 的群組原則之網網域控制站電腦上，使用 [群組原則管理主控台（GPMC）] 或 [高級群組原則管理（AGPM）] 工具，在 Microsoft 桌面優化套件（MDOP）中進行。</span><span class="sxs-lookup"><span data-stu-id="dadbe-160">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer that manages Group Policy for UE-V.</span></span> <span data-ttu-id="dadbe-161">流覽至 [**使用者**設定]，選取 [**原則**]，選取 [系統**管理範本**]，按一下 [ **Windows 元件**]，然後選取 [ **Microsoft 使用者體驗虛擬化**]。</span><span class="sxs-lookup"><span data-stu-id="dadbe-161">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="dadbe-162">選取已編輯的原則設定。</span><span class="sxs-lookup"><span data-stu-id="dadbe-162">Select the policy setting edited.</span></span>

<span data-ttu-id="dadbe-163">UE-V agent 會使用下列優先順序順序來判斷同步處理。</span><span class="sxs-lookup"><span data-stu-id="dadbe-163">The UE-V agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="dadbe-164">UE-V 設定的優先順序順序</span><span class="sxs-lookup"><span data-stu-id="dadbe-164">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="dadbe-165">由群組原則管理的使用者設定目標設定-這些設定設定會依群組原則儲存在登錄機碼中 `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="dadbe-165">User-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="dadbe-166">由群組原則管理的由電腦設定目標的設定-這些設定設定會依群組原則儲存在登錄機碼中 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="dadbe-166">Computer-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="dadbe-167">使用 PowerShell 或 WMI 的目前使用者所定義的配置設定，由 UE-V agent 儲存在此登錄位置： `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="dadbe-167">Configuration settings defined by the current user using PowerShell or WMI - These configuration settings are stored by the UE-V agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="dadbe-168">使用 PowerShell 或 WMI 為電腦定義的配置設定。</span><span class="sxs-lookup"><span data-stu-id="dadbe-168">Configuration settings defined for the computer using PowerShell or WMI.</span></span> <span data-ttu-id="dadbe-169">這些設定的設定是由 UE-V agent 儲存在 `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="dadbe-169">These configuration settings are stored by the UE-V agent under the `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration`.</span></span>

## <span data-ttu-id="dadbe-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="dadbe-170">Related topics</span></span>


[<span data-ttu-id="dadbe-171">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="dadbe-171">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="dadbe-172">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="dadbe-172">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





