---
title: 關於 Client 組態設定
description: 關於 Client 組態設定
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800719"
---
# <span data-ttu-id="4b6b7-103">關於 Client 組態設定</span><span class="sxs-lookup"><span data-stu-id="4b6b7-103">About Client Configuration Settings</span></span>


<span data-ttu-id="4b6b7-104">Microsoft Application Virtualization （App-v）5.0 用戶端將其設定儲存在註冊表中。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-104">The Microsoft Application Virtualization (App-V) 5.0 client stores its configuration in the registry.</span></span> <span data-ttu-id="4b6b7-105">如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="4b6b7-106">您也可以透過變更登錄專案來設定多個用戶端動作。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="4b6b7-107">本主題列出 App-v 5.0 用戶端設定設定並說明其用法。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-107">This topic lists the App-V 5.0 Client configuration settings and explains their uses.</span></span> <span data-ttu-id="4b6b7-108">您可以使用 PowerShell 來修改用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-108">You can use PowerShell to modify the client configuration settings.</span></span> <span data-ttu-id="4b6b7-109">如需有關使用 PowerShell 與 App-v 5.0 的詳細資訊，請參閱[使用 Powershell 管理 App-v](administering-app-v-by-using-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-109">For more information about using PowerShell and App-V 5.0 see [Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md).</span></span>

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> <span data-ttu-id="4b6b7-110">App-V 5.0 用戶端配置設定</span><span class="sxs-lookup"><span data-stu-id="4b6b7-110">App-V 5.0 Client Configuration Settings</span></span>


<span data-ttu-id="4b6b7-111">下表顯示 App-V 5.0 用戶端配置設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="4b6b7-111">The following table displays information about the App-V 5.0 client configuration settings:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4b6b7-112">設定名稱</span><span class="sxs-lookup"><span data-stu-id="4b6b7-112">Setting Name</span></span></th>
<th align="left"><span data-ttu-id="4b6b7-113">設定標誌</span><span class="sxs-lookup"><span data-stu-id="4b6b7-113">Setup Flag</span></span></th>
<th align="left"><span data-ttu-id="4b6b7-114">描述</span><span class="sxs-lookup"><span data-stu-id="4b6b7-114">Description</span></span></th>
<th align="left"><span data-ttu-id="4b6b7-115">設定選項</span><span class="sxs-lookup"><span data-stu-id="4b6b7-115">Setting Options</span></span></th>
<th align="left"><span data-ttu-id="4b6b7-116">登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="4b6b7-116">Registry Key Value</span></span></th>
<th align="left"><span data-ttu-id="4b6b7-117">已停用原則狀態金鑰和值</span><span class="sxs-lookup"><span data-stu-id="4b6b7-117">Disabled Policy State Keys and Values</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-118">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="4b6b7-118">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-119">PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="4b6b7-119">PACKAGEINSTALLATIONROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-120">指定將安裝所有新應用程式和更新的目錄。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-120">Specifies directory where all new applications and updates will be installed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-121">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-121">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-122">Streaming\PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="4b6b7-122">Streaming\PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-123">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-123">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-124">PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="4b6b7-124">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-125">PACKAGESOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="4b6b7-125">PACKAGESOURCEROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-126">覆寫下載套件內容的來源位置。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-126">Overrides source location for downloading package content.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-127">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-127">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-128">Streaming\PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="4b6b7-128">Streaming\PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-129">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-129">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-130">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="4b6b7-130">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-131">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-131">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-132">此設定會控制是否要在透過計量付費網路連線（例如4G）連線的 Windows 8 電腦上啟動虛擬化應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-132">This setting controls whether virtualized applications are launched on Windows 8 machines connected via a metered network connection (For example, 4G).</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-133">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-133">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-134">Streaming\AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="4b6b7-134">Streaming\AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-135">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-135">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-136">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="4b6b7-136">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-137">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-137">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-138">指定重試刪除的會話的次數。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-138">Specifies the number of times to retry a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-139">Integer （0-99）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-139">Integer (0-99)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-140">Streaming\ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="4b6b7-140">Streaming\ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-141">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-141">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-142">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-142">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-143">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-143">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-144">指定嘗試重建已刪除的會話之間的秒數。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-144">Specifies the number of seconds between attempts to reestablish a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-145">Integer （0-3600）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-145">Integer (0-3600)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-146">Streaming\ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-146">Streaming\ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-147">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-147">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-148">AutoLoad</span><span class="sxs-lookup"><span data-stu-id="4b6b7-148">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-149">AUTOLOAD</span><span class="sxs-lookup"><span data-stu-id="4b6b7-149">AUTOLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-150">指定如何在特定電腦上使用 App-v 自動載入新套件。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-150">Specifies how new packages should be loaded automatically by App-V on a specific computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-151">（0x0）無;（0x1）先前已使用;（0x2） All</span><span class="sxs-lookup"><span data-stu-id="4b6b7-151">(0x0) None; (0x1) Previously used; (0x2) All</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-152">Streaming\AutoLoad</span><span class="sxs-lookup"><span data-stu-id="4b6b7-152">Streaming\AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-153">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-153">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-154">LocationProvider</span><span class="sxs-lookup"><span data-stu-id="4b6b7-154">LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-155">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-155">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-156">指定 IAppvPackageLocationProvider 介面的相容實現的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-156">Specifies the CLSID for a compatible implementation of the IAppvPackageLocationProvider interface.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-157">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-157">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-158">Streaming\LocationProvider</span><span class="sxs-lookup"><span data-stu-id="4b6b7-158">Streaming\LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-159">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-159">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-160">CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="4b6b7-160">CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-161">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-161">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-162">指定憑證存放區中有效憑證的路徑。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-162">Specifies the path to a valid certificate in the certificate store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-163">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-163">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-164">Streaming\CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="4b6b7-164">Streaming\CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-165">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-165">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-166">VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="4b6b7-166">VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-167">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-167">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-168">在使用 HTTPS steaming 前驗證服務器憑證吊銷狀態。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-168">Verifies Server certificate revocation status before steaming using HTTPS.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-169">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-169">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-170">Streaming\VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="4b6b7-170">Streaming\VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-171">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-171">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-172">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="4b6b7-172">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-173">SHAREDCONTENTSTOREMODE</span><span class="sxs-lookup"><span data-stu-id="4b6b7-173">SHAREDCONTENTSTOREMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-174">指定不會將流式套件內容儲存到本機硬碟。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-174">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-175">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-175">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-176">Streaming\SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="4b6b7-176">Streaming\SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-177">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-177">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-178">名稱</span><span class="sxs-lookup"><span data-stu-id="4b6b7-178">Name</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-179">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-179">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-180">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-180">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-181">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-181">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-182">PUBLISHINGSERVERNAME</span><span class="sxs-lookup"><span data-stu-id="4b6b7-182">PUBLISHINGSERVERNAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-183">顯示發佈伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-183">Displays the name of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-184">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-184">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-185">Publishing\Servers {serverId} \ FriendlyName</span><span class="sxs-lookup"><span data-stu-id="4b6b7-185">Publishing\Servers{serverId}\FriendlyName</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-186">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-186">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-187">URL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-187">URL</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-188">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-188">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-189">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-189">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-190">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-190">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-191">PUBLISHINGSERVERURL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-191">PUBLISHINGSERVERURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-192">顯示發佈伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-192">Displays the URL of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-193">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-193">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-194">Publishing\Servers {serverId} \ URL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-194">Publishing\Servers{serverId}\URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-195">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-195">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-196">GlobalRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="4b6b7-196">GlobalRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-197">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-197">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-198">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-198">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-199">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-199">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-200">GLOBALREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="4b6b7-200">GLOBALREFRESHENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-201">啟用全域發佈重新整理（布林值）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-201">Enables global publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-202">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-202">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-203">Publishing\Servers{serverId}\GlobalEnabled</span><span class="sxs-lookup"><span data-stu-id="4b6b7-203">Publishing\Servers{serverId}\GlobalEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-204">False</span><span class="sxs-lookup"><span data-stu-id="4b6b7-204">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-205">GlobalRefreshOnLogon</span><span class="sxs-lookup"><span data-stu-id="4b6b7-205">GlobalRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-206">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-206">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-207">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-207">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-208">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-208">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-209">GLOBALREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="4b6b7-209">GLOBALREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-210">在登入時觸發全域發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-210">Triggers a global publishing refresh on logon.</span></span> <span data-ttu-id="4b6b7-211">布林值</span><span class="sxs-lookup"><span data-stu-id="4b6b7-211">( Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-212">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-212">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-213">Publishing\Servers{serverId}\GlobalLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="4b6b7-213">Publishing\Servers{serverId}\GlobalLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-214">False</span><span class="sxs-lookup"><span data-stu-id="4b6b7-214">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-215">GlobalRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-215">GlobalRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-216">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-216">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-217">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-217">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-218">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-218">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-219">GLOBALREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-219">GLOBALREFRESHINTERVAL</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-220">使用 GlobalRefreshIntervalUnit 指定發佈重新整理間隔。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-220">Specifies the publishing refresh interval using the GlobalRefreshIntervalUnit.</span></span> <span data-ttu-id="4b6b7-221">若要停用套件重新整理，請選取 [0]。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-221">To disable package refresh, select 0.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-222">Integer （0-744</span><span class="sxs-lookup"><span data-stu-id="4b6b7-222">Integer (0-744</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-224">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-224">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-225">GlobalRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-225">GlobalRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-226">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-226">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-227">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-227">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-228">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-228">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-229">GLOBALREFRESHINTERVALUNI</span><span class="sxs-lookup"><span data-stu-id="4b6b7-229">GLOBALREFRESHINTERVALUNI</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-230">指定間隔單位（小時0-23，天0-31）。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-230">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-231">0代表小時，1代表日</span><span class="sxs-lookup"><span data-stu-id="4b6b7-231">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-232">Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-232">Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-233">sr-1</span><span class="sxs-lookup"><span data-stu-id="4b6b7-233">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-234">UserRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="4b6b7-234">UserRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-235">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-235">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-236">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-236">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-237">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-237">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-238">USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="4b6b7-238">USERREFRESHENABLED</span></span> </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-239">啟用使用者發佈更新（布林值）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-239">Enables user publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-240">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-240">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-241">Publishing\Servers{serverId}\UserEnabled</span><span class="sxs-lookup"><span data-stu-id="4b6b7-241">Publishing\Servers{serverId}\UserEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-242">False</span><span class="sxs-lookup"><span data-stu-id="4b6b7-242">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-243">UserRefreshOnLogon</span><span class="sxs-lookup"><span data-stu-id="4b6b7-243">UserRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-244">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-244">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-245">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-245">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-246">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-246">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-247">USERREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="4b6b7-247">USERREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-248">觸發使用者發佈重新整理 onlogon。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-248">Triggers a user publishing refresh onlogon.</span></span> <span data-ttu-id="4b6b7-249">布林值</span><span class="sxs-lookup"><span data-stu-id="4b6b7-249">( Boolean)</span></span></p>
<p><span data-ttu-id="4b6b7-250">字數統計（含空格）：60</span><span class="sxs-lookup"><span data-stu-id="4b6b7-250">Word count (with spaces): 60</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-251">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-251">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-252">Publishing\Servers{serverId}\UserLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="4b6b7-252">Publishing\Servers{serverId}\UserLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-253">False</span><span class="sxs-lookup"><span data-stu-id="4b6b7-253">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-254">UserRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-254">UserRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-255">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-255">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-256">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-256">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-257">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-257">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-258">USERREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-258">USERREFRESHINTERVAL</span></span>     </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-259">使用 UserRefreshIntervalUnit 指定發佈重新整理間隔。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-259">Specifies the publishing refresh interval using the UserRefreshIntervalUnit.</span></span> <span data-ttu-id="4b6b7-260">若要停用套件重新整理，請選取 [0]。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-260">To disable package refresh, select 0.</span></span></p>
<p><span data-ttu-id="4b6b7-261">字數統計（含空格）：85</span><span class="sxs-lookup"><span data-stu-id="4b6b7-261">Word count (with spaces): 85</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-262">整數（0-744 小時）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-262">Integer (0-744 Hours)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-264">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-264">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-265">UserRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-265">UserRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-266">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-266">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-267">此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-267">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="4b6b7-268">您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-268">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-269">USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="4b6b7-269">USERREFRESHINTERVALUNIT</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-270">指定間隔單位（小時0-23，天0-31）。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-270">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="4b6b7-271">0代表小時，1代表日</span><span class="sxs-lookup"><span data-stu-id="4b6b7-271">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-272">Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-272">Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-273">sr-1</span><span class="sxs-lookup"><span data-stu-id="4b6b7-273">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-274">MigrationMode</span><span class="sxs-lookup"><span data-stu-id="4b6b7-274">MigrationMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-275">MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="4b6b7-275">MIGRATIONMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-276">[遷移] 模式可讓 App-V 用戶端修改使用舊版 App-v 所建立之套件的快速鍵與 FTA。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-276">Migration mode allows the App-V client to modify shortcuts and FTA’s for packages created using a previous version of App-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-277">True （啟用狀態）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-277">True(enabled state); False (disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-278">Coexistence\MigrationMode</span><span class="sxs-lookup"><span data-stu-id="4b6b7-278">Coexistence\MigrationMode</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-279">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="4b6b7-279">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-280">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="4b6b7-280">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-281">允許執行 App-v 5.0 用戶端的電腦收集並傳回特定的使用資訊，以協助我們進一步改善應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-281">Allows the computer running the App-V 5.0 Client to collect and return certain usage information to help allow us to further improve the application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-282">0：停用;1以啟用</span><span class="sxs-lookup"><span data-stu-id="4b6b7-282">0 for disabled; 1 for enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-283">軟體/Microsoft/AppV/CEIP/CEIPEnable</span><span class="sxs-lookup"><span data-stu-id="4b6b7-283">SOFTWARE/Microsoft/AppV/CEIP/CEIPEnable</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-284">0</span><span class="sxs-lookup"><span data-stu-id="4b6b7-284">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-285">EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="4b6b7-285">EnablePackageScripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-286">ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="4b6b7-286">ENABLEPACKAGESCRIPTS</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-287">啟用要執行之設定檔案的套件資訊清單中定義的腳本。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-287">Enables scripts defined in the package manifest of configuration files that should run.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-288">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-288">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-289">\Scripting\EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="4b6b7-289">\Scripting\EnablePackageScripts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-290">RoamingFileExclusions</span><span class="sxs-lookup"><span data-stu-id="4b6b7-290">RoamingFileExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-291">ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="4b6b7-291">ROAMINGFILEEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-292">指定相對於% userprofile% （不會與使用者&#39;s 設定檔漫遊）的檔路徑。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-292">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="4b6b7-293">範例用法：/ROAMINGFILEEXCLUSIONS =&#39;桌面; 我的圖片&#39;</span><span class="sxs-lookup"><span data-stu-id="4b6b7-293">Example usage:  /ROAMINGFILEEXCLUSIONS=&#39;desktop;my pictures&#39;</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-294">RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="4b6b7-294">RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-295">ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="4b6b7-295">ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-296">指定不使用使用者設定檔漫遊的登錄路徑。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-296">Specifies the registry paths that do not roam with a user profile.</span></span> <span data-ttu-id="4b6b7-297">範例用法：/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</span><span class="sxs-lookup"><span data-stu-id="4b6b7-297">Example usage: /ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-298">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-298">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-299">Integration\RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="4b6b7-299">Integration\RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-300">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-300">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-301">IntegrationRootUser</span><span class="sxs-lookup"><span data-stu-id="4b6b7-301">IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-302">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-302">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-303">指定位置，以建立與每個使用者已發佈套件之目前版本相關聯的符號連結。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-303">Specifies the location to create symbolic links associated with the current version of a per-user published package.</span></span> <span data-ttu-id="4b6b7-304">所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-304">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="4b6b7-305">如果您沒有指定路徑，則在發佈套件時不會使用符號連結。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-305">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="4b6b7-306">例如：%localappdata%\Microsoft\AppV\Client\Integration。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-306">For example: %localappdata%\Microsoft\AppV\Client\Integration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-307">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-307">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-308">Integration\IntegrationRootUser</span><span class="sxs-lookup"><span data-stu-id="4b6b7-308">Integration\IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-309">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-309">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-310">IntegrationRootGlobal</span><span class="sxs-lookup"><span data-stu-id="4b6b7-310">IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-311">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-311">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-312">指定位置，以建立與全域發佈套件目前版本相關聯的符號連結。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-312">Specifies the location to create symbolic links associated with the current version of a globally published package.</span></span> <span data-ttu-id="4b6b7-313">所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-313">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="4b6b7-314">如果您沒有指定路徑，則在發佈套件時不會使用符號連結。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-314">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="4b6b7-315">例如：%allusersprofile%\Microsoft\AppV\Client\Integration</span><span class="sxs-lookup"><span data-stu-id="4b6b7-315">For example: %allusersprofile%\Microsoft\AppV\Client\Integration</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-316">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-316">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-317">Integration\IntegrationRootGlobal</span><span class="sxs-lookup"><span data-stu-id="4b6b7-317">Integration\IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-318">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-318">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-319">VirtualizableExtensions</span><span class="sxs-lookup"><span data-stu-id="4b6b7-319">VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-320">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-320">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-321">以逗號分隔的副檔名清單，可用於判斷本機安裝的應用程式是否可以在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-321">A comma -delineated list of file name extensions that can be used to determine if a locally installed application can be run in the virtual environment.</span></span></p>
<p><span data-ttu-id="4b6b7-322">在發佈期間建立 [快捷方式]、[FTAs] 和其他延伸點時，如果與延伸點相關聯的應用程式是在本機安裝，App-v 會將檔案副檔名與清單進行比較。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-322">When shortcuts, FTAs, and other extension points are created during publishing, App-V will compare the file name extension to the list if the application that is associated with the extension point is locally installed.</span></span> <span data-ttu-id="4b6b7-323">如果副檔名位於這個位置， <strong> 就會 </strong> 新增 RunVirtual 命令列參數，而應用程式將會在實際執行。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-323">If the extension is located, the <strong>RunVirtual</strong> command line parameter will be added, and the application will run virtually.</span></span></p>
<p><span data-ttu-id="4b6b7-324">如需 RunVirtual 參數的詳細資訊 <strong> </strong> ，請參閱 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 使用虛擬化應用程式在虛擬環境中執行本機安裝的應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-324">For more information about the <strong>RunVirtual</strong> parameter, see <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</a>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-325">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-325">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-326">Integration\VirtualizableExtensions</span><span class="sxs-lookup"><span data-stu-id="4b6b7-326">Integration\VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-327">未寫入原則值</span><span class="sxs-lookup"><span data-stu-id="4b6b7-327">Policy value not written</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-328">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="4b6b7-328">ReportingEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-329">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-329">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-330">可讓用戶端傳回信息給報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-330">Enables the client to return information to a reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-331">True （enabled）;False （停用狀態）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-331">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-332">Reporting\EnableReporting</span><span class="sxs-lookup"><span data-stu-id="4b6b7-332">Reporting\EnableReporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-333">False</span><span class="sxs-lookup"><span data-stu-id="4b6b7-333">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-334">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="4b6b7-334">ReportingServerURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-335">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-335">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-336">指定報表服務器上儲存用戶端資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-336">Specifies the location on the reporting server where client information is saved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-337">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-337">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-338">Reporting\ReportingServer</span><span class="sxs-lookup"><span data-stu-id="4b6b7-338">Reporting\ReportingServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-339">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-339">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-340">ReportingDataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-340">ReportingDataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-341">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-341">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-342">指定儲存報告資訊的 XML 快取大小上限（MB）。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-342">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="4b6b7-343">此大小會套用到記憶體中的快取。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-343">The size applies to the cache in memory.</span></span> <span data-ttu-id="4b6b7-344">當達到限制時，記錄檔案將會滾過。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-344">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="4b6b7-345">設定為0至1024。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-345">Set between 0 and 1024.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-346">整型 [0-1024]</span><span class="sxs-lookup"><span data-stu-id="4b6b7-346">Integer [0-1024]</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-347">Reporting\DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="4b6b7-347">Reporting\DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-348">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-348">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-349">ReportingDataBlockSize</span><span class="sxs-lookup"><span data-stu-id="4b6b7-349">ReportingDataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-350">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-350">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-351">指定要傳送給伺服器以取得報告上傳要求的最大大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-351">Specifies the maximum size in bytes to transmit to the server for reporting upload requests.</span></span> <span data-ttu-id="4b6b7-352">當記錄達到大量大小時，這可以協助避免永久傳輸失敗。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-352">This can help avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="4b6b7-353">在1024和無限制之間設定。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-353">Set between 1024 and unlimited.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-354">整數 [1024-無限制]</span><span class="sxs-lookup"><span data-stu-id="4b6b7-354">Integer [1024 - Unlimited]</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-355">Reporting\DataBlockSize</span><span class="sxs-lookup"><span data-stu-id="4b6b7-355">Reporting\DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-356">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-356">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-357">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="4b6b7-357">ReportingStartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-358">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-358">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-359">指定啟動用戶端以傳送資料至報表伺服器的時間。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-359">Specifies the time to initiate the client to send data to the reporting server.</span></span> <span data-ttu-id="4b6b7-360">您必須在0-23 之間指定有效的整數，以對應到一天中的每個小時。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-360">You must specify a valid integer between 0-23 corresponding to the hour of the day.</span></span> <span data-ttu-id="4b6b7-361">根據預設， <strong> ReportingStartTime </strong> 會在 [10] P. M. 或22日的當天開始。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-361">By default the <strong>ReportingStartTime</strong> will start on the current day at 10 P.M.or 22.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-362">注意</span><span class="sxs-lookup"><span data-stu-id="4b6b7-362">Note</span></span></strong><br/><p><span data-ttu-id="4b6b7-363">在執行 App-v 5.0 用戶端的電腦最不可能處於離線狀態時，您應該將此設定設定為時間。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-363">You should configure this setting to a time when computers running the App-V 5.0 client are least likely to be offline.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-364">整數（0到23）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-364">Integer (0 – 23)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-365">報告 \ StartTime</span><span class="sxs-lookup"><span data-stu-id="4b6b7-365">Reporting\ StartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-366">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-366">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-367">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-367">ReportingInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-368">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-368">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-369">指定用戶端將用來重新傳送資料至報表伺服器的重試時間間隔。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-369">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-370">整數</span><span class="sxs-lookup"><span data-stu-id="4b6b7-370">Integer</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-371">Reporting\RetryInterval</span><span class="sxs-lookup"><span data-stu-id="4b6b7-371">Reporting\RetryInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-372">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-372">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-373">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="4b6b7-373">ReportingRandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-374">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-374">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-375">指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-375">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="4b6b7-376">當排程的任務開始時，用戶端會在0與 ReportingRandomDelay 之間產生隨機延遲， <strong> </strong> 並在傳送資料之前等待指定的持續時間。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-376">When the scheduled task is started, the client generates a random delay between 0 and <strong>ReportingRandomDelay</strong> and will wait the specified duration before sending data.</span></span> <span data-ttu-id="4b6b7-377">這有助於避免在伺服器上發生衝突。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-377">This can help to prevent collisions on the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-378">Integer [0-ReportingRandomDelay]</span><span class="sxs-lookup"><span data-stu-id="4b6b7-378">Integer [0 - ReportingRandomDelay]</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-379">Reporting\RandomDelay</span><span class="sxs-lookup"><span data-stu-id="4b6b7-379">Reporting\RandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-380">未寫入原則值（與 [未設定] 相同）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-380">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-381">EnableDynamicVirtualization</span><span class="sxs-lookup"><span data-stu-id="4b6b7-381">EnableDynamicVirtualization</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-382">重要</span><span class="sxs-lookup"><span data-stu-id="4b6b7-382">Important</span></span></strong><br/><p><span data-ttu-id="4b6b7-383">此設定僅適用于 App-v 5.0 SP2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-383">This setting is available only with App-V 5.0 SP2 or later.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-384">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-384">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-385">啟用支援的命令介面延伸、瀏覽器 Helper 物件，以及使用中 X 控制項來虛擬化並與虛擬應用程式一起執行。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-385">Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-386">1（啟用），0（停用）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-386">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-387">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</span><span class="sxs-lookup"><span data-stu-id="4b6b7-387">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Virtualization</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-388">EnablePublishingRefreshUI</span><span class="sxs-lookup"><span data-stu-id="4b6b7-388">EnablePublishingRefreshUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-389">重要</span><span class="sxs-lookup"><span data-stu-id="4b6b7-389">Important</span></span></strong><br/><p><span data-ttu-id="4b6b7-390">此設定僅適用于 App-v 5.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-390">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-391">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-391">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-392">針對執行 App-v 5.0 用戶端的電腦啟用 [發佈更新進度] 列。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-392">Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-393">1（啟用），0（停用）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-393">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-394">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</span><span class="sxs-lookup"><span data-stu-id="4b6b7-394">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Publishing</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4b6b7-395">HideUI</span><span class="sxs-lookup"><span data-stu-id="4b6b7-395">HideUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4b6b7-396">重要</span><span class="sxs-lookup"><span data-stu-id="4b6b7-396">Important</span></span></strong><br/><p><span data-ttu-id="4b6b7-397">此設定僅適用于 App-v 5.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-397">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="4b6b7-398">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-398">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-399">隱藏發佈更新進度列。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-399">Hides the publishing refresh progress bar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-400">1（啟用），0（停用）</span><span class="sxs-lookup"><span data-stu-id="4b6b7-400">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4b6b7-401">ProcessesUsingVirtualComponents</span><span class="sxs-lookup"><span data-stu-id="4b6b7-401">ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-402">無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-402">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-403">指定程式路徑的清單（可能包含萬用字元），這是使用動態虛擬化（支援的命令介面延伸、瀏覽器 helper 物件和 ActiveX 控制項）的候選項目。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-403">Specifies a list of process paths (that may contain wildcards), which are candidates for using dynamic virtualization (supported shell extensions, browser helper objects, and ActiveX controls).</span></span> <span data-ttu-id="4b6b7-404">只有其完整路徑符合其中一個專案的進程才能使用動態虛擬化。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-404">Only processes whose full path matches one of these items can use dynamic virtualization.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-405">字串</span><span class="sxs-lookup"><span data-stu-id="4b6b7-405">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-406">Virtualization\ProcessesUsingVirtualComponents</span><span class="sxs-lookup"><span data-stu-id="4b6b7-406">Virtualization\ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="4b6b7-407">空字串。</span><span class="sxs-lookup"><span data-stu-id="4b6b7-407">Empty string.</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="4b6b7-408">相關主題</span><span class="sxs-lookup"><span data-stu-id="4b6b7-408">Related topics</span></span>


[<span data-ttu-id="4b6b7-409">部署 App-V 5.0 排序器和用戶端</span><span class="sxs-lookup"><span data-stu-id="4b6b7-409">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

[<span data-ttu-id="4b6b7-410">如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態</span><span class="sxs-lookup"><span data-stu-id="4b6b7-410">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[<span data-ttu-id="4b6b7-411">如何部署 App-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="4b6b7-411">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-gb18030.md)









