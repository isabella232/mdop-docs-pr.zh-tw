---
title: '[應用程式虛擬化順序] 嚮導 [高級選項] 頁面'
description: '[應用程式虛擬化順序] 嚮導 [高級選項] 頁面'
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802281"
---
# [應用程式虛擬化順序] 嚮導 [高級選項] 頁面


使用 [應用程式虛擬化（App-v）順序嚮導] 的 [**高級選項**] 頁面，來指定要安裝之應用程式的高級選項。 此頁面包含下表所述的元素。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>區塊大小</strong></p></td>
<td align="left"><p>用來指定當您在網路上傳送時，要將 SFT 檔案分成多個區塊的大小。 所有區塊都等於指定大小;不過，最後一個區塊可能小於指定的大小。 選取下列其中一個值：</p>
<ul>
<li><p><strong>4 KB</strong></p></li>
<li><p><strong>16 KB</strong></p></li>
<li><p><strong>32 KB</strong></p></li>
<li><p><strong>64 KB</strong></p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>當您選取區塊大小時，請考慮 SFT 檔案和網路頻寬的大小。 區塊大小較小的檔案需要較長的時間，才能在網路上傳輸，但較少佔用頻寬。 區塊大小較大的檔案速度可能較快，但使用的網路頻寬更多。 透過實驗，您可以探索您網路上的資料流程應用程式的最佳區塊大小。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>在監視期間啟用 Microsoft 更新</strong></p></td>
<td align="left"><p>允許在順序嚮導&#39;s 監視階段中安裝 Microsoft 更新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>變基 Dll</strong></p></td>
<td align="left"><p>可將支援的動態連結程式庫重新映射到 RAM 中的連續空間，儲存記憶體並改善效能。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>向後</strong></p></td>
<td align="left"><p>存取 [排序] 嚮導&#39;s 前頁]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>下一則</strong></p></td>
<td align="left"><p>存取 [順序] 嚮導&#39;s [下一頁]。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>取消</strong></p></td>
<td align="left"><p>[結束排序嚮導] 的操作。</p></td>
</tr>
</tbody>
</table>



\ [範本標記值 \]

使用 App-v 先後順序嚮導的 [**高級選項**] 頁面，來指定您要排序之應用程式的高級選項。 此頁面包含下表所述的元素。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>允許 Microsoft Update 在監視期間執行</strong></p></td>
<td align="left"><p>指定是否要在應用程式排序期間的監視階段，將軟體更新套用到應用程式。 如果需要更新才能成功完成應用程式安裝，此選項很有説明。 預設不會選取此選項。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>變基 Dll</strong></p></td>
<td align="left"><p>可將支援的動態連結程式庫重新映射至 RAM 中的連續空間。 選取此選項可協助管理記憶體，並改善應用程式的效能。 預設不會選取此選項。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>向後</strong></p></td>
<td align="left"><p>移至上一頁的嚮導。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>下一則</strong></p></td>
<td align="left"><p>移至嚮導的下一個頁面。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>取消</strong></p></td>
<td align="left"><p>捨棄設定並退出嚮導。</p></td>
</tr>
</tbody>
</table>



\ [範本標記值 \]

## 相關主題


[排序精靈](sequencing-wizard.md)









