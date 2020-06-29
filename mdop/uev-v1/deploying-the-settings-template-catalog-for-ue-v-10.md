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
# 部署適用於 UE-V 1.0 的設定範本類別目錄


您可以將自訂設定位置範本儲存在 Microsoft 使用者體驗虛擬化（UE-V）電腦或伺服器消息區塊（SMB）網路共用上的資料夾路徑。 電腦上的排程任務會從這個位置檢查新的或更新的範本。 工作每天都會檢查這個位置，並根據此資料夾中的範本更新其同步處理行為。 在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。 UE-V agent deregisters 已從這個資料夾移除的範本。 [排程] 任務會以系統的方式執行。 網路共用至少必須授與 Domain 電腦群組的許可權。 此外，請將網路共用資料夾的存取權限授與將管理已儲存範本的管理員。 如需自訂設定位置範本的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。

**若要設定 UE-V 的設定範本目錄**

1.  在要儲存 UE-V 設定範本目錄的電腦上建立新資料夾。

2.  針對設定範本目錄資料夾設定下列共用層（SMB）許可權。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>使用者帳戶</strong></th>
    <th align="left"><strong>建議許可權</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>網域電腦</p></td>
    <td align="left"><p>讀取權限等級</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>管理員</p></td>
    <td align="left"><p>讀取/寫入權限等級</p></td>
    </tr>
    </tbody>
    </table>

     

3.  針對設定範本目錄資料夾設定下列 NTFS 許可權。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">使用者帳戶</th>
    <th align="left">建議的許可權</th>
    <th align="left">套用至</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>建立者/擁有者</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>網域電腦</p></td>
    <td align="left"><p>列出資料夾內容並閱讀</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>所有人</p></td>
    <td align="left"><p>沒有許可權</p></td>
    <td align="left"><p>沒有許可權</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>管理員</p></td>
    <td align="left"><p>完全控制</p></td>
    <td align="left"><p>這個資料夾、子資料夾及檔案</p></td>
    </tr>
    </tbody>
    </table>

     

4.  按一下 **[確定**] 以關閉對話方塊。

## 相關主題


[部署 UE-V 1.0](deploying-ue-v-10.md)

[規劃 UE-V 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





