---
title: 部署 UE-V 2.x 的必要功能
description: 部署 UE-V 2.x 的必要功能
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810694"
---
# <span data-ttu-id="484aa-103">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="484aa-103">Deploy Required Features for UE-V 2.x</span></span>


<span data-ttu-id="484aa-104">所有 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 部署都需要這些功能</span><span class="sxs-lookup"><span data-stu-id="484aa-104">All Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 deployments require these features</span></span>

-   <span data-ttu-id="484aa-105">部署最終使用者可以存取的[設定儲存位置](#ssl)。</span><span class="sxs-lookup"><span data-stu-id="484aa-105">[Deploy a Settings Storage Location](#ssl) that is accessible to end users.</span></span>

    <span data-ttu-id="484aa-106">這是一個儲存及檢索使用者設定的標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="484aa-106">This is a standard network share that stores and retrieves user settings.</span></span>

-   [<span data-ttu-id="484aa-107">選擇 UE-V 的配置方法</span><span class="sxs-lookup"><span data-stu-id="484aa-107">Choose the Configuration Method for UE-V</span></span>](#config)

    <span data-ttu-id="484aa-108">UE-V 可以使用通用管理工具（包括群組原則、Configuration Manager 或 Windows 管理基礎結構和 Powershell）進行部署和設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-108">UE-V can be deployed and configured using common management tools including group policy, Configuration Manager, or Windows Management Infrastructure and Powershell.</span></span>

-   <span data-ttu-id="484aa-109">部署要在同步處理設定的每台電腦上安裝的[Ue-v Agent](#agent) 。</span><span class="sxs-lookup"><span data-stu-id="484aa-109">[Deploy a UE-V Agent](#agent) to be installed on every computer that synchronizes settings.</span></span>

    <span data-ttu-id="484aa-110">這會監視已註冊的應用程式與作業系統的任何設定變更，並在電腦之間同步處理這些設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-110">This monitors registered applications and the operating system for any settings changes and synchronizes those settings between computers.</span></span>

<span data-ttu-id="484aa-111">本節中的主題描述如何部署這些功能。</span><span class="sxs-lookup"><span data-stu-id="484aa-111">The topics in this section describe how to deploy these features.</span></span>

## <a href="" id="ssl"></a><span data-ttu-id="484aa-112">部署 UE-V 設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="484aa-112">Deploy a UE-V Settings Storage Location</span></span>


<span data-ttu-id="484aa-113">UE-V 需要在設定套件檔案中儲存使用者設定的位置。</span><span class="sxs-lookup"><span data-stu-id="484aa-113">UE-V requires a location in which to store user settings in settings package files.</span></span> <span data-ttu-id="484aa-114">您可以透過下列其中一種方式來設定儲存位置：</span><span class="sxs-lookup"><span data-stu-id="484aa-114">You can configure this settings storage location in one of these ways:</span></span>

-   <span data-ttu-id="484aa-115">建立您自己的設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="484aa-115">Create your own settings storage location</span></span>

-   <span data-ttu-id="484aa-116">針對您的設定儲存位置使用現有的 Active Directory</span><span class="sxs-lookup"><span data-stu-id="484aa-116">Use existing Active Directory for your settings storage location</span></span>

<span data-ttu-id="484aa-117">如果您沒有建立設定儲存位置，UE-V Agent 預設會使用 Active Directory （AD）。</span><span class="sxs-lookup"><span data-stu-id="484aa-117">If you don’t create a settings storage location, the UE-V Agent will use Active Directory (AD) by default.</span></span>

**<span data-ttu-id="484aa-118">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-118">Note</span></span>**  
<span data-ttu-id="484aa-119">考慮[效能與容量規劃](https://technet.microsoft.com/library/dn458932.aspx#capacity)，並減少網路延遲的問題，請在使用者電腦所在的同一個本機網路上建立設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="484aa-119">As a matter of [performance and capacity planning](https://technet.microsoft.com/library/dn458932.aspx#capacity) and to reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="484aa-120">針對設定儲存位置，我們建議每個使用者有 20 MB 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="484aa-120">We recommend 20 MB of disk space per user for the settings storage location.</span></span>



### <span data-ttu-id="484aa-121">建立 UE-V 設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="484aa-121">Create a UE-V Settings Storage Location</span></span>

<span data-ttu-id="484aa-122">在您定義設定儲存位置之前，您必須先建立一個根目錄，並針對儲存在共用上設定的使用者提供讀/寫許可權。</span><span class="sxs-lookup"><span data-stu-id="484aa-122">Before you define the settings storage location, you must create a root directory with read/write permissions for users who store settings on the share.</span></span> <span data-ttu-id="484aa-123">UE-V Agent 會在這個根目錄下建立使用者專用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="484aa-123">The UE-V Agent creates user-specific folders under this root directory.</span></span>

<span data-ttu-id="484aa-124">設定儲存位置是透過設定 [SettingsStoragePath 設定] 選項來定義，您可以使用下列其中一種方法加以設定：</span><span class="sxs-lookup"><span data-stu-id="484aa-124">The settings storage location is defined by setting the SettingsStoragePath configuration option, which you can configure by using one of these methods:</span></span>

-   <span data-ttu-id="484aa-125">當您透過命令列參數或在批次腳本中[部署 Ue-v Agent](#agent)時</span><span class="sxs-lookup"><span data-stu-id="484aa-125">When you [Deploy the UE-V Agent](#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="484aa-126">透過[群組原則](https://technet.microsoft.com/library/dn458893.aspx)設定</span><span class="sxs-lookup"><span data-stu-id="484aa-126">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="484aa-127">使用[System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx)進行 ue-v</span><span class="sxs-lookup"><span data-stu-id="484aa-127">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="484aa-128">使用[Windows PowerShell 或 Windows 管理工具（WMI）](https://technet.microsoft.com/library/dn458937.aspx)安裝 ue-v Agent 之後</span><span class="sxs-lookup"><span data-stu-id="484aa-128">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>

<span data-ttu-id="484aa-129">路徑必須位於伺服器和共用的通用命名慣例（UNC）路徑中。</span><span class="sxs-lookup"><span data-stu-id="484aa-129">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="484aa-130">例如， **\\\\Server\\Settingsshare\\**。</span><span class="sxs-lookup"><span data-stu-id="484aa-130">For example, **\\\\Server\\Settingsshare\\**.</span></span> <span data-ttu-id="484aa-131">這個設定選項支援使用變數來啟用特定的同步處理案例。</span><span class="sxs-lookup"><span data-stu-id="484aa-131">This configuration option supports the use of variables to enable specific synchronization scenarios.</span></span> <span data-ttu-id="484aa-132">例如，您可以使用變數， `%username%\%computername%` 在這些案例中保留使用者設定的體驗：</span><span class="sxs-lookup"><span data-stu-id="484aa-132">For example, you can use the `%username%\%computername%` variables to preserve the end user settings experience in these scenarios:</span></span>

-   <span data-ttu-id="484aa-133">在企業中使用多個物理電腦的終端使用者</span><span class="sxs-lookup"><span data-stu-id="484aa-133">End users that use multiple physical computers in your enterprise</span></span>

-   <span data-ttu-id="484aa-134">多名使用者使用的企業電腦</span><span class="sxs-lookup"><span data-stu-id="484aa-134">Enterprise computers that are used by multiple end users</span></span>

<span data-ttu-id="484aa-135">UE-V Agent 會根據 `SettingsPackages` **SettingsStoragePath**的設定設定，動態建立一個使用者專用的設定儲存路徑，並將隱藏的系統資料夾命名為。</span><span class="sxs-lookup"><span data-stu-id="484aa-135">The UE-V Agent dynamically creates a user-specific settings storage path, with a hidden system folder named `SettingsPackages`, based on the configuration setting of **SettingsStoragePath**.</span></span> <span data-ttu-id="484aa-136">代理程式會讀取並將設定寫入此位置，如已註冊的 UE-V 設定位置範本所定義。</span><span class="sxs-lookup"><span data-stu-id="484aa-136">The agent reads and writes settings to this location as defined by the registered UE-V settings location templates.</span></span>

<span data-ttu-id="484aa-137">**Ue-v 設定是由「上次寫入 wins」規則所決定：** 如果有多個受管理電腦的使用者的設定儲存位置相同，則一個 UE-V Agent 會讀取並寫入 [設定] 位置，而不是在其他電腦上執行的代理程式。</span><span class="sxs-lookup"><span data-stu-id="484aa-137">**UE-V settings are determined by a "Last write wins" rule:** If the settings storage location is the same for user with multiple managed computers, one UE-V Agent reads and writes to the settings location independently of agents running on other computers.</span></span> <span data-ttu-id="484aa-138">在下一個代理程式從設定儲存位置讀取時，會套用上次寫入的設定和值。</span><span class="sxs-lookup"><span data-stu-id="484aa-138">The last written settings and values are the ones applied when the next agent reads from the settings storage location.</span></span>

<span data-ttu-id="484aa-139">**部署設定儲存位置：** 請依照這些步驟來定義設定儲存位置，而不是使用您現有的 Active Directory 服務。</span><span class="sxs-lookup"><span data-stu-id="484aa-139">**Deploy the settings storage location:** Follow these steps to define the settings storage location rather than using your existing Active Directory service.</span></span> <span data-ttu-id="484aa-140">您應該將設定儲存空間共用的存取許可權制為需要它的使用者，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="484aa-140">You should limit access to the settings storage share to those users that require it, as shown in the tables below.</span></span>

**<span data-ttu-id="484aa-141">部署 UE-V 網路共用</span><span class="sxs-lookup"><span data-stu-id="484aa-141">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="484aa-142">為 UE-V 使用者建立新的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="484aa-142">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="484aa-143">在集中位置的電腦上建立儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者存取資料夾的群組許可權。</span><span class="sxs-lookup"><span data-stu-id="484aa-143">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="484aa-144">支援 UE-V 的管理員必須擁有此共用資料夾的許可權。</span><span class="sxs-lookup"><span data-stu-id="484aa-144">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="484aa-145">針對 [設定儲存位置] 資料夾設定下列共用層伺服器訊息區塊（SMB）許可權。</span><span class="sxs-lookup"><span data-stu-id="484aa-145">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="484aa-146">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="484aa-146">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="484aa-147">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="484aa-147">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="484aa-148">所有人</span><span class="sxs-lookup"><span data-stu-id="484aa-148">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-149">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="484aa-149">No permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="484aa-150">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="484aa-150">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-151">完全控制</span><span class="sxs-lookup"><span data-stu-id="484aa-151">Full control</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="484aa-152">針對 [設定儲存位置] 資料夾設定下列 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="484aa-152">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="484aa-153">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="484aa-153">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="484aa-154">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="484aa-154">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="484aa-155">資料夾</span><span class="sxs-lookup"><span data-stu-id="484aa-155">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="484aa-156">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="484aa-156">Creator/owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-157">完全控制</span><span class="sxs-lookup"><span data-stu-id="484aa-157">Full control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-158">僅限子資料夾和檔案</span><span class="sxs-lookup"><span data-stu-id="484aa-158">Subfolders and files only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="484aa-159">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="484aa-159">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-160">列出資料夾/讀取資料、建立資料夾/附加資料</span><span class="sxs-lookup"><span data-stu-id="484aa-160">List folder/read data, create folders/append data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="484aa-161">僅限此資料夾</span><span class="sxs-lookup"><span data-stu-id="484aa-161">This folder only</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="484aa-162">使用此設定時，UE-V Agent 會在使用者的內容中執行時建立並保護 Settingspackage 資料夾，並授與每個使用者的許可權，以建立設定儲存空間的資料夾。</span><span class="sxs-lookup"><span data-stu-id="484aa-162">With this configuration, the UE-V Agent creates and secures a Settingspackage folder while it runs in the context of the user, and grants each user permission to create folders for settings storage.</span></span> <span data-ttu-id="484aa-163">使用者在其 Settingspackage 資料夾中接收完全控制，而其他使用者則無法存取。</span><span class="sxs-lookup"><span data-stu-id="484aa-163">Users receive full control to their Settingspackage folder while other users cannot access it.</span></span>

**<span data-ttu-id="484aa-164">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-164">Note</span></span>**  
<span data-ttu-id="484aa-165">如果您在執行 Windows Server 作業系統的電腦上建立 [設定儲存空間共用]，請設定 UE-V，確認 [本機管理員] 群組或 [目前的使用者] 是儲存設定套件的資料夾擁有者。</span><span class="sxs-lookup"><span data-stu-id="484aa-165">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="484aa-166">若要啟用此額外的安全性，請在 Windows Server 登錄編輯程式中指定此設定：</span><span class="sxs-lookup"><span data-stu-id="484aa-166">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="484aa-167">將名為 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**]。</span><span class="sxs-lookup"><span data-stu-id="484aa-167">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="484aa-168">將 [登錄機碼] 值設定為*1*。</span><span class="sxs-lookup"><span data-stu-id="484aa-168">Set the registry key value to *1*.</span></span>



### <span data-ttu-id="484aa-169">使用具有 UE-V 2 的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="484aa-169">Use Active Directory with UE-V 2.x</span></span>

<span data-ttu-id="484aa-170">如果沒有另行定義設定儲存位置，UE-V Agent 預設會使用 Active Directory （AD）。</span><span class="sxs-lookup"><span data-stu-id="484aa-170">The UE-V Agent uses Active Directory (AD) by default if a settings storage location is not otherwise defined.</span></span> <span data-ttu-id="484aa-171">在這些情況下，UE-V Agent 會動態地在每位使用者的 AD home directory 根目錄底下建立 [設定儲存空間] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="484aa-171">In these cases, the UE-V Agent dynamically creates the settings storage folder under the root of the AD home directory of each user.</span></span> <span data-ttu-id="484aa-172">但是，如果您在 AD 中設定自訂目錄設定，則會改為使用該目錄。</span><span class="sxs-lookup"><span data-stu-id="484aa-172">But, if a custom directory setting is configured in AD, then that directory is used instead.</span></span>

## <a href="" id="config"></a><span data-ttu-id="484aa-173">選擇 UE-V 2 的配置方法。</span><span class="sxs-lookup"><span data-stu-id="484aa-173">Choose the Configuration Method for UE-V 2.x</span></span>


<span data-ttu-id="484aa-174">您想要找出部署之後要用來管理 UE-V 的設定方法，因為這會是您用來部署 UE-V Agent 的設定方法。</span><span class="sxs-lookup"><span data-stu-id="484aa-174">You want to figure out which configuration method you'll use to manage UE-V after deployment since this will be the configuration method you use to deploy the UE-V Agent.</span></span> <span data-ttu-id="484aa-175">通常，這是您在您的環境中已使用的配置方法，例如 Windows PowerShell 或 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="484aa-175">Typically, this is the configuration method that you already use in your environment, such as Windows PowerShell or Configuration Manager.</span></span>

<span data-ttu-id="484aa-176">您可以在 UE-V Agent 安裝之前、期間或之後設定 UE-V，視您使用的配置方法而定。</span><span class="sxs-lookup"><span data-stu-id="484aa-176">You can configure UE-V before, during, or after UE-V Agent installation, depending on the configuration method that you use.</span></span>

-   <span data-ttu-id="484aa-177">[群組原則](https://technet.microsoft.com/library/dn458893.aspx)**：** 您可以使用現有的群組原則基礎結構，在 ue-v agent 部署之前或之後設定 ue-v。</span><span class="sxs-lookup"><span data-stu-id="484aa-177">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You can use your existing Group Policy infrastructure to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="484aa-178">UE-V 群組原則 ADMX 範本可讓您集中管理通用的 UE-V Agent 設定選項，並且包括設定 UE-V 同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-178">The UE-V Group Policy ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span>

    <span data-ttu-id="484aa-179">**安裝 Ue-v 群組原則 ADMX 範本：** UE-V 的群組原則 ADMX 範本設定 UE-V Agent 的同步處理設定，並使用現有的群組原則基礎結構啟用常見 UE-V Agent 設定設定的集中式管理。</span><span class="sxs-lookup"><span data-stu-id="484aa-179">**Installing the UE-V Group Policy ADMX Templates:** Group Policy ADMX templates for UE-V configure the synchronization settings for the UE-V Agent and enable the central management of common UE-V Agent configuration settings by using an existing Group Policy infrastructure.</span></span>

    <span data-ttu-id="484aa-180">部署群組原則物件之網網域控制站支援的作業系統包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="484aa-180">Supported operating systems for the domain controller that deploys the Group Policy Objects include the following:</span></span>

    <span data-ttu-id="484aa-181">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="484aa-181">Windows Server 2008 R2</span></span>

    <span data-ttu-id="484aa-182">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="484aa-182">Windows Server 2012 and Windows Server 2012 R2</span></span>

-   <span data-ttu-id="484aa-183">[Configuration Manager](https://technet.microsoft.com/library/dn458917.aspx)**：** ue-v 設定套件可讓您使用 System Center configuration Manager 2012 SP1 或更新版本的相容性設定功能，在安裝了 ue-v 和 Configuration Manager 的各個網站上套用一致的設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-183">[Configuration Manager](https://technet.microsoft.com/library/dn458917.aspx)**:** The UE-V Configuration Pack lets you use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

-   <span data-ttu-id="484aa-184">[Windows powershell 和 WMI](https://technet.microsoft.com/library/dn458937.aspx)**：** 您可以在安裝 ue-v agent 之後，使用 windows powershell 和 windows Management Instrumentation （WMI）的指令碼命令來修改設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-184">[Windows PowerShell and WMI](https://technet.microsoft.com/library/dn458937.aspx)**:** You can use scripted commands for Windows PowerShell and Windows Management Instrumentation (WMI) to modify configurations after you install the UE-V Agent.</span></span>

    **<span data-ttu-id="484aa-185">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-185">Note</span></span>**  
    <span data-ttu-id="484aa-186">註冊表修改可能會造成資料遺失，或電腦變得不回應。</span><span class="sxs-lookup"><span data-stu-id="484aa-186">Registry modification can result in data loss, or the computer becomes unresponsive.</span></span> <span data-ttu-id="484aa-187">建議您使用其他配置方法。</span><span class="sxs-lookup"><span data-stu-id="484aa-187">We recommend that you use other configuration methods.</span></span>



-   <span data-ttu-id="484aa-188">**命令列或批次腳本安裝：**[部署 Ue-v Agent](#agent)時所使用的參數會設定許多 ue-v 設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-188">**Command-line or Batch Script Installation:** Parameters that are used when you [Deploy the UE-V Agent](#agent) configure many UE-V settings.</span></span> <span data-ttu-id="484aa-189">電子軟體發佈系統，例如 System Center 2012 Configuration Manager，請在部署並安裝 UE-V Agent 軟體時，使用這些參數來設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="484aa-189">Electronic software distribution systems, such as System Center 2012 Configuration Manager, use these parameters to configure their clients when they deploy and install the UE-V Agent software.</span></span>

## <a href="" id="agent"></a><span data-ttu-id="484aa-190">部署 UE-V a.x 代理程式</span><span class="sxs-lookup"><span data-stu-id="484aa-190">Deploy the UE-V 2.x Agent</span></span>


<span data-ttu-id="484aa-191">UE-V Agent 是 UE-V 部署的核心，而且必須在使用 UE-V 的每台電腦上執行，才能同步處理應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-191">The UE-V Agent is the core of a UE-V deployment and must run on each computer that uses UE-V to synchronize application and Windows settings.</span></span>

<span data-ttu-id="484aa-192">**Ue-v Agent 安裝檔：** AgentSetup.exe 的單一安裝檔案，會在32位和64位作業系統上安裝 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-192">**UE-V Agent Installation Files:** A single installation file, AgentSetup.exe, installs the UE-V Agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="484aa-193">此外，您也提供 AgentSetupx86.msi 或 AgentSetupx64.msi 架構特定的 Windows 安裝程式檔案，因為這些檔案較小，所以它們可能會簡化代理部署。</span><span class="sxs-lookup"><span data-stu-id="484aa-193">In addition, AgentSetupx86.msi or AgentSetupx64.msi architecture-specific Windows Installer files are provided, and since they are smaller, they might streamline the agent deployments.</span></span> <span data-ttu-id="484aa-194">Windows 安裝程式安裝也支援[AgentSetup.exe 安裝程式的命令列參數](#params)。</span><span class="sxs-lookup"><span data-stu-id="484aa-194">The [command-line parameters for the AgentSetup.exe installer](#params) are supported for the Windows Installer installation as well.</span></span>

**<span data-ttu-id="484aa-195">重要</span><span class="sxs-lookup"><span data-stu-id="484aa-195">Important</span></span>**  
<span data-ttu-id="484aa-196">在 UE-V Agent 安裝或卸載期間，您可以使用 AgentSetup.exe 檔案或 AgentSetup 的 &lt; &gt; .msi 檔案，但不能同時使用這兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="484aa-196">During UE-V Agent installation or uninstallation, you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="484aa-197">必須使用相同的檔案才能卸載用來安裝 UE-V Agent 的 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-197">The same file must be used to uninstall the UE-V Agent that was used to install the UE-V Agent.</span></span>



### <span data-ttu-id="484aa-198">部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="484aa-198">To Deploy the UE-V Agent</span></span>

<span data-ttu-id="484aa-199">您可以使用下列方法來部署 UE-V Agent：</span><span class="sxs-lookup"><span data-stu-id="484aa-199">You can use the following methods to deploy the UE-V Agent:</span></span>

-   <span data-ttu-id="484aa-200">可安裝 Windows 安裝程式（.msi）檔案的電子軟體發佈（ESD）方案系統，例如建構管理員。</span><span class="sxs-lookup"><span data-stu-id="484aa-200">An electronic software distribution (ESD) solution system, such as Configuration Manager, that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="484aa-201">參照在共用中集中儲存的 Windows Installer （.msi）檔案的安裝腳本。</span><span class="sxs-lookup"><span data-stu-id="484aa-201">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="484aa-202">您在電腦上手動執行的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="484aa-202">An installation program that you run manually on the computer.</span></span>

<span data-ttu-id="484aa-203">使用下列程式從網路共用部署 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-203">Use the following procedure to deploy the UE-V Agent from a network share.</span></span>

**<span data-ttu-id="484aa-204">從網路共用安裝並設定 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="484aa-204">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="484aa-205">在使用者擁有 [讀取] 許可權的網路共用上，暫存 UE-V Agent 安裝檔 AgentSetup.exe。</span><span class="sxs-lookup"><span data-stu-id="484aa-205">Stage the UE-V Agent installation file AgentSetup.exe on a network share to which users have Read permission.</span></span>

2.  <span data-ttu-id="484aa-206">將腳本部署到安裝 UE-V Agent 的使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="484aa-206">Deploy a script to user computers that installs the UE-V Agent.</span></span> <span data-ttu-id="484aa-207">此腳本應指定設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="484aa-207">The script should specify the settings storage location.</span></span>

<span data-ttu-id="484aa-208">**部署選項：** 安裝 UE-V Agent 時，請務必使用正確的變數格式。</span><span class="sxs-lookup"><span data-stu-id="484aa-208">**Deployment options:** Be sure to use the correct variable format when you install the UE-V Agent.</span></span> <span data-ttu-id="484aa-209">下表提供使用 AgentSetup.exe 或 Windows Installer （.msi）檔案之部署選項的範例。</span><span class="sxs-lookup"><span data-stu-id="484aa-209">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="484aa-210">部署類型</span><span class="sxs-lookup"><span data-stu-id="484aa-210">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="484aa-211">部署描述</span><span class="sxs-lookup"><span data-stu-id="484aa-211">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="484aa-212">範例</span><span class="sxs-lookup"><span data-stu-id="484aa-212">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-213">命令提示字元</span><span class="sxs-lookup"><span data-stu-id="484aa-213">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-214">當您在命令提示字元安裝 UE-V Agent 時，請使用 <em> % ^ username% </em> 變數格式。</span><span class="sxs-lookup"><span data-stu-id="484aa-214">When you install the UE-V Agent at a command prompt, use the <em>%^username%</em> variable format.</span></span> <span data-ttu-id="484aa-215">如果由於設定儲存路徑中有空格而需要引號，請使用批次腳本檔案進行部署。</span><span class="sxs-lookup"><span data-stu-id="484aa-215">If quotation marks are required because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-216">批次處理腳本</span><span class="sxs-lookup"><span data-stu-id="484aa-216">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-217">當您從批次腳本檔案安裝 UE-V Agent 時，請使用 <em> %% username%% </em> 變數格式。</span><span class="sxs-lookup"><span data-stu-id="484aa-217">When you install the UE-V Agent from a batch script file, use the <em>%%username%%</em> variable format.</span></span> <span data-ttu-id="484aa-218">如果您使用這個安裝方法，您必須使用%% 字元來轉義變數。</span><span class="sxs-lookup"><span data-stu-id="484aa-218">If you use this installation method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="484aa-219">如果沒有此字元，腳本會 <em> </em> 在安裝時（而不是在執行時間）展開使用者名稱變數，而不是在執行時間，這會讓 ue-v 針對所有使用者使用單一的設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="484aa-219">Without this character, the script expands the <em>username</em> variable at installation time, rather than at run time, which causes UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-220">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="484aa-220">Windows PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-221">當您從 Windows PowerShell 提示或 Windows PowerShell 腳本安裝 UE-V Agent 時，請使用 <em> % username% </em> 變數格式。</span><span class="sxs-lookup"><span data-stu-id="484aa-221">When you install the UE-V Agent from a Windows PowerShell prompt or a Windows PowerShell script, use the <em>%username%</em> variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-222">電子軟體發佈，例如部署 Configuration Manager 軟體部署</span><span class="sxs-lookup"><span data-stu-id="484aa-222">Electronic software distribution, such as deployment of Configuration Manager Software Deployment</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-223">當您使用 Configuration Manager 安裝 UE-V Agent 時，請使用 <em> ^% username ^% </em> 變數格式。</span><span class="sxs-lookup"><span data-stu-id="484aa-223">When you install the UE-V Agent by using Configuration Manager, use the <em>^%username^%</em> variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="484aa-224">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-224">Note</span></span>**  
<span data-ttu-id="484aa-225">UE-V Agent 的安裝需要系統管理員許可權，且電腦必須重新開機，才能執行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-225">The installation of the UE-V Agent requires administrator rights, and the computer requires a restart before the UE-V Agent can run.</span></span>



### <a href="" id="params"></a><span data-ttu-id="484aa-226">UE-V Agent 部署的命令列參數</span><span class="sxs-lookup"><span data-stu-id="484aa-226">Command-line parameters for UE-V Agent deployment</span></span>

<span data-ttu-id="484aa-227">UE-V Agent 的命令列參數如下所示。</span><span class="sxs-lookup"><span data-stu-id="484aa-227">The command-line parameters of the UE-V Agent are as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="484aa-228">命令列參數</span><span class="sxs-lookup"><span data-stu-id="484aa-228">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="484aa-229">定義</span><span class="sxs-lookup"><span data-stu-id="484aa-229">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="484aa-230">附註</span><span class="sxs-lookup"><span data-stu-id="484aa-230">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-231">/help 或/h 或/？</span><span class="sxs-lookup"><span data-stu-id="484aa-231">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-232">顯示 [AgentSetup.exe 用法] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="484aa-232">Displays the AgentSetup.exe usage dialog box.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-233">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="484aa-233">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-234">指示定義儲存位置設定的通用命名慣例（UNC）路徑。</span><span class="sxs-lookup"><span data-stu-id="484aa-234">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="484aa-235">重要</span><span class="sxs-lookup"><span data-stu-id="484aa-235">Important</span></span></strong><br/><p><span data-ttu-id="484aa-236">您必須在 UE-V 2.1 和 UE-V 2.1 SP1 中指定 SettingsStoragePath。</span><span class="sxs-lookup"><span data-stu-id="484aa-236">You must specify a SettingsStoragePath in UE-V 2.1 and UE-V 2.1 SP1.</span></span> <span data-ttu-id="484aa-237">您可以設定 AdHomePath 字串，以指定使用使用者&#39;s Active Directory 主路徑。</span><span class="sxs-lookup"><span data-stu-id="484aa-237">You can set the AdHomePath string to specify that the user&#39;s Active Directory home path is used.</span></span> <span data-ttu-id="484aa-238">例如，<code>SettingsStoragePath = \share\path|AdHomePath</code>。</span><span class="sxs-lookup"><span data-stu-id="484aa-238">For example, <code>SettingsStoragePath = \share\path|AdHomePath</code>.</span></span></p>
<p><span data-ttu-id="484aa-239">在 UE-V 2.0 中，您可以將 SettingsStoragePath 保留為空白，以改用 Active Directory 的主路徑。</span><span class="sxs-lookup"><span data-stu-id="484aa-239">In UE-V 2.0, you can leave SettingsStoragePath blank to use the Active Directory home path instead.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="484aa-240">已接受% username% 或% computername% 環境變數。</span><span class="sxs-lookup"><span data-stu-id="484aa-240">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="484aa-241">腳本可能需要轉義變數。</span><span class="sxs-lookup"><span data-stu-id="484aa-241">Scripting can require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="484aa-242">預設值 </strong> ： &lt; 無&gt;</span><span class="sxs-lookup"><span data-stu-id="484aa-242">Default</strong>: &lt;none&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-243">SettingsStoragePathReg</span><span class="sxs-lookup"><span data-stu-id="484aa-243">SettingsStoragePathReg</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-244">在安裝期間從註冊表取得 SettingsStoragePath 值。</span><span class="sxs-lookup"><span data-stu-id="484aa-244">Gets the SettingsStoragePath value from the registry during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-245">在命令提示字元中，輸入下列範例，強迫 UE-V 使用 Active Directory 主路徑，而不是特定的 UNC。</span><span class="sxs-lookup"><span data-stu-id="484aa-245">At the command prompt, type the following example to force UE-V to use the Active Directory home path instead of a specific UNC.</span></span></p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-246">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="484aa-246">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-247">表示通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</span><span class="sxs-lookup"><span data-stu-id="484aa-247">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-248">只需要自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="484aa-248">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-249">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="484aa-249">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-250">指定是否應在安裝期間註冊預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="484aa-250">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-251">True |虛假</span><span class="sxs-lookup"><span data-stu-id="484aa-251">True | False</span></span></p>
<p><strong><span data-ttu-id="484aa-252">預設值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="484aa-252">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-253">SyncMethod</span><span class="sxs-lookup"><span data-stu-id="484aa-253">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-254">指定應該使用哪一種同步處理方法。</span><span class="sxs-lookup"><span data-stu-id="484aa-254">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-255">SyncProvider |所有</span><span class="sxs-lookup"><span data-stu-id="484aa-255">SyncProvider | None</span></span></p>
<p><strong><span data-ttu-id="484aa-256">預設值 </strong> ： SyncProvider</span><span class="sxs-lookup"><span data-stu-id="484aa-256">Default</strong>: SyncProvider</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-257">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="484aa-257">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-258">指定當它從設定儲存位置中檢索使用者設定時，電腦等待超時的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="484aa-258">Specifies the number of milliseconds that the computer waits before time-out when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="484aa-259">預設值 </strong> ：2000毫秒</span><span class="sxs-lookup"><span data-stu-id="484aa-259">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="484aa-260">（等待最長2秒）</span><span class="sxs-lookup"><span data-stu-id="484aa-260">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-261">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="484aa-261">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-262">指定是啟用還是停用 UE-V 同步處理。</span><span class="sxs-lookup"><span data-stu-id="484aa-262">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-263">True |虛假</span><span class="sxs-lookup"><span data-stu-id="484aa-263">True | False</span></span></p>
<p><strong><span data-ttu-id="484aa-264">預設值 </strong> ： True</span><span class="sxs-lookup"><span data-stu-id="484aa-264">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-265">MaxPackageSizeInBytes</span><span class="sxs-lookup"><span data-stu-id="484aa-265">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-266">在 UE-V Agent 報告檔案超過閾值時，指定設定套件檔案大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="484aa-266">Specifies a settings package file size in bytes when the UE-V Agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-267">&lt;大小&gt;</span><span class="sxs-lookup"><span data-stu-id="484aa-267">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="484aa-268">預設值 </strong> ：無（無警告閾值）</span><span class="sxs-lookup"><span data-stu-id="484aa-268">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-269">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="484aa-269">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-270">指定參與客戶經驗改進計畫的設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-270">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="484aa-271">如果設為 <strong> True </strong> ，則會將安裝程式資訊上傳到 Microsoft 客戶經驗改進計畫網站。</span><span class="sxs-lookup"><span data-stu-id="484aa-271">If set to <strong>True</strong>, installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="484aa-272">如果設定為 <strong> False </strong> ，則不會上傳任何資訊。</span><span class="sxs-lookup"><span data-stu-id="484aa-272">If set to <strong>False</strong>, no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-273">True |虛假</span><span class="sxs-lookup"><span data-stu-id="484aa-273">True | False</span></span></p>
<p><strong><span data-ttu-id="484aa-274">預設值 </strong> ： False</span><span class="sxs-lookup"><span data-stu-id="484aa-274">Default</strong>: False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-275">NoRestart</span><span class="sxs-lookup"><span data-stu-id="484aa-275">NoRestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-276">支援在安裝 UE-V Agent 之後延遲重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="484aa-276">Supports deferral of the restart of the computer after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-277">INSTALLFOLDER</span><span class="sxs-lookup"><span data-stu-id="484aa-277">INSTALLFOLDER</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-278">啟用針對 UE-V Agent 或 UE-V 發生器設定不同的安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="484aa-278">Enables a different installation folder to be set for the UE-V Agent or UE-V Generator.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-279">MUENABLED</span><span class="sxs-lookup"><span data-stu-id="484aa-279">MUENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-280">讓安裝程式接受 Microsoft Update 程式中包含的選項。</span><span class="sxs-lookup"><span data-stu-id="484aa-280">Enables Setup to accept the option to be included in the Microsoft Update program.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="484aa-281">ACCEPTLICENSETERMS</span><span class="sxs-lookup"><span data-stu-id="484aa-281">ACCEPTLICENSETERMS</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-282">讓 UE-V 可以自行安裝。</span><span class="sxs-lookup"><span data-stu-id="484aa-282">Lets UE-V be installed silently.</span></span> <span data-ttu-id="484aa-283">必須將此屬性設為 <strong> True </strong> ，才能自行安裝 ue-v，並略過使用者接受 ue-v 授權條款的需求。</span><span class="sxs-lookup"><span data-stu-id="484aa-283">This must be set to <strong>True</strong> to install UE-V silently and bypass the requirement that the user accepts the UE-V license terms.</span></span> <span data-ttu-id="484aa-284">如果設定為 <strong> False </strong> 或保留空白，使用者就會收到錯誤訊息，而且沒有安裝 ue-v。</span><span class="sxs-lookup"><span data-stu-id="484aa-284">If set to <strong>False</strong> or left empty, the user receives an error message and UE-V is not installed.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="484aa-285">重要</span><span class="sxs-lookup"><span data-stu-id="484aa-285">Important</span></span></strong><br/><p><span data-ttu-id="484aa-286">此參數是自行安裝 UE-V 所必需的。</span><span class="sxs-lookup"><span data-stu-id="484aa-286">This parameter is required to install UE-V silently.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="484aa-287">NORESTART</span><span class="sxs-lookup"><span data-stu-id="484aa-287">NORESTART</span></span></p></td>
<td align="left"><p><span data-ttu-id="484aa-288">在安裝 UE-V Agent 之後，避免強制重新開機。</span><span class="sxs-lookup"><span data-stu-id="484aa-288">Prevents a mandatory restart after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="484aa-289">更新 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="484aa-289">Update the UE-V Agent</span></span>

<span data-ttu-id="484aa-290">UE-V Agent 軟體的更新是透過 Microsoft Update 提供的。</span><span class="sxs-lookup"><span data-stu-id="484aa-290">Updates for the UE-V Agent software are provided through Microsoft Update.</span></span> <span data-ttu-id="484aa-291">您可以使用企業軟體發佈（ESD）基礎結構系統來部署 UE-V Agent 更新。</span><span class="sxs-lookup"><span data-stu-id="484aa-291">You can deploy UE-V Agent updates by using Enterprise Software Distribution (ESD) infrastructure systems.</span></span>

<span data-ttu-id="484aa-292">在 UE-V Agent 升級期間，您可以更新常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。</span><span class="sxs-lookup"><span data-stu-id="484aa-292">During a UE-V Agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings can be updated.</span></span>

### <span data-ttu-id="484aa-293">升級 UE-V a.x 代理程式</span><span class="sxs-lookup"><span data-stu-id="484aa-293">Upgrade the UE-V 2.x Agent</span></span>

<span data-ttu-id="484aa-294">UE-V a.x Agent 會引進許多新功能，並修改代理程式將內容上傳到設定儲存空間共用的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="484aa-294">The UE-V 2.x Agent introduces many new features and modifies how and when the agent uploads content to the settings storage share.</span></span> <span data-ttu-id="484aa-295">升級程式會自動執行這些變更。</span><span class="sxs-lookup"><span data-stu-id="484aa-295">The upgrade process automates these changes.</span></span> <span data-ttu-id="484aa-296">若要升級 UE-V Agent，請在使用者的電腦上執行 UE-V Agent 安裝套件（AgentSetup.exe、AgentSetupx86.msi 或 AgentSetupx64.msi）。</span><span class="sxs-lookup"><span data-stu-id="484aa-296">To upgrade the UE-V Agent, run the UE-V Agent install package (AgentSetup.exe, AgentSetupx86.msi, or AgentSetupx64.msi) on users’ computers.</span></span>

**<span data-ttu-id="484aa-297">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-297">Note</span></span>**  
<span data-ttu-id="484aa-298">當您升級 UE-V Agent 時，您必須使用已安裝舊版 UE-V Agent 的相同安裝程式類型（.exe 檔案或 .msi 資料包）。</span><span class="sxs-lookup"><span data-stu-id="484aa-298">When you upgrade the UE-V Agent, you must use the same installer type (.exe file or .msi packet) that installed the previous UE-V Agent.</span></span> <span data-ttu-id="484aa-299">例如，使用 UE-V 2 AgentSetup.exe 升級使用 AgentSetup.exe 安裝的 UE-V 1.0 Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-299">For example, use the UE-V 2 AgentSetup.exe to upgrade UE-V 1.0 Agents that were installed by using AgentSetup.exe.</span></span>



<span data-ttu-id="484aa-300">當代理程式安裝程式執行時，會保留下列配置：</span><span class="sxs-lookup"><span data-stu-id="484aa-300">The following configurations are preserved when the Agent Setup program runs:</span></span>

-   <span data-ttu-id="484aa-301">設定儲存路徑</span><span class="sxs-lookup"><span data-stu-id="484aa-301">Settings storage path</span></span>

-   <span data-ttu-id="484aa-302">登錄設定</span><span class="sxs-lookup"><span data-stu-id="484aa-302">Registry settings</span></span>

-   <span data-ttu-id="484aa-303">排程的任務（間隔設定會重設為預設值）</span><span class="sxs-lookup"><span data-stu-id="484aa-303">Scheduled tasks (Interval settings are reset to their defaults)</span></span>

**<span data-ttu-id="484aa-304">注意</span><span class="sxs-lookup"><span data-stu-id="484aa-304">Note</span></span>**  
<span data-ttu-id="484aa-305">在 UE-V 1.0 Agent 中註冊的 UE-V a.x 設定位置範本的電腦，會在 Windows 事件記錄檔中註冊錯誤。</span><span class="sxs-lookup"><span data-stu-id="484aa-305">A computer with UE-V 2.x settings location templates that are registered in the UE-V 1.0 Agent register errors in the Windows Event Log.</span></span>



<span data-ttu-id="484aa-306">您可以使用 Microsoft System Center 2012 Configuration Manager 或其他企業軟體發佈工具來自動化並散佈 UE-V Agent 升級。</span><span class="sxs-lookup"><span data-stu-id="484aa-306">You can use Microsoft System Center 2012 Configuration Manager or another enterprise software distribution tool to automate and distribute the UE-V Agent upgrade.</span></span>

<span data-ttu-id="484aa-307">**建議：** 我們建議您升級計算環境中的所有 UE-V 1.0 Agent，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="484aa-307">**Recommendations:** We recommend that you upgrade all of the UE-V 1.0 Agents in a computing environment, but it is not required.</span></span> <span data-ttu-id="484aa-308">UE-V a.x 設定位置範本可以與 UE-V 1.0 Agent 互動，因為它們只會共用設定儲存路徑中的設定。</span><span class="sxs-lookup"><span data-stu-id="484aa-308">UE-V 2.x settings location templates can interact with a UE-V 1.0 Agent because they only share the settings from the settings storage path.</span></span> <span data-ttu-id="484aa-309">不過，我們建議您將部署移至單一的代理程式版本，以簡化管理並支援 UE-V。</span><span class="sxs-lookup"><span data-stu-id="484aa-309">We recommend, however, that you move the deployments to a single agent version to simplify management and to support UE-V.</span></span>

### <span data-ttu-id="484aa-310">升級失敗之後，請修復 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="484aa-310">Repair the UE-V Agent after an unsuccessful upgrade</span></span>

<span data-ttu-id="484aa-311">嘗試下列其中一項操作後，您可能會遇到錯誤：</span><span class="sxs-lookup"><span data-stu-id="484aa-311">You might experience errors after you attempt one of the following operations:</span></span>

-   <span data-ttu-id="484aa-312">從 UE-V 1.0 升級到 UE-V 2</span><span class="sxs-lookup"><span data-stu-id="484aa-312">Upgrade from UE-V 1.0 to UE-V 2</span></span>

-   <span data-ttu-id="484aa-313">升級至較新版本的 Windows，例如從 Windows 7 移至 Windows 8 或從 Windows 8 升級至 Windows 8.1。</span><span class="sxs-lookup"><span data-stu-id="484aa-313">Upgrade to a newer version of Windows, for example, from Windows 7 to Windows 8 or from Windows 8 to Windows 8.1.</span></span>

-   <span data-ttu-id="484aa-314">升級 UE-V Agent 之後卸載代理程式</span><span class="sxs-lookup"><span data-stu-id="484aa-314">Uninstall the agent after upgrading the UE-V Agent</span></span>

<span data-ttu-id="484aa-315">若要解決任何問題，請嘗試在安裝代理程式的電腦上的命令提示字元中輸入這個命令來修復 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="484aa-315">To resolve any issues, attempt to repair the UE-V Agent by entering this command at a command prompt on the computer where the agent is installed.</span></span>

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

<span data-ttu-id="484aa-316">然後，您可以安裝較新版的 UE-V Agent 來重試卸載程式或升級。</span><span class="sxs-lookup"><span data-stu-id="484aa-316">You can then retry the uninstall process or upgrade by installing the newer version of the UE-V Agent.</span></span>






## <span data-ttu-id="484aa-317">相關主題</span><span class="sxs-lookup"><span data-stu-id="484aa-317">Related topics</span></span>


[<span data-ttu-id="484aa-318">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="484aa-318">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="484aa-319">部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="484aa-319">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









