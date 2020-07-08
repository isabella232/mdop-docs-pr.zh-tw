---
title: 如何使用進階設定來編輯已發行的應用程式
description: 如何使用進階設定來編輯已發行的應用程式
author: dansimp
ms.assetid: 06a79049-9ce9-490f-aad7-fd4fdf185590
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 843aebb38f54959f209e742b398e3979acac3334
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812092"
---
# 如何使用進階設定來編輯已發行的應用程式


在已新增和設定發佈的應用程式之後，就可以編輯已發佈的應用程式，並設定其他高級設定。

**使用 [高級設定] 編輯已發佈的應用程式**

1.  在 [**應用程式**] 窗格中，新增並設定已發佈的應用程式。

2.  選取要編輯的已發佈應用程式。

3.  按一下**編輯**。

4.  在 [**已發佈的應用程式**] 對話方塊中，按照下表所述的方式來設定參數。

5.  按一下 \[確定\] ****。

6.  在 [**原則**] 功能表上，選取 [**確認**]。

**編輯已發佈的應用程式屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>顯示名稱</p></td>
<td align="left"><p>使用者&#39;s Windows [開始] 功能表中的快捷方式名稱。</p>
<div class="alert">
<strong>注意</strong><br/><p>顯示名稱 <strong> 不 </strong> 區分大小寫。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>已發佈功能表的描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>開始于</p></td>
<td align="left"><p>要從哪個目錄啟動應用程式。</p>
<div class="alert">
<strong>注意</strong><br/><p>路徑不需要包含引號。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>命令列</p></td>
<td align="left"><p>在 MED-V 工作區中執行應用程式所用的命令。</p>
<p>完整路徑是必要的，而且參數可以與任何其他 Windows 命令一樣，以類似的方式傳遞到應用程式。</p>
<p>在網域設定中，共用的磁片磁碟機通常存在於所有網域電腦對應的伺服器上。 目錄應該對應在這裡，如果它是需要使用者驗證的資料夾，則 <strong> 必須選取 [使用 med-v 認證來執行此應用程式] </strong> 核取方塊。</p>
<p>在 revertible med-v 工作區中，您可以使用 MapNetworkDrive 語法、 &quot; <em> MapNetworkDrive &lt; 磁片磁碟機 &gt; &lt; 路徑 &gt; </em> &quot; （例如， &quot; <em> MapNetworkDrive t： \tux\data） </em> &quot; 來對應網路磁碟機。</p>
<p>例如，若要發佈 Windows 資源管理器，請使用下列語法： &quot; <em> c： &amp; q; 或 &quot; c：\windows </em> &quot; 。</p>
<div class="alert">
<strong>注意</strong><br/><p>若要使用名稱解析，您必須執行下列其中一項操作：</p>
</div>
<div>

</div>
<ul>
<li><p>在 base MED-V 工作區圖像中設定 DNS。</p></li>
<li><p>確認主機中定義了 DNS 解析，並將其設定為使用主機 DNS。</p></li>
<li><p>使用 IP 來定義網路磁碟機。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>如果路徑包含空格，整個路徑必須以引號括住。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>路徑不應該以反斜線（）結尾。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>在主機視窗 [開始] 功能表中新增快速鍵</p></td>
<td align="left"><p>選取此核取方塊，即可在使用者&#39;s Windows [開始] 功能表中建立應用程式的快捷方式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>啟動工作區時啟動此應用程式</p></td>
<td align="left"><p>選取此核取方塊，以在 MED-V 工作區啟動時自動執行應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用 MED-V 認證來執行這個應用程式</p></td>
<td align="left"><p>選取此核取方塊以驗證使用 MED-V 認證（而非針對應用程式設定的認證）要求使用者名稱和密碼的應用程式。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用 SSO 時，命令列應該 <strong>C:\Windows\Explorer.exe &quot; 資料夾路徑中 &quot; </strong> 。 如果不使用 SSO，命令列應該是 &quot; <strong> 資料夾路徑 </strong> &quot; 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相關主題


[如何設定已發佈的應用程式](how-to-configure-published-applicationsmedvv2.md)









