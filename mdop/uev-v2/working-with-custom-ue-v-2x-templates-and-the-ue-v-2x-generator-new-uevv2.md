---
title: 使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機
description: 使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機
author: dansimp
ms.assetid: f0bb4920-0132-472c-a564-abf06a884275
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8d863896e4ccfa92161f8a8f5e2b8955f139872
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802158"
---
# <span data-ttu-id="1d1df-103">使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機</span><span class="sxs-lookup"><span data-stu-id="1d1df-103">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="1d1df-104">若要在使用者電腦之間同步處理應用程式設定，Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 使用*設定位置範本*。</span><span class="sxs-lookup"><span data-stu-id="1d1df-104">To synchronize application settings between user computers, Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use *settings location templates*.</span></span> <span data-ttu-id="1d1df-105">某些設定位置範本包含在使用者體驗虛擬化中。</span><span class="sxs-lookup"><span data-stu-id="1d1df-105">Some settings location templates are included in User Experience Virtualization.</span></span> <span data-ttu-id="1d1df-106">您也可以使用 UE-V 發生器來建立、編輯或驗證自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-106">You can also create, edit, or validate custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="1d1df-107">UE-V 發生器會監視 Windows 桌面應用程式，以探索並捕獲應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-107">The UE-V Generator monitors Windows desktop applications to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="1d1df-108">受監視的應用程式必須是桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-108">The application that is monitored must be a desktop application.</span></span> <span data-ttu-id="1d1df-109">UE-V 發生器無法為下列應用程式類型建立設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="1d1df-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="1d1df-110">虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="1d1df-110">Virtualized applications</span></span>

-   <span data-ttu-id="1d1df-111">透過終端服務提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="1d1df-111">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="1d1df-112">JAVA 應用程式</span><span class="sxs-lookup"><span data-stu-id="1d1df-112">Java applications</span></span>

-   <span data-ttu-id="1d1df-113">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="1d1df-113">Windows apps</span></span>

<span data-ttu-id="1d1df-114">本主題</span><span class="sxs-lookup"><span data-stu-id="1d1df-114">This topic</span></span>

<span data-ttu-id="1d1df-115">**標準和非標準的設定位置：** UE-V 發生器可協助您識別應用程式搜尋設定檔案的位置，以及應用程式用來儲存設定資訊的註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-115">**Standard and Nonstandard settings locations:** The UE-V Generator helps you identify where applications search for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="1d1df-116">發生器只會探索標準使用者可存取之位置中的設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-116">The generator only discovers settings in locations that are accessible to a standard user.</span></span> <span data-ttu-id="1d1df-117">儲存在其他位置的設定會被排除。</span><span class="sxs-lookup"><span data-stu-id="1d1df-117">Settings that are stored in other locations are excluded.</span></span> <span data-ttu-id="1d1df-118">已發現的設定會分為兩個類別：**標準**和**非標準**。</span><span class="sxs-lookup"><span data-stu-id="1d1df-118">Discovered settings are grouped into two categories: **Standard** and **Non-standard**.</span></span> <span data-ttu-id="1d1df-119">建議使用標準設定來進行同步處理，而 UE-V 可以隨時捕獲並套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-119">Standard settings are recommended for synchronization, and UE-V can readily capture and apply them.</span></span> <span data-ttu-id="1d1df-120">非標準設定可能會同步處理設定，但由於 UE-V 使用的規則，這些設定可能不會持續或 dependably 同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-120">Non-standard settings can potentially synchronize settings but, because of the rules that UE-V uses, these settings might not consistently or dependably synchronize settings.</span></span> <span data-ttu-id="1d1df-121">這些設定可能會依賴臨時檔案、導致不可靠的同步處理，或者可能不會有用處。</span><span class="sxs-lookup"><span data-stu-id="1d1df-121">These settings might depend on temporary files, result in unreliable synchronization, or might not be useful.</span></span> <span data-ttu-id="1d1df-122">這些設定位置會顯示在 UE-V 發生器中。</span><span class="sxs-lookup"><span data-stu-id="1d1df-122">These settings locations are presented in the UE-V Generator.</span></span> <span data-ttu-id="1d1df-123">您可以選擇在每個案例中包含或排除它們。</span><span class="sxs-lookup"><span data-stu-id="1d1df-123">You can choose to include or exclude them on a case-by-case basis.</span></span>

<span data-ttu-id="1d1df-124">UE-V 發生器會在探索程式中開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-124">The UE-V Generator opens the application as part of the discovery process.</span></span> <span data-ttu-id="1d1df-125">發生器可以在下列位置捕獲設定：</span><span class="sxs-lookup"><span data-stu-id="1d1df-125">The generator can capture settings in the following locations:</span></span>

-   <span data-ttu-id="1d1df-126">[**註冊表設定**]-[HKEY \] 下的 [註冊表位置] **_CURRENT \ _USER**</span><span class="sxs-lookup"><span data-stu-id="1d1df-126">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="1d1df-127">**應用程式設定**檔案–儲存在 \**使用者**\ \ [使用者名稱 \] 中的檔案檔案是**AppData*\*  \\  **漫遊**</span><span class="sxs-lookup"><span data-stu-id="1d1df-127">**Application Settings Files** – Files that are stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="1d1df-128">UE-V 發生器會排除位置，這些位置通常會儲存應用程式軟體檔案，但在使用者電腦或環境之間無法正常同步處理。</span><span class="sxs-lookup"><span data-stu-id="1d1df-128">The UE-V Generator excludes locations, which commonly store application software files, but do not synchronize well between user computers or environments.</span></span> <span data-ttu-id="1d1df-129">UE-V 發生器會將這些位置排除在一起。</span><span class="sxs-lookup"><span data-stu-id="1d1df-129">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="1d1df-130">[排除的位置] 如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d1df-130">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="1d1df-131">HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="1d1df-131">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="1d1df-132">HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="1d1df-132">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="1d1df-133">位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼，都需要系統管理員許可權，而且可能需要設定使用者帳戶控制（UAC）合約</span><span class="sxs-lookup"><span data-stu-id="1d1df-133">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive, which requires administrator rights and might require to set a User Account Control (UAC) agreement</span></span>

-   <span data-ttu-id="1d1df-134">位於 [Program Files] 目錄中的檔案，需要系統管理員許可權，而且可能需要設定 UAC 合約</span><span class="sxs-lookup"><span data-stu-id="1d1df-134">Files that are located in Program Files directories, which requires administrator rights and might require to set a UAC agreement</span></span>

-   <span data-ttu-id="1d1df-135">位於 [使用者] \\ [User name \] \\ AppData \\ LocalLow] 底下的檔案</span><span class="sxs-lookup"><span data-stu-id="1d1df-135">Files that are located under Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="1d1df-136">在% Systemroot% 中的 Windows 作業系統檔案，需要系統管理員許可權，而且可能需要設定 UAC 合約</span><span class="sxs-lookup"><span data-stu-id="1d1df-136">Windows operating system files that are located in %Systemroot%, which requires administrator rights and might require to set a UAC agreement</span></span>

<span data-ttu-id="1d1df-137">如果您在這些位置儲存的登錄機碼和檔案需要同步處理應用程式設定，您可以在範本建立程式期間將排除的位置手動新增到 [設定位置] 範本（HKEY \ _LOCAL \ _MACHINE hive 中的登錄專案除外）。</span><span class="sxs-lookup"><span data-stu-id="1d1df-137">If registry keys and files that are stored in these locations are required to synchronize application settings, you can manually add the excluded locations to the settings location template during the template creation process (except for registry entries in the HKEY\_LOCAL\_MACHINE hive).</span></span>

## <a href="" id="edit"></a><span data-ttu-id="1d1df-138">使用 UE-V 發生器編輯設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-138">Edit Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="1d1df-139">使用 UE-V 發生器編輯設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-139">Use the UE-V Generator to edit settings location templates.</span></span> <span data-ttu-id="1d1df-140">當您使用 UE-V 發生器將修訂的設定新增到範本時，範本內的版本資訊會自動更新，以確保在企業中部署的任何現有範本都能正確更新。</span><span class="sxs-lookup"><span data-stu-id="1d1df-140">When the revised settings are added to the templates by using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates that are deployed in the enterprise are updated correctly.</span></span>

<span data-ttu-id="1d1df-141">**記事** 如果您使用 UE-V 2 發生器編輯 UE-V 1.0 範本，則範本會自動轉換為 UE-V 2 範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-141">**Note** If you edit a UE-V 1.0 template by using the UE-V 2 Generator, the template is automatically converted to a UE-V 2 template.</span></span> <span data-ttu-id="1d1df-142">UE-V 1.0 Agent 將無法再使用編輯過的範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-142">UE-V 1.0 Agents can no longer use the edited template.</span></span>

 

**<span data-ttu-id="1d1df-143">使用 UE-V 發生器編輯 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-143">To edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="1d1df-144">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-144">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="1d1df-145">按一下 [**編輯設定位置範本**]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-145">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="1d1df-146">在最近使用的範本清單中，選取要編輯的範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-146">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="1d1df-147">或者，按一下 **[流覽]** 以搜尋設定範本檔。</span><span class="sxs-lookup"><span data-stu-id="1d1df-147">Alternatively, click **Browse** to search for the settings template file.</span></span> <span data-ttu-id="1d1df-148">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="1d1df-148">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="1d1df-149">查看設定範本的**屬性** **、登錄**位置**及檔案**位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-149">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="1d1df-150">根據需要進行編輯。</span><span class="sxs-lookup"><span data-stu-id="1d1df-150">Edit as required.</span></span>

    -   <span data-ttu-id="1d1df-151">在 [**屬性**] 索引標籤上，您可以查看及編輯下列屬性：</span><span class="sxs-lookup"><span data-stu-id="1d1df-151">On the **Properties** tab, you can view and edit the following properties:</span></span>

        -   <span data-ttu-id="1d1df-152">**應用程式名稱**：已寫入程式檔案屬性描述的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="1d1df-152">**Application name**: The application name that is written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="1d1df-153">**程式名稱**：從程式檔案屬性提取的程式名稱。</span><span class="sxs-lookup"><span data-stu-id="1d1df-153">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="1d1df-154">這個名稱通常具有 .exe 副檔名。</span><span class="sxs-lookup"><span data-stu-id="1d1df-154">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="1d1df-155">**產品版本**：應用程式 .exe 檔案的產品版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1d1df-155">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="1d1df-156">這個屬性與檔案**版本**，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-156">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="1d1df-157">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1d1df-157">This property accepts a major version number.</span></span> <span data-ttu-id="1d1df-158">如果此屬性為空白，則 [設定位置] 範本會套用至所有版本的產品。</span><span class="sxs-lookup"><span data-stu-id="1d1df-158">If this property is empty, then the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="1d1df-159">[檔案**版本**]：應用程式 .exe 檔案的檔案版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1d1df-159">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="1d1df-160">這個屬性和**產品版本**，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-160">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="1d1df-161">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="1d1df-161">This property accepts a major version number.</span></span> <span data-ttu-id="1d1df-162">如果這個屬性是空的，設定位置範本會套用至所有版本的程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-162">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="1d1df-163">**範本作者名稱**（選用）：設定範本作者的名稱。</span><span class="sxs-lookup"><span data-stu-id="1d1df-163">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="1d1df-164">**範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1d1df-164">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="1d1df-165">[**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。</span><span class="sxs-lookup"><span data-stu-id="1d1df-165">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="1d1df-166">您可以使用 [**任務**] 下拉式功能表來編輯註冊表位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-166">You can edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="1d1df-167">在 [工作] 功能表中，您可以新增索引鍵、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。</span><span class="sxs-lookup"><span data-stu-id="1d1df-167">In the Tasks menu, you can add new keys, edit the name or scope of existing keys, delete keys, and browse the registry in which the keys are located.</span></span> <span data-ttu-id="1d1df-168">當您定義註冊表的範圍時，您可以使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。</span><span class="sxs-lookup"><span data-stu-id="1d1df-168">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="1d1df-169">使用 [**所有設定**] 和 [子機] **，將所有**的登錄設定都包含在指定的索引鍵、子機和子項設定底下。</span><span class="sxs-lookup"><span data-stu-id="1d1df-169">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="1d1df-170">[**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案檢測。</span><span class="sxs-lookup"><span data-stu-id="1d1df-170">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="1d1df-171">您可以使用 [**任務**] 下拉式功能表來編輯檔案位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-171">You can edit the file locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="1d1df-172">**在檔案位置的 [工作**] 功能表中，您可以新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-172">In the **Tasks** menu for file locations, you can add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="1d1df-173">若要包含指定資料夾中的所有檔案，請將檔案遮罩保留為空白。</span><span class="sxs-lookup"><span data-stu-id="1d1df-173">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="1d1df-174">按一下 [**儲存**]，將變更儲存到 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-174">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="1d1df-175">按一下 [**關閉**]，關閉 [設定範本] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="1d1df-175">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="1d1df-176">退出 UE-V 發生器應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-176">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="1d1df-177">在您編輯應用程式的設定位置範本後，您應該測試該範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-177">After you edit the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="1d1df-178">在實驗室環境中部署已修改的設定位置範本，然後再將它放入企業中的生產環境。</span><span class="sxs-lookup"><span data-stu-id="1d1df-178">Deploy the revised settings location template in a lab environment before you put it into production in the enterprise.</span></span>

**<span data-ttu-id="1d1df-179">如何手動編輯設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-179">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="1d1df-180">建立 [設定位置] 範本 .xml 檔案的本機複本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-180">Create a local copy of the settings location template .xml file.</span></span> <span data-ttu-id="1d1df-181">UE-V 設定位置範本是 .xml 檔案，可識別應用程式儲存設定值的位置。</span><span class="sxs-lookup"><span data-stu-id="1d1df-181">UE-V settings location templates are .xml files that identify the locations where application store settings values.</span></span>

    <span data-ttu-id="1d1df-182">**記事** 因為範本**識別碼**，所以設定位置範本是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d1df-182">**Note** A settings location template is unique because of the template **ID**.</span></span> <span data-ttu-id="1d1df-183">如果您複製範本並重新命名 .xml 檔案，範本註冊會失敗，因為 UE-V 會讀取 .xml 檔案中的範本**識別碼**標記，以判斷該名稱，而非 .xml 檔案的檔案名。</span><span class="sxs-lookup"><span data-stu-id="1d1df-183">If you copy the template and rename the .xml file, template registration fails because UE-V reads the template **ID** tag in the .xml file to determine the name, not the file name of the .xml file.</span></span> <span data-ttu-id="1d1df-184">UE-V 也會讀取**版本**號碼，以瞭解是否有任何變更。</span><span class="sxs-lookup"><span data-stu-id="1d1df-184">UE-V also reads the **Version** number to know if anything has changed.</span></span> <span data-ttu-id="1d1df-185">如果版本號碼較高，則 UE-V 會更新範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-185">If the version number is higher, UE-V updates the template.</span></span>

     

2.  <span data-ttu-id="1d1df-186">使用 XML 編輯器開啟 [設定位置] 範本檔。</span><span class="sxs-lookup"><span data-stu-id="1d1df-186">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="1d1df-187">編輯設定位置範本檔。</span><span class="sxs-lookup"><span data-stu-id="1d1df-187">Edit the settings location template file.</span></span> <span data-ttu-id="1d1df-188">所有變更必須符合[SettingsLocationTempate](https://technet.microsoft.com/library/dn763947.aspx)中定義的 ue-v 架構檔案。</span><span class="sxs-lookup"><span data-stu-id="1d1df-188">All changes must conform to the UE-V schema file that is defined in [SettingsLocationTempate.xsd](https://technet.microsoft.com/library/dn763947.aspx).</span></span> <span data-ttu-id="1d1df-189">根據預設，.xsd 檔案的複本位於 \\ProgramData\\Microsoft\\UEV\\Templates。</span><span class="sxs-lookup"><span data-stu-id="1d1df-189">By default, a copy of the .xsd file is located in \\ProgramData\\Microsoft\\UEV\\Templates.</span></span>

4.  <span data-ttu-id="1d1df-190">增加 [設定位置] 範本的**版本**號碼。</span><span class="sxs-lookup"><span data-stu-id="1d1df-190">Increment the **Version** number for the settings location template.</span></span>

5.  <span data-ttu-id="1d1df-191">儲存 [設定位置] 範本檔案，然後關閉 [XML 編輯器]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-191">Save the settings location template file, and then close the XML editor.</span></span>

6.  <span data-ttu-id="1d1df-192">使用 UE-V 發生器驗證已修改的設定位置範本檔。</span><span class="sxs-lookup"><span data-stu-id="1d1df-192">Validate the modified settings location template file by using the UE-V Generator.</span></span>

7.  <span data-ttu-id="1d1df-193">您必須先註冊已編輯的 UE-V 設定位置範本，才能在用戶端電腦之間同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-193">You must register the edited UE-V settings location template before it can synchronize settings between client computers.</span></span> <span data-ttu-id="1d1df-194">若要註冊範本，請開啟 Windows PowerShell，然後執行下列 Cmdlet： `update-uevtemplate [templatefilename]` 。</span><span class="sxs-lookup"><span data-stu-id="1d1df-194">To register a template, open Windows PowerShell, and then run the following cmdlet: `update-uevtemplate [templatefilename]`.</span></span> <span data-ttu-id="1d1df-195">然後，您可以將檔案複製到 [設定儲存目錄]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-195">You can then copy the file to the settings storage catalog.</span></span> <span data-ttu-id="1d1df-196">接著，使用者電腦上的 UE-V Agent，就應該在排程的工作中以排程的方式更新。</span><span class="sxs-lookup"><span data-stu-id="1d1df-196">The UE-V Agent on users’ computers should then update as scheduled in the scheduled task.</span></span>

## <a href="" id="validate"></a><span data-ttu-id="1d1df-197">使用 UE-V 發生器驗證設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-197">Validate Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="1d1df-198">您可以在 XML 編輯器中建立或編輯設定位置範本，而不需要使用 UE-V 發生器。</span><span class="sxs-lookup"><span data-stu-id="1d1df-198">It is possible to create or edit settings location templates in an XML editor without using the UE-V Generator.</span></span> <span data-ttu-id="1d1df-199">如果您這樣做，您可以使用 UE-V 發生器來驗證新的或修改過的 XML 與已針對範本定義的架構相符。</span><span class="sxs-lookup"><span data-stu-id="1d1df-199">If you do, you can use the UE-V Generator to validate that the new or revised XML matches the schema that has been defined for the template.</span></span>

**<span data-ttu-id="1d1df-200">使用 UE-V 發生器驗證 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-200">To validate a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="1d1df-201">按一下 [**開始**]，指向 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-201">Click **Start**, point to **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="1d1df-202">按一下 [**驗證設定位置] 範本**。</span><span class="sxs-lookup"><span data-stu-id="1d1df-202">Click **Validate a settings location template**.</span></span>

3.  <span data-ttu-id="1d1df-203">在最近使用的範本清單中，選取要編輯的範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-203">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="1d1df-204">或者，您也可以流覽至 [設定 **]** 範本檔案。</span><span class="sxs-lookup"><span data-stu-id="1d1df-204">Alternatively, you can **Browse** to the settings template file.</span></span> <span data-ttu-id="1d1df-205">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="1d1df-205">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="1d1df-206">按一下 [**驗證**] 以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="1d1df-206">Click **Validate** to continue.</span></span>

5.  <span data-ttu-id="1d1df-207">按一下 [**關閉**]，關閉 [設定範本] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="1d1df-207">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="1d1df-208">退出 UE-V 發生器應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d1df-208">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="1d1df-209">驗證應用程式的設定位置範本後，您應該測試範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-209">After you validate the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="1d1df-210">將範本部署到實驗室環境，然後將它放入企業中的生產環境。</span><span class="sxs-lookup"><span data-stu-id="1d1df-210">Deploy the template in a lab environment before you put it into a production environment in enterprise.</span></span>

## <a href="" id="share"></a><span data-ttu-id="1d1df-211">使用範本庫共用設定位置範本</span><span class="sxs-lookup"><span data-stu-id="1d1df-211">Share Settings Location Templates with the Template Gallery</span></span>


<span data-ttu-id="1d1df-212">Microsoft 使用者體驗虛擬化（UE-V）2.0 範本庫可讓系統管理員共用其 UE-V 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-212">The Microsoft User Experience Virtualization (UE-V) 2.0 template gallery enables administrators to share their UE-V settings location templates.</span></span> <span data-ttu-id="1d1df-213">您可以在圖庫中上傳您的設定位置範本供其他使用者使用，而且您可以下載其他使用者已建立的範本。</span><span class="sxs-lookup"><span data-stu-id="1d1df-213">In the gallery, you can upload your settings location templates for other users to use, and you can download templates that other users have created.</span></span> <span data-ttu-id="1d1df-214">UE-V 範本庫位於 Microsoft TechNet 上的 [在[這裡](https://go.microsoft.com/fwlink/p/?LinkId=246589)]。</span><span class="sxs-lookup"><span data-stu-id="1d1df-214">The UE-V template gallery is located on Microsoft TechNet [here](https://go.microsoft.com/fwlink/p/?LinkId=246589).</span></span>

<span data-ttu-id="1d1df-215">在 UE-V 範本圖庫上共用設定位置範本前，請確定它不包含任何個人或公司資訊。</span><span class="sxs-lookup"><span data-stu-id="1d1df-215">Before you share a settings location template on the UE-V template gallery, ensure it does not contain any personal or company information.</span></span> <span data-ttu-id="1d1df-216">您可以使用任何 XML 檢視器來開啟及查看設定位置範本檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="1d1df-216">You can use any XML viewer to open and view the contents of a settings location template file.</span></span> <span data-ttu-id="1d1df-217">在您與公司以外的任何人共用範本前，請先檢查下列範本值。</span><span class="sxs-lookup"><span data-stu-id="1d1df-217">The following template values should be reviewed before you share a template with anyone outside your company.</span></span>

-   <span data-ttu-id="1d1df-218">範本作者名稱–指定範本作者名稱的一般、非鑒別名稱，或從範本中排除此資料。</span><span class="sxs-lookup"><span data-stu-id="1d1df-218">Template Author Name – Specify a general, non-identifying name for the template author name or exclude this data from the template.</span></span>

-   <span data-ttu-id="1d1df-219">範本作者電子郵件：指定一般、非鑒別範本作者電子郵件，或從範本中排除此資料。</span><span class="sxs-lookup"><span data-stu-id="1d1df-219">Template Author Email – Specify a general, non-identifying template author email or exclude this data from the template.</span></span>

<span data-ttu-id="1d1df-220">在您部署從 UE-V 圖庫下載的任何設定位置範本之前，您應該先測試範本，以確保應用程式設定能在測試環境中正確同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1d1df-220">Before you deploy any settings location template that you have downloaded from the UE-V gallery, you should first test the template to ensure that the application settings synchronize settings correctly in a test environment.</span></span>






## <span data-ttu-id="1d1df-221">相關主題</span><span class="sxs-lookup"><span data-stu-id="1d1df-221">Related topics</span></span>


[<span data-ttu-id="1d1df-222">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="1d1df-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="1d1df-223">部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="1d1df-223">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





