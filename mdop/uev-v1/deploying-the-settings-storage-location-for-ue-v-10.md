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
# 部署適用於 UE-V 1.0 的設定儲存位置


Microsoft 使用者體驗虛擬化（UE-V）部署需要設定儲存位置，其中的使用者設定儲存在設定套件檔案中。 設定儲存位置可以使用下列兩種方法的其中一種來設定：

-   **Active directory 主目錄**：如果在 active directory 中為使用者定義了主目錄，ue-v agent 將會使用這個位置來儲存設定位置套件。 UE-V agent 會在主目錄的根目錄下方動態建立使用者專用的儲存空間資料夾。 如果沒有定義設定儲存位置，則代理程式只會使用 Active Directory 的主目錄。

-   **建立設定儲存空間共用**： [設定儲存空間共用] 是一個可由 ue-v 使用者存取的標準網路共用。

## 部署 UE-V 設定儲存空間共用


當您建立 [設定儲存空間共用] 時，您應該只將存取許可權制為需要存取權的使用者。 所需許可權如下表所示。

**部署 UE-V 網路共用**

1.  為 UE-V 使用者建立新的安全性群組。

2.  在集中位置的電腦上建立將儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者的群組許可權給該資料夾。 支援 UE-V 的管理員將需要此共用資料夾的許可權。

3.  針對 [設定儲存位置] 資料夾設定下列共用層（SMB）許可權：

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議的許可權</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 使用者的安全性群組</p></td>
    <td align="left"><p>完全控制</p></td>
    </tr>
    </tbody>
    </table>

     

4.  針對 [設定儲存位置] 資料夾設定下列 NTFS 許可權：

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議的許可權</strong></th>
    <th align="left"><strong>資料夾</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>建立者/擁有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>僅限子資料夾和檔案</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V 使用者的安全性群組</p></td>
    <td align="left"><p>列出資料夾/讀取資料、建立資料夾/附加資料</p></td>
    <td align="left"><p>僅限此資料夾</p></td>
    </tr>
    </tbody>
    </table>

     

5.  按一下 **[確定**] 以關閉對話方塊。

此許可權設定可讓使用者建立資料夾來儲存設定。 UE-V agent `settingspackage` 在使用者的內容中執行時，會建立並保護資料夾。 使用者會收到其資料夾的 [完全控制] `settingspackage` 。 其他使用者不會繼承此資料夾的存取權。 您不需要建立並保護個別的使用者目錄，因為這將由在使用者的內容中執行的代理程式自動完成。

**記事** 在針對設定儲存空間共用使用 Windows 伺服器時，可以設定額外的安全性。 UE-V 可以設定為確認本機管理員群組或目前的使用者是儲存設定套件的資料夾擁有者。 若要啟用其他安全性，請完成下列步驟：

1.  將名為 "RepositoryOwnerCheckEnabled" 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration.**

2.  將 [登錄金鑰] 值設為1。

 

## 相關主題


[部署 UE-V 1.0](deploying-ue-v-10.md)

[UE-V 1.0 支援的組態](supported-configurations-for-ue-v-10.md)

部署適用于使用者體驗虛擬化設定範本的中央儲存區，以及[安裝 Ue-v 發生器](installing-the-ue-v-generator.md)的設定套件

[部署 UE-V 代理程式](deploying-the-ue-v-agent.md)

 

 





