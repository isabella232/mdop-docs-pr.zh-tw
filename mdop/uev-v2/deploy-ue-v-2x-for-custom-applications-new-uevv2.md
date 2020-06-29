---
title: 部署自訂應用程式的 UE-V 2. x
description: 部署自訂應用程式的 UE-V 2. x
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810533"
---
# <span data-ttu-id="92da4-103">部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="92da4-103">Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="92da4-104">Microsoft 使用者體驗虛擬化（UE-V）2.0。</span><span class="sxs-lookup"><span data-stu-id="92da4-104">Microsoft User Experience Virtualization (UE-V) 2.0.</span></span> <span data-ttu-id="92da4-105">2.1 和 2.1 SP1 使用名為 [**設定位置範本**] 的 XML 檔案，在使用者電腦之間監視及同步處理桌面應用程式設定與 Windows 桌面設定。</span><span class="sxs-lookup"><span data-stu-id="92da4-105">2.1, and 2.1 SP1 use XML files called **settings location templates** to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="92da4-106">根據預設值，UE-V 中包含一些設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-106">By default, some settings location templates are included in UE-V.</span></span> <span data-ttu-id="92da4-107">但如果您想要同步處理桌面應用程式的設定，而不包含在預設範本中，您可以使用 UE-V 發生器建立自己的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-107">But if you want to synchronize settings for desktop applications other than those included in the default templates, you can create your own custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="92da4-108">當您在[準備 ue-v 2. x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)中閱讀規劃資料並決定要同步處理自訂應用程式（協力廠商、商務線等）的設定後，您將會按照本主題中所述的方式來部署 ue-v 的功能。</span><span class="sxs-lookup"><span data-stu-id="92da4-108">Once you have read through the planning material in [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md) and have decided that you want to synchronize settings for custom applications (third-party, line-of-business, etc.), you will deploy the features of UE-V as described in this topic.</span></span> <span data-ttu-id="92da4-109">若要開始，以下是同步處理自訂應用程式設定所需的主要步驟：</span><span class="sxs-lookup"><span data-stu-id="92da4-109">To start, here are the main steps required to synchronize settings for custom applications:</span></span>

-   [<span data-ttu-id="92da4-110">安裝 UEV 發生器</span><span class="sxs-lookup"><span data-stu-id="92da4-110">Install the UEV Generator</span></span>](#uevgen)

    <span data-ttu-id="92da4-111">使用 UEV 發生器來建立自訂 XML 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-111">Use the UEV Generator to create custom XML settings location templates.</span></span>

-   [<span data-ttu-id="92da4-112">設定 UE-V 設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="92da4-112">Configure a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="92da4-113">您可以定義儲存自訂設定位置範本的這個路徑。</span><span class="sxs-lookup"><span data-stu-id="92da4-113">You can define this path where custom settings location templates are stored.</span></span>

-   [<span data-ttu-id="92da4-114">建立自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-114">Create custom settings location templates</span></span>](#createcustomtemplates)

    <span data-ttu-id="92da4-115">這些自訂範本可讓使用者同步處理自訂應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="92da4-115">These custom templates let users sync settings for custom applications.</span></span>

-   [<span data-ttu-id="92da4-116">部署自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-116">Deploy the custom settings location templates</span></span>](#deploycustomtemplates)

    <span data-ttu-id="92da4-117">在您測試自訂範本以確保正確同步處理之後，您可以透過下列其中一種方式來部署這些範本：</span><span class="sxs-lookup"><span data-stu-id="92da4-117">After you test the custom template to ensure that settings are synced correctly, you can deploy these templates in one of these ways:</span></span>

    -   <span data-ttu-id="92da4-118">透過您現有的部署基礎結構，例如 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="92da4-118">Through your existing deployment infrastructure, such as Configuration Manager</span></span>

    -   <span data-ttu-id="92da4-119">使用群組原則喜好設定</span><span class="sxs-lookup"><span data-stu-id="92da4-119">By using Group Policy preferences</span></span>

    -   [<span data-ttu-id="92da4-120">部署 UE-V 設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="92da4-120">Deploy a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="92da4-121">**記事** 使用 ESD 或群組原則部署的範本，必須在 UE-V Windows Management Instrumentation （WMI）或 Windows PowerShell 中註冊。</span><span class="sxs-lookup"><span data-stu-id="92da4-121">**Note** Templates that are deployed by using ESD or Group Policy must be registered with UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span>

     

## <span data-ttu-id="92da4-122">準備部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="92da4-122">Prepare to Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="92da4-123">開始部署處理自訂應用程式的 UE-V 功能前，只需要複習幾個事項。</span><span class="sxs-lookup"><span data-stu-id="92da4-123">Before you start deploying the UE-V features that handle custom applications, there are just a couple things to review.</span></span>

### <span data-ttu-id="92da4-124">UE-V 發生器</span><span class="sxs-lookup"><span data-stu-id="92da4-124">The UE-V Generator</span></span>

<span data-ttu-id="92da4-125">UE-V 發生器會監視應用程式，以探索和捕獲應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-125">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="92da4-126">受監視的應用程式必須是傳統的應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-126">The application that is monitored must be a traditional application.</span></span> <span data-ttu-id="92da4-127">您可以使用 UE-V 發生器來建立設定位置範本，但無法從這些應用程式類型建立設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="92da4-127">You use the UE-V Generator to create settings location templates, but it cannot create a settings location template from these application types:</span></span>

-   <span data-ttu-id="92da4-128">虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="92da4-128">Virtualized applications</span></span>

-   <span data-ttu-id="92da4-129">透過終端服務提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="92da4-129">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="92da4-130">JAVA 應用程式</span><span class="sxs-lookup"><span data-stu-id="92da4-130">Java applications</span></span>

-   <span data-ttu-id="92da4-131">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="92da4-131">Windows apps</span></span>

<span data-ttu-id="92da4-132">**記事** UE-V 設定位置範本無法從虛擬化應用程式或終端服務應用程式建立。</span><span class="sxs-lookup"><span data-stu-id="92da4-132">**Note** UE-V settings location templates cannot be created from virtualized applications or Terminal Services applications.</span></span> <span data-ttu-id="92da4-133">不過，使用範本同步處理的設定可以套用到那些應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-133">However, settings that are synchronized by using the templates can be applied to those applications.</span></span> <span data-ttu-id="92da4-134">若要建立支援虛擬桌面基礎結構（VDI）和終端服務應用程式的範本，請使用 UE-V 發生器開啟應用程式的 Windows Installer （.msi）套件版本。</span><span class="sxs-lookup"><span data-stu-id="92da4-134">To create templates that support Virtual Desktop Infrastructure (VDI) and Terminal Services applications, open a version of the Windows Installer (.msi) package of the application by using the UE-V Generator.</span></span> <span data-ttu-id="92da4-135">如需有關同步處理虛擬應用程式設定的詳細資訊，請參閱[使用 ue-v 2. 與應用程式虛擬化應用程式](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="92da4-135">For more information about synchronizing settings for virtual applications, see [Using UE-V 2.x with Application Virtualization Applications](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md).</span></span>

 

<span data-ttu-id="92da4-136">已**排除的位置：** 探索程式會排除通常儲存應用程式軟體檔案的位置，而這些檔案不會在使用者電腦或計算環境之間同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="92da4-136">**Excluded Locations:** The discovery process excludes locations that commonly store application software files that do not synchronize settings well between user computers or computing environments.</span></span> <span data-ttu-id="92da4-137">根據預設，會排除這些專案：</span><span class="sxs-lookup"><span data-stu-id="92da4-137">By default, these are excluded:</span></span>

-   <span data-ttu-id="92da4-138">HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-138">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="92da4-139">HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-139">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="92da4-140">位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼</span><span class="sxs-lookup"><span data-stu-id="92da4-140">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="92da4-141">位於 [Program Files] 目錄中的檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-141">Files that are located in Program Files directories</span></span>

-   <span data-ttu-id="92da4-142">位於使用者 \\ [User name \] \\ AppData \\ LocalLow 中的檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-142">Files that are located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="92da4-143">位於% Systemroot% 中的 Windows 作業系統檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-143">Windows operating system files that are located in %Systemroot%</span></span>

<span data-ttu-id="92da4-144">如果您需要儲存在排除位置的登錄機碼和檔案，才能同步處理應用程式設定，您可以在範本建立期間將位置手動新增到 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-144">If registry keys and files that are stored in excluded locations are required to synchronize application settings, you can manually add the locations to the settings location template during the template creation process.</span></span>
<span data-ttu-id="92da4-145">不過，只有對 HKEY \ _CURRENT \ _USER hive 的變更才會同步處理。</span><span class="sxs-lookup"><span data-stu-id="92da4-145">However, only changes to the HKEY\_CURRENT\_USER hive will be sync-ed.</span></span>

### <span data-ttu-id="92da4-146">取代預設的 Microsoft 範本</span><span class="sxs-lookup"><span data-stu-id="92da4-146">Replace the default Microsoft templates</span></span>

<span data-ttu-id="92da4-147">UE-V Agent 會安裝適用于常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。</span><span class="sxs-lookup"><span data-stu-id="92da4-147">The UE-V Agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="92da4-148">如果您自訂這些範本，或建立設定位置範本來同步處理自訂應用程式的設定，則可以將 UE-V Agent 設定為使用設定範本目錄來儲存範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-148">If you customize these templates, or create settings location templates to synchronize settings for custom applications, the UE-V Agent can be configured to use a settings template catalog to store the templates.</span></span> <span data-ttu-id="92da4-149">在這種情況下，您將需要在 [設定] 範本目錄中加入預設範本以及自訂範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-149">In this case, you will need to include the default templates along with the custom templates in the settings template catalog.</span></span>

<span data-ttu-id="92da4-150">當您[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)時，您可以使用命令列參數 `RegisterMSTemplates` 來停用預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-150">When you [Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent), you can use the command-line parameter `RegisterMSTemplates` to disable the registration of the default Microsoft templates.</span></span>

<span data-ttu-id="92da4-151">當您使用群組原則來設定設定範本目錄路徑時，您可以選擇取代預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-151">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="92da4-152">如果您將原則設定設定為取代預設的 Microsoft 範本，則會刪除由 UE-V Agent 安裝的所有預設 Microsoft 範本，而且只會使用位於設定範本目錄中的範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-152">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V Agent are deleted and only the templates that are located in the settings template catalog are used.</span></span> <span data-ttu-id="92da4-153">UE-V Agent 設定參數 `RegisterMSTemplates` 必須設定為*true* ，才能覆寫預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-153">The UE-V Agent configuration setting parameter `RegisterMSTemplates` must be set to *true* in order to override the default Microsoft template.</span></span>

<span data-ttu-id="92da4-154">**記事** 如果您在啟用此原則設定後停用它，UE-V Agent 就不會還原預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-154">**Note** If you disable this policy setting after it has been enabled, the UE-V Agent does not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="92da4-155">如果設定範本目錄中存在使用與預設 Microsoft 範本相同識別碼的自訂範本，而 UE-V Agent 並未設定為取代預設的 Microsoft 範本，則會忽略 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-155">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V Agent is not configured to replace the default Microsoft templates, the Microsoft templates are ignored.</span></span>

<span data-ttu-id="92da4-156">您也可以使用 UE-V Windows PowerShell 功能取代預設範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-156">You can also replace the default templates by using the UE-V Windows PowerShell features.</span></span> <span data-ttu-id="92da4-157">若要使用 Windows PowerShell 取代預設的 Microsoft 範本，請登出所有預設的 Microsoft 範本，然後註冊自訂範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-157">To replace the default Microsoft template with Windows PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="92da4-158">**記事** 即使您為應用程式部署新的設定位置範本，舊的設定套件仍會保留在 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-158">**Note** Old settings packages remain in the settings storage location even if you deploy new settings location templates for an application.</span></span> <span data-ttu-id="92da4-159">這些套件不會由代理程式讀取，但它們不會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="92da4-159">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <a href="" id="uevgen"></a><span data-ttu-id="92da4-160">安裝 UEV （2. x）產生器</span><span class="sxs-lookup"><span data-stu-id="92da4-160">Install the UEV 2.x Generator</span></span>


<span data-ttu-id="92da4-161">在電腦上安裝 Microsoft 使用者體驗 Virtualization （UE-V）2.0 發生器，您可以用來建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-161">Install the Microsoft User Experience Virtualization (UE-V) 2.0 Generator on a computer that you can then use to create a custom settings location template.</span></span> <span data-ttu-id="92da4-162">此電腦應該已安裝的應用程式是要產生的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-162">This computer should have the applications installed for which custom settings location templates are to be generated.</span></span>

**<span data-ttu-id="92da4-163">若要安裝 UE-V 發生器</span><span class="sxs-lookup"><span data-stu-id="92da4-163">To install the UE-V Generator</span></span>**

1.  <span data-ttu-id="92da4-164">以擁有本機系統管理員許可權的使用者的身分，找出 ue-v 發生器安裝檔案**ToolSetup.exe**提供給 ue-v 軟體。</span><span class="sxs-lookup"><span data-stu-id="92da4-164">As a user with local administrator rights, locate the UE-V Generator installation file **ToolSetup.exe** provided with the UE-V software.</span></span> <span data-ttu-id="92da4-165">或者，如果您知道電腦架構，您可以執行適當的 Windows Installer （.msi）檔案， **ToolsSetupx64.msi**或**ToolsSetupx86.msi**。</span><span class="sxs-lookup"><span data-stu-id="92da4-165">Or, if you know the computer architecture, you can run the appropriate Windows Installer (.msi) file, **ToolsSetupx64.msi** or **ToolsSetupx86.msi**.</span></span>

2.  <span data-ttu-id="92da4-166">按兩下安裝檔。</span><span class="sxs-lookup"><span data-stu-id="92da4-166">Double-click the installation file.</span></span> <span data-ttu-id="92da4-167">隨即會開啟 [使用者體驗虛擬化發生器設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="92da4-167">The User Experience Virtualization Generator Setup wizard opens.</span></span> <span data-ttu-id="92da4-168">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="92da4-168">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="92da4-169">接受 Microsoft 軟體授權條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="92da4-169">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="92da4-170">按一下 [Microsoft 更新] 和 [客戶經驗改進計畫] 的選項。</span><span class="sxs-lookup"><span data-stu-id="92da4-170">Click the options for Microsoft Updates and the Customer Experience Improvement Program.</span></span>

5.  <span data-ttu-id="92da4-171">選取要安裝 UE-V 發生器的目的地資料夾，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="92da4-171">Select the destination folder in which to install the UE-V Generator, and then click **Next**.</span></span>

6.  <span data-ttu-id="92da4-172">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="92da4-172">Click **Install** to begin the installation.</span></span>

    <span data-ttu-id="92da4-173">**記事** 在安裝應用程式之前，會出現 [**使用者帳戶控制**] 提示。</span><span class="sxs-lookup"><span data-stu-id="92da4-173">**Note** A prompt for **User Account Control** appears before the application is installed.</span></span> <span data-ttu-id="92da4-174">必須具備許可權，才能安裝 UE-V 發生器。</span><span class="sxs-lookup"><span data-stu-id="92da4-174">Permission is required to install the UE-V Generator.</span></span>

     

7.  <span data-ttu-id="92da4-175">安裝完成後，按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="92da4-175">Click **Finish** to close the wizard after the installation is finished.</span></span> <span data-ttu-id="92da4-176">您必須重新開機電腦，才能執行 UE-V 發生器。</span><span class="sxs-lookup"><span data-stu-id="92da4-176">You must restart your computer before you can run the UE-V Generator.</span></span>

    <span data-ttu-id="92da4-177">若要確認安裝已成功，請依序按一下 [**開始**]、[**所有程式**]、[ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="92da4-177">To verify that the installation was successful, click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

    <span data-ttu-id="92da4-178">**記事** UE-V 2 發生器只能用來建立 UE-V 2 個代理程式的範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-178">**Note** The UE-V 2 Generator can only be used to create templates for UE-V 2 Agents.</span></span> <span data-ttu-id="92da4-179">在 UE-V 1.0 Agent 與 UE-V 2 Agent 的混合式部署中，您應該繼續使用 UE-V 1.0 發生器，直到您升級完所有 UE-V Agent 為止。</span><span class="sxs-lookup"><span data-stu-id="92da4-179">In a mixed deployment of UE-V 1.0 Agents and UE-V 2 Agents, you should continue to use the UE-V 1.0 Generator until you have upgraded all UE-V Agents.</span></span>

     

## <a href="" id="deploycatalogue"></a><span data-ttu-id="92da4-180">部署設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="92da4-180">Deploy a Settings Template Catalog</span></span>


<span data-ttu-id="92da4-181">使用者體驗虛擬化設定範本目錄是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-181">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="92da4-182">UE-V Agent 中的排程任務會根據此資料夾中的範本，每日檢查一次此位置，並更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="92da4-182">A scheduled task in the UE-V Agent checks this location one time each day and updates its synchronization behavior, based on the templates in this folder.</span></span>

<span data-ttu-id="92da4-183">UE-V Agent 會在您最後一次檢查資料夾並登出已移除的範本之後，註冊此資料夾中新增或更新的範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-183">The UE-V Agent registers templates that were added or updated in this folder after the last time that the folder was checked and unregisters templates that are removed.</span></span> <span data-ttu-id="92da4-184">根據預設，範本是在每天淩晨3:30 登錄並取消註冊一次。</span><span class="sxs-lookup"><span data-stu-id="92da4-184">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="92da4-185">[任務排程器] 和 [系統啟動] 中的 [當地時間]。</span><span class="sxs-lookup"><span data-stu-id="92da4-185">local time by the Task Scheduler and at system startup.</span></span> <span data-ttu-id="92da4-186">若要自訂此排程任務的頻率，請參閱[變更 ue-v 2. x 排程任務的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="92da4-186">To customize the frequency of this scheduled task, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="92da4-187">您可以使用安裝命令列選項、群組原則、WMI 或 Windows PowerShell，來設定設定範本的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="92da4-187">You can configure the settings template catalog path by using the installation command-line options, Group Policy, WMI, or Windows PowerShell.</span></span> <span data-ttu-id="92da4-188">儲存在設定範本目錄路徑的範本會自動由排程的工作進行註冊和取消註冊。</span><span class="sxs-lookup"><span data-stu-id="92da4-188">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span>

**<span data-ttu-id="92da4-189">若要設定 UE-V 2. x 的設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="92da4-189">To configure the settings template catalog for UE-V 2.x</span></span>**

1.  <span data-ttu-id="92da4-190">在儲存 UE-V 設定範本目錄的電腦上建立新資料夾。</span><span class="sxs-lookup"><span data-stu-id="92da4-190">Create a new folder on the computer that stores the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="92da4-191">針對設定範本目錄資料夾設定下列共用層（SMB）許可權。</span><span class="sxs-lookup"><span data-stu-id="92da4-191">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="92da4-192">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="92da4-192">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="92da4-193">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="92da4-193">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="92da4-194">所有人</span><span class="sxs-lookup"><span data-stu-id="92da4-194">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-195">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="92da4-195">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="92da4-196">網域電腦</span><span class="sxs-lookup"><span data-stu-id="92da4-196">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-197">讀取權限等級</span><span class="sxs-lookup"><span data-stu-id="92da4-197">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="92da4-198">管理員</span><span class="sxs-lookup"><span data-stu-id="92da4-198">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-199">讀取/寫入權限等級</span><span class="sxs-lookup"><span data-stu-id="92da4-199">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="92da4-200">針對 [設定範本目錄] 資料夾設定下列 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="92da4-200">Set the following NTFS file system permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="92da4-201">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="92da4-201">User account</span></span></th>
    <th align="left"><span data-ttu-id="92da4-202">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="92da4-202">Recommended permissions</span></span></th>
    <th align="left"><span data-ttu-id="92da4-203">套用至</span><span class="sxs-lookup"><span data-stu-id="92da4-203">Apply to</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="92da4-204">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="92da4-204">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-205">完全控制</span><span class="sxs-lookup"><span data-stu-id="92da4-205">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-206">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-206">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="92da4-207">網域電腦</span><span class="sxs-lookup"><span data-stu-id="92da4-207">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-208">列出資料夾內容並閱讀</span><span class="sxs-lookup"><span data-stu-id="92da4-208">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-209">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-209">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="92da4-210">所有人</span><span class="sxs-lookup"><span data-stu-id="92da4-210">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-211">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="92da4-211">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-212">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="92da4-212">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="92da4-213">管理員</span><span class="sxs-lookup"><span data-stu-id="92da4-213">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-214">完全控制</span><span class="sxs-lookup"><span data-stu-id="92da4-214">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="92da4-215">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="92da4-215">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="92da4-216">按一下 **[確定**] 以關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="92da4-216">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="92da4-217">網路共用至少必須授與 Domain 電腦群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="92da4-217">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="92da4-218">此外，請將網路共用資料夾的存取權限授與要管理已儲存範本的管理員。</span><span class="sxs-lookup"><span data-stu-id="92da4-218">In addition, grant access permissions for the network share folder to administrators who are to manage the stored templates.</span></span>

## <a href="" id="createcustomtemplates"></a><span data-ttu-id="92da4-219">建立自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-219">Create Custom Settings Location Templates</span></span>


<span data-ttu-id="92da4-220">使用 UE-V 發生器來建立商務用應用程式或其他自訂應用程式的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-220">Use the UE-V Generator to create settings location templates for line-of-business applications or other custom applications.</span></span> <span data-ttu-id="92da4-221">在建立應用程式的範本之後，您可以將它部署到電腦，讓該應用程式的設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="92da4-221">After the template for an application is created, you can deploy it to computers so that settings are synchronized for that application.</span></span>

**<span data-ttu-id="92da4-222">使用 UE-V 發生器建立 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-222">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="92da4-223">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="92da4-223">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="92da4-224">按一下 [**建立設定位置] 範本**。</span><span class="sxs-lookup"><span data-stu-id="92da4-224">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="92da4-225">指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-225">Specify the application.</span></span> <span data-ttu-id="92da4-226">流覽至應用程式（.exe）的檔案路徑，或是您想要建立設定位置範本的應用程式快捷方式（.lnk）。</span><span class="sxs-lookup"><span data-stu-id="92da4-226">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="92da4-227">指定命令列引數（如果有的話），以及工作目錄（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="92da4-227">Specify the command-line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="92da4-228">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="92da4-228">Click **Next** to continue.</span></span>

    <span data-ttu-id="92da4-229">**記事** 在應用程式啟動之前，系統會顯示**使用者帳戶控制**的提示。</span><span class="sxs-lookup"><span data-stu-id="92da4-229">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="92da4-230">必須具備許可權，才能監視應用程式用來儲存設定的登錄和檔案位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-230">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="92da4-231">應用程式啟動後，請關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-231">After the application starts, close the application.</span></span> <span data-ttu-id="92da4-232">UE-V 發生器會記錄應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-232">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="92da4-233">處理常式完成後，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="92da4-233">After the process is completed, click **Next** to continue.</span></span>

6.  <span data-ttu-id="92da4-234">檢查並選取適當的登錄位置旁邊的核取方塊，以及要針對此應用程式同步處理的設定檔位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-234">Review and select the check boxes that are next to the appropriate registry settings locations and settings file locations to synchronize for this application.</span></span> <span data-ttu-id="92da4-235">此清單包含下列兩個類別的設定位置：</span><span class="sxs-lookup"><span data-stu-id="92da4-235">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="92da4-236">**標準**：儲存在登錄中的 [HKEY \ _CURRENT \ _USER] 索引卷名或 **[使用者名稱**\]] 下的檔案資料夾中的應用程式設定，請**AppData**  \\  **漫遊**。</span><span class="sxs-lookup"><span data-stu-id="92da4-236">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="92da4-237">UE-V 發生器預設會包含這些設定。</span><span class="sxs-lookup"><span data-stu-id="92da4-237">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="92da4-238">**非標準**：儲存在位置以外的應用程式設定是在設定資料儲存區的最佳做法中指定（選用）。</span><span class="sxs-lookup"><span data-stu-id="92da4-238">**Nonstandard**: Application settings that are stored outside the locations are specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="92da4-239">其中包括 [**使用者**] \\ [使用者名稱 \] \\ **AppData**Local] 下的檔案和資料夾  \\  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="92da4-239">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="92da4-240">請查看這些位置，判斷是否要在 [設定位置] 範本中包含這些位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-240">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="92da4-241">選取 [位置] 核取方塊以包含它們。</span><span class="sxs-lookup"><span data-stu-id="92da4-241">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="92da4-242">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="92da4-242">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="92da4-243">針對 [設定位置] 範本，查看及編輯任何**屬性** **、登錄位置及\*\*\*\*檔案位置。**</span><span class="sxs-lookup"><span data-stu-id="92da4-243">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="92da4-244">在 [**屬性**] 索引標籤上編輯下列屬性：</span><span class="sxs-lookup"><span data-stu-id="92da4-244">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="92da4-245">**應用程式名稱**：已寫入程式檔案屬性描述的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="92da4-245">**Application Name**: The application name that is written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="92da4-246">**程式名稱**：從程式檔案屬性提取的程式名稱。</span><span class="sxs-lookup"><span data-stu-id="92da4-246">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="92da4-247">這個名稱通常具有 .exe 副檔名。</span><span class="sxs-lookup"><span data-stu-id="92da4-247">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="92da4-248">**產品版本**：應用程式 .exe 檔案的產品版本號碼。</span><span class="sxs-lookup"><span data-stu-id="92da4-248">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="92da4-249">這個屬性與檔案**版本**搭配使用，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-249">This property, in conjunction with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="92da4-250">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="92da4-250">This property accepts a major version number.</span></span> <span data-ttu-id="92da4-251">如果這個屬性是空的，設定位置範本會套用至所有版本的產品。</span><span class="sxs-lookup"><span data-stu-id="92da4-251">If this property is empty, the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="92da4-252">[檔案**版本**]：應用程式 .exe 檔案的檔案版本號碼。</span><span class="sxs-lookup"><span data-stu-id="92da4-252">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="92da4-253">這個屬性會與**產品版本**搭配使用，協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-253">This property, in conjunction with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="92da4-254">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="92da4-254">This property accepts a major version number.</span></span> <span data-ttu-id="92da4-255">如果這個屬性是空的，設定位置範本會套用至所有版本的程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-255">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="92da4-256">**範本作者名稱**（選用）：設定位置範本作者的名稱。</span><span class="sxs-lookup"><span data-stu-id="92da4-256">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="92da4-257">**範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="92da4-257">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="92da4-258">[**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。</span><span class="sxs-lookup"><span data-stu-id="92da4-258">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="92da4-259">使用 [**任務**] 下拉式功能表編輯登錄位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-259">Edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="92da4-260">[工作] 可讓您新增金鑰、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。</span><span class="sxs-lookup"><span data-stu-id="92da4-260">Tasks enable you to add new keys, edit the name or scope of existing keys, delete keys, and browse the registry where the keys are located.</span></span> <span data-ttu-id="92da4-261">使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。</span><span class="sxs-lookup"><span data-stu-id="92da4-261">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="92da4-262">使用 [**所有設定] 和 [子項**]，將所有的登錄設定都包含在指定的索引鍵、子項和子項設定底下。</span><span class="sxs-lookup"><span data-stu-id="92da4-262">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="92da4-263">[**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案檢測。</span><span class="sxs-lookup"><span data-stu-id="92da4-263">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="92da4-264">使用 [**任務**] 下拉式功能表來編輯檔案位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-264">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="92da4-265">檔案位置的工作可讓您新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。</span><span class="sxs-lookup"><span data-stu-id="92da4-265">Tasks for file locations enable you to add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="92da4-266">將檔案遮罩保留為空白，以包含指定資料夾中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="92da4-266">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="92da4-267">按一下 [**建立**]，然後按一下 [**儲存**] 以儲存電腦上的 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-267">Click **Create**, and then click **Save** to save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="92da4-268">按一下 [**關閉**]，關閉 [設定範本] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="92da4-268">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="92da4-269">退出 UE-V 發生器應用程式。</span><span class="sxs-lookup"><span data-stu-id="92da4-269">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="92da4-270">在您為應用程式建立設定位置範本之後，您應該測試該範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-270">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="92da4-271">在實驗室環境中部署範本，然後將它放入企業中的生產環境。</span><span class="sxs-lookup"><span data-stu-id="92da4-271">Deploy the template in a lab environment before you put it into production in the enterprise.</span></span>

<span data-ttu-id="92da4-272">[Ue-v 的應用程式範本架構參考](https://technet.microsoft.com/library/dn763947.aspx)[ue-v 設定位置] 範本的 XML 結構，並提供編輯這些檔案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="92da4-272">[Application Template Schema Reference for UE-V](https://technet.microsoft.com/library/dn763947.aspx) details the XML structure of the UE-V settings location template and provides guidance for editing these files.</span></span>

## <a href="" id="deploycustomtemplates"></a><span data-ttu-id="92da4-273">部署自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-273">Deploy the Custom Settings Location Templates</span></span>


<span data-ttu-id="92da4-274">在使用 UE-V 發生器建立設定位置範本後，您應該對它進行測試，以確保正確同步處理應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="92da4-274">After you create a settings location template with the UE-V Generator, you should test it to ensure that the application settings are synchronized correctly.</span></span> <span data-ttu-id="92da4-275">然後，您就可以將設定位置範本安全地部署到企業中的電腦上。</span><span class="sxs-lookup"><span data-stu-id="92da4-275">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="92da4-276">您可以使用下列其中一種方法來部署設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="92da4-276">Settings location templates can be deployed by using one of these methods:</span></span>

-   <span data-ttu-id="92da4-277">企業軟體發佈（ESD）系統，例如 System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="92da4-277">An enterprise software distribution (ESD) system such as System Center Configuration Manager</span></span>

-   <span data-ttu-id="92da4-278">群組原則喜好設定</span><span class="sxs-lookup"><span data-stu-id="92da4-278">Group Policy preferences</span></span>

-   <span data-ttu-id="92da4-279">UE-V 設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="92da4-279">A UE-V settings template catalog</span></span>

<span data-ttu-id="92da4-280">使用 ESD 系統或群組原則物件所部署的範本，必須透過 UE-V Windows 管理規範（WMI）或 Windows PowerShell 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="92da4-280">Templates that are deployed by using an ESD system or Group Policy Objects must be registered through UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span> <span data-ttu-id="92da4-281">儲存在設定範本目錄位置的範本會自動由 UE-V Agent 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="92da4-281">Templates that are stored in the settings template catalog location are automatically registered by the UE-V Agent.</span></span>

**<span data-ttu-id="92da4-282">使用設定範本目錄路徑來部署 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="92da4-282">To use the settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="92da4-283">流覽至定義為 [設定] 範本目錄的網路共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="92da4-283">Browse to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="92da4-284">在設定範本目錄中新增、移除或更新設定位置範本，以反映您想要用於 UE-V 電腦的 UE-V Agent 範本配置。</span><span class="sxs-lookup"><span data-stu-id="92da4-284">Add, remove, or update settings location templates in the settings template catalog to reflect the UE-V Agent template configuration that you want for UE-V computers.</span></span>

    <span data-ttu-id="92da4-285">**記事** 電腦上的範本每天都會更新。</span><span class="sxs-lookup"><span data-stu-id="92da4-285">**Note** Templates on computers are updated daily.</span></span> <span data-ttu-id="92da4-286">更新是以設定範本目錄的變更為基礎。</span><span class="sxs-lookup"><span data-stu-id="92da4-286">The update is based on changes to the settings template catalog.</span></span>

     

3.  <span data-ttu-id="92da4-287">若要在執行 UE-V Agent 的電腦上手動更新範本，請開啟提升許可權的命令提示字元，然後流覽到 **% Program Files%\\Microsoft 使用者體驗虛擬化 \\ Agent \\ &lt; x86 或 x64 &gt; **，然後執行**ApplySettingsTemplateCatalog.exe**。</span><span class="sxs-lookup"><span data-stu-id="92da4-287">To manually update templates on a computer that runs the UE-V Agent, open an elevated command prompt, and browse to **%Program Files%\\Microsoft User Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe**.</span></span>

    <span data-ttu-id="92da4-288">**記事** 這個程式會在電腦啟動期間自動執行，而在3:30 時則會在 M。</span><span class="sxs-lookup"><span data-stu-id="92da4-288">**Note** This program runs automatically during computer startup and daily at 3:30 A. M.</span></span> <span data-ttu-id="92da4-289">收集最近新增到目錄中的任何新範本。</span><span class="sxs-lookup"><span data-stu-id="92da4-289">to gather any new templates that were recently added to the catalog.</span></span>

     






## <span data-ttu-id="92da4-290">相關主題</span><span class="sxs-lookup"><span data-stu-id="92da4-290">Related topics</span></span>


[<span data-ttu-id="92da4-291">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="92da4-291">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="92da4-292">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="92da4-292">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





