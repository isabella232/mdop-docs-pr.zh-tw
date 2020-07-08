---
title: 如何設定應用程式封裝擷取的用戶端
description: 如何設定應用程式封裝擷取的用戶端
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801573"
---
# 如何設定應用程式封裝擷取的用戶端


當用戶端是使用應用程式虛擬化（App-v）管理伺服器（其發佈伺服器）進行設定時，預設會在下次發佈重新整理週期中，用戶端從伺服器針對使用者有權使用的每個套件從已開啟的軟體描述項（OSD）和套件資訊清單檔案中進行檢索。 用戶端會使用在這些檔案中定義的套件來源資訊來決定哪裡可以找到套件內容、圖示及檔案類型關聯。

如果您想要用戶端從本機 App-v 流式處理伺服器或其他替代來源（例如 Web 服務器或檔案伺服器）取得套件內容（SFT 檔案），而不是從 App-v 管理伺服器，您可以將電腦上的 ApplicationSourceRoot 登錄項值設定為指向其他伺服器上的本機內容共用。 OSD 檔案仍會定義封裝內容的原始來源路徑。 但用戶端會使用 ApplicationSourceRoot 設定的值來代替在 OSD 檔案的內容路徑中指定的伺服器和共用。 這會重新導向用戶端，以從另一個伺服器中取得內容。

如果您想要在封裝資訊清單檔案或發佈伺服器傳送的路徑中覆寫這些設定，您也可以設定 OSDSourceRoot 和 IconSourceRoot 登錄機碼的值。 OSDSourceRoot 會在發佈期間指定應用程式套件的 OSD 檔案檢索源位置。 IconSourceRoot 指定發佈期間應用程式套件的圖示檢索來源位置。

**注意**  
-   IconSourceRoot 和 OSDSourceRoot 設定會覆寫封裝資訊清單檔案中的值，因此如果您嘗試使用 Windows 安裝程式（.msi）檔方法來部署套件，則它也會覆寫該 .msi 檔案中包含的套件資訊清單檔案中的值。

-   在發佈與 HTTP （S）資料流程作業期間，App-v 4.5 SP1 用戶端會使用在使用者電腦上的 Internet Explorer 中設定的 proxy 伺服器設定。



**設定 ApplicationSourceRoot 登錄機碼值**

-   使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 ApplicationSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot

    通用命名慣例（UNC）路徑的正確格式為**\\\\computername\\sharefolder\\\ [folder \] \ [\\]**，其中**資料夾**是選擇性的。 **Computername**可以是完整的功能變數名稱（FQDN）或 IP 位址，而**sharefolder**可以是磁片磁碟機盤符。 只會取代 OSD 路徑的**\\\\computername\\sharedfolder**或磁片磁碟機盤符部分。

    URL 路徑的正確格式為**protocol：/path\： \ [port \] \ [] \ [/\]**，其中**port**和**path**是選擇性的。 如果未指定**port** ，則會使用通訊協定的預設埠。 只會取代 OSD URL 中的**通訊協定：//server：埠**部分。

    **重要**  
    ApplicationSourceRoot 定義中不支援環境變數。



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**若要設定 OSDSourceRoot 值**

-   使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 OSDSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\OSDSourceRoot

    OSDSourceRoot 的可接受格式包括 UNC 路徑和 Url，如下列範例所示：

    **\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或** &lt; drive &gt; ： \\foldername**

    **http://computername/productivity/** 或**https://computername/productivity/**

**若要設定 IconSourceRoot 值**

-   使用 UNC 路徑或 URL 來設定下列登錄機碼值中的 IconSourceRoot：

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot

    IconSourceRoot 的可接受格式包括 UNC 路徑和 Url，如下列範例所示：

    **\\\\computername\\sharefolder\\resource**或**\\\\computername\\content**或** &lt; drive &gt; ： \\foldername**

    **http://computername/productivity/** 或**https://computername/productivity/**

## 相關主題


[如何使用命令列設定 App-V 用戶端登錄設定](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









