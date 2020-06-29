---
title: 使用 UE-V 產生器編輯 UE-V 設定位置範本
description: 使用 UE-V 產生器編輯 UE-V 設定位置範本
author: dansimp
ms.assetid: da78f9c8-1624-4111-8c96-79db7224bd0b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b90cd58761e6ac40c089f3afeade3c445a52ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812159"
---
# <span data-ttu-id="07342-103">使用 UE-V 產生器編輯 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="07342-103">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="07342-104">使用 Microsoft 使用者經驗虛擬化（UE-V）發生器編輯設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="07342-104">Use the Microsoft User Experience Virtualization (UE-V) Generator to edit settings location templates.</span></span> <span data-ttu-id="07342-105">當使用 UE-V 發生器將修訂的設定新增到範本時，範本內的版本資訊會自動更新，以確保企業中部署的任何現有範本都能正確更新。</span><span class="sxs-lookup"><span data-stu-id="07342-105">When the revised settings are added to the templates using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates deployed in the enterprise are updated correctly.</span></span>

**<span data-ttu-id="07342-106">如何使用 UE-V 發生器編輯 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="07342-106">How to edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="07342-107">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft 使用者體驗虛擬化**]，然後按一下 [ **microsoft 使用者體驗虛擬化發生器**]。</span><span class="sxs-lookup"><span data-stu-id="07342-107">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="07342-108">按一下 [**編輯設定位置範本**]。</span><span class="sxs-lookup"><span data-stu-id="07342-108">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="07342-109">在最近使用的範本清單中，選取要編輯的範本。</span><span class="sxs-lookup"><span data-stu-id="07342-109">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="07342-110">或者，**流覽**至 [設定] 範本檔案。</span><span class="sxs-lookup"><span data-stu-id="07342-110">Alternatively, **Browse** to the settings template file.</span></span> <span data-ttu-id="07342-111">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="07342-111">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="07342-112">查看設定範本的**屬性** **、登錄**位置**及檔案**位置。</span><span class="sxs-lookup"><span data-stu-id="07342-112">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="07342-113">視需要編輯。</span><span class="sxs-lookup"><span data-stu-id="07342-113">Edit as needed.</span></span>

    -   <span data-ttu-id="07342-114">[**屬性**] 索引標籤可讓您查看及編輯下列屬性：</span><span class="sxs-lookup"><span data-stu-id="07342-114">The **Properties** tab allows you to view and edit the following properties:</span></span>

        -   <span data-ttu-id="07342-115">**應用程式名稱**：寫入程式檔案屬性描述的應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="07342-115">**Application name**: The application name written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="07342-116">**程式名稱**：從程式檔案屬性中取得的程式名稱。</span><span class="sxs-lookup"><span data-stu-id="07342-116">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="07342-117">這個名稱通常具有 .exe 副檔名。</span><span class="sxs-lookup"><span data-stu-id="07342-117">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="07342-118">**產品版本**：應用程式 .exe 檔案的產品版本號碼。</span><span class="sxs-lookup"><span data-stu-id="07342-118">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="07342-119">這個屬性與檔案**版本**，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="07342-119">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="07342-120">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="07342-120">This property accepts a major version number.</span></span> <span data-ttu-id="07342-121">如果此屬性為空白，則會將設定位置範本套用至所有版本的產品。</span><span class="sxs-lookup"><span data-stu-id="07342-121">If this property is empty, then the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="07342-122">**檔版本**：應用程式 the.exe 檔案的檔案版本號碼。</span><span class="sxs-lookup"><span data-stu-id="07342-122">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="07342-123">這個屬性和**產品版本**，可協助判斷設定位置範本所針對的是哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="07342-123">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="07342-124">這個屬性接受主要版本號碼。</span><span class="sxs-lookup"><span data-stu-id="07342-124">This property accepts a major version number.</span></span> <span data-ttu-id="07342-125">如果這個屬性是空的，設定位置範本會套用至所有版本的程式。</span><span class="sxs-lookup"><span data-stu-id="07342-125">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="07342-126">**範本作者名稱**（選用）：設定範本作者的名稱。</span><span class="sxs-lookup"><span data-stu-id="07342-126">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="07342-127">**範本作者電子郵件**（選用）：設定位置範本作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="07342-127">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="07342-128">[**登錄] 索引**標籤會列出 [設定位置] 範本中所包含的登錄位置**金鑰**和**範圍**。</span><span class="sxs-lookup"><span data-stu-id="07342-128">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="07342-129">您可以使用 [**任務**] 下拉式功能表來編輯登錄位置。</span><span class="sxs-lookup"><span data-stu-id="07342-129">You can edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="07342-130">工作包括新增金鑰、編輯現有金鑰的名稱或範圍、刪除金鑰，以及流覽金鑰所在的註冊表。</span><span class="sxs-lookup"><span data-stu-id="07342-130">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry in which the keys are located.</span></span> <span data-ttu-id="07342-131">當您定義註冊表的範圍時，您可以使用**All 設定**範圍，將所有的登錄設定都包含在指定的索引鍵底下。</span><span class="sxs-lookup"><span data-stu-id="07342-131">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="07342-132">使用 [**所有設定**] 和 [子機] **，將所有**的登錄設定都包含在指定的索引鍵、子機和子項設定底下。</span><span class="sxs-lookup"><span data-stu-id="07342-132">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="07342-133">[**檔案] 索引**標籤會列出 [設定位置] 範本中所包含之檔案位置的檔案路徑和檔案遮罩。</span><span class="sxs-lookup"><span data-stu-id="07342-133">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="07342-134">您可以使用 [**任務**] 下拉式功能表來編輯檔案位置。</span><span class="sxs-lookup"><span data-stu-id="07342-134">You can edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="07342-135">檔案位置的工作包括新增檔案或資料夾位置、編輯現有檔案或資料夾的範圍、刪除檔案或資料夾，以及在 Windows 資源管理器中開啟所選的位置。</span><span class="sxs-lookup"><span data-stu-id="07342-135">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="07342-136">若要包含指定資料夾中的所有檔案，請將檔案遮罩保留為空白。</span><span class="sxs-lookup"><span data-stu-id="07342-136">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="07342-137">按一下 [**儲存**]，將變更儲存到 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="07342-137">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="07342-138">按一下 [**關閉**]，關閉 [設定範本] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="07342-138">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="07342-139">退出 UE-V 發生器應用程式。</span><span class="sxs-lookup"><span data-stu-id="07342-139">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="07342-140">在編輯應用程式的設定位置範本之後，您應該測試範本。</span><span class="sxs-lookup"><span data-stu-id="07342-140">After editing the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="07342-141">在實驗室環境中部署已修改的設定位置範本，然後將它放入企業中的生產環境。</span><span class="sxs-lookup"><span data-stu-id="07342-141">Deploy the revised settings location template in a lab environment before putting it into production in the enterprise.</span></span>

**<span data-ttu-id="07342-142">如何手動編輯設定位置範本</span><span class="sxs-lookup"><span data-stu-id="07342-142">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="07342-143">建立 [設定位置] 範本（.xml 檔案）的本機複本。</span><span class="sxs-lookup"><span data-stu-id="07342-143">Create a local copy of the settings location template (.xml file).</span></span> <span data-ttu-id="07342-144">UE-V 設定位置範本是 .xml 檔案，可識別應用程式儲存設定值的位置。</span><span class="sxs-lookup"><span data-stu-id="07342-144">UE-V settings location templates are .xml files identifying the locations where application store settings values.</span></span>

2.  <span data-ttu-id="07342-145">使用 XML 編輯器開啟 [設定位置] 範本檔。</span><span class="sxs-lookup"><span data-stu-id="07342-145">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="07342-146">編輯設定位置範本檔。</span><span class="sxs-lookup"><span data-stu-id="07342-146">Edit the settings location template file.</span></span> <span data-ttu-id="07342-147">所有變更必須符合 SettingsLocationTempate 中定義的 UE-V 架構檔案。</span><span class="sxs-lookup"><span data-stu-id="07342-147">All changes must conform to the UE-V schema file defined in SettingsLocationTempate.xsd.</span></span> <span data-ttu-id="07342-148">Xsd 檔案的複本預設位於中 `\ProgramData\Microsoft\UEV\Templates` 。</span><span class="sxs-lookup"><span data-stu-id="07342-148">A copy of the .xsd file is located in `\ProgramData\Microsoft\UEV\Templates` by default.</span></span>

4.  <span data-ttu-id="07342-149">儲存 [設定位置] 範本檔案，然後關閉 [XML 編輯器]。</span><span class="sxs-lookup"><span data-stu-id="07342-149">Save the settings location template file and close the XML editor.</span></span>

5.  <span data-ttu-id="07342-150">使用 UE-V 發生器驗證已修改的設定位置範本檔。</span><span class="sxs-lookup"><span data-stu-id="07342-150">Validate the modified settings location template file with the UE-V Generator.</span></span> <span data-ttu-id="07342-151">如需使用 UE-V 發生器驗證的詳細資訊，請參閱[使用 Ue-v 發生器驗證 Ue-v 設定位置範本](validate-ue-v-settings-location-templates-with-ue-v-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="07342-151">For more information about validating with the UE-V Generator, see [Validate UE-V Settings Location Templates with UE-V Generator](validate-ue-v-settings-location-templates-with-ue-v-generator.md).</span></span>

## <span data-ttu-id="07342-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="07342-152">Related topics</span></span>


[<span data-ttu-id="07342-153">使用自訂 UE-V 範本與 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="07342-153">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="07342-154">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="07342-154">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





