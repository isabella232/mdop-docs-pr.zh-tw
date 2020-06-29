---
title: Application Virtualization Client 安裝程式命令列參數
description: Application Virtualization Client 安裝程式命令列參數
author: dansimp
ms.assetid: 508fa404-52a5-4919-8788-2a3dfb00639b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 911d333c80060c1881c96430c1d2d0516b6a4855
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802329"
---
# <span data-ttu-id="c50c3-103">Application Virtualization Client 安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="c50c3-103">Application Virtualization Client Installer Command-Line Parameters</span></span>


<span data-ttu-id="c50c3-104">下表列出所有可用的 Microsoft Application Virtualization 用戶端安裝程式命令列參數、其值，以及每個參數的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="c50c3-104">The following table lists all available Microsoft Application Virtualization Client installer command-line parameters, their values, and a brief description of each parameter.</span></span> <span data-ttu-id="c50c3-105">參數區分大小寫，且必須以全大寫字母輸入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-105">Parameters are case-sensitive and must be entered as all-uppercase letters.</span></span> <span data-ttu-id="c50c3-106">所有參數值都必須以雙引號括住。</span><span class="sxs-lookup"><span data-stu-id="c50c3-106">All parameter values must be enclosed in double quotes.</span></span>

**<span data-ttu-id="c50c3-107">注意</span><span class="sxs-lookup"><span data-stu-id="c50c3-107">Note</span></span>**  
-   <span data-ttu-id="c50c3-108">在 App-v 4.6 版中，在用戶端升級期間無法使用命令列參數。</span><span class="sxs-lookup"><span data-stu-id="c50c3-108">For App-V version 4.6, command-line parameters cannot be used during a client upgrade.</span></span>

-   <span data-ttu-id="c50c3-109">在命令列上不能結合*SWICACHESIZE*和*MINFREESPACEMB*參數。</span><span class="sxs-lookup"><span data-stu-id="c50c3-109">The *SWICACHESIZE* and *MINFREESPACEMB* parameters cannot be combined on the command line.</span></span> <span data-ttu-id="c50c3-110">如果同時使用兩者，則會忽略*SWICACHESIZE*參數。</span><span class="sxs-lookup"><span data-stu-id="c50c3-110">If both are used, the *SWICACHESIZE* parameter will be ignored.</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c50c3-111">參數</span><span class="sxs-lookup"><span data-stu-id="c50c3-111">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c50c3-112">相對值</span><span class="sxs-lookup"><span data-stu-id="c50c3-112">Values</span></span></th>
<th align="left"><span data-ttu-id="c50c3-113">描述</span><span class="sxs-lookup"><span data-stu-id="c50c3-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-114">ALLOWINDEPENDENTFILESTREAMING</span><span class="sxs-lookup"><span data-stu-id="c50c3-114">ALLOWINDEPENDENTFILESTREAMING</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-115">TRUE</span><span class="sxs-lookup"><span data-stu-id="c50c3-115">TRUE</span></span></p>
<p><span data-ttu-id="c50c3-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="c50c3-116">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-117">指示是否要啟用來自檔案的資料流程，不論用戶端是否已使用 <em> APPLICATIONSOURCEROOT 參數進行設定 </em> 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-117">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the <em>APPLICATIONSOURCEROOT</em> parameter.</span></span> <span data-ttu-id="c50c3-118">如果設定為 FALSE，即使 OSD HREF 或 <em> APPLICATIONSOURCEROOT 參數包含檔案路徑，傳輸也不會啟用檔案的資料流程 </em> 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-118">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the <em>APPLICATIONSOURCEROOT</em> parameter contains a file path.</span></span></p>
<p><span data-ttu-id="c50c3-119">可能的值：</span><span class="sxs-lookup"><span data-stu-id="c50c3-119">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-120">TRUE-可能會從磁片載入手動部署的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-120">TRUE—Manually deployed application may be loaded from disk.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-121">FALSE-所有應用程式都必須來自來來源資料流伺服器。</span><span class="sxs-lookup"><span data-stu-id="c50c3-121">FALSE—All applications must come from source streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-122">APPLICATIONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="c50c3-122">APPLICATIONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-123">RTSP:// <em> URL </em> （適用于動態套件傳遞）</span><span class="sxs-lookup"><span data-stu-id="c50c3-123">RTSP:// <em>URL</em> (for dynamic package delivery)</span></span></p>
<p><span data-ttu-id="c50c3-124">File:// <em> URL </em> 或 <em> UNC </em> （從檔案套件傳送中載入）</span><span class="sxs-lookup"><span data-stu-id="c50c3-124">File:// <em>URL</em> or <em>UNC</em> (for load from file package delivery)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-125">若要啟用系統管理員或電子軟體發佈系統，以確保應用程式載入與拓撲管理配置相容，可以覆寫應用程式 HREF 元素的 OSD 基本代碼（來源位置）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-125">To enable an administrator or an electronic software distribution system to ensure that application loading is performed in compliance with the topology management scheme, allows an override of the OSD CODEBASE for the application HREF element (the source location).</span></span> <span data-ttu-id="c50c3-126">如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</span><span class="sxs-lookup"><span data-stu-id="c50c3-126">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="c50c3-127">URL 有數個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-127">A URL has several parts:</span></span></p>
<p><span data-ttu-id="c50c3-128">&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-128">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="c50c3-129">UNC 路徑有三個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-129">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="c50c3-130">&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-130">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<p><span data-ttu-id="c50c3-131">如果 <em> APPLICATIONSOURCEROOT </em> 參數是在用戶端上指定，用戶端會將來自 OSD 檔案的 URL 或 UNC 路徑中斷到其構成元件，並將 osd 區段取代為對應的 <em> APPLICATIONSOURCEROOT </em> 區段。</span><span class="sxs-lookup"><span data-stu-id="c50c3-131">If the <em>APPLICATIONSOURCEROOT</em> parameter is specified on a client, the client will break the URL or UNC path from an OSD file into its constituent parts and replace the OSD sections with the corresponding <em>APPLICATIONSOURCEROOT</em> sections.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-132">重要</span><span class="sxs-lookup"><span data-stu-id="c50c3-132">Important</span></span></strong><br/><p><span data-ttu-id="c50c3-133">在搭配 UNC 路徑使用 file://時，請務必使用正確的格式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-133">Be sure to use the correct format when using file:// with a UNC path.</span></span> <span data-ttu-id="c50c3-134">正確的格式是 file://[lt]; [ &amp; 伺服器 &gt; &amp; lt; share] &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-134">The correct format is file://&amp;lt;server&gt;&amp;lt;share&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-135">ICONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="c50c3-135">ICONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="c50c3-136">UNC</span><span class="sxs-lookup"><span data-stu-id="c50c3-136">UNC</span></span></em></p>
<p><span data-ttu-id="c50c3-137">HTTP:// <em> url </em> 或 HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="c50c3-137">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-138">可讓系統管理員在發佈期間指定已排序之應用程式套件的圖示檢索來源位置。</span><span class="sxs-lookup"><span data-stu-id="c50c3-138">Enables an administrator to specify a source location for icon retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="c50c3-139">圖示來源根支援 UNC 路徑和 Url （HTTP 或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-139">Icon source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="c50c3-140">如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</span><span class="sxs-lookup"><span data-stu-id="c50c3-140">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="c50c3-141">URL 有數個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-141">A URL has several parts:</span></span></p>
<p><span data-ttu-id="c50c3-142">&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-142">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="c50c3-143">UNC 路徑有三個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-143">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="c50c3-144">&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-144">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-145">重要</span><span class="sxs-lookup"><span data-stu-id="c50c3-145">Important</span></span></strong><br/><p><span data-ttu-id="c50c3-146">使用 UNC 路徑時，請務必使用正確的格式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-146">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="c50c3-147">可接受的格式為 &amp; lt; server &gt; &amp; lt; share &gt; 或 &lt; drive 字母 &gt; ： &amp; lt; 資料夾 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-147">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-148">OSDSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="c50c3-148">OSDSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="c50c3-149">UNC</span><span class="sxs-lookup"><span data-stu-id="c50c3-149">UNC</span></span></em></p>
<p><span data-ttu-id="c50c3-150">HTTP:// <em> url </em> 或 HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="c50c3-150">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-151">讓系統管理員在發佈期間指定應用程式套件的 OSD 檔案檢索源位置。</span><span class="sxs-lookup"><span data-stu-id="c50c3-151">Enables an administrator to specify a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="c50c3-152">OSD 來源根支援 UNC 路徑和 Url （HTTP 或 HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-152">OSD source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="c50c3-153">如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</span><span class="sxs-lookup"><span data-stu-id="c50c3-153">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="c50c3-154">URL 有數個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-154">A URL has several parts:</span></span></p>
<p><span data-ttu-id="c50c3-155">&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-155">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="c50c3-156">UNC 路徑有三個部分：</span><span class="sxs-lookup"><span data-stu-id="c50c3-156">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="c50c3-157">&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-157">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-158">重要</span><span class="sxs-lookup"><span data-stu-id="c50c3-158">Important</span></span></strong><br/><p><span data-ttu-id="c50c3-159">使用 UNC 路徑時，請務必使用正確的格式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-159">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="c50c3-160">可接受的格式為 &amp; lt; server &gt; &amp; lt; share &gt; 或 &lt; drive 字母 &gt; ： &amp; lt; 資料夾 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-160">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-161">AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="c50c3-161">AUTOLOADONLOGIN</span></span></em></p>
<p><em><span data-ttu-id="c50c3-162">AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="c50c3-162">AUTOLOADONLAUNCH</span></span></em></p>
<p><em><span data-ttu-id="c50c3-163">AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="c50c3-163">AUTOLOADONREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-164">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="c50c3-164">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-165">AutoLoad 觸發程式，定義啟動自動載入應用程式的事件。</span><span class="sxs-lookup"><span data-stu-id="c50c3-165">The AutoLoad triggers that define the events that initiate auto-loading of applications.</span></span> <span data-ttu-id="c50c3-166">AutoLoad 會隱式使用背景資料流程，讓應用程式完全載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="c50c3-166">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span></p>
<p><span data-ttu-id="c50c3-167">將會儘快載入主要功能區塊。</span><span class="sxs-lookup"><span data-stu-id="c50c3-167">The primary feature block will be loaded as quickly as possible.</span></span> <span data-ttu-id="c50c3-168">剩餘的功能區塊會在背景中載入，以啟用前景作業，例如使用者與應用程式互動、取得優先順序，以及提供最佳效能。</span><span class="sxs-lookup"><span data-stu-id="c50c3-168">Remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take priority and provide optimal performance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-169">注意</span><span class="sxs-lookup"><span data-stu-id="c50c3-169">Note</span></span></strong><br/><p><span data-ttu-id="c50c3-170"><em>AUTOLOADTARGET </em> 參數會決定自動載入哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-170">The <em>AUTOLOADTARGET</em> parameter determines which applications are auto-loaded.</span></span> <span data-ttu-id="c50c3-171">根據預設，已使用的套件會自動載入（除非 <em> </em> 已設定 AUTOLOADTARGET）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-171">By default, packages that have been used are auto-loaded unless <em>AUTOLOADTARGET</em> is set.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="c50c3-172">每個參數都會影響載入行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c50c3-172">Each parameter affects loading behavior as follows:</span></span></p>
<ul>
<li><p><em><span data-ttu-id="c50c3-173">AUTOLOADONLOGIN </em> -在使用者登入時開始載入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-173">AUTOLOADONLOGIN</em>—Loading starts when the user logs in.</span></span></p></li>
<li><p><em><span data-ttu-id="c50c3-174">AUTOLOADONLAUNCH </em> -當使用者開始使用應用程式時，就會開始載入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-174">AUTOLOADONLAUNCH</em>—Loading starts when the user starts an application.</span></span></p></li>
<li><p><em><span data-ttu-id="c50c3-175">AUTOLOADONREFRESH </em> -在進行發佈更新時開始載入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-175">AUTOLOADONREFRESH</em>—Loading starts when a publishing refresh occurs.</span></span></p></li>
</ul>
<p><span data-ttu-id="c50c3-176">這三個值可以結合。</span><span class="sxs-lookup"><span data-stu-id="c50c3-176">The three values can be combined.</span></span> <span data-ttu-id="c50c3-177">在下列範例中，使用者登入和發佈重新整理時會啟用 AutoLoad 觸發程式：</span><span class="sxs-lookup"><span data-stu-id="c50c3-177">In the following example, AutoLoad triggers are enabled both at user login and when publishing refresh occurs:</span></span></p>
<p><em><span data-ttu-id="c50c3-178">AUTOLOADONLOGIN AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="c50c3-178">AUTOLOADONLOGIN AUTOLOADONREFRESH</span></span></em></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-179">注意</span><span class="sxs-lookup"><span data-stu-id="c50c3-179">Note</span></span></strong><br/><p><span data-ttu-id="c50c3-180">如果在第一次安裝時會將用戶端設定為使用這些值，則在使用者下次登入並重新登入時，就不會觸發 Autoload。</span><span class="sxs-lookup"><span data-stu-id="c50c3-180">If the client is configured with these values at first install, Autoload will not be triggered until the next time the user logs off and logs back on.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-181">AUTOLOADTARGET</span><span class="sxs-lookup"><span data-stu-id="c50c3-181">AUTOLOADTARGET</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-182">所有</span><span class="sxs-lookup"><span data-stu-id="c50c3-182">NONE</span></span></p>
<p><span data-ttu-id="c50c3-183">同時</span><span class="sxs-lookup"><span data-stu-id="c50c3-183">ALL</span></span></p>
<p><span data-ttu-id="c50c3-184">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="c50c3-184">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-185">指示在任何指定的 AutoLoad 觸發程式發生時，將會自動載入哪些內容。</span><span class="sxs-lookup"><span data-stu-id="c50c3-185">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span></p>
<p><span data-ttu-id="c50c3-186">可能的值：</span><span class="sxs-lookup"><span data-stu-id="c50c3-186">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-187">無：不會自動載入，不論可能會設定哪些觸發程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-187">NONE—No auto-loading, regardless of what triggers might be set.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-188">[全部]-如果已啟用任何 AutoLoad 觸發程式，則會自動載入所有套件，不論它們是否曾啟動。</span><span class="sxs-lookup"><span data-stu-id="c50c3-188">ALL—If any AutoLoad trigger is enabled, all packages are automatically loaded, whether or not they have ever been launched.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-189">注意</span><span class="sxs-lookup"><span data-stu-id="c50c3-189">Note</span></span></strong><br/><p><span data-ttu-id="c50c3-190">此設定是使用 SFTMIME [ <strong> 新增套件] </strong> 並 <strong> 設定套件命令來針對個別套件進行設定 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-190">This setting is configured for individual packages by using the SFTMIME <strong>ADD PACKAGE</strong> and <strong>CONFIGURE PACKAGE</strong> commands.</span></span> <span data-ttu-id="c50c3-191">如需這些命令的詳細資訊，請參閱 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> SFTMIME 命令參考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-191">For more information about these commands, see <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)">SFTMIME Command Reference</a>.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="c50c3-192">PREVUSED-如果已啟用任何 AutoLoad 觸發程式，請只載入套件中以前使用過的套件（亦即啟動或 precached）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-192">PREVUSED—If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used (that is, launched or precached).</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="c50c3-193">注意</span><span class="sxs-lookup"><span data-stu-id="c50c3-193">Note</span></span></strong><br/><p><span data-ttu-id="c50c3-194">當您安裝 App-V 用戶端以使用唯讀快取（例如，作為 VDI 伺服器實現）時，您必須將 <em> AUTOLOADTARGET </em> 參數設定為 NONE，以免用戶端嘗試更新唯讀快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-194">When you install the App-V client to use a read-only cache, (for example, as a VDI server implementation), you must set the <em>AUTOLOADTARGET</em> parameter to NONE to prevent the client from trying to update applications in the read-only cache.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-195">DOTIMEOUTMINUTES</span><span class="sxs-lookup"><span data-stu-id="c50c3-195">DOTIMEOUTMINUTES</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-196">29600（預設值）</span><span class="sxs-lookup"><span data-stu-id="c50c3-196">29600 (default)</span></span></p>
<p><span data-ttu-id="c50c3-197">1–1439998560分鐘（範圍）</span><span class="sxs-lookup"><span data-stu-id="c50c3-197">1–1439998560 minutes (range)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-198">指出應用程式在中斷式作業中可使用的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="c50c3-198">Indicates how many minutes an application may be used in disconnected operation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-199">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="c50c3-199">INSTALLDIR</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-200">&lt;pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="c50c3-200">&lt;pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-201">指定 App-V 用戶端的安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="c50c3-201">Specifies the installation directory of the App-V Client.</span></span></p>
<p><span data-ttu-id="c50c3-202">範例： INSTALLDIR = &quot; C:\Program Files\Microsoft 應用程式虛擬化用戶端&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-202">Example: INSTALLDIR=&quot;C:\Program Files\Microsoft Application Virtualization Client&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-203">OPTIN</span><span class="sxs-lookup"><span data-stu-id="c50c3-203">OPTIN</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-204">滿足</span><span class="sxs-lookup"><span data-stu-id="c50c3-204">“TRUE”</span></span></p>
<p><span data-ttu-id="c50c3-205">“”</span><span class="sxs-lookup"><span data-stu-id="c50c3-205">“”</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-206">當您將更新提供給一般公用時，microsoft 應用程式虛擬化用戶端元件會透過 Microsoft Update 進行升級。</span><span class="sxs-lookup"><span data-stu-id="c50c3-206">Microsoft Application Virtualization Client components will be upgradable through Microsoft Update when updates are made available to the general public.</span></span> <span data-ttu-id="c50c3-207">在 Windows 作業系統上安裝的 Microsoft Update 代理程式要求使用者明確選擇使用該服務。</span><span class="sxs-lookup"><span data-stu-id="c50c3-207">The Microsoft Update Agent installed on Windows operating systems requires a user to explicitly opt-in to use the service.</span></span> <span data-ttu-id="c50c3-208">針對裝置上的所有應用程式，此自願加入只需要一次。</span><span class="sxs-lookup"><span data-stu-id="c50c3-208">This opt-in is required only one time for all applications on the device.</span></span> <span data-ttu-id="c50c3-209">如果您已加入宣告 Microsoft Update，裝置上的 Microsoft 應用程式虛擬化元件將會自動利用該服務。</span><span class="sxs-lookup"><span data-stu-id="c50c3-209">If you have already opted into Microsoft Update, the Microsoft Application Virtualization components on the device will automatically take advantage of the service.</span></span></p>
<p><span data-ttu-id="c50c3-210">針對命令列安裝，使用 Microsoft Update 是預設退出宣告（除非前一個應用程式已啟用裝置），因為您需要手動加入宣告 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="c50c3-210">For command-line installation, use of Microsoft Update is by default opt-out (unless a previous application already enabled the device to be opted in) due to the requirement for manually opting into Microsoft Update.</span></span> <span data-ttu-id="c50c3-211">因此，在命令列安裝中，選擇 [加入] 必須是明確的。</span><span class="sxs-lookup"><span data-stu-id="c50c3-211">Therefore, opting in must be explicit for command-line installations.</span></span> <span data-ttu-id="c50c3-212">將命令列參數 OPTIN 設定 <em> </em> 為 TRUE，就會強制設定 Microsoft Update 自願加入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-212">Setting the command-line parameter <em>OPTIN</em> to TRUE forces the Microsoft Update opt-in to be set.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-213">REQUIREAUTHORIZATIONIFCACHED</span><span class="sxs-lookup"><span data-stu-id="c50c3-213">REQUIREAUTHORIZATIONIFCACHED</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-214">TRUE</span><span class="sxs-lookup"><span data-stu-id="c50c3-214">TRUE</span></span></p>
<p><span data-ttu-id="c50c3-215">FALSE</span><span class="sxs-lookup"><span data-stu-id="c50c3-215">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-216">指出是否總是需要授權（無論是否已在快取中有應用程式）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-216">Indicates whether authorization is always required, whether or not an application is already in cache.</span></span></p>
<p><span data-ttu-id="c50c3-217">可能的值：</span><span class="sxs-lookup"><span data-stu-id="c50c3-217">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-218">TRUE-應用程式永遠必須在啟動時授權。</span><span class="sxs-lookup"><span data-stu-id="c50c3-218">TRUE—Application always must be authorized at startup.</span></span> <span data-ttu-id="c50c3-219">針對 RTSP 流程式應用程式，會將使用者授權權杖傳送到伺服器以進行授權。</span><span class="sxs-lookup"><span data-stu-id="c50c3-219">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="c50c3-220">對於以檔案為基礎的應用程式，檔案 Acl 會指示使用者是否可以存取應用程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-220">For file-based applications, file ACLs dictate whether a user may access the application.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-221">FALSE —請務必連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="c50c3-221">FALSE—Always try to connect to the server.</span></span> <span data-ttu-id="c50c3-222">如果無法建立伺服器連線，用戶端仍可讓使用者啟動先前載入到快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c50c3-222">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-223">SWICACHESIZE</span><span class="sxs-lookup"><span data-stu-id="c50c3-223">SWICACHESIZE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-224">快取記憶體大小（MB）</span><span class="sxs-lookup"><span data-stu-id="c50c3-224">Cache size in MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-225">指定用戶端快取的大小（以 mb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-225">Specifies the size in megabytes of the client cache.</span></span> <span data-ttu-id="c50c3-226">預設大小為 4096 MB，最大大小為 1048576 MB （1 TB）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-226">The default size is 4096 MB, and the maximum size is 1,048,576 MB (1 TB).</span></span> <span data-ttu-id="c50c3-227">系統會在安裝時檢查可用的空間，但不保留空間。</span><span class="sxs-lookup"><span data-stu-id="c50c3-227">The system checks for the available space at installation time, but the space is not reserved.</span></span></p>
<p><span data-ttu-id="c50c3-228">範例： <strong> SWICACHESIZE = &quot; 1024&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-228">Example: <strong>SWICACHESIZE=&quot;1024&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-229">SWIPUBSVRDISPLAY</span><span class="sxs-lookup"><span data-stu-id="c50c3-229">SWIPUBSVRDISPLAY</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-230">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c50c3-230">Display name</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-231">指定發佈伺服器的顯示名稱;<em>使用 SWIPUBSVRHOST 時 </em> 是必要的。</span><span class="sxs-lookup"><span data-stu-id="c50c3-231">Specifies the displayed name of the publishing server; required when <em>SWIPUBSVRHOST</em> is used.</span></span></p>
<p><span data-ttu-id="c50c3-232">範例： <strong> SWIPUBSVRDISPLAY = &quot; 生產環境&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-232">Example: <strong>SWIPUBSVRDISPLAY=&quot;PRODUCTION ENVIRONMENT&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-233">SWIPUBSVRTYPE</span><span class="sxs-lookup"><span data-stu-id="c50c3-233">SWIPUBSVRTYPE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-234">[HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="c50c3-234">[HTTP|RTSP]</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-235">指定發佈伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="c50c3-235">Specifies the publishing server type.</span></span> <span data-ttu-id="c50c3-236">預設伺服器類型是 Application Virtualization 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c50c3-236">The default server type is Application Virtualization Server.</span></span> <span data-ttu-id="c50c3-237"><strong>/Secure </strong> 開關不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="c50c3-237">The <strong>/secure</strong> switch is not case sensitive.</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-238">HTTP-標準 HTTP 伺服器</span><span class="sxs-lookup"><span data-stu-id="c50c3-238">HTTP—Standard HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="c50c3-239">HTTP <strong> /secure </strong> -增強的安全性 HTTP 伺服器</span><span class="sxs-lookup"><span data-stu-id="c50c3-239">HTTP <strong>/secure</strong>—Enhanced Security HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="c50c3-240">RTSP-應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="c50c3-240">RTSP—Application Virtualization Server</span></span></p></li>
<li><p><span data-ttu-id="c50c3-241">RTSP <strong> /secure </strong> -增強的安全性應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="c50c3-241">RTSP <strong>/secure</strong>—Enhanced Security Application Virtualization Server</span></span></p></li>
</ul>
<p><span data-ttu-id="c50c3-242">範例： <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-242">Example: <strong>SWIPUBSVRTYPE=&quot;HTTP /secure&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-243">SWIPUBSVRHOST</span><span class="sxs-lookup"><span data-stu-id="c50c3-243">SWIPUBSVRHOST</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-244">IP 位址 | 主機名稱</span><span class="sxs-lookup"><span data-stu-id="c50c3-244">IP address|host name</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-245">指定應用程式虛擬化伺服器的 IP 位址，或伺服器的主機名稱（可解析成伺服器&#39;s IP 位址）;<em>使用 SWIPUBSVRDISPLAY 時 </em> 是必要的。</span><span class="sxs-lookup"><span data-stu-id="c50c3-245">Specifies either the IP address of the Application Virtualization Server or a host name of the server that resolves into the server&#39;s IP address; required when <em>SWIPUBSVRDISPLAY</em> is used.</span></span></p>
<p><span data-ttu-id="c50c3-246">範例： <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-246">Example: <strong>SWIPUBSVRHOST=&quot;SERVER01&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-247">SWIPUBSVRPORT</span><span class="sxs-lookup"><span data-stu-id="c50c3-247">SWIPUBSVRPORT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-248">埠號碼</span><span class="sxs-lookup"><span data-stu-id="c50c3-248">Port number</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-249">指定此應用程式虛擬化伺服器用來偵聽用戶端要求的邏輯埠（default = 554）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-249">Specifies the logical port that is used by this Application Virtualization Server to listen for requests from the client (default = 554).</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-250">標準 HTTP 伺服器—預設 = 80。</span><span class="sxs-lookup"><span data-stu-id="c50c3-250">Standard HTTP server—Default = 80.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-251">增強的安全性 HTTP 伺服器（預設 = 443）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-251">Enhanced Security HTTP Server—Default = 443.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-252">應用程式虛擬化伺服器—預設 = 554。</span><span class="sxs-lookup"><span data-stu-id="c50c3-252">Application Virtualization Server—Default = 554.</span></span></p></li>
<li><p><span data-ttu-id="c50c3-253">增強型安全性應用程式虛擬化伺服器—預設 = 322。</span><span class="sxs-lookup"><span data-stu-id="c50c3-253">Enhanced Security Application Virtualization Server—Default = 322.</span></span></p></li>
</ul>
<p><span data-ttu-id="c50c3-254">範例： <strong> SWIPUBSVRPORT = &quot; 443&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-254">Example: <strong>SWIPUBSVRPORT=&quot;443&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-255">SWIPUBSVRPATH</span><span class="sxs-lookup"><span data-stu-id="c50c3-255">SWIPUBSVRPATH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-256">路徑名稱</span><span class="sxs-lookup"><span data-stu-id="c50c3-256">Path name</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-257">指定檔案發佈伺服器上定義檔案類型關聯的位置（預設 =/）;在 <em> SWIPUBSVRTYPE </em> 參數值為 HTTP 時是必要的。</span><span class="sxs-lookup"><span data-stu-id="c50c3-257">Specifies the location on the publishing server of the file that defines file type associations (default = /); required when the <em>SWIPUBSVRTYPE</em> parameter value is HTTP.</span></span></p>
<p><span data-ttu-id="c50c3-258">範例： <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-258">Example: <strong>SWIPUBSVRPATH=&quot;/AppVirt/appsntypes.xml&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-259">SWIPUBSVRREFRESH</span><span class="sxs-lookup"><span data-stu-id="c50c3-259">SWIPUBSVRREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-260">[開啟 |出</span><span class="sxs-lookup"><span data-stu-id="c50c3-260">[ON|OFF]</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-261">指定當使用者登入用戶端時，用戶端是否會自動查詢檔案類型關聯和應用程式的發佈伺服器（預設 = 開啟）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-261">Specifies whether the client automatically queries the publishing server for file type associations and applications when a user logs in to the client (default = ON).</span></span></p>
<p><span data-ttu-id="c50c3-262">範例： <strong> SWIPUBSVRREFRESH = &quot; off&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-262">Example: <strong>SWIPUBSVRREFRESH=&quot;off&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-263">SWIGLOBALDATA</span><span class="sxs-lookup"><span data-stu-id="c50c3-263">SWIGLOBALDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-264">全域資料目錄</span><span class="sxs-lookup"><span data-stu-id="c50c3-264">Global data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-265">指定要儲存資料的目錄，而不是特定的使用者（預設 = C:\Documents 和 Settings\All Users\Documents）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-265">Specifies the directory where data will be stored that is not specific to particular users (default = C:\Documents and Settings\All Users\Documents).</span></span></p>
<p><span data-ttu-id="c50c3-266">範例： <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-266">Example: <strong>SWIGLOBALDATA=&quot;D:\Microsoft Application Virtualization Client\Global&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-267">SWIUSERDATA</span><span class="sxs-lookup"><span data-stu-id="c50c3-267">SWIUSERDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-268">使用者資料目錄</span><span class="sxs-lookup"><span data-stu-id="c50c3-268">User data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-269">指定將儲存特定使用者專用之資料的目錄（預設值 =% APPDATA%）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-269">Specifies the directory where data will be stored that is specific to particular users (default = %APPDATA%).</span></span></p>
<p><span data-ttu-id="c50c3-270">範例： <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization 用戶端&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-270">Example: <strong>SWIUSERDATA=&quot;H:\Windows\Microsoft Application Virtualization Client&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-271">SWIFSDRIVE</span><span class="sxs-lookup"><span data-stu-id="c50c3-271">SWIFSDRIVE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-272">首選的磁片磁碟機號</span><span class="sxs-lookup"><span data-stu-id="c50c3-272">Preferred drive letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-273">對應至您針對虛擬磁片磁碟機所選取的磁片磁碟機字母。</span><span class="sxs-lookup"><span data-stu-id="c50c3-273">Corresponds to the drive letter that you selected for the virtual drive.</span></span></p>
<p><span data-ttu-id="c50c3-274">範例： <strong> SWIFSDRIVE = &quot; S&quot;</span><span class="sxs-lookup"><span data-stu-id="c50c3-274">Example: <strong>SWIFSDRIVE=&quot;S&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-275">SYSTEMEVENTLOGLEVEL</span><span class="sxs-lookup"><span data-stu-id="c50c3-275">SYSTEMEVENTLOGLEVEL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-276">0–4</span><span class="sxs-lookup"><span data-stu-id="c50c3-276">0–4</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-277">指出記錄層級，日誌訊息會寫入 NT 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="c50c3-277">Indicates the logging level at which log messages are written to the NT event Log.</span></span> <span data-ttu-id="c50c3-278">此值表示記錄的閾值，也就是等於或小於該值的所有專案都會登入。</span><span class="sxs-lookup"><span data-stu-id="c50c3-278">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="c50c3-279">例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-279">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="c50c3-280">可能的值：</span><span class="sxs-lookup"><span data-stu-id="c50c3-280">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="c50c3-281">0 = = 無</span><span class="sxs-lookup"><span data-stu-id="c50c3-281">0 == None</span></span></p></li>
<li><p><span data-ttu-id="c50c3-282">1 = = 臨界</span><span class="sxs-lookup"><span data-stu-id="c50c3-282">1 == Critical</span></span></p></li>
<li><p><span data-ttu-id="c50c3-283">2 = = 錯誤</span><span class="sxs-lookup"><span data-stu-id="c50c3-283">2 == Error</span></span></p></li>
<li><p><span data-ttu-id="c50c3-284">3 = = 警告</span><span class="sxs-lookup"><span data-stu-id="c50c3-284">3 == Warning</span></span></p></li>
<li><p><span data-ttu-id="c50c3-285">4 = = 資訊</span><span class="sxs-lookup"><span data-stu-id="c50c3-285">4 == Information</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="c50c3-286">MINFREESPACEMB</span><span class="sxs-lookup"><span data-stu-id="c50c3-286">MINFREESPACEMB</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-287">以 MB 為單位</span><span class="sxs-lookup"><span data-stu-id="c50c3-287">In MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-288">指定在快取大小增加前，在主機上必須提供的可用空間大小（mb）。</span><span class="sxs-lookup"><span data-stu-id="c50c3-288">Specifies the amount of free space (in megabytes) that must be available on the host before the cache size can increase.</span></span> <span data-ttu-id="c50c3-289">下列範例會將用戶端設定為確保磁片上至少有 5 GB 的可用空間，才能讓快取的大小增加。</span><span class="sxs-lookup"><span data-stu-id="c50c3-289">The following example would configure the client to ensure at least 5 GB of free space on the disk before allowing the size of the cache to increase.</span></span> <span data-ttu-id="c50c3-290">在安裝時，磁片上的可用磁碟空間大小預設為 5000 MB。</span><span class="sxs-lookup"><span data-stu-id="c50c3-290">The default is 5000 MB of free space available on disk at installation time.</span></span></p>
<p><span data-ttu-id="c50c3-291">範例： <strong> MINFREESPACEMB = &quot; 5000 &quot; （5 GB）</span><span class="sxs-lookup"><span data-stu-id="c50c3-291">Example: <strong>MINFREESPACEMB =&quot;5000&quot; (5 GB)</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="c50c3-292">KEEPCURRENTSETTINGS</span><span class="sxs-lookup"><span data-stu-id="c50c3-292">KEEPCURRENTSETTINGS</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="c50c3-293">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="c50c3-293">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="c50c3-294">在部署用戶端之前（例如使用群組原則），在您已套用完登錄設定的情況下使用。</span><span class="sxs-lookup"><span data-stu-id="c50c3-294">Used when you have applied registry settings prior to deploying a client—for example, by using Group Policy.</span></span> <span data-ttu-id="c50c3-295">部署用戶端時，請將此參數設定為1的值，這樣就不會覆寫註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="c50c3-295">When a client is deployed, set this parameter to a value of 1 so that it will not overwrite the registry settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="c50c3-296">重要</span><span class="sxs-lookup"><span data-stu-id="c50c3-296">Important</span></span></strong><br/><p><span data-ttu-id="c50c3-297">如果設定為值1，則會忽略下列用戶端安裝程式命令列參數：</span><span class="sxs-lookup"><span data-stu-id="c50c3-297">If set to a value of 1, the following client installer command-line parameters are ignored:</span></span></p>
<p><strong><span data-ttu-id="c50c3-298">SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT </strong> 、 <strong> ICONSOURCEROOT </strong> 、 <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA、、、、、和。</span><span class="sxs-lookup"><span data-stu-id="c50c3-298">SWICACHESIZE</strong>, <strong>MINFREESPACEMB</strong>, <strong>ALLOWINDEPENDENTFILESTREAMING</strong>, <strong>APPLICATIONSOURCEROOT</strong>, <strong>ICONSOURCEROOT</strong>, <strong>OSDSOURCEROOT</strong>, <strong>SYSTEMEVENTLOGLEVEL</strong>, <strong>SWIGLOBALDATA</strong>, <strong>DOTIMEOUTMINUTES</strong>, <strong>SWIFSDRIVE</strong>, <strong>AUTOLOADTARGET</strong>, <strong>AUTOLOADTRIGGERS</strong>, and <strong>SWIUSERDATA</strong>.</span></span></p>
<p><span data-ttu-id="c50c3-299">如需在安裝後設定這些值的進一步資訊，請參閱在應用程式虛擬化（App-v）操作指南（）中的「如何使用命令列來設定 App-v Client Registry 設定」 <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c50c3-299">For further information about setting these values after installation, see “How to Configure the App-V Client Registry Settings by Using the Command Line” in the Application Virtualization (App-V) Operations Guide (<a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)">https://go.microsoft.com/fwlink/?LinkId=122939</a>).</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="c50c3-300">相關主題</span><span class="sxs-lookup"><span data-stu-id="c50c3-300">Related topics</span></span>


[<span data-ttu-id="c50c3-301">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="c50c3-301">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="c50c3-302">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="c50c3-302">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="c50c3-303">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="c50c3-303">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)









