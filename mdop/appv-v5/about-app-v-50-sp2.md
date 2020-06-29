---
title: 關於 App-V 5.0 SP2
description: 關於 App-V 5.0 SP2
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800729"
---
# 關於 App-V 5.0 SP2


App-v 5.0 SP2 提供改良的整合平臺、更具彈性的虛擬化，以及適用于虛擬化應用程式的強大管理功能。 如需詳細資訊，請參閱[app-v 5.0 概覽](https://go.microsoft.com/fwlink/p/?LinkId=325265)（ https://go.microsoft.com/fwlink/?LinkId=325265) 。

## 標準 App V 5.0 SP2 功能中的變更


下列各節包含應用程式 V 5.0 SP2 之標準功能變更的相關資訊。

### <a href="" id="bkmk-sp2-supported-cfg"></a>Windows Server 2012 R2 和 Windows 8.1 的支援

App-V 5.0 包含 Windows Server 2012 R2 和 Windows 8.1 的支援

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> App-V 5.0 SP2 現在支援使用者的漫遊 AppData 目錄的資料夾重新導向

App V 5.0 SP2 支援漫遊 AppData （% AppData%）資料夾重新導向。 如需詳細資訊，請參閱[規劃在 app-v 中使用資料夾](planning-to-use-folder-redirection-with-app-v.md)重新導向。

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a>套件升級改進與擱置中的任務

在 App-v 5.0 SP2 中，當發佈更新版本的套件或連線群組時，系統不會再提示您關閉正在執行的虛擬應用程式。 如果您嘗試執行相關工作時，封裝或連線群組處於使用中，則會顯示一則訊息，指出該物件已在使用中，且稍後會嘗試該操作。

根據下列規則，將會執行已置於擱置狀態的工作：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務類型</th>
<th align="left">適用的規則</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以使用者為基礎的工作，例如，將套件發佈給使用者</p></td>
<td align="left"><p>暫停的工作將會在使用者登出後執行，然後重新登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>以全域為基礎的工作，例如，全域啟用連接群組</p></td>
<td align="left"><p>當電腦關閉後再重新開機時，會執行待處理的工作。</p></td>
</tr>
</tbody>
</table>

 

當任務放在擱置狀態時，App-v 用戶端也會產生未決工作的登錄機碼，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">以使用者為基礎或以全域為基礎的工作</th>
<th align="left">登錄機碼的產生位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以使用者為基礎的工作</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>全域基礎任務</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

### 使用 App-v 5.0 虛擬化 Microsoft Office 2013 和 Microsoft Office 2010

如需 Microsoft Office 案例支援的 App-v 5.0 的詳細資訊，請使用下列連結。

[為 Application Virtualization (APP-V) 5.0 虛擬化 Microsoft Office 2013](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

**記事** 本檔的重點是建立 Microsoft Office 2013 App-v 5.0 套件。 不過，它也會提供 Microsoft Office 2010 應用程式與 App-v 5.0 相關案例的相關資訊。

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> App-V 5.0 用戶端管理使用者介面應用程式

在舊版 App-V 5.0 中，由 app-v 5.0 用戶端安裝提供用戶端管理使用者介面（UI）。 如果使用 App-v 5.0 SP2，就不會再這麼做。 系統管理員現在可以選擇將 App-V 5.0 用戶端 UI 部署為虛擬應用程式（使用所有受支援的 App-v 部署配置），或安裝為已安裝的應用程式。

如需詳細資訊，請參閱[Microsoft Application Virtualization 5.0 用戶端 UI 應用程式](https://go.microsoft.com/fwlink/p/?LinkId=386345)（ https://go.microsoft.com/fwlink/?LinkId=386345) 。

### 並列（SxS）元件自動封裝及部署

App-V 5.0 SP2 現在會自動偵測並行（SxS）元件，以及在執行 App-v 5.0 SP2 用戶端的電腦上進行部署。 SxS 元件主要由 VC + + 執行時間相依性或 MSXML 所組成。 在舊版 App-V 中，具有 VC 執行時間相依性的虛擬應用程式需要在執行 App-v 5.0 SP2 用戶端的電腦上本機使用這些相依性。

現在支援下列功能：

-   App-v 5.0 sequencer 會自動捕獲套件中的 SxS 元件，不論是否已在執行排序器的電腦上安裝 VC 執行時間。

-   App-V 5.0 用戶端會根據發佈時間所需的方式，自動將所需的 SxS 元件安裝到執行用戶端的電腦上。

-   App-v 5.0 sequencer 會使用 sequencer 報告機制來報告 VC 執行時間相依性。

-   App-v 5.0 sequencer 現在可讓您在執行排序器的電腦上已提供相依性的事件時，排除 VC 執行時間相依性。

### 發佈更新改良功能

App-V 5.0 支援多個新增的功能，以改善針對特定使用者重新整理一組應用程式的整體體驗。

下列清單顯示 [發佈更新] 增強功能：

下列清單包含有關如何啟用新的發佈重新整理改善的詳細資訊。

-   **EnablePublishingRefreshUI** -針對執行 App-v 5.0 用戶端的電腦啟用 [發佈更新進度] 列。

-   **HideUI** -在手動同步處理期間隱藏發佈更新進度列。

### 新的用戶端設定設定

App-v 5.0 SP2 提供下列新的用戶端配置設定：

**EnableDynamicVirtualization** -啟用支援的命令介面延伸、瀏覽器 Helper 物件，以及使用中 X 控制項來虛擬化並與虛擬應用程式一起執行。

如需詳細資訊，請參閱[關於用戶端配置設定](about-client-configuration-settings.md)。

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> App-v 5.0 命令介面延伸

App-v 5.0 SP2 現在支援命令介面延伸。

如需詳細資訊，請參閱[建立及管理 app-v 5.0 虛擬化應用程式](creating-and-managing-app-v-50-virtualized-applications.md)的**APP v 5.0 sp2 shell 擴充支援**區段。

## <a href="" id="---------app-v-5-0-documentation-updates"></a> App-v 5.0 檔更新


App-V 5.0 SP2 提供下列案例的更新檔：

-   [從舊版移轉](migrating-from-a-previous-version-app-v-50.md)

-   [關於 App-V 5.0](about-app-v-50.md)

-   [關於 App-V 5.0 報告](about-app-v-50-reporting.md)（常見問題區段）

## 如何取得 MDOP 技術


App-v 5.0 是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。






## 相關主題


[App-V 5.0 SP2 版本資訊](release-notes-for-app-v-50-sp2.md)

 

 





