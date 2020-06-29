---
title: UE-V 2.x 的同步觸發程序事件
description: UE-V 2.x 的同步觸發程序事件
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811972"
---
# UE-V 2.x 的同步觸發程序事件


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 可讓您在所有網域加入的裝置上同步處理您的應用程式和 Windows 設定。 *同步處理觸發事件*可定義 ue-v agent 何時將這些設定與設定儲存位置進行同步處理。 UE-V 2 引入了稱為*SyncProvider*的新*同步處理方法*。 如需同步處理方法設定的詳細資訊，請參閱[ue-v 2. x 的同步處理方法](sync-methods-for-ue-v-2x-both-uevv2.md)。

## UE-V 2 同步觸發事件


下表說明適用于傳統型應用程式和 Windows 設定的觸發事件。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V 2 觸發事件</strong></p></td>
<td align="left"><p><strong>SyncMethod = SyncProvider</strong></p></td>
<td align="left"><p><strong>SyncMethod = None</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 登入</strong></p></td>
<td align="left"><ul>
<li><p>您可以從 [設定] 儲存位置將應用程式和 Windows 設定匯入到本機快取。</p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)">已套用非同步 Windows 設定 </a> 。</p></li>
<li><p>系統會在下一個 Windows 登入期間套用同步 Windows 設定。</p></li>
<li><p>應用程式會在應用程式啟動時套用設定。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>您可以直接從 [設定] 儲存位置讀取 [應用程式] 和 [Windows 設定]。</p></li>
<li><p>已套用非同步及同步 Windows 設定。</p></li>
<li><p>應用程式會在應用程式啟動時套用設定。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 登出</strong></p></td>
<td align="left"><p>將變更儲存在本機，並將非同步及同步 Windows 設定複製到 [設定儲存位置伺服器] （如果有的話）</p></td>
<td align="left"><p>將變更儲存至非同步及同步 Windows 設定儲存位置</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows Connect （RDP）/解除鎖定</strong></p></td>
<td align="left"><p>將任何非同步 Windows 設定從 [設定儲存位置] 同步處理到本機快取（如果有的話）。</p>
<p>套用快取的 Windows 設定</p></td>
<td align="left"><p>從 [設定] 儲存位置下載並套用非同步 windows 設定</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 中斷連線（RDP）/鎖</strong></p></td>
<td align="left"><p>將非同步 Windows 設定變更儲存到本機快取。</p>
<p>將本機快取中的任何非同步 Windows 設定同步處理至 [設定] 儲存位置（如果有的話）</p></td>
<td align="left"><p>將 [非同步 Windows 設定] 變更儲存至 [設定] 儲存位置</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>應用程式啟動</strong></p></td>
<td align="left"><p>在應用程式啟動時從本機快取套用應用程式設定</p></td>
<td align="left"><p>應用程式啟動時從設定儲存位置套用應用程式設定</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>應用程式關閉</strong></p></td>
<td align="left"><p>將任何應用程式設定變更儲存至本機快取，並將設定複製到 [設定儲存位置] （如果有的話）</p></td>
<td align="left"><p>將任何應用程式設定變更儲存至 [設定儲存位置]</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>已從公司設定中心執行同步處理控制器排程任務或「立即同步處理」</strong></p>
<p></p></td>
<td align="left"><p>應用程式和 Windows 設定會在設定儲存位置與本機快取之間同步處理。</p>
<div class="alert">
<strong>注意</strong><br/><p>設定變更不會在本機進行緩衝，直到應用程式關閉為止。 這個觸發程式不會將變更匯出至目前執行的應用程式。</p>
<p>在 Windows 設定中，這表示任何變更都不會在本機進行緩衝及匯出，直到下次鎖定（非同步）或登出（非同步與同步）為止。</p>
</div>
<div>

</div>
<p>在這些情況下，會套用設定：</p>
<ul>
<li><p>[非同步 Windows 設定] 是直接套用的。</p></li>
<li><p>應用程式的設定會在應用程式啟動時套用。</p></li>
<li><p>在下次 Windows 登入期間，會套用非同步與同步 Windows 設定。</p></li>
<li><p>Windows 應用程式（AppX）設定會在下一次重新整理期間套用。 <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)"> </a> 如需詳細資訊，請參閱監視應用程式設定。</p></li>
</ul></td>
<td align="left"><p>NA</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>在遠端存放區上更新的非同步設定 *</strong></p></td>
<td align="left"><p>從快取載入並套用新的非同步設定。</p></td>
<td align="left"><p>從中央伺服器載入及套用設定</p></td>
</tr>
</tbody>
</table>








## 相關主題


[UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)

[變更 UE-V 2. x 排程任務的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[選擇 UE-V 2 的配置方法。](https://technet.microsoft.com/library/dn458891.aspx#config)









