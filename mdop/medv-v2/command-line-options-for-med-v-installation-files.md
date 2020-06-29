---
title: MED-V 安裝檔案的命令列選項
description: MED-V 安裝檔案的命令列選項
author: dansimp
ms.assetid: 7b8cd3e4-1d09-44a0-b690-f85b0d0a6b02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39582a592a59a4d0e81ef406edc6a984497275c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811774"
---
# MED-V 安裝檔案的命令列選項


當您安裝或卸載 Microsoft 企業桌面虛擬化（MED-V）2.0 時，您可以選擇在命令提示字元執行安裝檔。 本節說明您可以在命令提示字元上安裝或卸載 MED-V 時指定的不同選項。

### 命令列引數

您可以將下列命令列引數與它們各自的 MED-V 安裝檔案搭配使用。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安裝檔</th>
<th align="left">引數</th>
<th align="left">已接受的值</th>
<th align="left">類型</th>
<th align="left">描述</th>
<th align="left">預設值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>主機代理程式</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;安裝路徑&gt;</p></td>
<td align="left"><p>安裝</p></td>
<td align="left"><p>變更已安裝的目錄</p></td>
<td align="left"><p>安裝程式會移至 Program Files\Microsoft 企業版桌面虛擬化。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V-V 工作區包裝程式</p></td>
<td align="left"><p>MEDVDIR</p></td>
<td align="left"><p>&lt;安裝路徑&gt;</p></td>
<td align="left"><p>安裝</p></td>
<td align="left"><p>變更已安裝的目錄</p></td>
<td align="left"><p>安裝程式會移至 Program Files\Microsoft 企業版桌面虛擬化。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V 工作區</p></td>
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;安裝路徑&gt;</p></td>
<td align="left"><p>安裝</p></td>
<td align="left"><p>變更已安裝的目錄</p></td>
<td align="left"><p>安裝移至 ProgramData\Microsoft\Medv\Workspace。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V 工作區</p></td>
<td align="left"><p>覆寫 VHD</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>安裝</p></td>
<td align="left"><p>如果 VHD 存在（0）或覆寫現有的 VHD （1），則無法安裝。</p></td>
<td align="left"><p>如果虛擬硬碟（VHD）已經存在，則不會發生覆寫，且安裝失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V 工作區</p></td>
<td align="left"><p>SUPPRESSMEDVLAUNCH</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>安裝</p></td>
<td align="left"><p>啟動（0）或 [不啟動] （1）安裝 MED-V 工作區後的 MED-V。</p></td>
<td align="left"><p>如果 MED-V 工作區是與使用者介面（UI）一起安裝，則 [完成] 頁面上的核取方塊會 <strong> </strong> 控制是否要啟動 med-v。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MED-V 工作區</p></td>
<td align="left"><p>DELETEDIFFDISKS</p></td>
<td align="left"><p>0 或 1</p></td>
<td align="left"><p>解除安裝</p></td>
<td align="left"><p>保留（0）或刪除（1）由 MED-V 建立的 Vhd-V</p></td>
<td align="left"><p>不會刪除任何 Vhd。</p></td>
</tr>
</tbody>
</table>

 

### 命令列引數的範例

下列範例會安裝由 MED-V 工作區包裝程式所建立的 MED-V 工作區。 安裝檔案會在 Temp 目錄中建立一個記錄檔案，並以安靜模式執行安裝檔案，但在完成時不會啟動 MED-V 主機代理程式。 安裝檔案會覆寫您先前安裝的相同名稱留下的任何 VHD。

``` syntax
setup.exe /l* %temp%\medv-workspace-install.log /qn SUPPRESSMEDVLAUNCH=1 OVERWRITEVHD=1
```

下列範例會卸載先前安裝的 MED-V 工作區。 安裝檔案會在 Temp 目錄中建立一個記錄檔案，並以安靜模式執行安裝檔。 安裝檔案會從檔案系統中刪除所有剩餘的虛擬硬碟檔案。

``` syntax
%ProgramData%\Microsoft\Medv\Workspace\uninstall.exe /l* %temp%\medv-workspace-uninstall.log /qn DELETEDIFFDISKS=1
```

## 相關主題


[部署 MED-V 元件](deploy-the-med-v-components.md)

[MED-V 技術參考資料](technical-reference-for-med-v.md)

 

 





