---
title: App-V 用戶端登錄值
description: App-V 用戶端登錄值
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802365"
---
# <span data-ttu-id="bcf00-103">App-V 用戶端登錄值</span><span class="sxs-lookup"><span data-stu-id="bcf00-103">App-V Client Registry Values</span></span>


<span data-ttu-id="bcf00-104">Microsoft Application Virtualization （App-v）用戶端將其設定儲存在註冊表中。</span><span class="sxs-lookup"><span data-stu-id="bcf00-104">The Microsoft Application Virtualization (App-V) client stores its configuration in the registry.</span></span> <span data-ttu-id="bcf00-105">如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="bcf00-106">您也可以透過變更登錄專案來設定多個用戶端動作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="bcf00-107">本主題列出所有應用程式虛擬化（App-v）用戶端登錄機碼，並說明其用法。</span><span class="sxs-lookup"><span data-stu-id="bcf00-107">This topic lists all the Application Virtualization (App-V) client registry keys and explains their uses.</span></span>

**<span data-ttu-id="bcf00-108">重要</span><span class="sxs-lookup"><span data-stu-id="bcf00-108">Important</span></span>**  
<span data-ttu-id="bcf00-109">在執行64位作業系統的電腦上，下列各節中所述的金鑰和值將會位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client。</span><span class="sxs-lookup"><span data-stu-id="bcf00-109">On a computer running a 64-bit operating system, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>



## <span data-ttu-id="bcf00-110">設定鍵</span><span class="sxs-lookup"><span data-stu-id="bcf00-110">Configuration Key</span></span>


<span data-ttu-id="bcf00-111">下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration 金鑰有關之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-111">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-112">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-112">Name</span></span></th>
<th align="left"><span data-ttu-id="bcf00-113">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-113">Type</span></span></th>
<th align="left"><span data-ttu-id="bcf00-114">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-114">Data (Examples)</span></span></th>
<th align="left"><span data-ttu-id="bcf00-115">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-116">ProductName</span><span class="sxs-lookup"><span data-stu-id="bcf00-116">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-117">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-117">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-118">Microsoft Application Virtualization 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="bcf00-118">Microsoft Application Virtualization Desktop Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-119">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-119">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-120">版本</span><span class="sxs-lookup"><span data-stu-id="bcf00-120">Version</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-121">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-121">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-122">4.5.0.xxx</span><span class="sxs-lookup"><span data-stu-id="bcf00-122">4.5.0.xxx</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-123">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-123">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-124">驅動程式</span><span class="sxs-lookup"><span data-stu-id="bcf00-124">Drivers</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-125">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-125">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-126">Sftfs.sys</span><span class="sxs-lookup"><span data-stu-id="bcf00-126">Sftfs.sys</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-127">如果此項值存在，則會包含上次啟動核心時導致停止錯誤的驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="bcf00-127">If this key value is present, it contains the name of the driver that caused a stop error the last time the core was starting.</span></span> <span data-ttu-id="bcf00-128">修正停止錯誤之後，您必須刪除此金鑰值，才能開始 sftlist。</span><span class="sxs-lookup"><span data-stu-id="bcf00-128">After you have fixed the stop error, you must delete this key value so that sftlist can start.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-129">InstallPath</span><span class="sxs-lookup"><span data-stu-id="bcf00-129">InstallPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-130">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-130">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-131">預設 = C:\Program Files\Microsoft Application Virtualization 用戶端</span><span class="sxs-lookup"><span data-stu-id="bcf00-131">Default=C:\Program Files\Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-132">用戶端的安裝位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-132">The location where the client is installed.</span></span> <span data-ttu-id="bcf00-133">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-133">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-134">LogFileName</span><span class="sxs-lookup"><span data-stu-id="bcf00-134">LogFileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-135">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-135">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-136">預設 = CSIDL_COMMON_APPDATA \Microsoft\Application 虛擬化 Client\sftlog.txt</span><span class="sxs-lookup"><span data-stu-id="bcf00-136">Default=CSIDL_COMMON_APPDATA\Microsoft\Application Virtualization Client\sftlog.txt</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-137">用戶端記錄檔的路徑和名稱。</span><span class="sxs-lookup"><span data-stu-id="bcf00-137">The path and name for the client log file.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bcf00-138">注意</span><span class="sxs-lookup"><span data-stu-id="bcf00-138">Note</span></span></strong><br/><p><span data-ttu-id="bcf00-139">如果您執行的是舊版 App-v 4.6、SP1，且您修改了記錄檔案名或位置，您必須重新開機 sftlist 服務，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="bcf00-139">If you are running an earlier version than App-V 4.6, SP1 and you modify the log file name or location, you must restart the sftlist service for the change to take effect.</span></span></p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-140">LogMinSeverity</span><span class="sxs-lookup"><span data-stu-id="bcf00-140">LogMinSeverity</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-141">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-142">預設值 = 4，資訊</span><span class="sxs-lookup"><span data-stu-id="bcf00-142">Default=4, Informational</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-143">控制要寫入記錄的訊息。</span><span class="sxs-lookup"><span data-stu-id="bcf00-143">Controls which messages are written to the log.</span></span> <span data-ttu-id="bcf00-144">此值表示記錄的閾值，即記錄小於或等於該值的所有專案。</span><span class="sxs-lookup"><span data-stu-id="bcf00-144">The value indicates a threshold of what is logged—everything less than or equal to that value is logged.</span></span> <span data-ttu-id="bcf00-145">例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-145">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="bcf00-146">值範圍： 0x0 = 無，0x1 = 臨界，0x2 = 錯誤，0x3 = Warning，0x4 = 資訊（預設值），0x5 = Verbose。</span><span class="sxs-lookup"><span data-stu-id="bcf00-146">Value Range: 0x0 = None, 0x1 = Critical, 0x2 = Error, 0x3 = Warning, 0x4 = Information (Default), 0x5 = Verbose.</span></span></p>
<p><span data-ttu-id="bcf00-147">記錄層級可從應用程式虛擬化（App-v）用戶端主控台和命令提示字元進行設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-147">The log level is configurable from the Application Virtualization (App-V) client console and from the command prompt.</span></span> <span data-ttu-id="bcf00-148">在命令提示字元中，sftlist.exe/verboselog 的命令會將記錄層級增加到詳細。</span><span class="sxs-lookup"><span data-stu-id="bcf00-148">At a command prompt, the command sftlist.exe /verboselog will increase the log level to verbose.</span></span> <span data-ttu-id="bcf00-149">如需有關命令列詳細資料的詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="bcf00-149">For more information on command-line details see</span></span></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p><span data-ttu-id="bcf00-150">.</span><span class="sxs-lookup"><span data-stu-id="bcf00-150">.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-151">LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="bcf00-151">LogRolloverCount</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-152">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-152">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-153">預設 = 4</span><span class="sxs-lookup"><span data-stu-id="bcf00-153">Default=4</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-154">定義要在重設時保留的記錄檔案備份複本數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-154">Defines the number of backup copies of the log file that are kept when it is reset.</span></span> <span data-ttu-id="bcf00-155">有效範圍為0到9999。</span><span class="sxs-lookup"><span data-stu-id="bcf00-155">The valid range is 0–9999.</span></span> <span data-ttu-id="bcf00-156">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="bcf00-156">The default is 4.</span></span> <span data-ttu-id="bcf00-157">值為0表示不會保留任何複本。</span><span class="sxs-lookup"><span data-stu-id="bcf00-157">A value of 0 means no copies will be kept.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-158">LogMaxSize</span><span class="sxs-lookup"><span data-stu-id="bcf00-158">LogMaxSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-160">預設 = 256</span><span class="sxs-lookup"><span data-stu-id="bcf00-160">Default=256</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-161">在重設前，定義記錄檔可能會增長的最大大小（MB）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-161">Defines the maximum size in megabytes (MB) that the log file can grow before being reset.</span></span> <span data-ttu-id="bcf00-162">預設大小為 256 MB。</span><span class="sxs-lookup"><span data-stu-id="bcf00-162">The default size is 256 MB.</span></span> <span data-ttu-id="bcf00-163">達到此大小時，系統會在下一次寫入嘗試時強制進行記錄重設。</span><span class="sxs-lookup"><span data-stu-id="bcf00-163">When this size is reached, a log reset will be forced on the next write attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-164">SystemEventLogLevel</span><span class="sxs-lookup"><span data-stu-id="bcf00-164">SystemEventLogLevel</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-165">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-165">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-166">預設值 = 0x4 （App-v 4.5）</span><span class="sxs-lookup"><span data-stu-id="bcf00-166">Default=0x4 (App-V 4.5)</span></span></p>
<p><span data-ttu-id="bcf00-167">預設值 = 0x3 （App-v 4.6）</span><span class="sxs-lookup"><span data-stu-id="bcf00-167">Default=0x3 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-168">指出記錄層級，日誌訊息會寫入 NT 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="bcf00-168">Indicates the logging level at which log messages are written to the NT event log.</span></span> <span data-ttu-id="bcf00-169">此值表示記錄的閾值，也就是等於或小於該值的所有專案都會登入。</span><span class="sxs-lookup"><span data-stu-id="bcf00-169">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="bcf00-170">例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-170">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="bcf00-171">值範圍</span><span class="sxs-lookup"><span data-stu-id="bcf00-171">Value Range</span></span></p>
<p><span data-ttu-id="bcf00-172">0x0 = None</span><span class="sxs-lookup"><span data-stu-id="bcf00-172">0x0 = None</span></span></p>
<p><span data-ttu-id="bcf00-173">0x1 = 危急</span><span class="sxs-lookup"><span data-stu-id="bcf00-173">0x1 = Critical</span></span></p>
<p><span data-ttu-id="bcf00-174">0x2 = 錯誤</span><span class="sxs-lookup"><span data-stu-id="bcf00-174">0x2 = Error</span></span></p>
<p><span data-ttu-id="bcf00-175">0x3 = 警告</span><span class="sxs-lookup"><span data-stu-id="bcf00-175">0x3 = Warning</span></span></p>
<p><span data-ttu-id="bcf00-176">0x4 = 資訊（預設值）</span><span class="sxs-lookup"><span data-stu-id="bcf00-176">0x4 = Information (Default)</span></span></p>
<p><span data-ttu-id="bcf00-177">0x5 = 詳細</span><span class="sxs-lookup"><span data-stu-id="bcf00-177">0x5 = Verbose</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-178">AllowIndependentFileStreaming</span><span class="sxs-lookup"><span data-stu-id="bcf00-178">AllowIndependentFileStreaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-179">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-179">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-180">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-180">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-181">指示是否要啟用來自檔案的資料流程，不論用戶端是否已使用 APPLICATIONSOURCEROOT 參數進行設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-181">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the APPLICATIONSOURCEROOT parameter.</span></span> <span data-ttu-id="bcf00-182">如果設定為 FALSE，即使 OSD HREF 或 APPLICATIONSOURCEROOT 參數包含檔案路徑，傳輸也不會啟用檔案的資料流程。</span><span class="sxs-lookup"><span data-stu-id="bcf00-182">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the APPLICATIONSOURCEROOT parameter contains a file path.</span></span></p>
<p><span data-ttu-id="bcf00-183">0x0 = False （預設值）</span><span class="sxs-lookup"><span data-stu-id="bcf00-183">0x0=False (default)</span></span></p>
<p><span data-ttu-id="bcf00-184">0x1 = True</span><span class="sxs-lookup"><span data-stu-id="bcf00-184">0x1=True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-185">ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="bcf00-185">ApplicationSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-186">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-186">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-187">rtsps://mainserver:322/prodapps</span><span class="sxs-lookup"><span data-stu-id="bcf00-187">rtsps://mainserver:322/prodapps</span></span></p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p><span data-ttu-id="bcf00-188">檔案：//\uncserver\share\prodapps</span><span class="sxs-lookup"><span data-stu-id="bcf00-188">file://\uncserver\share\prodapps</span></span></p>
<p><span data-ttu-id="bcf00-189">檔案：//\uncserver\share</span><span class="sxs-lookup"><span data-stu-id="bcf00-189">file://\uncserver\share</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-190">啟用系統管理員或電子軟體發佈（ESD）系統，以確保根據拓撲管理配置來執行應用程式載入。</span><span class="sxs-lookup"><span data-stu-id="bcf00-190">Enables an administrator or electronic software distribution (ESD) system to ensure application loading is performed according to the topology management scheme.</span></span> <span data-ttu-id="bcf00-191">使用此金鑰值來覆寫應用程式的 HREF 元素（例如，來源位置）的 OSD 基本代碼。</span><span class="sxs-lookup"><span data-stu-id="bcf00-191">Use this key value to override the OSD CODEBASE for the HREF element (for example, the source location) for an application.</span></span> <span data-ttu-id="bcf00-192">應用程式來源根目錄支援 Url 和通用命名慣例（UNC）路徑格式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-192">Application Source Root supports URLs and Universal Naming Convention (UNC) path formats.</span></span></p>
<p><span data-ttu-id="bcf00-193">URL 路徑的正確格式為 protocol：：（port） [/path] [/]，其中的埠和路徑是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="bcf00-193">The correct format for the URL path is protocol://servername:[port][/path][/], where port and path are optional.</span></span> <span data-ttu-id="bcf00-194">如果沒有指定埠，則會使用通訊協定的預設埠。</span><span class="sxs-lookup"><span data-stu-id="bcf00-194">If a port is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="bcf00-195">只會取代 OSD URL 中的通訊協定：//server：埠部分。</span><span class="sxs-lookup"><span data-stu-id="bcf00-195">Only the protocol://server:port portion of the OSD URL is replaced.</span></span> </p>
<p><span data-ttu-id="bcf00-196">UNC 路徑的正確格式為 \computername\sharefolder [folder] []，其中資料夾是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="bcf00-196">The correct format for the UNC path is \computername\sharefolder[folder][], where folder is optional.</span></span> <span data-ttu-id="bcf00-197">電腦名稱稱可以是完整的功能變數名稱（FQDN）或 IP 位址，而 sharefolder 可以是磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="bcf00-197">The computer name can be a fully qualified domain name (FQDN) or an IP address, and sharefolder can be a drive letter.</span></span> <span data-ttu-id="bcf00-198">只會取代 OSD 路徑的 \computername\sharefolder 或磁片磁碟機盤符部分。</span><span class="sxs-lookup"><span data-stu-id="bcf00-198">Only the \computername\sharefolder or drive letter portion of the OSD path is replaced.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-199">OSDSourceRoot</span><span class="sxs-lookup"><span data-stu-id="bcf00-199">OSDSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-200">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-200">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-201">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="bcf00-201">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="bcf00-202">\computername\content</span><span class="sxs-lookup"><span data-stu-id="bcf00-202">\computername\content</span></span></p>
<p><span data-ttu-id="bcf00-203">C:\foldername</span><span class="sxs-lookup"><span data-stu-id="bcf00-203">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="bcf00-204">可讓系統管理員在發佈期間為已排序的應用程式套件指定 OSD 檔案檢索的來源位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-204">Enables an administrator to specify a source location for OSD file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="bcf00-205">OSDSourceRoot 的可接受格式包括 UNC 路徑和 Url （HTTP 或 HTTPs）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-205">Acceptable formats for the OSDSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-206">IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="bcf00-206">IconSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-207">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-207">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-208">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="bcf00-208">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="bcf00-209">\computername\content</span><span class="sxs-lookup"><span data-stu-id="bcf00-209">\computername\content</span></span></p>
<p><span data-ttu-id="bcf00-210">C:\foldername</span><span class="sxs-lookup"><span data-stu-id="bcf00-210">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="bcf00-211">可讓系統管理員在發佈期間指定已排序之應用程式套件的圖示檔案檢索來源位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-211">Enables an administrator to specify a source location for icon file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="bcf00-212">IconSourceRoot 的可接受格式包括 UNC 路徑和 Url （HTTP 或 HTTPs）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-212">Acceptable formats for the IconSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-213">AutoLoadTriggers</span><span class="sxs-lookup"><span data-stu-id="bcf00-213">AutoLoadTriggers</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-214">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-214">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-215">預設 = 5</span><span class="sxs-lookup"><span data-stu-id="bcf00-215">Default=5</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-216">AutoLoad 是用戶端執行時間原則設定參數，可讓虛擬化應用程式的次要功能區塊在背景自動流入用戶端。</span><span class="sxs-lookup"><span data-stu-id="bcf00-216">AutoLoad is a client runtime policy configuration parameter that enables the secondary feature block of a virtualized application to be streamed to the client automatically in the background.</span></span> <span data-ttu-id="bcf00-217">AutoLoad 觸發程式是標誌，用來表示啟動自動載入應用程式的事件。</span><span class="sxs-lookup"><span data-stu-id="bcf00-217">The AutoLoad triggers are flags to indicate events that initiate auto-loading of applications.</span></span> <span data-ttu-id="bcf00-218">AutoLoad 會隱式使用背景資料流程，讓應用程式完全載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="bcf00-218">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span> <span data-ttu-id="bcf00-219">首先會載入主要功能區塊，並在背景中載入其餘的功能區塊，以啟用前景作業（例如與應用程式互動的使用者），並提供最佳的感知效能。</span><span class="sxs-lookup"><span data-stu-id="bcf00-219">The primary feature block will be loaded first, and the remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take place and provide optimal perceived performance.</span></span></p>
<p><span data-ttu-id="bcf00-220">位元遮罩值：</span><span class="sxs-lookup"><span data-stu-id="bcf00-220">Bit mask values:</span></span></p>
<p><span data-ttu-id="bcf00-221">（0）永不：不會設定任何位（值為0），不會執行自動載入，因為沒有設定任何觸發程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-221">(0) Never: No bits are set (value is 0), no auto loading will be performed, because there are no triggers set.</span></span></p>
<p><span data-ttu-id="bcf00-222">（1） OnLaunch：使用者啟動應用程式時開始載入。</span><span class="sxs-lookup"><span data-stu-id="bcf00-222">(1) OnLaunch: Loading starts when a user starts an application.</span></span></p>
<p><span data-ttu-id="bcf00-223">（2） OnRefresh：應用程式發佈時開始載入。</span><span class="sxs-lookup"><span data-stu-id="bcf00-223">(2) OnRefresh: Loading starts when the application is published.</span></span> <span data-ttu-id="bcf00-224">每當新增或更新套件記錄時，就會發生這種情況，例如，當進行發佈重新整理時。</span><span class="sxs-lookup"><span data-stu-id="bcf00-224">This occurs whenever the package record is added or updated—for example, when a publishing refresh occurs.</span></span></p>
<p><span data-ttu-id="bcf00-225">（4） OnLogin：使用者登入時開始載入。</span><span class="sxs-lookup"><span data-stu-id="bcf00-225">(4) OnLogin: Loading starts when a user logs in.</span></span></p>
<p><span data-ttu-id="bcf00-226">（5） OnLaunch 和 OnLogin： Default。</span><span class="sxs-lookup"><span data-stu-id="bcf00-226">(5) OnLaunch and OnLogin: Default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-227">AutoLoadTarget</span><span class="sxs-lookup"><span data-stu-id="bcf00-227">AutoLoadTarget</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-228">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-228">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-229">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-229">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-230">指示在任何指定的 AutoLoad 觸發程式發生時，將會自動載入哪些內容。</span><span class="sxs-lookup"><span data-stu-id="bcf00-230">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span> <span data-ttu-id="bcf00-231">位元遮罩值：</span><span class="sxs-lookup"><span data-stu-id="bcf00-231">Bit mask values:</span></span></p>
<p><span data-ttu-id="bcf00-232">（0）無：不會自動載入，不論可能會設定哪些觸發程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-232">(0) None: No auto-loading, regardless of what triggers may be set.</span></span></p>
<p><span data-ttu-id="bcf00-233">（1） PreviouslyUsed （預設值）：如果已啟用任何 AutoLoad 觸發程式，請只載入套件中之前已使用過之至少一個應用程式的套件，即已開始或 precached。</span><span class="sxs-lookup"><span data-stu-id="bcf00-233">(1) PreviouslyUsed (default): If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used—that is, started or precached.</span></span></p>
<p><span data-ttu-id="bcf00-234">（2）全部：如果已啟用任何 AutoLoad 觸發程式，套件（每個套件）或所有套件（針對用戶端設定）的所有應用程式都會自動載入，不論它們是否曾啟動。</span><span class="sxs-lookup"><span data-stu-id="bcf00-234">(2) All: If any AutoLoad trigger is enabled, all applications in the package (per package) or all packages (set for client) will be automatically loaded, whether or not they have ever been started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-235">RequireAuthorizationIfCached</span><span class="sxs-lookup"><span data-stu-id="bcf00-235">RequireAuthorizationIfCached</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-236">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-236">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-237">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-237">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-238">表示無論是否已在快取中，都必須擁有授權。</span><span class="sxs-lookup"><span data-stu-id="bcf00-238">Indicates that authorization is always required, whether or not an application is already in cache.</span></span> <span data-ttu-id="bcf00-239">可能的值：</span><span class="sxs-lookup"><span data-stu-id="bcf00-239">Possible values:</span></span></p>
<p><span data-ttu-id="bcf00-240">0 = False：總是嘗試連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="bcf00-240">0=False: Always try to connect to the server.</span></span> <span data-ttu-id="bcf00-241">如果無法建立伺服器連線，用戶端仍可讓使用者啟動先前載入到快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-241">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p>
<p><span data-ttu-id="bcf00-242">1 = True （預設值）：應用程式永遠必須在啟動時授權。</span><span class="sxs-lookup"><span data-stu-id="bcf00-242">1=True (default): Application always must be authorized at startup.</span></span> <span data-ttu-id="bcf00-243">針對 RTSP 流程式應用程式，會將使用者授權權杖傳送到伺服器以進行授權。</span><span class="sxs-lookup"><span data-stu-id="bcf00-243">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="bcf00-244">對於以檔案為基礎的應用程式，檔案 Acl 會控制使用者是否可存取應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-244">For file-based applications, file ACLs control whether a user may access the application.</span></span></p>
<p><span data-ttu-id="bcf00-245">重新開機 sftlist 服務，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="bcf00-245">Restart the sftlist service for the change to take effect.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-246">UserDataDirectory</span><span class="sxs-lookup"><span data-stu-id="bcf00-246">UserDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-247">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-247">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-248">APPDATA</span><span class="sxs-lookup"><span data-stu-id="bcf00-248">%APPDATA%</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-249">儲存圖示快取及使用者設定的位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-249">Location where the icon cache and user settings are stored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-250">GlobalDataDirectory</span><span class="sxs-lookup"><span data-stu-id="bcf00-250">GlobalDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-251">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-251">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-252">C:\Users\Public\Documents</span><span class="sxs-lookup"><span data-stu-id="bcf00-252">C:\Users\Public\Documents</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-253">用於全域 App-v 資料的目錄，包括適用于 OSD 檔案、圖示檔案、快速鍵資訊及 SystemGuard 資源（例如 .ini 檔案）的緩存。</span><span class="sxs-lookup"><span data-stu-id="bcf00-253">Directory to use for global App-V data, including caches for OSD files, icon files, shortcut information, and SystemGuard resources such as .ini files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-254">AllowCrashes</span><span class="sxs-lookup"><span data-stu-id="bcf00-254">AllowCrashes</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-255">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-255">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-256">0 或 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-256">0 or 1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-257">預設 = 0：值為0表示用戶端嘗試捕捉內部程式例外狀況，以便讓其他使用者應用程式在發生當機時能復原並繼續。</span><span class="sxs-lookup"><span data-stu-id="bcf00-257">Default=0: A value of 0 means that the client tries to catch internal program exceptions so that other user applications can recover and continue when a crash happens.</span></span> <span data-ttu-id="bcf00-258">值為1表示用戶端允許內部程式例外狀況發生，以便在偵錯工具中捕獲它們。</span><span class="sxs-lookup"><span data-stu-id="bcf00-258">A value of 1 means that the client allows the internal program exceptions to occur so that they can be captured in a debugger.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-259">CoreInternalTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-259">CoreInternalTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-260">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-260">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-261">60</span><span class="sxs-lookup"><span data-stu-id="bcf00-261">60</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-262">核心與前端之間的內部 IPC 要求超時（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-262">Time-out in seconds for internal IPC requests between core and front-end.</span></span> <span data-ttu-id="bcf00-263">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-263">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-264">DefaultSuiteCombineTime</span><span class="sxs-lookup"><span data-stu-id="bcf00-264">DefaultSuiteCombineTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-265">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-265">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-266">第</span><span class="sxs-lookup"><span data-stu-id="bcf00-266">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-267">這個值是用來指出啟動程式可以關閉的時間，以及在相同套件中的另一個應用程式執行時，不會產生任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bcf00-267">This value is used to indicate how soon after being started that a program can shut down and not generate any error messages when another application in the same suite is running.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-268">SerializedSuiteLaunchTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-268">SerializedSuiteLaunchTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-269">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-269">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-270">預設 = 60000</span><span class="sxs-lookup"><span data-stu-id="bcf00-270">Default=60000</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-271">定義用戶端在同一個套件中開始序列化程式時，要等待的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-271">Defines how long in milliseconds the client will wait as it tries to serialize program starts in the same suite.</span></span> <span data-ttu-id="bcf00-272">如果用戶端超時，程式將會繼續執行，但不會將其序列化。</span><span class="sxs-lookup"><span data-stu-id="bcf00-272">If the client times out, the program start will continue but it will not be serialized.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-273">ScriptTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-273">ScriptTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-274">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-275">300</span><span class="sxs-lookup"><span data-stu-id="bcf00-275">300</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-276">如果 WAIT = TRUE，則在 OSD 檔案中的腳本預設超時時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-276">Default time-out in seconds for scripts in OSD file if WAIT=TRUE.</span></span> <span data-ttu-id="bcf00-277">您可以使用超時（而不是 [等待]）來指定每腳本超時。</span><span class="sxs-lookup"><span data-stu-id="bcf00-277">You can specify per-script time-outs with TIMEOUT instead of WAIT.</span></span> <span data-ttu-id="bcf00-278">值為0表示沒有等待，而0xFFFFFFFF 則表示 [永久等待]。</span><span class="sxs-lookup"><span data-stu-id="bcf00-278">A value of 0 means no wait, and 0xFFFFFFFF means wait forever.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-279">LaunchRecordLogPath</span><span class="sxs-lookup"><span data-stu-id="bcf00-279">LaunchRecordLogPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-280">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-280">String</span></span> </p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="bcf00-281">如果在 HKLM 或 HKCU 底下，此值包含記錄檔的有效路徑，SFTTray 將會在程式啟動、關閉、無法啟動時寫入此記錄，並進入或離開中斷模式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-281">If, under either HKLM or HKCU, this value contains a valid path to a log file, SFTTray will write to this log when programs start, shut down, fail to launch, and enter or exit disconnected mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-282">LaunchRecordMask</span><span class="sxs-lookup"><span data-stu-id="bcf00-282">LaunchRecordMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-283">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-283">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-284">0x1A （26）記錄啟動錯誤和中斷模式進入與結束活動。</span><span class="sxs-lookup"><span data-stu-id="bcf00-284">0x1A (26) log launch errors and disconnected mode entry and exit activity.</span></span></p>
<p><span data-ttu-id="bcf00-285">0x1F （31）記錄所有內容。</span><span class="sxs-lookup"><span data-stu-id="bcf00-285">0x1F (31) logs everything.</span></span></p>
<p><span data-ttu-id="bcf00-286">0x0 （0）不記錄任何內容。</span><span class="sxs-lookup"><span data-stu-id="bcf00-286">0x0 (0) logs nothing.</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-287">指定記錄五個事件中的哪一個（位元遮罩值）：</span><span class="sxs-lookup"><span data-stu-id="bcf00-287">Specifies which of the five events are logged (bitmask values):</span></span></p>
<p><span data-ttu-id="bcf00-288">啟動程式1</span><span class="sxs-lookup"><span data-stu-id="bcf00-288">1 for program starts</span></span></p>
<p><span data-ttu-id="bcf00-289">2代表啟動失敗錯誤</span><span class="sxs-lookup"><span data-stu-id="bcf00-289">2 for launch failure errors</span></span></p>
<p><span data-ttu-id="bcf00-290">4供關閉</span><span class="sxs-lookup"><span data-stu-id="bcf00-290">4 for shutdowns</span></span></p>
<p><span data-ttu-id="bcf00-291">8用於進入斷開連接模式</span><span class="sxs-lookup"><span data-stu-id="bcf00-291">8 for entering disconnected mode</span></span></p>
<p><span data-ttu-id="bcf00-292">將 [退出中斷模式] 重新連線到伺服器的16</span><span class="sxs-lookup"><span data-stu-id="bcf00-292">16 for exiting disconnected mode to reconnect to a server</span></span></p>
<p><span data-ttu-id="bcf00-293">新增這些數位的任何組合，以開啟個別的訊息。</span><span class="sxs-lookup"><span data-stu-id="bcf00-293">Add any combination of those numbers to turn on the respective messages.</span></span> <span data-ttu-id="bcf00-294">如果不在註冊表中，則預設為0x1F。</span><span class="sxs-lookup"><span data-stu-id="bcf00-294">Defaults to 0x1F if not in registry.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-295">LaunchRecordWriteTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-295">LaunchRecordWriteTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-296">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-296">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-297">預設 = 3000</span><span class="sxs-lookup"><span data-stu-id="bcf00-297">Default=3000</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-298">指定在嘗試寫入開機記錄記錄檔（如果有另一個程式正在使用它）時，紙盒會等待的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-298">Specifies in milliseconds how long the tray will wait when trying to write to the launch record log if another process is using it.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-299">ImportSearchPath</span><span class="sxs-lookup"><span data-stu-id="bcf00-299">ImportSearchPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-300">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-300">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-301">d:\files;C:\documents 和 settings\user1\SFTs</span><span class="sxs-lookup"><span data-stu-id="bcf00-301">d:\files;C:\documents and settings\user1\SFTs</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-302">在提示使用者選取目錄前，最多五個目錄的分號分隔清單，以搜尋便攜 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="bcf00-302">A semicolon delimited list of up to five directories to search for portable SFT files before prompting the user to select a directory.</span></span> <span data-ttu-id="bcf00-303">路徑中的尾部反斜線是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="bcf00-303">Trailing backslash in paths is optional.</span></span> <span data-ttu-id="bcf00-304">此值預設不存在，且必須手動設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-304">This value is not present by default and must be set manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-305">UserImportPath</span><span class="sxs-lookup"><span data-stu-id="bcf00-305">UserImportPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-306">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-306">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-307">D:\SFTs</span><span class="sxs-lookup"><span data-stu-id="bcf00-307">D:\SFTs</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="bcf00-308">僅在 HKCU 下有效。</span><span class="sxs-lookup"><span data-stu-id="bcf00-308">Valid only under HKCU.</span></span> <span data-ttu-id="bcf00-309">尋找封裝匯入的 SFT 檔案時，使用者流覽到的最後一個位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-309">The last location the user browsed to while finding a SFT file for package import.</span></span> <span data-ttu-id="bcf00-310">如果成功找到 SFT，就會自動設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-310">Set automatically if the SFT is found successfully.</span></span> <span data-ttu-id="bcf00-311">當您嘗試自動找到 SFT 檔案時，會針對連續的匯入使用此功能。</span><span class="sxs-lookup"><span data-stu-id="bcf00-311">This is used on successive imports when trying to automatically locate SFT files.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-312">共用金鑰</span><span class="sxs-lookup"><span data-stu-id="bcf00-312">Shared Key</span></span>


<span data-ttu-id="bcf00-313">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared 鍵會控制跨 App V 元件共用的值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-313">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared key controls values that are shared across App-V components.</span></span> <span data-ttu-id="bcf00-314">下表提供與共享金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-314">The following table provides information about the registry values associated with the Shared key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-315">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-315">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-316">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-316">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-317">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-317">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-318">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-318">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-319">DumpPath</span><span class="sxs-lookup"><span data-stu-id="bcf00-319">DumpPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-320">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-320">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-321">Default = C：</span><span class="sxs-lookup"><span data-stu-id="bcf00-321">Default=C:</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="bcf00-322">在例外狀況中產生小型處理常式時，建立轉儲檔案的預設路徑。</span><span class="sxs-lookup"><span data-stu-id="bcf00-322">Default path to create dump files when generating a minidump on an exception.</span></span> <span data-ttu-id="bcf00-323">預設值為 C：\如果未指定的話。</span><span class="sxs-lookup"><span data-stu-id="bcf00-323">This defaults to C:\ if not specified.</span></span> <span data-ttu-id="bcf00-324">用戶端安裝程式會將此金鑰設定為 &lt; 應用程式虛擬化全域資料目錄 &gt; \Dumps。</span><span class="sxs-lookup"><span data-stu-id="bcf00-324">The Client installer sets this key to the &lt;App Virtualization global data directory&gt;\Dumps.</span></span> <span data-ttu-id="bcf00-325">Sequencer 安裝程式會將此金鑰設定為安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="bcf00-325">The Sequencer installer sets this key to the installation directory.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-326">DumpPathSizeLimit</span><span class="sxs-lookup"><span data-stu-id="bcf00-326">DumpPathSizeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-327">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-327">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-328">1000</span><span class="sxs-lookup"><span data-stu-id="bcf00-328">1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-329">指定可用於儲存 minidumps 的最大磁碟空間總量（以 mb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-329">Specifies the maximum total amount of disk space in megabytes that can be used to store minidumps.</span></span> <span data-ttu-id="bcf00-330">預設 = 1000 MB。</span><span class="sxs-lookup"><span data-stu-id="bcf00-330">Default = 1000 MB.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-331">網路金鑰</span><span class="sxs-lookup"><span data-stu-id="bcf00-331">Network Key</span></span>


<span data-ttu-id="bcf00-332">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network 鍵會控制各種與網路相關的參數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-332">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network key controls a variety of network-related parameters.</span></span> <span data-ttu-id="bcf00-333">此金鑰主要是由網路傳輸代理程式所使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-333">This key is primarily used by the network transport agent.</span></span> <span data-ttu-id="bcf00-334">下表提供與網路金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-334">The following table provides information about the registry values associated with the Network key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-335">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-335">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-336">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-336">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-337">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-337">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-338">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-338">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-339">Online</span><span class="sxs-lookup"><span data-stu-id="bcf00-339">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-340">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-340">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-341">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-341">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-342">啟用或停用離線模式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-342">Enables or disables offline mode.</span></span> <span data-ttu-id="bcf00-343">如果設為0，用戶端將無法與 App-v 管理伺服器或發佈伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-343">If set to 0, the client will not communicate with App-V Management Servers or publishing servers.</span></span> <span data-ttu-id="bcf00-344">在中斷連接的操作中，用戶端可以啟動已載入的應用程式，即使未連線到 App-v 管理伺服器也一樣。</span><span class="sxs-lookup"><span data-stu-id="bcf00-344">In disconnected operations, the client can start a loaded application even when it is not connected to an App-V Management Server.</span></span> <span data-ttu-id="bcf00-345">在離線模式中，用戶端不會嘗試連線到 App-v 管理伺服器或發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="bcf00-345">In offline mode, the client does not attempt to connect to an App-V Management Server or publishing server.</span></span> <span data-ttu-id="bcf00-346">您必須允許斷開連接的操作能夠離線工作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-346">You must allow disconnected operations to be able to work offline.</span></span> <span data-ttu-id="bcf00-347">預設值為1（線上），而0則停用（離線）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-347">Default value is 1 enabled (online), and 0 is disabled (offline).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-348">AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="bcf00-348">AllowDisconnectedOperation</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-349">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-349">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-350">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-350">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-351">啟用或停用中斷式的操作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-351">Enables or disables disconnected operation.</span></span> <span data-ttu-id="bcf00-352">預設值為1，且停用0。</span><span class="sxs-lookup"><span data-stu-id="bcf00-352">Default value is 1 enabled, and 0 is disabled.</span></span> <span data-ttu-id="bcf00-353">當中斷式作業啟用時，App-v 用戶端可以啟動已載入的應用程式（即使它未連線到 App-v 管理伺服器）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-353">When disconnected operations are enabled, the App-V client can start a loaded application even when it is not connected to an App-V Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-354">FastConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-354">FastConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-356">預設 = 1000</span><span class="sxs-lookup"><span data-stu-id="bcf00-356">Default=1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-357">這個值會指定 TCP 連接逾時（以毫秒為單位），以判斷何時進入中斷式作業模式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-357">This value specifies the TCP connect time-out in milliseconds to determine when to go into disconnected operations mode.</span></span> <span data-ttu-id="bcf00-358">這個值可以用來覆寫預設的 ConnectTimeout 為20秒（網路事務的 App-v 連接逾時），或是系統的 TCP 超時大約25秒的時間。</span><span class="sxs-lookup"><span data-stu-id="bcf00-358">This value can be used to override the default ConnectTimeout of 20 seconds (App-V connect time-out for network transactions) or the system’s TCP time-out of approximately 25 seconds.</span></span> <span data-ttu-id="bcf00-359">這樣就能快速地將用戶端連線到 [中斷連線] 作業模式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-359">This brings the client into disconnected operations mode quickly.</span></span> <span data-ttu-id="bcf00-360">在下一次連接時套用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-360">Applied on the next connect.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-361">LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="bcf00-361">LimitDisconnectedOperation</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-363">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-363">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-364">只有在 AllowDisconnectedOperation 為1時才適用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-364">Applicable only if AllowDisconnectedOperation is 1, enabled.</span></span> <span data-ttu-id="bcf00-365">這個值會判斷在中斷連接的操作中，允許用戶端執行多久時間的時間限制。</span><span class="sxs-lookup"><span data-stu-id="bcf00-365">This value determines whether there will be a time limit for how long the client will be allowed to operate in disconnected operations.</span></span> <span data-ttu-id="bcf00-366">1 = 有限。</span><span class="sxs-lookup"><span data-stu-id="bcf00-366">1=limited.</span></span> <span data-ttu-id="bcf00-367">0 = 無限制。</span><span class="sxs-lookup"><span data-stu-id="bcf00-367">0=unlimited.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-368">DOTimeoutMinutes</span><span class="sxs-lookup"><span data-stu-id="bcf00-368">DOTimeoutMinutes</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-369">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-369">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-370">預設 = 129600</span><span class="sxs-lookup"><span data-stu-id="bcf00-370">Default=129,600</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-371">指出應用程式在中斷式作業模式中可使用的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-371">Indicates how many minutes an application may be used in disconnected operation mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="bcf00-372">有效值為1至999999，以分鐘為單位（1–1439998560分鐘）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-372">The valid values are 1–999,999 in days expressed in minutes (1–1,439,998,560 minutes).</span></span> <span data-ttu-id="bcf00-373">預設值為90天或129600分鐘。</span><span class="sxs-lookup"><span data-stu-id="bcf00-373">The default value is 90 days or 129,600 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-374">通訊協定</span><span class="sxs-lookup"><span data-stu-id="bcf00-374">Protocol</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-375">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-375">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-376">預設值 = 8</span><span class="sxs-lookup"><span data-stu-id="bcf00-376">Default=8</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-377">要使用的預設通訊協定（TCP 與 SSL）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-377">Default protocol to use (TCP vs SSL).</span></span> <span data-ttu-id="bcf00-378">[選項] 對話方塊中的 [設定]。</span><span class="sxs-lookup"><span data-stu-id="bcf00-378">Configure in Options Dialog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-379">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-379">ReadTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-380">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-380">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-381">20</span><span class="sxs-lookup"><span data-stu-id="bcf00-381">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-382">讀取網路交易的超時時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-382">Read time-out for network transactions, in seconds.</span></span> <span data-ttu-id="bcf00-383">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-383">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-384">WriteTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-384">WriteTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-385">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-385">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-386">20</span><span class="sxs-lookup"><span data-stu-id="bcf00-386">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-387">寫入網路交易的超時時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-387">Write time-out for network transactions, in seconds.</span></span> <span data-ttu-id="bcf00-388">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-388">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-389">ConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="bcf00-389">ConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-390">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-390">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-391">20</span><span class="sxs-lookup"><span data-stu-id="bcf00-391">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-392">連接網路交易的超時時間（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-392">Connect time-out for network transactions, in seconds.</span></span> <span data-ttu-id="bcf00-393">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-393">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-394">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="bcf00-394">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-396">3</span><span class="sxs-lookup"><span data-stu-id="bcf00-396">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-397">嘗試重新建立刪除的會話的次數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-397">The number of times to try to reestablish a dropped session.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-398">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="bcf00-398">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-399">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-399">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-400">工資</span><span class="sxs-lookup"><span data-stu-id="bcf00-400">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-401">嘗試重新建立已刪除的會話之間所等待的秒數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-401">The number of seconds to wait between tries to reestablish a dropped session.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-402">Http 金鑰</span><span class="sxs-lookup"><span data-stu-id="bcf00-402">Http Key</span></span>


<span data-ttu-id="bcf00-403">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http 鍵會控制與 Http 資料流程相關的參數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-403">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http key controls the parameters that are related to Http streaming.</span></span> <span data-ttu-id="bcf00-404">此金鑰主要是由網路傳輸代理程式使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-404">This key is used primarily by the network transport agent.</span></span> <span data-ttu-id="bcf00-405">下表提供與 Http 金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-405">The following table provides information about the registry values that are associated with the Http key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-406">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-406">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-407">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-407">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-408">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-408">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-409">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-409">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-410">LaunchIfNotFound</span><span class="sxs-lookup"><span data-stu-id="bcf00-410">LaunchIfNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-411">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-411">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-412">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-412">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-413">控制 HTTP 資料流程連線與 HTTP 伺服器的連線，以及資料包檔案在 HTTP 伺服器上不再存在的行為。</span><span class="sxs-lookup"><span data-stu-id="bcf00-413">Controls the behavior of HTTP streaming when a connection to the HTTP server can be established and the package file no longer exists on the HTTP server.</span></span> <span data-ttu-id="bcf00-414">如果該值不存在，或者如果未設定為1，則 App-v 用戶端不會讓您啟動先前載入到快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-414">If the value does not exist or if it is not set to 1, the App-V client does not let you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="bcf00-415">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-415">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-416">如果此值設定為1，則 App-v 用戶端可讓您啟動先前載入到快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-416">If this value is set to 1, the App-V client lets you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-417">檔案系統金鑰</span><span class="sxs-lookup"><span data-stu-id="bcf00-417">File System Key</span></span>


<span data-ttu-id="bcf00-418">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS 參數所含的值控制 App-v 的檔案系統參數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-418">The values that are contained under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS key control the file system parameters for App-V.</span></span> <span data-ttu-id="bcf00-419">下表提供與 AppFS 金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-419">The following table provides information about the registry values associated with the AppFS key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-420">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-420">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-421">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-421">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-422">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-422">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-423">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-423">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-424">FileSize</span><span class="sxs-lookup"><span data-stu-id="bcf00-424">FileSize</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-425">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-425">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-426">4096</span><span class="sxs-lookup"><span data-stu-id="bcf00-426">4096</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-427">檔案系統快取檔案的大小上限（mb）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-427">Maximum size in megabytes of file system cache file.</span></span> <span data-ttu-id="bcf00-428">如果您在註冊表中變更這個值，您必須將狀態設為0並重新啟動。</span><span class="sxs-lookup"><span data-stu-id="bcf00-428">If you change this value in the registry, you must set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-429">FileName</span><span class="sxs-lookup"><span data-stu-id="bcf00-429">FileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-430">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-430">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="bcf00-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-432">檔案系統快取檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-432">Location of file system cache file.</span></span> <span data-ttu-id="bcf00-433">如果您在註冊表中變更這個值，您必須將 FileSize 保持不變，然後重新開機或將狀態設定為0並重新啟動。</span><span class="sxs-lookup"><span data-stu-id="bcf00-433">If you change this value in the registry, you must either leave FileSize the same and reboot or set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-434">DriveLetter</span><span class="sxs-lookup"><span data-stu-id="bcf00-434">DriveLetter</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-435">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-435">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-436">Q：</span><span class="sxs-lookup"><span data-stu-id="bcf00-436">Q:</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-437">將掛載 app-v 檔案系統的磁片磁碟機（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-437">Drive where App-V file system will be mounted, if it is available.</span></span> <span data-ttu-id="bcf00-438">此值是由監聽器或安裝程式所設定，且會由檔案系統讀取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-438">This value is set either by the listener or the installer, and it is read by the file system.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-439">狀態</span><span class="sxs-lookup"><span data-stu-id="bcf00-439">State</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-440">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-440">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-441">0x100</span><span class="sxs-lookup"><span data-stu-id="bcf00-441">0x100</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-442">檔案系統的狀態。</span><span class="sxs-lookup"><span data-stu-id="bcf00-442">State of file system.</span></span> <span data-ttu-id="bcf00-443">設定為0並重新啟動，以完全清除檔案系統快取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-443">Set to 0 and reboot to completely clear the file system cache.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-444">FileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="bcf00-444">FileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-445">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-445">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-446">C:\Profiles\Joe\SG</span><span class="sxs-lookup"><span data-stu-id="bcf00-446">C:\Profiles\Joe\SG</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-447">Symlinks 的路徑，請在 [HKCU] 下設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-447">Path for symlinks, set under HKCU.</span></span> <span data-ttu-id="bcf00-448">請勿修改（使用 [設定] 底下的 [資料目錄] 來變更）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-448">Do not modify (use data directory under Configuration to change).</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-449">GlobalFileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="bcf00-449">GlobalFileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-450">字串</span><span class="sxs-lookup"><span data-stu-id="bcf00-450">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-451">C:\Users\Public\Documents\SoftGrid Client\AppFS 儲存體</span><span class="sxs-lookup"><span data-stu-id="bcf00-451">C:\Users\Public\Documents\SoftGrid Client\AppFS Storage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-452">通用檔案系統資料的路徑。</span><span class="sxs-lookup"><span data-stu-id="bcf00-452">Path for global file system data.</span></span> <span data-ttu-id="bcf00-453">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-453">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-454">MaxPercentToLockInCache</span><span class="sxs-lookup"><span data-stu-id="bcf00-454">MaxPercentToLockInCache</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-455">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-455">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-456">預設值 = 90</span><span class="sxs-lookup"><span data-stu-id="bcf00-456">Default=90</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-457">指定可鎖定之檔案系統快取檔案的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="bcf00-457">Specifies the maximum percentage of the file system cache file that can be locked.</span></span> <span data-ttu-id="bcf00-458">請勿修改。</span><span class="sxs-lookup"><span data-stu-id="bcf00-458">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-459">UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="bcf00-459">UnloadLeastRecentlyUsed</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-460">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-460">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-461">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-461">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-462">檔案系統快取空間管理功能使用最近最常使用的（LRU）演算法，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-462">The file system cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="bcf00-463">如果新套件所需的空間會超過快取中的可用空間，App-v 用戶端會使用這項功能來判斷它可以從快取中刪除的現有套件（如果有的話），為新套件騰出空間。</span><span class="sxs-lookup"><span data-stu-id="bcf00-463">If the space that is required for a new package would exceed the available free space in the cache, the App-V Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="bcf00-464">用戶端會刪除最舊的最近存取日期的套件（如果它比 MinPkgAge 註冊表值中指定的值還舊）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-464">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="bcf00-465">值為0（停用）和1（預設值為啟用）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-465">Values are 0 (disabled) and 1 (default, enabled).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-466">MinPackageAge</span><span class="sxs-lookup"><span data-stu-id="bcf00-466">MinPackageAge</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-467">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-467">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-468">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-468">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-469">若要判斷何時可以選取要捨棄的套件，請將此登錄值設定為在最近一次存取套件之後所要經過的最少天數。</span><span class="sxs-lookup"><span data-stu-id="bcf00-469">To determine when the package can be selected for discard, set this registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="bcf00-470">您最近使用的套件將不會遭到捨棄。</span><span class="sxs-lookup"><span data-stu-id="bcf00-470">Packages that have been used more recently are not discarded.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-471">許可權金鑰</span><span class="sxs-lookup"><span data-stu-id="bcf00-471">Permissions Key</span></span>


<span data-ttu-id="bcf00-472">為了協助防止使用者犯錯誤，系統管理員可以使用 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions 鍵來控制對非系統管理使用者的部分動作，例如防止使用者不小心卸載程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-472">To help to prevent users from making mistakes, administrators can use the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions key to control access to some actions for non-administrative users—for example, to prevent users from accidentally unloading programs.</span></span> <span data-ttu-id="bcf00-473">具有系統管理許可權的使用者可以為自己提供下列任何一種許可權。</span><span class="sxs-lookup"><span data-stu-id="bcf00-473">Users with administrative rights can give themselves any of these permissions.</span></span> <span data-ttu-id="bcf00-474">在共用系統上（例如遠端桌面工作階段主機（RD 工作階段主機）伺服器（舊稱終端伺服器）系統），請謹慎向使用者授予其他許可權，因為其中一些許可權可以讓使用者控制系統上所有使用者所使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-474">On shared systems, such as a Remote Desktop Session Host (RD Session Host) server (formerly Terminal Server) system, be careful when granting additional permissions to users because some of these permissions would enable users to control the applications used by all users on the system.</span></span> <span data-ttu-id="bcf00-475">這些設定的可能值為1（允許）和0（不允許）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-475">Possible values for these settings are 1 (allow) and 0 (disallow).</span></span>

<span data-ttu-id="bcf00-476">[許可權金鑰] 設定會控制啟用命名動作的所有介面。</span><span class="sxs-lookup"><span data-stu-id="bcf00-476">The Permissions key settings control all interfaces that enable the named actions.</span></span> <span data-ttu-id="bcf00-477">這包括 [選項] 對話方塊、[SFTTray] 和 [SFTMime]。</span><span class="sxs-lookup"><span data-stu-id="bcf00-477">This includes the Options Dialog, SFTTray, and SFTMime.</span></span> <span data-ttu-id="bcf00-478">這些設定不會影響系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bcf00-478">These settings do not affect administrators.</span></span> <span data-ttu-id="bcf00-479">下表提供與許可權金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-479">The following table provides information about the registry values associated with the Permissions key.</span></span>

<span data-ttu-id="bcf00-480">名稱類型資料（範例）描述 ChangeFSDrive</span><span class="sxs-lookup"><span data-stu-id="bcf00-480">Name Type Data (Examples) Description ChangeFSDrive</span></span>

<span data-ttu-id="bcf00-481">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-481">DWORD</span></span>

<span data-ttu-id="bcf00-482">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-482">Default=0</span></span>

<span data-ttu-id="bcf00-483">值為1時，可讓使用者挑選不同的磁片磁碟機盤符作為檔案系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="bcf00-483">A value of 1 allows users to pick a different drive letter to be used as the file system drive.</span></span>

<span data-ttu-id="bcf00-484">ChangeCacheSize</span><span class="sxs-lookup"><span data-stu-id="bcf00-484">ChangeCacheSize</span></span>

<span data-ttu-id="bcf00-485">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-485">DWORD</span></span>

<span data-ttu-id="bcf00-486">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-486">Default=0</span></span>

<span data-ttu-id="bcf00-487">值1可讓使用者變更快取大小。</span><span class="sxs-lookup"><span data-stu-id="bcf00-487">A value of 1 allows users to change the cache size.</span></span>

<span data-ttu-id="bcf00-488">ChangeLogSettings</span><span class="sxs-lookup"><span data-stu-id="bcf00-488">ChangeLogSettings</span></span>

<span data-ttu-id="bcf00-489">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-489">DWORD</span></span>

<span data-ttu-id="bcf00-490">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-490">Default=0</span></span>

<span data-ttu-id="bcf00-491">值1可讓使用者修改記錄層級、變更其位置，以及透過使用者介面將其重設。</span><span class="sxs-lookup"><span data-stu-id="bcf00-491">A value of 1 allows users to modify the log level, change its location, and reset it through the user interface.</span></span>

<span data-ttu-id="bcf00-492">AddApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-492">AddApp</span></span>

<span data-ttu-id="bcf00-493">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-493">DWORD</span></span>

<span data-ttu-id="bcf00-494">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-494">Default=0</span></span>

<span data-ttu-id="bcf00-495">值1可讓使用者明確地新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-495">A value of 1 allows users to add applications explicitly.</span></span> <span data-ttu-id="bcf00-496">這不會影響透過發佈重新整理所新增的應用程式，也不會防止使用者開始（也不是隱式新增）尚未新增的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-496">This does not affect applications that are added through publishing refresh nor does it prevent users from starting (and thereby implicitly adding) applications that have not already been added.</span></span> <span data-ttu-id="bcf00-497">值為0或1。</span><span class="sxs-lookup"><span data-stu-id="bcf00-497">Values are 0 or 1.</span></span>

<span data-ttu-id="bcf00-498">LoadApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-498">LoadApp</span></span> 

<span data-ttu-id="bcf00-499">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-499">DWORD</span></span> 

<span data-ttu-id="bcf00-500">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-500">0</span></span>

<span data-ttu-id="bcf00-501">不允許使用者載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-501">Does not allow a user to load an application.</span></span> <span data-ttu-id="bcf00-502">這是 RD 工作階段主機的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-502">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="bcf00-503">如果您是行動使用者，您可能會想要將您的應用程式完全載入在快取中，以便在斷開式作業或離線模式時使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-503">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="bcf00-504">若要從 App-v 管理伺服器或 App-v 流式處理伺服器對流進行應用程式，您必須連線到伺服器才能載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-504">To stream applications from the App-V Management Server or the App-V Streaming Server, you must be connected to a server to load applications.</span></span>

<span data-ttu-id="bcf00-505">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-505">1</span></span>

<span data-ttu-id="bcf00-506">允許使用者載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-506">Allows a user to load an application.</span></span> <span data-ttu-id="bcf00-507">這是 Windows 桌上型電腦的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-507">This is the default for Windows desktops.</span></span> 

<span data-ttu-id="bcf00-508">UnloadApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-508">UnloadApp</span></span> 

<span data-ttu-id="bcf00-509">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-509">DWORD</span></span> 

<span data-ttu-id="bcf00-510">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-510">0</span></span>

<span data-ttu-id="bcf00-511">不允許使用者卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-511">Does not allow a user to unload an application.</span></span> <span data-ttu-id="bcf00-512">當您載入或卸載套件時，套件中的所有應用程式都會載入或從快取中移除。</span><span class="sxs-lookup"><span data-stu-id="bcf00-512">When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span>

<span data-ttu-id="bcf00-513">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-513">1</span></span>

<span data-ttu-id="bcf00-514">允許使用者卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-514">Allows a user to unload an application.</span></span> 

<span data-ttu-id="bcf00-515">LockApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-515">LockApp</span></span> 

<span data-ttu-id="bcf00-516">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-516">DWORD</span></span> 

<span data-ttu-id="bcf00-517">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-517">0</span></span>

<span data-ttu-id="bcf00-518">不允許使用者鎖定和解除鎖定應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-518">Does not allow a user to lock and unlock an application.</span></span> <span data-ttu-id="bcf00-519">這是 RD 工作階段主機的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-519">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="bcf00-520">無法從快取中移除鎖定的應用程式，為新的應用程式騰出空間。</span><span class="sxs-lookup"><span data-stu-id="bcf00-520">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="bcf00-521">若要從適用于遠端桌面服務（舊稱終端服務）快取的 App-v 桌面或用戶端移除鎖定的應用程式，您必須解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-521">To remove a locked application from the App-V Desktop or Client for Remote Desktop Services (formerly Terminal Services) cache, you must unlock it.</span></span>

<span data-ttu-id="bcf00-522">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-522">1</span></span>

<span data-ttu-id="bcf00-523">允許使用者鎖定和解除鎖定應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-523">Allows a user to lock and unlock an application.</span></span> <span data-ttu-id="bcf00-524">這是 Windows 桌上型電腦的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-524">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="bcf00-525">ManageTypes</span><span class="sxs-lookup"><span data-stu-id="bcf00-525">ManageTypes</span></span> 

<span data-ttu-id="bcf00-526">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-526">DWORD</span></span> 

<span data-ttu-id="bcf00-527">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-527">0</span></span>

<span data-ttu-id="bcf00-528">不允許使用者單獨新增、編輯或移除該使用者的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="bcf00-528">Does not allow a user to add, edit, or remove file type associations for that User alone.</span></span> <span data-ttu-id="bcf00-529">這是 RD 工作階段主機的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-529">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="bcf00-530">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-530">1</span></span>

<span data-ttu-id="bcf00-531">允許使用者只新增、編輯及移除該使用者的檔案類型關聯，而不是全域。</span><span class="sxs-lookup"><span data-stu-id="bcf00-531">Allows a user to add, edit, and remove file type associations for that user only and not globally.</span></span> <span data-ttu-id="bcf00-532">這是 Windows 桌上型電腦的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-532">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="bcf00-533">RefreshServer</span><span class="sxs-lookup"><span data-stu-id="bcf00-533">RefreshServer</span></span> 

<span data-ttu-id="bcf00-534">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-534">DWORD</span></span> 

<span data-ttu-id="bcf00-535">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-535">0</span></span>

<span data-ttu-id="bcf00-536">不允許使用者觸發 MIME 設定的重新整理。</span><span class="sxs-lookup"><span data-stu-id="bcf00-536">Does not allow a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="bcf00-537">這是 RD 工作階段主機的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-537">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="bcf00-538">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-538">1</span></span>

<span data-ttu-id="bcf00-539">讓使用者觸發 MIME 設定的重新整理。</span><span class="sxs-lookup"><span data-stu-id="bcf00-539">Enables a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="bcf00-540">這是 Windows 桌上型電腦的預設值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-540">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="bcf00-541">UpdateOSDFile</span><span class="sxs-lookup"><span data-stu-id="bcf00-541">UpdateOSDFile</span></span>

<span data-ttu-id="bcf00-542">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-542">DWORD</span></span>

<span data-ttu-id="bcf00-543">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-543">Default= 0</span></span>

<span data-ttu-id="bcf00-544">值為1時，使用者可以使用修改過的 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="bcf00-544">A value of 1 enables a user to use a modified OSD file.</span></span>

<span data-ttu-id="bcf00-545">ImportApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-545">ImportApp</span></span> 

<span data-ttu-id="bcf00-546">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-546">DWORD</span></span> 

<span data-ttu-id="bcf00-547">0</span><span class="sxs-lookup"><span data-stu-id="bcf00-547">0</span></span>

<span data-ttu-id="bcf00-548">不允許使用者將應用程式匯入快取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-548">Does not allow a user to import applications into cache.</span></span> <span data-ttu-id="bcf00-549">[載入] 與 [匯入] 之間的差異是，觸發載入時，用戶端會從位於 OSD、ASR 或 Override URL 中的目前設定位置取得套件。</span><span class="sxs-lookup"><span data-stu-id="bcf00-549">The difference between Load and Import is that when a Load is triggered, the client gets the package from the currently configured location contained in the OSD, ASR, or Override URL.</span></span> <span data-ttu-id="bcf00-550">使用匯入時，必須指定從中取得套件的位置。</span><span class="sxs-lookup"><span data-stu-id="bcf00-550">When using Import, a location to get the package from must be specified.</span></span> 

<span data-ttu-id="bcf00-551">sr-1</span><span class="sxs-lookup"><span data-stu-id="bcf00-551">1</span></span>

<span data-ttu-id="bcf00-552">允許使用者將應用程式匯入快取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-552">Allows a user to import applications into cache.</span></span> 

<span data-ttu-id="bcf00-553">ChangeRefreshSettings</span><span class="sxs-lookup"><span data-stu-id="bcf00-553">ChangeRefreshSettings</span></span>

<span data-ttu-id="bcf00-554">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-554">DWORD</span></span>

<span data-ttu-id="bcf00-555">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-555">Default=0</span></span>

<span data-ttu-id="bcf00-556">值1可讓使用者修改伺服器的重新整理設定（[登入] 和 [定期重新整理] 時重新整理）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-556">A value of 1 allows users to modify the refresh settings for servers (refresh on login and periodic refresh).</span></span> <span data-ttu-id="bcf00-557">這並不表示使用者可以修改其他伺服器設定（path、host 等）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-557">This does not imply that the user can modify other server settings (path, host, and so on).</span></span>

<span data-ttu-id="bcf00-558">ManageServers</span><span class="sxs-lookup"><span data-stu-id="bcf00-558">ManageServers</span></span>

<span data-ttu-id="bcf00-559">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-559">DWORD</span></span>

<span data-ttu-id="bcf00-560">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-560">Default=0</span></span>

<span data-ttu-id="bcf00-561">如果值為1，則使用者可以新增、編輯及移除伺服器，除了編輯由 ChangeRefreshSettings 許可權控制的重新整理設定以外。</span><span class="sxs-lookup"><span data-stu-id="bcf00-561">A value of 1 allows the user to add, edit, and remove servers, except for editing the refresh settings, which is controlled by the ChangeRefreshSettings permission.</span></span>

<span data-ttu-id="bcf00-562">PublishShortcut</span><span class="sxs-lookup"><span data-stu-id="bcf00-562">PublishShortcut</span></span>

<span data-ttu-id="bcf00-563">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-563">DWORD</span></span>

<span data-ttu-id="bcf00-564">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-564">Default=0</span></span>

<span data-ttu-id="bcf00-565">值1可讓使用者透過使用者介面發佈快速鍵。</span><span class="sxs-lookup"><span data-stu-id="bcf00-565">A value of 1 allows users to publish shortcuts through the user interface.</span></span> <span data-ttu-id="bcf00-566">這不會影響在發佈更新期間發佈的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-566">This does not affect shortcuts that are published during a publishing refresh.</span></span>

<span data-ttu-id="bcf00-567">ViewAllApplications</span><span class="sxs-lookup"><span data-stu-id="bcf00-567">ViewAllApplications</span></span>

<span data-ttu-id="bcf00-568">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-568">DWORD</span></span>

<span data-ttu-id="bcf00-569">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-569">Default=0</span></span>

<span data-ttu-id="bcf00-570">值1會透過使用者介面顯示所有應用程式;否則，只會顯示使用者的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-570">A value of 1 displays all applications through the user interface; otherwise, only the user’s applications are displayed.</span></span>

<span data-ttu-id="bcf00-571">RepairApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-571">RepairApp</span></span>

<span data-ttu-id="bcf00-572">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-572">DWORD</span></span>

<span data-ttu-id="bcf00-573">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-573">Default=1</span></span>

<span data-ttu-id="bcf00-574">值1可讓使用者在 SFTMime 或用戶端管理主控台上的應用程式上使用修復動作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-574">A value of 1 allows the user to use the Repair action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="bcf00-575">當您修復應用程式時，您會移除任何自訂的使用者設定，並還原預設設定。</span><span class="sxs-lookup"><span data-stu-id="bcf00-575">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="bcf00-576">這個動作不會變更或刪除快速鍵或檔案類型關聯，也不會從快取中移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-576">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

<span data-ttu-id="bcf00-577">ClearApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-577">ClearApp</span></span>

<span data-ttu-id="bcf00-578">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-578">DWORD</span></span>

<span data-ttu-id="bcf00-579">預設 = 1</span><span class="sxs-lookup"><span data-stu-id="bcf00-579">Default=1</span></span>

<span data-ttu-id="bcf00-580">如果值為1，則使用者可以在 SFTMime 或用戶端管理主控台中使用應用程式的 Clear 操作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-580">A value of 1 allows the user to use the Clear action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="bcf00-581">當您從主控台清除應用程式時，您將無法再使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-581">When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="bcf00-582">不過，應用程式仍會保留在快取中，而且在同一系統上仍可供其他使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-582">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="bcf00-583">在發佈重新整理之後，清除的應用程式就會再次提供給您使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-583">After a publishing refresh, the cleared applications will again become available to you.</span></span>

<span data-ttu-id="bcf00-584">DeleteApp</span><span class="sxs-lookup"><span data-stu-id="bcf00-584">DeleteApp</span></span>

<span data-ttu-id="bcf00-585">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-585">DWORD</span></span>

<span data-ttu-id="bcf00-586">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-586">Default=0</span></span>

<span data-ttu-id="bcf00-587">值1可讓使用者在 SFTMime 或用戶端管理主控台上的應用程式上使用 [刪除] 動作。</span><span class="sxs-lookup"><span data-stu-id="bcf00-587">A value of 1 allows the user to use the Delete action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="bcf00-588">當您刪除應用程式時，所選的應用程式將無法再供該用戶端上的任何使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-588">When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="bcf00-589">快捷方式和檔案類型關聯隨即刪除，並從快取中刪除應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcf00-589">Shortcuts and file type associations are deleted and the application is deleted from cache.</span></span> <span data-ttu-id="bcf00-590">不過，如果另一個應用程式參照檔案系統快取或所選應用程式的設定資料中的資料，這些專案就不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="bcf00-590">However, if another application refers to data in the file system cache or settings data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="bcf00-591">更新發佈之後，已刪除的應用程式就會再次提供給您使用。</span><span class="sxs-lookup"><span data-stu-id="bcf00-591">After a publishing refresh, the deleted applications will again become available to you.</span></span>

<span data-ttu-id="bcf00-592">ToggleOfflineMode</span><span class="sxs-lookup"><span data-stu-id="bcf00-592">ToggleOfflineMode</span></span>

<span data-ttu-id="bcf00-593">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-593">DWORD</span></span>

<span data-ttu-id="bcf00-594">值1可讓使用者選取以離線模式執行用戶端。</span><span class="sxs-lookup"><span data-stu-id="bcf00-594">A value of 1 allows the users to select to run the client in Offline Mode.</span></span> <span data-ttu-id="bcf00-595">在離線模式中，應用程式虛擬化用戶端可以啟動已載入的應用程式（即使它未連線到 Application Virtualization 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-595">In Offline Mode, the Application Virtualization client can start a loaded application even when it is not connected to an Application Virtualization Server.</span></span>



## <span data-ttu-id="bcf00-596">自訂設定</span><span class="sxs-lookup"><span data-stu-id="bcf00-596">Custom Settings</span></span>


<span data-ttu-id="bcf00-597">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings 鍵包含前端元件專用的值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-597">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings key contains values specific to front-end components.</span></span> <span data-ttu-id="bcf00-598">所有的自訂設定都是以字串形式儲存。</span><span class="sxs-lookup"><span data-stu-id="bcf00-598">All custom settings are stored as strings.</span></span> <span data-ttu-id="bcf00-599">下表提供與 CustomSettings 金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-599">The following table provides information about the registry values associated with the CustomSettings key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-600">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-600">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-601">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-601">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-602">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-602">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-603">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-603">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-604">TrayErrorDelay</span><span class="sxs-lookup"><span data-stu-id="bcf00-604">TrayErrorDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-605">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-605">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-606">預設 = 30</span><span class="sxs-lookup"><span data-stu-id="bcf00-606">Default=30</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-607">應用程式虛擬化通知區域將會顯示錯誤訊息（例如啟動失敗）的時間（以秒為單位） &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="bcf00-607">Time in seconds that the Application Virtualization notification area will display error messages like &quot;Launch failed&quot;.</span></span> <span data-ttu-id="bcf00-608">1的最小值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-608">Minimum value of 1.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-609">TraySuccessDelay</span><span class="sxs-lookup"><span data-stu-id="bcf00-609">TraySuccessDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-610">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-610">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-611">預設值 = 10</span><span class="sxs-lookup"><span data-stu-id="bcf00-611">Default=10</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bcf00-612">Appvmed 通知區域會顯示成功訊息（例如 &quot; Word 啟動 &quot; 或 &quot; Excel 關閉）的時間（秒） &quot; 。</span><span class="sxs-lookup"><span data-stu-id="bcf00-612">Time in seconds that the appvmed notification area will display success messages like &quot;Word launched&quot; or &quot;Excel shut down&quot;.</span></span> <span data-ttu-id="bcf00-613">如果是0，則會禁止顯示這些訊息。</span><span class="sxs-lookup"><span data-stu-id="bcf00-613">If 0, those messages will be suppressed.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-614">TrayVisibility</span><span class="sxs-lookup"><span data-stu-id="bcf00-614">TrayVisibility</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-615">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-615">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-616">預設 = 0</span><span class="sxs-lookup"><span data-stu-id="bcf00-616">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-617">0 = 在使用虛擬化應用程式時顯示盤匣。</span><span class="sxs-lookup"><span data-stu-id="bcf00-617">0=Show Tray when virtualized applications are in use.</span></span></p>
<p><span data-ttu-id="bcf00-618">1 = 顯示紙盒（總是）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-618">1=Show Tray always.</span></span></p>
<p><span data-ttu-id="bcf00-619">2 = 永不顯示紙盒。</span><span class="sxs-lookup"><span data-stu-id="bcf00-619">2=Never show Tray.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-620">TrayShowRefresh</span><span class="sxs-lookup"><span data-stu-id="bcf00-620">TrayShowRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-621">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-621">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="bcf00-622">當存在並設定為1值時，允許功能表項目重新整理應用程式顯示在工作列功能表上，且可供使用者存取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-622">When present and set to a value of 1, allows menu item Refresh Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-623">TrayShowLoad</span><span class="sxs-lookup"><span data-stu-id="bcf00-623">TrayShowLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-624">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-624">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="bcf00-625">當存在並設定為1值時，允許功能表項目載入應用程式顯示在工作列功能表上，且可供使用者存取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-625">When present and set to a value of 1, allows menu item Load Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-626">報告設定</span><span class="sxs-lookup"><span data-stu-id="bcf00-626">Reporting Settings</span></span>


<span data-ttu-id="bcf00-627">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting 鍵包含向 App-v 管理伺服器報告的特定值。</span><span class="sxs-lookup"><span data-stu-id="bcf00-627">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting key contains values specific to reporting to an App-V Management Server.</span></span> <span data-ttu-id="bcf00-628">下表提供與報告金鑰相關聯之註冊表值的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bcf00-628">The following table provides information about the registry values associated with the Reporting key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bcf00-629">名稱</span><span class="sxs-lookup"><span data-stu-id="bcf00-629">Name</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-630">類型</span><span class="sxs-lookup"><span data-stu-id="bcf00-630">Type</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-631">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="bcf00-631">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="bcf00-632">描述</span><span class="sxs-lookup"><span data-stu-id="bcf00-632">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bcf00-633">DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="bcf00-633">DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-634">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-634">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-635">預設值 = 20</span><span class="sxs-lookup"><span data-stu-id="bcf00-635">Default=20</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-636">此值指定要儲存報告資訊的 XML 快取大小上限（MB）。</span><span class="sxs-lookup"><span data-stu-id="bcf00-636">This value specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="bcf00-637">此大小會套用到記憶體中的快取。</span><span class="sxs-lookup"><span data-stu-id="bcf00-637">The size applies to the cache in memory.</span></span> <span data-ttu-id="bcf00-638">當達到限制時，記錄檔案將會滾過。</span><span class="sxs-lookup"><span data-stu-id="bcf00-638">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="bcf00-639">新增新記錄時（清單的底部），一或多個最舊的記錄（清單的頂端）將會被刪除，以留出空間。</span><span class="sxs-lookup"><span data-stu-id="bcf00-639">When a new record is added (bottom of the list), one or more of the oldest records (top of the list) will be deleted to make room.</span></span> <span data-ttu-id="bcf00-640">當您第一次發生此情況時，會在用戶端記錄和事件日誌中記錄一個警告，直到在傳輸成功清除快取且記錄再次填滿之後，才會再次記錄。</span><span class="sxs-lookup"><span data-stu-id="bcf00-640">A warning will be logged to the Client log and the event log the first time this occurs, and it will not be logged again until after the cache has been successfully cleared on transmission and the log has filled up again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bcf00-641">DataBlockSize</span><span class="sxs-lookup"><span data-stu-id="bcf00-641">DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-642">DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf00-642">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-643">預設 = 65536</span><span class="sxs-lookup"><span data-stu-id="bcf00-643">Default=65536</span></span></p></td>
<td align="left"><p><span data-ttu-id="bcf00-644">此值指定在發佈重新整理時，傳送到伺服器的最大大小（以位元組為單位），以避免在記錄達到巨大大小時永久傳輸失敗。</span><span class="sxs-lookup"><span data-stu-id="bcf00-644">This value specifies the maximum size in bytes to transmit to the server at once on publishing refresh, to avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="bcf00-645">預設值為65536。</span><span class="sxs-lookup"><span data-stu-id="bcf00-645">The default value is 65536.</span></span> <span data-ttu-id="bcf00-646">將報表資料傳送到伺服器時，應用程式記錄的一個區塊（小於或等於 XML 資料的組塊大小）會從快取中移除並傳送到伺服器。</span><span class="sxs-lookup"><span data-stu-id="bcf00-646">When transmitting report data to the server, one block of application records—less than or equal to the block size in bytes of XML data—will be removed from the cache and sent to the server.</span></span> <span data-ttu-id="bcf00-647">每個區塊都將會有一般用戶端資料和全域套件清單資料，且這些資料不會影響區塊大小計算。極大的封裝清單可能存在，導致無法透過低頻寬或不可靠的連線傳送失敗。</span><span class="sxs-lookup"><span data-stu-id="bcf00-647">Each block will have the general Client data and global package list data prepended, and these will not factor into the block size calculations; the potential exists for an extremely large package list to result in transmission failures over low bandwidth or unreliable connections.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="bcf00-648">相關主題</span><span class="sxs-lookup"><span data-stu-id="bcf00-648">Related topics</span></span>


[<span data-ttu-id="bcf00-649">Application Virtualization Client 參考資料</span><span class="sxs-lookup"><span data-stu-id="bcf00-649">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)









