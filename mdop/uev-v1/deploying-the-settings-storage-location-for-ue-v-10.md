---
title: 部署適用於 UE-V 1.0 的設定儲存位置
description: 部署適用於 UE-V 1.0 的設定儲存位置
author: dansimp
ms.assetid: b187d44d-649b-487e-98d3-a61ee2be8c2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c179be0882bc6a0efc0f11f21fc231f03b63b0fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811876"
---
# <span data-ttu-id="fa8b4-103">部署適用於 UE-V 1.0 的設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="fa8b4-103">Deploying the Settings Storage Location for UE-V 1.0</span></span>


<span data-ttu-id="fa8b4-104">Microsoft 使用者體驗虛擬化（UE-V）部署需要設定儲存位置，其中的使用者設定儲存在設定套件檔案中。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-104">Microsoft User Experience Virtualization (UE-V) deployment requires a settings storage location where the user settings are stored in a settings package file.</span></span> <span data-ttu-id="fa8b4-105">設定儲存位置可以使用下列兩種方法的其中一種來設定：</span><span class="sxs-lookup"><span data-stu-id="fa8b4-105">The settings storage location can be configured in one of the following two ways:</span></span>

-   <span data-ttu-id="fa8b4-106">**Active directory 主目錄**：如果在 active directory 中為使用者定義了主目錄，ue-v agent 將會使用這個位置來儲存設定位置套件。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-106">**Active Directory home directory** – if a home directory is defined for the user in Active Directory, the UE-V agent will use this location to store settings location packages.</span></span> <span data-ttu-id="fa8b4-107">UE-V agent 會在主目錄的根目錄下方動態建立使用者專用的儲存空間資料夾。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-107">The UE-V agent dynamically creates the user-specific storage folder below the root of the home directory.</span></span> <span data-ttu-id="fa8b4-108">如果沒有定義設定儲存位置，則代理程式只會使用 Active Directory 的主目錄。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-108">The agent only uses the home directory of the Active Directory if a settings storage location is not defined.</span></span>

-   <span data-ttu-id="fa8b4-109">**建立設定儲存空間共用**： [設定儲存空間共用] 是一個可由 ue-v 使用者存取的標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-109">**Create a settings storage share** – the settings storage share is a standard network share that is accessible by UE-V users.</span></span>

## <span data-ttu-id="fa8b4-110">部署 UE-V 設定儲存空間共用</span><span class="sxs-lookup"><span data-stu-id="fa8b4-110">Deploy a UE-V settings storage share</span></span>


<span data-ttu-id="fa8b4-111">當您建立 [設定儲存空間共用] 時，您應該只將存取許可權制為需要存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-111">When you create the settings storage share, you should limit access only to users that need access.</span></span> <span data-ttu-id="fa8b4-112">所需許可權如下表所示。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-112">The necessary permissions are shown in the tables below.</span></span>

**<span data-ttu-id="fa8b4-113">部署 UE-V 網路共用</span><span class="sxs-lookup"><span data-stu-id="fa8b4-113">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="fa8b4-114">為 UE-V 使用者建立新的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-114">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="fa8b4-115">在集中位置的電腦上建立將儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者的群組許可權給該資料夾。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-115">Create a new folder on the centrally located computer that will store the UE-V settings packages, and then grant the UE-V users with group permissions to the folder.</span></span> <span data-ttu-id="fa8b4-116">支援 UE-V 的管理員將需要此共用資料夾的許可權。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-116">The administrator supporting UE-V will need permissions to this shared folder.</span></span>

3.  <span data-ttu-id="fa8b4-117">針對 [設定儲存位置] 資料夾設定下列共用層（SMB）許可權：</span><span class="sxs-lookup"><span data-stu-id="fa8b4-117">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="fa8b4-118">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fa8b4-118">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="fa8b4-119">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="fa8b4-119">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="fa8b4-120">所有人</span><span class="sxs-lookup"><span data-stu-id="fa8b4-120">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-121">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="fa8b4-121">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="fa8b4-122">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="fa8b4-122">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-123">完全控制</span><span class="sxs-lookup"><span data-stu-id="fa8b4-123">Full Control</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="fa8b4-124">針對 [設定儲存位置] 資料夾設定下列 NTFS 許可權：</span><span class="sxs-lookup"><span data-stu-id="fa8b4-124">Set the following NTFS permissions for the settings storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="fa8b4-125">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="fa8b4-125">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="fa8b4-126">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="fa8b4-126">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="fa8b4-127">資料夾</span><span class="sxs-lookup"><span data-stu-id="fa8b4-127">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="fa8b4-128">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="fa8b4-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-129">完全控制</span><span class="sxs-lookup"><span data-stu-id="fa8b4-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-130">僅限子資料夾和檔案</span><span class="sxs-lookup"><span data-stu-id="fa8b4-130">Subfolders and Files Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="fa8b4-131">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="fa8b4-131">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-132">列出資料夾/讀取資料、建立資料夾/附加資料</span><span class="sxs-lookup"><span data-stu-id="fa8b4-132">List Folder/Read Data, Create Folders/Append Data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fa8b4-133">僅限此資料夾</span><span class="sxs-lookup"><span data-stu-id="fa8b4-133">This Folder Only</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

5.  <span data-ttu-id="fa8b4-134">按一下 **[確定**] 以關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-134">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="fa8b4-135">此許可權設定可讓使用者建立資料夾來儲存設定。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-135">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="fa8b4-136">UE-V agent `settingspackage` 在使用者的內容中執行時，會建立並保護資料夾。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-136">The UE-V agent creates and secures a `settingspackage` folder while running in the context of the user.</span></span> <span data-ttu-id="fa8b4-137">使用者會收到其資料夾的 [完全控制] `settingspackage` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-137">The user receives full control to their `settingspackage` folder.</span></span> <span data-ttu-id="fa8b4-138">其他使用者不會繼承此資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-138">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="fa8b4-139">您不需要建立並保護個別的使用者目錄，因為這將由在使用者的內容中執行的代理程式自動完成。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-139">You do not need to create and secure individual user directories, because this will be done automatically by the agent that runs in the context of the user.</span></span>

<span data-ttu-id="fa8b4-140">**記事** 在針對設定儲存空間共用使用 Windows 伺服器時，可以設定額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-140">**Note** Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="fa8b4-141">UE-V 可以設定為確認本機管理員群組或目前的使用者是儲存設定套件的資料夾擁有者。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-141">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="fa8b4-142">若要啟用其他安全性，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fa8b4-142">To enable additional security complete the following:</span></span>

1.  <span data-ttu-id="fa8b4-143">將名為 "RepositoryOwnerCheckEnabled" 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration.**</span><span class="sxs-lookup"><span data-stu-id="fa8b4-143">Add a **REG\_DWORD** registry key named "RepositoryOwnerCheckEnabled" to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration.**</span></span>

2.  <span data-ttu-id="fa8b4-144">將 [登錄金鑰] 值設為1。</span><span class="sxs-lookup"><span data-stu-id="fa8b4-144">Set registry key value to 1.</span></span>

 

## <span data-ttu-id="fa8b4-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa8b4-145">Related topics</span></span>


[<span data-ttu-id="fa8b4-146">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="fa8b4-146">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="fa8b4-147">UE-V 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="fa8b4-147">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

<span data-ttu-id="fa8b4-148">部署適用于使用者體驗虛擬化設定範本的中央儲存區，以及[安裝 Ue-v 發生器](installing-the-ue-v-generator.md)的設定套件</span><span class="sxs-lookup"><span data-stu-id="fa8b4-148">Deploy the Central Storage for User Experience Virtualization Settings Templates and Settings Packages [Installing the UE-V Generator](installing-the-ue-v-generator.md)</span></span>

[<span data-ttu-id="fa8b4-149">部署 UE-V 代理程式</span><span class="sxs-lookup"><span data-stu-id="fa8b4-149">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

 

 





