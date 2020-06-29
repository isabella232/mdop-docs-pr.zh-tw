---
title: 部署適用於 UE-V 1.0 的設定範本類別目錄
description: 部署適用於 UE-V 1.0 的設定範本類別目錄
author: dansimp
ms.assetid: 0e6ab5ef-8eeb-40b4-be7b-a841bd83be96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f342daa958607a077fa5eb2a27ec705c8d99e67f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811871"
---
# <span data-ttu-id="17be6-103">部署適用於 UE-V 1.0 的設定範本類別目錄</span><span class="sxs-lookup"><span data-stu-id="17be6-103">Deploying the Settings Template Catalog for UE-V 1.0</span></span>


<span data-ttu-id="17be6-104">您可以將自訂設定位置範本儲存在 Microsoft 使用者體驗虛擬化（UE-V）電腦或伺服器消息區塊（SMB）網路共用上的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="17be6-104">Custom settings location templates can be stored on a folder path on Microsoft User Experience Virtualization (UE-V) computers or on a Server Message Block (SMB) network share.</span></span> <span data-ttu-id="17be6-105">電腦上的排程任務會從這個位置檢查新的或更新的範本。</span><span class="sxs-lookup"><span data-stu-id="17be6-105">A scheduled task on the computer checks for new or updated templates from this location.</span></span> <span data-ttu-id="17be6-106">工作每天都會檢查這個位置，並根據此資料夾中的範本更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="17be6-106">The task checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="17be6-107">在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。</span><span class="sxs-lookup"><span data-stu-id="17be6-107">Templates that are added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="17be6-108">UE-V agent deregisters 已從這個資料夾移除的範本。</span><span class="sxs-lookup"><span data-stu-id="17be6-108">The UE-V agent deregisters templates that were removed from this folder.</span></span> <span data-ttu-id="17be6-109">[排程] 任務會以系統的方式執行。</span><span class="sxs-lookup"><span data-stu-id="17be6-109">The scheduled task runs as SYSTEM.</span></span> <span data-ttu-id="17be6-110">網路共用至少必須授與 Domain 電腦群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="17be6-110">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="17be6-111">此外，請將網路共用資料夾的存取權限授與將管理已儲存範本的管理員。</span><span class="sxs-lookup"><span data-stu-id="17be6-111">In addition, grant access permissions for the network share folder to administrators who will manage the stored templates.</span></span> <span data-ttu-id="17be6-112">如需自訂設定位置範本的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="17be6-112">For more information about custom setting location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

**<span data-ttu-id="17be6-113">若要設定 UE-V 的設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="17be6-113">To configure the settings template catalog for UE-V</span></span>**

1.  <span data-ttu-id="17be6-114">在要儲存 UE-V 設定範本目錄的電腦上建立新資料夾。</span><span class="sxs-lookup"><span data-stu-id="17be6-114">Create a new folder on the computer that will store the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="17be6-115">針對設定範本目錄資料夾設定下列共用層（SMB）許可權。</span><span class="sxs-lookup"><span data-stu-id="17be6-115">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="17be6-116">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="17be6-116">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="17be6-117">建議許可權</span><span class="sxs-lookup"><span data-stu-id="17be6-117">Recommend permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="17be6-118">所有人</span><span class="sxs-lookup"><span data-stu-id="17be6-118">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-119">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="17be6-119">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="17be6-120">網域電腦</span><span class="sxs-lookup"><span data-stu-id="17be6-120">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-121">讀取權限等級</span><span class="sxs-lookup"><span data-stu-id="17be6-121">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="17be6-122">管理員</span><span class="sxs-lookup"><span data-stu-id="17be6-122">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-123">讀取/寫入權限等級</span><span class="sxs-lookup"><span data-stu-id="17be6-123">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="17be6-124">針對設定範本目錄資料夾設定下列 NTFS 許可權。</span><span class="sxs-lookup"><span data-stu-id="17be6-124">Set the following NTFS permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="17be6-125">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="17be6-125">User Account</span></span></th>
    <th align="left"><span data-ttu-id="17be6-126">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="17be6-126">Recommended Permissions</span></span></th>
    <th align="left"><span data-ttu-id="17be6-127">套用至</span><span class="sxs-lookup"><span data-stu-id="17be6-127">Apply To</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="17be6-128">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="17be6-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-129">完全控制</span><span class="sxs-lookup"><span data-stu-id="17be6-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-130">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="17be6-130">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="17be6-131">網域電腦</span><span class="sxs-lookup"><span data-stu-id="17be6-131">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-132">列出資料夾內容並閱讀</span><span class="sxs-lookup"><span data-stu-id="17be6-132">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-133">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="17be6-133">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="17be6-134">所有人</span><span class="sxs-lookup"><span data-stu-id="17be6-134">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-135">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="17be6-135">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-136">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="17be6-136">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="17be6-137">管理員</span><span class="sxs-lookup"><span data-stu-id="17be6-137">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-138">完全控制</span><span class="sxs-lookup"><span data-stu-id="17be6-138">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17be6-139">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="17be6-139">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="17be6-140">按一下 **[確定**] 以關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="17be6-140">Click **OK** to close the dialog boxes.</span></span>

## <span data-ttu-id="17be6-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="17be6-141">Related topics</span></span>


[<span data-ttu-id="17be6-142">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="17be6-142">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="17be6-143">規劃 UE-V 1.0 的自訂範本部署</span><span class="sxs-lookup"><span data-stu-id="17be6-143">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





