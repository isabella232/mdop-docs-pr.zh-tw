---
title: UE-V 2.1 的新功能
description: UE-V 2.1 的新功能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811649"
---
# UE-V 2.1 的新功能


使用者體驗虛擬化2.1 提供了與 UE-V 2.0 相比的這些新功能和功能。 [Microsoft 使用者體驗虛擬化（ue-v）2.1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)提供關於 ue-v 2.1 發行的詳細資訊。

## Office 2013 設定位置範本


UE-V 2.1 包含 Microsoft Office 2013 設定位置範本，改良了 Outlook 簽名支援。 在 UE-V 2.1 中，簽名資料會在使用者裝置之間同步處理。 我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。 客戶不需要再選擇預設的簽名設定。

**記事** 您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。 如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。

 

先前的 UE-V 包含 Microsoft Office 2010 設定位置範本，這些範本是透過 UE-V Agent 自動分發及註冊。 UE-V 2.1 可與 Office 365 搭配使用，以判斷 office 2013 設定是否由 Office 365 所漫遊。 如果設定是由 Office 365 漫遊，就不會透過 UE-V 漫遊。 [Office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供詳細資訊。

若要使用 UE-V 2.1 啟用設定同步處理，請執行下列其中一項操作：

-   使用群組原則來停用 Office 365 同步處理

-   在安裝 Office 2013 期間，請勿啟用 Office 365 同步處理體驗

UE-V 2.1 隨附[office 2013 和 office 2010 範本](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。 此版本會移除 Office 2007 範本。 使用者仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，但仍可在[此處](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得 ue-v 範本庫的範本。

## 修正分散式檔案系統命名空間使用者


UE-V 已新增稱為 SyncProviderPingEnabled 的 UE-V 設定，以改善分散式檔案系統命名空間（DFSN）的支援。 使用 PowerShell 或 WMI 來停用此設定，可讓使用者停用 UE-V ping。 在使用 DFSN 伺服器時，UE-V ping 會導致錯誤，因為這些伺服器不會回應 ping。 [非回應] 可防止 UE-V 同步處理設定。 停用 UE-V ping 可讓 UE-V 同步處理正常運作。

若要停用 UE-V ping，請使用此 PowerShell Cmdlet：

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## 針對認證進行同步處理


UE-V 2.1 可讓客戶同步處理儲存在 Windows 認證管理器中的認證與證書。 此元件預設為停用。 啟用此元件可讓使用者保持其網域認證與憑證同步處理。使用者可以在裝置上一次登入，而這些認證將會在所有 UE-V 啟用的裝置上漫遊該使用者。 [使用 ue-v 2.1 管理認證](https://technet.microsoft.com/library/dn458932.aspx#creds)提供詳細資訊。

**記事** 在 Windows 8 和更新版本中，認證管理員包含網頁認證。 這些認證不會在使用者的裝置之間同步處理。

 

## UE-V 與 Microsoft 帳戶同步處理


UE-V 會偵測到 [使用 OneDrive 同步處理設定] （也稱為 Microsoft 帳戶同步處理）是否已開啟。 如果未將 Microsoft 帳戶設定為同步處理設定，UE-V 會同步處理 Windows 應用程式、AppX 套件，以及裝置之間的 Windows 桌面設定。 這可讓使用者存取其 Microsoft Store app、音樂、圖片及其他支援 Microsoft 帳戶的應用程式，而不需要在企業防火牆以外進行同步處理。 UE-V 會檢查群組原則是否會停止同步處理設定與 OneDrive，或使用者是否在使用者控制項中停用**此電腦上**的 [同步處理您的設定]。

## 支援 SyncMethod 外部


名為「**外部**」的新[SyncMethod](https://technet.microsoft.com/library/dn554321.aspx)設定會指定將 ue-v 設定寫入使用者電腦上的本機資料夾，而任何外部同步引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。

## VDI 模式的增強支援


UE-V 2.1 包含在最終使用者之間共用的[VDI 會話支援](https://technet.microsoft.com/library/dn458932.aspx#vdi)。 作為系統管理員，您可以註冊和設定特殊的 VDI 範本，這可確保 UE-V 在非持續性的 VDI 會話中完整保留其所有功能。

**記事** 如果您沒有為非持久性 VDI 會話啟用 VDI 模式，則某些功能無法運作，例如備份/還原及 LKG。

 

## 系統管理備份和還原


您可以在使用 UevTemplateProfile PowerShell Cmdlet 的**備份**或**漫遊（預設）** 設定檔中，使用 [設定位置] 範本，在使用者採用新的裝置時，還原其他設定。 這可讓電腦設定與新電腦同步處理，以及使用者設定。 系統會針對該裝置備份指派給備份設定檔的範本，並針對每個裝置進行設定。 [在 ue-v 2. x 中管理系統管理備份和還原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

## 其他 Windows 設定的同步處理


UE-V 現在會同步處理觸控式鍵盤個人化設定、拼寫字典，並啟用應用程式切換以使用 [最近的 App] 和 [螢幕邊緣] 設定，在 Windows 8 和 Windows 8.1 裝置之間進行同步處理。






## 相關主題


[UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

[準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[Microsoft User Experience Virtualization (UE-V) 2.1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





