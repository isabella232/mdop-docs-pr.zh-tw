---
title: 關於 User Experience Virtualization 1.0 SP1
description: 關於 User Experience Virtualization 1.0 SP1
author: dansimp
ms.assetid: 0212d3fb-e882-476c-9496-9eb52301703d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a480ac5d4f4083fc15a724b7cc79390b0caef14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812027"
---
# 關於 User Experience Virtualization 1.0 SP1


Microsoft 使用者體驗虛擬化（UE-V） 1.0 Service Pack 1 會將版本從1.0.414 變更為1.0.520。 當 UE-V Agent setup.exe 或 UE-V 發生器 setup.exe 啟動時，它會偵測到升級的需求，並將升級 UE-V Agent 或發生器。

## 現在支援其他語言


UE-V 1.0 Service Pack 1 提供 UE-V Agent 和支援其他語言之 UE-V 發生器的更新。 安裝程式執行時，會安裝所有支援的語言。 UE-V 1 SP1 包含下列語言：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">UE-V Agent</th>
<th align="left">UE-V 發生器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>簡體中文（中國） zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁體中文-臺灣 zh-cn&platform</p></li>
</ul>
<ul>
<li><p>捷克文（捷克共和國） cs-CZ</p></li>
</ul>
<ul>
<li><p>丹麥文（丹麥） da-深色</p></li>
</ul>
<ul>
<li><p>荷蘭文（荷蘭） nl-nl&platform-NL-NL&PLATFORM</p></li>
</ul>
<ul>
<li><p>芬蘭文（芬蘭） fi</p></li>
</ul>
<ul>
<li><p>法文（法國） fr-fr</p></li>
</ul>
<ul>
<li><p>德國（德國） de</p></li>
</ul>
<ul>
<li><p>希臘文（希臘） el-GR</p></li>
</ul>
<ul>
<li><p>匈牙利文（匈牙利） hu</p></li>
</ul>
<ul>
<li><p>義大利文（義大利） it</p></li>
</ul>
<ul>
<li><p>日文（日本） ja-jp</p></li>
</ul>
<ul>
<li><p>韓文（韓國） ko-KR</p></li>
</ul>
<ul>
<li><p>挪威文-挪威博克瑪律文（無）</p></li>
</ul>
<ul>
<li><p>波蘭文（波蘭） pl-PL</p></li>
</ul>
<ul>
<li><p>葡萄牙文（巴西） pt-BR</p></li>
</ul>
<ul>
<li><p>葡萄牙文（葡萄牙） pt</p></li>
</ul>
<ul>
<li><p>俄文（俄羅斯） ru-RU</p></li>
</ul>
<ul>
<li><p>斯洛伐克文（斯洛伐克） sk-SK</p></li>
</ul>
<ul>
<li><p>斯洛維尼亞文（斯洛維尼亞） sl-SL</p></li>
</ul>
<ul>
<li><p>西班牙文，國際排序（西班牙） es</p></li>
</ul>
<ul>
<li><p>瑞典文（瑞典） sv-SE</p></li>
</ul>
<ul>
<li><p>土耳其文（土耳其） tr-TR</p></li>
</ul>
<p></p></td>
<td align="left"><ul>
<li><p>簡體中文（中國） zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁體中文-臺灣 zh-cn&platform</p></li>
</ul>
<ul>
<li><p>法文（法國） fr-fr</p></li>
</ul>
<ul>
<li><p>德國（德國） de</p></li>
</ul>
<ul>
<li><p>義大利文（義大利） it</p></li>
</ul>
<ul>
<li><p>日文（日本） ja-jp</p></li>
</ul>
<ul>
<li><p>韓文（韓國） ko-KR</p></li>
</ul>
<ul>
<li><p>葡萄牙文（巴西） pt-BR</p></li>
</ul>
<ul>
<li><p>俄文（俄羅斯） ru-RU</p></li>
</ul>
<ul>
<li><p>西班牙文，國際排序（西班牙） es</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**重要** 雖然 UE-V Agent 安裝程式（AgentSetup.exe）和 UE-V 發生器安裝程式（ToolSetup.exe）都已翻譯成上述語言，但 Windows Installer （.msi）檔案僅提供英文版本。

 

## Office 2007 設定位置範本


UE-V Agent 安裝軟體會安裝代理程式，並為常見的 Microsoft 應用程式登錄預設的設定位置範本組。 Microsoft Office 2007 現已成為這些應用程式的一部分。 有兩個 Office 2007 範本： MicrosoftOffice2007.xml 和 MicrosoftCommunicator2007.xml。 這些設定位置範本會在 Microsoft Office 2007 中捕獲下列應用程式的設定：

-   Microsoft Access 2007

-   Microsoft Communicator 2007

-   Microsoft Excel 2007

-   Microsoft InfoPath 2007

-   Microsoft OneNote 2007

-   Microsoft Outlook 2007

-   Microsoft PowerPoint 2007

-   Microsoft Project 2007

-   Microsoft Publisher 2007

-   Microsoft SharePoint Designer 2007

-   Microsoft Visio 2007

-   Microsoft Word 2007

### Office 2010 設定位置範本更新

此外，還建立了設定位置範本的更新。 這些變更包括：

-   新增範本至 Office 2010 範本（MicrosoftOffice2010Win32.xml 和 MicrosoftOffice2010Win64.xml），以新增 Microsoft SharePoint Designer 2010 的支援。

-   次要錯誤修正，包括自訂狀態列-Word、Excel 和 PowerPoint

## [立即] 的目錄更新排程工作


範本自動更新工作會檢查 [設定] 範本目錄，以瞭解新的、更新或移除的範本。 只有在 SettingsTemplateCatalog 已設定的情況下，才會執行此工作。 範本自動更新工作會執行 ApplySettingsCatalog.exe 檔案，該檔案位於 UE-V Agent 安裝目錄中，而 UE-V SP1 已變更為一小時內隨機更新。

## Citrix EdgeSight 支援


在使用 Citrix EdgeSight 的伺服器上執行 UE-V 時發現衝突。 UE-V 1.0 SP1 可解決此問題。

## Internet Explorer [我的最愛] 的索引


當 UE-V 將 Internet Explorer 我的最愛從一部電腦漫遊至另一部電腦時，同步處理電腦上位址列中的最愛位址索引現在已更新。 當使用者在網址列中輸入時，漫遊的 [我的最愛] 現在會在同步處理的電腦上顯示為可用的搜尋結果。

## UE-V Agent 與 UE-V 發生器的新 setup.exe 命令列參數


隨著 UE-V 1.0 SP1 的發行，UE-V Agent 和 UE-V 發生器的 setup.exe 都已更新，以允許下列額外的命令列參數：

1.  `CEIPENABLED` -允許安裝程式接受 Microsoft 客戶經驗改進計畫中包含的選項。

2.  `INSTALLFOLDER` -允許針對代理程式或發電機設定不同的安裝資料夾。

3.  `MUENABLED` -允許安裝程式接受 Microsoft Update 程式中包含的選項。

## 設定的新錯誤碼


執行 UE-V Agent （AgentSetup.exe）的 UE-V 設定時，可以在安裝記錄 [/loglog.txt] 中查看下列傳回碼 &lt; &gt; 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>安裝程式已順利完成。</p></td>
</tr>
<tr class="even">
<td align="left"><p>pplx-2</p></td>
<td align="left"><p>嘗試卸載時，使用了較舊版本的 UE-V。 若要卸載 UE-V，請使用與安裝所用的相同版本的 UE-V。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3</p></td>
<td align="left"><p>已使用較新的 UE-V 版本來卸載。 若要卸載 UE-V，請使用與安裝所用的相同版本的 UE-V。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4</p></td>
<td align="left"><p>安裝程式發生意外的錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>500</p></td>
<td align="left"><p>在試用（評估版）版本之上，不能安裝完整版 UE-V。 卸載試用版，然後再試一次。</p></td>
</tr>
<tr class="even">
<td align="left"><p>6</p></td>
<td align="left"><p>安裝期間發生意外的錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>utf-7</p></td>
<td align="left"><p>在 Windows 7 或 Windows Server2008 R2 電腦上找不到 .NET 3.5 架構。</p></td>
</tr>
<tr class="even">
<td align="left"><p>型</p></td>
<td align="left"><p>[離線檔案] 功能沒有啟用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>9</p></td>
<td align="left"><p>UE-V 安裝程式無法判斷是否已安裝 UE-V，或安裝檔案中有錯誤。</p></td>
</tr>
</tbody>
</table>

 

 

 





