---
title: 監視 Web 服務要求效能計數器
description: 監視 Web 服務要求效能計數器
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810220"
---
# 監視 Web 服務要求效能計數器


Microsoft BitLocker 管理與監控（MBAM）提供的效能計數器會記錄傳送至下列 web 服務的要求效能：

-   **StatusReportingService** –接收合規性狀態要求的服務

-   **CoreService** -接收到金鑰復原嘗試要求的服務

## MBAM 提供的效能計數器


MBAM 會針對每個由其 StatusReportingService 和 CoreService web 服務所實現的公用方法，提供下列效能計數器：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">效能計數器類型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要求總次數</p></td>
<td align="left"><p>提供伺服器啟動或重新開機時從零開始的遞增計數。</p>
<p>提供系統活動的整體視圖。 可透過自動化工具加以監視，以確保伺服器的健康情況，並確認計數器在指定的一段時間內持續增加。</p></td>
</tr>
<tr class="even">
<td align="left"><p>每秒的要求數</p></td>
<td align="left"><p>指示 MBAM 伺服器的目前輸送量，因為它支援 MBAM 用戶端基礎。</p>
<p>可讓網站系統管理員：</p>
<ul>
<li><p>根據 MBAM 用戶端數及其報告頻率，計算每秒的平均請求數。</p></li>
<li><p>驗證每秒的要求數已廣泛與計算每秒的平均請求數。 明顯的變化可能表示 MBAM 用戶端未安裝在用戶端基礎的某個部分，或是 MBAM 群組原則物件尚未順利部署。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>要求持續時間</p></td>
<td align="left"><p>記錄要求的持續時間（以毫秒為單位）。</p>
<p>雖然這個計數器會在每個要求的持續時間內更新，但是 Windows 效能監視器會定期（通常是每秒一個）進行範例，因此您可能會在值中看到一些可變性。 基於這個原因，請考慮使用 [效能監視器] 所顯示的 [平均值] 值。</p></td>
</tr>
</tbody>
</table>

 

## 效能計數器結果與建議


當您將新的 MBAM 用戶端新增到具有備用容量的 MBAM 伺服器時，預期每秒的要求數量都會增加。 這個增加會與新用戶端電腦的數目成比例。 平均要求期間將保持相對靜態。 隨著伺服器接近其最大容量，每秒的要求都會開始到階層，而平均要求期間則會開始較長的時間。

如果您擔心 MBAM 伺服器是否可支援您的用戶端基礎，請考慮在不同的用戶端電腦集合的階段中部署 MBAM。 當您將 MBAM 部署到每個用戶端電腦集合時，建議您拍攝效能計數器的快照，以查看部署到每個新用戶端集合的相對效果。 如果每秒的要求數開始為 [停止調配]，而平均要求持續時間增加，請執行下列其中一項操作來加強您的 MBAM 伺服器基礎結構：

-   將 MBAM 資料庫移至專用的 Microsoft SQL Server 或 SQL Server 群集

-   跨多個網際網路資訊服務（IIS） web 伺服器的負載平衡 MBAM

-   在功能更強大的伺服器硬體上部署 MBAM

## 查看效能計數器


建議用來查看 MBAM 效能計數器的工具是 windows 效能監視器，它隨附于 Windows。 如果您使用的是 Windows PowerShell，您就不需要在查看計數器之前啟用它們，因為它們是由 Windows PowerShell **enable-webapplication** Cmdlet 自動註冊。

如需如何查看效能計數器的詳細指示，請參閱[如何查看 MBAM 效能計數器](https://go.microsoft.com/fwlink/?LinkId=393457)。



## 相關主題


[維護 MBAM 2.5](maintaining-mbam-25.md)

 

 


## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。


