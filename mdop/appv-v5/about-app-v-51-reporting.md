---
title: 關於 App-V 5.1 報表
description: 關於 App-V 5.1 報表
author: dansimp
ms.assetid: 385dca00-7178-4e35-8d86-c58867ebd65c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 827343d538238ca638b57a74ae5d2d74bc6c5968
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800722"
---
# 關於 App-V 5.1 報表

Microsoft Application Virtualization （App-v）5.1 包含內建的報告功能，可協助您收集執行 App-v 5.1 用戶端之電腦的相關資訊，以及有關虛擬應用程式套件用法的資訊。 您可以使用此資訊來從集中式資料庫產生報告。

## <a href="" id="---------app-v-5-1-reporting-overview"></a> App-V 5.1 報告概述

下列清單顯示在 App-v 5.1 中報告的端對端高層次工作流程。

1. App-v 5.1 報表伺服器具有下列先決條件：

    - Internet Information Services （IIS） web 伺服器角色

    - Windows 驗證角色（在 [ **IIS/Security**] 下）

    - 使用 SQL Server Reporting Services （SSRS）安裝及執行的 SQL Server

    若要確認 SQL Server Reporting Services 正在執行，請 `http://localhost/Reports` 在網頁瀏覽器中以系統管理員身分查看，並將其設為可託管 app-v 5.1 報告的伺服器。 [SQL Server Reporting Services] 首頁應該會顯示。

2. 安裝 App-v 5.1 報表伺服器與相關聯的資料庫。 如需安裝報表伺服器的詳細資訊，請參閱[如何在獨立電腦上安裝報表伺服器並將它連線至資料庫](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)。 設定執行 App-v 5.1 用戶端的電腦應傳送資料至報表伺服器的時間。

3. 如果您不是使用電子軟體發佈系統（例如 Configuration Manager）來查看報表，則可以在 SQL Server Reporting Services 中定義報表。 從[下載中心](https://go.microsoft.com/fwlink/?LinkId=397255)下載預先定義的 SSRS 報告。

    > [!NOTE]
    > 如果您將 Configuration Manager 整合與 App-v 5.1 結合使用，則大部分報告都是從 Configuration Manager 產生，而不是從 App-v 5.1 產生。

4. 匯入以系統管理員身分使用 app-v 5.1 PowerShell 模組後 `Import-Module AppvClient` ，請啟用 app-v 5.1 用戶端。 此範例 PowerShell Cmdlet 可啟用 App-v 5.1 報告：

    ```powershell
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    若要立即傳送 App-v 5.1 報告資料，請 `Send-AppvClientReport` 在 app-v 5.1 用戶端上執行。

    如需安裝應用程式的 App-V 5.1 用戶端的詳細資訊，請參閱[關於用戶端設定設定](about-client-configuration-settings51.md)。 若要使用 Windows PowerShell 管理 App-v 5.1 報告，請參閱[如何使用 PowerShell 啟用 app-v 5.1 用戶端上的報告](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)。

5. 在報表伺服器從 App-v 5.1 用戶端收到資料之後，它會將資料傳送到報表資料庫。 當資料庫收到並處理用戶端資料時，會將成功的回復傳送到報表伺服器，然後將通知傳送到 App-v 5.1 用戶端。

6. 當 App-v 5.1 用戶端收到成功通知時，它會清空資料快取以節省空間。

    > [!NOTE]
    > 根據預設，會在伺服器確認資料收到之後清除快取。 您可以手動設定用戶端來儲存資料快取。

如果 App-v 5.1 用戶端裝置沒有從伺服器接收到成功通知，它會將資料保留在快取中，並嘗試在下一個設定的間隔重新傳送資料。 用戶端會繼續收集資料，並將它新增到快取。

### <a href="" id="-------------app-v-5-1-reporting-server-frequently-asked-questions"></a> App-V 5.1 報表伺服器常見問題

下表顯示 App-V 5.1 報告的常見問題解答

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>報告資訊傳送到報表資料庫的頻率為何？</p></td>
<td align="left"><p>該頻率取決於執行 App-v 5.1 用戶端的電腦上的報表工作設定方式。 您必須設定傳送報告資料的頻率/間隔。 預設不會啟用 app-v 5.1 報告。</p></td>
</tr>
<tr class="even">
<td align="left"><p>報表伺服器資料庫中會儲存哪些資訊？</p></td>
<td align="left"><p>下列清單會顯示報告資料庫中所儲存的內容：</p>
<ul>
<li><p>執行 App-V 5.1 用戶端的電腦上執行的作業系統：主機名稱、版本、service pack、類型用戶端/伺服器、處理器架構。</p></li>
<li><p>App-V 5.1 用戶端資訊：版本。</p></li>
<li><p>已發佈的套件清單： GUID、版本 GUID、名稱。</p></li>
<li><p>應用程式使用量資訊：名稱、版本、流式伺服器、使用者（domain\alias）、套件版本 GUID、啟動狀態與時間、關閉時間。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>傳送到報表伺服器的資訊的平均數量為何？</p></td>
<td align="left"><p>視情況而定。 下列清單顯示傳送到報表伺服器的三組資料：</p>
<ol>
<li><p>作業系統與 App-v 5.1 用戶端資訊。 每次傳送這個資料時，大約150個位元組。</p></li>
<li><p>已發佈套件清單。 30個套件的大約 7 KB。 這只會在套件清單以較不常完成的發佈重新整理進行更新時傳送;如果沒有變更，就不會傳送此資訊。</p></li>
<li><p>虛擬應用程式使用量資訊–大約每個事件 0.25 KB。 如果兩者都發生在傳送資訊之前，則在開始和結束計數為一個事件。 使用排程的任務傳送時，只會將最後一次成功上傳的資料傳送至伺服器。 如果您是透過 PowerShell Cmdlet 手動傳送，則會有一個選擇性引數，可控制是否要在下次需要重新傳送資料時，該引數是 <strong> DeleteOnSuccess </strong> 。</p>
<p></p>
<p>例如，如果二十個應用程式是開啟和關閉，而且報告資訊是定期傳送，則通常的每日流量應該是大約 0.15 KB + 20 x 0.25 KB，或關於 5KB/user</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>您可以排程報告嗎？</p></td>
<td align="left"><p>是。 除了使用 PowerShell Cmdlet 手動傳送報告（ <strong> 傳送 AppvClientReport </strong> ）之外，也可以將工作排程成自動進行。 有兩種方式可以排程報告：</p>
<ol>
<li><p>使用 PowerShell Cmdlet- <strong> Set-AppvClientConfiguration </strong> 。 例如：</p>
<p>Set-AppvClientConfiguration-ReportingEnabled 1-ReportingServerURL<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</a></p>
<p></p>
<p>如需用戶端設定設定的完整清單 <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)"> ，請參閱關於用戶端設定設定， </a> 並尋找下列專案： <strong> ReportingEnabled </strong> 、 <strong> ReportingServerURL </strong> 、 <strong> ReportingDataCacheLimit </strong> 、 <strong> ReportingDataBlockSize </strong> 、 <strong> ReportingStartTime、 </strong> <strong> ReportingRandomDelay </strong> 、 <strong> ReportingInterval </strong> 。</p>
<p></p></li>
<li><p>使用 [群組原則]。 如果是使用網網域控制站進行分散式，這些設定就與前面所列的相同。</p>
<div class="alert">
<strong>注意</strong><br/><p>群組原則設定會覆寫使用 PowerShell 設定的本機設定。</p>
</div>
<div>
</div></li>
</ol></td>
</tr>
</tbody>
</table>

## <a href="" id="---------app-v-5-1-client-reporting"></a> App-V 5.1 用戶端報告

若要使用 App-v 5.1 報告，您必須安裝並設定 App-v 5.1 用戶端。 用戶端安裝之後，請使用**AppVClientConfiguration** PowerShell Cmdlet 或**ADMX 範本**來設定報告。 您可以透過使用下列連結，並以 [**報告**] 開頭取得報告功能 Cmdlet。 如需用戶端配置設定的完整清單，請參閱[關於用戶端設定設定](about-client-configuration-settings51.md)。 下列章節提供使用 PowerShell 的 App-v 5.1 用戶端報告配置範例。

### 使用 PowerShell 配置 app-v 用戶端報告

下列範例會示範 PowerShell 參數如何設定 App-v 5.1 用戶端的報告功能。

> [!NOTE]
> 您也可以使用 App-v 5.1 ADMX 範本中的 [群組原則] 設定來設定下列配置任務。 如需有關使用 ADMX 範本的詳細資訊，請參閱[如何使用 Admx 範本和群組原則修改 app-v 5.1 用戶端](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)設定。

**若要在執行 App-V 5.1 用戶端的電腦上啟用報告及啟動資料收集**：

```powershell
Set-AppVClientConfiguration –ReportingEnabled 1
```

**若要將用戶端設定為自動傳送資料至特定的報表伺服器**，請執行下列動作：

```powershell
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30 -ReportingInterval 1 -ReportingRandomDelay 30
```

這個範例會將用戶端設定為自動將報告資料傳送到報表伺服器 URL **http://MyReportingServer:MyPort/** 。 此外，系統會在8:00 和 8:30 PM 之間每天傳送報告資料，視會話產生的隨機延遲而定。

**若要限制用戶端上的資料**快取大小：

```powershell
Set-AppvClientConfiguration –ReportingDataCacheLimit 100
```

在執行 App-V 5.1 用戶端到 100 MB 的電腦上，設定最大報告快取大小。 如果在資料傳送到伺服器之前達到快取限制，則記錄會滾過，並視需要覆寫資料。

**若要設定在用戶端與伺服器之間跨網路傳輸的資料區塊大小**：

```powershell
Set-AppvClientConfiguration –ReportingDataBlockSize 10240
```

指定用戶端傳送至 10240 MB 的最大資料區塊。

### 收集的資料類型

下表顯示您可以使用 App-v 5.1 報告收集的資訊類型。

|用戶端資訊  |封裝資訊  |應用程式使用量  |
|---------|---------|---------|
|主機名稱 |套件名稱|開始和結束時間|
|App-V 5.1 用戶端版本 |套件版本|運行狀態|
|處理器架構 |套件來源|關閉狀態|
|作業系統版本|已緩存百分比|應用程式名稱|
|Service Pack 層級| |應用程式版本|
|作業系統類型| |使用者名稱|
| | |連線群組|

用戶端會以 **.xml**格式收集及儲存此資料。 資料快取預設為隱藏，且需要系統管理員許可權才能開啟 XML 檔案。

### 傳送資料至伺服器

您可以設定執行 App-v 5.1 用戶端的電腦，以將資料自動傳送至指定的報表伺服器。 若要指定伺服器使用**AppvClientConfiguration** Cmdlet，請使用下列設定：

- ReportingEnabled
- ReportingServerURL
- ReportingStartTime
- ReportingInterval
- ReportingRandomDelay

在您設定先前的設定之後，您必須建立排程任務。 排程的任務將會與**ReportingServerURL**設定所指定的伺服器聯繫，並會啟動傳輸。 如果您想要在排程的時間以外手動傳送資料，請使用下列 PowerShell Cmdlet：

```powershell
Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess
```

如果先前已設定報表伺服器，則可以省略 **– URL**參數。 或者，如果資料應該傳送到備用位置，請指定不同的 URL 來覆寫這個資料集合的已設定**ReportingServerURL** 。

**-DeleteOnSuccess**參數指出如果傳輸成功，則會清除資料快取。 如果未指定此選項，則不會清除快取。

### 手動資料收集

您也可以使用**Send AppVClientReport** Cmdlet 來手動收集資料。 這個方案對現有的報表伺服器很有説明。 下列清單顯示使用或不含報表伺服器收集資料的相關資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用報表伺服器</th>
<th align="left">沒有報表伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>如果您有現有的 app-v 5.1 報表伺服器，請建立自訂的排程任務或腳本。 指定用戶端以所需的頻率將資料傳送到指定的位置。</p></td>
<td align="left"><p>如果您沒有現有的 App-v 5.1 報表伺服器，請使用 <strong> – URL 參數，將 </strong> 資料傳送至指定的共用。 例如：</p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p>前面的範例會將報告資料傳送到 <strong> &lt; &gt; 由 <strong> -URL 參數指示的 \MyShare\MyData/strong 位置 </strong> 。 資料傳送之後，就會清除快取。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果已指定報表伺服器以外的位置，則會使用 <strong> </strong> 不含額外處理的 .xml 格式傳送資料。</p>
</div>
<div>
</div></td>
</tr>
</tbody>
</table>

### 建立報表

若要使用 App-v 5.1 來檢索報表資訊並建立報表，您必須使用下列其中一種方法：

- **MICROSOFT Sql Server Reporting services （SSRS）** -microsoft Sql Server reporting services 可與 Microsoft sql server 一起使用。 安裝 App-v 5.1 報表伺服器時，不會安裝 SSRS。 必須單獨部署它，才能產生相關聯的報表。

    如需有關使用[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)的詳細資訊，請使用下列連結。

- **腳本**–您可以直接針對 app-v 5.1 報表資料庫，透過腳本撰寫來產生報告。 例如：

    **已儲存程式：**

    **spProcessClientReport**已排程在午夜或 12:00 AM 執行。

    若要執行 Microsoft SQL Server 排程的儲存程式，必須執行 Microsoft SQL Server 代理程式。 您應該確定 Microsoft SQL Server Agent 程式已設定為**自動啟動**。 如需詳細資訊，請參閱[AUTOSTART SQL Server 代理程式（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=287045)。

    使用 App-v 5.1 資料庫腳本時，也會建立此儲存程式。

您也應該確保將報表伺服器 web 服務的**最大併發連線數**設定為伺服器能夠管理且不會影響可用性的值。 **報告 Web 服務**的建議**最大併發連接**數是**10000**。

## 相關主題

[部署 App-V 5.1 伺服器](deploying-the-app-v-51-server.md)

[如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)
