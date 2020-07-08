---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809423"
---
# 如何修復損毀的磁碟機


您可以將此程式與 [管理及監視] 網站（也稱為 [技術支援中心]）網站搭配使用，以復原受 BitLocker 保護的損壞的磁片磁碟機。 若要這樣做，您將完成下表所述的工作。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料及詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>透過存取 [管理] 和 [監視] 網站的 [磁碟機] 恢復區域，建立復原金鑰套件檔案 <strong> </strong> 。</p></td>
<td align="left"><p>若要存取 <strong> 磁片磁碟機復原 </strong> 區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。 您可能會在建立這些角色時，為它們指定不同的名稱。 如需詳細資訊，請參閱 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> 規劃 MBAM 2.5 群組和帳戶 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>將套件檔案複製到內含損壞之磁片磁碟機的電腦上。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用 <code>repair-bde</code> 命令完成恢復程式。</p></td>
<td align="left"><p>為了避免潛在的資料遺失，強烈建議您 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 先查看 manage-bde </a> 命令，然後再使用它。</p></td>
</tr>
</tbody>
</table>

 

**復原損壞的磁片磁碟機**

1.  開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。

2.  在左窗格中，選取 [**磁片磁碟機**復原] 以開啟 [**復原存取加密的磁碟機**] 頁面。

3.  輸入使用者的 Windows 登入網域和使用者名稱、解除磁片磁碟機鎖定的原因，以及使用者的復原密碼識別碼。

    **記事** 如果您是 [高級支援人員] 使用者訪問群組的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。

     

4.  按一下 **\[提交\]**。 隨即會顯示覆原金鑰。

5.  按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。 系統會在您的電腦上建立復原金鑰套件。

6.  將復原金鑰套件複製到有損毀磁片磁碟機的電腦。

7.  開啟提升權限的命令提示字元。 若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式和**檔案] 文字方塊中輸入。 以滑鼠右鍵按一下 [ **cmd.exe**]，然後選取 [**以系統管理員身分執行**]。

8.  在命令提示字元中，輸入下列內容：

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    **記事** 將 &lt; *固定磁碟機*更換 &gt; 為可用的硬碟磁片磁碟機，其可用空間等於或大於損壞的磁片磁碟機上的資料。 已損壞的磁片磁碟機上的資料會復原並移至指定的硬碟。

     


## 相關主題


[使用 MBAM 2.5 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-25.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





