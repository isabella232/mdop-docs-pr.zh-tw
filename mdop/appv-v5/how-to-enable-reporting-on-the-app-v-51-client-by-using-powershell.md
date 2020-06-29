---
title: 如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表
description: 如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表
author: dansimp
ms.assetid: c4c58be6-cc50-44f6-bf4f-8346fc5d0c0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1d8c0d5e1930020ed1ce354f806f8917a9644e02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800502"
---
# 如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表


使用下列程式來設定用於報告的 App-v 5.1。

**設定執行 App-V 5.1 用戶端以進行報告的電腦**

1. 安裝 App-V 5.1 用戶端。 如需有關安裝用戶端的詳細資訊，請參閱[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)。

2. 安裝 App-V 5.1 用戶端之後，請使用 AppvClientConfiguration PowerShell 來設定適當**的**報告配置設定：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">設定</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>ReportingEnabled</p></td>
   <td align="left"><p>可讓用戶端傳回信息給報表伺服器。 用戶端在用戶端上收集報表資料時，必須有這個設定。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingServerURL</p></td>
   <td align="left"><p>指定報表服務器上儲存用戶端資訊的位置。 例如，HTTP:// &lt; reportingservername &gt; ： &lt; reportingportnumber &gt; 。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>這是在報表伺服器安裝期間指派的埠號</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>報告開始時間</p></td>
   <td align="left"><p>此設定是為了安排用戶端自動將資料傳送到伺服器。 此設定會指出報告資料開始傳送的小時數。 它是24小時制格式，並會在0-23 之間取得數位。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingRandomDelay</p></td>
   <td align="left"><p>指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。 當排程的任務開始時，用戶端會在0與 ReportingRandomDelay 之間產生隨機延遲，並在傳送資料之前等待指定的持續時間。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ReportingInterval</p></td>
   <td align="left"><p>指定用戶端將用來重新傳送資料至報表伺服器的重試時間間隔。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingDataCacheLimit</p></td>
   <td align="left"><p>指定儲存報告資訊的 XML 快取大小上限（MB）。 此大小會套用到記憶體中的快取。 當達到限制時，記錄檔案將會滾過。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ReportingDataBlockSize</p></td>
   <td align="left"><p>指定儲存報告資訊的 XML 快取大小上限（MB）。 此大小會套用到記憶體中的快取。 當達到限制時，記錄檔案將會滾過。</p></td>
   </tr>
   </tbody>
   </table>



3. 設定適當的設定之後，執行 App-v 5.1 用戶端的電腦會自動收集資料，並將資料傳送回報表伺服器。

   此外，系統管理員可以使用**AppvClientReport** PowerShell Cmdlet，手動將資料傳回按需方式。

   您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[使用 PowerShell 管理 App-V 5.1](administering-app-v-51-by-using-powershell.md)









