---
title: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件
description: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件
author: dansimp
ms.assetid: c8989b01-1769-4e69-82b1-4aadb261d2d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79268e3384aaaf08bdd4e9b92d74b039ce96596a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802161"
---
# <span data-ttu-id="36c9e-103">使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件</span><span class="sxs-lookup"><span data-stu-id="36c9e-103">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>


<span data-ttu-id="36c9e-104">您可以使用 WMI 和 PowerShell 來管理 Microsoft 使用者體驗虛擬化（UE-V） Agent 設定和同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="36c9e-104">You can use WMI and PowerShell to manage Microsoft User Experience Virtualization (UE-V) Agent configuration and synchronization behavior.</span></span>

**<span data-ttu-id="36c9e-105">如何使用 PowerShell 部署 UE-V agent</span><span class="sxs-lookup"><span data-stu-id="36c9e-105">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="36c9e-106">在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="36c9e-106">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="36c9e-107">注意</span><span class="sxs-lookup"><span data-stu-id="36c9e-107">Note</span></span>**  
    <span data-ttu-id="36c9e-108">使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="36c9e-108">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="36c9e-109">Windows Installer 檔案版本、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。</span><span class="sxs-lookup"><span data-stu-id="36c9e-109">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="36c9e-110">若要在稍後使用安裝檔來卸載 UE-V Agent，您必須使用相同的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="36c9e-110">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="36c9e-111">使用下列其中一個 PowerShell 命令來安裝代理程式。</span><span class="sxs-lookup"><span data-stu-id="36c9e-111">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="36c9e-112">如何使用 PowerShell 設定 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="36c9e-112">How to configure the UE-V Agent with PowerShell</span></span>**

1.  <span data-ttu-id="36c9e-113">使用具有系統管理員許可權的帳戶來開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="36c9e-113">Use an account with administrator rights to open a PowerShell window.</span></span> <span data-ttu-id="36c9e-114">使用下列命令匯入 UE-V PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="36c9e-114">Import the UE-V PowerShell module by using the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="36c9e-115">使用下列 PowerShell 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="36c9e-115">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36c9e-116">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="36c9e-116">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="36c9e-117">描述</span><span class="sxs-lookup"><span data-stu-id="36c9e-117">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-118">UevConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-118">Get-UevConfiguration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-119">查看有效的 UE-V agent 設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-119">View the effective UE-V agent settings.</span></span> <span data-ttu-id="36c9e-120">[使用者專用] 設定的優先順序高於 [電腦設定]。</span><span class="sxs-lookup"><span data-stu-id="36c9e-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-121">UevConfiguration-CurrentComputerUser</span><span class="sxs-lookup"><span data-stu-id="36c9e-121">Get-UevConfiguration - CurrentComputerUser</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-122">僅針對目前的使用者，查看 UE-V agent 設定值。</span><span class="sxs-lookup"><span data-stu-id="36c9e-122">View the UE-V agent settings values for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-123">UevConfiguration-電腦</span><span class="sxs-lookup"><span data-stu-id="36c9e-123">Get-UevConfiguration -Computer</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-124">針對電腦上的所有使用者，查看 UE-V agent 設定的值。</span><span class="sxs-lookup"><span data-stu-id="36c9e-124">View the UE-V agent configuration settings values for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-125">UevConfiguration-電腦-SettingsStoragePath &lt; 路徑至 _settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-125">Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-126">定義每個電腦的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="36c9e-126">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-127">UevConfiguration-CurrentComputerUser-SettingsStoragePath &lt; 路徑至 _settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-127">Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-128">定義每個使用者的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="36c9e-128">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-129">Set-UevConfiguration-電腦-SyncTimeoutInMilliseconds &lt; 超時（毫秒）&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-129">Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-130">設定同步處理超時值（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="36c9e-130">Set the synchronization timeout in milliseconds</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-131">UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds 超時（ &lt; 以毫秒為單位）&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-131">Set-UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-132">設定目前使用者的同步處理超時。</span><span class="sxs-lookup"><span data-stu-id="36c9e-132">Set the synchronization timeout for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-133">UevConfiguration-電腦-MaxPackageSizeInBytes 大小（ &lt; 以位元組為單位）&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-133">Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-134">設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="36c9e-134">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="36c9e-135">設定閥值套件大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="36c9e-135">Set the threshold package size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-136">UevConfiguration-CurrentComputerUser-MaxPackageSizeInBytes 大小（ &lt; 以位元組為單位）&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-136">Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-137">設定目前使用者的套件大小警告閾值。</span><span class="sxs-lookup"><span data-stu-id="36c9e-137">Set the package size warning threshold for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-138">UevConfiguration –電腦– SettingsTemplateCatalogPath &lt; 路徑至目錄&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-138">Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-139">設定 [設定] 範本的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="36c9e-139">Set the settings template catalog path.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-140">UevConfiguration-電腦-SyncMethod 同步處理 &lt; 方法&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-140">Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-141">設定同步處理方法： [OfflineFiles] 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="36c9e-141">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-142">UevConfiguration-CurrentComputerUser-SyncMethod 同步處理 &lt; 方法&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-142">Set-UevConfiguration -CurrentComputerUser -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-143">為目前的使用者設定同步處理方法： OfflineFiles 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="36c9e-143">Set the synchronization method for the current user: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-144">UEVConfiguration-電腦– EnableSettingsImportNotify</span><span class="sxs-lookup"><span data-stu-id="36c9e-144">Set-UEVConfiguration -Computer –EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-145">當使用者的 [匯入] 設定延遲時，啟用通知。</span><span class="sxs-lookup"><span data-stu-id="36c9e-145">Enable notification to occur when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="36c9e-146">使用– DisableSettingsImportNotify 停用通知。</span><span class="sxs-lookup"><span data-stu-id="36c9e-146">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-147">Set-UEVConfiguration-CurrentComputerUser-EnableSettingsImportNotify</span><span class="sxs-lookup"><span data-stu-id="36c9e-147">Set-UEVConfiguration - CurrentComputerUser -EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-148">當使用者的 [匯入] 設定為延遲時，啟用目前使用者的通知。</span><span class="sxs-lookup"><span data-stu-id="36c9e-148">Enable notification for the current user when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="36c9e-149">使用– DisableSettingsImportNotify 停用通知。</span><span class="sxs-lookup"><span data-stu-id="36c9e-149">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-150">UEVConfiguration-電腦-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="36c9e-150">Set-UEVConfiguration -Computer -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-151">指定通知使用者前的時間（以秒為單位）</span><span class="sxs-lookup"><span data-stu-id="36c9e-151">Specify the time in seconds before the user is notified</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-152">Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="36c9e-152">Set-UEVConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-153">指定目前使用者的通知前的時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="36c9e-153">Specify the time in seconds before notification for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-154">UevConfiguration –電腦– DisableSync</span><span class="sxs-lookup"><span data-stu-id="36c9e-154">Set-UevConfiguration –Computer –DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-155">針對電腦上的所有使用者停用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="36c9e-155">Disable UE-V for all the users on the computer.</span></span></p>
    <p><span data-ttu-id="36c9e-156">使用– EnableSync 以啟用或重新啟用。</span><span class="sxs-lookup"><span data-stu-id="36c9e-156">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-157">UevConfiguration – CurrentComputerUser-DisableSync</span><span class="sxs-lookup"><span data-stu-id="36c9e-157">Set-UevConfiguration –CurrentComputerUser -DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-158">針對電腦上的目前使用者停用 UE-V。</span><span class="sxs-lookup"><span data-stu-id="36c9e-158">Disable UE-V for the current user on the computer.</span></span></p>
    <p><span data-ttu-id="36c9e-159">使用– EnableSync 以啟用或重新啟用。</span><span class="sxs-lookup"><span data-stu-id="36c9e-159">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-160">UevConfiguration –電腦 &lt; 設定名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-160">Clear-UevConfiguration –Computer -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-161">針對電腦上的所有使用者，清除特定設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-161">Clear a specific setting for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-162">UevConfiguration – CurrentComputerUser- &lt; 設定名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-162">Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-163">請清除目前使用者的特定設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-163">Clear a specific setting for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-164">Export-UevConfiguration &lt; 設定遷移檔&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-164">Export-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-165">將 UE-V 電腦設定匯出至設定遷移檔案。</span><span class="sxs-lookup"><span data-stu-id="36c9e-165">Export the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="36c9e-166">檔案副檔名必須是 ". uev"。</span><span class="sxs-lookup"><span data-stu-id="36c9e-166">The extension of the file must be “.uev”.</span></span></p>
    <p><span data-ttu-id="36c9e-167">Export Cmdlet 會匯出所有可使用-電腦參數設定的 UE-V agent 設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-167">The export cmdlet exports all UE-V agent settings that are configurable with the -computer parameter.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-168">匯入-UevConfiguration &lt; 設定遷移檔&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-168">Import-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-169">從設定遷移檔案（uev 檔案）匯入 UE-V 電腦設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-169">Import the UE-V computer configuration from a settings migration file (.uev file).</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="36c9e-170">如何使用 PowerShell 匯出 UE-V 封裝設定及修復 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="36c9e-170">How to export UE-V package settings and repair UE-V templates with PowerShell</span></span>**

1.  <span data-ttu-id="36c9e-171">以系統管理員身分開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="36c9e-171">Open a PowerShell window as an Administrator.</span></span> <span data-ttu-id="36c9e-172">使用下列命令匯入 UE-V PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="36c9e-172">Import the UE-V PowerShell module with the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="36c9e-173">使用下列 PowerShell 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="36c9e-173">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36c9e-174">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="36c9e-174">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="36c9e-175">描述</span><span class="sxs-lookup"><span data-stu-id="36c9e-175">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-176">Export-UevPackage MicrosoftCalculator6. pkgx</span><span class="sxs-lookup"><span data-stu-id="36c9e-176">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-177">從 Microsoft 計算機套件檔案提取設定，並將其轉換成 XML 中的使用者可閱讀格式。</span><span class="sxs-lookup"><span data-stu-id="36c9e-177">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-178">修復 UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="36c9e-178">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-179">修復 UE-V 設定位置範本的索引。</span><span class="sxs-lookup"><span data-stu-id="36c9e-179">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="36c9e-180">如何設定 UE-V Agent 與 WMI</span><span class="sxs-lookup"><span data-stu-id="36c9e-180">How to configure the UE-V Agent with WMI</span></span>**

1.  <span data-ttu-id="36c9e-181">使用者體驗虛擬化提供下列一組 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="36c9e-181">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="36c9e-182">系統管理員可以使用此介面，從命令列設定 UE-V agent，並自動執行一般的配置工作。</span><span class="sxs-lookup"><span data-stu-id="36c9e-182">Administrators can use this interface to configure the UE-V agent from the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="36c9e-183">使用具有系統管理員許可權的帳戶來開啟 PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="36c9e-183">Use an account with administrator rights to open a PowerShell window.</span></span>

2.  <span data-ttu-id="36c9e-184">使用下列 WMI 命令來設定代理程式。</span><span class="sxs-lookup"><span data-stu-id="36c9e-184">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="36c9e-185">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="36c9e-185">PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="36c9e-186">描述</span><span class="sxs-lookup"><span data-stu-id="36c9e-186">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-187">WmiObject-命名空間 root\Microsoft\UEV 設定</span><span class="sxs-lookup"><span data-stu-id="36c9e-187">Get-WmiObject -Namespace root\Microsoft\UEV Configuration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-188">查看活動的 UE-V agent 設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-188">View the active UE-V agent settings.</span></span> <span data-ttu-id="36c9e-189">[使用者專用] 設定的優先順序高於 [電腦設定]。</span><span class="sxs-lookup"><span data-stu-id="36c9e-189">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-190">WmiObject-Namespace root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-190">Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-191">查看為使用者定義的 UE-V agent 設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-191">View the UE-V agent configuration that is defined for user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-192">WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-192">Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-193">查看為電腦定義的 UE-V agent 設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-193">View the UE-V agent configuration that is defined for computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-194">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-194">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-195">$config]。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-195">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-196">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-196">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-197">定義每個電腦的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="36c9e-197">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-198">$config = WmiObject-Namespace root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-198">$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-199">$config]。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-199">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-200">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-200">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-201">定義每個使用者的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="36c9e-201">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-202">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-202">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-203">$config]。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-203">$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-204">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-204">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-205">設定同步處理超時（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="36c9e-205">Set the synchronization timeout in milliseconds.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-206">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-206">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-207">$config]。MaxPackageSizeInBytes = &lt; size_in_bytes&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-207">$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-208">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-208">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-209">設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。</span><span class="sxs-lookup"><span data-stu-id="36c9e-209">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="36c9e-210">設定閾值套件檔案大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="36c9e-210">Set the threshold package file size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-211">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-211">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-212">$config]。SyncMethod = &lt; sync_method&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-212">$config.SyncMethod = &lt;sync_method&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-213">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-213">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-214">設定同步處理方法： [OfflineFiles] 或 [無]。</span><span class="sxs-lookup"><span data-stu-id="36c9e-214">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="36c9e-215">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-215">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-216">$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-216">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-217">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-217">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-218">更新特定的每電腦設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-218">Update a specific per-computer setting.</span></span> <span data-ttu-id="36c9e-219">若要清除此設定，請使用 $null 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="36c9e-219">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="36c9e-220">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="36c9e-220">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="36c9e-221">$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</span><span class="sxs-lookup"><span data-stu-id="36c9e-221">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="36c9e-222">$config]。Put （）</span><span class="sxs-lookup"><span data-stu-id="36c9e-222">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="36c9e-223">更新特定的每個使用者設定。</span><span class="sxs-lookup"><span data-stu-id="36c9e-223">Update a specific per-user setting.</span></span> <span data-ttu-id="36c9e-224">若要清除此設定，請使用 $null 做為設定值。</span><span class="sxs-lookup"><span data-stu-id="36c9e-224">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## <span data-ttu-id="36c9e-225">相關主題</span><span class="sxs-lookup"><span data-stu-id="36c9e-225">Related topics</span></span>


[<span data-ttu-id="36c9e-226">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="36c9e-226">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="36c9e-227">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="36c9e-227">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)









