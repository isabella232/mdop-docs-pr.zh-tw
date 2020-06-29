---
title: UE-V 2.x 的同步方法
description: UE-V 2.x 的同步方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810040"
---
# UE-V 2.x 的同步方法


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 代理程式可讓您使用設定儲存位置來同步處理使用者的應用程式和 Windows 設定。 *同步方法*設定會定義 ue-v agent 將這些設定傳到設定儲存位置，以及將這些設定下載到這些設定的方式。 UE-V 2. x 引進了稱為*SyncProvider*的新 SyncMethod。 如需觸發應用程式和 Windows 設定同步處理之觸發事件的詳細資訊，請參閱為[ue-v 2-D 同步處理觸發程式事件（x](sync-trigger-events-for-ue-v-2x-both-uevv2.md)）。

## SyncMethod 設定


下表說明將 SyncMethod 從 UE-V v 1.0 變更為 v-v，以及每個設定的設定：

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>SyncMethod 設定</strong></p></td>
<td align="left"><p><strong>V 1。0</strong></p></td>
<td align="left"><p><strong>V 2。0</strong></p></td>
<td align="left"><p><strong>V 2.1 和 V 2.1 SP1</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncProvider</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>預設值</p></td>
<td align="left"><p>預設值</p></td>
<td align="left"><p>特定應用程式或全域 Windows 桌面設定的設定變更會儲存在本機的快取資料夾中。 當同步處理觸發事件發生時，這些變更會與 [設定] 儲存位置進行同步處理。 推送變更會將本機變更儲存至 [設定] 儲存路徑。</p>
<p>此預設設定為電腦的黃金標準。 這個選項會嘗試在短暫的延遲之後同步處理設定和超時，以確保應用程式或作業系統啟動不會在長時間內延遲。</p>
<p>此功能也會與 [排程的任務–同步處理控制器] 應用程式相關聯。 系統管理員控制排程任務的頻率。 根據預設，電腦在登入後每30分鐘都會同步處理其設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OfflineFiles</p></td>
<td align="left"><p>預設值</p></td>
<td align="left"><p>已取代。</p></td>
<td align="left"><p>已取代。</p></td>
<td align="left"><p>在 V 2.0 中的行為與 SyncProvider 相同。</p>
<p>如果啟用離線檔案並釘選資料夾，則 UE-V 會將此資料夾解除固定，並直接與中央 SMB 目錄同步處理。</p>
<p><strong>注意： </strong> 在 V 1.0 中，如果您想要使用公司的斷開連接方式（亦即在膝上型電腦上傳送）來使用 ue-v，則指導方針是使用離線檔案來確保您的設定是漫遊。我們收到了足夠的客戶意見反應，讓您開啟 [離線檔案] 是不重要的企業封鎖。 所以在 UE-V 2 中，我們建立了一個緊密結合的同步引擎，以在本機緩存您的資料，並將設定同步處理到中央伺服器。 此功能區域不會取代離線檔案或資料夾重新導向。</p>
<p>UE-V 2 在離線資料夾中無法正常運作，因此本指南不會將設定儲存路徑設定為釘選的 [已固定的離線] 或 [CSC] 資料夾。</p></td>
</tr>
<tr class="even">
<td align="left"><p>External</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>不適用</p></td>
<td align="left"><p>支援</p></td>
<td align="left"><p>UE-V 2.1 中的新功能，此設定方法會指定，如果 UE-V 設定是寫入使用者電腦上的本機資料夾，則任何外部同步處理引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>無</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>此設定設定是針對虛擬桌面基礎結構（VDI）及流程式應用程式體驗而設計。 此設定應該用於資料中心中使用的 Windows Server 方塊，其中的連線將一直是可用的。</p>
<p>任何設定變更都會直接儲存到伺服器。 如果無法使用 [設定] 儲存路徑的網路連線，則會將設定變更放在裝置上，並在下次同步處理提供程式執行時進行同步處理。 如果找不到設定儲存路徑，且在登出時從彙集的 VDI 環境中移除使用者設定檔，這些設定變更會遺失，而且使用者必須重新套用變更，才能讓電腦再次達到設定儲存路徑。</p>
<p>App 與 OS 會無限期地等待存在該位置。 如果找不到該位置，這可能會導致 App 載入或 OS 登入時間大幅增加。</p></td>
</tr>
</tbody>
</table>

 

您可以透過下列方式設定同步處理方法：

-   當您透過命令列參數或在批次腳本中[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)時

-   透過[群組原則](https://technet.microsoft.com/library/dn458893.aspx)設定

-   使用[System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx)進行 ue-v

-   使用[Windows PowerShell 或 Windows 管理工具（WMI）](https://technet.microsoft.com/library/dn458937.aspx)安裝 ue-v Agent 之後






## 相關主題


[部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





