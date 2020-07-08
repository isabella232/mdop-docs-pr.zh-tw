---
title: App-V 5.0 的高階架構
description: App-V 5.0 的高階架構
author: dansimp
ms.assetid: fdf8b841-918f-4672-b352-0f2b9519581b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0ec105ffcc3213e488615603484b2de6bafce4d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800623"
---
# App-V 5.0 的高階架構


使用下列資訊來協助您簡化 Microsoft Application Virtualization （App-v）5.0 部署。

## 架構概述


典型的 App-v 5.0 實現是由下列元素所組成。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元素</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 5.0 管理伺服器</p></td>
<td align="left"><p>App-v 5.0 管理伺服器提供 App-V 5.0 基礎結構的整體管理功能。 此外，您也可以在您的環境中安裝一個以上的管理伺服器實例，提供下列好處：</p>
<ul>
<li><p>容錯與高可用性–在兩部不同的電腦上安裝和設定 App-v 5.0 管理伺服器，可在其中一個伺服器無法使用或離線時協助進行。</p>
<p>您也可以在多部電腦上安裝管理伺服器，以協助增加 App-V 5.0 的可用性。 在這種情況下，您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</p></li>
<li><p>可伸縮性：您可以根據需要新增額外的管理伺服器以支援高負荷，例如，您可以在負載平衡器後面安裝多個伺服器。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.0 發佈伺服器</p></td>
<td align="left"><p>App-v 5.0 發佈伺服器提供虛擬應用程式裝載與流式處理的功能。 發佈伺服器不需要資料庫連線，且支援下列通訊協定：</p>
<ul>
<li><p>HTTP 和 HTTPS</p></li>
</ul>
<p>您也可以在多部電腦上安裝發佈伺服器，以協助增加 App-v 5.0 的可用性。 您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 5.0 報表伺服器</p></td>
<td align="left"><p>App-V 5.0 報表服務器可讓獲授權的使用者執行並查看現有的 App-v 5.0 報告，以及可協助其管理 App-v 5.0 基礎結構的特定報告。 報表伺服器需要連線到 App-v 5.0 報告資料庫。 您也可以在多部電腦上安裝報表伺服器，以協助增加 App V 5.0 的可用性。 您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.0 用戶端</p></td>
<td align="left"><p>App-V 5.0 用戶端可讓使用 App-v 5.0 建立的套件在目的電腦上執行。</p></td>
</tr>
</tbody>
</table>

 

**記事** 如果您使用的是 App-v 5.0 搭配電子軟體發佈（ESD），則您不需要使用 app-v 5.0 管理伺服器，但是您仍然可以利用 App-v 5.0 的報告與資料流程功能。

 






## 相關主題


[App-V 5.0 入門](getting-started-with-app-v-50--rtm.md)

 

 





