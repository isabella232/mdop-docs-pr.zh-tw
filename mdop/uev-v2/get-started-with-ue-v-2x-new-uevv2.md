---
title: UE-V 2.x 入門
description: UE-V 2.x 入門
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809866"
---
# <span data-ttu-id="64a58-103">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="64a58-103">Get Started with UE-V 2.x</span></span>


<span data-ttu-id="64a58-104">請依照本指南中的步驟，在小型測試環境中快速部署 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1。</span><span class="sxs-lookup"><span data-stu-id="64a58-104">Follow the steps in this guide to quickly deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 in a small test environment.</span></span> <span data-ttu-id="64a58-105">這可協助您判斷 UE-V 是否是正確的解決方案，可在企業中的多個裝置上管理使用者設定。</span><span class="sxs-lookup"><span data-stu-id="64a58-105">This helps you determine whether UE-V is the right solution to manage user settings across multiple devices within your enterprise.</span></span>

<span data-ttu-id="64a58-106">**記事** 本區段中的資訊會在整個檔中更詳細地重複。</span><span class="sxs-lookup"><span data-stu-id="64a58-106">**Note** The information in this section is repeated in greater detail throughout the rest of the documentation.</span></span> <span data-ttu-id="64a58-107">因此，如果您已經知道 UE-V 2 是正確的解決方案，而且您不需要評估它，您可以直接[使用 [準備 ue-v 2. x] 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="64a58-107">So if you already know that UE-V 2 is the right solution and you don’t need to evaluate it, you can just go right to [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md).</span></span>

 

<span data-ttu-id="64a58-108">UE-V 的標準安裝會同步處理預設的 Microsoft Windows 和 Office 設定，以及許多 Windows 應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="64a58-108">The standard installation of UE-V synchronizes the default Microsoft Windows and Office settings and many Windows app settings.</span></span> <span data-ttu-id="64a58-109">請確定您的測試環境包含兩個或多個共用網路存取的使用者電腦，而且您會在一段短期內評估 UE-V。</span><span class="sxs-lookup"><span data-stu-id="64a58-109">Make sure your test environment includes two or more user computers that share network access and you’ll be evaluating UE-V in just a short time.</span></span>

-   <span data-ttu-id="64a58-110">[步驟1：確認先決條件](#step1)：請確定您的環境能夠執行 ue-v，包括支援的設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="64a58-110">[Step 1: Confirm Prerequisites](#step1): Make sure your environment is able to run UE-V, including details about supported configurations.</span></span>

-   <span data-ttu-id="64a58-111">[步驟2：部署 ue-v 2 的設定儲存位置](#step2)：所有 Ue-v 部署都需要包含同步處理設定值之設定套件的位置。</span><span class="sxs-lookup"><span data-stu-id="64a58-111">[Step 2: Deploy the Settings Storage Location for UE-V 2](#step2): All UE-V deployments require a location for settings packages that contain the synchronized setting values.</span></span>

-   <span data-ttu-id="64a58-112">[步驟3：部署 ue-v 2 代理](#step3)：若要使用 ue-v 同步處理設定，裝置必須已安裝並執行 ue-v Agent。</span><span class="sxs-lookup"><span data-stu-id="64a58-112">[Step 3: Deploy the UE-V 2 Agent](#step3): To synchronize settings using UE-V, devices must have the UE-V Agent installed and running.</span></span>

-   <span data-ttu-id="64a58-113">[步驟4：測試您的 ue-v 2 評估部署](#step4)：在裝有 ue-v agent 的兩部電腦上執行一些測試，並瞭解 ue-v 的運作方式。</span><span class="sxs-lookup"><span data-stu-id="64a58-113">[Step 4: Test Your UE-V 2 Evaluation Deployment](#step4): Run a few tests on two computers that have the UE-V Agent installed and see how UE-V works.</span></span>

<span data-ttu-id="64a58-114">就是這樣！</span><span class="sxs-lookup"><span data-stu-id="64a58-114">That’s it!</span></span> <span data-ttu-id="64a58-115">遵循這些步驟之後，您就可以評估 UE-V 在企業中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="64a58-115">Once you follow the steps, you’ll be able to evaluate how UE-V can work in your enterprise.</span></span>

<span data-ttu-id="64a58-116">**進一步評估：** 您也可以執行其他步驟來設定部分協力廠商與行業應用程式，以使用 UE-V 同步處理其設定，請參閱[部署 UE-v （自訂應用程式](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)）。</span><span class="sxs-lookup"><span data-stu-id="64a58-116">**Further evaluation:** You can also perform additional steps to configure some third-party and line-of-business applications to synchronize their settings using UE-V as detailed in [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <a href="" id="step1"></a><span data-ttu-id="64a58-117">步驟1：確認先決條件</span><span class="sxs-lookup"><span data-stu-id="64a58-117">Step 1: Confirm Prerequisites</span></span>


<span data-ttu-id="64a58-118">在您繼續進行之前，請確定您的環境包含執行 UE-V 的這些需求。</span><span class="sxs-lookup"><span data-stu-id="64a58-118">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

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
<th align="left"><strong><span data-ttu-id="64a58-119">作業系統</span><span class="sxs-lookup"><span data-stu-id="64a58-119">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="64a58-120">版本</span><span class="sxs-lookup"><span data-stu-id="64a58-120">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="64a58-121">Service pack</span><span class="sxs-lookup"><span data-stu-id="64a58-121">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="64a58-122">系統架構</span><span class="sxs-lookup"><span data-stu-id="64a58-122">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="64a58-123">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64a58-123">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="64a58-124">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="64a58-124">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64a58-125">Windows7</span><span class="sxs-lookup"><span data-stu-id="64a58-125">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-126">旗艦版、企業版或專業版</span><span class="sxs-lookup"><span data-stu-id="64a58-126">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-127">SP1</span><span class="sxs-lookup"><span data-stu-id="64a58-127">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-128">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-128">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-129">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-129">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-130">.NET Framework 4 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-130">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64a58-131">Windows Server2008R2</span><span class="sxs-lookup"><span data-stu-id="64a58-131">Windows Server2008R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-132">標準版、企業版、資料中心或 Web 服務器</span><span class="sxs-lookup"><span data-stu-id="64a58-132">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-133">SP1</span><span class="sxs-lookup"><span data-stu-id="64a58-133">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-134">64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-134">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-135">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-135">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-136">.NET Framework 4 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-136">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64a58-137">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="64a58-137">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-138">企業或專業版</span><span class="sxs-lookup"><span data-stu-id="64a58-138">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-139">無</span><span class="sxs-lookup"><span data-stu-id="64a58-139">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-140">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-140">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-141">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-141">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-142">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="64a58-142">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64a58-143">Windows Server 2012 或 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="64a58-143">Windows Server 2012 or Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-144">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="64a58-144">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-145">無</span><span class="sxs-lookup"><span data-stu-id="64a58-145">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-146">64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-146">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-147">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-147">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-148">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="64a58-148">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64a58-149">Windows 10、1607以前的 verison</span><span class="sxs-lookup"><span data-stu-id="64a58-149">Windows 10, pre-1607 verison</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-150">企業或專業版</span><span class="sxs-lookup"><span data-stu-id="64a58-150">Enterprise or Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="64a58-151">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-151">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-152">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-152">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-153">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="64a58-153">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64a58-154">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="64a58-154">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-155">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="64a58-155">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-156">無</span><span class="sxs-lookup"><span data-stu-id="64a58-156">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-157">64 位元</span><span class="sxs-lookup"><span data-stu-id="64a58-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-158">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="64a58-158">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="64a58-159">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="64a58-159">.NET Framework 4.5</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="64a58-160">**注意：** 從 Windows 10 開始，版本1607、UE-V 已包含在企業版[windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，而且不再是 Microsoft 桌面優化套件的一部分</span><span class="sxs-lookup"><span data-stu-id="64a58-160">**Note:** Starting with Windows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack</span></span>

<span data-ttu-id="64a58-161">另外 .。。</span><span class="sxs-lookup"><span data-stu-id="64a58-161">Also…</span></span>

-   <span data-ttu-id="64a58-162">**MDOP 授權：** 這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="64a58-162">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="64a58-163">企業客戶可以使用 Microsoft 軟體保證進行 MDOP。</span><span class="sxs-lookup"><span data-stu-id="64a58-163">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="64a58-164">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱如何取得 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="64a58-164">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="64a58-165">您要安裝之任何電腦的系統**管理認證**</span><span class="sxs-lookup"><span data-stu-id="64a58-165">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

## <a href="" id="step2"></a><span data-ttu-id="64a58-166">步驟2：部署 UE-V 2 的設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="64a58-166">Step 2: Deploy the Settings Storage Location for UE-V 2</span></span>


<span data-ttu-id="64a58-167">您必須部署設定儲存位置，即使用者設定儲存在設定套件檔案中的標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="64a58-167">You’ll need to deploy a settings storage location, a standard network share where user settings are stored in a settings package file.</span></span> <span data-ttu-id="64a58-168">當您建立設定儲存區共用時，應該限制存取需要的使用者。</span><span class="sxs-lookup"><span data-stu-id="64a58-168">When you create the settings storage share, you should limit access to users that require it.</span></span> <span data-ttu-id="64a58-169">[[部署設定] 儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)可提供更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="64a58-169">[Deploy a Settings Storage Location](https://technet.microsoft.com/library/dn458891.aspx#ssl) provides more detailed information.</span></span>

**<span data-ttu-id="64a58-170">建立網路共用</span><span class="sxs-lookup"><span data-stu-id="64a58-170">Create a network share</span></span>**

1.  <span data-ttu-id="64a58-171">建立新的安全性群組，並將 UE-V 使用者新增到其中。</span><span class="sxs-lookup"><span data-stu-id="64a58-171">Create a new security group and add UE-V users to it.</span></span>

2.  <span data-ttu-id="64a58-172">在集中位置的電腦上建立儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者存取資料夾的群組許可權。</span><span class="sxs-lookup"><span data-stu-id="64a58-172">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="64a58-173">支援 UE-V 的管理員必須擁有此共用資料夾的許可權。</span><span class="sxs-lookup"><span data-stu-id="64a58-173">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="64a58-174">指派 UE-V 使用者在連線時建立目錄的許可權。</span><span class="sxs-lookup"><span data-stu-id="64a58-174">Assign UE-V users permission to create a directory when they connect.</span></span> <span data-ttu-id="64a58-175">授與該目錄所有子目錄的完整許可權，但封鎖上述任何內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="64a58-175">Grant full permission to all subdirectories of that directory, but block access to anything above.</span></span>

    1.  <span data-ttu-id="64a58-176">針對 [設定儲存位置] 資料夾設定下列共用層伺服器訊息區塊（SMB）許可權。</span><span class="sxs-lookup"><span data-stu-id="64a58-176">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="64a58-177">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="64a58-177">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="64a58-178">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="64a58-178">Recommended permissions</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="64a58-179">所有人</span><span class="sxs-lookup"><span data-stu-id="64a58-179">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-180">沒有許可權</span><span class="sxs-lookup"><span data-stu-id="64a58-180">No permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="64a58-181">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="64a58-181">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-182">完全控制</span><span class="sxs-lookup"><span data-stu-id="64a58-182">Full control</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

    2.  <span data-ttu-id="64a58-183">針對 [設定儲存位置] 資料夾設定下列 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="64a58-183">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="64a58-184">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="64a58-184">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="64a58-185">建議的許可權</span><span class="sxs-lookup"><span data-stu-id="64a58-185">Recommended permissions</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="64a58-186">資料夾</span><span class="sxs-lookup"><span data-stu-id="64a58-186">Folder</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="64a58-187">建立者/擁有者</span><span class="sxs-lookup"><span data-stu-id="64a58-187">Creator/owner</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-188">完全控制</span><span class="sxs-lookup"><span data-stu-id="64a58-188">Full control</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-189">僅限子資料夾和檔案</span><span class="sxs-lookup"><span data-stu-id="64a58-189">Subfolders and files only</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="64a58-190">UE-V 使用者的安全性群組</span><span class="sxs-lookup"><span data-stu-id="64a58-190">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-191">列出資料夾/讀取資料、建立資料夾/附加資料</span><span class="sxs-lookup"><span data-stu-id="64a58-191">List folder/read data, create folders/append data</span></span></p></td>
        <td align="left"><p><span data-ttu-id="64a58-192">僅限此資料夾</span><span class="sxs-lookup"><span data-stu-id="64a58-192">This folder only</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

**<span data-ttu-id="64a58-193">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="64a58-193">Security Note:</span></span>**

<span data-ttu-id="64a58-194">如果您在執行 Windows Server 作業系統的電腦上建立 [設定儲存空間共用]，請設定 UE-V，確認 [本機管理員] 群組或 [目前的使用者] 是儲存設定套件的資料夾擁有者。</span><span class="sxs-lookup"><span data-stu-id="64a58-194">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="64a58-195">若要啟用此額外的安全性，請在 Windows Server 登錄編輯程式中指定此設定：</span><span class="sxs-lookup"><span data-stu-id="64a58-195">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="64a58-196">將名為 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**]。</span><span class="sxs-lookup"><span data-stu-id="64a58-196">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="64a58-197">將 [登錄機碼] 值設定為*1*。</span><span class="sxs-lookup"><span data-stu-id="64a58-197">Set the registry key value to *1*.</span></span>

## <a href="" id="step3"></a><span data-ttu-id="64a58-198">步驟3：部署 UE-V 2 代理程式</span><span class="sxs-lookup"><span data-stu-id="64a58-198">Step 3: Deploy the UE-V 2 Agent</span></span>


<span data-ttu-id="64a58-199">UE-V Agent 會在使用者的電腦和裝置之間同步處理應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="64a58-199">The UE-V Agent synchronizes application and Windows settings between users’ computers and devices.</span></span> <span data-ttu-id="64a58-200">針對評估目的，請在您的測試環境中，將代理安裝在屬於同一位使用者的至少兩台電腦上。</span><span class="sxs-lookup"><span data-stu-id="64a58-200">For evaluation purposes, install the agent on at least two computers in your test environment that belong to the same user.</span></span>

<span data-ttu-id="64a58-201">從命令列執行 AgentSetup.exe 檔案，以安裝 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="64a58-201">Run the AgentSetup.exe file from the command line to install the UE-V Agent.</span></span> <span data-ttu-id="64a58-202">它是在32位和64位作業系統上安裝。</span><span class="sxs-lookup"><span data-stu-id="64a58-202">It installs on both 32-bit and 64-bit operating systems.</span></span>

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

<span data-ttu-id="64a58-203">您必須將 SettingsStoragePath 命令列參數指定為步驟2的網路共用。</span><span class="sxs-lookup"><span data-stu-id="64a58-203">You must specify the SettingsStoragePath command line parameter as the network share from Step 2.</span></span> <span data-ttu-id="64a58-204">[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)提供更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="64a58-204">[Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more detailed information.</span></span>

## <a href="" id="step4"></a><span data-ttu-id="64a58-205">步驟4：測試您的 UE-V 2 評估部署</span><span class="sxs-lookup"><span data-stu-id="64a58-205">Step 4: Test Your UE-V 2 Evaluation Deployment</span></span>


<span data-ttu-id="64a58-206">您現在可以在 UE-V 評估部署上執行一些測試，以瞭解 UE-V 的運作方式。</span><span class="sxs-lookup"><span data-stu-id="64a58-206">You can now run a few tests on your UE-V evaluation deployment to see how UE-V works.</span></span>

****

1.  <span data-ttu-id="64a58-207">在第一部電腦（電腦 A）上，進行下列其中一項或多項變更：</span><span class="sxs-lookup"><span data-stu-id="64a58-207">On the first computer (Computer A), make one or more of these changes:</span></span>

    1.  <span data-ttu-id="64a58-208">開啟至 Windows 桌面並將工作列移至視窗中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="64a58-208">Open to Windows Desktop and move the taskbar to a different location in the window.</span></span>

    2.  <span data-ttu-id="64a58-209">變更預設字型。</span><span class="sxs-lookup"><span data-stu-id="64a58-209">Change the default fonts.</span></span>

    3.  <span data-ttu-id="64a58-210">開啟 [計算機] 並設定為 [**科學**]。</span><span class="sxs-lookup"><span data-stu-id="64a58-210">Open Calculator and set to **scientific**.</span></span>

    4.  <span data-ttu-id="64a58-211">變更任何 Windows 應用程式的行為，如[管理使用 Windows PowerShell 和 WMI 的 ue-v A.x 設定位置範本](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="64a58-211">Change the behavior of any Windows app, as detailed in [Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    5.  <span data-ttu-id="64a58-212">停用 Microsoft 帳戶設定同步處理和漫遊設定檔。</span><span class="sxs-lookup"><span data-stu-id="64a58-212">Disable Microsoft Account settings synchronization and Roaming Profiles.</span></span>

2.  <span data-ttu-id="64a58-213">登出電腦 A：當使用者鎖定、登出、結束應用程式時，或同步處理提供程式執行時（每30分鐘預設），設定就會儲存在 UE-V 設定套件中。</span><span class="sxs-lookup"><span data-stu-id="64a58-213">Log off Computer A. Settings are saved in a UE-V settings package when users lock, logoff, exit an application, or when the sync provider runs (every 30 minutes by default).</span></span>

3.  <span data-ttu-id="64a58-214">登入第二部電腦（電腦 B）做為電腦 A 的同一個使用者。</span><span class="sxs-lookup"><span data-stu-id="64a58-214">Log in to the second computer (Computer B) as the same user as Computer A.</span></span>

4.  <span data-ttu-id="64a58-215">開啟至 Windows 桌面並確認工作列位置與電腦 A 相符。請確認預設字型相符，且該計算機已設定為**科學型**。</span><span class="sxs-lookup"><span data-stu-id="64a58-215">Open to Windows Desktop and verify that the taskbar location matches that of Computer A. Verify that the default fonts match and that Calculator is set to **scientific**.</span></span> <span data-ttu-id="64a58-216">此外，請確認您對任何 Windows app 所做的變更。</span><span class="sxs-lookup"><span data-stu-id="64a58-216">Also verify the change you made to any Windows app.</span></span>

<span data-ttu-id="64a58-217">您可以將電腦 B 中的設定變更回原始電腦的設定。</span><span class="sxs-lookup"><span data-stu-id="64a58-217">You can change the settings in Computer B back to the original Computer A settings.</span></span> <span data-ttu-id="64a58-218">然後登出電腦 B 並登入電腦 A 以驗證變更。</span><span class="sxs-lookup"><span data-stu-id="64a58-218">Then log off Computer B and log in to Computer A to verify the changes.</span></span>

## <span data-ttu-id="64a58-219">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="64a58-219">Other resources for this product</span></span>


-   [<span data-ttu-id="64a58-220">Microsoft 使用者體驗虛擬化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="64a58-220">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="64a58-221">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="64a58-221">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="64a58-222">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="64a58-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="64a58-223">疑難排解 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="64a58-223">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="64a58-224">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="64a58-224">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





