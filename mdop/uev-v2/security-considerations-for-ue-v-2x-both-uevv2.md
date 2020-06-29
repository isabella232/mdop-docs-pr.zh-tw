---
title: UE-V 2.x 的安全性考量
description: UE-V 2.x 的安全性考量
author: dansimp
ms.assetid: 9d5c3cae-9fcb-4dea-bd67-741b3dea63be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8e24e9e37de11053663bb90974fabf2ff369aeca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810689"
---
# <span data-ttu-id="7c2ec-103">UE-V 2.x 的安全性考量</span><span class="sxs-lookup"><span data-stu-id="7c2ec-103">Security Considerations for UE-V 2.x</span></span>


<span data-ttu-id="7c2ec-104">本主題包含帳戶與群組、記錄檔案，以及 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 的其他安全相關考慮。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1.</span></span> <span data-ttu-id="7c2ec-105">如需詳細資訊，請參閱此處提供的連結。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="7c2ec-106">UE-V 設定的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="7c2ec-106">Security considerations for UE-V configuration</span></span>


<span data-ttu-id="7c2ec-107">**重要** 當您建立 [設定儲存空間共用] 時，請將 [共用] 存取許可權制為需要存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-107">**Important** When you create the settings storage share, limit the share access to users who require access.</span></span>

 

<span data-ttu-id="7c2ec-108">因為 [設定套件] 可能包含個人資訊，所以您應該小心地加以保護。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-108">Because settings packages might contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="7c2ec-109">一般來說，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7c2ec-109">In general, do the following:</span></span>

-   <span data-ttu-id="7c2ec-110">將共用限制為只需要存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-110">Restrict the share to only those users who require access.</span></span> <span data-ttu-id="7c2ec-111">針對在特定共用上已重定向資料夾的使用者建立安全性群組，並將存取許可權制為僅限這些使用者。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-111">Create a security group for users who have redirected folders on a particular share and limit access to only those users.</span></span>

-   <span data-ttu-id="7c2ec-112">當您建立共用時，請在共用名稱稱後加上 $ [隱藏] 共用。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="7c2ec-113">這項新增功能會隱藏不在瀏覽器中的共用，且在 [網路位置] 中不會顯示共用。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-113">This addition hides the share from casual browsers, and the share is not visible in My Network Places.</span></span>

-   <span data-ttu-id="7c2ec-114">只給予使用者其所需的最小許可權量。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-114">Only give users the minimum amount of permissions that they must have.</span></span> <span data-ttu-id="7c2ec-115">下表顯示所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-115">The following tables show the required permissions.</span></span>

    1.  <span data-ttu-id="7c2ec-116">針對 [設定儲存位置] 資料夾設定下列共用層 SMB 許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-116">Set the following share-level SMB permissions for the setting storage location folder.</span></span>

        | <span data-ttu-id="7c2ec-117">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7c2ec-117">User account</span></span> | <span data-ttu-id="7c2ec-118">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-118">Recommended permissions</span></span> |
        | - | - |
        | <span data-ttu-id="7c2ec-119">所有人</span><span class="sxs-lookup"><span data-stu-id="7c2ec-119">Everyone</span></span> | <span data-ttu-id="7c2ec-120">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-120">No permissions</span></span> |
        |<span data-ttu-id="7c2ec-121">UE-V 的安全性群組</span><span class="sxs-lookup"><span data-stu-id="7c2ec-121">Security group of UE-V</span></span> | <span data-ttu-id="7c2ec-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="7c2ec-122">Full control</span></span> |

    2.  <span data-ttu-id="7c2ec-123">針對 [設定儲存位置] 資料夾設定下列 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-123">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        | <span data-ttu-id="7c2ec-124">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7c2ec-124">User account</span></span> | <span data-ttu-id="7c2ec-125">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-125">Recommended permissions</span></span> | <span data-ttu-id="7c2ec-126">資料夾</span><span class="sxs-lookup"><span data-stu-id="7c2ec-126">Folder</span></span> |
        | - | - | - |
        | <span data-ttu-id="7c2ec-127">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="7c2ec-127">Creator/Owner</span></span> | <span data-ttu-id="7c2ec-128">完全控制</span><span class="sxs-lookup"><span data-stu-id="7c2ec-128">Full control</span></span> | <span data-ttu-id="7c2ec-129">僅限子資料夾和檔案</span><span class="sxs-lookup"><span data-stu-id="7c2ec-129">Subfolders and files only</span></span>|
        | <span data-ttu-id="7c2ec-130">網域管理員</span><span class="sxs-lookup"><span data-stu-id="7c2ec-130">Domain Admins</span></span> | <span data-ttu-id="7c2ec-131">完全控制</span><span class="sxs-lookup"><span data-stu-id="7c2ec-131">Full control</span></span> | <span data-ttu-id="7c2ec-132">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="7c2ec-132">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="7c2ec-133">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="7c2ec-133">Security group of UE-V users</span></span> | <span data-ttu-id="7c2ec-134">列出資料夾/讀取資料、建立資料夾/附加資料</span><span class="sxs-lookup"><span data-stu-id="7c2ec-134">List folder/read data, create folders/append data</span></span> | <span data-ttu-id="7c2ec-135">僅限此資料夾</span><span class="sxs-lookup"><span data-stu-id="7c2ec-135">This folder only</span></span> |
        | <span data-ttu-id="7c2ec-136">所有人</span><span class="sxs-lookup"><span data-stu-id="7c2ec-136">Everyone</span></span> | <span data-ttu-id="7c2ec-137">移除擁有權限</span><span class="sxs-lookup"><span data-stu-id="7c2ec-137">Remove all permissions</span></span> | <span data-ttu-id="7c2ec-138">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-138">No permissions</span></span> |

    3.  <span data-ttu-id="7c2ec-139">針對設定範本目錄資料夾設定下列共用層 SMB 許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-139">Set the following share-level SMB permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="7c2ec-140">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7c2ec-140">User account</span></span> | <span data-ttu-id="7c2ec-141">建議許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-141">Recommend permissions</span></span> |
        | - | - |
        | <span data-ttu-id="7c2ec-142">所有人</span><span class="sxs-lookup"><span data-stu-id="7c2ec-142">Everyone</span></span> | <span data-ttu-id="7c2ec-143">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-143">No permissions</span></span> |
        | <span data-ttu-id="7c2ec-144">網域電腦</span><span class="sxs-lookup"><span data-stu-id="7c2ec-144">Domain computers</span></span> | <span data-ttu-id="7c2ec-145">讀取權限等級</span><span class="sxs-lookup"><span data-stu-id="7c2ec-145">Read permission Levels</span></span> |
        | <span data-ttu-id="7c2ec-146">管理員</span><span class="sxs-lookup"><span data-stu-id="7c2ec-146">Administrators</span></span> | <span data-ttu-id="7c2ec-147">讀取/寫入權限等級</span><span class="sxs-lookup"><span data-stu-id="7c2ec-147">Read/write permission levels</span></span> |
         
    4.  <span data-ttu-id="7c2ec-148">針對設定範本目錄資料夾設定下列 NTFS 許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-148">Set the following NTFS permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="7c2ec-149">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7c2ec-149">User account</span></span> | <span data-ttu-id="7c2ec-150">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-150">Recommended permissions</span></span> | <span data-ttu-id="7c2ec-151">套用至</span><span class="sxs-lookup"><span data-stu-id="7c2ec-151">Apply to</span></span> |
        | - | - | - |
        | <span data-ttu-id="7c2ec-152">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="7c2ec-152">Creator/Owner</span></span> | <span data-ttu-id="7c2ec-153">完全控制</span><span class="sxs-lookup"><span data-stu-id="7c2ec-153">Full control</span></span> | <span data-ttu-id="7c2ec-154">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="7c2ec-154">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="7c2ec-155">網域電腦</span><span class="sxs-lookup"><span data-stu-id="7c2ec-155">Domain Computers</span></span> | <span data-ttu-id="7c2ec-156">列出資料夾內容和讀取權限</span><span class="sxs-lookup"><span data-stu-id="7c2ec-156">List folder contents and Read permissions</span></span> | <span data-ttu-id="7c2ec-157">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="7c2ec-157">This folder, subfolders, and files</span></span>|
        | <span data-ttu-id="7c2ec-158">所有人</span><span class="sxs-lookup"><span data-stu-id="7c2ec-158">Everyone</span></span>| <span data-ttu-id="7c2ec-159">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-159">No permissions</span></span>| <span data-ttu-id="7c2ec-160">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="7c2ec-160">No permissions</span></span>|
        | <span data-ttu-id="7c2ec-161">管理員</span><span class="sxs-lookup"><span data-stu-id="7c2ec-161">Administrators</span></span>| <span data-ttu-id="7c2ec-162">完全控制</span><span class="sxs-lookup"><span data-stu-id="7c2ec-162">Full Control</span></span>| <span data-ttu-id="7c2ec-163">這個資料夾、子資料夾及檔案</span><span class="sxs-lookup"><span data-stu-id="7c2ec-163">This folder, subfolders, and files</span></span>|

### <span data-ttu-id="7c2ec-164">使用 WindowsServer 做為 WindowsServer2003 來託管重新導向的檔案共用</span><span class="sxs-lookup"><span data-stu-id="7c2ec-164">Use WindowsServer as of WindowsServer2003 to host redirected file shares</span></span>

<span data-ttu-id="7c2ec-165">使用者設定套件檔案包含在用戶端電腦和儲存設定套件的伺服器之間傳送的個人資訊。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-165">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="7c2ec-166">由於這個程式，您應該確保資料在網路上傳輸時受到保護。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-166">Because of this process, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="7c2ec-167">使用者設定資料容易受到下列潛在威脅：截獲在網路上傳輸的資料、在網路上傳輸的資料被篡改，以及寄存資料的伺服器欺騙。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-167">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network, tampering with the data as it passes over the network, and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="7c2ec-168">從 Windows Server2003，Windows Server 作業系統有幾項功能可協助保護使用者資料：</span><span class="sxs-lookup"><span data-stu-id="7c2ec-168">As of Windows Server2003, several features of the Windows Server operating system can help secure user data:</span></span>

-   <span data-ttu-id="7c2ec-169">**Kerberos** -kerberos 在所有版本的 Microsoft Windows2000Server 和 WindowsServer （從 WindowsServer2003 開始）中都是標準的。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-169">**Kerberos** - Kerberos is standard on all versions of Microsoft Windows2000Server and WindowsServer beginning with WindowsServer2003.</span></span> <span data-ttu-id="7c2ec-170">Kerberos 可確保網路資源的最高安全等級。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-170">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="7c2ec-171">NTLM 只會驗證用戶端;Kerberos 會驗證服務器和用戶端。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-171">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="7c2ec-172">使用 NTLM 時，用戶端不會知道伺服器是否有效。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-172">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="7c2ec-173">如果用戶端與伺服器交換個人檔案，則這種差別尤為重要，就像在漫遊使用者設定檔中一樣。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-173">This difference is particularly important if the client exchanges personal files with the server, as is the case with Roaming User Profiles.</span></span> <span data-ttu-id="7c2ec-174">Kerberos 提供比 NTLM 更佳的安全性。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-174">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="7c2ec-175">在 Microsoft WindowsNTServer 4.0 或較舊版本的作業系統上無法使用 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-175">Kerberos is not available on the Microsoft WindowsNTServer 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="7c2ec-176">**IPsec** -IP 安全通訊協定（ipsec）提供網路層級驗證、資料完整性與加密。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-176">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="7c2ec-177">IPsec 可確保下列事項：</span><span class="sxs-lookup"><span data-stu-id="7c2ec-177">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="7c2ec-178">在資料是透過路線時，漫遊資料可安全地從資料修改中移除。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-178">Roamed data is safe from data modification while data is en route.</span></span>

    -   <span data-ttu-id="7c2ec-179">漫遊資料可安全地攔截、查看或複製。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-179">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="7c2ec-180">未經驗證的一方可以安全地存取漫遊資料。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-180">Roamed data is safe from access by unauthenticated parties.</span></span>

-   <span data-ttu-id="7c2ec-181">**SMB**登入-伺服器訊息區塊（SMB）驗證通訊協定支援訊息驗證，防止使用中的訊息和「中間人」攻擊。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-181">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication, which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="7c2ec-182">SMB 簽名可將數位簽章放入每個 SMB，提供此驗證。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-182">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="7c2ec-183">用戶端和伺服器都要驗證數位簽章。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-183">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="7c2ec-184">若要使用 SMB 簽署，您必須先啟用它，或者必須在 SMB 用戶端和 SMB 伺服器上都需要它。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-184">In order to use SMB signing, you must first either enable it, or you must require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="7c2ec-185">請注意，SMB 簽署會影響效能。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-185">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="7c2ec-186">它不會佔用任何網路頻寬，但會在用戶端和伺服器端使用更多的 CPU 週期。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-186">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="7c2ec-187">針對保留使用者資料的磁片，請務必使用 NTFS 檔案系統</span><span class="sxs-lookup"><span data-stu-id="7c2ec-187">Always use the NTFS file system for volumes that hold user data</span></span>

<span data-ttu-id="7c2ec-188">針對最安全的設定，請將承載 UE-V 設定檔案的伺服器設定為使用 NTFS 檔案系統。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-188">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS file system.</span></span> <span data-ttu-id="7c2ec-189">NTFS 不像 FAT 檔案系統，NTFS 支援隨機存取控制清單（Dacl）和系統存取控制清單（Sacl）。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-189">Unlike the FAT file system, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="7c2ec-190">Dacl 與 Sacl 控制哪些人可以在檔案上執行作業，以及觸發檔案執行動作的記錄。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-190">DACLs and SACLs control who can perform operations on a file and what events trigger the logging of actions that is performed on a file.</span></span>

### <span data-ttu-id="7c2ec-191">請勿依靠 EFS 在使用者在網路上傳輸時對使用者檔案進行加密</span><span class="sxs-lookup"><span data-stu-id="7c2ec-191">Do not rely on EFS to encrypt user files when they are transmitted over the network</span></span>

<span data-ttu-id="7c2ec-192">當您使用 [加密檔案系統（EFS）] 加密遠端伺服器上的檔案時，加密的資料在透過網路傳輸期間不會加密。它只會在儲存在磁片上時變成加密。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-192">When you use the Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; it only becomes encrypted when it is stored on disk.</span></span>

<span data-ttu-id="7c2ec-193">當您的系統包含網際網路通訊協定安全性（IPsec）或 Web 分散式撰寫及版本設定（WebDAV）時，就不會套用這個加密處理常式。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-193">This encryption process does not apply when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="7c2ec-194">在通過 TCP/IP 網路傳輸時，IPsec 會對資料進行加密。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-194">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="7c2ec-195">如果檔案在複製或移動到伺服器上的 WebDAV 資料夾之前經過加密，則在傳輸期間並儲存在伺服器上時，檔案會保持加密。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-195">If the file is encrypted before it is copied or moved to a WebDAV folder on a server, it remains encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="7c2ec-196">讓 UE-V Agent 為每位使用者建立資料夾</span><span class="sxs-lookup"><span data-stu-id="7c2ec-196">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="7c2ec-197">為了確保 UE-V 能以最佳方式運作，請在伺服器上只建立根目錄共用，並讓 UE-V Agent 為每位使用者建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-197">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="7c2ec-198">UE-V 會以適當的安全性建立這些使用者資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-198">UE-V creates these user folders with the appropriate security.</span></span>

<span data-ttu-id="7c2ec-199">此許可權設定可讓使用者建立設定儲存空間的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-199">This permission configuration enables users to create folders for settings storage.</span></span> <span data-ttu-id="7c2ec-200">UE-V Agent 會在設定套件資料夾在使用者的內容中執行時建立並保護它。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-200">The UE-V Agent creates and secures a settings package folder while it runs in the context of the user.</span></span> <span data-ttu-id="7c2ec-201">使用者接收 [完全控制] 的 [設定套件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-201">Users receive full control to their settings package folder.</span></span> <span data-ttu-id="7c2ec-202">其他使用者不會繼承此資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-202">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="7c2ec-203">您不需要建立並保護個別的使用者目錄。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-203">You do not have to create and secure individual user directories.</span></span> <span data-ttu-id="7c2ec-204">在使用者的內容中執行的代理程式會自動進行。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-204">The agent that runs in the context of the user does it automatically.</span></span>

<span data-ttu-id="7c2ec-205">**記事** 當您將 Windows Server 用於設定儲存空間共用時，可以設定額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-205">**Note** Additional security can be configured when a Windows Server is used for the settings storage share.</span></span> <span data-ttu-id="7c2ec-206">UE-V 可以設定為確認 [本機管理員] 群組或 [目前的使用者] 是儲存設定套件的資料夾擁有者。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-206">UE-V can be configured to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="7c2ec-207">若要啟用額外的安全性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="7c2ec-207">To enable additional security, use the following command:</span></span>

1.  <span data-ttu-id="7c2ec-208">將 REG \ _DWORD 登錄機碼 RepositoryOwnerCheckEnabled 至 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-208">Add the REG\_DWORD registry key RepositoryOwnerCheckEnabled to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="7c2ec-209">將 [登錄機碼] 值設定為*1*。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-209">Set the registry key value to *1*.</span></span>

<span data-ttu-id="7c2ec-210">設定好後，UE-V Agent 會確認 [本機管理員] 群組或 [目前使用者] 是 [設定套件] 資料夾的擁有者。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-210">When this configuration setting is in place, the UE-V Agent verifies that the local Administrators group or current user is the owner of the settings package folder.</span></span> <span data-ttu-id="7c2ec-211">如果不是，則 UE-V Agent 不會授與資料夾的存取權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-211">If not, then the UE-V Agent does not grant access to the folder.</span></span>

 

<span data-ttu-id="7c2ec-212">如果您必須為使用者建立資料夾，請確定您已設定正確的許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-212">If you must create folders for the users, ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="7c2ec-213">我們強烈建議您不要預先建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-213">We strongly recommend that you do not pre-create folders.</span></span> <span data-ttu-id="7c2ec-214">相反地，讓 UE-V Agent 為使用者建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-214">Instead, let the UE-V Agent create the folder for the user.</span></span>

### <span data-ttu-id="7c2ec-215">確保正確的許可權，以便在主目錄或自訂目錄中儲存 UE-V 2 設定</span><span class="sxs-lookup"><span data-stu-id="7c2ec-215">Ensure correct permissions to store UE-V 2 settings in a home directory or custom directory</span></span>

<span data-ttu-id="7c2ec-216">如果您將 UE-V 設定重新導向至使用者的主目錄或自訂 Active Directory （AD）目錄，請確定針對您的組織適當地設定目錄許可權。</span><span class="sxs-lookup"><span data-stu-id="7c2ec-216">If you redirect UE-V settings to a user’s home directory or a custom Active Directory (AD) directory, ensure that the permissions on the directory are set appropriately for your organization.</span></span>






## <span data-ttu-id="7c2ec-217">相關主題</span><span class="sxs-lookup"><span data-stu-id="7c2ec-217">Related topics</span></span>


[<span data-ttu-id="7c2ec-218">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="7c2ec-218">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





