---
title: MED-V 2.0 支援的組態
description: MED-V 2.0 支援的組態
author: dansimp
ms.assetid: 88f1d232-aa01-45ab-8da7-d086269250b5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0fed090ec04cf67a32b13533f4003c01ae167493
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811024"
---
# MED-V 2.0 支援的組態


您的環境可能已符合此處提供的設定需求，因此您可以安裝並執行 Microsoft 企業版桌面虛擬化（MED-V）2.0。 我們已納入需求，包括主機作業系統、磁碟空間和 MED-V 工作區需求。

## MED-V 2.0 主機電腦需求


### MED-V 2.0 主機作業系統需求

下表列出了主機電腦上的 MED-V 2.0 安裝支援的作業系統。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p>None 或 SP1</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
</tbody>
</table>

 

下表列出 MED-V 2.0 中支援的每個作業系統所需的最低 RAM。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">最低所需 RAM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7 x86</p></td>
<td align="left"><p>超過</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows7 x64</p></td>
<td align="left"><p>超過</p></td>
</tr>
</tbody>
</table>

 

### 建議的磁碟空間最小值

我們建議您至少10GB 可用儲存空間。 不過，所需的磁碟空間會有很大的差異，視在 MED-V 工作區中發佈的應用程式數目而定。

### <a href="" id="med-v-2-0-host-configuration-"></a>MED-V 2.0 主機設定

**.NET Framework 版本**

MED-V 2.0 需要 .NET Framework 3.5 SP1 版的 Microsoft .NET Framework。 不過，如果已安裝 .NET Framework 3.5，就可以安裝 .NET Framework 4 或更新版本。

**虛擬化引擎**

Windows 虛擬 PCwith Microsoft 知識庫文章977206中所述的修復程式支援 MED-V 2.0。

**網際網路瀏覽器**

MED-V 2.0 支援 windows Internet Explorer8 和 Windows Internet Explorer 9。

**Microsoft Server 環境**

在任何伺服器環境中，都不支援 MED-V 主機代理程式和 MED-V 工作區包裝程式。

## MED-V 2.0 工作區需求


### MED-V 2.0 工作區作業系統需求

下表列出 MED-V 2.0 工作區支援的作業系統。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="med-v-2-0-workspace-configuration-"></a>MED-V 2.0 工作區配置

**.NET Framework 版本**

MED-V 2.0 工作區安裝只支援 .NET Framework 3.5 SP1 版的 Microsoft .NET Framework。

**網際網路瀏覽器**

MED-V 2.0 工作區安裝支援 windows Internet Explorer6、Windows Internet Explorer7、Windows Internet Explorer8 及 Windows Internet Explorer9。

### MED-V 2.0 工作區建立

用來建立 MED-V 2.0 工作區套件的虛擬硬碟必須使用 Windows 虛擬電腦建立。

## MED-V 2.0 全球化資訊


### MED-V 2.0 主機代理程式全球化資訊

MED-V 2.0 主機代理支援下列 Windows 作業系統語言版本：

-   法文

-   義大利文

-   德文

-   西班牙文

-   韓文

-   日文

-   巴西葡萄牙文

-   俄文

-   繁體中文

-   簡體中文

-   荷蘭文

-   瑞典文

-   丹麥文

-   芬蘭文

-   葡萄牙文

-   挪威文

-   波蘭文

-   土耳其文

-   匈牙利文

-   捷克文

-   希臘文

-   斯洛伐克文

-   斯洛維尼亞文

### MED-V 2.0 工作區包裝程式全球化資訊

MED-V 2.0 工作區包裝程式支援下列 Windows 作業系統語言版本：

-   法文

-   義大利文

-   德文

-   西班牙文

-   韓文

-   日文

-   巴西葡萄牙文

-   俄文

-   繁體中文

-   簡體中文

## 相關主題


[MED-V 部署](deployment-of-med-v.md)

 

 





