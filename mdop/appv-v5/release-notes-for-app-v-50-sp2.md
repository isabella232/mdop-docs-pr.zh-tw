---
title: App-V 5.0 SP2 版本資訊
description: App-V 5.0 SP2 版本資訊
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800316"
---
# App-V 5.0 SP2 版本資訊


**若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。**

安裝 App-v 5.0 SP2 之前，請先通讀這些版本資訊。

這些版本資訊包含成功安裝 App-v 5.0 SP2 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 5.0 檔之間有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 關於產品檔


如需 App-V 5.0 檔的相關資訊，請參閱 Microsoft TechNet 上的 app-v 5.0 首頁。

## 提供意見反應


我們對 App-v 5.0 的意見反應感興趣。 您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。

**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。

 

如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。

如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。

## 應用程式虛擬化 5.0 SP2 的修補程式套件4已知問題


### 卸載應用程式虛擬化 5.0 SP2 的修復程式套件4之後，套件停止運作

當應用程式虛擬化 5.0 SP2 的修補程式套件4已移除5.0 時，發佈的套件會停止運作。

避免

如果下列資料夾存在，則必須將它刪除：

**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **用戶端**  \\ **VFS**  \\ 已發佈的每個套件的** &lt; 封裝識別碼 &gt; ** 。

**記事** 您必須具備較高的許可權才能刪除此資料夾。

 

若要使用腳本，針對電腦上的每個使用者帳戶，以及在安裝應用程式虛擬化 5.0 SP2 的修復程式套件4之後所發佈的每個套件識別碼：

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   即使從上一節的目錄刪除資料夾後，快速鍵仍會保留在使用者會話中，因此您可以按一下快捷方式來再次執行應用程式。 您不需要重新發佈應用程式。

-   對於使用者發佈的封裝及全域發佈套件（例如 Microsoft Office2013），會發生這個問題。 在這兩種類型的套件中都必須刪除該資料夾。

-   您不需要刪除漫遊應用程式資料中的 VFS 資料夾（**% appdata%**）。 只有 **% localappdata%** 必須刪除。

### Microsoft Office 整合指向錯誤的檔案系統位置

Microsoft Office 整合指向錯誤的檔案系統位置（Groove.exe 錯誤訊息）。

避免

使用下列其中一種方法：

1.  升級後刪除開機檔案夾中的快捷方式。

2.  使用腳本變更開機檔案夾中的快捷方式。

3.  使用部署設定檔，指定整合根的快捷方式目標。

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> 應用程式虛擬化5.0 的修補程式套件 4 SP2 安裝程式可能需要花費很長的時間

應用程式虛擬化 5.0 SP2 安裝程式的修復程式套件4可能需要花很長的時間，這取決於現有套件快取中所儲存的檔案數目。

在針對應用程式虛擬化 5.0 SP2 安裝的修復程式套件4中更新關聯的套件安全性描述項，會對安裝所需的時間產生很大的影響。 在先前，安裝安裝為 [持續時間] 的標準。 不過，它現在依賴您在套件快取中暫存的檔案數目。

因應措施：無

### 卸載應用程式虛擬化5.0 的修復程式套件4如果使用的是 JIT V 套件，SP2 會失敗

如果您安裝應用程式虛擬化 5.0 SP2 的修補程式套件4，然後嘗試在使用即時虛擬化（JIT-V）時卸載此熱修復程式，則在下列所有條件成立時，該作業將會失敗：

-   您是使用 Windows 安裝程式檔案（.msi）安裝，然後使用 Microsoft Installer 修補程式檔案（.msp）來套用更新。

-   您嘗試使用 [控制台] 中的 [新增或移除程式] 專案來卸載更新。

-   電腦上正在執行 JIT 啟用的套件。

解決方法：完成下列步驟：

1.  開啟 Windows PowerShell，然後執行下列命令：

    -   **匯入-模組 appvclient**

    -   **AppvClientPackage |停止 AppvClientPackage**

2.  使用 [新增或移除程式] 卸載更新。

## App-v 5.0 SP2 的已知問題


### <a href="" id="bkmk-folderredirection"></a>App-V 用戶端資料夾重新導向有時無法將檔案從% AppData% 移至% LocalAppData%

當% AppData% 是您針對資料夾重新導向所設定的共用網路資料夾時，當使用者切換電腦時，或當他們的本地 AppData 在登出後再重新登入時，可能會遺失最終使用者對 AppData （漫遊）所做的變更。 發生此錯誤的原因是登錄機碼（AppDataTime）會指出最近已知上傳的與本機快取 AppData 的同步處理。

解決方法：當使用者登入或關閉時，手動刪除每個相關套件的下列登錄機碼：

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

當使用者登入後第一次在套件中啟動應用程式時，App-v 會強制下載 zipped% AppData%，即使% LocalAppData% 已經是最新的。

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> App-v 5.0 Service Pack 2 （App-v 5.0 SP2）不包含新版本的 App-v Server

App-V 5.0 SP2 不包含新版的 App-v 伺服器。 如果您要部署在您的環境中執行 Windows 8.1 的 App-v 5.0 SP2 用戶端，並規劃使用 App-v 基礎結構管理用戶端，您必須安裝[Microsoft Application Virtualization 5.0 Service Pack 1 的修補程式套件 2](https://go.microsoft.com/fwlink/?LinkId=386634)。 (https://go.microsoft.com/fwlink/?LinkId=386634)

如果您正在執行和管理 App-v 5.0 SP2 用戶端使用下列任何一種方法，則不需要用戶端更新程式：

-   獨立模式。

-   Configuration Manager。

-   協力廠商 ESD。

App-v 5.0 SP2 用戶端與 Windows 8.1 完全相容

因應措施：無。

## 版本資訊版權資訊


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。 所有其他商標都是其各自擁有者的財產。








## 相關主題


[關於 App-V 5.0 SP2](about-app-v-50-sp2.md)

 

 





