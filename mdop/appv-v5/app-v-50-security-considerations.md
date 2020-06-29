---
title: App-V 5.0 安全性考量
description: App-V 5.0 安全性考量
author: dansimp
ms.assetid: 1e7292a0-7972-4b4f-85a9-eaf33f6c563a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fcd740345be7f532502b8996d8d2b1f4437ed6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800686"
---
# App-V 5.0 安全性考量


本主題包含 App-v 5.0 的帳戶和群組、記錄檔案及其他安全相關考慮事項的簡短概述。

**重要**  
App-v 5.0 不是安全性產品，而且不提供任何對安全環境的保證。



## PackageStoreAccessControl （PSAC）功能已棄用


從2014年6月起生效，Microsoft Application Virtualization （App-v） 5.0 Service Pack 2 （SP2）中引入的 PackageStoreAccessControl （PSAC）功能在單一使用者和多使用者環境中都已被棄用。

## 一般安全性考慮


**瞭解安全性風險。** App-V 5.0 最嚴重的風險是它的功能可能會被未經授權的使用者劫持，這樣就可以在 App-V 5.0 用戶端重新設定重要資料。 由於拒絕服務攻擊，短時間內的應用程式-V 5.0 功能損失通常不會造成災難性影響。

**在物理上保護您的電腦**。 安全性不完整，沒有實際的安全性。 任何人都能以物理方式存取 app-v 5.0 伺服器，可能會攻擊整個用戶端基礎。 任何潛在的物理攻擊都必須被視為高風險，並適當地減輕問題。 App-v 5.0 伺服器應該儲存在具有可控存取權的物理安全伺服器機房中。 使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。

**將最新的安全性更新套用至所有電腦**。 若要掌握最新的作業系統、Microsoft SQL Server 和 App-v 5.0 更新，請訂閱安全性通知服務（ <https://go.microsoft.com/fwlink/p/?LinkId=28819> ）。

**使用強式密碼或密碼片語**。 針對所有 App-v 5.0 和 App-v 5.0 系統管理員帳戶，請務必將強式密碼搭配15個或以上的字元使用。 請勿使用空白密碼。 如需密碼概念的詳細資訊，請參閱 TechNet 上的「帳戶密碼及原則」白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。

## App-v 5.0 中的帳戶和群組


使用者帳戶管理的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。 接著，將 [網域通用帳戶] 新增至 App-v 5.0 伺服器上必要的 App-v 5.0 本機群組。

**注意**  
需要連接至發佈伺服器的 app-v 用戶端電腦帳戶必須是發佈伺服器的**使用者**本機群組的一部分。 根據預設，網域中的所有電腦都是 [**授權的使用者**] 群組的一部分，而這是 [**使用者**本機] 群組的一部分。



### <a href="" id="-------------app-v-5-0-server-security"></a> App-V 5.0 伺服器安全性

在 App-v 5.0 設定期間不會自動建立任何群組。 您應該建立下列 Active Directory 網域服務全域群組，以管理 App-v 5.0 伺服器作業。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">群組名稱</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 管理管理員群組</p></td>
<td align="left"><p>用來管理 App-v 5.0 管理伺服器。 這個群組是在 App-V 5.0 管理伺服器安裝期間建立的。</p>
<div class="alert">
<strong>重要</strong><br/><p>完成安裝後，沒有方法可以使用管理主控台建立群組。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>管理服務帳戶的資料庫讀/寫</p></td>
<td align="left"><p>提供管理資料庫的讀/寫存取權。 此帳戶應該在 App-V 5.0 管理資料庫安裝期間建立。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Management Service 安裝管理員帳戶</p>
<div class="alert">
<strong>注意</strong><br/><p>只有在將管理資料庫與服務分開安裝時，才需要這麼做。</p>
</div>
<div>

</div></td>
<td align="left"><p>提供管理資料庫中架構版本資料表的公用存取權。 此帳戶應該在 App-V 5.0 管理資料庫安裝期間建立。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Reporting Services 安裝系統管理員帳戶</p>
<div class="alert">
<strong>注意</strong><br/><p>只有在已將報表資料庫與服務分開安裝時，才需要這麼做。</p>
</div>
<div>

</div></td>
<td align="left"><p>在報表資料庫中公開存取架構版本表。 此帳戶應該在 App-V 5.0 報告資料庫安裝期間建立。</p></td>
</tr>
</tbody>
</table>



請考慮下列其他資訊：

-   存取套件共用（如果共用與管理伺服器位於相同的電腦上），**網路**服務必須擁有共用的讀取存取權。 此外，每個應用程式 V 用戶端電腦都必須具有套件共用的讀取存取權。

    **注意**  
    在舊版 App-v 中，套件共用稱為「內容共用」。



-   使用管理伺服器註冊發佈伺服器-必須在管理伺服器上註冊發佈伺服器。 例如，必須將它新增到資料庫，才能讓發佈伺服器電腦帳戶呼叫管理服務 API。

### <a href="" id="-------------app-v-5-0-package-security"></a> App-v 5.0 套件安全性

下列將協助您規劃如何確保虛擬化套件是安全的。

-   如果應用程式安裝程式將存取控制清單（ACL）套用至檔案或目錄，則該 ACL 不會保留在套件中。 部署套件時，如果使用者修改了檔案或目錄，就會在 **% userprofile%** 中繼承 acl，或繼承目的電腦目錄的 acl。 如果檔案或目錄不存在於虛擬檔案系統位置，則會發生前個情況;如果檔案或目錄存在於虛擬檔案系統位置（例如 **% windir%**），就會發生後一個情況。

## <a href="" id="---------app-v-5-0-log-files"></a> App-v 5.0 記錄檔


在 App-v 5.0 設定期間，系統會在安裝使用者的 **% temp%** 資料夾中建立安裝記錄檔案。
