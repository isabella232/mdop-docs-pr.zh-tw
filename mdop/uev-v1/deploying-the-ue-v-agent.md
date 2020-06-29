---
title: 部署 UE-V 代理程式
description: 部署 UE-V 代理程式
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812201"
---
# <span data-ttu-id="4c17b-103">部署 UE-V 代理程式</span><span class="sxs-lookup"><span data-stu-id="4c17b-103">Deploying the UE-V Agent</span></span>


<span data-ttu-id="4c17b-104">Microsoft 使用者體驗虛擬化（UE-V） agent 必須在每一個使用 UE-V 的電腦上執行，以便漫遊應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="4c17b-104">The Microsoft User Experience Virtualization (UE-V) agent must run on each computer that uses UE-V to roam application and Windows settings.</span></span> <span data-ttu-id="4c17b-105">AgentSetup.exe 的單一安裝程式檔案，會在32位和64位作業系統上安裝 UE-V agent。</span><span class="sxs-lookup"><span data-stu-id="4c17b-105">A single installer file, AgentSetup.exe, installs the UE-V agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="4c17b-106">UE-V Agent 的命令列參數如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c17b-106">The command-line parameters of the UE-V Agent are the following:</span></span>

**<span data-ttu-id="4c17b-107">AgentSetup.exe 命令列參數</span><span class="sxs-lookup"><span data-stu-id="4c17b-107">AgentSetup.exe command-line parameters</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="4c17b-108">命令列參數</span><span class="sxs-lookup"><span data-stu-id="4c17b-108">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="4c17b-109">定義</span><span class="sxs-lookup"><span data-stu-id="4c17b-109">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="4c17b-110">附註</span><span class="sxs-lookup"><span data-stu-id="4c17b-110">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-111">/help 或/h 或/？</span><span class="sxs-lookup"><span data-stu-id="4c17b-111">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-112">顯示 [AgentSetup.exe 用法] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4c17b-112">Displays the AgentSetup.exe usage dialog.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-113">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="4c17b-113">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-114">指示定義儲存位置設定的通用命名慣例（UNC）路徑。</span><span class="sxs-lookup"><span data-stu-id="4c17b-114">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-115">已接受% username% 或% computername% 環境變數。</span><span class="sxs-lookup"><span data-stu-id="4c17b-115">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="4c17b-116">腳本可能需要轉義變數。</span><span class="sxs-lookup"><span data-stu-id="4c17b-116">Scripting may require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="4c17b-117">預設值 </strong> ： &lt; 無 &gt; （Active Directory 使用者家用版）</span><span class="sxs-lookup"><span data-stu-id="4c17b-117">Default</strong>: &lt;none&gt; (Active Directory user home)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-118">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="4c17b-118">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-119">表示通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-119">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-120">只需要自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="4c17b-120">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-121">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="4c17b-121">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-122">指定是否應在安裝期間註冊預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4c17b-122">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-123">True |虛假</span><span class="sxs-lookup"><span data-stu-id="4c17b-123">True | False</span></span></p>
<p><strong><span data-ttu-id="4c17b-124">預設值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="4c17b-124">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-125">SyncMethod</span><span class="sxs-lookup"><span data-stu-id="4c17b-125">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-126">指定應該使用哪一種同步處理方法。</span><span class="sxs-lookup"><span data-stu-id="4c17b-126">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-127">OfflineFiles |所有</span><span class="sxs-lookup"><span data-stu-id="4c17b-127">OfflineFiles | None</span></span></p>
<p><strong><span data-ttu-id="4c17b-128">預設值 </strong> ： OfflineFiles</span><span class="sxs-lookup"><span data-stu-id="4c17b-128">Default</strong>: OfflineFiles</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-129">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="4c17b-129">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-130">指定在從設定儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="4c17b-130">Specifies the number of milliseconds that the computer waits before timeout when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="4c17b-131">預設值 </strong> ：2000毫秒</span><span class="sxs-lookup"><span data-stu-id="4c17b-131">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="4c17b-132">（等待最長2秒）</span><span class="sxs-lookup"><span data-stu-id="4c17b-132">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-133">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="4c17b-133">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-134">指定是啟用還是停用 UE-V 同步處理。</span><span class="sxs-lookup"><span data-stu-id="4c17b-134">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-135">True |虛假</span><span class="sxs-lookup"><span data-stu-id="4c17b-135">True | False</span></span></p>
<p><strong><span data-ttu-id="4c17b-136">預設值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="4c17b-136">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-137">MaxPackageSizeInBytes</span><span class="sxs-lookup"><span data-stu-id="4c17b-137">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-138">在 UE-V agent 報告檔案超過閾值時，指定設定套件檔案大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="4c17b-138">Specifies a settings package file size in bytes when the UE-V agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-139">&lt;大小&gt;</span><span class="sxs-lookup"><span data-stu-id="4c17b-139">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="4c17b-140">預設值 </strong> ：無（無警告閾值）</span><span class="sxs-lookup"><span data-stu-id="4c17b-140">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-141">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="4c17b-141">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-142">指定參與客戶經驗改進計畫的設定。</span><span class="sxs-lookup"><span data-stu-id="4c17b-142">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="4c17b-143">如果設定為 true，則會將安裝程式資訊上傳到 Microsoft 客戶經驗改進計畫網站。</span><span class="sxs-lookup"><span data-stu-id="4c17b-143">If set to true, then installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="4c17b-144">如果設定為 false，則不會上傳任何資訊。</span><span class="sxs-lookup"><span data-stu-id="4c17b-144">If set to false, then no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-145">True |虛假</span><span class="sxs-lookup"><span data-stu-id="4c17b-145">True | False</span></span></p>
<p><strong><span data-ttu-id="4c17b-146">預設值 </strong> ： False</span><span class="sxs-lookup"><span data-stu-id="4c17b-146">Default</strong>: False</span></span></p>
<p><strong><span data-ttu-id="4c17b-147">在 Windows 7 上 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="4c17b-147">On Windows 7</strong>: True</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4c17b-148">在安裝期間，SettingsStoragePath 命令列參數會指定設定值的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-148">During installation, the SettingsStoragePath command-line parameter specifies the settings storage location for the settings values.</span></span> <span data-ttu-id="4c17b-149">您可以在部署 UE-V Agent 之前，先定義設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-149">A settings storage location can be defined before deploying the UE-V Agent.</span></span> <span data-ttu-id="4c17b-150">如果未定義任何設定儲存位置，則 UE-V 會使用 Active Directory 使用者主目錄作為設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-150">If no settings storage location is defined, then UE-V uses the Active Directory user Home Directory as the settings storage location.</span></span> <span data-ttu-id="4c17b-151">當您在安裝期間指定 SettingsStoragePath 設定並使用% username% 作為值的一部分時，這會在使用者登入的所有電腦或會話上漫遊相同的使用者設定體驗。</span><span class="sxs-lookup"><span data-stu-id="4c17b-151">When you specify the SettingsStoragePath configuration during setup and use the %username% as part of the value, this will roam the same user settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="4c17b-152">如果您指定%username%\\%computername% 變數作為 SettingsStoragePath 值的一部分，這將會保留每個電腦的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="4c17b-152">If you specify the %username%\\%computername% variables as part of the SettingsStoragePath value, this will preserve the settings experience for each computer.</span></span>

<span data-ttu-id="4c17b-153">除了結合32位和64位安裝程式之外，還提供 UE-V agent 安裝的體系結構專用 Windows 安裝程式（.msi）檔案。</span><span class="sxs-lookup"><span data-stu-id="4c17b-153">Architecture-specific Windows Installer (.msi) files are provided for the UE-V agent installation in addition to the combined 32-bit and 64-bit installer.</span></span> <span data-ttu-id="4c17b-154">AgentSetupx86.msi 或 AgentSetupx64.msi 安裝檔小於 AgentSetup.exe 檔案，可能會簡化代理程式部署。</span><span class="sxs-lookup"><span data-stu-id="4c17b-154">The AgentSetupx86.msi or AgentSetupx64.msi install files are smaller than the AgentSetup.exe file and might streamline the agent deployments.</span></span> <span data-ttu-id="4c17b-155">Windows Installer （.msi）安裝支援 AgentSetup.exe 安裝程式的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="4c17b-155">The command-line parameters for the AgentSetup.exe installer are supported for the Windows Installer (.msi) installation.</span></span>

<span data-ttu-id="4c17b-156">**記事** 在 UE-V agent 安裝或卸載期間，您可以使用 AgentSetup.exe 檔案或 AgentSetup 的 .msi 檔案 &lt; &gt; ，但不能同時使用這兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="4c17b-156">**Note** During UE-V agent installation or uninstallation you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="4c17b-157">您必須使用相同的檔案才能卸載 UE-V Agent，就像它是用來安裝 UE-V Agent 一樣。</span><span class="sxs-lookup"><span data-stu-id="4c17b-157">The same file must be used to uninstall the UE-V Agent as it was used to install the UE-V Agent.</span></span>

 

<span data-ttu-id="4c17b-158">安裝 UE-V agent 時，請務必使用正確的變數格式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-158">Be sure to use the correct variable format when you install the UE-V agent.</span></span> <span data-ttu-id="4c17b-159">下表提供使用 AgentSetup.exe 或 Windows Installer （.msi）安裝檔案之部署選項的範例。</span><span class="sxs-lookup"><span data-stu-id="4c17b-159">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) installation files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="4c17b-160">部署類型</span><span class="sxs-lookup"><span data-stu-id="4c17b-160">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="4c17b-161">部署描述</span><span class="sxs-lookup"><span data-stu-id="4c17b-161">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="4c17b-162">範例</span><span class="sxs-lookup"><span data-stu-id="4c17b-162">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-163">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="4c17b-163">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-164">當您從命令提示字元安裝 UE-V agent 時，請使用% ^ username% 變數格式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-164">When you install the UE-V agent from a command prompt, use the %^username% variable format.</span></span> <span data-ttu-id="4c17b-165">如果由於設定儲存路徑中有空格而需要引號，請使用批次腳本檔案進行部署。</span><span class="sxs-lookup"><span data-stu-id="4c17b-165">If quotation marks are needed because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-166">批次處理腳本</span><span class="sxs-lookup"><span data-stu-id="4c17b-166">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-167">當您從批次腳本檔案安裝 UE-V Agent 時，請使用%% username%% 變數格式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-167">When you install the UE-V Agent from a batch script file, use the %%username%% variable format.</span></span> <span data-ttu-id="4c17b-168">如果您使用這個安裝方法，您必須使用%% 字元來轉義變數。</span><span class="sxs-lookup"><span data-stu-id="4c17b-168">If you use this install method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="4c17b-169">如果沒有此字元，腳本會在安裝時（而不是在執行時間）擴充使用者名稱變數，導致 UE-V 針對所有使用者使用單一的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-169">Without this character, the script expands the username variable at install time, rather than at run time, causing UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c17b-170">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c17b-170">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-171">當您從 PowerShell 提示或 PowerShell 腳本安裝 UE-V agent 時，請使用% username% 變數格式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-171">When you install the UE-V agent from a PowerShell prompt or PowerShell script, use the %username% variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c17b-172">電子軟體發佈，例如部署 Configuration Manager 軟體部署）</span><span class="sxs-lookup"><span data-stu-id="4c17b-172">Electronic software distribution, such as deployment of Configuration Manager Software Deployment)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c17b-173">當您使用 Configuration Manager 安裝 UE-V Agent 時，請使用 ^% username ^% 變數格式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-173">When you install the UE-V Agent with Configuration Manager, use the ^%username^% variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4c17b-174">**記事** 安裝 U EV 代理程式需要系統管理員許可權，而且電腦必須先重新開機，才能執行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="4c17b-174">**Note** The installation of the U-EV Agent requires Administrator rights and the computer will require a restart before the UE-V agent can run.</span></span>

 

## <span data-ttu-id="4c17b-175">從網路共用的 UE-V Agent 部署方法</span><span class="sxs-lookup"><span data-stu-id="4c17b-175">UE-V Agent deployment methods from a network share</span></span>


<span data-ttu-id="4c17b-176">您可以使用下列方法來部署 UE-V agent：</span><span class="sxs-lookup"><span data-stu-id="4c17b-176">You can use the following methods to deploy the UE-V agent:</span></span>

-   <span data-ttu-id="4c17b-177">可安裝 Windows 安裝程式（.msi）檔案的電子軟體發佈（ESD）方案。</span><span class="sxs-lookup"><span data-stu-id="4c17b-177">An electronic software distribution (ESD) solution that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="4c17b-178">參照在共用中集中儲存的 Windows Installer （.msi）檔案的安裝腳本。</span><span class="sxs-lookup"><span data-stu-id="4c17b-178">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="4c17b-179">在電腦上手動執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4c17b-179">Manually running the installation program on the computer.</span></span>

<span data-ttu-id="4c17b-180">若要從網路共用部署 UE-V agent，請使用下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4c17b-180">To deploy the UE-V agent from a network share, use the following steps:</span></span>

**<span data-ttu-id="4c17b-181">從網路共用安裝並設定 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="4c17b-181">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="4c17b-182">在使用者擁有「讀取」許可權的網路共用上，暫存 UE-V agent 安裝檔（AgentSetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="4c17b-182">Stage the UE-V agent installation file (AgentSetup.exe) on a network share to which users have “read” permission.</span></span>

2.  <span data-ttu-id="4c17b-183">將腳本部署到安裝 UE-V agent 的使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="4c17b-183">Deploy a script to user computers that installs the UE-V agent.</span></span> <span data-ttu-id="4c17b-184">此腳本應指定設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="4c17b-184">The script should specify the settings storage location.</span></span>

**<span data-ttu-id="4c17b-185">更新 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="4c17b-185">Update the UE-V Agent</span></span>**

<span data-ttu-id="4c17b-186">UE-V agent 軟體的更新將透過 Microsoft Update 提供。</span><span class="sxs-lookup"><span data-stu-id="4c17b-186">Updates for the UE-V agent software will be provided through Microsoft Update.</span></span> <span data-ttu-id="4c17b-187">在 UE-V agent 升級期間，可能會更新常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。</span><span class="sxs-lookup"><span data-stu-id="4c17b-187">During a UE-V agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings may be updated.</span></span> <span data-ttu-id="4c17b-188">UE-V agent 更新可以使用企業軟體發佈（ESD）基礎結構來部署。</span><span class="sxs-lookup"><span data-stu-id="4c17b-188">UE-V agent updates can be deployed by using Enterprise Software Distribution (ESD) infrastructure.</span></span>

## <span data-ttu-id="4c17b-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="4c17b-189">Related topics</span></span>


[<span data-ttu-id="4c17b-190">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="4c17b-190">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="4c17b-191">UE-V 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="4c17b-191">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

[<span data-ttu-id="4c17b-192">部署適用於 UE-V 1.0 的設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="4c17b-192">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

[<span data-ttu-id="4c17b-193">安裝 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="4c17b-193">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="4c17b-194">部署使用者體驗虛擬化代理程式</span><span class="sxs-lookup"><span data-stu-id="4c17b-194">Deploy the User Experience Virtualization Agent</span></span>
 

 





