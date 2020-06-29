---
title: 為 UE-V 準備您的環境
description: 為 UE-V 準備您的環境
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810682"
---
# <span data-ttu-id="1c799-103">為 UE-V 準備您的環境</span><span class="sxs-lookup"><span data-stu-id="1c799-103">Preparing Your Environment for UE-V</span></span>


<span data-ttu-id="1c799-104">Microsoft 使用者體驗虛擬化（UE-V）使用設定儲存位置在電腦之間漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="1c799-104">Microsoft User Experience Virtualization (UE-V) roams settings between computers by the use of a settings storage location.</span></span> <span data-ttu-id="1c799-105">[設定] 儲存位置是檔案共用，應該在 UE-V Agent 部署期間進行設定。</span><span class="sxs-lookup"><span data-stu-id="1c799-105">The settings storage location is a file share and should be configured during the UE-V Agent deployment.</span></span> <span data-ttu-id="1c799-106">它必須定義為 [設定儲存位置] 或 [作為 Active Directory 主目錄]。</span><span class="sxs-lookup"><span data-stu-id="1c799-106">It must be defined either as a settings storage location or as an Active Directory home directory.</span></span> <span data-ttu-id="1c799-107">此外，系統管理員還應該將時間伺服器設定為支援一致的同步處理。</span><span class="sxs-lookup"><span data-stu-id="1c799-107">In addition, the administrator should configure a time server to support consistent synchronization.</span></span> <span data-ttu-id="1c799-108">若要為 UE-V 準備您的環境，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="1c799-108">To prepare your environment for UE-V, you should consider the following:</span></span>

-   <span data-ttu-id="1c799-109">[Ue-v 設定儲存空間](#bkmk-uevsettingsstorage)：</span><span class="sxs-lookup"><span data-stu-id="1c799-109">[UE-V Settings Storage](#bkmk-uevsettingsstorage):</span></span>

    -   [<span data-ttu-id="1c799-110">定義設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="1c799-110">Defining a Settings Storage Location</span></span>](#bkmk-definingsettingsstoragelocation)

    -   [<span data-ttu-id="1c799-111">使用 Active Directory 主目錄與 UE-V</span><span class="sxs-lookup"><span data-stu-id="1c799-111">Using Active Directory Home Directory with UE-V</span></span>](#bkmk-usingactivedirectoryhomedirectory)

-   [<span data-ttu-id="1c799-112">同步處理 UE-V 設定同步處理電腦的時鐘</span><span class="sxs-lookup"><span data-stu-id="1c799-112">Synchronize Computer Clocks for UE-V Settings Synchronization</span></span>](#bkmk-synchronizecomputerclocks)

-   [<span data-ttu-id="1c799-113">效能與容量規劃</span><span class="sxs-lookup"><span data-stu-id="1c799-113">Performance and Capacity Planning</span></span>](#bkmk-performancecapacityplanning)

<span data-ttu-id="1c799-114">如需作業系統和電腦需求的詳細資訊，請參閱[ue-v 1.0 支援的](supported-configurations-for-ue-v-10.md)設定。</span><span class="sxs-lookup"><span data-stu-id="1c799-114">For more information about operating system and computer requirements, see [Supported Configurations for UE-V 1.0](supported-configurations-for-ue-v-10.md).</span></span>

## <a href="" id="bkmk-uevsettingsstorage"></a><span data-ttu-id="1c799-115">UE-V 設定儲存空間</span><span class="sxs-lookup"><span data-stu-id="1c799-115">UE-V settings storage</span></span>


<span data-ttu-id="1c799-116">您可以在下列其中一種設定中定義 [使用者體驗虛擬化設定] 儲存空間： [設定儲存位置] 或 [Active Directory 主目錄]。</span><span class="sxs-lookup"><span data-stu-id="1c799-116">You can define the User Experience Virtualization settings storage in one of two configurations: a settings storage location or an Active Directory home directory.</span></span>

### <a href="" id="bkmk-definingsettingsstoragelocation"></a><span data-ttu-id="1c799-117">定義設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="1c799-117">Define a settings storage location</span></span>

<span data-ttu-id="1c799-118">UE-V 設定儲存位置是一個可由 UE-V 使用者存取的標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="1c799-118">The UE-V settings storage location is a standard network share that is accessible by UE-V users.</span></span> <span data-ttu-id="1c799-119">您必須先建立根目錄，才能定義設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1c799-119">Before you define the settings storage location, you must create a root directory.</span></span> <span data-ttu-id="1c799-120">將在共用上儲存設定的使用者，必須擁有儲存位置的讀/寫許可權。</span><span class="sxs-lookup"><span data-stu-id="1c799-120">Users who will store settings on the share must have read/write permissions to the storage location.</span></span> <span data-ttu-id="1c799-121">UE-V Agent 將在這個根目錄下建立使用者專用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="1c799-121">The UE-V Agent will create user-specific folders under this root directory.</span></span> <span data-ttu-id="1c799-122">設定儲存位置是透過設定**SettingsStoragePath**配置選項來定義。</span><span class="sxs-lookup"><span data-stu-id="1c799-122">The settings storage location is defined by setting the **SettingsStoragePath** configuration option.</span></span> <span data-ttu-id="1c799-123">此選項可以使用下列方式進行設定：</span><span class="sxs-lookup"><span data-stu-id="1c799-123">This option can be configured in the following ways:</span></span>

-   <span data-ttu-id="1c799-124">透過命令列參數或在批次腳本中安裝 UE-V agent 期間。</span><span class="sxs-lookup"><span data-stu-id="1c799-124">During the installation of the UE-V agent through a command-line parameter or in a batch script.</span></span>

-   <span data-ttu-id="1c799-125">使用 [群組原則]。</span><span class="sxs-lookup"><span data-stu-id="1c799-125">Using Group Policy.</span></span>

-   <span data-ttu-id="1c799-126">安裝之後，請使用 PowerShell 或 WMI。</span><span class="sxs-lookup"><span data-stu-id="1c799-126">After installation, by using PowerShell or WMI.</span></span>

<span data-ttu-id="1c799-127">路徑必須位於伺服器和共用的通用命名慣例（UNC）路徑中。</span><span class="sxs-lookup"><span data-stu-id="1c799-127">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="1c799-128">例如， **\\\\server\\settingsshare\\**。</span><span class="sxs-lookup"><span data-stu-id="1c799-128">For example, **\\\\server\\settingsshare\\**.</span></span> <span data-ttu-id="1c799-129">這個設定選項支援使用變數來啟用特定的漫遊案例。</span><span class="sxs-lookup"><span data-stu-id="1c799-129">This configuration option supports the use of variables to enable specific roaming scenarios.</span></span>

<span data-ttu-id="1c799-130">您可以將 `%username%` 變數與伺服器的 UNC 路徑搭配使用並共用。</span><span class="sxs-lookup"><span data-stu-id="1c799-130">You can use the `%username%` variable with the UNC path of the server and share.</span></span> <span data-ttu-id="1c799-131">這將在使用者登入的所有電腦或會話上提供相同的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="1c799-131">This will provide the same settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="1c799-132">在下列情況下，請考慮進行這項設定：</span><span class="sxs-lookup"><span data-stu-id="1c799-132">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="1c799-133">企業中的使用者有多個相似設定的物理電腦，且每個使用者的設定在所有電腦上都應該是相同的。</span><span class="sxs-lookup"><span data-stu-id="1c799-133">Users in the enterprise have multiple, similarly configured physical computers and each user’s settings should be the same across all computers.</span></span>

2.  <span data-ttu-id="1c799-134">企業中的使用者使用虛擬桌面基礎結構（VDI）池，這些設定應該在每個使用者的 VDI 會話中保留。</span><span class="sxs-lookup"><span data-stu-id="1c799-134">Users in the enterprise use virtual desktop infrastructure (VDI) pools where settings should be retained across each user’s VDI sessions.</span></span>

3.  <span data-ttu-id="1c799-135">企業中的使用者有一部物理電腦，另外也使用 VDI。</span><span class="sxs-lookup"><span data-stu-id="1c799-135">Users in the enterprise have one physical computer and additionally use a VDI.</span></span> <span data-ttu-id="1c799-136">無論是使用物理電腦或 VDI 會話，每個使用者的設定體驗都應該是一樣的。</span><span class="sxs-lookup"><span data-stu-id="1c799-136">Each user’s settings experience should be the same whether using the physical computer or VDI session.</span></span>

4.  <span data-ttu-id="1c799-137">有多個企業電腦是由多個使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1c799-137">Multiple enterprise computers are used by multiple users.</span></span> <span data-ttu-id="1c799-138">每個使用者的設定體驗在所有電腦上應該都是相同的。</span><span class="sxs-lookup"><span data-stu-id="1c799-138">Each user’s settings experience should be the same across all computers.</span></span>

<span data-ttu-id="1c799-139">您可以將 **%username%\\%computername%** 變數與伺服器的 UNC 路徑搭配使用，然後共用。</span><span class="sxs-lookup"><span data-stu-id="1c799-139">You can use the **%username%\\%computername%** variables with the UNC path of the server and share.</span></span> <span data-ttu-id="1c799-140">這將會保留每個電腦的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="1c799-140">This will preserve the settings experience for each computer.</span></span> <span data-ttu-id="1c799-141">在下列情況下，請考慮進行這項設定：</span><span class="sxs-lookup"><span data-stu-id="1c799-141">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="1c799-142">企業中的使用者有多個物理電腦，而且您想要保留每個電腦的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="1c799-142">Users in the enterprise have multiple physical computers and you want to preserve the settings experience for each computer.</span></span>

2.  <span data-ttu-id="1c799-143">企業電腦是由多個使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1c799-143">The enterprise computers are used by multiple users.</span></span> <span data-ttu-id="1c799-144">針對使用者登入的每一台電腦，都應該保留設定體驗。</span><span class="sxs-lookup"><span data-stu-id="1c799-144">The settings experience should be preserved for each computer that the user logs into.</span></span>

<span data-ttu-id="1c799-145">UE-V agent 會根據 UE-V `SettingsStoragePath` 設定及定義的變數，動態建立使用者專用的設定儲存路徑。</span><span class="sxs-lookup"><span data-stu-id="1c799-145">The UE-V agent dynamically creates the user-specific settings storage path based on a UE-V `SettingsStoragePath` configuration setting and the variables that are defined.</span></span>

<span data-ttu-id="1c799-146">UE-V agent 會動態建立一個 `SettingsPackages` 在每個使用者特定儲存位置中指定的隱藏系統資料夾。</span><span class="sxs-lookup"><span data-stu-id="1c799-146">The UE-V agent dynamically creates a hidden system folder named `SettingsPackages` within each user-specific storage location.</span></span> <span data-ttu-id="1c799-147">UE-V agent 會讀取並將設定寫入此位置，如已註冊的 UE-V 設定位置範本所定義。</span><span class="sxs-lookup"><span data-stu-id="1c799-147">The UE-V agent reads and writes settings to this location as defined by registered UE-V settings location templates.</span></span>

<span data-ttu-id="1c799-148">如果使用者的一組受管理電腦的設定儲存位置相同，適用的 UE-V 設定是由「上次寫入 wins」規則所決定。</span><span class="sxs-lookup"><span data-stu-id="1c799-148">If the settings storage location is the same for a set of managed computers of a user, the applicable UE-V settings are determined by a “Last write wins” rule.</span></span> <span data-ttu-id="1c799-149">在一部電腦上執行的代理程式會讀取並寫入到 [設定] 位置，而不受在其他電腦上執行的代理程式的影響。</span><span class="sxs-lookup"><span data-stu-id="1c799-149">The agent that runs on one computer reads and writes to the settings location independently of agents that run on other computers.</span></span> <span data-ttu-id="1c799-150">[上次寫入的設定] 和 [值] 是下一個代理程式從 [設定] 儲存位置讀取時所套用的設定。</span><span class="sxs-lookup"><span data-stu-id="1c799-150">The last settings and values written are the settings that are applied when the next agent reads from the settings storage location.</span></span> <span data-ttu-id="1c799-151">如需詳細資訊，請參閱[部署 ue-v 1.0 的設定儲存位置](deploying-the-settings-storage-location-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="1c799-151">For more information, see [Deploying the Settings Storage Location for UE-V 1.0](deploying-the-settings-storage-location-for-ue-v-10.md).</span></span>

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a><span data-ttu-id="1c799-152">在 UE-V 使用 Active Directory 主目錄</span><span class="sxs-lookup"><span data-stu-id="1c799-152">Use Active Directory home directory with UE-V</span></span>

<span data-ttu-id="1c799-153">如果在部署代理時沒有為 UE-V 設定設定儲存位置，則會使用使用者的 Active Directory （AD）主目錄來儲存設定位置套件。</span><span class="sxs-lookup"><span data-stu-id="1c799-153">If no settings storage location is configured for UE-V when the agent is deployed, then the user’s Active Directory (AD) home directory is used to store settings location packages.</span></span> <span data-ttu-id="1c799-154">UE-V agent 會在每個使用者的廣告主目錄根目錄下，動態建立 [設定儲存空間] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1c799-154">The UE-V agent dynamically creates the settings storage folder below the root of the AD home directory of each user.</span></span> <span data-ttu-id="1c799-155">如果沒有另行定義設定儲存位置（SettingsStoragePath），則代理程式只會使用 Active Directory 主目錄。</span><span class="sxs-lookup"><span data-stu-id="1c799-155">The agent only uses the Active Directory home directory if a settings storage location (SettingsStoragePath) is not otherwise defined.</span></span>

## <a href="" id="bkmk-synchronizecomputerclocks"></a><span data-ttu-id="1c799-156">同步處理 UE-V 設定同步處理電腦的時鐘</span><span class="sxs-lookup"><span data-stu-id="1c799-156">Synchronize computer clocks for UE-V settings synchronization</span></span>


<span data-ttu-id="1c799-157">執行 UE-V agent 以進行同步處理設定的電腦，必須使用時間伺服器。</span><span class="sxs-lookup"><span data-stu-id="1c799-157">Computers that run the UE-V agent to synchronize settings must use a time server.</span></span> <span data-ttu-id="1c799-158">時間戳記是用來判斷是否需要從 [設定] 儲存位置同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1c799-158">Time stamps are used to determine if settings need to be synchronized from the settings storage location.</span></span> <span data-ttu-id="1c799-159">如果電腦時鐘不准確，較舊的設定會覆寫較新的設定，或者新設定可能不會儲存到設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1c799-159">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span> <span data-ttu-id="1c799-160">使用時間伺服器可讓 UE-V 維持一致的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="1c799-160">The use of a time server enables UE-V to maintain a consistent settings experience.</span></span>

## <a href="" id="bkmk-performancecapacityplanning"></a><span data-ttu-id="1c799-161">效能與容量規劃</span><span class="sxs-lookup"><span data-stu-id="1c799-161">Performance and capacity planning</span></span>


<span data-ttu-id="1c799-162">UE-V 的容量需求可透過使用標準磁片容量和網路狀況監視來決定。</span><span class="sxs-lookup"><span data-stu-id="1c799-162">Capacity requirements for UE-V can be determined by use of standard disk capacity and network health monitoring.</span></span> <span data-ttu-id="1c799-163">UE-V 使用伺服器訊息區塊（SMB）共用來儲存設定套件。</span><span class="sxs-lookup"><span data-stu-id="1c799-163">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="1c799-164">[設定] 套件的大小會根據特定應用程式的設定資訊而有所不同。</span><span class="sxs-lookup"><span data-stu-id="1c799-164">The size of settings packages varies depending on the settings information for a specific application.</span></span> <span data-ttu-id="1c799-165">雖然大部分的設定套件都很小，但同步處理可能較大的檔案（例如桌面影像），可能會導致效能較差，特別是在較慢的網路上。</span><span class="sxs-lookup"><span data-stu-id="1c799-165">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span> <span data-ttu-id="1c799-166">若要最大限度地減少網路延遲的問題，您應該在使用者電腦所在的同一個本機網路上建立設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1c799-166">To minimize problems with network latency, you should create settings storage locations on the same local networks where the users’ computers reside.</span></span>

<span data-ttu-id="1c799-167">根據預設，如果網路速度緩慢或設定套件較大，UE-V 同步處理會在2秒後超時。</span><span class="sxs-lookup"><span data-stu-id="1c799-167">By default, the UE-V synchronization will time out after 2 seconds if the network is slow or the settings package is large.</span></span> <span data-ttu-id="1c799-168">您可以使用群組原則設定超時。</span><span class="sxs-lookup"><span data-stu-id="1c799-168">You can configure the timeout with Group Policy.</span></span> <span data-ttu-id="1c799-169">如需如何設定超時的詳細資訊，請參閱[使用群組原則物件設定 ue-v](configuring-ue-v-with-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="1c799-169">For more information about how to set the timeout, see [Configuring UE-V with Group Policy Objects](configuring-ue-v-with-group-policy-objects.md).</span></span>

## <span data-ttu-id="1c799-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="1c799-170">Related topics</span></span>


[<span data-ttu-id="1c799-171">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="1c799-171">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="1c799-172">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="1c799-172">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="1c799-173">UE-V 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="1c799-173">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

 

 





