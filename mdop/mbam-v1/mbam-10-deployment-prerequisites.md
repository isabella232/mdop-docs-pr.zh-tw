---
title: MBAM 1.0 部署必要條件
description: MBAM 1.0 部署必要條件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809489"
---
# <span data-ttu-id="9171c-103">MBAM 1.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="9171c-103">MBAM 1.0 Deployment Prerequisites</span></span>


<span data-ttu-id="9171c-104">開始進行 Microsoft BitLocker 管理與監視（MBAM）安裝之前，請確定您符合安裝產品所需的先決條件。</span><span class="sxs-lookup"><span data-stu-id="9171c-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you meet the necessary prerequisites to install the product.</span></span> <span data-ttu-id="9171c-105">本節包含的資訊可協助您在部署 MBAM 用戶端和伺服器功能之前成功準備您的計算環境。</span><span class="sxs-lookup"><span data-stu-id="9171c-105">This section contains information to help you successfully prepare your computing environment before you deploy the MBAM Clients and Server features.</span></span>

## <span data-ttu-id="9171c-106">MBAM Server 功能的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-106">Installation prerequisites for MBAM Server features</span></span>


<span data-ttu-id="9171c-107">每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。</span><span class="sxs-lookup"><span data-stu-id="9171c-107">Each of the MBAM server features has specific prerequisites that must be met before they can be successfully installed.</span></span> <span data-ttu-id="9171c-108">MBAM 安裝程式會在安裝開始前驗證是否已滿足所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="9171c-108">MBAM Setup verifies if all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="9171c-109">管理和監視伺服器的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-109">Installation prerequisites for Administration and Monitoring Server</span></span>

<span data-ttu-id="9171c-110">下表包含 MBAM 管理和監視伺服器的安裝先決條件：</span><span class="sxs-lookup"><span data-stu-id="9171c-110">The following table contains the installation prerequisites for the MBAM Administration and Monitoring Server:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9171c-111">必備</span><span class="sxs-lookup"><span data-stu-id="9171c-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="9171c-112">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9171c-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9171c-113">Windows ServerWeb 服務器角色</span><span class="sxs-lookup"><span data-stu-id="9171c-113">Windows ServerWeb Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9171c-114">這個角色必須新增至 mbam 系統管理和監視伺服器功能支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="9171c-114">This role must be added to a server operating system supported for the mbam Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9171c-115">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="9171c-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9171c-116">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="9171c-116">IIS Management Scripts and Tools</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9171c-117">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="9171c-117">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9171c-118">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="9171c-118">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="9171c-119">靜態內容</span><span class="sxs-lookup"><span data-stu-id="9171c-119">Static Content</span></span></p></li>
<li><p><span data-ttu-id="9171c-120">預設檔</span><span class="sxs-lookup"><span data-stu-id="9171c-120">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="9171c-121">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="9171c-121">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="9171c-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9171c-122">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="9171c-123">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="9171c-123">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="9171c-124">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="9171c-124">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="9171c-125">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="9171c-125">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="9171c-126">安全性</span><span class="sxs-lookup"><span data-stu-id="9171c-126">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="9171c-127">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="9171c-127">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="9171c-128">要求篩選</span><span class="sxs-lookup"><span data-stu-id="9171c-128">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9171c-129">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="9171c-129">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9171c-130">Microsoft .NET Framework 3.5.1 功能：</span><span class="sxs-lookup"><span data-stu-id="9171c-130">Microsoft .NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="9171c-131">.NET Framework 3.5。1</span><span class="sxs-lookup"><span data-stu-id="9171c-131">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="9171c-132">WCF 啟用</span><span class="sxs-lookup"><span data-stu-id="9171c-132">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="9171c-133">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="9171c-133">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="9171c-134">非 HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="9171c-134">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="9171c-135">Windows 處理序啟用服務</span><span class="sxs-lookup"><span data-stu-id="9171c-135">Windows Process Activation Service</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="9171c-136">處理模型</span><span class="sxs-lookup"><span data-stu-id="9171c-136">Process Model</span></span></p></li>
<li><p><span data-ttu-id="9171c-137">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="9171c-137">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="9171c-138">配置 Api</span><span class="sxs-lookup"><span data-stu-id="9171c-138">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9171c-139">**記事** 如需支援的作業系統清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="9171c-139">**Note** For a list of supported operating systems, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="9171c-140">合規性和審核報告的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-140">Installation prerequisites for the Compliance and Audit Reports</span></span>

<span data-ttu-id="9171c-141">合規性和審核報告必須安裝在支援的 SQLServer 版本上。</span><span class="sxs-lookup"><span data-stu-id="9171c-141">The Compliance and Audit Reports must be installed on a supported version of SQLServer.</span></span> <span data-ttu-id="9171c-142">此功能的安裝先決條件包括 SQL Server Reporting Services （SSRS）。</span><span class="sxs-lookup"><span data-stu-id="9171c-142">Installation prerequisites for this feature include SQL Server Reporting Services (SSRS).</span></span>

<span data-ttu-id="9171c-143">在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="9171c-143">SSRS must be installed and running during MBAM server installation.</span></span> <span data-ttu-id="9171c-144">SSRS 也應該設定為「原生」模式，而不是「未配置」或「SharePoint」模式。</span><span class="sxs-lookup"><span data-stu-id="9171c-144">SSRS should also be configured in “native” mode, not in the “unconfigured” or “SharePoint” mode.</span></span>

<span data-ttu-id="9171c-145">**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="9171c-145">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="9171c-146">恢復與硬體資料庫的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-146">Installation prerequisites for the Recovery and Hardware Database</span></span>

<span data-ttu-id="9171c-147">復原和硬體資料庫必須安裝在支援的 SQLServer 版本上。</span><span class="sxs-lookup"><span data-stu-id="9171c-147">The Recovery and Hardware Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="9171c-148">SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。</span><span class="sxs-lookup"><span data-stu-id="9171c-148">SQL Server must have Database Engine Services installed and running during the MBAM server installation.</span></span> <span data-ttu-id="9171c-149">必須啟用 [透明資料加密（TDE）] 功能。</span><span class="sxs-lookup"><span data-stu-id="9171c-149">The Transparent Data Encryption (TDE) feature must be enabled.</span></span>

<span data-ttu-id="9171c-150">**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="9171c-150">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

<span data-ttu-id="9171c-151">TDE SQLServer 功能可執行即時輸入/輸出（i/o）對資料和記錄檔進行加密和解密。</span><span class="sxs-lookup"><span data-stu-id="9171c-151">The TDE SQLServer feature performs real-time input/output (I/O) encryption and decryption of the data and log files.</span></span> <span data-ttu-id="9171c-152">TDE 會保護「存放中」的資料，其中包含資料和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="9171c-152">TDE protects data that is "at rest,” which include the data and the log files.</span></span> <span data-ttu-id="9171c-153">它可讓您遵守許多行業中建立的各種法律、規章及指導方針。</span><span class="sxs-lookup"><span data-stu-id="9171c-153">It provides the ability to comply with many laws, regulations, and guidelines that are established in various industries.</span></span>

<span data-ttu-id="9171c-154">**記事** 因為 TDE 會執行資料庫資訊的即時解密，所以如果您在 [登入] 下的帳戶有權在您查看 [復原金鑰資訊] SQL 資料表時，系統會看到該資料庫的許可權，就會顯示覆原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="9171c-154">**Note** Because TDE performs real-time decryption of database information, the recovery key information will be visible if the account under which you are logged in has permissions to the database when you view the recovery key information SQL tables.</span></span>

 

### <span data-ttu-id="9171c-155">合規性和審核資料庫的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-155">Installation prerequisites for the Compliance and Audit Database</span></span>

<span data-ttu-id="9171c-156">合規性和審核資料庫必須安裝在支援的 SQLServer 版本上。</span><span class="sxs-lookup"><span data-stu-id="9171c-156">The Compliance and Audit Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="9171c-157">SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。</span><span class="sxs-lookup"><span data-stu-id="9171c-157">SQL Server must have Database Engine Services installed and running during MBAM server installation.</span></span>

<span data-ttu-id="9171c-158">**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="9171c-158">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="9171c-159">MBAM 用戶端的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="9171c-159">Installation prerequisites for MBAM Clients</span></span>


<span data-ttu-id="9171c-160">開始 MBAM 用戶端安裝之前，您必須符合下列必要的先決條件：</span><span class="sxs-lookup"><span data-stu-id="9171c-160">The necessary prerequisites that you must meet before you begin the MBAM Client installation are the following:</span></span>

-   <span data-ttu-id="9171c-161">受信任的平臺模組（TPM） v 1.2 功能</span><span class="sxs-lookup"><span data-stu-id="9171c-161">Trusted Platform Module (TPM) v1.2 capability</span></span>

-   <span data-ttu-id="9171c-162">TPM 晶片必須在 BIOS 中開啟，而且必須從作業系統 resettable。</span><span class="sxs-lookup"><span data-stu-id="9171c-162">The TPM chip must be turned on in the BIOS and it must be resettable from the operating system.</span></span> <span data-ttu-id="9171c-163">如需詳細資訊，請參閱 BIOS 檔。</span><span class="sxs-lookup"><span data-stu-id="9171c-163">For more information, see the BIOS documentation.</span></span>

<span data-ttu-id="9171c-164">**警告** 確定鍵盤、滑鼠和影片都直接連接到電腦，而不是鍵盤、影片、滑鼠（KVM）開關。</span><span class="sxs-lookup"><span data-stu-id="9171c-164">**Warning** Ensure that the keyboard, mouse, and video are directly connected to the computer, instead of to a keyboard, video, mouse (KVM) switch.</span></span> <span data-ttu-id="9171c-165">KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。</span><span class="sxs-lookup"><span data-stu-id="9171c-165">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span>

 

## <span data-ttu-id="9171c-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="9171c-166">Related topics</span></span>


[<span data-ttu-id="9171c-167">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="9171c-167">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="9171c-168">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="9171c-168">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

 

 





