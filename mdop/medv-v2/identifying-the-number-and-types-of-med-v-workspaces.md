---
title: 識別 MED-V 工作區的數量和類型
description: 識別 MED-V 工作區的數量和類型
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812249"
---
# <span data-ttu-id="5baa7-103">識別 MED-V 工作區的數量和類型</span><span class="sxs-lookup"><span data-stu-id="5baa7-103">Identifying the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="5baa7-104">MED-V 會建立虛擬環境，以執行需要 Windows XP 的應用程式，或需要與主機電腦上的版本不同的 Internet Explorer 版本。</span><span class="sxs-lookup"><span data-stu-id="5baa7-104">MED-V creates a virtual environment for running applications that require Windows XP or that require a version of Internet Explorer that differs from the version on the host computer.</span></span> <span data-ttu-id="5baa7-105">這個虛擬環境稱為 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="5baa7-105">This virtual environment is known as a MED-V workspace.</span></span>

<span data-ttu-id="5baa7-106">根據您的組織在您遷移至 Windows 7 時所面臨的應用程式相容性需求而定，只有特定使用者或部門可能需要 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="5baa7-106">Depending on the application compatibility requirements faced by your organization as you migrate to Windows 7, only certain users or departments might require MED-V workspaces.</span></span> <span data-ttu-id="5baa7-107">規劃部署時，您必須判斷企業中所需的 MED-V 工作區數目。</span><span class="sxs-lookup"><span data-stu-id="5baa7-107">As you plan your deployment, you have to determine the number of MED-V workspaces required in your enterprise.</span></span> <span data-ttu-id="5baa7-108">您也必須定義每個 MED-V 工作區的需求。</span><span class="sxs-lookup"><span data-stu-id="5baa7-108">You also have to define the requirements of each MED-V workspace.</span></span>

## <span data-ttu-id="5baa7-109">識別 MED-V 工作區的數量與類型</span><span class="sxs-lookup"><span data-stu-id="5baa7-109">Identify the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="5baa7-110">找出您企業中將建立 MED-V 工作區的電腦和群組。</span><span class="sxs-lookup"><span data-stu-id="5baa7-110">Identify the computers and groups in your enterprise for which you will be creating MED-V workspaces.</span></span> <span data-ttu-id="5baa7-111">通常，這些使用者需要存取那些無法遷移至 Windows 7 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5baa7-111">Typically, these are the users who require access to those applications that cannot be migrated to Windows 7.</span></span> <span data-ttu-id="5baa7-112">識別那些無法遷移的應用程式，以及需要 MED-V 工作區來執行這些應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="5baa7-112">Identify those applications that cannot be migrated and the users who require a MED-V workspace to run these applications.</span></span>

<span data-ttu-id="5baa7-113">您可能也有尚未針對 Windows 7 優化的 intranet 位址。</span><span class="sxs-lookup"><span data-stu-id="5baa7-113">You might also have intranet addresses that have not yet been optimized for Windows 7.</span></span> <span data-ttu-id="5baa7-114">MED-V 工作區提供 Internet Explorer 瀏覽器，讓使用者可以更好地存取那些尚未準備好用於遷移至 Windows 7 的網址。</span><span class="sxs-lookup"><span data-stu-id="5baa7-114">The MED-V workspace provides an Internet Explorer browser through which end users can better access those web addresses that are not yet ready for the migration to Windows 7.</span></span> <span data-ttu-id="5baa7-115">當您準備並規劃 MED-V 部署時，您必須先識別並編譯 URL 地址清單，才能從主機電腦上的 Internet Explorer 重新導向到 MED-V 工作區中的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="5baa7-115">As you are preparing and planning your MED-V deployment, you will have to identify and compile a list of the URL addresses to redirect from Internet Explorer on the host computer to Internet Explorer in the MED-V workspace.</span></span>

<span data-ttu-id="5baa7-116">最後，您必須評估磁碟空間需求。</span><span class="sxs-lookup"><span data-stu-id="5baa7-116">Finally, you have to evaluate your disk space requirements.</span></span> <span data-ttu-id="5baa7-117">大多數的 MED-V 工作區都是 2 gb 或更大的。</span><span class="sxs-lookup"><span data-stu-id="5baa7-117">Most MED-V workspaces are 2 gigabytes (GB) or larger.</span></span> <span data-ttu-id="5baa7-118">系統上的可用磁碟空間可以快速消耗，視使用者數量和 MED-V 的設定而定。</span><span class="sxs-lookup"><span data-stu-id="5baa7-118">The available disk space on a system can be consumed quickly, depending on the number of users and the configuration of MED-V.</span></span> <span data-ttu-id="5baa7-119">此外，貴公司的喜好發佈方法也可能需要額外的空間。</span><span class="sxs-lookup"><span data-stu-id="5baa7-119">Also, your company’s preferred method of distribution can require additional space.</span></span> <span data-ttu-id="5baa7-120">一般來說，您應該為 MED-V 工作區釋放至少 10 GB 的磁碟空間，但視影像的大小而定，這會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="5baa7-120">Generally, you should free a minimum of 10 GB of disk space for a MED-V workspace, but this varies greatly, depending on the size of the image.</span></span>

### <span data-ttu-id="5baa7-121">計算 MED-V 工作區的磁碟空間需求</span><span class="sxs-lookup"><span data-stu-id="5baa7-121">Calculate the Disk Space Requirements for MED-V Workspaces</span></span>

<span data-ttu-id="5baa7-122">MED-V 工作區需要記憶體及磁碟空間來自安裝它的主機。</span><span class="sxs-lookup"><span data-stu-id="5baa7-122">A MED-V workspace requires memory and disk space from the host computer on which it is installed.</span></span> <span data-ttu-id="5baa7-123">主機上至少需要 2 GB 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="5baa7-123">At a minimum, 2 GB of disk space are required on the host.</span></span> <span data-ttu-id="5baa7-124">磁碟空間是可變的，視使用者的 MED-V 工作區中的應用程式數和資料而定。</span><span class="sxs-lookup"><span data-stu-id="5baa7-124">Disk space is variable and depends on the number of applications and the data in a user’s MED-V workspace.</span></span>

<span data-ttu-id="5baa7-125">我們建議在 MED-V 中至少 10 GB 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="5baa7-125">We recommend a minimum of 10 GB of disk space for MED-V.</span></span> <span data-ttu-id="5baa7-126">這個數量允許基本的 Windows XP 工作區和一些基本安裝的應用程式和 web 重新導向。</span><span class="sxs-lookup"><span data-stu-id="5baa7-126">This amount allows for a basic Windows XP workspace and some basic installed applications and web redirection.</span></span> <span data-ttu-id="5baa7-127">它也會為主機交換磁碟機提供可用的空間。</span><span class="sxs-lookup"><span data-stu-id="5baa7-127">It also provides available space for the host swap drive.</span></span> <span data-ttu-id="5baa7-128">在基本設定中，MED-V 與單一部署的 MED-V 工作區會使用最大6到 8 GB 的配置。</span><span class="sxs-lookup"><span data-stu-id="5baa7-128">In a basic configuration, MED-V and a single deployed MED-V workspace consume as much as 6 to 8 GB.</span></span> <span data-ttu-id="5baa7-129">如果您在 MED-V 工作區包含許多應用程式，或是每個電腦都有一個以上的使用者，您可以使用下列計算來更精確地判斷您的 MED-V 工作區所需的磁碟空間：</span><span class="sxs-lookup"><span data-stu-id="5baa7-129">If you include lots of applications on the MED-V workspace or have more than one user per computer, then you can use the following calculation to more accurately determine the disk space your MED-V workspace requires:</span></span>

*<span data-ttu-id="5baa7-130">基本 VHD + （每個電腦的使用者 x （差異磁片 + 已儲存狀態））</span><span class="sxs-lookup"><span data-stu-id="5baa7-130">Base VHD + (User per computer x (Difference Disk + Saved State))</span></span>*

<span data-ttu-id="5baa7-131">若要計算所需的磁碟空間，請判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="5baa7-131">To calculate the required disk space, determine the following:</span></span>

-   <span data-ttu-id="5baa7-132">**基本 VHD 的大小**，即用來建立 med-v 工作區的虛擬硬碟。</span><span class="sxs-lookup"><span data-stu-id="5baa7-132">**Size of the base VHD** – the virtual hard disk that was used to create the MED-V workspace.</span></span>

    <span data-ttu-id="5baa7-133">**重要** 請勿針對您的計算使用 medv 檔案大小，因為 medv 檔案已壓縮。</span><span class="sxs-lookup"><span data-stu-id="5baa7-133">**Important** Do not use the .medv file size for your calculation because the .medv file is compressed.</span></span>

     

-   <span data-ttu-id="5baa7-134">**每個電腦的使用者**-med-v 為電腦上的每位使用者建立 med-v 工作區。MED-V 工作區會在每個使用者登入時佔用磁碟空間，並建立 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="5baa7-134">**Users per computer** – MED-V creates a MED-V workspace for each user on a computer; the MED-V workspace consumes disk space as each user logs on and the MED-V workspace is created.</span></span>

-   <span data-ttu-id="5baa7-135">**差異磁片的大小**-用於追蹤與基礎 VHD 的差異。</span><span class="sxs-lookup"><span data-stu-id="5baa7-135">**Size of the differencing disk** – used to track the difference from the base VHD.</span></span> <span data-ttu-id="5baa7-136">當您將應用程式和軟體更新新增至虛擬硬碟時，此大小會有所不同。</span><span class="sxs-lookup"><span data-stu-id="5baa7-136">This size varies as you add applications and software updates to the virtual hard disk.</span></span> <span data-ttu-id="5baa7-137">第一次啟動 MED-V 時，會為每個 MED-V 使用者建立差異磁片。</span><span class="sxs-lookup"><span data-stu-id="5baa7-137">A differencing disk is created for each MED-V user when they start MED-V for the first time.</span></span>

-   <span data-ttu-id="5baa7-138">**已儲存狀態**檔案的大小-用來維護虛擬機器中的狀態。</span><span class="sxs-lookup"><span data-stu-id="5baa7-138">**Size of the Saved State file** – used to maintain state in the virtual machine.</span></span> <span data-ttu-id="5baa7-139">一般來說，這只會比虛擬機器的已分配 RAM 稍大一些。</span><span class="sxs-lookup"><span data-stu-id="5baa7-139">Typically, this is just a bit larger than the allocated RAM for the virtual machine.</span></span> <span data-ttu-id="5baa7-140">例如，已分配的 1 GB RAM 會建立大約 1081000 KB 的檔案。</span><span class="sxs-lookup"><span data-stu-id="5baa7-140">For example, 1 GB of RAM allocated creates a file about 1,081,000 KB.</span></span>

<span data-ttu-id="5baa7-141">下列範例顯示一個根據 MED-V 工作區中的三個使用者（具有 2.6 GB 虛擬硬碟）來進行的計算：</span><span class="sxs-lookup"><span data-stu-id="5baa7-141">The following example shows a calculation based on three users of a MED-V workspace that has a 2.6 GB virtual hard disk:</span></span>

*<span data-ttu-id="5baa7-142">2.6 gb + （3 x （1.5 gb + 1gb）） = 10.1 gb</span><span class="sxs-lookup"><span data-stu-id="5baa7-142">2.6gb + (3 x (1.5gb + 1gb)) = 10.1gb</span></span>*

<span data-ttu-id="5baa7-143">**記事** MED-V 最佳做法是使用實驗式部署來驗證需求，以計算所需的空間。</span><span class="sxs-lookup"><span data-stu-id="5baa7-143">**Note** A MED-V best practice is to calculate the required space by using a lab deployment to validate the requirements.</span></span>

 

### <span data-ttu-id="5baa7-144">找出檔案以判斷檔案大小</span><span class="sxs-lookup"><span data-stu-id="5baa7-144">Locate the Files to Determine File Size</span></span>

<span data-ttu-id="5baa7-145">下列位置包含電腦和使用者設定的檔案：</span><span class="sxs-lookup"><span data-stu-id="5baa7-145">The following locations contain the files for the computer and user settings:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5baa7-146">類型</span><span class="sxs-lookup"><span data-stu-id="5baa7-146">Type</span></span></th>
<th align="left"><span data-ttu-id="5baa7-147">位置</span><span class="sxs-lookup"><span data-stu-id="5baa7-147">Location</span></span></th>
<th align="left"><span data-ttu-id="5baa7-148">檔案</span><span class="sxs-lookup"><span data-stu-id="5baa7-148">Files</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5baa7-149">基本 VHD</span><span class="sxs-lookup"><span data-stu-id="5baa7-149">Base VHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="5baa7-150">%ProgramData%\Microsoft\Medv\Workspace</span><span class="sxs-lookup"><span data-stu-id="5baa7-150">%ProgramData%\Microsoft\Medv\Workspace</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="5baa7-151">InternalName </em> （.vhd）-其中 <em> InternalName </em> 是您在 Med-v 工作區包裝程式中選取的虛擬硬碟名稱。</span><span class="sxs-lookup"><span data-stu-id="5baa7-151">InternalName</em>.vhd - Where <em>InternalName</em> is the name of the virtual hard disk that you selected in the MED-V Workspace Packager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5baa7-152">差異磁片</span><span class="sxs-lookup"><span data-stu-id="5baa7-152">Differencing Disk</span></span></p></td>
<td align="left"><p><span data-ttu-id="5baa7-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual 電腦</span><span class="sxs-lookup"><span data-stu-id="5baa7-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="5baa7-154">WorkspaceName </em></span><span class="sxs-lookup"><span data-stu-id="5baa7-154">WorkspaceName</em>.vhd</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5baa7-155">已儲存狀態檔案</span><span class="sxs-lookup"><span data-stu-id="5baa7-155">Saved State File</span></span></p></td>
<td align="left"><p><span data-ttu-id="5baa7-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual 電腦</span><span class="sxs-lookup"><span data-stu-id="5baa7-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="5baa7-157">WorkspaceName </em> . vsv</span><span class="sxs-lookup"><span data-stu-id="5baa7-157">WorkspaceName</em>.vsv</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5baa7-158">計算共用 MED-V 工作區的磁碟空間需求</span><span class="sxs-lookup"><span data-stu-id="5baa7-158">Calculate the Disk Space Requirements for Shared MED-V Workspaces</span></span>

<span data-ttu-id="5baa7-159">如果您是在一部電腦上計算共用的 MED-V 工作區部署，則計算中的每個電腦使用者數永遠都是 "1"，因為 MED-V 只會針對所有使用者設定單一差異磁片。</span><span class="sxs-lookup"><span data-stu-id="5baa7-159">If you are calculating for a shared MED-V workspace deployment on a single computer, then the number of users per computer in your calculation is always “1” because MED-V only configures a single differencing disk for all users.</span></span>

<span data-ttu-id="5baa7-160">您可以在%ProgramData%\\Microsoft\\Medv\\AllUsers. 中找到差異磁片與共享 MED-V 工作區的已儲存狀態檔案</span><span class="sxs-lookup"><span data-stu-id="5baa7-160">You can find the differencing disk and the saved state file for shared MED-V workspaces in %ProgramData%\\Microsoft\\Medv\\AllUsers.</span></span>

## <span data-ttu-id="5baa7-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="5baa7-161">Related topics</span></span>


[<span data-ttu-id="5baa7-162">定義和規劃 MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="5baa7-162">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

[<span data-ttu-id="5baa7-163">規劃 MED-V</span><span class="sxs-lookup"><span data-stu-id="5baa7-163">Planning for MED-V</span></span>](planning-for-med-v.md)

 

 





