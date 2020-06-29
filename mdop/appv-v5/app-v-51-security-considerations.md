---
title: App-V 5.1 安全性考量
description: App-V 5.1 安全性考量
author: dansimp
ms.assetid: 6bc6c1fc-f813-47d4-b763-06fd4faf6a72
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a5606b3e0ba5e6fb8c62f14e2ed8d93ea2cf134
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800675"
---
# <span data-ttu-id="5d5a9-103">App-V 5.1 安全性考量</span><span class="sxs-lookup"><span data-stu-id="5d5a9-103">App-V 5.1 Security Considerations</span></span>


<span data-ttu-id="5d5a9-104">本主題包含針對 Microsoft 應用程式虛擬化（App-v）5.1 的帳戶和群組、記錄檔案及其他安全相關考慮事項的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for Microsoft Application Virtualization (App-V) 5.1.</span></span>

**<span data-ttu-id="5d5a9-105">重要</span><span class="sxs-lookup"><span data-stu-id="5d5a9-105">Important</span></span>**  
<span data-ttu-id="5d5a9-106">App-v 5.1 不是安全性產品，而且不提供任何對安全環境的保證。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-106">App-V 5.1 is not a security product and does not provide any guarantees for a secure environment.</span></span>



## <span data-ttu-id="5d5a9-107">PackageStoreAccessControl （PSAC）功能已棄用</span><span class="sxs-lookup"><span data-stu-id="5d5a9-107">PackageStoreAccessControl (PSAC) feature has been deprecated</span></span>


<span data-ttu-id="5d5a9-108">從2014年6月起生效，Microsoft Application Virtualization （App-v） 5.0 Service Pack 2 （SP2）中引入的 PackageStoreAccessControl （PSAC）功能在單一使用者和多使用者環境中都已被棄用。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-108">Effective as of June, 2014, the PackageStoreAccessControl (PSAC) feature that was introduced in Microsoft Application Virtualization (App-V) 5.0 Service Pack 2 (SP2) has been deprecated in both single-user and multi-user environments.</span></span>

## <span data-ttu-id="5d5a9-109">一般安全性考慮</span><span class="sxs-lookup"><span data-stu-id="5d5a9-109">General security considerations</span></span>


**<span data-ttu-id="5d5a9-110">瞭解安全性風險。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-110">Understand the security risks.</span></span>** <span data-ttu-id="5d5a9-111">App-V 5.1 最嚴重的風險是它的功能可能會被未經授權的使用者劫持，這樣就可以在 App-V 5.1 用戶端重新設定重要資料。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-111">The most serious risk to App-V 5.1 is that its functionality could be hijacked by an unauthorized user who could then reconfigure key data on App-V 5.1 clients.</span></span> <span data-ttu-id="5d5a9-112">由於拒絕服務攻擊，短時間內的應用程式-V 5.1 功能損失通常不會造成災難性影響。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-112">The loss of App-V 5.1 functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="5d5a9-113">**在物理上保護您的電腦**。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-113">**Physically secure your computers**.</span></span> <span data-ttu-id="5d5a9-114">安全性不完整，沒有實際的安全性。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-114">Security is incomplete without physical security.</span></span> <span data-ttu-id="5d5a9-115">任何人都能以物理方式存取 app-v 5.1 伺服器，可能會攻擊整個用戶端基礎。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-115">Anyone with physical access to an App-V 5.1 server could potentially attack the entire client base.</span></span> <span data-ttu-id="5d5a9-116">任何潛在的物理攻擊都必須被視為高風險，並適當地減輕問題。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-116">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="5d5a9-117">App-v 5.1 伺服器應該儲存在具有可控存取權的物理安全伺服器機房中。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-117">App-V 5.1 servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="5d5a9-118">使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-118">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="5d5a9-119">**將最新的安全性更新套用至所有電腦**。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-119">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="5d5a9-120">若要掌握最新的作業系統、Microsoft SQL Server 和 App-v 5.1 更新，請訂閱安全性通知服務（ <https://go.microsoft.com/fwlink/p/?LinkId=28819> ）。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-120">To stay informed about the latest updates for operating systems, Microsoft SQL Server, and App-V 5.1, subscribe to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="5d5a9-121">**使用強式密碼或密碼片語**。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-121">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="5d5a9-122">針對所有 App-v 5.1 和 App-v 5.1 系統管理員帳戶，請務必將強式密碼搭配15個或以上的字元使用。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-122">Always use strong passwords with 15 or more characters for all App-V 5.1 and App-V 5.1 administrator accounts.</span></span> <span data-ttu-id="5d5a9-123">請勿使用空白密碼。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-123">Never use blank passwords.</span></span> <span data-ttu-id="5d5a9-124">如需密碼概念的詳細資訊，請參閱 TechNet 上的「帳戶密碼及原則」白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-124">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="5d5a9-125">App-v 5.1 中的帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="5d5a9-125">Accounts and groups in App-V 5.1</span></span>


<span data-ttu-id="5d5a9-126">使用者帳戶管理的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-126">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="5d5a9-127">接著，將 [網域通用帳戶] 新增至 App-v 5.1 伺服器上必要的 App-v 5.1 本機群組。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-127">Then, add the domain global accounts to the necessary App-V 5.1 local groups on the App-V 5.1 servers.</span></span>

**<span data-ttu-id="5d5a9-128">注意</span><span class="sxs-lookup"><span data-stu-id="5d5a9-128">Note</span></span>**  
<span data-ttu-id="5d5a9-129">需要連接至發佈伺服器的 app-v 用戶端電腦帳戶必須是發佈伺服器的**使用者**本機群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-129">App-V client computer accounts that need to connect to the publishing server must be part of the publishing server’s **Users** local group.</span></span> <span data-ttu-id="5d5a9-130">根據預設，網域中的所有電腦都是 [**授權的使用者**] 群組的一部分，而這是 [**使用者**本機] 群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-130">By default, all computers in the domain are part of the **Authorized Users** group, which is part of the **Users** local group.</span></span>



### <a href="" id="-------------app-v-5-1-server-security"></a> <span data-ttu-id="5d5a9-131">App-V 5.1 伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="5d5a9-131">App-V 5.1 server security</span></span>

<span data-ttu-id="5d5a9-132">在 App-v 5.1 設定期間不會自動建立任何群組。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-132">No groups are created automatically during App-V 5.1 Setup.</span></span> <span data-ttu-id="5d5a9-133">您應該建立下列 Active Directory 網域服務全域群組，以管理 App-v 5.1 伺服器作業。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-133">You should create the following Active Directory Domain Services global groups to manage App-V 5.1 server operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5d5a9-134">群組名稱</span><span class="sxs-lookup"><span data-stu-id="5d5a9-134">Group name</span></span></th>
<th align="left"><span data-ttu-id="5d5a9-135">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5d5a9-135">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d5a9-136">App-v 管理管理員群組</span><span class="sxs-lookup"><span data-stu-id="5d5a9-136">App-V Management Admin group</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d5a9-137">用來管理 App-v 5.1 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-137">Used to manage the App-V 5.1 management server.</span></span> <span data-ttu-id="5d5a9-138">這個群組是在 App-V 5.1 管理伺服器安裝期間建立的。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-138">This group is created during the App-V 5.1 Management Server installation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5d5a9-139">重要</span><span class="sxs-lookup"><span data-stu-id="5d5a9-139">Important</span></span></strong><br/><p><span data-ttu-id="5d5a9-140">完成安裝後，沒有方法可以使用管理主控台建立群組。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-140">There is no method to create the group using the management console after you have completed the installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d5a9-141">管理服務帳戶的資料庫讀/寫</span><span class="sxs-lookup"><span data-stu-id="5d5a9-141">Database read/write for Management Service account</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d5a9-142">提供管理資料庫的讀/寫存取權。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-142">Provides read/write access to the management database.</span></span> <span data-ttu-id="5d5a9-143">此帳戶應該在 App-V 5.1 管理資料庫安裝期間建立。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-143">This account should be created during the App-V 5.1 management database installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d5a9-144">App-v Management Service 安裝管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="5d5a9-144">App-V Management Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5d5a9-145">注意</span><span class="sxs-lookup"><span data-stu-id="5d5a9-145">Note</span></span></strong><br/><p><span data-ttu-id="5d5a9-146">只有在將管理資料庫與服務分開安裝時，才需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-146">This is only required if management database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="5d5a9-147">提供管理資料庫中架構版本資料表的公用存取權。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-147">Provides public access to schema-version table in management database.</span></span> <span data-ttu-id="5d5a9-148">此帳戶應該在 App-V 5.1 管理資料庫安裝期間建立。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-148">This account should be created during the App-V 5.1 management database installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d5a9-149">App-v Reporting Services 安裝系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="5d5a9-149">App-V Reporting Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5d5a9-150">注意</span><span class="sxs-lookup"><span data-stu-id="5d5a9-150">Note</span></span></strong><br/><p><span data-ttu-id="5d5a9-151">只有在已將報表資料庫與服務分開安裝時，才需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-151">This is only required if reporting database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="5d5a9-152">在報表資料庫中公開存取架構版本表。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-152">Public access to schema-version table in reporting database.</span></span> <span data-ttu-id="5d5a9-153">此帳戶應該在 App-V 5.1 報告資料庫安裝期間建立。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-153">This account should be created during the App-V 5.1 reporting database installation.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="5d5a9-154">請考慮下列其他資訊：</span><span class="sxs-lookup"><span data-stu-id="5d5a9-154">Consider the following additional information:</span></span>

-   <span data-ttu-id="5d5a9-155">存取套件共用（如果共用與管理伺服器位於相同的電腦上），**網路**服務必須擁有共用的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-155">Access to the package shares - If a share exists on the same computer as the management Server, the **Network** service requires read access to the share.</span></span> <span data-ttu-id="5d5a9-156">此外，每個應用程式 V 用戶端電腦都必須具有套件共用的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-156">In addition, each App-V client computer must have read access to the package share.</span></span>

    **<span data-ttu-id="5d5a9-157">注意</span><span class="sxs-lookup"><span data-stu-id="5d5a9-157">Note</span></span>**  
    <span data-ttu-id="5d5a9-158">在舊版 App-v 中，套件共用稱為「內容共用」。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-158">In previous versions of App-V, package share was referred to as content share.</span></span>



-   <span data-ttu-id="5d5a9-159">使用管理伺服器註冊發佈伺服器-必須在管理伺服器上註冊發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-159">Registering publishing servers with Management Server - A publishing server must be registered with the Management server.</span></span> <span data-ttu-id="5d5a9-160">例如，必須將它新增到資料庫，才能讓發佈伺服器電腦帳戶呼叫管理服務 API。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-160">For example, it must be added to the database, so that the Publishing server machine accounts are able to call into the Management service API.</span></span>

### <a href="" id="-------------app-v-5-1-package-security"></a> <span data-ttu-id="5d5a9-161">App-v 5.1 套件安全性</span><span class="sxs-lookup"><span data-stu-id="5d5a9-161">App-V 5.1 package security</span></span>

<span data-ttu-id="5d5a9-162">下列將協助您規劃如何確保虛擬化套件是安全的。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-162">The following will help you plan how to ensure that virtualized packages are secure.</span></span>

-   <span data-ttu-id="5d5a9-163">如果應用程式安裝程式將存取控制清單（ACL）套用至檔案或目錄，則該 ACL 不會保留在套件中。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-163">If an application installer applies an access control list (ACL) to a file or directory, then that ACL is not persisted in the package.</span></span> <span data-ttu-id="5d5a9-164">部署套件時，如果使用者修改了檔案或目錄，就會在 **% userprofile%** 中繼承 acl，或繼承目的電腦目錄的 acl。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-164">When the package is deployed, if the file or directory is modified by a user it will either inherit the ACL in the **%userprofile%** or inherit the ACL of the target computer’s directory.</span></span> <span data-ttu-id="5d5a9-165">如果檔案或目錄不存在於虛擬檔案系統位置，則會發生前個情況;如果檔案或目錄存在於虛擬檔案系統位置（例如 **% windir%**），就會發生後一個情況。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-165">The former case occurs if the file or directory does not exist in a virtual file system location; the latter case occurs if the file or directory exists in a virtual file system location, for example **%windir%**.</span></span>

## <a href="" id="---------app-v-5-1-log-files"></a> <span data-ttu-id="5d5a9-166">App-v 5.1 記錄檔</span><span class="sxs-lookup"><span data-stu-id="5d5a9-166">App-V 5.1 log files</span></span>


<span data-ttu-id="5d5a9-167">在 App-v 5.1 設定期間，系統會在安裝使用者的 **% temp%** 資料夾中建立安裝記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="5d5a9-167">During App-V 5.1 Setup, setup log files are created in the **%temp%** folder of the installing user.</span></span>






## <span data-ttu-id="5d5a9-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="5d5a9-168">Related topics</span></span>


[<span data-ttu-id="5d5a9-169">為 App-V 5.1 準備您的環境</span><span class="sxs-lookup"><span data-stu-id="5d5a9-169">Preparing Your Environment for App-V 5.1</span></span>](preparing-your-environment-for-app-v-51.md)









