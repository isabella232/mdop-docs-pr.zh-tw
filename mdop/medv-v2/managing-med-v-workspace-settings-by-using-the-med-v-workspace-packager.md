---
title: 使用 MED-V 工作區封裝工具來管理 MED-V 工作區設定
description: 使用 MED-V 工作區封裝工具來管理 MED-V 工作區設定
author: dansimp
ms.assetid: e4b2c516-b9f8-44f9-9eae-caac6c2af3e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9905c8da0f1f0678cce9587296526e8f04493c20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811565"
---
# 使用 MED-V 工作區封裝工具來管理 MED-V 工作區設定


您可以使用 MED-V 工作區包裝程式來管理 MED-V 工作區中的某些設定。

**在 MED-V 工作區中管理設定**

1. 若要開啟**Med-v 工作區包裝**程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 工作區包裝程式**]。

2. 在**Med-v 工作區包裝**程式主版面板中，按一下 [**管理設定**]。

3. 在 [**管理設定**] 視窗中，您可以設定下列 med-v 工作區設定：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>開始 MED-V-V 工作區</strong></p></td>
   <td align="left"><p>選擇是否要在使用者登入時、第一次使用時啟動 MED-V 工作區，或是讓最終使用者決定 MED-V 工作區何時開始。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V 工作區以兩種方法的其中一種開始：當使用者登入時，或當他們第一次執行需要 MED-V 的動作時，例如開啟已發佈的應用程式，或輸入需要重新導向的 URL。</p>
   <p>您可以為最終使用者定義此設定，或讓使用者控制 MED-V 的啟動方式。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果您指定最終使用者決定，其體驗的預設行為就是 MED-V 工作區在登入時就會啟動。 您可以在通知區域中，以滑鼠右鍵按一下 MED-V 圖示，然後選取 [Med-v 使用者設定] 來變更預設值 <strong> </strong> 。 如果您為最終使用者定義此設定，就無法變更 MED-V 的啟動方式。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>網路</strong></p></td>
   <td align="left"><p><strong> </strong> <strong> </strong> 針對您的網路設定選取 [共用] 或 [橋接]。 預設值為 [ <strong> 共用] </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>已共用 </strong> - med-v 工作區使用網路位址轉譯（NAT）來共用主機&#39;s IP 以進行外寄通訊。</p>
   <p><strong>已橋接 </strong> - med-v 工作區有自己的網路位址，通常是透過 DHCP 取得的。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>儲存身分認證</strong></p></td>
   <td align="left"><p>選擇是否要儲存使用者認證。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>預設行為是已停用認證儲存，因此使用者必須在每次登入時對其進行驗證。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>雖然快取使用者的認證會提供最佳的使用者體驗，但是您應該知道所涉及的風險。</p>
   <p>在 Windows 認證管理員中，使用者的網域認證會以可逆的格式儲存。 攻擊者可以撰寫可檢索密碼的程式，進而取得使用者認證的存取權。 您只需要停用使用者認證，即可減少這項風險。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



4. 按一下 [**另存**新格式]。 將更新的設定儲存在指定資料夾中。 MED-V 會建立包含更新設定的登錄檔案。 使用 [群組原則] 部署更新的註冊表檔案。 如需如何使用群組原則的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

   MED-V 也會在指定的資料夾中建立 Windows PowerShell 腳本，您可以用來重新建立此更新的註冊表檔案。

## 相關主題


[管理 MED-V 工作區組態設定](managing-med-v-workspace-configuration-settings.md)

[管理 MED-V 工作區設定](manage-med-v-workspace-settings.md)









