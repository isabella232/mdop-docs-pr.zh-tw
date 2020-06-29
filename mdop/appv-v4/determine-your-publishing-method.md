---
title: 決定您的發佈方法
description: 決定您的發佈方法
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808900"
---
# 決定您的發佈方法


使用應用程式虛擬化排序器將應用程式排序之後，您必須將該應用程式*發佈*給您的使用者。 發佈應用程式的方式，包括將圖示、套件定義資訊和內容源位置傳送給安裝應用程式虛擬化用戶端的每個電腦。 下表說明當您使用電子軟體發佈（ESD）系統部署應用程式虛擬化時支援的發佈方法。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">優點</th>
<th align="left">缺點</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在排序期間產生 Windows 安裝程式檔案，做為獨立的方案。</p></td>
<td align="left"><ul>
<li><p>輕鬆使用。</p></li>
<li><p>套件會載入到每個電腦上本機的快取中。</p></li>
<li><p>顯示給使用者的圖示。</p></li>
<li><p>類似傳統的軟體部署。</p></li>
<li><p>不需要流式伺服器。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>在電腦上的套件內容位置，不具靈活性-所有電腦上的位置都相同。</p></li>
<li><p>必須只使用 [新增/移除程式] 或 msiexec 來移除應用程式。</p></li>
<li><p>移除和取代套件更新所需的新版本。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在排序期間產生 Windows 安裝程式檔案，搭配使用 MODE、LOAD 及 OVERRIDEURL 命令列屬性和套件資訊清單。</p></td>
<td align="left"><ul>
<li><p>簡單易用，但增加了靈活性。</p></li>
<li><p>顯示給使用者的圖示。</p></li>
<li><p>包含應用程式的 SFT 檔案可以放在流式來源位置，並將用戶端設定為使用該位置。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>靈活性有限-只有套件內容的位置可以在執行時間加以控制。</p></li>
<li><p>必須只使用 [新增/移除程式] 或 msiexec 來移除應用程式。</p></li>
<li><p>移除和取代套件更新所需的新版本，除非使用流式伺服器。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>執行 SFTMIME 命令。</p></td>
<td align="left"><ul>
<li><p>全面的靈活性：完全控制所有套件管理功能。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>命令必須經過腳本才能搭配 ESD 系統使用。</p></li>
<li><p>命令必須以正確順序在每個電腦上執行。</p></li>
<li><p>深入瞭解命令語言及需要小心規劃。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

如需使用這些發佈方法的詳細資訊，請參閱[如何在用戶端發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)。

## 相關主題


[決定您的串流方法](determine-your-streaming-method.md)

[以電子軟體發佈為基礎的案例](electronic-software-distribution-based-scenario.md)

[以電子軟體發佈為基礎的案例概觀](electronic-software-distribution-based-scenario-overview.md)

[如何在用戶端上發佈虛擬應用程式](how-to-publish-a-virtual-application-on-the-client.md)

[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





