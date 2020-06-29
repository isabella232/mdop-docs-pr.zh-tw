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
# UE-V 1.0 安全性考量


本主題包含帳戶與群組、記錄檔案，以及 Microsoft 使用者體驗虛擬化（UE-V）的其他安全相關考慮事項的簡短概述。 如需詳細資訊，請參閱此處提供的連結。

## UE-V 設定的安全性考慮


**當您建立 [設定儲存空間共用] 時，請將 [共用] 存取許可權制為需要存取的使用者。**

因為 [設定套件] 可能包含個人資訊，所以您應該小心地加以保護。 一般來說，請執行下列動作：

-   將共用限制為只有需要存取權的使用者。 針對特定共用上有重新導向資料夾的使用者建立安全性群組，並將存取許可權制為僅限這些使用者。

-   當您建立共用時，請在共用名稱稱後加上 $ [隱藏] 共用。 這將會隱藏隨意瀏覽器的共用，而且在 [網路位置] 中不會顯示共用。

-   只給予使用者最少的許可權需求。 所需的許可權如下表所示。

    1.  針對 [設定儲存位置] 資料夾設定下列共用層（SMB）許可權：

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">使用者帳戶</th>
        <th align="left">建議的許可權</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>所有人</p></td>
        <td align="left"><p>沒有許可權</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 的安全性群組</p></td>
        <td align="left"><p>完全控制</p></td>
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



### 使用 Windows Server 2003 或更新版本的伺服器來託管重新導向的檔案共用

使用者設定套件檔案包含在用戶端電腦和儲存設定套件的伺服器之間傳送的個人資訊。 因此，您應該確保資料在網路上傳輸時受到保護。

使用者設定資料容易受到下列潛在威脅：截獲在網路上傳遞的資料;隨著資料在網路上傳遞而篡改資料;宿主資料的伺服器的欺騙性。

Windows Server 2003 及以上版本中的數個功能可協助保護使用者資料：

-   **Kerberos** -kerberos 在所有版本的 windows 2000 和 windows Server 2003 及更新版本中都是標準的。 Kerberos 可確保網路資源的最高安全等級。 NTLM 只會驗證用戶端;Kerberos 會驗證服務器和用戶端。 使用 NTLM 時，用戶端不會知道伺服器是否有效。 如果用戶端正在與伺服器交換個人檔案，這一點尤為重要，就像使用漫遊設定檔的情況一樣。 Kerberos 提供比 NTLM 更佳的安全性。 在 Windows NT 版本4.0 或較舊版本的作業系統上無法使用 Kerberos。

-   **IPsec** -IP 安全通訊協定（ipsec）提供網路層級驗證、資料完整性與加密。 IPsec 可確保下列事項：

    -   漫遊資料在途中進行資料修改是安全的。

    -   漫遊資料可安全地攔截、查看或複製。

    -   未經驗證的一方可以安全地存取漫遊資料。

-   **SMB**登入-伺服器訊息區塊（SMB）驗證通訊協定支援訊息驗證，防止使用中的訊息和「中間人」攻擊。 SMB 簽名可將數位簽章放入每個 SMB，提供此驗證。 用戶端和伺服器都要驗證數位簽章。 若要使用 SMB 簽署，您必須先在 SMB 用戶端和 SMB 伺服器上啟用或需要它。 請注意，SMB 簽署會影響效能。 它不會佔用任何網路頻寬，但會在用戶端和伺服器端使用更多的 CPU 週期。

### 針對擁有使用者資料的磁片，請務必使用 NTFS 檔案系統

針對最安全的設定，請將承載 UE-V 設定檔案的伺服器設定為使用 NTFS 檔案系統。 與 FAT 不同，NTFS 支援隨機存取控制清單（Dacl）和系統存取控制清單（Sacl）。 Dacl 與 Sacl 控制哪些人可以在檔案上執行作業，以及哪些事件會觸發檔案在檔案上執行的動作記錄。

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a>請勿依靠 EFS 在網路上傳輸時，對使用者的檔案進行加密

當您使用 [加密檔案系統（EFS）] 加密遠端伺服器上的檔案時，加密的資料在透過網路傳輸期間不會加密。它只會在儲存在磁片上時受到加密。

如果您的系統包含網際網路通訊協定安全性（IPsec）或 Web 分散式撰寫及版本設定（WebDAV），則例外情況例外。 在通過 TCP/IP 網路傳輸時，IPsec 會對資料進行加密。 如果檔案是在複製或移動到伺服器上的 WebDAV 資料夾之前經過加密，則在傳輸期間和儲存在伺服器上時，檔案會保持加密。

### 加密離線檔案快取

根據預設，離線檔案快取會受 Acl 在 NTFS 分區上受到保護，但加密快取會進一步增強本機電腦的安全性。 根據預設，本機電腦上的快取不會加密，因此從網路緩存的任何加密檔案，都不會在本機電腦上加密。 這可能會在某些環境中帶來安全性風險。

啟用加密時，離線檔案快取中的所有檔案都會經過加密。 這包括加密現有的檔案，以及稍後新增的檔案。 本機電腦上的快取複本會受到影響，但是相關的網路複本則不會受到影響。

您可以使用下列兩種方法的其中一種來加密緩存：

1.  透過群組原則。 -在 [群組原則編輯器] 中啟用 [**加密離線**檔案快取] 設定（位於 [電腦 Configuration\\Administrative Templates\\Network\\Offline 檔案]）。

2.  手動. -在 Windows Explorer 的 [命令] 功能表中，選取 [工具] 和 [資料夾選項]。 選取 [離線檔案] 索引標籤，然後選取 [**加密離線檔案以保護資料**] 核取方塊。

### 讓 UE-V Agent 為每位使用者建立資料夾

為了確保 UE-V 能以最佳方式運作，請在伺服器上只建立根目錄共用，並讓 UE-V Agent 為每位使用者建立資料夾。 UE-V 會以適當的安全性建立這些使用者資料夾。

此許可權設定可讓使用者建立資料夾來儲存設定。 UE-V agent 在使用者的內容中執行時，會建立並保護 settingspackage 資料夾。 使用者會收到 [完全控制] settingspackage 資料夾。 其他使用者不會繼承此資料夾的存取權。 您不需要建立個別的使用者目錄並加以保護。 這將由在使用者的內容中執行的代理程式自動完成。

**注意**  
在針對設定儲存空間共用使用 Windows 伺服器時，可以設定額外的安全性。 UE-V 可以設定為確認本機管理員群組或目前的使用者是儲存設定套件的資料夾擁有者。 若要啟用額外的安全性，請使用下列命令：

1.  將名為 "RepositoryOwnerCheckEnabled" 的 REG \ _DWORD 登錄機碼新增至 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 。

2.  將 [登錄金鑰] 值設為1。

設定好後，UE-V agent 會驗證本機管理員群組或目前的使用者是否為 settingspackage 資料夾的擁有者。 如果不是，則 UE-V agent 將不允許存取該資料夾。



如果您必須為使用者建立資料夾，並確認您已設定正確的許可權。

我們強烈建議您不要 precreate 資料夾，而是允許 UE-V agent 建立使用者的資料夾。

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a>在使用者的主目錄中儲存 UE-V 設定時，請確定正確的許可權已設定

如果您重新導向 UE-V 設定至使用者的主目錄，請確認已針對您的組織設定適當的使用者主目錄許可權。

## 相關主題


[UE-V 1.0 的安全性與隱私權](security-and-privacy-for-ue-v-10.md)









