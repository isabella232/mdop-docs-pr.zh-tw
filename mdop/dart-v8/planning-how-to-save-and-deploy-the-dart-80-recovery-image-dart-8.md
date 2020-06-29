---
title: 規劃如何儲存和部署 DaRT 8.0 復原映像
description: 規劃如何儲存和部署 DaRT 8.0 復原映像
author: dansimp
ms.assetid: 939fbe17-0e30-4c85-8782-5b84d69442a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2e5cca90c644eb3edf233564c474d2601d4227fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808637"
---
# 規劃如何儲存和部署 DaRT 8.0 復原映像


您可以使用下列方法儲存及部署 Microsoft Diagnostics 和復原工具庫（DaRT）8.0 復原影像。 當您決定要使用的方法時，請考慮每個方法的優點與缺點。 您也應該考慮您的基礎結構及支援人員。 如果您有小型基礎結構，您可能會想要使用 [卸除式媒體] 來部署 DaRT 8.0，因為當您將其安裝到本機硬碟時，系統會一直提供復原影像。

如果您的組織使用 Active Directory 網域服務（AD DS），您可能會想要使用 Windows DS 將復原影像部署為網路服務。 任何已連接的電腦都能使用復原影像。 您可以從 Windows DS 部署多個影像，並將它們全部保留在同一個位置。

**記事** 您可能會想要在組織中使用多個方法。 例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。

 

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
<td align="left"><p><strong>卸除式媒體</strong></p>
<p>[復原] 影像會寫入 CD、DVD 或 USB 磁片磁碟機，以讓支援人員將恢復工具隨身攜帶到不穩定的電腦。</p></td>
<td align="left"><p>支援主要開機記錄（MBR）損毀，而且您無法存取硬碟及支援沒有網路連線的情況。</p>
<p>可讓您使用不同的工具建立多個復原影像，以提供不同的支援層級。</p>
<p>提供將復原影像燒錄至卸除式媒體的內建工具。</p></td>
<td align="left"><p>需要支援人員實際在最終使用者電腦上，才能引導至 DaRT。</p>
<p>需要進行時間和維護，以針對32位和64位電腦建立多個不同的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>從遠端（網路）分區</strong></p>
<p>復原影像是在網路啟動伺服器（例如 Windows 部署服務（Windows DS））上裝載，這可讓使用者或支援人員將它流式處理到電腦的需求。</p></td>
<td align="left"><p>可供所有可存取網路啟動伺服器的電腦使用。</p>
<p>復原影像是以中央伺服器為宿主，可啟用集中式更新。</p>
<p>中央技術支援人員可使用遠端連線來提供修復。</p>
<p>用戶端上沒有本機儲存需求。</p>
<p>能夠針對特定的支援層級，使用不同的工具來建立多個復原影像。</p></td>
<td align="left"><p>需要保護 Windows DS 基礎結構，以確保一般使用者只能啟動 DaRT 復原影像，而不能啟動完整的作業系統影像處理常式。</p>
<p></p>
<p></p>
<p>要求使用者電腦在執行時間連線至網路。</p>
<p>需要在網路上進行復原影像。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>從本機硬碟上的 [恢復] 分區</strong></p>
<p>您可以手動或使用電子軟體發佈系統（例如 System Center Configuration Manager），在本機硬碟上安裝復原影像。</p></td>
<td align="left"><p>復原影像永遠可供使用，因為它是在電腦上預先暫存。</p>
<p>中央技術支援人員可使用遠端連線提供支援。</p>
<p>復原影像會集中管理並部署。</p>
<p>已消除由 Windows BitLocker 磁碟機加密所保護之電腦上的其他修復金鑰要求。</p></td>
<td align="left"><p>需要本機儲存空間。</p>
<p>建議使用專門的未加密分區來進行復原影像放置，以降低啟動磁碟分割失敗的風險。</p>
<p>更新 DaRT 時，您必須更新企業中的所有電腦，而不是只有一個分區（在網路上）或移除裝置。</p>
<p>如果您在啟用 BitLocker 之後部署復原映像，則需要其他考慮。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)

 

 





