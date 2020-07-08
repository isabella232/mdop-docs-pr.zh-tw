---
title: 驗證 MED-V 終端使用者
description: 驗證 MED-V 終端使用者
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810826"
---
# 驗證 MED-V 終端使用者


驗證 Microsoft 企業桌面虛擬化（MED-V）2.0 使用者是一個非常重要的安全性問題。 在這種情況下，驗證是指驗證 MED-V 端使用者的身分識別。

下列章節提供有關 MED-V 中的使用者驗證的資訊與指導方針。

## MED-V 中的使用者驗證


MED-V 中的驗證通常會發生在兩個層面：使用者第一次存取 MED-V，以及每次變更其密碼。

根據您設定的 MED-V 設定進行驗證的方式，通常會在您第一次啟動 MED-V 或第一次嘗試開啟已發佈的應用程式時，在某些時候提示使用者輸入密碼。

最終使用者驗證的幾個層面可供您控制，包括下列各項：

使用者輸入的認證是否儲存在認證管理員中

最終使用者呈現的方式，提供輸入並儲存密碼的選項

根據貴公司管理使用者驗證的首選程式，您可以指定是否要針對特定的 MED-V 工作區進行認證快取。 因為使用者只會收到一次密碼的提示，所以快取使用者的認證很有説明。 如果使用者每次啟動新的 MED-V 會話時，都不能儲存其密碼或決定不要，必須再次輸入。 例如，如果 MED-V 設定為在使用者登入主機時開始，但已停用驗證，則在登入時只會提示使用者一次。 在這種情況下，認證會一直有效，直到最終使用者從主機登出為止。

如有需要，您可以使用認證管理員來移除任何已儲存的最終使用者認證。

根據預設，認證儲存已停用，但您可以透過下列其中一種方法變更此設定：

**當您建立 med-v 工作區套件時**。 如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。

**部署 med-v 工作區後**。 編輯 MED-V Cmdlet 參數 UxCredentialCacheEnabled，以設定終端服務登錄機碼。 如需詳細資訊，請參閱 Windows PowerShell 說明。

在 MED-V 工作區部署之後，您可以修改名為 DisablePasswordSaving 的終端服務原則，以設定使用者對使用者驗證的喜好設定。 DisablePasswordSaving 控制 [RDP 用戶端] 對話方塊視窗是否出現 [密碼儲存] 核取方塊，以及是否顯示 MED-V 認證提示。

下列是名為 DisablePasswordSaving 的終端服務原則的原則路徑。

**註冊表**

HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving

**注意**  
您對 DisablePasswordSaving 所做的變更只會影響 RDP 提示至虛擬機器。



下表列出您可以用來設定認證儲存空間與不同設定效果的不同方式：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">設定</th>
<th align="left">結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>停用</strong></p></td>
<td align="left"><p>隨後便會出現 MED-V 提示，且可使用並清除 [接受] 核取方塊。 如果使用者選取核取方塊，就會針對後續使用來緩存認證。 當密碼到期時，最終使用者也有只會出現提示的好處。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>如果使用者沒有選取核取方塊，則會出現 [遠端桌面連線（RDC）] 用戶端提示，而不是 MED-V 提示，且已清除 [接受] 核取方塊。 如果使用者選取核取方塊，則會儲存 RDC 用戶端認證以備日後使用。</p>
<div class="alert">
<strong>重要</strong><br/><p>當使用者輸入時，RDC 不會驗證認證。 如果使用者透過 RDC 提示來緩存認證，可能會有儲存無法正確認證的風險。 在這種情況下，必須在 Windows 認證管理器中刪除不正確的認證。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DisablePasswordSaving</p></td>
<td align="left"><p><strong>啟用</strong></p></td>
<td align="left"><div class="alert">
<strong>注意</strong><br/><p>這種設定較安全，因為它不允許快取使用者認證。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



根據預設，MED-V 安裝會將來賓中的登錄機碼設為抑制「要過期的密碼」提示。 系統只會提示使用者在主機上變更密碼。 主機上更新的認證會傳遞到來賓。

**警告**  
如果您在您的環境中使用群組原則，請知道它可以覆寫登錄機碼，導致來自來賓的密碼提示再次出現。



### 驗證的安全性問題

雖然快取最終使用者的認證能提供最佳的使用者體驗，您必須知道所涉及的風險。

啟用認證快取時，使用者的網域認證會以可還原的格式儲存在 Windows 認證管理員中。 因此，攻擊者可以撰寫以系統層級程式或使用者程式來執行的工具，並會檢索最終使用者的認證。 您只需要將 DisablePasswordSaving 設定為 [**啟用**]，就能減輕此風險。

當 MED-V 驗證已停用，但已啟用 [終端服務原則] 設定時，也會有這個問題。

## 相關主題


[MED-V 作業的安全性最佳做法](security-best-practices-for-med-v-operations.md)









