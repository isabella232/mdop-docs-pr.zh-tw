---
title: 規劃如何儲存和部署 DaRT 7.0 復原映像
description: 規劃如何儲存和部署 DaRT 7.0 復原映像
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809572"
---
# 規劃如何儲存和部署 DaRT 7.0 復原映像


當您規劃儲存及部署 Microsoft Diagnostics 和復原工具集（DaRT）7復原影像時，請使用本節中的資訊。

## 規劃如何儲存和部署 DaRT 恢復影像


您可以使用下列方法儲存及部署 DaRT 復原影像。 當您決定要使用的方法時，請考慮每個方法的優點與缺點。 此外，請考慮您想要在企業中使用 DaRT 的方式。

**記事** 您可能會想要在您的組織中使用一個以上的方法。 例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。

 

下表顯示在貴組織中使用 DaRT 的每個方法的一些優點與缺點。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">啟動到 DaRT 的方法</th>
<th align="left">優點</th>
<th align="left">缺點</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>從 CD 或 DVD</p></td>
<td align="left"><p>支援主要開機記錄（MBR）損毀且無法存取硬碟的情況。 也支援沒有網路連線的情況。</p>
<p>這對於舊版 DaRT 的使用者而言是最熟悉的，而且可以直接從 DaRT 復原映射嚮導燒錄 CD 或 DVD <strong> </strong> 。</p></td>
<td align="left"><p>需要擁有 CD 或 DVD 存取權的人在物理位置是在最終使用者電腦上啟動到 DaRT。</p></td>
</tr>
<tr class="even">
<td align="left"><p>從 USB 快閃記憶體磁片磁碟機（UFD）</p></td>
<td align="left"><p>提供從 CD 或 DVD 開機的相同優點，同時也為沒有 CD 或 DVD 磁片磁碟機的電腦提供支援。</p></td>
<td align="left"><p>需要您先格式化 UFD，才能使用它來引導至 DaRT。 此外，您也需要擁有 UFD 存取權的人在物理位置是在最終使用者電腦上引導至 DaRT。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>從遠端（網路）分區</p></td>
<td align="left"><p>可讓您在不需要 CD、DVD 或 UFD 的情況下，啟動到 DaRT。 還可讓您輕鬆升級 DaRT，因為只有一個要更新的檔案位置。</p></td>
<td align="left"><p>如果最終使用者電腦未連線至網路，則無法運作。</p>
<p>廣泛提供給使用者，並且可能需要在建立恢復影像時，進行其他安全性考慮。</p></td>
</tr>
<tr class="even">
<td align="left"><p>從還原分區</p></td>
<td align="left"><p>可讓您啟動到 DaRT，而不需要 CD、DVD 或 UFD，包括沒有網路連接的情況。</p>
<p>此外，您也可以使用自動化的發佈工具（例如 Microsoft 端點設定管理員），來實現和管理標準 Windows 影像程式。</p></td>
<td align="left"><p>更新 DaRT 時，需要您更新企業中的所有電腦，而不是只有一個分區（在網路上）或裝置（CD、DVD 或 UFD）。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 DaRT 7.0](planning-to-deploy-dart-70.md)

 

 





