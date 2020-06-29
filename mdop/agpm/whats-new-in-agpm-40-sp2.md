---
title: AGPM 4.0 SP2 的新功能
description: AGPM 4.0 SP2 的新功能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801701"
---
# <span data-ttu-id="3f460-103">AGPM 4.0 SP2 的新功能</span><span class="sxs-lookup"><span data-stu-id="3f460-103">What's New in AGPM 4.0 SP2</span></span>


<span data-ttu-id="3f460-104">此內容說明 Microsoft Advanced 群組原則管理（AGPM）4.0 服務 Pack2 （SP2）的增強功能和支援的設定。</span><span class="sxs-lookup"><span data-stu-id="3f460-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack2 (SP2).</span></span> <span data-ttu-id="3f460-105">如果此內容與其他 AGPM 檔之間有差異，請考慮此內容的權威性，並假設它取代其他檔。</span><span class="sxs-lookup"><span data-stu-id="3f460-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="3f460-106">新功能</span><span class="sxs-lookup"><span data-stu-id="3f460-106">What’s new</span></span>


<span data-ttu-id="3f460-107">AGPM 4.0 SP2 支援下列功能和功能。</span><span class="sxs-lookup"><span data-stu-id="3f460-107">AGPM4.0 SP2 supports the following features and functionality.</span></span>

### <span data-ttu-id="3f460-108">Windows 8.1 和 Windows Server2012 R2 的支援</span><span class="sxs-lookup"><span data-stu-id="3f460-108">Support for Windows8.1 and Windows Server2012 R2</span></span>

<span data-ttu-id="3f460-109">AGPM 4.0 SP2 新增 Windows 8.1 和 Windows Server2012 R2 作業系統的支援。</span><span class="sxs-lookup"><span data-stu-id="3f460-109">AGPM4.0 SP2 adds support for the Windows8.1 and Windows Server2012 R2 operating systems.</span></span>

### <span data-ttu-id="3f460-110">新的及變更的用戶端延伸</span><span class="sxs-lookup"><span data-stu-id="3f460-110">New and changed client-side extensions</span></span>

<span data-ttu-id="3f460-111">已新增或變更 AGPM 的群組原則用戶端延伸，以支援 Windows 8.1 中的新原則設定。</span><span class="sxs-lookup"><span data-stu-id="3f460-111">Group Policy client-side extensions have been added or changed for AGPM to support new policy settings in Windows8.1.</span></span> <span data-ttu-id="3f460-112">這些原則設定可讓群組原則管理員管理和追蹤在兩個群組原則物件（Gpo）或範本之間變更的 Windows 8.1 專用原則設定。</span><span class="sxs-lookup"><span data-stu-id="3f460-112">These policy settings enable Group Policy administrators to manage and track Windows8.1–specific policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="3f460-113">若要查看用戶端延伸，請使用在 AGPM 用戶端中提供的 [設定] 和 [差異] 報告。</span><span class="sxs-lookup"><span data-stu-id="3f460-113">To view your client-side extensions, use the settings and difference reports that are available in the AGPM Client.</span></span>

<span data-ttu-id="3f460-114">新的和已變更的群組原則用戶端延伸為：</span><span class="sxs-lookup"><span data-stu-id="3f460-114">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="3f460-115">**指定 [工作資料夾] 設定**。</span><span class="sxs-lookup"><span data-stu-id="3f460-115">**Specify Work Folders settings**.</span></span> <span data-ttu-id="3f460-116">如果您啟用此原則設定，IT 系統管理員可以將工作資料夾設定為自動建立。</span><span class="sxs-lookup"><span data-stu-id="3f460-116">If you enable this policy setting, IT administrators can configure Work Folders to be created automatically.</span></span> <span data-ttu-id="3f460-117">[工作資料夾] 功能可讓使用者將檔案從其 Windows 桌面裝置同步處理到其他裝置。</span><span class="sxs-lookup"><span data-stu-id="3f460-117">The Work Folders feature enables end users to synchronize files from their Windows desktop devices to their other devices.</span></span> <span data-ttu-id="3f460-118">使用此原則設定，在最終使用者的裝置上建立同步處理關聯，並設定如何識別儲存使用者工作資料夾的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f460-118">Use this policy setting to create the synchronization relationship on an end user’s devices and to configure how to identify the file server that stores the user’s Work Folders.</span></span> <span data-ttu-id="3f460-119">如果您選取 [**自動設定同步**處理] 核取方塊，就會建立不含使用者輸入的同步處理合作關係，而且資料會自動開始同步處理到使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="3f460-119">If you select the **Auto provision synchronization** check box, the synchronization partnership will be created without user input, and data will automatically start synchronizing to the user’s device.</span></span> <span data-ttu-id="3f460-120">如果您沒有選取 [**自動設定同步**處理] 核取方塊，使用者就必須提供輸入才能啟動同步處理。</span><span class="sxs-lookup"><span data-stu-id="3f460-120">If you do not select the **Auto provision synchronization** check box, users must provide input to start the synchronization.</span></span>

-   <span data-ttu-id="3f460-121">**針對所有使用者強制執行自動設定**。</span><span class="sxs-lookup"><span data-stu-id="3f460-121">**Force automatic setup for all users**.</span></span> <span data-ttu-id="3f460-122">如果您啟用此原則設定，IT 管理員可以決定是否要在最終使用者裝置上自動建立工作資料夾共同作業，而不需要使用者輸入。</span><span class="sxs-lookup"><span data-stu-id="3f460-122">If you enable this policy setting, IT administrators can determine whether to create the Work Folders partnership automatically on end-user devices without input from end users.</span></span> <span data-ttu-id="3f460-123">如果您啟用此原則設定，就會根據您設定 [**指定工作資料夾設定**] 策略設定的方式，來設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="3f460-123">If you enable this policy setting, the synchronization will be set up according to how you configure the **Specify Work Folders settings** policy setting.</span></span> <span data-ttu-id="3f460-124">如果您將 [**強制自動設定**] 策略設定為 [**已停用**] 或 [**未設定**]，則會根據您在 [**指定工作資料夾設定**] 設定策略設定中設定**自動提供**選項的方式，設定 [工作資料夾合作關係]。</span><span class="sxs-lookup"><span data-stu-id="3f460-124">If you set the **Force automatic setup for all users** policy setting to **Disabled** or **Not configured**, the Work Folders partnership will be configured according to how you set the **Automatic Provisioning** option in the **Specify Work Folders settings** policy setting.</span></span>

<span data-ttu-id="3f460-125">如需工作資料夾功能的詳細資訊，請參閱[工作資料夾概覽](https://go.microsoft.com/fwlink/?LinkId=330444)。</span><span class="sxs-lookup"><span data-stu-id="3f460-125">For more information about the Work Folders feature, see [Work Folders Overview](https://go.microsoft.com/fwlink/?LinkId=330444).</span></span>

### <span data-ttu-id="3f460-126">客戶意見反應與修補程式匯總</span><span class="sxs-lookup"><span data-stu-id="3f460-126">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="3f460-127">AGPM 4.0 SP2 包括修正在 AGPM 4.0 服務 Pack1 （SP1）發行後發現的問題的修復程式匯總。</span><span class="sxs-lookup"><span data-stu-id="3f460-127">AGPM4.0 SP2 includes a rollup of hotfixes to address issues found since the AGPM4.0 Service Pack1 (SP1) release.</span></span> <span data-ttu-id="3f460-128">AGPM 4.0 SP2 包含最新的修正程式，包括 Microsoft 高級群組原則管理 4.0 SP1 Hotfix1。</span><span class="sxs-lookup"><span data-stu-id="3f460-128">AGPM4.0 SP2 contains the latest fixes up to and including Microsoft Advanced Group Policy Management4.0 SP1 Hotfix1.</span></span> <span data-ttu-id="3f460-129">如需詳細資訊，請參閱知識庫文章[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)）。</span><span class="sxs-lookup"><span data-stu-id="3f460-129">For more information, see Knowledge Base article [2873472](https://go.microsoft.com/fwlink/?LinkId=325400)).</span></span>

### <span data-ttu-id="3f460-130">[設定] 和 [差異] 報告中的新群組原則延伸</span><span class="sxs-lookup"><span data-stu-id="3f460-130">New Group Policy extensions in settings and difference reports</span></span>

<span data-ttu-id="3f460-131">新的群組原則延伸已新增至 [設定] 和 [差異] 報告中。</span><span class="sxs-lookup"><span data-stu-id="3f460-131">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="3f460-132">安裝程式變更與支援</span><span class="sxs-lookup"><span data-stu-id="3f460-132">Installer changes and support</span></span>

<span data-ttu-id="3f460-133">AGPM 4.0 SP2 安裝程式的變更和支援包括：</span><span class="sxs-lookup"><span data-stu-id="3f460-133">The changes and support for the AGPM4.0 SP2 installer are:</span></span>

-   <span data-ttu-id="3f460-134">如果您在 Windows 8 或 Windows Server 2012 作業系統或更新版本的作業系統上安裝 AGPM 4.0 SP2，AGPM 安裝程式會驗證已安裝必要的必備軟體（群組原則管理主控台（GPMC）及 Microsoft .NET Framework 3.5）。</span><span class="sxs-lookup"><span data-stu-id="3f460-134">If you install AGPM4.0 SP2 on the Windows 8 or Windows Server 2012 operating system or later operating systems, the AGPM installer verifies that the required prerequisite software (the Group Policy Management Console (GPMC) and the Microsoft .NET Framework3.5) is installed.</span></span> <span data-ttu-id="3f460-135">如果未安裝此必備軟體，則會封鎖 AGPM 4.0 SP2 安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-135">If this prerequisite software is not installed, the AGPM4.0 SP2 installation is blocked.</span></span>

-   <span data-ttu-id="3f460-136">當您安裝 AGPM 服務器時，會自動啟用 WCF 啟用、非 HTTP 啟用和 Windows Process Activation Service。</span><span class="sxs-lookup"><span data-stu-id="3f460-136">When you install the AGPM Server, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="3f460-137">在 WindowsVista 用戶端作業系統及更新版本的作業系統上，在安裝 AGPM 4.0 SP2 之前，請先為您的作業系統下載適當版本的遠端系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="3f460-137">On the WindowsVista client operating system and later operating systems, download the appropriate version of the Remote System Administration Tools for your operating system before you install AGPM4.0 SP2.</span></span>

-   <span data-ttu-id="3f460-138">AGPM 4.0 SP2 支援與舊版支援的作業系統提供向後相容性。</span><span class="sxs-lookup"><span data-stu-id="3f460-138">AGPM4.0 SP2 supports backward compatibility with older supported operating systems.</span></span>

### <span data-ttu-id="3f460-139">能夠升級至 AGPM 4.0 SP2，而不需重新加入設定參數</span><span class="sxs-lookup"><span data-stu-id="3f460-139">Ability to upgrade to AGPM4.0 SP2 without reentering configuration parameters</span></span>

<span data-ttu-id="3f460-140">您可以將 AGPM 用戶端或 AGPM 服務器升級至 AGPM 4.0 SP2，而不會提示您重新輸入來自 AGPM 4.0 後的配置參數（稱為 [智慧升級]），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="3f460-140">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP2 without being prompted to reenter configuration parameters (called the Smart Upgrade) only from AGPM4.0 onward, as shown in the following table.</span></span> <span data-ttu-id="3f460-141">如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP2，如資料表所示，您必須使用 [傳統升級]，這需要您重新輸入配置參數。</span><span class="sxs-lookup"><span data-stu-id="3f460-141">If you are upgrading to AGPM4.0 SP2 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to reenter the configuration parameters.</span></span> <span data-ttu-id="3f460-142">由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並確認您在升級 AGPM 之前，請先升級您的作業系統。</span><span class="sxs-lookup"><span data-stu-id="3f460-142">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="3f460-143">AGPM 4.0 SP2 支援的升級</span><span class="sxs-lookup"><span data-stu-id="3f460-143">AGPM 4.0 SP2 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f460-144">您可以升級的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="3f460-144">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3f460-145">2.5</span><span class="sxs-lookup"><span data-stu-id="3f460-145">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3f460-146">3.0</span><span class="sxs-lookup"><span data-stu-id="3f460-146">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3f460-147">4.0</span><span class="sxs-lookup"><span data-stu-id="3f460-147">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3f460-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="3f460-148">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3f460-149">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="3f460-149">4.0 SP2</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f460-150">2.5</span><span class="sxs-lookup"><span data-stu-id="3f460-150">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-151">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-152">傳統升級</span><span class="sxs-lookup"><span data-stu-id="3f460-152">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-153">傳統升級</span><span class="sxs-lookup"><span data-stu-id="3f460-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-154">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="3f460-154">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-155">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="3f460-155">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f460-156">3.0</span><span class="sxs-lookup"><span data-stu-id="3f460-156">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-157">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-158">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-159">傳統升級</span><span class="sxs-lookup"><span data-stu-id="3f460-159">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-160">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="3f460-160">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-161">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="3f460-161">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f460-162">4.0</span><span class="sxs-lookup"><span data-stu-id="3f460-162">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-163">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-163">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-164">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-164">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-165">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-165">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-166">智慧升級</span><span class="sxs-lookup"><span data-stu-id="3f460-166">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-167">智慧升級</span><span class="sxs-lookup"><span data-stu-id="3f460-167">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f460-168">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="3f460-168">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-169">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-169">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-170">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-170">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-171">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-171">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-172">不適用</span><span class="sxs-lookup"><span data-stu-id="3f460-172">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-173">智慧升級</span><span class="sxs-lookup"><span data-stu-id="3f460-173">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3f460-174">支援的設定</span><span class="sxs-lookup"><span data-stu-id="3f460-174">Supported configurations</span></span>


<span data-ttu-id="3f460-175">AGPM 4.0 SP2 支援下表中的配置。</span><span class="sxs-lookup"><span data-stu-id="3f460-175">AGPM4.0 SP2 supports the configurations in the following table.</span></span> <span data-ttu-id="3f460-176">雖然 AGPM 支援混合式設定，但我們強烈建議您在相同的作業系統行上執行 AGPM 用戶端和 AGPM 服務器，例如，使用 Windows Server2012 R2、Windows 8 和 Windows Server 2012 的 windows 8.1 等。</span><span class="sxs-lookup"><span data-stu-id="3f460-176">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows8.1 with Windows Server2012 R2, Windows 8 with Windows Server 2012, and so on.</span></span>

**<span data-ttu-id="3f460-177">AGPM 4.0 SP2 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="3f460-177">AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="3f460-178">AGPM 服務器支援的設定</span><span class="sxs-lookup"><span data-stu-id="3f460-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="3f460-179">適用于 AGPM 用戶端的支援設定</span><span class="sxs-lookup"><span data-stu-id="3f460-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="3f460-180">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="3f460-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f460-181">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="3f460-181">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-182">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="3f460-182">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-183">支援</span><span class="sxs-lookup"><span data-stu-id="3f460-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f460-184">Windows Server2012 R2、Windows Server 2012、Windows 8.1 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="3f460-184">Windows Server2012 R2, Windows Server 2012, Windows8.1, or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-185">Windows Server 2012 或 Windows 8</span><span class="sxs-lookup"><span data-stu-id="3f460-185">Windows Server 2012 or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-186">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="3f460-186">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f460-187">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3f460-187">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-188">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3f460-188">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-189">支援，但無法編輯僅存在於 Windows 8.1 或 Windows 8 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="3f460-189">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1 or Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f460-190">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3f460-190">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-191">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="3f460-191">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-192">支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1、Windows 8 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="3f460-192">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f460-193">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="3f460-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-194">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="3f460-194">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-195">不支援</span><span class="sxs-lookup"><span data-stu-id="3f460-195">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f460-196">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="3f460-196">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-197">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="3f460-197">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f460-198">支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1、Windows 8 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="3f460-198">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3f460-199">安裝 AGPM 4.0 SP2 的先決條件</span><span class="sxs-lookup"><span data-stu-id="3f460-199">Prerequisites for installing AGPM4.0 SP2</span></span>


<span data-ttu-id="3f460-200">下表說明當 .NET Framework 3.5 或遠端伺服器管理工具中的 GPMC 遺失時，Windows 8.1 上的 AGPM 4.0 SP2 用戶端和伺服器安裝程式的行為。</span><span class="sxs-lookup"><span data-stu-id="3f460-200">The following table describes the behavior of AGPM4.0 SP2 Client and Server installers on Windows8.1 when the .NET Framework3.5 or the GPMC in the Remote Server Administration Tools is missing.</span></span>

**<span data-ttu-id="3f460-201">AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3f460-201">AGPM Client</span></span>**

**<span data-ttu-id="3f460-202">AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="3f460-202">AGPM Server</span></span>**

**<span data-ttu-id="3f460-203">作業系統</span><span class="sxs-lookup"><span data-stu-id="3f460-203">Operating system</span></span>**

**<span data-ttu-id="3f460-204">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f460-204">.NET Framework</span></span>**

**<span data-ttu-id="3f460-205">遠端伺服器管理工具</span><span class="sxs-lookup"><span data-stu-id="3f460-205">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="3f460-206">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f460-206">.NET Framework</span></span>**

**<span data-ttu-id="3f460-207">遠端伺服器管理工具</span><span class="sxs-lookup"><span data-stu-id="3f460-207">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="3f460-208">Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="3f460-208">Windows8.1</span></span>**

<span data-ttu-id="3f460-209">如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-209">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="3f460-210">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-210">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="3f460-211">如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-211">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="3f460-212">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-212">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

**<span data-ttu-id="3f460-213">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="3f460-213">Windows Server2012 R2</span></span>**

<span data-ttu-id="3f460-214">如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-214">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="3f460-215">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="3f460-215">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="3f460-216">如果沒有啟用或安裝 .NET Framework 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="3f460-216">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="3f460-217">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="3f460-217">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="3f460-218">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="3f460-218">How to Get MDOP Technologies</span></span>


<span data-ttu-id="3f460-219">AGPM 4.0 SP2 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f460-219">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="3f460-220">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="3f460-220">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="3f460-221">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="3f460-221">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="3f460-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="3f460-222">Related topics</span></span>


[<span data-ttu-id="3f460-223">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="3f460-223">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="3f460-224">Microsoft 進階群組原則管理 4.0 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="3f460-224">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP2</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[<span data-ttu-id="3f460-225">選擇要安裝的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="3f460-225">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





