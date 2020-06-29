---
title: 檢視 App-V Server 發佈中繼資料
description: 檢視 App-V Server 發佈中繼資料
author: dansimp
ms.assetid: 048dd42a-24d4-4cc4-81f6-7a919aadd9b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 304aa656de98a0c9d59f0a6166811ead911033ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800300"
---
# <span data-ttu-id="d8025-103">檢視 App-V Server 發佈中繼資料</span><span class="sxs-lookup"><span data-stu-id="d8025-103">Viewing App-V Server Publishing Metadata</span></span>


<span data-ttu-id="d8025-104">您可以使用此程式來查看發佈中繼資料，這可協助您解決與發佈相關的問題。</span><span class="sxs-lookup"><span data-stu-id="d8025-104">Use this procedure to view publishing metadata, which can help you resolve publishing-related issues.</span></span> <span data-ttu-id="d8025-105">您必須使用 App-v Management server 才能使用此程式。</span><span class="sxs-lookup"><span data-stu-id="d8025-105">You must be using the App-V Management server to use this procedure.</span></span>

<span data-ttu-id="d8025-106">本文包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d8025-106">This article contains the following information:</span></span>

-   [<span data-ttu-id="d8025-107">用於查看發佈中繼資料的 app-v 5.0 SP3 需求</span><span class="sxs-lookup"><span data-stu-id="d8025-107">App-V 5.0 SP3 requirements for viewing publishing metadata</span></span>](#bkmk-50sp3-reqs-pub-meta)

-   [<span data-ttu-id="d8025-108">用來查看發佈中繼資料的語法</span><span class="sxs-lookup"><span data-stu-id="d8025-108">Syntax to use for viewing publishing metadata</span></span>](#bkmk-syntax-view-pub-meta)

-   [<span data-ttu-id="d8025-109">用戶端作業系統與版本的查詢值</span><span class="sxs-lookup"><span data-stu-id="d8025-109">Query values for client operating system and version</span></span>](#bkmk-values-query-pub-meta)

-   [<span data-ttu-id="d8025-110">發佈中繼資料的定義</span><span class="sxs-lookup"><span data-stu-id="d8025-110">Definition of publishing metadata</span></span>](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-50sp3-reqs-pub-meta"></a><span data-ttu-id="d8025-111">用於查看發佈中繼資料的 app-v 5.0 SP3 需求</span><span class="sxs-lookup"><span data-stu-id="d8025-111">App-V 5.0 SP3 requirements for viewing publishing metadata</span></span>


<span data-ttu-id="d8025-112">在 App-V 5.0 SP3 中，當您查詢 app-v 發佈伺服器以取得中繼資料時，您必須在位址中提供下列值：</span><span class="sxs-lookup"><span data-stu-id="d8025-112">In App-V 5.0 SP3, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8025-113">值</span><span class="sxs-lookup"><span data-stu-id="d8025-113">Value</span></span></th>
<th align="left"><span data-ttu-id="d8025-114">其他詳細資料</span><span class="sxs-lookup"><span data-stu-id="d8025-114">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d8025-115">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="d8025-115">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8025-116">如果您省略 <strong> 查詢的 ClientVersion </strong> 參數，中繼資料會排除新的 APP-V 5.0 SP3 功能。</span><span class="sxs-lookup"><span data-stu-id="d8025-116">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the new App-V 5.0 SP3 features.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d8025-117">ClientOS</span><span class="sxs-lookup"><span data-stu-id="d8025-117">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d8025-118">您必須在順序套件時選取特定用戶端作業系統，才能提供這個值。</span><span class="sxs-lookup"><span data-stu-id="d8025-118">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="d8025-119">如果您選取 [預設（所有作業系統）]，請勿在查詢中指定這個值。</span><span class="sxs-lookup"><span data-stu-id="d8025-119">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="d8025-120">如果您在查詢中省略 <strong> ClientOS </strong> 參數，則只有已排序支援任何作業系統的套件才會出現在中繼資料中。</span><span class="sxs-lookup"><span data-stu-id="d8025-120">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a><span data-ttu-id="d8025-121">用於查看發佈中繼資料的查詢語法</span><span class="sxs-lookup"><span data-stu-id="d8025-121">Query syntax for viewing publishing metadata</span></span>


<span data-ttu-id="d8025-122">下表提供語法和查詢範例。</span><span class="sxs-lookup"><span data-stu-id="d8025-122">The following table provides the syntax and query examples.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8025-123">應用程式版本-V</span><span class="sxs-lookup"><span data-stu-id="d8025-123">Version of App-V</span></span></th>
<th align="left"><span data-ttu-id="d8025-124">查詢語法</span><span class="sxs-lookup"><span data-stu-id="d8025-124">Query syntax</span></span></th>
<th align="left"><span data-ttu-id="d8025-125">參數描述</span><span class="sxs-lookup"><span data-stu-id="d8025-125">Parameter descriptions</span></span></th>
<th align="left"><span data-ttu-id="d8025-126">範例</span><span class="sxs-lookup"><span data-stu-id="d8025-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-127">App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="d8025-127">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8025-128">參數</span><span class="sxs-lookup"><span data-stu-id="d8025-128">Parameter</span></span></th>
<th align="left"><span data-ttu-id="d8025-129">描述</span><span class="sxs-lookup"><span data-stu-id="d8025-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-130">&lt;PubServer&gt;</span><span class="sxs-lookup"><span data-stu-id="d8025-130">&lt;PubServer&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-131">App-v 發佈伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d8025-131">Name of the App-V Publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-132">&lt;發佈埠#&gt;</span><span class="sxs-lookup"><span data-stu-id="d8025-132">&lt;Publishing Port#&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-133">移植到您在設定發佈伺服器時定義的 App-v 發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="d8025-133">Port to the App-V Publishing server, which you defined when you configured the Publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-134">ClientVersion = &lt; AppvClientVersion&gt;</span><span class="sxs-lookup"><span data-stu-id="d8025-134">ClientVersion=&lt;AppvClientVersion&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-135">App-v 用戶端的版本。</span><span class="sxs-lookup"><span data-stu-id="d8025-135">Version of the App-V client.</span></span> <span data-ttu-id="d8025-136">請參閱下表以取得正確的值以供使用。</span><span class="sxs-lookup"><span data-stu-id="d8025-136">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-137">ClientOS = &lt; OSStringValue&gt;</span><span class="sxs-lookup"><span data-stu-id="d8025-137">ClientOS=&lt;OSStringValue&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-138">執行 App-V 用戶端的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="d8025-138">Operating system of the computer that is running the App-V client.</span></span> <span data-ttu-id="d8025-139">請參閱下表以取得正確的值以供使用。</span><span class="sxs-lookup"><span data-stu-id="d8025-139">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p><span data-ttu-id="d8025-140">若要從 App-v 用戶端取得發佈伺服器與埠號碼（HTTP:// &lt; PubServer &gt; ： &lt; 發佈埠 # &gt; ）的名稱，請查看 <strong> AppvPublishingServer PowerShell Cmdlet 的 URL 設定 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d8025-140">To get the name of the Publishing server and the port number (http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;) from the App-V Client, look at the URL configuration of the <strong>Get-AppvPublishingServer</strong> PowerShell cmdlet.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p><span data-ttu-id="d8025-141">在範例中：</span><span class="sxs-lookup"><span data-stu-id="d8025-141">In the example:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8025-142">名為 "pubsvr01" 的 Windows Server 2012 R2 會託管發佈服務。</span><span class="sxs-lookup"><span data-stu-id="d8025-142">A Windows Server 2012 R2 named “pubsvr01” hosts the Publishing service.</span></span></p></li>
<li><p><span data-ttu-id="d8025-143">Windows 用戶端為 Windows 8.1 64 位。</span><span class="sxs-lookup"><span data-stu-id="d8025-143">The Windows client is Windows 8.1 64-bit.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-144">App-v 5.0 透過 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="d8025-144">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong><span data-ttu-id="d8025-145">注意</span><span class="sxs-lookup"><span data-stu-id="d8025-145">Note</span></span></strong><br/><p><strong><span data-ttu-id="d8025-146"></strong> <strong> </strong> 只有在 app-v 5.0 SP3 中才支援 ClientVersion 和 ClientOS。</span><span class="sxs-lookup"><span data-stu-id="d8025-146">ClientVersion</strong> and <strong>ClientOS</strong> are supported only in App-V 5.0 SP3.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="d8025-147">請參閱 App-v 5.0 SP3 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d8025-147">See the information for App-V 5.0 SP3.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p><span data-ttu-id="d8025-148">在這個範例中，名為「pubsvr01」的 Windows Server 2012 R2 會託管管理和發佈服務。</span><span class="sxs-lookup"><span data-stu-id="d8025-148">In the example, A Windows Server 2012 R2 named “pubsvr01” hosts the Management and Publishing services.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a><span data-ttu-id="d8025-149">用戶端作業系統與版本的查詢值</span><span class="sxs-lookup"><span data-stu-id="d8025-149">Query values for client operating system and version</span></span>


<span data-ttu-id="d8025-150">在發佈中繼資料查詢中，輸入與您所使用之用戶端作業系統及版本相對應的字串值。</span><span class="sxs-lookup"><span data-stu-id="d8025-150">In your publishing metadata query, enter the string values that correspond to the client operating system and version that you’re using.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8025-151">作業系統</span><span class="sxs-lookup"><span data-stu-id="d8025-151">Operating system</span></span></th>
<th align="left"><span data-ttu-id="d8025-152">架構</span><span class="sxs-lookup"><span data-stu-id="d8025-152">Architecture</span></span></th>
<th align="left"><span data-ttu-id="d8025-153">操作字串字串值</span><span class="sxs-lookup"><span data-stu-id="d8025-153">Operating string string value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-154">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d8025-154">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-155">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-155">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-156">WindowsClient_6. 2_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-156">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-157">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d8025-157">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-158">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-158">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-159">WindowsClient_6. 2_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-159">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-160">Windows8</span><span class="sxs-lookup"><span data-stu-id="d8025-160">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-161">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-161">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-162">WindowsClient_6. 2_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-162">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-163">Windows8</span><span class="sxs-lookup"><span data-stu-id="d8025-163">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-164">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-164">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-165">WindowsClient_6. 2_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-165">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-166">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d8025-166">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-167">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-167">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-168">WindowsServer_6. 2_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-168">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-169">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d8025-169">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-170">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-170">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-171">WindowsServer_6. 2_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-171">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-172">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d8025-172">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-173">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-173">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-174">WindowsServer_6. 2_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-174">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-175">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d8025-175">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-176">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-176">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-177">WindowsServer_6. 2_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-177">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-178">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d8025-178">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-179">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-179">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-180">WindowsClient_6. 1_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-180">WindowsClient_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-181">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d8025-181">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-182">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-182">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-183">WindowsClient_6. 1_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-183">WindowsClient_6.1_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8025-184">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d8025-184">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-185">64 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-185">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-186">WindowsServer_6. 1_x64</span><span class="sxs-lookup"><span data-stu-id="d8025-186">WindowsServer_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8025-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d8025-187">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-188">32 位元</span><span class="sxs-lookup"><span data-stu-id="d8025-188">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8025-189">WindowsServer_6. 1_x86</span><span class="sxs-lookup"><span data-stu-id="d8025-189">WindowsServer_6.1_x86</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a><span data-ttu-id="d8025-190">發佈中繼資料的定義</span><span class="sxs-lookup"><span data-stu-id="d8025-190">Definition of publishing metadata</span></span>


<span data-ttu-id="d8025-191">當套件發佈至執行 App-v 用戶端的電腦時，會將中繼資料傳送至該電腦，指出要發佈哪些套件和連線組。</span><span class="sxs-lookup"><span data-stu-id="d8025-191">When packages are published to a computer that is running the App-V client, metadata is sent to that computer indicating which packages and connection groups are being published.</span></span> <span data-ttu-id="d8025-192">App-v 用戶端會針對下列兩個個別的要求進行：</span><span class="sxs-lookup"><span data-stu-id="d8025-192">The App-V Client makes two separate requests for the following:</span></span>

-   <span data-ttu-id="d8025-193">擁有用戶端電腦資格的套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="d8025-193">Packages and connection groups that are entitled to the client computer.</span></span>

-   <span data-ttu-id="d8025-194">擁有目前使用者資格的套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="d8025-194">Packages and connection groups that are entitled to the current user.</span></span>

<span data-ttu-id="d8025-195">發佈伺服器與管理伺服器進行通訊，以判斷申請者可以使用哪些套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="d8025-195">The Publishing server communicates with the Management server to determine which packages and connection groups are available to the requester.</span></span> <span data-ttu-id="d8025-196">發佈伺服器必須在管理伺服器上註冊，才能產生中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d8025-196">The Publishing server must be registered with the Management server in order for the metadata to be generated.</span></span>

<span data-ttu-id="d8025-197">您可以使用特定使用者或電腦內容中的查詢，在網際網路瀏覽器中查看每個要求的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d8025-197">You can view the metadata for each request in an Internet browser by using a query that is in the context of the specific user or computer.</span></span>






## <span data-ttu-id="d8025-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="d8025-198">Related topics</span></span>


[<span data-ttu-id="d8025-199">App-V 5.0 技術參考資訊</span><span class="sxs-lookup"><span data-stu-id="d8025-199">Technical Reference for App-V 5.0</span></span>](technical-reference-for-app-v-50.md)









