---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件
description: 使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件
author: dansimp
ms.assetid: 56e6780b-8b2c-4717-91c8-2af63062ab75
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6a709d2c66266cf33b8e89ddd905aa0f21eb7dfe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811973"
---
# <span data-ttu-id="2248e-103">使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件</span><span class="sxs-lookup"><span data-stu-id="2248e-103">Managing the UE-V 2.x Agent and Packages with Windows PowerShell and WMI</span></span>


<span data-ttu-id="2248e-104">您可以使用 Windows 管理工具（WMI）和 Windows PowerShell 來管理 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 Agent 設定和同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="2248e-104">You can use Windows Management Instrumentation (WMI) and Windows PowerShell to manage Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent configuration and synchronization behavior.</span></span> <span data-ttu-id="2248e-105">如需 UE-V PowerShell Cmdlet 的完整清單，請參閱[ue-v 2 Cmdlet 參考](https://go.microsoft.com/fwlink/?LinkId=393495)（ https://go.microsoft.com/fwlink/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="2248e-105">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/?LinkId=393495) (https://go.microsoft.com/fwlink/?LinkId=393495).</span></span>

**<span data-ttu-id="2248e-106">使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="2248e-106">To deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="2248e-107">在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="2248e-107">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="2248e-108">注意</span><span class="sxs-lookup"><span data-stu-id="2248e-108">Note</span></span>**  
    <span data-ttu-id="2248e-109">使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="2248e-109">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="2248e-110">Windows Installer 套件、AgentSetupx86.msi 和 AgentSetupx64.msi，可供每個架構使用。</span><span class="sxs-lookup"><span data-stu-id="2248e-110">Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="2248e-111">若要在稍後使用安裝檔案卸載 UE-V Agent，您必須使用相同的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="2248e-111">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="2248e-112">使用下列其中一個 Windows PowerShell 命令來安裝 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="2248e-112">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="2248e-113">使用 Windows PowerShell 來設定 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="2248e-113">To configure the UE-V Agent by using Windows PowerShell</span></span>**

1. <span data-ttu-id="2248e-114">開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="2248e-114">Open a Windows PowerShell window.</span></span> <span data-ttu-id="2248e-115">若要使用 [*電腦*] 參數管理影響電腦所有使用者的電腦設定，請以具有系統管理員許可權的帳戶開啟視窗。</span><span class="sxs-lookup"><span data-stu-id="2248e-115">To manage computer settings that affect all users of the computer by using the *Computer* parameter, open the window with an account that has administrator rights.</span></span>

2. <span data-ttu-id="2248e-116">使用下列 Windows PowerShell 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-116">Use the following Windows PowerShell commands to configure the agent.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="2248e-117">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="2248e-117">Windows PowerShell command</span></span></th>
   <th align="left"><span data-ttu-id="2248e-118">描述</span><span class="sxs-lookup"><span data-stu-id="2248e-118">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="2248e-119">取得有效的 UE-V Agent 設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-119">Gets the effective UE-V Agent settings.</span></span> <span data-ttu-id="2248e-120">[使用者專用] 設定的優先順序高於 [電腦設定]。</span><span class="sxs-lookup"><span data-stu-id="2248e-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="2248e-121">僅取得目前使用者的 UE-V Agent 設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-121">Gets the UE-V Agent settings values for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-122">取得電腦上所有使用者的 UE-V Agent 設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-122">Gets the UE-V Agent configuration settings values for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-123">取得每個設定設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2248e-123">Gets the details for each configuration setting.</span></span> <span data-ttu-id="2248e-124">顯示設定的設定位置，或是否使用預設值。</span><span class="sxs-lookup"><span data-stu-id="2248e-124">Displays where the setting is configured or if it uses the default value.</span></span> <span data-ttu-id="2248e-125">如果目前設定有效，就會顯示。</span><span class="sxs-lookup"><span data-stu-id="2248e-125">Is displayed if the current setting is valid.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-126">設定 [公司設定中心] 中顯示的 [說明] 連結文字。</span><span class="sxs-lookup"><span data-stu-id="2248e-126">Sets the text that is displayed in the Company Settings Center for the help link.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-127">在 [公司設定中心] 中設定 [說明] 連結的連結 URL。</span><span class="sxs-lookup"><span data-stu-id="2248e-127">Sets the URL of the link in the Company Settings Center for the help link.</span></span> <span data-ttu-id="2248e-128">您可以使用任何 URL 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2248e-128">Any URL protocol can be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-129">設定 UE-V Agent 不會同步處理電腦上所有使用者的任何 Windows app。</span><span class="sxs-lookup"><span data-stu-id="2248e-129">Configures the UE-V Agent to not synchronize any Windows apps for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-130">將 UE-V Agent 設定為不同步處理目前電腦使用者的任何 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-130">Configures the UE-V Agent to not synchronize any Windows apps for the current computer user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-131">針對電腦上的所有使用者，將 UE-V Agent 設定為在代理程式第一次執行時顯示通知。</span><span class="sxs-lookup"><span data-stu-id="2248e-131">Configures the UE-V Agent to display notification the first time the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-132">針對電腦上的所有使用者，將 UE-V Agent 設定為在第一次執行代理程式時不顯示通知。</span><span class="sxs-lookup"><span data-stu-id="2248e-132">Configures the UE-V Agent to not display notification the first time that the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-133">當設定同步處理延遲時，會設定 UE-V Agent 通知電腦上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2248e-133">Configures the UE-V Agent to notify all users on the computer when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="2248e-134">使用 <em> DisableSettingsImportNotify </em> 參數來停用通知。</span><span class="sxs-lookup"><span data-stu-id="2248e-134">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-135">將 UE-V Agent 設定為當設定同步處理延遲時通知目前使用者。</span><span class="sxs-lookup"><span data-stu-id="2248e-135">Configures the UE-V Agent to notify the current user when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="2248e-136">使用 <em> DisableSettingsImportNotify </em> 參數來停用通知。</span><span class="sxs-lookup"><span data-stu-id="2248e-136">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-137">針對電腦的所有使用者，設定 UE-V Agent 來同步處理未明確停用 Windows 應用程式清單的所有 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-137">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for all users of the computer.</span></span> <span data-ttu-id="2248e-138">如需詳細資訊，請參閱 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v A.x 設定位置範本中的 UevAppxPackage </a> 。</span><span class="sxs-lookup"><span data-stu-id="2248e-138">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="2248e-139">使用 <em> DisableSyncUnlistedWindows8Apps </em> 參數設定 ue-v Agent，只同步處理 Windows 應用程式清單明確啟用的 windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-139">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-140">針對電腦上目前使用者的 Windows 應用程式清單，設定 UE-V Agent 來同步處理所有未明確停用的 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-140">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for the current user on the computer.</span></span> <span data-ttu-id="2248e-141">如需詳細資訊，請參閱 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v A.x 設定位置範本中的 UevAppxPackage </a> 。</span><span class="sxs-lookup"><span data-stu-id="2248e-141">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="2248e-142">使用 <em> DisableSyncUnlistedWindows8Apps </em> 參數設定 ue-v Agent，只同步處理 Windows 應用程式清單明確啟用的 windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-142">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-143">針對電腦上的所有使用者停用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="2248e-143">Disables UE-V for all the users on the computer.</span></span></p>
   <p><span data-ttu-id="2248e-144">使用 <em> EnableSync </em> 參數來啟用或重新啟用。</span><span class="sxs-lookup"><span data-stu-id="2248e-144">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-145">針對電腦上的目前使用者停用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="2248e-145">Disables UE-V for the current user on the computer.</span></span></p>
   <p><span data-ttu-id="2248e-146">使用 <em> EnableSync </em> 參數來啟用或重新啟用。</span><span class="sxs-lookup"><span data-stu-id="2248e-146">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-147">針對電腦的所有使用者，在通知區域啟用 UE-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="2248e-147">Enables the UE-V icon in the notification area for all users of the computer.</span></span></p>
   <p><span data-ttu-id="2248e-148">使用 <em> DisableTrayIcon </em> 參數來停用圖示。</span><span class="sxs-lookup"><span data-stu-id="2248e-148">Use the <em>DisableTrayIcon</em> parameter to disable the icon.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-149">設定 UE-V agent 在設定套件檔案大小達到電腦上所有使用者的已定義閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="2248e-149">Configures the UE-V agent to report when a settings package file size reaches the defined threshold for all users on the computer.</span></span> <span data-ttu-id="2248e-150">設定閥值套件大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="2248e-150">Sets the threshold package size in bytes.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-151">設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="2248e-151">Configures the UE-V agent to report when a settings package file size reaches the defined threshold.</span></span> <span data-ttu-id="2248e-152">設定目前使用者的套件大小警告閾值。</span><span class="sxs-lookup"><span data-stu-id="2248e-152">Sets the package size warning threshold for the current user.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-153">指定使用者收到電腦所有使用者的通知時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="2248e-153">Specifies the time in seconds before the user is notified for all users of the computer</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-154">指定傳送目前使用者的通知前的時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="2248e-154">Specifies the time in seconds before notification for the current user is sent.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-155">針對電腦的所有使用者定義每電腦設定的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="2248e-155">Defines a per-computer settings storage location for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-156">定義每個使用者的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="2248e-156">Defines a per-user settings storage location.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-157">為電腦的所有使用者設定設定範本的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="2248e-157">Sets the settings template catalog path for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-158">為電腦的所有使用者設定同步處理方法： SyncProvider 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="2248e-158">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-159">為目前的使用者設定同步處理方法： SyncProvider 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="2248e-159">Sets the synchronization method for the current user: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-160">針對電腦的所有使用者設定同步超時時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="2248e-160">Sets the synchronization time-out in milliseconds for all users of the computer</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-161">為目前的使用者設定同步處理超時時間。</span><span class="sxs-lookup"><span data-stu-id="2248e-161">Set the synchronization time-out for the current user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-162">針對電腦上的所有使用者清除指定的設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-162">Clears the specified setting for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-163">僅清除目前使用者的指定設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-163">Clears the specified setting for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-164">將 UE-V 電腦設定匯出為設定遷移檔案。</span><span class="sxs-lookup"><span data-stu-id="2248e-164">Exports the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="2248e-165">副檔名必須是. uev。</span><span class="sxs-lookup"><span data-stu-id="2248e-165">The file name extension must be .uev.</span></span></p>
   <p><span data-ttu-id="2248e-166">這個 <code>Export</code> Cmdlet 會匯出所有可使用電腦參數設定的 Ue-v agent 設定 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="2248e-166">The <code>Export</code> cmdlet exports all UE-V Agent settings that are configurable with the <em>Computer</em> parameter.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="2248e-167">從設定遷移檔案匯入 UE-V 電腦設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-167">Imports the UE-V computer configuration from a settings migration file.</span></span> <span data-ttu-id="2248e-168">副檔名必須是. uev。</span><span class="sxs-lookup"><span data-stu-id="2248e-168">The file name extension must be .uev.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="2248e-169">若要匯出 UE-V 封裝設定並使用 Windows PowerShell 修復 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="2248e-169">To export UE-V package settings and repair UE-V templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="2248e-170">以系統管理員身分開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="2248e-170">Open a Windows PowerShell window as an administrator.</span></span>

2.  <span data-ttu-id="2248e-171">使用下列 Windows PowerShell 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-171">Use the following Windows PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="2248e-172">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="2248e-172">Windows PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="2248e-173">描述</span><span class="sxs-lookup"><span data-stu-id="2248e-173">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2248e-174">Export-UevPackage MicrosoftCalculator6. pkgx</span><span class="sxs-lookup"><span data-stu-id="2248e-174">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2248e-175">從 Microsoft 計算機套件檔案提取設定，並將其轉換成 XML 中的使用者可閱讀格式。</span><span class="sxs-lookup"><span data-stu-id="2248e-175">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2248e-176">修復 UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="2248e-176">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2248e-177">修復 UE-V 設定位置範本的索引。</span><span class="sxs-lookup"><span data-stu-id="2248e-177">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="2248e-178">使用 WMI 來設定 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="2248e-178">To configure the UE-V Agent by using WMI</span></span>**

1.  <span data-ttu-id="2248e-179">使用者體驗虛擬化提供下列一組 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="2248e-179">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="2248e-180">系統管理員可以使用此介面，在命令列設定 UE-V agent，並自動執行一般的配置工作。</span><span class="sxs-lookup"><span data-stu-id="2248e-180">Administrators can use this interface to configure the UE-V agent at the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="2248e-181">使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="2248e-181">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="2248e-182">使用下列 WMI 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="2248e-182">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="2248e-183">描述</span><span class="sxs-lookup"><span data-stu-id="2248e-183">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="2248e-184">顯示作用中 UE-V Agent 設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-184">Displays the active UE-V Agent settings.</span></span> <span data-ttu-id="2248e-185">[使用者專用] 設定的優先順序高於 [電腦設定]。</span><span class="sxs-lookup"><span data-stu-id="2248e-185">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-186">顯示為使用者定義的 UE-V Agent 配置。</span><span class="sxs-lookup"><span data-stu-id="2248e-186">Displays the UE-V Agent configuration that is defined for a user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-187">顯示為電腦定義的 UE-V Agent 配置。</span><span class="sxs-lookup"><span data-stu-id="2248e-187">Displays the UE-V Agent configuration that is defined for a computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-188">顯示每個設定專案的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2248e-188">Displays the details for each configuration item.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><span data-ttu-id="2248e-189">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="2248e-189">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2248e-190">定義每個電腦的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="2248e-190">Defines a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-191">定義每個使用者的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="2248e-191">Defines a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-192">針對電腦的所有使用者設定同步超時時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="2248e-192">Sets the synchronization time-out in milliseconds for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-193">設定 UE-V Agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="2248e-193">Configures the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="2248e-194">針對電腦的所有使用者，設定閾值套件檔案大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="2248e-194">Set the threshold package file size in bytes for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-195">為電腦的所有使用者設定同步處理方法： SyncProvider 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="2248e-195">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-196">若要啟用特定的每電腦設定，請清除該設定，然後使用 <em> $null </em> 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-196">To enable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="2248e-197">針對每位使用者設定使用 UserConfiguration。</span><span class="sxs-lookup"><span data-stu-id="2248e-197">Use UserConfiguration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-198">若要停用特定的每電腦設定，請清除該設定，然後使用 <em> $null </em> 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-198">To disable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="2248e-199">針對每位使用者設定使用 [使用者設定]。</span><span class="sxs-lookup"><span data-stu-id="2248e-199">Use User Configuration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-200">更新特定的每電腦設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-200">Updates a specific per-computer setting.</span></span> <span data-ttu-id="2248e-201">若要清除此設定，請使用 <em> $null </em> 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-201">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code><span data-ttu-id="2248e-202">$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</span><span class="sxs-lookup"><span data-stu-id="2248e-202">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-203">針對電腦的所有使用者更新特定的每個使用者設定。</span><span class="sxs-lookup"><span data-stu-id="2248e-203">Updates a specific per-user setting for all users of the computer.</span></span> <span data-ttu-id="2248e-204">若要清除此設定，請使用 <em> $null </em> 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="2248e-204">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**<span data-ttu-id="2248e-205">若要匯出 UE-V 封裝設定並使用 WMI 修復 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="2248e-205">To export UE-V package settings and repair UE-V templates by using WMI</span></span>**

1.  <span data-ttu-id="2248e-206">UE-V 提供下列幾組 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="2248e-206">UE-V provides the following set of WMI commands.</span></span> <span data-ttu-id="2248e-207">系統管理員可以使用此介面匯出套件或修復 UE-V 範本。</span><span class="sxs-lookup"><span data-stu-id="2248e-207">Administrators can use this interface to export a package or repair UE-V templates.</span></span>

2.  <span data-ttu-id="2248e-208">使用下列 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="2248e-208">Use the following WMI commands.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="2248e-209">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="2248e-209">WMI command</span></span></th>
    <th align="left"><span data-ttu-id="2248e-210">描述</span><span class="sxs-lookup"><span data-stu-id="2248e-210">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-211">從套件檔案提取設定，並將其轉換成 XML 中的使用者可閱讀格式。</span><span class="sxs-lookup"><span data-stu-id="2248e-211">Extracts the settings from a package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p><span data-ttu-id="2248e-212">修復 UE-V 設定位置範本的索引。</span><span class="sxs-lookup"><span data-stu-id="2248e-212">Repairs the index of the UE-V settings location templates.</span></span> <span data-ttu-id="2248e-213">必須以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="2248e-213">Must be run as administrator.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## <span data-ttu-id="2248e-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="2248e-214">Related topics</span></span>


[<span data-ttu-id="2248e-215">使用 Windows PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="2248e-215">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="2248e-216">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="2248e-216">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









