---
title: 規劃從舊版進行移轉
description: 規劃從舊版進行移轉
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800917"
---
# 規劃從舊版進行移轉


在嘗試升級至 Microsoft Application Virtualization 4.5 或更新版本之前，必須先將4.1 之前的任何版本升級至4.1 版本。 您應該先規劃升級用戶端，然後再升級伺服器元件。 已升級到4.5 的用戶端將會繼續與尚未升級的 Application Virtualization 伺服器搭配使用。 已升級為4.5 的伺服器不支援舊版用戶端。 如需升級系統元件的詳細資訊，請參閱[應用程式虛擬化部署和升級考慮](application-virtualization-deployment-and-upgrade-considerations.md)。

若要協助確保順利進行遷移，請依照下列順序升級應用程式虛擬化系統元件：

1.  **Microsoft Application Virtualization 用戶端。** 如需逐步升級指示，請參閱[如何升級應用程式虛擬化用戶端](how-to-upgrade-the-application-virtualization-client.md)。

2.  **Microsoft Application Virtualization 伺服器和資料庫。** 如需逐步升級指示，請參閱[如何升級伺服器與系統元件](how-to-upgrade-the-servers-and-system-components.md)。

    **記事** 如果您有多個伺服器共用應用程式虛擬化資料庫的存取權，所有這些伺服器都必須在資料庫升級時離線。 您應該遵循資料庫升級的一般業務做法，但強烈建議您在測試伺服器上先使用資料庫的備份複本來測試資料庫升級。 接著，您應該選取其中一個伺服器進行第一次升級，這會升級資料庫架構。 成功升級生產資料庫之後，您就可以升級其他伺服器。

     

3.  **Microsoft Application Virtualization 管理 Web 服務。** 此步驟僅適用于管理 Web 服務位於個別伺服器上，這會要求您在該個別伺服器上執行伺服器安裝程式，以升級 Web 服務。 否則，先前的伺服器升級步驟會自動升級管理 Web 服務。

4.  **Microsoft Application Virtualization 管理主控台。** 此步驟僅適用于管理主控台位於不同的電腦上，這會要求您在該個別電腦上執行伺服器安裝程式，以升級主機。 否則，先前的伺服器升級步驟將會升級管理主控台。

5.  **Microsoft Application Virtualization 排序器。** 如需逐步指示，請參閱[如何安裝應用程式虛擬化排序](how-to-install-the-application-virtualization-sequencer.md)器。 在版本4.2 中排序的任何虛擬應用程式套件，都不需要重新排序，就能與版本4.5 搭配使用。 不過，如果您想要套用預設的存取控制清單（Acl）或產生 Windows 安裝程式檔案，您應該考慮將虛擬套件升級為 Microsoft Application Virtualization 4.5 格式。 這是一個簡單的程式，只需要使用4.5 排序器開啟並儲存現有的虛擬應用程式套件。 您可以使用應用程式虛擬化排序器命令列介面自動化這種做法。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 用戶端套件支援


您可以將在早期版本的 App-v 中建立的套件部署到 App-v 4.6 用戶端。 不過，您必須修改相關的 **.osd**檔案，讓它包含適當的作業系統和晶片架構資訊。 使用下列值。

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

 

若要執行新建立的32位套件，您必須在執行32位作業系統的電腦上，依已安裝 App-v 4.6 Sequencer 的方式來排序應用程式。 當您將應用程式排序之後，請在 Sequencer 主控台中，選取 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。

**重要** 在執行64位作業系統的電腦上，必須將已排序的應用程式部署到執行64位作業系統的電腦上。 使用 App-v 4.6 Sequencer 來建立的新32位套件將無法在執行 App-v 4.5 用戶端的電腦上執行。

 

若要在 App-V 4.6 用戶端上執行新的64位套件，您必須在執行 App-v 4.6 Sequencer 的電腦上，並在執行64位作業系統的電腦上對應用程式進行排序。 當您將應用程式排序之後，請在 Sequencer 主控台中，選取 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。

下表列出哪些用戶端版本會使用各種不同版本的排序器來執行建立的套件。

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">使用 App-v 4.2 Sequencer 排序</th>
<th align="left">使用 App-v 4.5 Sequencer 排序</th>
<th align="left">使用32位 App-v-V 4.6 排序器進行排序</th>
<th align="left">使用64位 App-v-V 4.6 排序器進行排序</th>
<th align="left">使用32位 4.6 App-v Sequencer 排序器進行排序</th>
<th align="left">使用64位 4.6 App-v Sequencer 排序器進行排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 用戶端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
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
<td align="left"><p>否</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 用戶端（32位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可以</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可以</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 用戶端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 SP1 用戶端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可以</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>不可以</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 SP1 用戶端（64位）</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>

 

¹適用于 App-V 4.5 用戶端的所有版本，包括 App-v 4.5、App-v 4.5 CU1 和 App-v 4.5 SP1。

## 其他遷移考慮


App-v 4.5 排序器的其中一個功能是，可以建立 Windows 安裝程式檔案（.msi）作為虛擬應用程式套件與電子軟體發佈（ESD）系統（例如 Microsoft 端點設定管理員）的控制點。 以 .msi 工具所建立的舊版 Windows 安裝程式檔案，這些檔案是在隨後升級到4.5 的 App-v 或4.2 用戶端上安裝，不過這些檔案無法在4.5 用戶端上安裝。 不過，除非在4.5 排序器中升級，否則無法移除或升級它們。 原始的4.5 虛擬應用程式套件必須在4.5 排序器中開啟，然後另存為 Windows 安裝程式檔案。

**記事** 如果 App-v 4.2 用戶端已升級到4.5，就可以使用腳本做為因應措施，在4.5 用戶端上保留4.2 套件，並允許管理它們。 此腳本必須將兩個檔案（msvcp71.dll 和 msvcr71.dll）複製到 App V 安裝資料夾，並在登錄機碼 \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\] 下設定下列登錄機碼值：

"ClientVersion" = "4.2.1.20"

"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" （全域可寫位置）

 

當您嘗試在 App-v 4.6 用戶端上執行應用程式時，由 App-v 4.5 Sequencer 產生的 Windows Installer 檔案會顯示錯誤訊息「此套件需要 Microsoft Application Virtualization 用戶端4.5 或更新版本」。 使用 App-v 4.5 SP1 排序器或 App-v 4.6 排序器開啟舊的套件，並為套件產生新的 .msi。

已建立並儲存的任何4.2 報告將在伺服器升級為4.5 時覆蓋。 如果您需要保留這些報告，您必須儲存位於伺服器的 SoftGrid 管理主控台資料夾中的 SftMMC 檔案備份複本，然後使用該複本來取代升級期間安裝的新 SftMMC。

如需從舊版升級的其他資訊，請參閱[升級至 Microsoft Application Virtualization 4.5 常見問題](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。

## 相關主題


[規劃 Application Virtualization 系統部署](planning-for-application-virtualization-system-deployment.md)

 

 





