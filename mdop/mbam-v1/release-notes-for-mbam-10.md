---
title: MBAM 1.0 版本資訊
description: MBAM 1.0 版本資訊
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811510"
---
# MBAM 1.0 版本資訊


**若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。**

安裝 Microsoft BitLocker 管理和監控（MBAM）之前，請先閱讀這些版本資訊。

這些版本資訊包含成功安裝 MBAM 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 MBAM 檔有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 關於產品檔


如需 MBAM 檔的相關資訊，請參閱 Microsoft TechNet 上的 [MBAM] 首頁。

若要取得 MBAM 檔的可下載複本，請參閱 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft 下載中心。

## 提供意見反應


我們對您在 MBAM 的意見反應感興趣。 您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。

**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。

 

如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。

如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。

## MBAM 1.0 的已知問題


本節包含有關 MBAM 設定和安裝之已知問題的發行記錄。

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a>如果您在安裝期間選取 [使用憑證來加密網路通訊] 選項，現有的資料庫連線和相依的應用程式就會停止運作

您可以在安裝 [復原] 和 [硬體資料庫] 或 [合規性狀態資料庫] 功能之後，設定**加密網路通訊**的 MBAM。 如果您選擇設定 MBAM 以進行加密的網路通訊，MBAM 的安裝程式會將 SQL Server 資料庫引擎的實例設定為使用安全通訊端層（SSL），以進行適用資料庫與管理與監視伺服器以及合規性和審核報表伺服器功能之間的通訊。

-   如果 SQL Server 資料庫引擎實例尚未設定為使用 SSL，請 MBAM 安裝程式將其設定為使用 SSL。 這可防止嘗試在 SQL Server 資料庫引擎實例上使用非 MBAM 資料庫的應用程式與其資料庫進行通訊。

-   如果 SQL Server 資料庫引擎的實例已設定為使用 SSL，則會將其設定為使用使用者在安裝期間選取的憑證。 如果這個證書與已在使用的憑證不同，就可以避免在 SQL Server 資料庫引擎實例上使用 SQL Server 資料庫的應用程式執行。

因應措施 **：** 所有

### 當您使用本機系統管理員帳戶時，在安裝期間 MBAM 安裝失敗

如果您使用的是本機系統管理員帳戶，MBAM 安裝程式就會失敗。 記錄檔包含下列資訊：

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

因應措施 **：** 當您安裝 MBAM 時，請在伺服器電腦上使用網域帳戶和系統管理認證。

### 如果您選取 [不要加密網路通訊]，MBAM 安裝程式會將 SQL Server 資料庫引擎的實例重新設定為不使用 SSL

當您安裝 [恢復] 和 [硬體] 資料庫或 [合規性狀態] 資料庫時，您可以使用安裝程式來設定 MBAM，方法是選取**加密的網路通訊**。 如果您決定不加密網路通訊，MBAM 安裝程式會重新設定 SQL Server 資料庫引擎的實例，使其不使用 SSL。

-   如果 SQL Server 資料庫引擎的實例已設定為使用 SSL，MBAM 安裝程式會在 SQL Server 資料庫引擎的實例上停用 SSL。 這會變更使用與 SQL Server 資料庫引擎實例上的 MBAM 資料庫無關之資料庫之應用程式之間的通訊安全。

因應措施 **：** 所有

### 缺少 Internet Information Services （IIS）管理腳本與工具網頁伺服器功能的先決條件

MBAM 安裝程式會依賴 IIS 管理腳本與工具網頁伺服器功能，但不是強制性的先決條件。 伺服器安裝程式可讓您在遺失此功能時安裝 MBAM。 不過，這將會導致備份服務 MBAM VSS 書寫器開始並停止，因為它找不到 Windows Management Instrumentation （WMI）和 Internet Information Services （IIS）提供者。 此條件不會出現錯誤訊息，但在事件記錄檔中則不會發生。 不含 IIS 管理腳本與工具的 MBAM 安裝，就不會針對 MBAM 執行備份作業。

因應措施 **：** 在您啟動 MBAM 安裝程式之前，請先確認已安裝 IIS 管理腳本及工具網頁伺服器功能。

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a>安裝程式設定為使用憑證時，MBAM 安裝程式在「安裝選取的功能」階段停止回應

MBAM 安裝程式在**安裝選取的功能**階段期間停止回應。 這會在您選取 [**使用憑證來加密網路通訊**] 選項期間，在安裝恢復與硬體資料庫或合規性狀態資料庫期間發生。 此外，如果 SQL Server 資料庫引擎的實例無法存取在安裝期間指定的憑證，MBAM 安裝程式就會停止回應。

因應措施 **：** 更新憑證上的許可權，讓 SQL Server 資料庫引擎適用實例的 Windows 服務可以存取憑證。 您也可以變更 SQL Server 資料庫引擎實例在其上執行的帳戶，以供資料庫引擎使用憑證。 若要判斷憑證的許可權，請在命令提示字元中輸入下列命令： **certutil-v-將 MY**

### 安裝 SQL Server Reporting Services 時，MBAM 安裝程式暫停

在 MBAM 安裝期間，當您選取的 SQL Server Reporting Services （SSRS）實例無法使用或未正確設定時，MBAM 的安裝程式在嘗試與 SSRS 實例通訊時，最多可能暫停一分鐘。

因應措施 **：** 在安裝程式嘗試與 SSRS 實例取得聯繫時，請至少等待1分鐘的時間，MBAM 設定才能繼續。

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a>在安裝之後，系統管理和監控伺服器不會執行

MBAM 安裝程式成功安裝 [管理及監視伺服器] 功能後，當您嘗試存取 MBAM 管理員網站時，MBAM 會顯示錯誤訊息。 這個問題可能是由下列其中一個原因所導致：

-   在 MBAM 安裝之後，系統會移除管理和監視伺服器上的一個或多個先決條件。

-   在伺服器上安裝一個或多個先決條件之後，在執行 MBAM 安裝程式之前，這些系統會將它們移除。

因應措施 **：** 請參閱 MBAM 檔，並確認已安裝所有 MBAM 必備元件。

### 在安裝過程中按一下 [檔] 連結會導致安裝程式完成後出現應用程式錯誤

當您在安裝期間按一下檔連結，然後按一下 [**取消**] 或 [在安裝程式成功完成後**完成]** ，就會出現應用程式錯誤訊息。 這個問題是由於 Windows 工作排程器中發生存取侵犯錯誤所造成。

因應措施 **：** 所有. 您可以忽略這個錯誤。

### 失敗的 MBAM 設定無法移除新資料庫

如果 MBAM 設定失敗，安裝程式可能不會移除新建立的資料庫。 這可能會導致後續安裝失敗。

因應措施 **：** 在後續安裝期間，為資料庫實例選擇其他名稱。

### MBAM 安裝程式無法辨識有效的網路負載平衡群集憑證

在 MBAM 管理和監視伺服器安裝期間，選取 [網路加密] 選項時，系統不會將群集憑證識別為有效的憑證。 當已安裝與資料庫通訊的憑證，但由於負載平衡群集而遭到拒絕通訊時，就認為它是有效的。

因應措施 **：** 確認可存取與憑證相關聯的憑證吊銷清單（CRL），或使用不需要使用 CRL 驗證的憑證。

## 版本資訊版權資訊


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。 所有其他商標都是其各自擁有者的財產。



## 相關主題


[關於 MBAM 1.0](about-mbam-10.md)

 

 





