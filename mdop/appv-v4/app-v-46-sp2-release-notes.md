---
title: App-V 4.6 SP2 版本資訊
description: App-V 4.6 SP2 版本資訊
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809297"
---
# App-V 4.6 SP2 版本資訊


**若要搜尋這些版本筆記，請按 CTRL + F。**

在安裝 Microsoft Application Virtualization （App-v） 4.6 SP2 之前，請先閱讀這些版本資訊。

這些版本資訊包含成功安裝應用程式虛擬化 4.6 SP2 所需的資訊。 版本資訊中也包含產品檔中不提供的資訊。 如果這些版本資訊與其他 App-v 4.6 SP2 檔之間有差異，最新變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 關於產品檔


如需 App-v 相關檔的詳細資訊，請參閱 Microsoft TechNet 上的 [[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkID=232982)] 頁面。

## 提供意見反應


我們對 App-v 4.6 SP2 的意見反應感興趣。 您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。

**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品發行的未來變更。

 

如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。

如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a>App-V 4.6 SP2 的已知問題


### 當您按順序時，系統會停用非系統物理磁片磁碟機的短檔案名支援

當您在 Windows 8 或 Windows Server 2012 上順序時，短檔案名（8.3）的支援會預設為非系統物理磁片磁碟機停用。

在先後順序站上，與主要虛擬應用程式目錄（例如，"Q:\\appname"）相關聯的基礎物理磁片磁碟機，必須提供短檔案名（8.3）支援，才能讓 App-V 4.6 SP2 排序器在建立虛擬應用程式套件時產生短檔案名。 預設會針對 Windows 8 或 Windows Server 2012 上的非系統物理磁片磁碟機停用短檔案名（8.3）支援。

因應措施 **：** 啟用在非系統物理磁片磁碟機上的短檔案名（8.3）支援。 您可以使用下列命令，在 Windows 8 或 Windows Server 2012 上啟用短檔案名支援。

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

例如，如果磁碟機字母是「問：」，請使用下列命令：

``` syntax
fsutil 8dot3name set Q: 0
```

**記事** 您不需要在 App-V 用戶端上變更此設定，因為 App-v 檔案系統會在 Windows 8 或 Windows Server 2012 上正確處理短路徑。

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> 在 Windows 8 上，app-v 不會覆寫檔案類型或通訊協定關聯的預設處理常式

如果您在 Windows 8 上使用 [**控制台**] 中的 [**預設程式**] 選取預設的應用程式，app-v 將不會覆寫該應用程式的相關檔案類型關聯。

因應措施 **：** 所有.

### Windows 8 上的 mailto 可按一下連結的選項不會提供虛擬化 Outlook 2010

Mailto 命令介面擴展不會在 Windows 8 上提供虛擬化的 Outlook 2010。 例如，如果您在 Windows 8 上的虛擬化 Outlook 2010 中按一下 [mailto：] 連結，就不會建立新的電子郵件視窗。 此選項可在 Windows 7 和舊版 Windows 作業系統上正常運作。

因應措施 **：** 所有.

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> 在使用 Microsoft Update 的所有地區設定中，未提供 Application Virtualization 4.6 SP2 更新

當您使用 Microsoft Update 時，適用于下列語言地區設定的 App-v 4.6 SP2 更新無法使用：

-   哈薩克文

-   印度文

-   塞爾維亞文-西瑞爾文

因應措施 **：** 如果您使用的是 Microsoft Windows Server Update Services （WSUS），請使用英文版的更新，或從 Microsoft 更新目錄下載更新。

## 版本資訊版權資訊


Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。 所有其他商標都是其各自擁有者的財產。



## 相關主題


[關於 Microsoft Application Virtualization 4.6 SP2](about-microsoft-application-virtualization-46-sp2.md)

 

 





