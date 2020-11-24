---
title: MBAM 2.5 支援的組態
description: MBAM 2.5 支援的組態
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 8ed7915e33c5e4735a7c58674ed5f7d6da8e9a06
ms.sourcegitcommit: 9087f0a1b5bd3f81a9b790d5e39fdf39c18a2411
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182925"
---
# <span data-ttu-id="dddef-103">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="dddef-103">MBAM 2.5 Supported Configurations</span></span>


<span data-ttu-id="dddef-104">您可以在獨立拓朴中或與 System Center Configuration Manager 整合 MBAM 的 Configuration Manager 整合拓撲中，執行 Microsoft BitLocker 管理和監控 (MBAM) 2.5。</span><span class="sxs-lookup"><span data-stu-id="dddef-104">You can run Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a Stand-alone topology or in a Configuration Manager Integration topology that integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="dddef-105">如果您在生產環境中針對其中一個拓撲使用建議的設定，MBAM 最多可支援 500000 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="dddef-105">If you use the recommended configuration for either topology in a production environment, MBAM supports up to 500,000 MBAM clients.</span></span> <span data-ttu-id="dddef-106">如需每個伺服器上針對每個拓朴設定的建議架構與功能的相關資訊，請參閱 [MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="dddef-106">For information about the recommended architecture and features that are configured on each server for each topology, see [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<span data-ttu-id="dddef-107">如需 Configuration Manager 整合拓朴專用的其他設定，請參閱 [MBAM 支援的 Configuration Manager 版本](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="dddef-107">For additional configurations that are specific to the Configuration Manager Integration topology, see [Versions of Configuration Manager that MBAM supports](#bkmk-cm-ramreqs).</span></span>

**<span data-ttu-id="dddef-108">注意</span><span class="sxs-lookup"><span data-stu-id="dddef-108">Note</span></span>**  
<span data-ttu-id="dddef-109">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="dddef-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="dddef-110">若要尋找您產品的支援時程表，請參閱 [支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="dddef-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="dddef-111">如需 Microsoft 支援週期原則的其他相關資訊，請參閱 [Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="dddef-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



## <span data-ttu-id="dddef-112">MBAM 支援的語言</span><span class="sxs-lookup"><span data-stu-id="dddef-112">MBAM Supported Languages</span></span>


<span data-ttu-id="dddef-113">下表顯示 MBAM 用戶端支援的語言 (，包括 Self-Service 入口網站) 以及 MBAM 2.5 和 MBAM 2.5 SP1 中的 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="dddef-113">The following tables show the languages that are supported for the MBAM Client (including the Self-Service Portal) and the MBAM Server in MBAM 2.5 and MBAM 2.5 SP1.</span></span>

**<span data-ttu-id="dddef-114">MBAM 2.5 SP1 中支援的語言：</span><span class="sxs-lookup"><span data-stu-id="dddef-114">Supported Languages in MBAM 2.5 SP1:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-115">用戶端語言</span><span class="sxs-lookup"><span data-stu-id="dddef-115">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="dddef-116">伺服器語言</span><span class="sxs-lookup"><span data-stu-id="dddef-116">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-117">捷克 (捷克共和國) cs CZ</span><span class="sxs-lookup"><span data-stu-id="dddef-117">Czech (Czech Republic) cs-CZ</span></span></p>
<p><span data-ttu-id="dddef-118">丹麥文 (丹麥) da-深</span><span class="sxs-lookup"><span data-stu-id="dddef-118">Danish (Denmark) da-DK</span></span></p>
<p><span data-ttu-id="dddef-119">荷蘭 (荷蘭) nl-nl&platform-NL-NL&PLATFORM</span><span class="sxs-lookup"><span data-stu-id="dddef-119">Dutch (Netherlands) nl-NL</span></span></p>
<p><span data-ttu-id="dddef-120">英文 (美國) en-us</span><span class="sxs-lookup"><span data-stu-id="dddef-120">English (United States) en-US</span></span></p>
<p><span data-ttu-id="dddef-121">芬蘭文 (芬蘭) fi</span><span class="sxs-lookup"><span data-stu-id="dddef-121">Finnish (Finland) fi-FI</span></span></p>
<p><span data-ttu-id="dddef-122">法文 (法國) fr-fr</span><span class="sxs-lookup"><span data-stu-id="dddef-122">French (France) fr-FR</span></span></p>
<p><span data-ttu-id="dddef-123">德國 () 取消 de</span><span class="sxs-lookup"><span data-stu-id="dddef-123">German (Germany) de-DE</span></span></p>
<p><span data-ttu-id="dddef-124">希臘文 (希臘) el-GR</span><span class="sxs-lookup"><span data-stu-id="dddef-124">Greek (Greece) el-GR</span></span></p>
<p><span data-ttu-id="dddef-125">匈牙利文 (匈牙利) hu</span><span class="sxs-lookup"><span data-stu-id="dddef-125">Hungarian (Hungary) hu-HU</span></span></p>
<p><span data-ttu-id="dddef-126">義大利文 () it</span><span class="sxs-lookup"><span data-stu-id="dddef-126">Italian (Italy) it-IT</span></span></p>
<p><span data-ttu-id="dddef-127">日文 (日本) ja</span><span class="sxs-lookup"><span data-stu-id="dddef-127">Japanese (Japan) ja-JP</span></span></p>
<p><span data-ttu-id="dddef-128">朝鮮 (韓國) ko-KR</span><span class="sxs-lookup"><span data-stu-id="dddef-128">Korean (Korea) ko-KR</span></span></p>
<p><span data-ttu-id="dddef-129">挪威文、博克瑪律文 (挪威) nb-否</span><span class="sxs-lookup"><span data-stu-id="dddef-129">Norwegian, Bokmål (Norway) nb-NO</span></span></p>
<p><span data-ttu-id="dddef-130">波蘭文 (波蘭) pl-PL</span><span class="sxs-lookup"><span data-stu-id="dddef-130">Polish (Poland) pl-PL</span></span></p>
<p><span data-ttu-id="dddef-131">葡萄牙文 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="dddef-131">Portuguese (Brazil) pt-BR</span></span></p>
<p><span data-ttu-id="dddef-132">葡萄牙文 (葡萄牙) pt</span><span class="sxs-lookup"><span data-stu-id="dddef-132">Portuguese (Portugal) pt-PT</span></span></p>
<p><span data-ttu-id="dddef-133">俄文 (俄羅斯) ru</span><span class="sxs-lookup"><span data-stu-id="dddef-133">Russian (Russia) ru-RU</span></span></p>
<p><span data-ttu-id="dddef-134">斯洛伐克文 (斯洛伐克) sk-SK</span><span class="sxs-lookup"><span data-stu-id="dddef-134">Slovak (Slovakia) sk-SK</span></span></p>
<p><span data-ttu-id="dddef-135">西班牙文 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="dddef-135">Spanish (Spain) es-ES</span></span></p>
<p><span data-ttu-id="dddef-136">瑞典文 (瑞典) sv-SE</span><span class="sxs-lookup"><span data-stu-id="dddef-136">Swedish (Sweden) sv-SE</span></span></p>
<p><span data-ttu-id="dddef-137">土耳其文 (土耳其) tr-TR</span><span class="sxs-lookup"><span data-stu-id="dddef-137">Turkish (Turkey) tr-TR</span></span></p>
<p><span data-ttu-id="dddef-138">斯洛維尼亞 (斯洛維尼亞) sl-SI</span><span class="sxs-lookup"><span data-stu-id="dddef-138">Slovenian (Slovenia) sl-SI</span></span></p>
<p><span data-ttu-id="dddef-139">簡體中文 (中國) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="dddef-139">Simplified Chinese (PRC) zh-CN</span></span></p>
<p><span data-ttu-id="dddef-140">繁體中文 (臺灣) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="dddef-140">Traditional Chinese (Taiwan) zh-TW</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dddef-141">英文 (美國) en-us</span><span class="sxs-lookup"><span data-stu-id="dddef-141">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="dddef-142">法文 (法國) fr-fr</span><span class="sxs-lookup"><span data-stu-id="dddef-142">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="dddef-143">德國 () 取消 de</span><span class="sxs-lookup"><span data-stu-id="dddef-143">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="dddef-144">義大利文 () it</span><span class="sxs-lookup"><span data-stu-id="dddef-144">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="dddef-145">日文 (日本) ja</span><span class="sxs-lookup"><span data-stu-id="dddef-145">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="dddef-146">朝鮮 (韓國) ko-KR</span><span class="sxs-lookup"><span data-stu-id="dddef-146">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="dddef-147">葡萄牙文 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="dddef-147">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="dddef-148">俄文 (俄羅斯) ru</span><span class="sxs-lookup"><span data-stu-id="dddef-148">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="dddef-149">西班牙文 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="dddef-149">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="dddef-150">簡體中文 (中國) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="dddef-150">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="dddef-151">繁體中文 (臺灣) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="dddef-151">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="dddef-152">MBAM 2.5 中支援的語言：</span><span class="sxs-lookup"><span data-stu-id="dddef-152">Supported Languages in MBAM 2.5:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-153">用戶端語言</span><span class="sxs-lookup"><span data-stu-id="dddef-153">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="dddef-154">伺服器語言</span><span class="sxs-lookup"><span data-stu-id="dddef-154">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="dddef-155">英文 (美國) en-us</span><span class="sxs-lookup"><span data-stu-id="dddef-155">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="dddef-156">法文 (法國) fr-fr</span><span class="sxs-lookup"><span data-stu-id="dddef-156">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="dddef-157">德國 () 取消 de</span><span class="sxs-lookup"><span data-stu-id="dddef-157">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="dddef-158">義大利文 () it</span><span class="sxs-lookup"><span data-stu-id="dddef-158">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="dddef-159">日文 (日本) ja</span><span class="sxs-lookup"><span data-stu-id="dddef-159">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="dddef-160">朝鮮 (韓國) ko-KR</span><span class="sxs-lookup"><span data-stu-id="dddef-160">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="dddef-161">葡萄牙文 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="dddef-161">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="dddef-162">俄文 (俄羅斯) ru</span><span class="sxs-lookup"><span data-stu-id="dddef-162">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="dddef-163">西班牙文 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="dddef-163">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="dddef-164">簡體中文 (中國) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="dddef-164">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="dddef-165">繁體中文 (臺灣) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="dddef-165">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="dddef-166">英文 (美國) en-us</span><span class="sxs-lookup"><span data-stu-id="dddef-166">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="dddef-167">法文 (法國) fr-fr</span><span class="sxs-lookup"><span data-stu-id="dddef-167">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="dddef-168">德國 () 取消 de</span><span class="sxs-lookup"><span data-stu-id="dddef-168">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="dddef-169">義大利文 () it</span><span class="sxs-lookup"><span data-stu-id="dddef-169">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="dddef-170">日文 (日本) ja</span><span class="sxs-lookup"><span data-stu-id="dddef-170">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="dddef-171">朝鮮 (韓國) ko-KR</span><span class="sxs-lookup"><span data-stu-id="dddef-171">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="dddef-172">葡萄牙文 (巴西) pt-BR</span><span class="sxs-lookup"><span data-stu-id="dddef-172">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="dddef-173">俄文 (俄羅斯) ru</span><span class="sxs-lookup"><span data-stu-id="dddef-173">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="dddef-174">西班牙文 (西班牙) es</span><span class="sxs-lookup"><span data-stu-id="dddef-174">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="dddef-175">簡體中文 (中國) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="dddef-175">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="dddef-176">繁體中文 (臺灣) zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="dddef-176">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="dddef-177">MBAM 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="dddef-177">MBAM Server system requirements</span></span>


### <span data-ttu-id="dddef-178">MBAM 伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="dddef-178">MBAM Server operating system requirements</span></span>

<span data-ttu-id="dddef-179">我們強烈建議您在相同的作業系統上執行 MBAM 用戶端和 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="dddef-179">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="dddef-180">例如，windows 10 與 Windows Server 2016、Windows 8.1 （具備 Windows Server 2012 R2 等）。</span><span class="sxs-lookup"><span data-stu-id="dddef-180">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="dddef-181">下表列出 MBAM 伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="dddef-181">The following table lists the operating systems that are supported for the MBAM Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-182">作業系統</span><span class="sxs-lookup"><span data-stu-id="dddef-182">Operating system</span></span></th>
<th align="left"><span data-ttu-id="dddef-183">版本</span><span class="sxs-lookup"><span data-stu-id="dddef-183">Edition</span></span></th>
<th align="left"><span data-ttu-id="dddef-184">Service pack</span><span class="sxs-lookup"><span data-stu-id="dddef-184">Service pack</span></span></th>
<th align="left"><span data-ttu-id="dddef-185">系統架構</span><span class="sxs-lookup"><span data-stu-id="dddef-185">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-186">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dddef-186">Windows Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-187">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-187">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="dddef-188">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-189">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="dddef-189">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-190">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-190">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="dddef-191">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-191">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-192">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dddef-192">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-193">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-193">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-194">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-194">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dddef-195">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-196">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-196">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="dddef-197">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-197">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-198">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dddef-198">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-199">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-199">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-200">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-200">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-201">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-201">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="dddef-202">企業網域必須包含至少一個 Windows Server 2008 (或更新版本，才能) 網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="dddef-202">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span>

### <a href="" id="bkmk-stand-alone-ramreqs"></a><span data-ttu-id="dddef-203">MBAM 伺服器處理器、RAM 與磁碟空間需求-獨立拓朴</span><span class="sxs-lookup"><span data-stu-id="dddef-203">MBAM Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="dddef-204">這些需求適用于 MBAM 獨立拓撲。</span><span class="sxs-lookup"><span data-stu-id="dddef-204">These requirements are for the MBAM Stand-alone topology.</span></span> <span data-ttu-id="dddef-205">如需 Configuration Manager 整合拓朴的需求，請參閱 [MBAM 伺服器處理器、RAM 和磁碟空間需求-Configuration Manager 整合拓撲](#bkmk-cm-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="dddef-205">For the requirements for the Configuration Manager Integration topology, see [MBAM Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-206">硬體專案</span><span class="sxs-lookup"><span data-stu-id="dddef-206">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="dddef-207">最低需求</span><span class="sxs-lookup"><span data-stu-id="dddef-207">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="dddef-208">建議的需求</span><span class="sxs-lookup"><span data-stu-id="dddef-208">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-209">處理器</span><span class="sxs-lookup"><span data-stu-id="dddef-209">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-210">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="dddef-210">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-211">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="dddef-211">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-212">RAM</span><span class="sxs-lookup"><span data-stu-id="dddef-212">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-213">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-214">12 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-214">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-215">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="dddef-215">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-216">1 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-216">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-217">2 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-217">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-ramreqs"></a><span data-ttu-id="dddef-218">MBAM 伺服器處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="dddef-218">MBAM Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="dddef-219">下表列出當您使用 Configuration Manager 整合拓撲時，MBAM 伺服器的伺服器處理器、RAM 和磁碟空間需求。</span><span class="sxs-lookup"><span data-stu-id="dddef-219">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span> <span data-ttu-id="dddef-220">如需獨立拓朴的需求，請參閱 [MBAM 伺服器處理器、RAM 和磁碟空間需求-獨立拓朴](#bkmk-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="dddef-220">For the requirements for the Stand-alone topology, see [MBAM Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-221">硬體專案</span><span class="sxs-lookup"><span data-stu-id="dddef-221">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="dddef-222">最低需求</span><span class="sxs-lookup"><span data-stu-id="dddef-222">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="dddef-223">建議的需求</span><span class="sxs-lookup"><span data-stu-id="dddef-223">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-224">處理器</span><span class="sxs-lookup"><span data-stu-id="dddef-224">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-225">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="dddef-225">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-226">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="dddef-226">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-227">RAM</span><span class="sxs-lookup"><span data-stu-id="dddef-227">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-228">4 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-228">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-229">8 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-229">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-230">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="dddef-230">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-231">1 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-231">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-232">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a><span data-ttu-id="dddef-233">MBAM 支援的 Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="dddef-233">Versions of Configuration Manager that MBAM supports</span></span>

<span data-ttu-id="dddef-234">MBAM 支援下列 Configuration Manager 版本。</span><span class="sxs-lookup"><span data-stu-id="dddef-234">MBAM supports the following versions of Configuration Manager.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-235">支援的版本</span><span class="sxs-lookup"><span data-stu-id="dddef-235">Supported version</span></span></th>
<th align="left"><span data-ttu-id="dddef-236">Service pack</span><span class="sxs-lookup"><span data-stu-id="dddef-236">Service pack</span></span></th>
<th align="left"><span data-ttu-id="dddef-237">系統架構</span><span class="sxs-lookup"><span data-stu-id="dddef-237">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-238">Microsoft System Center Configuration Manager (目前的分支) ，最多1902個版本</span><span class="sxs-lookup"><span data-stu-id="dddef-238">Microsoft System Center Configuration Manager (Current Branch), versions up to 1902</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-239">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-239">64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-240">Microsoft System Center Configuration Manager 1806</span><span class="sxs-lookup"><span data-stu-id="dddef-240">Microsoft System Center Configuration Manager 1806</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-241">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-241">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-242">Microsoft System Center Configuration Manager (LTSB-版本 1606) </span><span class="sxs-lookup"><span data-stu-id="dddef-242">Microsoft System Center Configuration Manager (LTSB - version 1606)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-243">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-243">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-244">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dddef-244">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-245">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-245">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-246">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-246">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-247">Microsoft System Center Configuration Manager 2007 R2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dddef-247">Microsoft System Center Configuration Manager 2007 R2 or later</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-248">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-248">64-bit</span></span></p>

<span data-ttu-id="dddef-249">&gt;<strong>注意 </strong> 雖然 Configuration Manager 2007 R2 是32位，您必須將它與 SQL Server 安裝在64位作業系統上，才能符合64位 MBAM 軟體。</span><span class="sxs-lookup"><span data-stu-id="dddef-249">&gt;<strong>Note</strong> Although Configuration Manager 2007 R2 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span>
</td>
</tr>
</tbody>
</table>



<span data-ttu-id="dddef-250">如需 Configuration Manager 伺服器支援的設定的清單，請參閱適用于您所使用之 Configuration Manager 版本的相關 TechNet 檔。</span><span class="sxs-lookup"><span data-stu-id="dddef-250">For a list of supported configurations for the Configuration Manager Server, see the appropriate TechNet documentation for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="dddef-251">MBAM 對於 Configuration Manager 伺服器沒有額外的系統需求。</span><span class="sxs-lookup"><span data-stu-id="dddef-251">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="dddef-252">SQL Server 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="dddef-252">SQL Server database requirements</span></span>

<span data-ttu-id="dddef-253">下表列出 MBAM 伺服器功能支援的 Microsoft SQL Server 版本，其中包含復原資料庫、合規性和審核資料庫，以及 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="dddef-253">The following table lists the Microsoft SQL Server versions that are supported for the MBAM Server features, which include the Recovery Database, Compliance and Audit Database, and the Reports feature.</span></span> <span data-ttu-id="dddef-254">所需版本適用于獨立版或 Configuration Manager 整合拓撲。</span><span class="sxs-lookup"><span data-stu-id="dddef-254">The required versions apply to the Stand-alone or the Configuration Manager Integration topologies.</span></span>

<span data-ttu-id="dddef-255">您必須安裝 sql Server，並使用 **sql \ _Latin1 \ _General \ _CP1 \ _CI \ _AS** 排序。</span><span class="sxs-lookup"><span data-stu-id="dddef-255">You must install SQL Server with the **SQL\_Latin1\_General\_CP1\_CI\_AS** collation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-256">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="dddef-256">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="dddef-257">版本</span><span class="sxs-lookup"><span data-stu-id="dddef-257">Edition</span></span></th>
<th align="left"><span data-ttu-id="dddef-258">Service pack</span><span class="sxs-lookup"><span data-stu-id="dddef-258">Service pack</span></span></th>
<th align="left"><span data-ttu-id="dddef-259">系統架構</span><span class="sxs-lookup"><span data-stu-id="dddef-259">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-260">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="dddef-260">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-261">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-261">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-262">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-262">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="dddef-263">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="dddef-263">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-264">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-264">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-265">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-265">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="dddef-266">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="dddef-266">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-267">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-267">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-268">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-268">SP1</span></span></p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p><span data-ttu-id="dddef-269">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-269">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-270">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="dddef-270">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-271">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-271">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-272">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="dddef-272">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-273">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-273">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-274">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="dddef-274">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-275">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-275">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-276">SP3</span><span class="sxs-lookup"><span data-stu-id="dddef-276">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-277">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-277">64-bit</span></span></p></td>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-278">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dddef-278">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-279">Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dddef-279">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-280">SP3</span><span class="sxs-lookup"><span data-stu-id="dddef-280">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-281">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-281">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

**<span data-ttu-id="dddef-282">注意</span><span class="sxs-lookup"><span data-stu-id="dddef-282">Note</span></span>**  
<span data-ttu-id="dddef-283">MBAM 具有最高支援的相容性等級140。</span><span class="sxs-lookup"><span data-stu-id="dddef-283">MBAM has a maximum supported compatibility level of 140.</span></span> <span data-ttu-id="dddef-284">在 SQL Server 2019 上建立之新資料庫的預設相容性等級是150，必須在建立資料庫之後，使用 ALTER DATABASE 命令，將其變更為140或小寫。</span><span class="sxs-lookup"><span data-stu-id="dddef-284">The default compatibility level for new databases created on SQL Server 2019 is 150 which will need to be altered to 140 or lower, using the ALTER DATABASE command, after the database has been created.</span></span> <span data-ttu-id="dddef-285">從 SQL server 2017 或以下物件遷移的現有資料庫將會保持在其先前的相容性層級，且不需要變更。</span><span class="sxs-lookup"><span data-stu-id="dddef-285">Existing databases migrated from SQL server 2017 or below will remain at their previous compatibility level and do not need to be altered.</span></span>

<span data-ttu-id="dddef-286">為了支援 SQL 2016，您必須安裝 MDOP 年 3 2017 月的服務版本 https://www.microsoft.com/download/details.aspx?id=54967  ，並支援 sql 2017 您必須安裝2017年 7 2018 月的服務發行 https://www.microsoft.com/download/details.aspx?id=57157 。</span><span class="sxs-lookup"><span data-stu-id="dddef-286">In order to support SQL 2016 you must install the March 2017 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=54967  and to support SQL 2017 you must install the July 2018 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=57157.</span></span> <span data-ttu-id="dddef-287">一般來說，只要使用最新的服務更新，就能一直保持在最新狀態，因為它也包含所有 bugfixes 和新功能。</span><span class="sxs-lookup"><span data-stu-id="dddef-287">In general stay current by always using the most recent servicing update as it also includes all bugfixes and new features.</span></span>


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a><span data-ttu-id="dddef-288">SQL Server 處理器、RAM 與磁碟空間需求–獨立拓朴</span><span class="sxs-lookup"><span data-stu-id="dddef-288">SQL Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="dddef-289">下表列出當您使用獨立拓撲時，在 SQL Server 電腦上建議的伺服器處理器、RAM 和磁碟空間需求。</span><span class="sxs-lookup"><span data-stu-id="dddef-289">The following table lists the recommended server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Stand-alone topology.</span></span> <span data-ttu-id="dddef-290">使用這些需求做為指南。</span><span class="sxs-lookup"><span data-stu-id="dddef-290">Use these requirements as a guide.</span></span> <span data-ttu-id="dddef-291">您的特定需求會根據您在企業中支援的用戶端電腦數量而有所不同。</span><span class="sxs-lookup"><span data-stu-id="dddef-291">Your specific requirements will vary based on the number of client computers you are supporting in your enterprise.</span></span> <span data-ttu-id="dddef-292">若要查看 Configuration Manager 整合拓撲的需求，請參閱 [SQL Server 處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲](#bkmk-cm-sql-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="dddef-292">To view the requirements for the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-sql-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-293">硬體專案</span><span class="sxs-lookup"><span data-stu-id="dddef-293">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="dddef-294">最低需求</span><span class="sxs-lookup"><span data-stu-id="dddef-294">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="dddef-295">建議的需求</span><span class="sxs-lookup"><span data-stu-id="dddef-295">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-296">處理器</span><span class="sxs-lookup"><span data-stu-id="dddef-296">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-297">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="dddef-297">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-298">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="dddef-298">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-299">RAM</span><span class="sxs-lookup"><span data-stu-id="dddef-299">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-300">8 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-300">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-301">12 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-301">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-302">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="dddef-302">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-303">5 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-303">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-304">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="dddef-304">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-sql-ramreqs"></a><span data-ttu-id="dddef-305">SQL Server 處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="dddef-305">SQL Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="dddef-306">下表列出當您使用 Configuration Manager 整合拓撲時，Microsoft SQL Server 電腦的伺服器處理器、RAM 與磁碟空間需求，請參閱 [SQL Server 處理器、RAM 和磁碟空間需求–獨立拓撲](#bkmk-sql-stand-alone-ramreqs)。</span><span class="sxs-lookup"><span data-stu-id="dddef-306">The following table lists the server processor, RAM, and disk space requirements for the Microsoft SQL Server computer when you are using the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-sql-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-307">硬體專案</span><span class="sxs-lookup"><span data-stu-id="dddef-307">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="dddef-308">最低需求</span><span class="sxs-lookup"><span data-stu-id="dddef-308">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="dddef-309">建議的需求</span><span class="sxs-lookup"><span data-stu-id="dddef-309">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-310">處理器</span><span class="sxs-lookup"><span data-stu-id="dddef-310">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-311">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="dddef-311">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-312">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="dddef-312">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-313">RAM</span><span class="sxs-lookup"><span data-stu-id="dddef-313">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-314">4 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-314">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-315">8 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-315">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-316">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="dddef-316">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-317">5 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-317">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-318">5 GB</span><span class="sxs-lookup"><span data-stu-id="dddef-318">5 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="dddef-319">MBAM 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="dddef-319">MBAM Client system requirements</span></span>


### <span data-ttu-id="dddef-320">用戶端作業系統需求</span><span class="sxs-lookup"><span data-stu-id="dddef-320">Client operating system requirements</span></span>

<span data-ttu-id="dddef-321">我們強烈建議您在相同的作業系統上執行 MBAM 用戶端和 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="dddef-321">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="dddef-322">例如，windows 10 與 Windows Server 2016、Windows 8.1 （具備 Windows Server 2012 R2 等）。</span><span class="sxs-lookup"><span data-stu-id="dddef-322">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="dddef-323">下表列出 MBAM 用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="dddef-323">The following table lists the operating systems that are supported for MBAM Client installation.</span></span> <span data-ttu-id="dddef-324">在獨立與 Configuration Manager 整合拓朴中，相同的需求同樣適用。</span><span class="sxs-lookup"><span data-stu-id="dddef-324">The same requirements apply to the Stand-alone and the Configuration Manager Integration topologies.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-325">作業系統</span><span class="sxs-lookup"><span data-stu-id="dddef-325">Operating system</span></span></th>
<th align="left"><span data-ttu-id="dddef-326">版本</span><span class="sxs-lookup"><span data-stu-id="dddef-326">Edition</span></span></th>
<th align="left"><span data-ttu-id="dddef-327">Service pack</span><span class="sxs-lookup"><span data-stu-id="dddef-327">Service pack</span></span></th>
<th align="left"><span data-ttu-id="dddef-328">系統架構</span><span class="sxs-lookup"><span data-stu-id="dddef-328">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
    <td align="left"><p><span data-ttu-id="dddef-329">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="dddef-329">Windows 10 IoT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="dddef-330">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-330">Enterprise</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p><span data-ttu-id="dddef-331">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-331">32-bit or 64-bit</span></span></p></td>
</tr><br/><tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-332">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dddef-332">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-333">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-333">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-334">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-334">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-335">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="dddef-335">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-336">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-336">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-337">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-337">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-338">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dddef-338">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-339">企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="dddef-339">Enterprise or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-340">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-340">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-341">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-341">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-342">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="dddef-342">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-343">Windows 8.1 和 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="dddef-343">Windows 8.1 and Windows 10 Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-344">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-344">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="dddef-345">用戶端 RAM 需求</span><span class="sxs-lookup"><span data-stu-id="dddef-345">Client RAM requirements</span></span>

<span data-ttu-id="dddef-346">不是 MBAM 用戶端安裝所特有的 RAM 需求。</span><span class="sxs-lookup"><span data-stu-id="dddef-346">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="dddef-347">MBAM 群組原則系統需求</span><span class="sxs-lookup"><span data-stu-id="dddef-347">MBAM Group Policy system requirements</span></span>


<span data-ttu-id="dddef-348">下表列出 MBAM 群組原則範本安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="dddef-348">The following table lists the operating systems that are supported for MBAM Group Policy Templates installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dddef-349">作業系統</span><span class="sxs-lookup"><span data-stu-id="dddef-349">Operating system</span></span></th>
<th align="left"><span data-ttu-id="dddef-350">版本</span><span class="sxs-lookup"><span data-stu-id="dddef-350">Edition</span></span></th>
<th align="left"><span data-ttu-id="dddef-351">Service pack</span><span class="sxs-lookup"><span data-stu-id="dddef-351">Service pack</span></span></th>
<th align="left"><span data-ttu-id="dddef-352">系統架構</span><span class="sxs-lookup"><span data-stu-id="dddef-352">System architecture</span></span></th>
</tr>
</thead>
<tbody>
 <tr class="even">
      <td align="left"><p><span data-ttu-id="dddef-353">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="dddef-353">Windows 10 IoT</span></span></p></td>
      <td align="left"><p><span data-ttu-id="dddef-354">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-354">Enterprise</span></span></p></td>
      <td align="left"><p></p></td>
      <td align="left"><p><span data-ttu-id="dddef-355">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-355">32-bit or 64-bit</span></span></p></td>
 </tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-356">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dddef-356">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-357">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-357">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-358">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-358">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-359">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="dddef-359">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-360">企業</span><span class="sxs-lookup"><span data-stu-id="dddef-360">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-361">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-361">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-362">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dddef-362">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-363">企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="dddef-363">Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-364">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-364">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-365">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-365">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-366">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dddef-366">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-367">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-367">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-368">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-368">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dddef-369">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dddef-369">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-370">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-370">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="dddef-371">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-371">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dddef-372">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dddef-372">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-373">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="dddef-373">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-374">SP1</span><span class="sxs-lookup"><span data-stu-id="dddef-374">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dddef-375">64 位元</span><span class="sxs-lookup"><span data-stu-id="dddef-375">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="dddef-376">Azure IaaS 中的 MBAM</span><span class="sxs-lookup"><span data-stu-id="dddef-376">MBAM In Azure IaaS</span></span>

<span data-ttu-id="dddef-377">您可以在 Azure 基礎結構中，將 MBAM 伺服器部署為服務 (IaaS) 在上述任何支援的作業系統版本上，連線到託管于內部部署的 Active Directory，或是託管在 Azure IaaS 中的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="dddef-377">The MBAM server can be deployed in Azure Infrastructure as a Service (IaaS) on any of the supported OS versions listed above, connecting to an Active Directory hosted on premises or an Active Directory also hosted in Azure IaaS.</span></span>  <span data-ttu-id="dddef-378">在 Azure IaaS 上設定和設定 Active Directory 的檔在 [這裡](https://msdn.microsoft.com/library/azure/jj156090.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dddef-378">Documentation for setting up and configuring Active Directory on Azure IaaS is [here](https://msdn.microsoft.com/library/azure/jj156090.aspx).</span></span>

<span data-ttu-id="dddef-379">虛擬機器不支援 MBAM 用戶端，但在 Azure IaaS 上也不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="dddef-379">The MBAM client is not supported on virtual machines and is also not supported on Azure IaaS.</span></span>


## <span data-ttu-id="dddef-380">服務版本</span><span class="sxs-lookup"><span data-stu-id="dddef-380">Service releases</span></span> 

- [<span data-ttu-id="dddef-381">2016年4月的修補程式</span><span class="sxs-lookup"><span data-stu-id="dddef-381">April 2016 hotfix</span></span>](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="dddef-382">2016年9月</span><span class="sxs-lookup"><span data-stu-id="dddef-382">September 2016</span></span>](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [<span data-ttu-id="dddef-383">2016 年 12 月</span><span class="sxs-lookup"><span data-stu-id="dddef-383">December 2016</span></span>](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [<span data-ttu-id="dddef-384">2017 年 3 月</span><span class="sxs-lookup"><span data-stu-id="dddef-384">March 2017</span></span>](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [<span data-ttu-id="dddef-385">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="dddef-385">June 2017</span></span>](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="dddef-386">2017 年 9 月</span><span class="sxs-lookup"><span data-stu-id="dddef-386">September 2017</span></span>](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [<span data-ttu-id="dddef-387">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="dddef-387">March 2018</span></span>](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="dddef-388">2018年7月</span><span class="sxs-lookup"><span data-stu-id="dddef-388">July 2018</span></span>](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="dddef-389">2019年5月</span><span class="sxs-lookup"><span data-stu-id="dddef-389">May 2019</span></span>](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## <span data-ttu-id="dddef-390">相關主題</span><span class="sxs-lookup"><span data-stu-id="dddef-390">Related topics</span></span>


[<span data-ttu-id="dddef-391">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="dddef-391">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="dddef-392">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="dddef-392">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)




## <span data-ttu-id="dddef-393">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="dddef-393">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="dddef-394">在 [此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="dddef-394">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="dddef-395">如需 MBAM 問題，請使用 [MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="dddef-395">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




