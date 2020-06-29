---
title: 使用 UE-V 產生器建立 UE-V 設定位置範本
description: 使用 UE-V 產生器建立 UE-V 設定位置範本
author: dansimp
ms.assetid: b8e50e2f-0cc6-4f74-bb48-c471fefdc7d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ef7e3e5d00a95b9fcfc426207ce04f928cc0ebbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811877"
---
# <span data-ttu-id="a8cf4-103">使用 UE-V 產生器建立 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="a8cf4-103">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="a8cf4-104">Microsoft 使用者體驗虛擬化（UE-V）使用*設定位置範本*來在使用者電腦之間漫遊應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-104">Microsoft User Experience Virtualization (UE-V) uses *settings location templates* to roam application settings between user computers.</span></span> <span data-ttu-id="a8cf4-105">某些標準設定位置範本包含在使用者體驗虛擬化中。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-105">Some standard settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="a8cf4-106">您也可以使用 UE-V 發生器建立、編輯或驗證自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="a8cf4-107">UE-V 發生器會監視應用程式，以探索和捕獲應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="a8cf4-108">受監視的應用程式必須是傳統的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-108">The application that is being monitored must be a traditional application.</span></span> <span data-ttu-id="a8cf4-109">UE-V 發生器無法從下列應用程式類型建立設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="a8cf4-109">The UE-V Generator cannot create a settings location template from the following application types:</span></span>

-   <span data-ttu-id="a8cf4-110">虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="a8cf4-110">Virtualized applications</span></span>

-   <span data-ttu-id="a8cf4-111">透過終端服務提供的應用程式</span><span class="sxs-lookup"><span data-stu-id="a8cf4-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="a8cf4-112">JAVA 應用程式</span><span class="sxs-lookup"><span data-stu-id="a8cf4-112">Java applications</span></span>

-   <span data-ttu-id="a8cf4-113">Windows 8 應用程式</span><span class="sxs-lookup"><span data-stu-id="a8cf4-113">Windows 8 applications</span></span>

<span data-ttu-id="a8cf4-114">**記事** UE-V 範本無法從虛擬化應用程式或終端服務應用程式建立。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-114">**Note** UE-V templates cannot be created from virtualized applications or terminal services applications.</span></span> <span data-ttu-id="a8cf4-115">不過，您可以將使用範本同步處理的設定套用至這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-115">However, settings synchronized using the templates can be applied to those applications.</span></span> <span data-ttu-id="a8cf4-116">若要建立支援虛擬桌面基礎結構（VDI）和終端服務應用程式的範本，請使用 UE-V 發生器開啟 Windows Installer 檔案（.msi）版本的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-116">To create templates that support Virtual Desktop Infrastructure (VDI) and terminal services applications, open a Windows Installer File (.msi) version of the application with UE-V Generator.</span></span>

 

**<span data-ttu-id="a8cf4-117">排除的位置</span><span class="sxs-lookup"><span data-stu-id="a8cf4-117">Excluded Locations</span></span>**

<span data-ttu-id="a8cf4-118">探索程式會排除一些位置，這些位置通常會儲存應用程式軟體檔案，而這些檔案在使用者電腦或環境之間無法順利漫遊。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-118">The discovery process excludes locations which commonly store application software files that do not roam well between user computers or environments.</span></span> <span data-ttu-id="a8cf4-119">以下是不包括的專案：</span><span class="sxs-lookup"><span data-stu-id="a8cf4-119">The following are excluded:</span></span>

-   <span data-ttu-id="a8cf4-120">HKEY \ _CURRENT \ _USER 登錄的使用者無法寫入值的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="a8cf4-120">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="a8cf4-121">HKEY \ _CURRENT \ _USER 與 Windows 作業系統核心功能相關聯的登錄機碼和檔案</span><span class="sxs-lookup"><span data-stu-id="a8cf4-121">HKEY\_CURRENT\_USER registry keys and files associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="a8cf4-122">位於 HKEY \ _LOCAL \ _MACHINE hive 中的所有登錄機碼</span><span class="sxs-lookup"><span data-stu-id="a8cf4-122">All registry keys located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="a8cf4-123">位於 [Program Files] 目錄中的檔案</span><span class="sxs-lookup"><span data-stu-id="a8cf4-123">Files located in Program Files directories</span></span>

-   <span data-ttu-id="a8cf4-124">檔案位於使用者 \\ [使用者名稱 \] \] \\ AppData \\ LocalLow</span><span class="sxs-lookup"><span data-stu-id="a8cf4-124">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="a8cf4-125">Windows 作業系統檔案位於% systemroot%</span><span class="sxs-lookup"><span data-stu-id="a8cf4-125">Windows operating system files located in %systemroot%</span></span>

<span data-ttu-id="a8cf4-126">如果您需要儲存在這些排除位置的登錄機碼和檔案，才能漫遊應用程式設定，管理員可以在範本建立程式期間，手動將位置新增到 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-126">If registry keys and files stored in these excluded locations are required in order to roam application settings, administrators can manually add the locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="a8cf4-127">建立 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="a8cf4-127">Create UE-V templates</span></span>


<span data-ttu-id="a8cf4-128">使用 UE-V 發生器來建立商務用應用程式或其他應用程式的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-128">Use the UE-V Generator to create settings location templates for line-of-business applications or other applications.</span></span> <span data-ttu-id="a8cf4-129">在建立應用程式的範本之後，您可以將範本部署到電腦，讓使用者可以漫遊該應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-129">After the template for an application is created, you can deploy the template to computers so users can roam the settings for that application.</span></span>

**<span data-ttu-id="a8cf4-130">使用 UE-V 發生器建立 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="a8cf4-130">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="a8cf4-131">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-131">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="a8cf4-132">按一下 [**建立設定位置] 範本**。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-132">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="a8cf4-133">指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-133">Specify the application.</span></span> <span data-ttu-id="a8cf4-134">流覽至應用程式（.exe）的檔案路徑，或是您想要建立設定位置範本的應用程式快捷方式（.lnk）。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-134">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="a8cf4-135">指定命令列引數（如果有的話），以及工作目錄（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-135">Specify the command line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="a8cf4-136">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-136">Click **Next** to continue.</span></span>

    <span data-ttu-id="a8cf4-137">**記事** 在應用程式啟動之前，系統會顯示**使用者帳戶控制**的提示。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-137">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="a8cf4-138">必須具備許可權，才能監視應用程式用來儲存設定的登錄和檔案位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-138">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="a8cf4-139">應用程式啟動後，請關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-139">After the application starts, close the application.</span></span> <span data-ttu-id="a8cf4-140">UE-V 發生器會記錄應用程式儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-140">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="a8cf4-141">處理常式完成後，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-141">After the process is complete, click **Next** to continue.</span></span>

6.  <span data-ttu-id="a8cf4-142">查看並選取適當的登錄位置及設定檔案位置旁的核取方塊，以供此應用程式漫遊。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-142">Review and select the check boxes next to the appropriate registry settings locations and settings file locations to roam for this application.</span></span> <span data-ttu-id="a8cf4-143">此清單包含下列兩個類別的設定位置：</span><span class="sxs-lookup"><span data-stu-id="a8cf4-143">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="a8cf4-144">**標準**：儲存在登錄中的 [HKEY \ _CURRENT \ _USER] 索引卷名或 **[使用者名稱**\]] 下的檔案資料夾中的應用程式設定，請**AppData**  \\  **漫遊**。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-144">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="a8cf4-145">UE-V 發生器預設會包含這些設定。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-145">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="a8cf4-146">**非標準**：儲存在設定資料儲存最佳做法中所指定位置以外的應用程式設定（選用）。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-146">**Nonstandard**: Application settings that are stored outside the locations specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="a8cf4-147">其中包括 [**使用者**] \\ [使用者名稱 \] \\ **AppData**Local] 下的檔案和資料夾  \\  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-147">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="a8cf4-148">請查看這些位置，判斷是否要在 [設定位置] 範本中包含這些位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-148">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="a8cf4-149">選取 [位置] 核取方塊以包含它們。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-149">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="a8cf4-150">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-150">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="a8cf4-151">針對 [設定位置] 範本，查看及編輯任何**屬性** **、登錄位置及\*\*\*\*檔案位置。**</span><span class="sxs-lookup"><span data-stu-id="a8cf4-151">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="a8cf4-152">在 [**屬性**] 索引標籤上編輯下列屬性：</span><span class="sxs-lookup"><span data-stu-id="a8cf4-152">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="a8cf4-153">**應用程式名稱**：已寫入程式檔案屬性描述的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-153">**Application Name**: The application name written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="a8cf4-154">**程式名稱**：從程式檔案屬性中取得的程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-154">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="a8cf4-155">這個名稱通常具有 .exe 副檔名。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-155">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="a8cf4-156">**產品版本**：應用程式 .exe 檔案的產品版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-156">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="a8cf4-157">這個屬性與檔案版本搭配使用，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-157">This property, in conjunction with the File version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="a8cf4-158">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-158">This property accepts a major version number.</span></span> <span data-ttu-id="a8cf4-159">如果這個屬性是空的，設定位置範本會套用至所有版本的產品。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-159">If this property is empty, the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="a8cf4-160">**檔版本**：應用程式 the.exe 檔案的檔案版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-160">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="a8cf4-161">這個屬性會與產品版本搭配使用，協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-161">This property, in conjunction with the Product version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="a8cf4-162">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-162">This property accepts a major version number.</span></span> <span data-ttu-id="a8cf4-163">如果這個屬性是空的，設定位置範本會套用至所有版本的程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-163">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="a8cf4-164">**範本作者名稱**（選用）：設定位置範本作者的名稱。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-164">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="a8cf4-165">**範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-165">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="a8cf4-166">[**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-166">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="a8cf4-167">使用 [**任務**] 下拉式功能表來編輯登錄位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-167">Edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="a8cf4-168">工作包括新增金鑰、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-168">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry where the keys are located.</span></span> <span data-ttu-id="a8cf4-169">使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-169">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="a8cf4-170">使用 [**所有設定] 和 [子項**]，將所有的登錄設定都包含在指定的索引鍵、子項和子項設定底下。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-170">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="a8cf4-171">[**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案遮罩。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-171">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="a8cf4-172">使用 [**任務**] 下拉式功能表來編輯檔案位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-172">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="a8cf4-173">檔案位置的工作包括新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-173">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="a8cf4-174">將檔案遮罩保留為空白，以包含指定資料夾中的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-174">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="a8cf4-175">按一下 [**建立**]，然後將 [設定位置] 範本儲存在電腦上。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-175">Click **Create** and save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="a8cf4-176">按一下 [**關閉**]，關閉 [設定範本] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-176">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="a8cf4-177">退出 UE-V 發生器應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-177">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="a8cf4-178">在您為應用程式建立設定位置範本之後，您應該測試該範本。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-178">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="a8cf4-179">在實驗室環境中部署範本，然後將它放入企業中的生產環境。</span><span class="sxs-lookup"><span data-stu-id="a8cf4-179">Deploy the template in a lab environment before putting it into production in the enterprise.</span></span>

## <span data-ttu-id="a8cf4-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="a8cf4-180">Related topics</span></span>


[<span data-ttu-id="a8cf4-181">使用自訂 UE-V 範本與 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="a8cf4-181">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="a8cf4-182">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="a8cf4-182">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





