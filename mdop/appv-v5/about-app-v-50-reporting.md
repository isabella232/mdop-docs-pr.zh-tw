---
title: 關於 App-V 5.0 報表
description: 關於 App-V 5.0 報表
author: dansimp
ms.assetid: 27c33dda-f017-41e3-8a78-1b681543ec4f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a29585886aa20233f49c85101cff570a098c69ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800736"
---
# <span data-ttu-id="b7944-103">關於 App-V 5.0 報表</span><span class="sxs-lookup"><span data-stu-id="b7944-103">About App-V 5.0 Reporting</span></span>


<span data-ttu-id="b7944-104">Microsoft Application Virtualization （App-v）5.0 包含內建的報告功能，可協助您收集執行 App-v 5.0 用戶端之電腦的相關資訊，以及有關虛擬應用程式套件用法的資訊。</span><span class="sxs-lookup"><span data-stu-id="b7944-104">Microsoft Application Virtualization (App-V) 5.0 includes a built-in reporting feature that helps you collect information about computers running the App-V 5.0 client as well as information about virtual application package usage.</span></span> <span data-ttu-id="b7944-105">您可以使用此資訊來從集中式資料庫產生報告。</span><span class="sxs-lookup"><span data-stu-id="b7944-105">You can use this information to generate reports from a centralized database.</span></span>

## <a href="" id="---------app-v-5-0-reporting-overview"></a> <span data-ttu-id="b7944-106">App-V 5.0 報告概述</span><span class="sxs-lookup"><span data-stu-id="b7944-106">App-V 5.0 Reporting Overview</span></span>


<span data-ttu-id="b7944-107">下列清單顯示在 App-v 5.0 中報告的端對端高層次工作流程。</span><span class="sxs-lookup"><span data-stu-id="b7944-107">The following list displays the end–to-end high-level workflow for reporting in App-V 5.0.</span></span>

1.  <span data-ttu-id="b7944-108">Microsoft Application Virtualization （App-v）5.0 報表伺服器具有下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="b7944-108">The Microsoft Application Virtualization (App-V) 5.0 Reporting server has the following prerequisites:</span></span>

    -   <span data-ttu-id="b7944-109">Internet Information Services （IIS） web 伺服器角色</span><span class="sxs-lookup"><span data-stu-id="b7944-109">Internet Information Service (IIS) web server role</span></span>

    -   <span data-ttu-id="b7944-110">Windows 驗證角色（在 [ **IIS/Security**] 下）</span><span class="sxs-lookup"><span data-stu-id="b7944-110">Windows Authentication role (under **IIS / Security**)</span></span>

    -   <span data-ttu-id="b7944-111">使用 SQL Server Reporting Services （SSRS）安裝及執行的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7944-111">SQL Server installed and running with SQL Server Reporting Services (SSRS)</span></span>

    <span data-ttu-id="b7944-112">若要確認 SQL Server Reporting Services 正在執行，請 `http://localhost/Reports` 在網頁瀏覽器中以系統管理員身分查看，並將其設為可託管 app-v 5.0 報告的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7944-112">To confirm SQL Server Reporting Services is running, view `http://localhost/Reports` in a web browser as administrator on the server that will host App-V 5.0 Reporting.</span></span> <span data-ttu-id="b7944-113">[SQL Server Reporting Services] 首頁應該會顯示。</span><span class="sxs-lookup"><span data-stu-id="b7944-113">The SQL Server Reporting Services Home page should display.</span></span>

2.  <span data-ttu-id="b7944-114">安裝 App-v 5.0 報表伺服器與相關聯的資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7944-114">Install the App-V 5.0 reporting server and associated database.</span></span> <span data-ttu-id="b7944-115">如需安裝報表伺服器的詳細資訊，請參閱[如何在獨立電腦上安裝報表伺服器並將它連線至資料庫](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)。</span><span class="sxs-lookup"><span data-stu-id="b7944-115">For more information about installing the reporting server see [How to install the Reporting Server on a Standalone Computer and Connect it to the Database](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md).</span></span> <span data-ttu-id="b7944-116">設定執行 App-v 5.0 用戶端的電腦應傳送資料至報表伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="b7944-116">Configure the time when the computer running the App-V 5.0 client should send data to the reporting server.</span></span>

3.  <span data-ttu-id="b7944-117">如果您不是使用電子軟體發佈系統（例如 Configuration Manager）來查看報表，則可以在 SQL Server Reporting Services 中定義報表。</span><span class="sxs-lookup"><span data-stu-id="b7944-117">If you are not using an electronic software distribution system such as Configuration Manager to view reports then you can define reports in SQL Server Reporting Service.</span></span> <span data-ttu-id="b7944-118">從下載中心下載預定義的 appvshort 報告 <https://go.microsoft.com/fwlink/?LinkId=397255> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-118">Download predefined appvshort Reports from the Download Center at <https://go.microsoft.com/fwlink/?LinkId=397255>.</span></span>

    <span data-ttu-id="b7944-119">**記事** 如果您將 Configuration Manager 整合與 App-v 5.0 結合使用，則大部分報告都是從 Configuration Manager 產生，而不是從 App-v 5.0 產生。</span><span class="sxs-lookup"><span data-stu-id="b7944-119">**Note** If you are using the Configuration Manager integration with App-V 5.0, most reports are generated from Configuration Manager rather than from App-V 5.0.</span></span>

     

4.  <span data-ttu-id="b7944-120">匯入以系統管理員身分使用 app-v 5.0 PowerShell 模組後 `Import-Module AppvClient` ，請啟用 app-v 5.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b7944-120">After importing the App-V 5.0 PowerShell module using `Import-Module AppvClient` as administrator, enable the App-V 5.0 client.</span></span> <span data-ttu-id="b7944-121">此範例 PowerShell Cmdlet 可啟用 App-v 5.0 報告：</span><span class="sxs-lookup"><span data-stu-id="b7944-121">This sample PowerShell cmdlet enables App-V 5.0 reporting:</span></span>

    ``` syntax
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    <span data-ttu-id="b7944-122">若要立即傳送 App-v 5.0 報告資料，請 `Send-AppvClientReport` 在 app-v 5.0 用戶端上執行。</span><span class="sxs-lookup"><span data-stu-id="b7944-122">To immediately send App-V 5.0 report data, run `Send-AppvClientReport` on the App-V 5.0 client.</span></span>

    <span data-ttu-id="b7944-123">如需安裝應用程式的 App-V 5.0 用戶端的詳細資訊，請參閱[關於用戶端設定設定](about-client-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b7944-123">For more information about installing the App-V 5.0 client with reporting enabled see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span> <span data-ttu-id="b7944-124">若要使用 Windows PowerShell 管理 App-v 5.0 報告，請參閱[如何使用 PowerShell 啟用 app-v 5.0 用戶端上的報告](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="b7944-124">To administer App-V 5.0 Reporting with Windows PowerShell, see [How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md).</span></span>

5.  <span data-ttu-id="b7944-125">在報表伺服器從 App-v 5.0 用戶端收到資料之後，它會將資料傳送到報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="b7944-125">After the reporting server receives the data from the App-V 5.0 client it sends the data to the reporting database.</span></span> <span data-ttu-id="b7944-126">當資料庫收到並處理用戶端資料時，會將成功的回復傳送到報表伺服器，然後將通知傳送到 App-v 5.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b7944-126">When the database receives and processes the client data, a successful reply is sent to the reporting server and then a notification is sent to the App-V 5.0 client.</span></span>

6.  <span data-ttu-id="b7944-127">當 App-v 5.0 用戶端收到成功通知時，它會清空資料快取以節省空間。</span><span class="sxs-lookup"><span data-stu-id="b7944-127">When the App-V 5.0 client receives the success notification, it empties the data cache to conserve space.</span></span>

    <span data-ttu-id="b7944-128">**記事** 根據預設，會在伺服器確認資料收到之後清除快取。</span><span class="sxs-lookup"><span data-stu-id="b7944-128">**Note** By default the cache is cleared after the server confirms receipt of data.</span></span> <span data-ttu-id="b7944-129">您可以手動設定用戶端來儲存資料快取。</span><span class="sxs-lookup"><span data-stu-id="b7944-129">You can manually configure the client to save the data cache.</span></span>

     

~~~
If the App-V 5.0 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval. Clients continue to collect data and add it to the cache.
~~~

### <a href="" id="-------------app-v-5-0-reporting-server-frequently-asked-questions"></a> <span data-ttu-id="b7944-130">App-V 5.0 報表伺服器常見問題</span><span class="sxs-lookup"><span data-stu-id="b7944-130">App-V 5.0 reporting server frequently asked questions</span></span>

<span data-ttu-id="b7944-131">下表顯示 App-V 5.0 報告的常見問題解答</span><span class="sxs-lookup"><span data-stu-id="b7944-131">The following table displays answers to common questions about App-V 5.0 reporting</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7944-132">問題</span><span class="sxs-lookup"><span data-stu-id="b7944-132">Question</span></span></th>
<th align="left"><span data-ttu-id="b7944-133">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b7944-133">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-134">報告資訊傳送到報表資料庫的頻率為何？</span><span class="sxs-lookup"><span data-stu-id="b7944-134">What is the frequency that reporting information is sent to the reporting database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-135">該頻率取決於執行 App-v 5.0 用戶端的電腦上的報表工作設定方式。</span><span class="sxs-lookup"><span data-stu-id="b7944-135">The frequency depends on how the reporting task is configured on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="b7944-136">您必須設定傳送報告資料的頻率/間隔。</span><span class="sxs-lookup"><span data-stu-id="b7944-136">You must configure the frequency / interval for sending the reporting data.</span></span> <span data-ttu-id="b7944-137">預設不會啟用 app-v 5.0 報告。</span><span class="sxs-lookup"><span data-stu-id="b7944-137">App-V 5.0 Reporting is not enabled by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7944-138">報表伺服器資料庫中會儲存哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="b7944-138">What information is stored in the reporting server database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-139">下列清單會顯示報告資料庫中所儲存的內容：</span><span class="sxs-lookup"><span data-stu-id="b7944-139">The following list displays what is stored in the reporting database:</span></span></p>
<ul>
<li><p><span data-ttu-id="b7944-140">執行 App-V 5.0 用戶端的電腦上執行的作業系統：主機名稱、版本、service pack、類型用戶端/伺服器、處理器架構。</span><span class="sxs-lookup"><span data-stu-id="b7944-140">The operating system running on the computer running the App-V 5.0 client: host name, version, service pack, type - client/server, processor architecture.</span></span></p></li>
<li><p><span data-ttu-id="b7944-141">App-V 5.0 用戶端資訊：版本。</span><span class="sxs-lookup"><span data-stu-id="b7944-141">App-V 5.0 Client information: version.</span></span></p></li>
<li><p><span data-ttu-id="b7944-142">已發佈的套件清單： GUID、版本 GUID、名稱。</span><span class="sxs-lookup"><span data-stu-id="b7944-142">Published package list: GUID, version GUID, name.</span></span></p></li>
<li><p><span data-ttu-id="b7944-143">應用程式使用量資訊：名稱、版本、流式伺服器、使用者（domain\alias）、套件版本 GUID、啟動狀態與時間、關閉時間。</span><span class="sxs-lookup"><span data-stu-id="b7944-143">Application usage information: name, version, streaming server, user (domain\alias), package version GUID, launch status and time, shutdown time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-144">傳送到報表伺服器的資訊的平均數量為何？</span><span class="sxs-lookup"><span data-stu-id="b7944-144">What is the average volume of information that is sent to the reporting server?</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-145">視情況而定。</span><span class="sxs-lookup"><span data-stu-id="b7944-145">It depends.</span></span> <span data-ttu-id="b7944-146">下列清單顯示傳送到報表伺服器的三組資料：</span><span class="sxs-lookup"><span data-stu-id="b7944-146">The following list displays the three sets of the data sent to the reporting server:</span></span></p>
<ol>
<li><p><span data-ttu-id="b7944-147">作業系統與 App-v 5.0 用戶端資訊。</span><span class="sxs-lookup"><span data-stu-id="b7944-147">Operating system, and App-V 5.0 client information.</span></span> <span data-ttu-id="b7944-148">每次傳送這個資料時，大約150個位元組。</span><span class="sxs-lookup"><span data-stu-id="b7944-148">~150 Bytes, every time this data is sent.</span></span></p></li>
<li><p><span data-ttu-id="b7944-149">已發佈套件清單。</span><span class="sxs-lookup"><span data-stu-id="b7944-149">Published package list.</span></span> <span data-ttu-id="b7944-150">30個套件的大約 7 KB。</span><span class="sxs-lookup"><span data-stu-id="b7944-150">~7 KB for 30 packages.</span></span> <span data-ttu-id="b7944-151">這只會在套件清單以較不常完成的發佈重新整理進行更新時傳送;如果沒有變更，就不會傳送此資訊。</span><span class="sxs-lookup"><span data-stu-id="b7944-151">This is sent only when the package list is updated with a publishing refresh, which is done infrequently; if there is no change, this information is not sent.</span></span></p></li>
<li><p><span data-ttu-id="b7944-152">虛擬應用程式使用量資訊–大約每個事件 0.25 KB。</span><span class="sxs-lookup"><span data-stu-id="b7944-152">Virtual application usage information – about 0.25KB per event.</span></span> <span data-ttu-id="b7944-153">如果兩者都發生在傳送資訊之前，則在開始和結束計數為一個事件。</span><span class="sxs-lookup"><span data-stu-id="b7944-153">Opening and closing count as one event if both occur before sending the information.</span></span> <span data-ttu-id="b7944-154">使用排程的任務傳送時，只會將最後一次成功上傳的資料傳送至伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7944-154">When sending using a scheduled task, only the data since the last successful upload is sent to the server.</span></span> <span data-ttu-id="b7944-155">如果您是透過 PowerShell Cmdlet 手動傳送，則會有一個選擇性引數，可控制是否要在下次需要重新傳送資料時，該引數是 <strong> DeleteOnSuccess </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-155">If sending manually through the PowerShell cmdlet, there is an optional argument that controls if the data needs to be re-sent next time around – that argument is <strong>DeleteOnSuccess</strong>.</span></span></p>
<p></p>
<p><span data-ttu-id="b7944-156">例如，如果二十個應用程式是開啟和關閉，而且報告資訊是定期傳送，則通常的每日流量應該是大約 0.15 KB + 20 x 0.25 KB，或關於 5KB/user</span><span class="sxs-lookup"><span data-stu-id="b7944-156">So for example, if twenty applications are opened and closed and reporting information is scheduled to be sent daily, the typical daily traffic should be about 0.15KB + 20 x 0.25KB, or about 5KB/user</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7944-157">您可以排程報告嗎？</span><span class="sxs-lookup"><span data-stu-id="b7944-157">Can reporting be scheduled?</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-158">是。</span><span class="sxs-lookup"><span data-stu-id="b7944-158">Yes.</span></span> <span data-ttu-id="b7944-159">除了使用 PowerShell Cmdlet 手動傳送報告（ <strong> 傳送 AppvClientReport </strong> ）之外，也可以將工作排程成自動進行。</span><span class="sxs-lookup"><span data-stu-id="b7944-159">Besides manually sending reporting using PowerShell Cmdlets (<strong>Send-AppvClientReport</strong>), the task can be scheduled so it will happen automatically.</span></span> <span data-ttu-id="b7944-160">有兩種方式可以排程報告：</span><span class="sxs-lookup"><span data-stu-id="b7944-160">There are two ways to schedule the reporting:</span></span></p>
<ol>
<li><p><span data-ttu-id="b7944-161">使用 PowerShell Cmdlet- <strong> Set-AppvClientConfiguration </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-161">Using PowerShell cmdlets - <strong>Set-AppvClientConfiguration</strong>.</span></span> <span data-ttu-id="b7944-162">例如：</span><span class="sxs-lookup"><span data-stu-id="b7944-162">For example:</span></span></p>
<p><span data-ttu-id="b7944-163">Set-AppvClientConfiguration-ReportingEnabled 1-ReportingServerURL<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span><span class="sxs-lookup"><span data-stu-id="b7944-163">Set-AppvClientConfiguration -ReportingEnabled 1 - ReportingServerURL <a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span></span></a></p>
<p></p>
<p><span data-ttu-id="b7944-164">如需用戶端設定設定的完整清單 <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)"> ，請參閱關於用戶端設定設定， </a> 並尋找下列專案： <strong> ReportingEnabled </strong> 、 <strong> ReportingServerURL </strong> 、 <strong> ReportingDataCacheLimit </strong> 、 <strong> ReportingDataBlockSize </strong> 、 <strong> ReportingStartTime、 </strong> <strong> ReportingRandomDelay </strong> 、 <strong> ReportingInterval </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-164">For a complete list of client configuration settings see <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)">About Client Configuration Settings</a> and look for the following entries: <strong>ReportingEnabled</strong>, <strong>ReportingServerURL</strong>, <strong>ReportingDataCacheLimit</strong>, <strong>ReportingDataBlockSize</strong>, <strong>ReportingStartTime</strong>, <strong>ReportingRandomDelay</strong>, <strong>ReportingInterval</strong>.</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="b7944-165">使用 [群組原則]。</span><span class="sxs-lookup"><span data-stu-id="b7944-165">By using Group Policy.</span></span> <span data-ttu-id="b7944-166">如果是使用網網域控制站進行分散式，這些設定就與前面所列的相同。</span><span class="sxs-lookup"><span data-stu-id="b7944-166">If distributed using the domain controller, the settings are the same as previously listed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b7944-167">注意</span><span class="sxs-lookup"><span data-stu-id="b7944-167">Note</span></span></strong><br/><p><span data-ttu-id="b7944-168">群組原則設定會覆寫使用 PowerShell 設定的本機設定。</span><span class="sxs-lookup"><span data-stu-id="b7944-168">Group Policy settings override local settings configured using PowerShell.</span></span></p>
</div>
<div>

</div></li>
</ol></td>
</tr>
</tbody>
</table>
 


## <a href="" id="---------app-v-5-0-client-reporting"></a> <span data-ttu-id="b7944-169">App-V 5.0 用戶端報告</span><span class="sxs-lookup"><span data-stu-id="b7944-169">App-V 5.0 Client Reporting</span></span>


<span data-ttu-id="b7944-170">若要使用 App-v 5.0 報告，您必須安裝並設定 App-v 5.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b7944-170">To use App-V 5.0 reporting you must install and configure the App-V 5.0 client.</span></span> <span data-ttu-id="b7944-171">用戶端安裝之後，請使用**AppVClientConfiguration** PowerShell Cmdlet 或**ADMX 範本**來設定報告。</span><span class="sxs-lookup"><span data-stu-id="b7944-171">After the client has been installed, use the **Set-AppVClientConfiguration** PowerShell cmdlet or the **ADMX Template** to configure reporting.</span></span> <span data-ttu-id="b7944-172">您可以透過使用下列連結，並以 [**報告**] 開頭取得報告功能 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7944-172">The reporting feature cmdlets are available by using the following link and are prefaced by **Reporting**.</span></span> <span data-ttu-id="b7944-173">如需用戶端配置設定的完整清單，請參閱[關於用戶端設定設定](about-client-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b7944-173">For a complete list of client configuration settings see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span> <span data-ttu-id="b7944-174">下列章節提供使用 PowerShell 的 App-v 5.0 用戶端報告配置範例。</span><span class="sxs-lookup"><span data-stu-id="b7944-174">The following section provides examples of App-V 5.0 client reporting configuration using PowerShell.</span></span>

### <span data-ttu-id="b7944-175">使用 PowerShell 配置 app-v 用戶端報告</span><span class="sxs-lookup"><span data-stu-id="b7944-175">Configuring App-V Client reporting using PowerShell</span></span>

<span data-ttu-id="b7944-176">下列範例會示範 PowerShell 參數如何設定 App-v 5.0 用戶端的報告功能。</span><span class="sxs-lookup"><span data-stu-id="b7944-176">The following examples show how PowerShell parameters can configure the reporting features of the App-V 5.0 client.</span></span>

**<span data-ttu-id="b7944-177">注意</span><span class="sxs-lookup"><span data-stu-id="b7944-177">Note</span></span>**  
<span data-ttu-id="b7944-178">您也可以使用 App-v 5.0 ADMX 範本中的 [群組原則] 設定來設定下列配置任務。</span><span class="sxs-lookup"><span data-stu-id="b7944-178">The following configuration task can also be configured using Group Policy settings in the App-V 5.0 ADMX template.</span></span> <span data-ttu-id="b7944-179">如需有關使用 ADMX 範本的詳細資訊，請參閱[如何使用 Admx 範本和群組原則修改 app-v 5.0 用戶端](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)設定。</span><span class="sxs-lookup"><span data-stu-id="b7944-179">For more information about using the ADMX template, see [How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md).</span></span>
 


<span data-ttu-id="b7944-180">**若要在執行 App-V 5.0 用戶端的電腦上啟用報告及啟動資料收集**：</span><span class="sxs-lookup"><span data-stu-id="b7944-180">**To enable reporting and to initiate data collection on the computer running the App-V 5.0 client**:</span></span>

`Set-AppVClientConfiguration –ReportingEnabled 1`

<span data-ttu-id="b7944-181">**若要將用戶端設定為自動傳送資料至特定的報表伺服器**，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b7944-181">**To configure the client to automatically send data to a specific reporting server**:</span></span>

``` syntax
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30
```

`-ReportingInterval 1 -ReportingRandomDelay 30`

<span data-ttu-id="b7944-182">這個範例會將用戶端設定為自動將報告資料傳送到報表伺服器 URL <strong> http://MyReportingServer:MyPort/ </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-182">This example configures the client to automatically send the reporting data to the reporting server URL <strong>http://MyReportingServer:MyPort/</strong>.</span></span> <span data-ttu-id="b7944-183">此外，系統會在8:00 和 8:30 PM 之間每天傳送報告資料，視會話產生的隨機延遲而定。</span><span class="sxs-lookup"><span data-stu-id="b7944-183">Additionally, the reporting data will be sent daily between 8:00 and 8:30 PM, depending on the random delay generated for the session.</span></span>

<span data-ttu-id="b7944-184">**若要限制用戶端上的資料**快取大小：</span><span class="sxs-lookup"><span data-stu-id="b7944-184">**To limit the size of the data cache on the client**:</span></span>

`Set-AppvClientConfiguration –ReportingDataCacheLimit 100`

<span data-ttu-id="b7944-185">在執行 App-V 5.0 用戶端到 100 MB 的電腦上，設定最大報告快取大小。</span><span class="sxs-lookup"><span data-stu-id="b7944-185">Configures the maximum size of the reporting cache on the computer running the App-V 5.0 client to 100 MB.</span></span> <span data-ttu-id="b7944-186">如果在資料傳送到伺服器之前達到快取限制，則記錄會滾過，並視需要覆寫資料。</span><span class="sxs-lookup"><span data-stu-id="b7944-186">If the cache limit is reached before the data is sent to the server, then the log rolls over and data will be overwritten as necessary.</span></span>

<span data-ttu-id="b7944-187">**若要設定在用戶端與伺服器之間跨網路傳輸的資料區塊大小**：</span><span class="sxs-lookup"><span data-stu-id="b7944-187">**To configure the data block size transmitted across the network between the client and the server**:</span></span>

`Set-AppvClientConfiguration –ReportingDataBlockSize 10240`

<span data-ttu-id="b7944-188">指定用戶端傳送至 10240 MB 的最大資料區塊。</span><span class="sxs-lookup"><span data-stu-id="b7944-188">Specifies the maximum data block that the client sends to 10240 MB.</span></span>

### <span data-ttu-id="b7944-189">收集的資料類型</span><span class="sxs-lookup"><span data-stu-id="b7944-189">Types of data collected</span></span>

<span data-ttu-id="b7944-190">下表顯示您可以使用 App-v 5.0 報告收集的資訊類型。</span><span class="sxs-lookup"><span data-stu-id="b7944-190">The following table displays the types of information you can collect by using App-V 5.0 reporting.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7944-191">用戶端資訊</span><span class="sxs-lookup"><span data-stu-id="b7944-191">Client Information</span></span></th>
<th align="left"><span data-ttu-id="b7944-192">封裝資訊</span><span class="sxs-lookup"><span data-stu-id="b7944-192">Package Information</span></span></th>
<th align="left"><span data-ttu-id="b7944-193">應用程式使用量</span><span class="sxs-lookup"><span data-stu-id="b7944-193">Application Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-194">主機名稱</span><span class="sxs-lookup"><span data-stu-id="b7944-194">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-195">套件名稱</span><span class="sxs-lookup"><span data-stu-id="b7944-195">Package Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-196">開始和結束時間</span><span class="sxs-lookup"><span data-stu-id="b7944-196">Start and End Times</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7944-197">App-V 5.0 用戶端版本</span><span class="sxs-lookup"><span data-stu-id="b7944-197">App-V 5.0 Client Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-198">套件版本</span><span class="sxs-lookup"><span data-stu-id="b7944-198">Package Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-199">運行狀態</span><span class="sxs-lookup"><span data-stu-id="b7944-199">Run Status</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-200">處理器架構</span><span class="sxs-lookup"><span data-stu-id="b7944-200">Processor Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-201">套件來源</span><span class="sxs-lookup"><span data-stu-id="b7944-201">Package Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-202">關閉狀態</span><span class="sxs-lookup"><span data-stu-id="b7944-202">Shutdown State</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7944-203">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="b7944-203">Operating System Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-204">已緩存百分比</span><span class="sxs-lookup"><span data-stu-id="b7944-204">Percent Cached</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-205">應用程式名稱</span><span class="sxs-lookup"><span data-stu-id="b7944-205">Application Name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-206">Service Pack 層級</span><span class="sxs-lookup"><span data-stu-id="b7944-206">Service Pack Level</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b7944-207">應用程式版本</span><span class="sxs-lookup"><span data-stu-id="b7944-207">Application Version</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7944-208">作業系統類型</span><span class="sxs-lookup"><span data-stu-id="b7944-208">Operating System Type</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b7944-209">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="b7944-209">Username</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b7944-210">連線群組</span><span class="sxs-lookup"><span data-stu-id="b7944-210">Connection Group</span></span></p></td>
</tr>
</tbody>
</table>
 


<span data-ttu-id="b7944-211">用戶端會以 **.xml**格式收集及儲存此資料。</span><span class="sxs-lookup"><span data-stu-id="b7944-211">The client collects and saves this data in an **.xml** format.</span></span> <span data-ttu-id="b7944-212">資料快取預設為隱藏，且需要系統管理員許可權才能開啟 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7944-212">The data cache is hidden by default and requires administrator rights to open the XML file.</span></span>

### <span data-ttu-id="b7944-213">傳送資料至伺服器</span><span class="sxs-lookup"><span data-stu-id="b7944-213">Sending data to the server</span></span>

<span data-ttu-id="b7944-214">您可以設定執行 App-v 5.0 用戶端的電腦，以將資料自動傳送至指定的報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7944-214">You can configure the computer that is running the App-V 5.0 client to automatically send data to the specified reporting server.</span></span> <span data-ttu-id="b7944-215">若要指定伺服器使用**AppvClientConfiguration** Cmdlet，請使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="b7944-215">To specify the server use the **Set-AppvClientConfiguration** cmdlet with the following settings:</span></span>

-   <span data-ttu-id="b7944-216">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="b7944-216">ReportingEnabled</span></span>

-   <span data-ttu-id="b7944-217">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="b7944-217">ReportingServerURL</span></span>

-   <span data-ttu-id="b7944-218">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="b7944-218">ReportingStartTime</span></span>

-   <span data-ttu-id="b7944-219">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="b7944-219">ReportingInterval</span></span>

-   <span data-ttu-id="b7944-220">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="b7944-220">ReportingRandomDelay</span></span>

<span data-ttu-id="b7944-221">在您設定先前的設定之後，您必須建立排程任務。</span><span class="sxs-lookup"><span data-stu-id="b7944-221">After you configure the previous settings, you must create a scheduled task.</span></span> <span data-ttu-id="b7944-222">排程的任務將會與**ReportingServerURL**設定所指定的伺服器聯繫，並會啟動傳輸。</span><span class="sxs-lookup"><span data-stu-id="b7944-222">The scheduled task will contact the server specified by the **ReportingServerURL** setting and will initiate the transfer.</span></span> <span data-ttu-id="b7944-223">如果您想要在排程的時間以外手動傳送資料，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b7944-223">If you want to manually send data outside of the scheduled times, use the following PowerShell cmdlet:</span></span>

`Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess`

<span data-ttu-id="b7944-224">如果先前已設定報表伺服器，則可以省略 **– URL**參數。</span><span class="sxs-lookup"><span data-stu-id="b7944-224">If the reporting server has been previously configured, then the **–URL** parameter can be omitted.</span></span> <span data-ttu-id="b7944-225">或者，如果資料應該傳送到備用位置，請指定不同的 URL 來覆寫這個資料集合的已設定**ReportingServerURL** 。</span><span class="sxs-lookup"><span data-stu-id="b7944-225">Alternatively, if the data should be sent to an alternate location, specify a different URL to override the configured **ReportingServerURL** for this data collection.</span></span>

<span data-ttu-id="b7944-226">**-DeleteOnSuccess**參數指出如果傳輸成功，則會清除資料快取。</span><span class="sxs-lookup"><span data-stu-id="b7944-226">The **-DeleteOnSuccess** parameter indicates that if the transfer is successful, then the data cache is cleared.</span></span> <span data-ttu-id="b7944-227">如果未指定此選項，則不會清除快取。</span><span class="sxs-lookup"><span data-stu-id="b7944-227">If this is not specified, then the cache will not be cleared.</span></span>

### <span data-ttu-id="b7944-228">手動資料收集</span><span class="sxs-lookup"><span data-stu-id="b7944-228">Manual Data Collection</span></span>

<span data-ttu-id="b7944-229">您也可以使用**Send AppVClientReport** Cmdlet 來手動收集資料。</span><span class="sxs-lookup"><span data-stu-id="b7944-229">You can also use the **Send-AppVClientReport** cmdlet to manually collect data.</span></span> <span data-ttu-id="b7944-230">這個方案對現有的報表伺服器很有説明。</span><span class="sxs-lookup"><span data-stu-id="b7944-230">This solution is helpful with or without an existing reporting server.</span></span> <span data-ttu-id="b7944-231">下列清單顯示使用或不含報表伺服器收集資料的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b7944-231">The following list displays information about collecting data with or without a reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7944-232">使用報表伺服器</span><span class="sxs-lookup"><span data-stu-id="b7944-232">With a Reporting Server</span></span></th>
<th align="left"><span data-ttu-id="b7944-233">沒有報表伺服器</span><span class="sxs-lookup"><span data-stu-id="b7944-233">Without a Reporting Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7944-234">如果您有現有的 app-v 5.0 報表伺服器，請建立自訂的排程任務或腳本。</span><span class="sxs-lookup"><span data-stu-id="b7944-234">If you have an existing App-V 5.0 reporting Server, create a customized scheduled task or script.</span></span> <span data-ttu-id="b7944-235">指定用戶端以所需的頻率將資料傳送到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="b7944-235">Specify that the client send the data to the specified location with the desired frequency.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7944-236">如果您沒有現有的 App-v 5.0 報表伺服器，請使用 <strong> – URL 參數，將 </strong> 資料傳送至指定的共用。</span><span class="sxs-lookup"><span data-stu-id="b7944-236">If you do not have an existing App-V 5.0 reporting Server, use the <strong>–URL</strong> parameter to send the data to a specified share.</span></span> <span data-ttu-id="b7944-237">例如：</span><span class="sxs-lookup"><span data-stu-id="b7944-237">For example:</span></span></p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p><span data-ttu-id="b7944-238">前面的範例會將報告資料傳送到 <strong> &lt; &gt; 由 <strong> -URL 參數指示的 \MyShare\MyData/strong 位置 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b7944-238">The previous example will send the reporting data to <strong>\MyShare\MyData&lt;/strong&gt; location indicated by the <strong>-URL</strong> parameter.</span></span> <span data-ttu-id="b7944-239">資料傳送之後，就會清除快取。</span><span class="sxs-lookup"><span data-stu-id="b7944-239">After the data has been sent, the cache is cleared.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b7944-240">注意</span><span class="sxs-lookup"><span data-stu-id="b7944-240">Note</span></span></strong><br/><p><span data-ttu-id="b7944-241">如果已指定報表伺服器以外的位置，則會使用 <strong> </strong> 不含額外處理的 .xml 格式傳送資料。</span><span class="sxs-lookup"><span data-stu-id="b7944-241">If a location other than the Reporting Server is specified, the data is sent using <strong>.xml</strong> format with no additional processing.</span></span></p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b7944-242">建立報表</span><span class="sxs-lookup"><span data-stu-id="b7944-242">Creating Reports</span></span>

<span data-ttu-id="b7944-243">若要使用 App-v 5.0 來檢索報表資訊並建立報表，您必須使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="b7944-243">To retrieve report information and create reports using App-V 5.0 you must use one of the following methods:</span></span>

-   <span data-ttu-id="b7944-244">**MICROSOFT Sql Server Reporting services （SSRS）** -microsoft Sql Server reporting services 可與 Microsoft sql server 一起使用。</span><span class="sxs-lookup"><span data-stu-id="b7944-244">**Microsoft SQL Server Reporting Services (SSRS)** - Microsoft SQL Server Reporting Services is available with Microsoft SQL Server.</span></span> <span data-ttu-id="b7944-245">安裝 App-v 5.0 報表伺服器時，不會安裝 SSRS。</span><span class="sxs-lookup"><span data-stu-id="b7944-245">SSRS is not installed when you install the App-V 5.0 reporting server.</span></span> <span data-ttu-id="b7944-246">必須單獨部署它，才能產生相關聯的報表。</span><span class="sxs-lookup"><span data-stu-id="b7944-246">It must be deployed separately to generate the associated reports.</span></span>

    <span data-ttu-id="b7944-247">如需有關使用[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)的詳細資訊，請使用下列連結。</span><span class="sxs-lookup"><span data-stu-id="b7944-247">Use the following link for more information about using [Microsoft SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596).</span></span>

-   <span data-ttu-id="b7944-248">**腳本**–您可以直接針對 app-v 5.0 報表資料庫，透過腳本撰寫來產生報告。</span><span class="sxs-lookup"><span data-stu-id="b7944-248">**Scripting** – You can generate reports by scripting directly against the App-V 5.0 reporting database.</span></span> <span data-ttu-id="b7944-249">例如：</span><span class="sxs-lookup"><span data-stu-id="b7944-249">For example:</span></span>

    **<span data-ttu-id="b7944-250">已儲存程式：</span><span class="sxs-lookup"><span data-stu-id="b7944-250">Stored Procedure:</span></span>**

    <span data-ttu-id="b7944-251">**spProcessClientReport**已排程在午夜或 12:00 AM 執行。</span><span class="sxs-lookup"><span data-stu-id="b7944-251">**spProcessClientReport** is scheduled to run at midnight or 12:00 AM.</span></span>

    <span data-ttu-id="b7944-252">若要執行 Microsoft SQL Server 排程的儲存程式，必須執行 Microsoft SQL Server 代理程式。</span><span class="sxs-lookup"><span data-stu-id="b7944-252">To run the Microsoft SQL Server Scheduled Stored procedure, the Microsoft SQL Server Agent must be running.</span></span> <span data-ttu-id="b7944-253">您應該確定 Microsoft SQL Server Agent 程式已設定為**自動啟動**。</span><span class="sxs-lookup"><span data-stu-id="b7944-253">You should ensure that the Microsoft SQL Server Agent is set to **AutoStart**.</span></span> <span data-ttu-id="b7944-254">如需詳細資訊，請參閱[AUTOSTART SQL Server 代理程式（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=287045)。</span><span class="sxs-lookup"><span data-stu-id="b7944-254">For more information see [Autostart SQL Server Agent (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045).</span></span>

    <span data-ttu-id="b7944-255">使用 App-v 5.0 資料庫腳本時，也會建立此儲存程式。</span><span class="sxs-lookup"><span data-stu-id="b7944-255">The stored procedure is also created when using the App-V 5.0 database scripts.</span></span>

<span data-ttu-id="b7944-256">您也應該確保將報表伺服器 web 服務的**最大併發連線數**設定為伺服器能夠管理且不會影響可用性的值。</span><span class="sxs-lookup"><span data-stu-id="b7944-256">You should also ensure that the reporting server web service’s **Maximum Concurrent Connections** is set to a value that the server will be able to manage without impacting availability.</span></span> <span data-ttu-id="b7944-257">**報告 Web 服務**的建議**最大併發連接**數是**10000**。</span><span class="sxs-lookup"><span data-stu-id="b7944-257">The recommended number of **Maximum Concurrent Connections** for the **Reporting Web Service** is **10,000**.</span></span>






## <span data-ttu-id="b7944-258">相關主題</span><span class="sxs-lookup"><span data-stu-id="b7944-258">Related topics</span></span>


[<span data-ttu-id="b7944-259">部署 App-V 5.0 伺服器</span><span class="sxs-lookup"><span data-stu-id="b7944-259">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

[<span data-ttu-id="b7944-260">如何在獨立電腦上安裝 Reporting Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="b7944-260">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

 

 





