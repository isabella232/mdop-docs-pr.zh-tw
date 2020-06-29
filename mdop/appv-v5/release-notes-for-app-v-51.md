---
title: App-V 5.1 的版本資訊
description: App-V 5.1 的版本資訊
author: dansimp
ms.assetid: 62c5be3b-0a46-4512-93ed-97c23184f343
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2016
ms.openlocfilehash: 7437a16bc10b21bb15b0f8307c2711177e78cb72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800311"
---
# App-V 5.1 的版本資訊


下列是 Microsoft Application Virtualization （App-v）5.1 的已知問題。

## 在 Windows 10 上的 App-v 5.0 SP3 管理伺服器與 App-v 5.1 用戶端之間的發佈更新期間發生錯誤


將套件從 App-v 5.0 SP3 管理伺服器同步處理到 Windows 10 上的 App-v 5.1 用戶端時，會在發佈重新整理期間產生錯誤。 發生此錯誤的原因是，app-v 5.0 SP3 伺服器不知道發佈 URL 中指定的 Windows 10 作業系統。 這個問題針對 App-v 5.1 發佈伺服器已修正，但無法 backported 至 App-v 5.0 SP3 或更舊版本。

**解決方法**：將 App-v 5.0 管理伺服器升級至 Windows 10 用戶端的 App-v 5.1 管理伺服器。

## 如果您使用 App-v 5.1 Server 設定，就不會針對將在全域發行的套件套用自訂設定。


如果您將套件指派給包含電腦帳戶的 AD 群組，並使用 App-v 伺服器將自訂設定套用至該群組，則自訂設定將不會套用至這些電腦。 App-v 5.1 用戶端將在全域發佈指派給電腦帳戶的套件。 不過，它會在每個使用者的設定檔中儲存每位使用者的自訂設定檔。 全域發佈的套件將無法存取此自訂設定。

**解決方法**：執行下列其中一項操作：

-   將套件指派給只包含使用者帳戶的群組。 這將確保套件的自訂設定會儲存在每個使用者的設定檔中，且會正確套用。

-   使用 AppvClientPackage Cmdlet 和– DynamicDeploymentConfiguration 參數，建立自訂部署設定檔，並將它套用到用戶端上的套件。 如需詳細資訊，請參閱[關於 App-V 5.1 動態配置](about-app-v-51-dynamic-configuration.md)。

-   使用 App-v 5.1 排序器，建立含自訂設定的新套件。

## 在新的 App-v 5.1 Server 安裝之後，不會刪除伺服器檔案


如果您卸載 App-v 5.0 SP1 伺服器，然後安裝 App-v 5.1 伺服器，安裝會失敗、安裝了錯誤的管理伺服器版本，且會傳回錯誤訊息。 發生這個問題的原因是，當您卸載 app-v 5.0 SP1 時，伺服器檔案並未刪除，所以安裝程式會執行升級，而不是全新的安裝。

因應**措施：請**先刪除此登錄機碼，然後再開始安裝應用程式-V 5.1：

在 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall 下，找出並刪除包含 DWORD 值 "DisplayName" （含值資料 "Microsoft Application Virtualization （App-v） Server"）的安裝 GUID 金鑰。 這是唯一應該刪除的索引鍵。

## 手動新增的檔案類型關聯無法正確儲存


使用應用程式升級嚮導結尾的 [快速鍵] 和 [FTAs] 索引標籤，以手動方式新增到應用程式套件中的檔案類型關聯，並不會正確儲存。 當您再次更新已儲存的套件時，App-v 用戶端或 Sequencer 將無法使用它們。

因應**措施：若**要新增檔案類型關聯，請開啟套件以進行修改，然後執行更新嚮導。 在安裝步驟中，透過作業系統新增新的檔案類型關聯。 排序器會偵測系統登錄中的新關聯，並將它新增至套件的虛擬機器碼，以供用戶端使用。

## 當您將共用內容存儲區（SCS）模式中的資料流程封裝到同時使用 AppLocker 管理的用戶端時，額外的資料會寫入本機磁片。


若要減少寫入用戶端本機磁片的資料量，您可以在應用程式 V 5.1 用戶端上啟用 SCS 模式，以根據需要對流進行套件的內容。 不過，如果 AppLocker 在套件中管理應用程式，則某些資料可能會寫入到用戶端的本機磁片，而不會以其他方式寫入。

因應**措施：無**

## 在 [管理主控台新增套件] 對話方塊中，使用 Chrome 或 Firefox 時無法使用 [流覽] 按鈕


在管理主控台的 [套件] 頁面上，如果您按一下右下角的 [**新增] 或 [升級**]，就會出現 [**新增套件**] 對話方塊。 如果您是使用 Chrome 或 Firefox 作為瀏覽器來存取管理主控台，您將無法流覽至套件的位置。

因應**措施：在**[**新增套件**輸入] 欄位中，輸入或複製並貼上套件的路徑。 如果管理主機擁有此路徑的存取權，您就可以新增套件。 如果套件位於網路共用位置，您可以執行下列步驟，流覽至使用檔案資源管理器的位置：

1.  按下**Shift 鍵**，並以滑鼠右鍵按一下套件檔案

2.  選取 [**複製為路徑**]

3.  將路徑貼到 [**新增套件**] 對話方塊的輸入欄位

## <a href="" id="upgrading-app-v-management-server-to-5-1-sometimes-fails-with-the-message--a-database-error-occurred-"></a>將 App-v 管理伺服器升級至5.1 時，有時會失敗，並出現「發生資料庫錯誤」的訊息


如果您安裝應用程式-V 5.0 SP1 管理伺服器，然後嘗試升級至 App-v 5.1 伺服器，且已設定並啟用多個連線群組，則會顯示下列錯誤：「資料庫發生錯誤。 原因：「不正確欄名稱 ' PackageOptional」。 不正確欄名稱 ' VersionOptional」。

因應措施：在您的 SQL 資料庫**上執行這個**命令：

`ALTER TABLE AppVManagement.dbo.PackageGroupMembers ADD PackageOptional bit NOT NULL DEFAULT 0, VersionOptional bit NOT NULL DEFAULT 0`

其中，"AppVManagement" 是資料庫的名稱。

## 如果您新增或移除選擇性套件，使用者就無法在使用者發佈的連線群組中開啟套件


在執行 RDS 用戶端的環境中，或在每個電腦上有多個併發使用者的情況下，如果在連線群組中新增或移除選擇性套件，則登入使用者無法開啟使用者發佈連線群組中的套件中的應用程式。

因應**措施：讓**使用者登出後再重新登入。

## 當連線群組只發行給使用者時，會出現錯誤訊息


當您執行修復 AppvClientConnectionGroup 時，會顯示下列錯誤，即使連線群組只發行給使用者時也一樣：「內部 App-v 整合錯誤：套件未針對使用者整合。 請確定套件已新增至電腦併發布給使用者。

**解決方法**：執行下列其中一項操作：

-   發佈連線群組中的所有套件。

    當修復的連線群組有遺失或無法提供給使用者的套件（也就是不是全域發佈或使用者）時，就會發生此問題。 不過，如果所有的連線群組套件都可用，修復就會運作，因此請確定所有套件都已發佈。

-   使用 [修復 AppvClientPackage] 命令（而不是 [修復] AppvClientConnectionGroup 命令）個別修復套件。

    決定使用者可以使用哪些套件，然後針對每個套件執行一次 AppvClientPackage 命令。 使用 PowerShell Cmdlet 執行下列動作：

    1.  取得連接群組中的所有套件。

    2.  查看每個套件目前是否已發佈。

    3.  如果套件目前已發佈，請在該套件上執行 Repair AppvClientPackage。

## 無法在 Sequencer 中正確顯示圖示


修改 App-v 排序器中的套件時，[快速鍵] 和 [檔案類型關聯] 索引標籤中的圖示無法正確顯示。 當圖示大小不是16x16 或32x32 時，就會發生此問題。

**解決方法**：只使用16x16 或32x32 的圖示。

## 管理資料庫已不再需要 InsertVersionInfo sql 腳本


在 app-v 5.0 SP3 之後的 App-v management 資料庫版本中，不需要 InsertVersionInfo 腳本。

必須依據[知識庫文章 3031340](https://support.microsoft.com/kb/3031340)中的**步驟 2**來更新 [sql 腳本]。

**重要** 
在 app-v 5.0 SP3 的版本之後，不需要**步驟 1** 。

 

## 不支援 Microsoft Visual Studio 2012


App-V 5.1 不支援 Visual Studio 2012。

因應**措施：無**

## App 的應用程式檔案名限制-V 5. 排序器


App-V-x Sequencer 無法使用與 "CO_ x" 相符的檔案名來排序應用程式， &lt; &gt; 其中 x 是任何數位。 將會產生錯誤0x8007139F。

**解決方法**：使用不同的檔案名

## 裝載套件時，發生間歇性的 [找不到檔案] 錯誤


在安裝套件時，有時會產生「找不到檔案」（0x80070002）錯誤。 通常，當 App-v 中的資料夾包含許多檔案（亦即20K 或更多檔案）時，就會發生這種情況。 這可能會導致串流時間超過預期，而且會產生「找不到檔案」錯誤的時間。

因應**措施：從**HF06 開始，引入了新的登錄機碼，以啟用延伸此超時期間。

<table>
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<tbody>
<tr>
<td align="left">路徑</td>
<td align="left">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\Streaming</td>
</tr>
<tr>
<td align="left">設定</td>
<td align="left">StreamResponseWaitTimeout</td>
</tr>
<tr>
<td align="left">類型</td>
<td align="left">DWORD</td>
</tr>
<tr>
<td align="left">訂購</td>
<td align="left">秒</td>
</tr>
<tr>
<td align="left">預設值</td>
<td align="left">500<br />
<strong>注意 </strong> ：如果未定義登錄機碼或 &lt; 指定值 = 5，則此值為預設值。
</td>
</tr>
</tbody>
</table>






## 相關主題


[關於 App-V 5.1](about-app-v-51.md)

 

 





