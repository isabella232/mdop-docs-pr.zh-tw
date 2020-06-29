---
title: UE-V 1.0 安全性考量
description: UE-V 1.0 安全性考量
author: dansimp
ms.assetid: c5cdf9ff-dc96-4491-98e9-0eada898ffe0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b503028ae327f92759fe0f64f33fe0cffc62b05c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810292"
---
# <span data-ttu-id="364d2-103">UE-V 1.0 安全性考量</span><span class="sxs-lookup"><span data-stu-id="364d2-103">UE-V 1.0 Security Considerations</span></span>


<span data-ttu-id="364d2-104">本主題包含帳戶與群組、記錄檔案，以及 Microsoft 使用者體驗虛擬化（UE-V）的其他安全相關考慮事項的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="364d2-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V).</span></span> <span data-ttu-id="364d2-105">如需詳細資訊，請參閱此處提供的連結。</span><span class="sxs-lookup"><span data-stu-id="364d2-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="364d2-106">UE-V 設定的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="364d2-106">Security considerations for UE-V configuration</span></span>


**<span data-ttu-id="364d2-107">當您建立 [設定儲存空間共用] 時，請將 [共用] 存取許可權制為需要存取的使用者。</span><span class="sxs-lookup"><span data-stu-id="364d2-107">When you create the settings storage share, limit the share access to users that need access.</span></span>**

<span data-ttu-id="364d2-108">因為 [設定套件] 可能包含個人資訊，所以您應該小心地加以保護。</span><span class="sxs-lookup"><span data-stu-id="364d2-108">Because settings packages may contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="364d2-109">一般來說，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="364d2-109">In general, do the following:</span></span>

-   <span data-ttu-id="364d2-110">將共用限制為只有需要存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="364d2-110">Restrict the share to only the users that need access.</span></span> <span data-ttu-id="364d2-111">針對特定共用上有重新導向資料夾的使用者建立安全性群組，並將存取許可權制為僅限這些使用者。</span><span class="sxs-lookup"><span data-stu-id="364d2-111">Create a security group for users that have redirected folders on a particular share, and limit access to only those users.</span></span>

-   <span data-ttu-id="364d2-112">當您建立共用時，請在共用名稱稱後加上 $ [隱藏] 共用。</span><span class="sxs-lookup"><span data-stu-id="364d2-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="364d2-113">這將會隱藏隨意瀏覽器的共用，而且在 [網路位置] 中不會顯示共用。</span><span class="sxs-lookup"><span data-stu-id="364d2-113">This will hide the share from casual browsers, and the share will not be visible in My Network Places.</span></span>

-   <span data-ttu-id="364d2-114">只給予使用者最少的許可權需求。</span><span class="sxs-lookup"><span data-stu-id="364d2-114">Only give users the minimum amount of permissions needed.</span></span> <span data-ttu-id="364d2-115">所需的許可權如下表所示。</span><span class="sxs-lookup"><span data-stu-id="364d2-115">The permissions needed are shown in the tables below.</span></span>

    1.  <span data-ttu-id="364d2-116">針對 [設定儲存位置] 資料夾設定下列共用層（SMB）許可權：</span><span class="sxs-lookup"><span data-stu-id="364d2-116">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><span data-ttu-id="364d2-117">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="364d2-117">User account</span></span></th>
        <th align="left"><span data-ttu-id="364d2-118">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="364d2-118">Recommended permissions</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="364d2-119">所有人</span><span class="sxs-lookup"><span data-stu-id="364d2-119">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="364d2-120">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="364d2-120">No Permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="364d2-121">UE-V 的安全性群組</span><span class="sxs-lookup"><span data-stu-id="364d2-121">Security group of UE-V</span></span></p></td>
        <td align="left"><p><span data-ttu-id="364d2-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="364d2-122">Full Control</span></span></p></td>
        </tr>
        </tbody>
        </table>



~~~
2.  Set the following NTFS permissions for the settings storage location folder:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Folder</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Admins</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Security group of UE-V users</p></td>
    <td align="left"><p>List Folder/Read Data, Create Folders/Append Data</p></td>
    <td align="left"><p>This Folder Only</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>Remove all Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    </tbody>
    </table>



3.  Set the following share-level (SMB) permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommend permissions</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>Read Permission Levels</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Read/Write Permission Levels</p></td>
    </tr>
    </tbody>
    </table>



4.  Set the following NTFS permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Apply to</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>List Folder Contents and Read</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    </tbody>
    </table>
~~~



### <span data-ttu-id="364d2-123">使用 Windows Server 2003 或更新版本的伺服器來託管重新導向的檔案共用</span><span class="sxs-lookup"><span data-stu-id="364d2-123">Use Windows Server 2003 or later servers to host redirected file shares</span></span>

<span data-ttu-id="364d2-124">使用者設定套件檔案包含在用戶端電腦和儲存設定套件的伺服器之間傳送的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="364d2-124">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="364d2-125">因此，您應該確保資料在網路上傳輸時受到保護。</span><span class="sxs-lookup"><span data-stu-id="364d2-125">Because of this, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="364d2-126">使用者設定資料容易受到下列潛在威脅：截獲在網路上傳遞的資料;隨著資料在網路上傳遞而篡改資料;宿主資料的伺服器的欺騙性。</span><span class="sxs-lookup"><span data-stu-id="364d2-126">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network; tampering with the data as it passes over the network; and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="364d2-127">Windows Server 2003 及以上版本中的數個功能可協助保護使用者資料：</span><span class="sxs-lookup"><span data-stu-id="364d2-127">Several features of Windows Server 2003 and above can help to secure user data:</span></span>

-   <span data-ttu-id="364d2-128">**Kerberos** -kerberos 在所有版本的 windows 2000 和 windows Server 2003 及更新版本中都是標準的。</span><span class="sxs-lookup"><span data-stu-id="364d2-128">**Kerberos** - Kerberos is standard on all versions of Windows 2000 and Windows Server 2003 and later.</span></span> <span data-ttu-id="364d2-129">Kerberos 可確保網路資源的最高安全等級。</span><span class="sxs-lookup"><span data-stu-id="364d2-129">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="364d2-130">NTLM 只會驗證用戶端;Kerberos 會驗證服務器和用戶端。</span><span class="sxs-lookup"><span data-stu-id="364d2-130">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="364d2-131">使用 NTLM 時，用戶端不會知道伺服器是否有效。</span><span class="sxs-lookup"><span data-stu-id="364d2-131">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="364d2-132">如果用戶端正在與伺服器交換個人檔案，這一點尤為重要，就像使用漫遊設定檔的情況一樣。</span><span class="sxs-lookup"><span data-stu-id="364d2-132">This is particularly important if the client is exchanging personal files with the server, as is the case with Roaming Profiles.</span></span> <span data-ttu-id="364d2-133">Kerberos 提供比 NTLM 更佳的安全性。</span><span class="sxs-lookup"><span data-stu-id="364d2-133">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="364d2-134">在 Windows NT 版本4.0 或較舊版本的作業系統上無法使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="364d2-134">Kerberos is not available on Windows NT version 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="364d2-135">**IPsec** -IP 安全通訊協定（ipsec）提供網路層級驗證、資料完整性與加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-135">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="364d2-136">IPsec 可確保下列事項：</span><span class="sxs-lookup"><span data-stu-id="364d2-136">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="364d2-137">漫遊資料在途中進行資料修改是安全的。</span><span class="sxs-lookup"><span data-stu-id="364d2-137">Roamed data is safe from data modification while en route.</span></span>

    -   <span data-ttu-id="364d2-138">漫遊資料可安全地攔截、查看或複製。</span><span class="sxs-lookup"><span data-stu-id="364d2-138">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="364d2-139">未經驗證的一方可以安全地存取漫遊資料。</span><span class="sxs-lookup"><span data-stu-id="364d2-139">Roamed data is safe from being accessed by unauthenticated parties.</span></span>

-   <span data-ttu-id="364d2-140">**SMB**登入-伺服器訊息區塊（SMB）驗證通訊協定支援訊息驗證，防止使用中的訊息和「中間人」攻擊。</span><span class="sxs-lookup"><span data-stu-id="364d2-140">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="364d2-141">SMB 簽名可將數位簽章放入每個 SMB，提供此驗證。</span><span class="sxs-lookup"><span data-stu-id="364d2-141">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="364d2-142">用戶端和伺服器都要驗證數位簽章。</span><span class="sxs-lookup"><span data-stu-id="364d2-142">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="364d2-143">若要使用 SMB 簽署，您必須先在 SMB 用戶端和 SMB 伺服器上啟用或需要它。</span><span class="sxs-lookup"><span data-stu-id="364d2-143">In order to use SMB signing, you must first either enable it or require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="364d2-144">請注意，SMB 簽署會影響效能。</span><span class="sxs-lookup"><span data-stu-id="364d2-144">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="364d2-145">它不會佔用任何網路頻寬，但會在用戶端和伺服器端使用更多的 CPU 週期。</span><span class="sxs-lookup"><span data-stu-id="364d2-145">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="364d2-146">針對擁有使用者資料的磁片，請務必使用 NTFS 檔案系統</span><span class="sxs-lookup"><span data-stu-id="364d2-146">Always use the NTFS File system for volumes holding users data</span></span>

<span data-ttu-id="364d2-147">針對最安全的設定，請將承載 UE-V 設定檔案的伺服器設定為使用 NTFS 檔案系統。</span><span class="sxs-lookup"><span data-stu-id="364d2-147">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS File System.</span></span> <span data-ttu-id="364d2-148">與 FAT 不同，NTFS 支援隨機存取控制清單（Dacl）和系統存取控制清單（Sacl）。</span><span class="sxs-lookup"><span data-stu-id="364d2-148">Unlike FAT, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="364d2-149">Dacl 與 Sacl 控制哪些人可以在檔案上執行作業，以及哪些事件會觸發檔案在檔案上執行的動作記錄。</span><span class="sxs-lookup"><span data-stu-id="364d2-149">DACLs and SACLs control who can perform operations on a file and what events will trigger the logging of actions performed on a file.</span></span>

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a><span data-ttu-id="364d2-150">請勿依靠 EFS 在網路上傳輸時，對使用者的檔案進行加密</span><span class="sxs-lookup"><span data-stu-id="364d2-150">Do not rely on EFS to encrypt users’ files when transmitted over the network</span></span>

<span data-ttu-id="364d2-151">當您使用 [加密檔案系統（EFS）] 加密遠端伺服器上的檔案時，加密的資料在透過網路傳輸期間不會加密。它只會在儲存在磁片上時受到加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-151">When you use Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; It only becomes encrypted when stored on disk.</span></span>

<span data-ttu-id="364d2-152">如果您的系統包含網際網路通訊協定安全性（IPsec）或 Web 分散式撰寫及版本設定（WebDAV），則例外情況例外。</span><span class="sxs-lookup"><span data-stu-id="364d2-152">The exceptions to this are when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="364d2-153">在通過 TCP/IP 網路傳輸時，IPsec 會對資料進行加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-153">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="364d2-154">如果檔案是在複製或移動到伺服器上的 WebDAV 資料夾之前經過加密，則在傳輸期間和儲存在伺服器上時，檔案會保持加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-154">If the file is encrypted before being copied or moved to a WebDAV folder on a server, it will remain encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="364d2-155">加密離線檔案快取</span><span class="sxs-lookup"><span data-stu-id="364d2-155">Encrypt the Offline Files cache</span></span>

<span data-ttu-id="364d2-156">根據預設，離線檔案快取會受 Acl 在 NTFS 分區上受到保護，但加密快取會進一步增強本機電腦的安全性。</span><span class="sxs-lookup"><span data-stu-id="364d2-156">By default, the Offline Files cache is protected on NTFS partitions by ACLs, but encrypting the cache further enhances security on a local computer.</span></span> <span data-ttu-id="364d2-157">根據預設，本機電腦上的快取不會加密，因此從網路緩存的任何加密檔案，都不會在本機電腦上加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-157">By default, the cache on the local computer is not encrypted, so any encrypted files cached from the network will not be encrypted on the local computer.</span></span> <span data-ttu-id="364d2-158">這可能會在某些環境中帶來安全性風險。</span><span class="sxs-lookup"><span data-stu-id="364d2-158">This may pose a security risk in some environments.</span></span>

<span data-ttu-id="364d2-159">啟用加密時，離線檔案快取中的所有檔案都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="364d2-159">When encryption is enabled, all files in the Offline Files cache are encrypted.</span></span> <span data-ttu-id="364d2-160">這包括加密現有的檔案，以及稍後新增的檔案。</span><span class="sxs-lookup"><span data-stu-id="364d2-160">This includes encrypting existing files as well as files that are added later.</span></span> <span data-ttu-id="364d2-161">本機電腦上的快取複本會受到影響，但是相關的網路複本則不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="364d2-161">The cached copy on the local computer is affected, but the associated network copy is not.</span></span>

<span data-ttu-id="364d2-162">您可以使用下列兩種方法的其中一種來加密緩存：</span><span class="sxs-lookup"><span data-stu-id="364d2-162">The cache can be encrypted in one of two ways:</span></span>

1.  <span data-ttu-id="364d2-163">透過群組原則。</span><span class="sxs-lookup"><span data-stu-id="364d2-163">Via Group Policy.</span></span> <span data-ttu-id="364d2-164">-在 [群組原則編輯器] 中啟用 [**加密離線**檔案快取] 設定（位於 [電腦 Configuration\\Administrative Templates\\Network\\Offline 檔案]）。</span><span class="sxs-lookup"><span data-stu-id="364d2-164">- Enable the **Encrypt the Offline Files Cache** setting, located at Computer Configuration\\Administrative Templates\\Network\\Offline Files, in the Group Policy editor.</span></span>

2.  <span data-ttu-id="364d2-165">手動.</span><span class="sxs-lookup"><span data-stu-id="364d2-165">Manually.</span></span> <span data-ttu-id="364d2-166">-在 Windows Explorer 的 [命令] 功能表中，選取 [工具] 和 [資料夾選項]。</span><span class="sxs-lookup"><span data-stu-id="364d2-166">- Select Tools and then Folder Options in the command menu of Windows Explorer.</span></span> <span data-ttu-id="364d2-167">選取 [離線檔案] 索引標籤，然後選取 [**加密離線檔案以保護資料**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="364d2-167">Select the Offline Files tab, and then select the **Encrypt offline files to secure data** check box.</span></span>

### <span data-ttu-id="364d2-168">讓 UE-V Agent 為每位使用者建立資料夾</span><span class="sxs-lookup"><span data-stu-id="364d2-168">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="364d2-169">為了確保 UE-V 能以最佳方式運作，請在伺服器上只建立根目錄共用，並讓 UE-V Agent 為每位使用者建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-169">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="364d2-170">UE-V 會以適當的安全性建立這些使用者資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-170">UE-V will create these user folders with the appropriate security.</span></span>

<span data-ttu-id="364d2-171">此許可權設定可讓使用者建立資料夾來儲存設定。</span><span class="sxs-lookup"><span data-stu-id="364d2-171">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="364d2-172">UE-V agent 在使用者的內容中執行時，會建立並保護 settingspackage 資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-172">The UE-V agent creates and secures a settingspackage folder while running in the context of the user.</span></span> <span data-ttu-id="364d2-173">使用者會收到 [完全控制] settingspackage 資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-173">The user receives full control to their settingspackage folder.</span></span> <span data-ttu-id="364d2-174">其他使用者不會繼承此資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="364d2-174">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="364d2-175">您不需要建立個別的使用者目錄並加以保護。</span><span class="sxs-lookup"><span data-stu-id="364d2-175">You do not need to create and secure individual user directories.</span></span> <span data-ttu-id="364d2-176">這將由在使用者的內容中執行的代理程式自動完成。</span><span class="sxs-lookup"><span data-stu-id="364d2-176">This will be done automatically by the agent that runs in the context of the user.</span></span>

**<span data-ttu-id="364d2-177">注意</span><span class="sxs-lookup"><span data-stu-id="364d2-177">Note</span></span>**  
<span data-ttu-id="364d2-178">在針對設定儲存空間共用使用 Windows 伺服器時，可以設定額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="364d2-178">Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="364d2-179">UE-V 可以設定為確認本機管理員群組或目前的使用者是儲存設定套件的資料夾擁有者。</span><span class="sxs-lookup"><span data-stu-id="364d2-179">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="364d2-180">若要啟用額外的安全性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="364d2-180">To enable additional security use the following command:</span></span>

1.  <span data-ttu-id="364d2-181">將名為 "RepositoryOwnerCheckEnabled" 的 REG \ _DWORD 登錄機碼新增至 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="364d2-181">Add a REG\_DWORD registry key named "RepositoryOwnerCheckEnabled" to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="364d2-182">將 [登錄金鑰] 值設為1。</span><span class="sxs-lookup"><span data-stu-id="364d2-182">Set registry key value to 1.</span></span>

<span data-ttu-id="364d2-183">設定好後，UE-V agent 會驗證本機管理員群組或目前的使用者是否為 settingspackage 資料夾的擁有者。</span><span class="sxs-lookup"><span data-stu-id="364d2-183">When this configuration setting is in place, the UE-V agent verifies that the local administrator’s group or current user is the owner of the settingspackage folder.</span></span> <span data-ttu-id="364d2-184">如果不是，則 UE-V agent 將不允許存取該資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-184">If not, then the UE-V agent will not allow access to the folder.</span></span>



<span data-ttu-id="364d2-185">如果您必須為使用者建立資料夾，並確認您已設定正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="364d2-185">If you must create folders for the users and ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="364d2-186">我們強烈建議您不要 precreate 資料夾，而是允許 UE-V agent 建立使用者的資料夾。</span><span class="sxs-lookup"><span data-stu-id="364d2-186">We strongly recommend that you do not precreate folders and that instead, you allow the UE-V agent to create the folder for the user.</span></span>

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a><span data-ttu-id="364d2-187">在使用者的主目錄中儲存 UE-V 設定時，請確定正確的許可權已設定</span><span class="sxs-lookup"><span data-stu-id="364d2-187">Ensure that correct permissions are set when storing UE-V settings in a user’s home directory</span></span>

<span data-ttu-id="364d2-188">如果您重新導向 UE-V 設定至使用者的主目錄，請確認已針對您的組織設定適當的使用者主目錄許可權。</span><span class="sxs-lookup"><span data-stu-id="364d2-188">If you redirect UE-V settings to a user’s home directory, be sure that the permissions on the user's home directory are set appropriately for your organization.</span></span>

## <span data-ttu-id="364d2-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="364d2-189">Related topics</span></span>


[<span data-ttu-id="364d2-190">UE-V 1.0 的安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="364d2-190">Security and Privacy for UE-V 1.0</span></span>](security-and-privacy-for-ue-v-10.md)









