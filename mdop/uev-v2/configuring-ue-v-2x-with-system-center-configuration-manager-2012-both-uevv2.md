---
title: 使用 System Center Configuration Manager 2012 設定 UE-V 2. x
description: 使用 System Center Configuration Manager 2012 設定 UE-V 2. x
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810538"
---
# <span data-ttu-id="c3efc-103">使用 System Center Configuration Manager 2012 設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c3efc-103">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="c3efc-104">在您安裝 Microsoft 使用者體驗 Virtualization （UE-V）2.0、2.1 或 2.1 SP1 及其必要功能之後，就必須設定 UE-V。</span><span class="sxs-lookup"><span data-stu-id="c3efc-104">After you install Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 and their required features, UE-V must be configured.</span></span> <span data-ttu-id="c3efc-105">UE-V 設定套件提供一種方式，讓管理員使用 System Center Configuration Manager 2012 SP1 或更新版本的相容性設定功能，在安裝了 UE-V 和 Configuration Manager 的各個網站上套用一致的配置。</span><span class="sxs-lookup"><span data-stu-id="c3efc-105">The UE-V Configuration Pack provides a way for administrators to use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

## <span data-ttu-id="c3efc-106">UE-V Configuration Pack 支援的功能</span><span class="sxs-lookup"><span data-stu-id="c3efc-106">UE-V Configuration Pack supported features</span></span>


<span data-ttu-id="c3efc-107">UE-V Configuration Pack 包括執行下列工作的工具：</span><span class="sxs-lookup"><span data-stu-id="c3efc-107">The UE-V Configuration Pack includes tools to perform the following tasks:</span></span>

-   <span data-ttu-id="c3efc-108">建立或更新 UE-V 設定位置範本發佈比較基準。</span><span class="sxs-lookup"><span data-stu-id="c3efc-108">Create or update UE-V settings location template distribution baselines.</span></span>

    -   <span data-ttu-id="c3efc-109">定義要註冊或取消註冊的 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="c3efc-109">Define UE-V templates to be registered or unregistered</span></span>

    -   <span data-ttu-id="c3efc-110">在新增或更新範本時更新 UE-V 範本設定專案和比較基準</span><span class="sxs-lookup"><span data-stu-id="c3efc-110">Update UE-V template configuration items and baselines as templates are added or updated</span></span>

    -   <span data-ttu-id="c3efc-111">使用標準設定專案修正來散佈及註冊 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="c3efc-111">Distribute and register UE-V templates using standard Configuration Item remediation</span></span>

-   <span data-ttu-id="c3efc-112">建立或更新 UE-V Agent 策略設定專案，以設定或清除這些設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-112">Create or update a UE-V Agent policy configuration item to set or clear these settings.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="c3efc-113">套件大小上限</span><span class="sxs-lookup"><span data-stu-id="c3efc-113">Max package size</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-114">啟用/停用 Windows 應用程式同步處理</span><span class="sxs-lookup"><span data-stu-id="c3efc-114">Enable/disable Windows app sync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-115">在應用程式啟動時等待同步處理</span><span class="sxs-lookup"><span data-stu-id="c3efc-115">Wait for sync on application start</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="c3efc-116">設定匯入延遲</span><span class="sxs-lookup"><span data-stu-id="c3efc-116">Setting import delay</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-117">同步未列出的 Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="c3efc-117">Sync unlisted Windows apps</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-118">在登入後等待同步處理</span><span class="sxs-lookup"><span data-stu-id="c3efc-118">Wait for sync on logon</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="c3efc-119">設定匯入通知</span><span class="sxs-lookup"><span data-stu-id="c3efc-119">Settings import notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-120">IT 連絡人 URL</span><span class="sxs-lookup"><span data-stu-id="c3efc-120">IT contact URL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-121">等待同步處理超時</span><span class="sxs-lookup"><span data-stu-id="c3efc-121">Wait for sync timeout</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="c3efc-122">設定儲存路徑</span><span class="sxs-lookup"><span data-stu-id="c3efc-122">Settings storage path</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-123">IT 連絡人描述文字</span><span class="sxs-lookup"><span data-stu-id="c3efc-123">IT contact descriptive text</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-124">設定範本目錄路徑</span><span class="sxs-lookup"><span data-stu-id="c3efc-124">Settings template catalog path</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="c3efc-125">啟用同步處理</span><span class="sxs-lookup"><span data-stu-id="c3efc-125">Sync enablement</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-126">已啟用工作列圖示</span><span class="sxs-lookup"><span data-stu-id="c3efc-126">Tray icon enabled</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-127">開始/停止 UE-V agent 服務</span><span class="sxs-lookup"><span data-stu-id="c3efc-127">Start/Stop UE-V agent service</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="c3efc-128">同步處理方法</span><span class="sxs-lookup"><span data-stu-id="c3efc-128">Sync method</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-129">第一次使用通知</span><span class="sxs-lookup"><span data-stu-id="c3efc-129">First use notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="c3efc-130">定義哪些 Windows 應用程式將漫遊設定</span><span class="sxs-lookup"><span data-stu-id="c3efc-130">Define which Windows apps will roam settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="c3efc-131">同步處理超時</span><span class="sxs-lookup"><span data-stu-id="c3efc-131">Sync timeout</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="c3efc-132">確認 UE-V 正在執行，以驗證合規性。</span><span class="sxs-lookup"><span data-stu-id="c3efc-132">Verify compliance by confirming that UE-V is running.</span></span>

## <span data-ttu-id="c3efc-133">產生 UE-V Agent 原則設定項目</span><span class="sxs-lookup"><span data-stu-id="c3efc-133">Generate a UE-V Agent Policy Configuration Item</span></span>


<span data-ttu-id="c3efc-134">所有 UE-V Agent 原則和設定都是透過使用 UevAgentPolicyGenerator.exe 工具所產生的單一設定專案來發佈。</span><span class="sxs-lookup"><span data-stu-id="c3efc-134">All UE-V Agent policy and configuration is distributed through a single configuration item that is generated using the UevAgentPolicyGenerator.exe tool.</span></span> <span data-ttu-id="c3efc-135">這個工具會從 XML 設定檔中讀取所需的設定，並建立 CI，其中包含將電腦納入合規性所需的探索與修正設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-135">This tool reads the desired configuration from an XML configuration file and creates a CI containing the discovery and remediation settings needed to bring the machine into compliance.</span></span>

<span data-ttu-id="c3efc-136">UE-V Agent 原則設定專案 CAB 檔案是使用 UevTemplateBaselineGenerator.exe 命令列工具建立的，其中包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="c3efc-136">The UE-V Agent policy configuration item CAB file is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="c3efc-137">網站 &lt; 網站程式碼&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-137">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="c3efc-138">PolicyName &lt; 名稱 &gt; 選用：預設為 "Ue-v Agent Policy" （如果沒有的話）</span><span class="sxs-lookup"><span data-stu-id="c3efc-138">PolicyName &lt;name&gt; Optional: Defaults to “UE-V Agent Policy” if not present</span></span>

-   <span data-ttu-id="c3efc-139">PolicyDescription &lt; 說明 &gt; （選用）：如果不存在，就會提供描述</span><span class="sxs-lookup"><span data-stu-id="c3efc-139">PolicyDescription &lt;description&gt; Optional: A description is provided if not present</span></span>

-   <span data-ttu-id="c3efc-140">CabFilePath &lt; 設定項目的完整路徑。CAB 檔&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-140">CabFilePath &lt;full path to configuration item .CAB file&gt;</span></span>

-   <span data-ttu-id="c3efc-141">ConfigurationFile &lt; 代理程式配置 XML 檔案的完整路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-141">ConfigurationFile &lt;full path to agent configuration XML file&gt;</span></span>

<span data-ttu-id="c3efc-142">**記事** 可能需要變更 PowerShell 執行原則，以允許這些腳本在您的環境中執行。</span><span class="sxs-lookup"><span data-stu-id="c3efc-142">**Note** It might be necessary to change the PowerShell execution policy to allow these scripts to run in your environment.</span></span> <span data-ttu-id="c3efc-143">在 Configuration Manager 主控台中執行這些步驟：</span><span class="sxs-lookup"><span data-stu-id="c3efc-143">Perform these steps in the Configuration Manager console:</span></span>

1.  <span data-ttu-id="c3efc-144">選取**管理 &gt; 用戶端設定 &gt; 屬性**</span><span class="sxs-lookup"><span data-stu-id="c3efc-144">Select **Administration &gt; Client Settings &gt; Properties**</span></span>

2.  <span data-ttu-id="c3efc-145">在 [**使用者代理程式**] 索引標籤中，將**PowerShell 執行原則**設定為 [**略過**]</span><span class="sxs-lookup"><span data-stu-id="c3efc-145">In the **User Agent** tab, set the **PowerShell Execution Policy** to **Bypass**</span></span>

<a href="" id="create"></a>**<span data-ttu-id="c3efc-146">建立第一個 UE-V 原則設定項目</span><span class="sxs-lookup"><span data-stu-id="c3efc-146">Create the First UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="c3efc-147">從 UE-V Config Pack 安裝目錄將預設設定配置檔案複製到您的 ConfigMgr 系統管理主控台可看見的位置：</span><span class="sxs-lookup"><span data-stu-id="c3efc-147">Copy the default settings configuration file from the UE-V Config Pack installation directory to a location visible to your ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    <span data-ttu-id="c3efc-148">預設的設定檔包含五個區段：</span><span class="sxs-lookup"><span data-stu-id="c3efc-148">The default configuration file contains five sections:</span></span>

    <a href="" id="computer-policy"></a>**<span data-ttu-id="c3efc-149">電腦原則</span><span class="sxs-lookup"><span data-stu-id="c3efc-149">Computer Policy</span></span>**  
    <span data-ttu-id="c3efc-150">所有 UE-V 電腦層級設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-150">All UE-V machine level settings.</span></span> <span data-ttu-id="c3efc-151">DesiredState 屬性可以是</span><span class="sxs-lookup"><span data-stu-id="c3efc-151">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="c3efc-152">**設定**為在註冊表中指派值</span><span class="sxs-lookup"><span data-stu-id="c3efc-152">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="c3efc-153">**清除**以移除設定</span><span class="sxs-lookup"><span data-stu-id="c3efc-153">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="c3efc-154">**未受管理**，無法將設定項目保留在目前狀態</span><span class="sxs-lookup"><span data-stu-id="c3efc-154">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="c3efc-155">請勿移除此區段中的線條。</span><span class="sxs-lookup"><span data-stu-id="c3efc-155">Do not remove lines from this section.</span></span> <span data-ttu-id="c3efc-156">相反地，如果您不想讓 Configuration Manager 變更目前或預設值，請將 DesiredState 設定為 [未受管理的]。</span><span class="sxs-lookup"><span data-stu-id="c3efc-156">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="currentcomputeruserpolicy"></a>**<span data-ttu-id="c3efc-157">CurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="c3efc-157">CurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="c3efc-158">所有 UE-V 使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-158">All UE-V user level settings.</span></span> <span data-ttu-id="c3efc-159">這些專案會覆寫使用者的電腦設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-159">These entries override the machine settings for a user.</span></span> <span data-ttu-id="c3efc-160">DesiredState 屬性可以是</span><span class="sxs-lookup"><span data-stu-id="c3efc-160">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="c3efc-161">**設定**為在註冊表中指派值</span><span class="sxs-lookup"><span data-stu-id="c3efc-161">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="c3efc-162">**清除**以移除設定</span><span class="sxs-lookup"><span data-stu-id="c3efc-162">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="c3efc-163">**未受管理**，無法將設定項目保留在目前狀態</span><span class="sxs-lookup"><span data-stu-id="c3efc-163">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="c3efc-164">請勿移除此區段中的線條。</span><span class="sxs-lookup"><span data-stu-id="c3efc-164">Do not remove lines from this section.</span></span> <span data-ttu-id="c3efc-165">相反地，如果您不想讓 Configuration Manager 變更目前或預設值，請將 DesiredState 設定為 [未受管理的]。</span><span class="sxs-lookup"><span data-stu-id="c3efc-165">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="services"></a>**<span data-ttu-id="c3efc-166">服務</span><span class="sxs-lookup"><span data-stu-id="c3efc-166">Services</span></span>**  
    <span data-ttu-id="c3efc-167">此區段控制服務作業中的專案。</span><span class="sxs-lookup"><span data-stu-id="c3efc-167">Entries in this section control service operation.</span></span> <span data-ttu-id="c3efc-168">預設的設定檔包含 UevAgentService 的單一專案。</span><span class="sxs-lookup"><span data-stu-id="c3efc-168">The default configuration file contains a single entry for the UevAgentService.</span></span> <span data-ttu-id="c3efc-169">DesiredState 屬性可以**設定為 [** 執行] 或 [**停止**]。</span><span class="sxs-lookup"><span data-stu-id="c3efc-169">The DesiredState attribute can be set to **Running** or **Stopped**.</span></span>

    <a href="" id="windows8appscomputerpolicy"></a>**<span data-ttu-id="c3efc-170">Windows8AppsComputerPolicy</span><span class="sxs-lookup"><span data-stu-id="c3efc-170">Windows8AppsComputerPolicy</span></span>**  
    <span data-ttu-id="c3efc-171">所有電腦層級 Windows 應用程式同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-171">All machine level Windows app synchronization settings.</span></span> <span data-ttu-id="c3efc-172">此區段中所列的每個 PackageFamilyName 都可以指派 DesiredState</span><span class="sxs-lookup"><span data-stu-id="c3efc-172">Each PackageFamilyName listed in this section can be assigned a DesiredState of</span></span>

    -   <span data-ttu-id="c3efc-173">**已啟用**[設定] 漫遊</span><span class="sxs-lookup"><span data-stu-id="c3efc-173">**Enabled** to have settings roam</span></span>

    -   <span data-ttu-id="c3efc-174">[**已停用**] 以防止漫遊的設定</span><span class="sxs-lookup"><span data-stu-id="c3efc-174">**Disabled** to prevent settings from roaming</span></span>

    -   <span data-ttu-id="c3efc-175">已**清除**以從 ue-v 控制項移除專案</span><span class="sxs-lookup"><span data-stu-id="c3efc-175">**Cleared** to have the entry removed from UE-V control</span></span>

    <span data-ttu-id="c3efc-176">您可以根據已安裝的 Windows app 清單（可使用 PowerShell Cmdlet GetAppxPackage 查看），在此區段中新增其他行。</span><span class="sxs-lookup"><span data-stu-id="c3efc-176">Additional lines can be added to this section based on the list of installed Windows apps that can be viewed using the PowerShell cmdlet GetAppxPackage.</span></span>

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**<span data-ttu-id="c3efc-177">Windows8AppsCurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="c3efc-177">Windows8AppsCurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="c3efc-178">與 Windows8AppsComputerPolicy 相同，其設定會覆寫個別使用者的電腦設定。</span><span class="sxs-lookup"><span data-stu-id="c3efc-178">Identical to the Windows8AppsComputerPolicy with settings that override machine settings for an individual user.</span></span>

2.  <span data-ttu-id="c3efc-179">變更 [所需的狀態] 和 [值] 欄位以編輯設定檔。</span><span class="sxs-lookup"><span data-stu-id="c3efc-179">Edit the configuration file by changing the desired state and value fields.</span></span>

3.  <span data-ttu-id="c3efc-180">在執行 ConfigMgr 系統管理主控台的電腦上執行此命令：</span><span class="sxs-lookup"><span data-stu-id="c3efc-180">Run this command on a machine running the ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  <span data-ttu-id="c3efc-181">使用 ConfigMgr 主機或 PowerShell Import 匯入 CAB 檔案 CMConfigurationItem</span><span class="sxs-lookup"><span data-stu-id="c3efc-181">Import the CAB file using ConfigMgr console or PowerShell Import-CMConfigurationItem</span></span>

**<span data-ttu-id="c3efc-182">更新 UE-V 原則設定專案</span><span class="sxs-lookup"><span data-stu-id="c3efc-182">Update a UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="c3efc-183">變更 [所需的狀態] 和 [值] 欄位以編輯設定檔。</span><span class="sxs-lookup"><span data-stu-id="c3efc-183">Edit the configuration file by changing the desired state and value fields.</span></span>

2.  <span data-ttu-id="c3efc-184">在[建立第一個 Ue-v 原則設定專案](#create)中，從步驟3執行命令。</span><span class="sxs-lookup"><span data-stu-id="c3efc-184">Run the command from Step 3 in [Create the First UE-V Policy Configuration Item](#create).</span></span> <span data-ttu-id="c3efc-185">如果您使用 PolicyName 參數變更了名稱，請確認輸入相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3efc-185">If you changed the name with the PolicyName parameter, make sure you enter the same name.</span></span>

3.  <span data-ttu-id="c3efc-186">重新導入 CAB 檔案。</span><span class="sxs-lookup"><span data-stu-id="c3efc-186">Reimport the CAB file.</span></span> <span data-ttu-id="c3efc-187">將會更新 ConfigMgr 中的版本。</span><span class="sxs-lookup"><span data-stu-id="c3efc-187">The version in ConfigMgr will be updated.</span></span>

## <span data-ttu-id="c3efc-188">產生 UE-V 範本比較基準</span><span class="sxs-lookup"><span data-stu-id="c3efc-188">Generate a UE-V Template Baseline</span></span>
<span data-ttu-id="c3efc-189">UE-V 範本是使用包含多個設定專案的比較基準來散佈。</span><span class="sxs-lookup"><span data-stu-id="c3efc-189">UE-V templates are distributed using a baseline containing multiple configuration items.</span></span> <span data-ttu-id="c3efc-190">每個設定專案都包含安裝一個 UE-V 範本所需的探索與修正腳本。</span><span class="sxs-lookup"><span data-stu-id="c3efc-190">Each configuration item contains the discovery and remediation scripts needed to install one UE-V template.</span></span> <span data-ttu-id="c3efc-191">實際的 UE-V 範本內嵌在修正腳本中，以使用標準設定專案功能進行發佈。</span><span class="sxs-lookup"><span data-stu-id="c3efc-191">The actual UE-V template is embedded within the remediation script for distribution using standard Configuration Item functionality.</span></span>

<span data-ttu-id="c3efc-192">UE-V 範本比較基準是使用 UevTemplateBaselineGenerator.exe 命令列工具建立的，其中包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="c3efc-192">The UE-V template baseline is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="c3efc-193">網站 &lt; 網站程式碼&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-193">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="c3efc-194">BaselineName &lt; 名稱 &gt; （選用：預設為 "Ue-v 範本發佈比較基準" （如果沒有的話））</span><span class="sxs-lookup"><span data-stu-id="c3efc-194">BaselineName &lt;name&gt; (Optional: defaults to “UE-V Template Distribution Baseline” if not present)</span></span>

-   <span data-ttu-id="c3efc-195">BaselineDescription &lt; 說明 &gt; （選用：如果不存在，就會提供描述）</span><span class="sxs-lookup"><span data-stu-id="c3efc-195">BaselineDescription &lt;description&gt; (Optional: a description is provided if not present)</span></span>

-   <span data-ttu-id="c3efc-196">TemplateFolder &lt; ue-v 範本資料夾&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-196">TemplateFolder &lt;UE-V template folder&gt;</span></span>

-   <span data-ttu-id="c3efc-197">註冊 &lt; 逗號分隔的範本檔案清單&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-197">Register &lt;comma separated template file list&gt;</span></span>

-   <span data-ttu-id="c3efc-198">取消註冊 &lt; 以逗號分隔的範本清單&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-198">Unregister &lt;comma separated template list&gt;</span></span>

-   <span data-ttu-id="c3efc-199">CabFilePath 要 &lt; 產生的基線 CAB 檔案完整路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="c3efc-199">CabFilePath &lt;Full path to baseline CAB file to generate&gt;</span></span>

<span data-ttu-id="c3efc-200">結果是已準備好匯入 Configuration Manager 的基線 CAB 檔案。</span><span class="sxs-lookup"><span data-stu-id="c3efc-200">The result is a baseline CAB file that is ready for import into Configuration Manager.</span></span> <span data-ttu-id="c3efc-201">如果您是在未來的日期更新或新增範本，您可以使用相同的比較基準名稱重新執行命令。</span><span class="sxs-lookup"><span data-stu-id="c3efc-201">If at a future date, you update or add a template, you can rerun the command using the same baseline name.</span></span> <span data-ttu-id="c3efc-202">匯入 CAB 會導致 CI 版本在變更的範本上更新。</span><span class="sxs-lookup"><span data-stu-id="c3efc-202">Importing the CAB results in CI version updates on the changed templates.</span></span>

### <a href="" id="create2"></a><span data-ttu-id="c3efc-203">建立第一個 UE-V 範本比較基準</span><span class="sxs-lookup"><span data-stu-id="c3efc-203">Create the First UE-V Template Baseline</span></span>

1.  <span data-ttu-id="c3efc-204">在執行 ConfigMgr 系統管理主控台的電腦可見的穩定資料夾位置中，建立一組 UE-V 範本。</span><span class="sxs-lookup"><span data-stu-id="c3efc-204">Create a “master” set of UE-V templates in a stable folder location visible to the machine running your ConfigMgr Admin Console.</span></span> <span data-ttu-id="c3efc-205">在新增或更新範本時，此資料夾是用來進行發佈的位置。</span><span class="sxs-lookup"><span data-stu-id="c3efc-205">As templates are added or updated, this folder is where they are pulled for distribution.</span></span> <span data-ttu-id="c3efc-206">範本的初始清單可以從安裝了 UE-V 的電腦複製。</span><span class="sxs-lookup"><span data-stu-id="c3efc-206">The initial list of templates can be copied from a machine with UE-V installed.</span></span> <span data-ttu-id="c3efc-207">預設範本位置是 C:\\program files Files\\Microsoft 使用者體驗 Virtualization\\Templates。</span><span class="sxs-lookup"><span data-stu-id="c3efc-207">The default template location is C:\\Program Files\\Microsoft User Experience Virtualization\\Templates.</span></span>

2.  <span data-ttu-id="c3efc-208">建立 text.bat 檔案，您可以在其中新增 [範本發生器] 命令。</span><span class="sxs-lookup"><span data-stu-id="c3efc-208">Create a text.bat file where you can add the template generator command.</span></span> <span data-ttu-id="c3efc-209">這是選擇性的，但如果您儲存命令參數，就會使再生更簡單。</span><span class="sxs-lookup"><span data-stu-id="c3efc-209">This is optional, but will make regeneration simpler if you save the command parameters.</span></span>

3.  <span data-ttu-id="c3efc-210">將命令和參數新增至將產生比較基準的 .bat 檔案。</span><span class="sxs-lookup"><span data-stu-id="c3efc-210">Add the command and parameters to the .bat file that will generate the baseline.</span></span> <span data-ttu-id="c3efc-211">下列範例會建立一個分發記事本和計算機的比較基準：</span><span class="sxs-lookup"><span data-stu-id="c3efc-211">The following example creates a baseline that distributes Notepad and Calculator:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  <span data-ttu-id="c3efc-212">執行 .bat 檔案，建立 UevTemplateBaseline.cab 準備匯入 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="c3efc-212">Run the .bat file to create UevTemplateBaseline.cab ready for import into Configuration Manager.</span></span>

### <span data-ttu-id="c3efc-213">更新 UE-V 範本比較基準</span><span class="sxs-lookup"><span data-stu-id="c3efc-213">Update a UE-V Template Baseline</span></span>

<span data-ttu-id="c3efc-214">範本發生器使用範本版本來判斷是否應該更新範本。</span><span class="sxs-lookup"><span data-stu-id="c3efc-214">The template generator uses the template version to determine if a template should be updated.</span></span> <span data-ttu-id="c3efc-215">如果您進行範本變更並更新版本，比較基準發生器會將主資料夾中的範本與 ConfigMgr 伺服器上 CI 中包含的範本進行比較。</span><span class="sxs-lookup"><span data-stu-id="c3efc-215">If you make a template change and update the version, the baseline generator compares the template in your master folder with the template contained in the CI on the ConfigMgr server.</span></span> <span data-ttu-id="c3efc-216">如果找到差異，就會更新產生的比較基準與已修改的 CI 版本。</span><span class="sxs-lookup"><span data-stu-id="c3efc-216">If a difference is found, the generated baseline and modified CI versions are updated.</span></span>

<span data-ttu-id="c3efc-217">若要散佈新的記事本範本，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c3efc-217">To distribute a new Notepad template, you would perform these steps:</span></span>

1.  <span data-ttu-id="c3efc-218">更新位於 &lt; 範本之版本元素中的範本和範本版本 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c3efc-218">Update the template and template version located in the &lt;Version&gt; element of the template.</span></span>

2.  <span data-ttu-id="c3efc-219">將範本複製到您的主範本目錄。</span><span class="sxs-lookup"><span data-stu-id="c3efc-219">Copy the template to your master template directory.</span></span>

3.  <span data-ttu-id="c3efc-220">在[建立第一個 Ue-v 範本比較基準](#create2)的 .bat 檔案中，執行您在步驟3所建立的命令。</span><span class="sxs-lookup"><span data-stu-id="c3efc-220">Run the command in the .bat file that you created in Step 3 in [Create the First UE-V Template Baseline](#create2).</span></span>

4.  <span data-ttu-id="c3efc-221">使用主控台或 PowerShell 匯入 CMBaseline，將產生的 CAB 檔案匯入到 ConfigMgr。</span><span class="sxs-lookup"><span data-stu-id="c3efc-221">Import the generated CAB file into ConfigMgr using the console or PowerShell Import-CMBaseline.</span></span>

## <span data-ttu-id="c3efc-222">取得 UE-V Configuration Pack</span><span class="sxs-lookup"><span data-stu-id="c3efc-222">Get the UE-V Configuration Pack</span></span>


<span data-ttu-id="c3efc-223">Configuration Manager 2012 SP1 或更新版本的 UE-V Configuration Pack 可以在[此](https://go.microsoft.com/fwlink/?LinkId=317263)下載。</span><span class="sxs-lookup"><span data-stu-id="c3efc-223">The UE-V Configuration Pack for Configuration Manager 2012 SP1 or later can be downloaded [here](https://go.microsoft.com/fwlink/?LinkId=317263).</span></span>






## <span data-ttu-id="c3efc-224">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3efc-224">Related topics</span></span>


[<span data-ttu-id="c3efc-225">管理 UE-V 2.x 的設定</span><span class="sxs-lookup"><span data-stu-id="c3efc-225">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





