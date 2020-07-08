---
title: App-V 升級檢查清單
description: App-V 升級檢查清單
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802337"
---
# App-V 升級檢查清單


嘗試升級至 Microsoft Application Virtualization （App-v）4.5 或更新版本之前，您必須先將 App-v 4.1 之前的任何版本升級至 App-v 4.1。 您應該先規劃升級用戶端，然後再升級伺服器元件。 已升級至 app-v 4.5 的 app V 用戶端會繼續搭配尚未升級的 App-v 伺服器使用。 已升級至 App-v 4.5 的伺服器不支援舊版用戶端。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">參考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>升級 App-v 用戶端。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)">如何升級 Application Virtualization Client</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>升級 app-v 伺服器和資料庫。</p>
<div class="alert">
<strong>重要</strong><br/><p>如果您有多個伺服器共用存取 App V 資料庫，所有這些伺服器都必須在資料庫升級時離線。 您應該遵循資料庫升級的一般業務做法，但我們建議您先使用資料庫的備份複本來測試資料庫升級。 接著，您應該選取其中一個伺服器進行第一次升級，這會升級資料庫架構。 成功升級生產資料庫之後，您就可以在其他伺服器上升級 App-v 軟體。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升級伺服器和系統元件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>升級 app-v Management Web 服務。</p>
<p>此步驟僅適用于管理 Web 服務位於個別伺服器上，這會要求您在該個別伺服器上執行伺服器安裝程式，以升級管理 Web 服務。 否則，先前的伺服器升級步驟會自動升級管理 Web 服務。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升級伺服器和系統元件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>升級 app-v 管理主控台。</p>
<p>此步驟僅適用于管理主控台位於不同的電腦上，這會要求您在該個別電腦上執行伺服器安裝程式，以升級主機。 否則，先前的伺服器升級步驟將會升級管理主控台。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">如何升級伺服器和系統元件</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>升級 App-v 排序器。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)">如何升級 Application Virtualization Sequencer</a></p></td>
</tr>
</tbody>
</table>



## 其他升級考慮事項


-   在版本4.2 中排序的任何虛擬應用程式套件，都不需再次排序，就能與版本4.5 搭配使用。 不過，如果您想要套用預設的存取控制清單（Acl）或產生 Windows 安裝程式檔案，您應該考慮將虛擬套件升級為 Microsoft Application Virtualization 4.5 格式。 這是一個簡單的程式，只需要使用 App-v 4.5 排序器開啟並儲存現有的虛擬應用程式套件。 您可以使用應用程式 VSequencer 命令列介面自動化這種做法。 如需詳細資訊，請參閱[如何使用 App-v 排序器建立或升級虛擬應用程式](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

-   4.5 排序器的其中一個功能是，可以建立 Windows 安裝程式（.msi）檔案，做為虛擬應用程式套件與電子軟體發佈（ESD）系統（例如 Microsoft 端點設定管理員）的互通性的控點。 使用 MSI 工具所建立的舊版 Windows 安裝程式檔案，這些檔案會在隨後升級至 App-v 4.5 的 4.1 App-v 工具或4.2 用戶端上，繼續運作，不過這些檔案無法在 App-v 4.5 用戶端上安裝。 不過，除非在 App-v 4.5 排序器中升級，否則無法移除或升級它們。 早于4.5 的原始 App-v 套件必須在 App-v 4.5 排序器中開啟，然後另存為 Windows 安裝程式檔案。

    **注意**  
    如果 App-v 4.2 用戶端已升級至 App-v 4.5，則可以使用腳本來在版本4.5 用戶端上保留版本4.2 套件，並允許管理它們。 此腳本必須將兩個檔案（msvcp71.dll 和 msvcr71.dll）複製到 App V 安裝資料夾，並在登錄機碼底下設定下列登錄機碼值： \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]：

    "ClientVersion" = "4.2.1.20"

    "GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" （全域可寫位置）



-   在 app-v 4.6 用戶端上執行 app-v 4.5 Sequencer 所產生的 Windows Installer 檔案會顯示錯誤訊息：「此套件需要 Microsoft Application Virtualization 用戶端4.5 或更新版本」。 使用 App-v 4.5 SP1 排序器或 App-v 4.6 排序器開啟舊版套件，並為套件產生新的 .msi 檔案。

-   已建立並儲存的任何版本4.2 報告，都會在伺服器升級至版本4.5 時覆寫。 如果您必須保留這些報告，您必須儲存位於伺服器的 SoftGrid 管理主控台資料夾中的 SftMMC 檔案備份複本，然後使用該複本來取代升級期間安裝的新 SftMMC。

-   如需從舊版升級的其他資訊，請參閱[升級至 Microsoft Application Virtualization 4.5 常見問題](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 用戶端套件支援


您可以將在舊版 App-v 中建立的套件部署到 App-v 4.6 用戶端。 不過，您必須修改相關的 .osd 檔案，讓它包含適當的作業系統和晶片架構資訊。 下列值可以使用：

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">OS 值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2003TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win2003TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2008TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win2008TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win2008R2TS64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "Win7"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "Win764"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "WinVista"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "WinVista64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 值 = "WinXP"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 值 = "WinXP64"/&gt;</p></td>
</tr>
</tbody>
</table>



若要執行新建立的32位套件，您必須在執行32位作業系統的電腦上，使用安裝 app-v 4.6 Sequencer 的電腦來排序應用程式。 當您將應用程式排序之後，請在 Sequencer 主控台中，按一下 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。

**重要**  
在執行64位作業系統的電腦上，必須將已排序的應用程式部署到執行64位作業系統的電腦上。 使用 App-v 4.6 Sequencer 建立的新32位套件不會在執行 App-v 4.5 用戶端的電腦上執行。



若要在 App-V 4.6 用戶端上執行新的64位套件，您必須在執行 App-v 4.6 排序器的電腦上，將應用程式排序，且執行的是64位作業系統。 當您將應用程式排序之後，請在 Sequencer 主控台中，按一下 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。

下表列出哪些用戶端版本會使用各種不同版本的排序器來執行建立的套件。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">使用 App-v 4.2 Sequencer 排序</th>
<th align="left">使用 App-v 4.5 Sequencer 排序</th>
<th align="left">使用32位 App-v-V 4.6 排序器進行排序</th>
<th align="left">使用64位 App-v-V 4.6 排序器進行排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 用戶端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.5 用戶端¹</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 用戶端（32位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可以</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 用戶端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>



¹適用于 App-V 4.5 用戶端的所有版本，包括 App-v 4.5、App-v 4.5 CU1，以及 App-v 4.5 SP1。









