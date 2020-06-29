---
title: 關於部署索引標籤
description: 關於部署索引標籤
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802426"
---
# 關於部署索引標籤


使用應用程式虛擬化 Sequencer 主控台中的 [**部署**] 索引標籤，來變更您要順序的應用程式的資訊。 此索引標籤包含下列元素。

## 伺服器 URL


使用**伺服器 URL**控制項來指定虛擬應用程式伺服器設定。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控制項</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>通訊協定</strong></p></td>
<td align="left"><p>可讓您選取將已排序之應用程式套件從虛擬應用程式伺服器串流到應用程式虛擬化桌面用戶端的通訊協定。 提供下列通訊協定：</p>
<ul>
<li><p><strong>RTSP </strong> ：預設，它會指定即時資料流通訊協定控制啟用虛擬化的應用程式的交換。</p></li>
<li><p><strong>RTSPS </strong> -指定具有傳輸層安全性的即時資料流通訊協定會控制已排序之應用程式套件的交換。</p></li>
<li><p><strong>[檔案] </strong> —指定已排序的應用程式將從檔案共用傳送。</p></li>
<li><p><strong>HTTPS </strong> ：指定安全的超文字傳輸通訊協定控制套件的交換。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>主機</strong></p></td>
<td align="left"><p>可讓您在虛擬應用程式伺服器群組的前面，選取虛擬應用程式伺服器或負載平衡器，以將軟體套件傳輸到應用程式虛擬化桌面用戶端。 您必須完成這個專案，才能建立已排序的應用程式套件，但您可以從預設的% SFT_SOFTGRIDSERVER% 環境變數變更為虛擬應用程式伺服器的實際主機名稱或 IP 位址。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您選擇不指定靜態主機名稱或 IP 位址，在每個應用程式的虛擬化桌面用戶端上，您必須設定一個名為 SFT_SOFTGRIDSERVER 的環境變數。 其值必須是此用戶端&#39;s 應用程式來源的虛擬應用程式伺服器或負載平衡器的主機名稱或 IP 位址。 您應該將這個環境變數設為系統變數，而不是使用者變數。 您必須先關閉並開啟此變數，才能在這台電腦上執行的任何應用程式虛擬化桌面用戶端會話，以讓繼續進行的會話知道其新的應用程式來源。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>連接埠</strong></p></td>
<td align="left"><p>可讓您指定虛擬應用程式伺服器或負載平衡器在哪個埠上偵聽應用程式虛擬化桌面用戶端的&#39;s 要求。 此資訊是建立套件所必需的，但您可以變更它。 預設埠是554。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>路徑</strong></p></td>
<td align="left"><p>可讓您指定儲存軟體套件並將其流入的虛擬應用程式伺服器上的相對路徑。 如果 SFT 檔案將儲存在內容子目錄中，則需要此資訊才能建立套件;否則，不需要此資訊。</p></td>
</tr>
</tbody>
</table>



## 作業系統


使用**作業系統**控制項來指定應用程式的作業系統需求。 如果應用程式虛擬化桌面用戶端無法支援任何選定的作業系統，應用程式將無法啟動。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控制項</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>可用的作業系統</strong></p></td>
<td align="left"><p>顯示可支援套件中應用程式的作業系統清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>選取的作業系統</strong></p></td>
<td align="left"><p>顯示支援套件中應用程式的選取作業系統清單。</p></td>
</tr>
</tbody>
</table>



## 輸出選項


使用**輸出選項**控制項來指定要安裝之應用程式的輸出選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">控制項</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>壓縮演算法</strong></p></td>
<td align="left"><p>用來選取壓縮 SFT 檔案以在網路上傳輸的方法。 選取下列其中一個壓縮方法：</p>
<ul>
<li><p><strong>[已壓縮] </strong> ：指定將 SFT 檔案壓縮為 <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> ZLIB </a> 格式。</p></li>
<li><p><strong>未壓縮 </strong> （預設值）; 指定不壓縮 SFT 檔案。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>強制執行安全性描述項</strong></p></td>
<td align="left"><p>選取以在將套件部署到用戶端之後，強制執行該應用程式的安全描述項。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>產生 Microsoft Windows Installer （MSI）套件</strong></p></td>
<td align="left"><p>選取以使用 Windows 安裝程式來安裝或部署已排序的應用程式套件。 如果您使用 sequencer 進行任何變更，則 Windows Installer 檔案不會包含這些變更。 Windows Installer 檔案將永遠會使用儲存在硬碟上的 sft 檔案來建立。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[如何變更部署內容](how-to-change-deployment-properties.md)

[排序器主控台](sequencer-console.md)









