---
title: 如何設定網域使用者或群組
description: 如何設定網域使用者或群組
author: dansimp
ms.assetid: 055aba81-a9c9-4b98-969d-775e603becf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c51da13808df657c1341572767c24860d9d5e8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812212"
---
# <span data-ttu-id="04b4f-103">如何設定網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="04b4f-103">How to Configure a Domain User or Group</span></span>


<span data-ttu-id="04b4f-104">部署設定可讓您控制哪些使用者或群組可以存取 MED-V 工作區，以及可以使用 MED-V 工作區的時間長度，以及它是否可離線使用。</span><span class="sxs-lookup"><span data-stu-id="04b4f-104">The deployment settings enable you to control which users or groups can access the MED-V workspace, as well as how long the MED-V workspace can be utilized and whether it can be used offline.</span></span> <span data-ttu-id="04b4f-105">您也可以設定其他規則來控制 MED-V 工作區與主機之間的存取。</span><span class="sxs-lookup"><span data-stu-id="04b4f-105">You can also configure additional rules to control access between the MED-V workspace and the host.</span></span>

<span data-ttu-id="04b4f-106">所有的 MED-V 工作區許可權都在 [**部署**] 索引標籤上的 [**原則**] 模組中設定。</span><span class="sxs-lookup"><span data-stu-id="04b4f-106">All MED-V workspace permissions are configured in the **Policy** module, on the **Deployment** tab.</span></span>

<span data-ttu-id="04b4f-107">若要允許使用者使用 MED-V 工作區，您必須先將網域使用者或群組新增至 MED-V 工作區許可權。</span><span class="sxs-lookup"><span data-stu-id="04b4f-107">To allow users to utilize the MED-V workspace, you must first add domain users or groups to the MED-V workspace permissions.</span></span> <span data-ttu-id="04b4f-108">接著，您可以為每個使用者或群組設定許可權。</span><span class="sxs-lookup"><span data-stu-id="04b4f-108">You can then set permissions for each user or group.</span></span>

## <span data-ttu-id="04b4f-109">如何新增網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="04b4f-109">How to Add a Domain User or Group</span></span>


**<span data-ttu-id="04b4f-110">新增網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="04b4f-110">To add a domain user or group</span></span>**

1.  <span data-ttu-id="04b4f-111">在 [**使用者/群組**] 視窗中，按一下 [**新增]。**</span><span class="sxs-lookup"><span data-stu-id="04b4f-111">In the **Users / Groups** window, click **Add.**</span></span>

2.  <span data-ttu-id="04b4f-112">在 [**輸入使用者或組名**] 對話方塊中，執行下列其中一項動作，選取 [網域使用者] 或 [群組]：</span><span class="sxs-lookup"><span data-stu-id="04b4f-112">In the **Enter User or Group names** dialog box, select domain users or groups by doing one of the following:</span></span>

    -   <span data-ttu-id="04b4f-113">在 [**輸入使用者或組名**] 欄位中，輸入網域或電腦上的本機使用者或群組中存在的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="04b4f-113">In the **Enter User or Group names** field, type a user or group that exists in the domain or as a local user or group on the computer.</span></span> <span data-ttu-id="04b4f-114">然後按一下 [**檢查名稱**]，將它解析成完整的名稱。</span><span class="sxs-lookup"><span data-stu-id="04b4f-114">Then click **Check Names** to resolve it to the full existent name.</span></span>

    -   <span data-ttu-id="04b4f-115">按一下 [**尋找**] 以開啟 [標準**選取使用者或群組**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="04b4f-115">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="04b4f-116">然後選取 [網域使用者] 或 [群組]。</span><span class="sxs-lookup"><span data-stu-id="04b4f-116">Then select domain users or groups.</span></span>

3.  <span data-ttu-id="04b4f-117">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="04b4f-117">Click **OK**.</span></span>

    <span data-ttu-id="04b4f-118">新增網域使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="04b4f-118">The domain users or groups are added.</span></span>

    **<span data-ttu-id="04b4f-119">注意</span><span class="sxs-lookup"><span data-stu-id="04b4f-119">Note</span></span>**  
    <span data-ttu-id="04b4f-120">信任網域中的使用者應該手動新增。</span><span class="sxs-lookup"><span data-stu-id="04b4f-120">Users from trusted domains should be added manually.</span></span>



~~~
**Warning**  
Do not run the management application from a computer that is part of a domain that is not trusted by the domain the server is installed on.
~~~



## <span data-ttu-id="04b4f-121">如何移除網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="04b4f-121">How to Remove a Domain User or Group</span></span>


**<span data-ttu-id="04b4f-122">移除網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="04b4f-122">To remove a domain user or group</span></span>**

1.  <span data-ttu-id="04b4f-123">在 [**使用者/群組**] 視窗中，選取一個使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="04b4f-123">In the **Users / Groups** window, select a user or group.</span></span>

2.  <span data-ttu-id="04b4f-124">按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="04b4f-124">Click **Remove**.</span></span>

    <span data-ttu-id="04b4f-125">已刪除使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="04b4f-125">The user or group is deleted.</span></span>

## <span data-ttu-id="04b4f-126">如何設定使用者或群組的許可權</span><span class="sxs-lookup"><span data-stu-id="04b4f-126">How to Set Permissions for a User or a Group</span></span>


**<span data-ttu-id="04b4f-127">若要設定使用者或群組的許可權</span><span class="sxs-lookup"><span data-stu-id="04b4f-127">To set permissions for a user or a group</span></span>**

1.  <span data-ttu-id="04b4f-128">按一下您要設定許可權的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="04b4f-128">Click the user or group for which you are setting the permissions.</span></span>

2.  <span data-ttu-id="04b4f-129">按照下表所述，設定 MED-V 工作區屬性。</span><span class="sxs-lookup"><span data-stu-id="04b4f-129">Configure the MED-V workspace properties as described in the following table.</span></span>

3.  <span data-ttu-id="04b4f-130">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="04b4f-130">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="04b4f-131">工作區部署屬性</span><span class="sxs-lookup"><span data-stu-id="04b4f-131">Workspace Deployment Properties</span></span>**

<span data-ttu-id="04b4f-132">*一般*屬性描述</span><span class="sxs-lookup"><span data-stu-id="04b4f-132">Property Description *General*</span></span>

<span data-ttu-id="04b4f-133">啟用 &lt; 使用者或群組的工作區&gt;</span><span class="sxs-lookup"><span data-stu-id="04b4f-133">Enable Workspace for &lt;user or group&gt;</span></span>

<span data-ttu-id="04b4f-134">選取此核取方塊以啟用此使用者或群組的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="04b4f-134">Select this check box to enable the MED-V workspace for this user or group.</span></span>

<span data-ttu-id="04b4f-135">工作區在此日期到期</span><span class="sxs-lookup"><span data-stu-id="04b4f-135">Workspace expires on this date</span></span>

<span data-ttu-id="04b4f-136">選取此核取方塊，為此使用者或群組指派許可權集的到期日。</span><span class="sxs-lookup"><span data-stu-id="04b4f-136">Select this check box to assign an expiration date for the permissions set for this user or group.</span></span>

<span data-ttu-id="04b4f-137">選取此選項時，即會啟用 [日期] 方塊。</span><span class="sxs-lookup"><span data-stu-id="04b4f-137">When selected, the date box is enabled.</span></span> <span data-ttu-id="04b4f-138">設定日期和許可權會在指定日期結束時到期。</span><span class="sxs-lookup"><span data-stu-id="04b4f-138">Set the date, and permissions will expire at the end of the date specified.</span></span>

<span data-ttu-id="04b4f-139">[離線工作] 限制為</span><span class="sxs-lookup"><span data-stu-id="04b4f-139">Offline work is restricted to</span></span>

<span data-ttu-id="04b4f-140">選取此核取方塊，指派必須針對此使用者或群組重新整理原則的時段。</span><span class="sxs-lookup"><span data-stu-id="04b4f-140">Select this check box to assign a time period in which the policy must be refreshed for this user or group.</span></span> <span data-ttu-id="04b4f-141">選取此選項時，即會啟用 [時間週期] 方塊。</span><span class="sxs-lookup"><span data-stu-id="04b4f-141">When selected, the time period box is enabled.</span></span> <span data-ttu-id="04b4f-142">設定天數或小時數，並在指定的時間期限結束時，如果原則沒有重新整理，使用者或群組就無法連線。</span><span class="sxs-lookup"><span data-stu-id="04b4f-142">Set the number of days or hours, and at the end of the specified time period, the user or group will not be able to connect if the policy is not refreshed.</span></span>

<span data-ttu-id="04b4f-143">工作區刪除選項</span><span class="sxs-lookup"><span data-stu-id="04b4f-143">Workspace deletion options</span></span>

<span data-ttu-id="04b4f-144">按一下以設定 MED-V 工作區刪除選項。</span><span class="sxs-lookup"><span data-stu-id="04b4f-144">Click to set the MED-V workspace deletion options.</span></span> <span data-ttu-id="04b4f-145">如需詳細資訊，請參閱[如何設定 Med-v 工作區刪除選項](how-to-set-med-v-workspace-deletion-options.md)。</span><span class="sxs-lookup"><span data-stu-id="04b4f-145">For more information, see [How to Set MED-V Workspace Deletion Options](how-to-set-med-v-workspace-deletion-options.md).</span></span>

*<span data-ttu-id="04b4f-146">資料傳輸</span><span class="sxs-lookup"><span data-stu-id="04b4f-146">Data Transfer</span></span>*

<span data-ttu-id="04b4f-147">在主機和工作區之間支援剪貼簿</span><span class="sxs-lookup"><span data-stu-id="04b4f-147">Support clipboard between host and Workspace</span></span>

<span data-ttu-id="04b4f-148">選取此核取方塊可在主機與 MED-V 工作區之間啟用複製與貼上。</span><span class="sxs-lookup"><span data-stu-id="04b4f-148">Select this check box to enable copying and pasting between the host and the MED-V workspace.</span></span>

<span data-ttu-id="04b4f-149">主機與工作區之間的支援檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="04b4f-149">Support file transfer between the host and Workspace</span></span>

<span data-ttu-id="04b4f-150">選取此核取方塊以啟用在 host 與 MED-V 工作區之間傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="04b4f-150">Select this check box to enable transferring files between the host and MED-V workspace.</span></span> <span data-ttu-id="04b4f-151">從 [檔案**傳輸**] 方塊中選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="04b4f-151">Select one of the following options from the **File Transfer** box:</span></span>

-   <span data-ttu-id="04b4f-152">**兩者皆**可讓您在主機和 med-v 工作區之間傳送檔案。</span><span class="sxs-lookup"><span data-stu-id="04b4f-152">**Both**—Enable transferring files between the host and the MED-V workspace.</span></span>

-   <span data-ttu-id="04b4f-153">**主機至工作區**-可讓您從主機傳送檔案至 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="04b4f-153">**Host to Workspace**—Enable transferring files from the host to the MED-V workspace.</span></span>

-   <span data-ttu-id="04b4f-154">**主機工作區**-啟用從 med-v 工作區傳送檔案至主機。</span><span class="sxs-lookup"><span data-stu-id="04b4f-154">**Workspace to Host**—Enable transferring files from the MED-V workspace to the host.</span></span>

**<span data-ttu-id="04b4f-155">注意</span><span class="sxs-lookup"><span data-stu-id="04b4f-155">Note</span></span>**  
<span data-ttu-id="04b4f-156">如果沒有許可權的使用者嘗試傳輸檔案，系統會顯示一個視窗，提示他輸入擁有執行檔案傳輸許可權的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="04b4f-156">If a user without permissions attempts to transfer files, a window will appear prompting him to enter the credentials of a user with permissions to perform the file transfer.</span></span>



**<span data-ttu-id="04b4f-157">重要</span><span class="sxs-lookup"><span data-stu-id="04b4f-157">Important</span></span>**  
<span data-ttu-id="04b4f-158">若要在 Windows XP SP3 中支援檔案傳輸，您必須透過編輯登錄來停用離線檔案同步處理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04b4f-158">To support file transfer in Windows XP SP3, you must disable offline file synchronization by editing the registry as follows:</span></span>

`REG ADD HKLM\software\microsoft\windows\currentversion\netcache /V Enabled /T REG_DWORD /F /D 0`



<span data-ttu-id="04b4f-159">進階</span><span class="sxs-lookup"><span data-stu-id="04b4f-159">Advanced</span></span>

<span data-ttu-id="04b4f-160">按一下以設定高級檔案傳輸選項。</span><span class="sxs-lookup"><span data-stu-id="04b4f-160">Click to set the advanced file transfer options.</span></span> <span data-ttu-id="04b4f-161">如需詳細資訊，請參閱[如何設定高級檔案傳輸選項](how-to-set-advanced-file-transfer-options.md)。</span><span class="sxs-lookup"><span data-stu-id="04b4f-161">For more information, see [How to Set Advanced File Transfer Options](how-to-set-advanced-file-transfer-options.md).</span></span>

*<span data-ttu-id="04b4f-162">裝置控制</span><span class="sxs-lookup"><span data-stu-id="04b4f-162">Device Control</span></span>*

<span data-ttu-id="04b4f-163">啟用列印至連線至主機的印表機</span><span class="sxs-lookup"><span data-stu-id="04b4f-163">Enable printing to printers connected to the host</span></span>

<span data-ttu-id="04b4f-164">選取此核取方塊可讓使用者使用主機印表機從 MED-V 工作區列印。</span><span class="sxs-lookup"><span data-stu-id="04b4f-164">Select this check box to enable users to print from the MED-V workspace using the host printer.</span></span>

**<span data-ttu-id="04b4f-165">注意</span><span class="sxs-lookup"><span data-stu-id="04b4f-165">Note</span></span>**  
<span data-ttu-id="04b4f-166">列印是由主機上定義的印表機所執行。</span><span class="sxs-lookup"><span data-stu-id="04b4f-166">The printing is performed by the printers defined on the host.</span></span>



<span data-ttu-id="04b4f-167">啟用 CD/DVD 存取</span><span class="sxs-lookup"><span data-stu-id="04b4f-167">Enable access to CD / DVD</span></span>

<span data-ttu-id="04b4f-168">選取此核取方塊以允許從這個 MED-V 工作區存取 CD 或 DVD 光碟機。</span><span class="sxs-lookup"><span data-stu-id="04b4f-168">Select this check box to allow access to a CD or DVD drive from this MED-V workspace.</span></span>



**<span data-ttu-id="04b4f-169">多個成員資格</span><span class="sxs-lookup"><span data-stu-id="04b4f-169">Multiple Memberships</span></span>**

1.  <span data-ttu-id="04b4f-170">如果使用者是群組的一部分，且許可權會套用至使用者以及其所屬的群組，則會套用擁有權限。</span><span class="sxs-lookup"><span data-stu-id="04b4f-170">If the user is part of a group and permissions are applied to the user as well as to the group they are part of, all permissions are applied.</span></span>

2.  <span data-ttu-id="04b4f-171">如果使用者是兩個不同群組的成員，則會套用限制性最低的許可權。</span><span class="sxs-lookup"><span data-stu-id="04b4f-171">If the user is a member of two different groups, the least restrictive permissions are applied.</span></span>

## <span data-ttu-id="04b4f-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="04b4f-172">Related topics</span></span>


[<span data-ttu-id="04b4f-173">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="04b4f-173">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="04b4f-174">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="04b4f-174">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="04b4f-175">如何設定 MED-V 工作區刪除選項</span><span class="sxs-lookup"><span data-stu-id="04b4f-175">How to Set MED-V Workspace Deletion Options</span></span>](how-to-set-med-v-workspace-deletion-options.md)

[<span data-ttu-id="04b4f-176">如何設定進階檔案傳輸選項</span><span class="sxs-lookup"><span data-stu-id="04b4f-176">How to Set Advanced File Transfer Options</span></span>](how-to-set-advanced-file-transfer-options.md)









