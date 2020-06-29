---
title: AGPM 4.0 SP1 的新功能
description: AGPM 4.0 SP1 的新功能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801702"
---
# <span data-ttu-id="0a253-103">AGPM 4.0 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="0a253-103">What's New in AGPM 4.0 SP1</span></span>


<span data-ttu-id="0a253-104">此「新增功能」內容描述 Microsoft 高級群組原則管理（AGPM） 4.0 SP1 的增強功能和支援的設定。</span><span class="sxs-lookup"><span data-stu-id="0a253-104">This “What’s New” content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="0a253-105">如果此內容與其他 AGPM 檔之間有差異，此內容應該被視為權威性，而且應該取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="0a253-105">If there is a difference between this content and other AGPM documentation, this content should be considered authoritative and should supersede the content included with this product.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="0a253-106">新功能</span><span class="sxs-lookup"><span data-stu-id="0a253-106">What’s new</span></span>


<span data-ttu-id="0a253-107">AGPM 4.0 SP1 支援下列增強功能：</span><span class="sxs-lookup"><span data-stu-id="0a253-107">AGPM 4.0 SP1 supports the following enhancements:</span></span>

### <span data-ttu-id="0a253-108">新的及變更的用戶端延伸</span><span class="sxs-lookup"><span data-stu-id="0a253-108">New and changed client-side extensions</span></span>

<span data-ttu-id="0a253-109">已針對 AGPM 新增或變更群組原則用戶端延伸（CSEs），以支援 Windows 8 和 Windows Server 2012 中的新群組原則。</span><span class="sxs-lookup"><span data-stu-id="0a253-109">Group Policy client-side extensions (CSEs) have been added or changed for AGPM to support new Group Policies in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="0a253-110">這些群組原則可讓群組原則管理員管理和追蹤在兩個群組原則物件（Gpo）或範本之間變更的 Windows 8 特定群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="0a253-110">These group policies enable Group Policy administrators to manage and track Windows 8-specific Group Policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="0a253-111">您也可以使用 Windows 8 專用的設定來建立自訂 Gpo，並設定並將 Gpo 儲存為範本。</span><span class="sxs-lookup"><span data-stu-id="0a253-111">You can also create custom GPOs, with Windows 8-specific settings, and configure and save the GPOs as a template.</span></span> <span data-ttu-id="0a253-112">若要查看您的 CSEs，請使用在 AGPM 4.0 SP1 用戶端中提供的 [設定] 和 [差異] 報告。</span><span class="sxs-lookup"><span data-stu-id="0a253-112">To view your CSEs, use the settings and difference reports that are available in the AGPM 4.0 SP1 client.</span></span>

<span data-ttu-id="0a253-113">新的和已變更的群組原則用戶端延伸為：</span><span class="sxs-lookup"><span data-stu-id="0a253-113">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="0a253-114">**中心存取原則：** 可讓群組原則管理員在群組原則伺服器上指定中心存取原則，例如，檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="0a253-114">**Central Access Policy:** Enables Group Policy administrators to specify Central Access Policies on Group Policy servers, for example, file servers.</span></span> <span data-ttu-id="0a253-115">[中心存取原則] 是由 GPO 專案所指定並套用至原則目標的授權原則，可協助集中存取及控制資源。</span><span class="sxs-lookup"><span data-stu-id="0a253-115">Central Access Policy is an authorization policy that is specified by a GPO item and applied to policy targets to facilitate centralized access and control of resources.</span></span> <span data-ttu-id="0a253-116">您必須在 Active Directory 中的群群組原則用戶端電腦上設定這些中心存取原則。</span><span class="sxs-lookup"><span data-stu-id="0a253-116">These Central Access Policies must be configured on a Group Policy client computer from within Active Directory.</span></span> <span data-ttu-id="0a253-117">群組原則會將適用之中心存取原則的知識發佈到必須強制執行的電腦上。</span><span class="sxs-lookup"><span data-stu-id="0a253-117">A Group Policy distributes the knowledge of an applicable Central Access Policy to the computers that have to enforce it.</span></span>

-   <span data-ttu-id="0a253-118">**名稱解析原則變更：** 可讓群組原則管理員在 DNS 用戶端電腦上設定 DNS 安全與 DirectAccess 的設定。</span><span class="sxs-lookup"><span data-stu-id="0a253-118">**Name Resolution Policy changes:** Enables Group Policy administrators to configure settings for DNS security and DirectAccess on DNS client computers.</span></span> <span data-ttu-id="0a253-119">已新增配置一般 DNS 伺服器設定和編碼設定的新索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0a253-119">New tabs for configuring Generic DNS Server settings and Encoding settings have been added.</span></span>

-   <span data-ttu-id="0a253-120">**群組原則喜好設定變更：** 新增針對 Windows 8 所新增之 Internet Explorer 10 設定的設定和管理的支援。</span><span class="sxs-lookup"><span data-stu-id="0a253-120">**Group Policy Preference changes:** Adds support for the configuration and management of Internet Explorer 10 settings that were added for Windows 8.</span></span>

-   <span data-ttu-id="0a253-121">**遠端應用程式和桌面連線：** 讓群組原則管理員指定用於遠端應用程式和桌面連線的預設連線 URL。</span><span class="sxs-lookup"><span data-stu-id="0a253-121">**Remote Application and Desktop Connections:** Lets Group Policy administrators specify the default connection URL that is used for Remote Application and Desktop Connections.</span></span>

-   <span data-ttu-id="0a253-122">**Windows 移至 [啟動] 選項：** 讓群組原則管理員設定在已連接包含 Windows To Go 工作區的 USB 裝置時，電腦是否會引導至 Windows。</span><span class="sxs-lookup"><span data-stu-id="0a253-122">**Windows To Go Startup Options:** Lets Group Policy administrators configure whether the computer will boot to Windows To Go if a USB device that contains a Windows To Go workspace is connected.</span></span>

-   <span data-ttu-id="0a253-123">**Windows To Go 休眠選項：** 可讓群組原則管理員設定電腦從 Windows 移至 [前往] 工作區時，電腦是否可以使用休眠睡眠狀態（S4）。</span><span class="sxs-lookup"><span data-stu-id="0a253-123">**Windows To Go Hibernate Options:** Lets Group Policy administrators configure whether a computer can use the hibernation sleep state (S4) when the computer is started from a Windows To Go workspace.</span></span>

### <span data-ttu-id="0a253-124">客戶意見反應與修補程式匯總</span><span class="sxs-lookup"><span data-stu-id="0a253-124">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="0a253-125">AGPM 4.0 SP1 包含修正在 AGPM 4.0 發行後發現問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="0a253-125">AGPM 4.0 SP1 includes a rollup of fixes to address issues found since the AGPM 4.0 release.</span></span> <span data-ttu-id="0a253-126">AGPM 4.0 SP1 包含最新的修正程式，包括 Microsoft 高級群組原則管理4.0 修正程式1。</span><span class="sxs-lookup"><span data-stu-id="0a253-126">AGPM 4.0 SP1 contains the latest fixes up to and including Microsoft Advanced Group Policy Management 4.0 Hotfix 1.</span></span>

### <span data-ttu-id="0a253-127">[設定與差異] 報告顯示新的群組原則延伸</span><span class="sxs-lookup"><span data-stu-id="0a253-127">Settings and difference reports show new Group Policy extensions</span></span>

<span data-ttu-id="0a253-128">新的群組原則延伸已新增至 [設定] 和 [差異] 報告中。</span><span class="sxs-lookup"><span data-stu-id="0a253-128">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="0a253-129">安裝程式變更與支援</span><span class="sxs-lookup"><span data-stu-id="0a253-129">Installer changes and support</span></span>

<span data-ttu-id="0a253-130">AGPM 4.0 SP1 安裝程式的變更與支援為：</span><span class="sxs-lookup"><span data-stu-id="0a253-130">The changes and support for the AGPM 4.0 SP1 installer are:</span></span>

-   <span data-ttu-id="0a253-131">如果您在 Windows 8 或 Windows Server 2012 上安裝 AGPM 4.0 SP1，AGPM 安裝程式會驗證是否已安裝所需的必備軟體（群組原則管理主控台和 .NET 3.5 架構）。</span><span class="sxs-lookup"><span data-stu-id="0a253-131">If you install AGPM 4.0 SP1 on Windows 8 or Windows Server 2012, the AGPM installer verifies that the required prerequisite software (Group Policy Management Console and the .NET 3.5 Framework) is installed.</span></span> <span data-ttu-id="0a253-132">如果未安裝這些必備元件，則會封鎖 AGPM 4.0 SP1 安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-132">If these prerequisites are not installed, the AGPM 4.0 SP1 installation is blocked.</span></span>

-   <span data-ttu-id="0a253-133">當您安裝 [AGPM 4.0 SP1]、[WCF 啟動]、[非 HTTP 啟用] 和 [Windows Process Activation Service] 時，系統會自動啟用。</span><span class="sxs-lookup"><span data-stu-id="0a253-133">When you install AGPM 4.0 SP1, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="0a253-134">在 Windows Vista、Windows 7 和 Windows 8 用戶端作業系統上，請先下載適用于您作業系統的遠端系統管理工具組版本，然後再安裝 AGPM 4.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="0a253-134">On Windows Vista, Windows 7, and Windows 8 client operating systems, download the appropriate version of the Remote System Administration Toolkit for your operating system before you install AGPM 4.0 SP1.</span></span>

-   <span data-ttu-id="0a253-135">支援與舊版支援的作業系統進行向後相容性。</span><span class="sxs-lookup"><span data-stu-id="0a253-135">Backward compatibility with older supported operating systems is supported.</span></span>

### <span data-ttu-id="0a253-136">能夠升級或更新到 AGPM 4.0 SP1，而不需重新輸入配置參數</span><span class="sxs-lookup"><span data-stu-id="0a253-136">Ability to upgrade or update to AGPM 4.0 SP1 without re-entering configuration parameters</span></span>

<span data-ttu-id="0a253-137">您只能從 AGPM 4.0 將 AGPM 用戶端或伺服器升級至 AGPM 4.0 SP1，而不會提示您重新輸入設定參數（稱為「智慧升級」），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="0a253-137">You can upgrade the AGPM client or server to AGPM 4.0 SP1 only from AGPM 4.0 without being prompted to re-enter configuration parameters (called “Smart Upgrade”), as shown in the following table.</span></span> <span data-ttu-id="0a253-138">如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP1 （如下表所示），您必須使用 [傳統升級]，這需要您重新輸入配置參數。</span><span class="sxs-lookup"><span data-stu-id="0a253-138">If you are upgrading to AGPM 4.0 SP1 from other versions of AGPM, as shown in the table, you must use the “Classic Upgrade,” which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="0a253-139">由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並在執行升級前，務必要升級作業系統。</span><span class="sxs-lookup"><span data-stu-id="0a253-139">Since each version of AGPM is associated with a particular operating system, refer to [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350), and be sure to upgrade your operating system as appropriate before performing an upgrade.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0a253-140">您可以升級的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="0a253-140">AGPM Version From Which You Can Upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-141">2.5</span><span class="sxs-lookup"><span data-stu-id="0a253-141">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-142">3.0</span><span class="sxs-lookup"><span data-stu-id="0a253-142">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-143">4.0</span><span class="sxs-lookup"><span data-stu-id="0a253-143">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-144">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="0a253-144">4.0 SP1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a253-145">2.5</span><span class="sxs-lookup"><span data-stu-id="0a253-145">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-146">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-146">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-147">傳統升級</span><span class="sxs-lookup"><span data-stu-id="0a253-147">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-148">傳統升級</span><span class="sxs-lookup"><span data-stu-id="0a253-148">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-149">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="0a253-149">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0a253-150">3.0</span><span class="sxs-lookup"><span data-stu-id="0a253-150">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-151">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-151">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-152">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-152">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-153">傳統升級</span><span class="sxs-lookup"><span data-stu-id="0a253-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-154">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="0a253-154">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a253-155">4.0</span><span class="sxs-lookup"><span data-stu-id="0a253-155">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-156">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-156">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-157">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-157">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-158">不適用</span><span class="sxs-lookup"><span data-stu-id="0a253-158">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-159">智慧升級</span><span class="sxs-lookup"><span data-stu-id="0a253-159">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0a253-160">支援的設定</span><span class="sxs-lookup"><span data-stu-id="0a253-160">Supported configurations</span></span>


<span data-ttu-id="0a253-161">AGPM 支援下表中的設定。</span><span class="sxs-lookup"><span data-stu-id="0a253-161">AGPM supports the configurations in the following table.</span></span> <span data-ttu-id="0a253-162">雖然 AGPM 支援混合式設定，但強烈建議您在相同的作業系統系列上執行 AGPM 用戶端和伺服器，例如 windows 8 與 Windows Server 2012、Windows 7 和 Windows Server 2008 R2 等。</span><span class="sxs-lookup"><span data-stu-id="0a253-162">Although AGPM supports mixed configurations, it is strongly recommended that you run the AGPM client and server on the same operating system family, for example, Windows 8 with Windows Server 2012, Windows 7 with Windows Server 2008 R2, and so on.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0a253-163">針對 AGPM 4.0 SP1 伺服器所支援的設定</span><span class="sxs-lookup"><span data-stu-id="0a253-163">Supported Configurations for AGPM 4.0 SP1 Server</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-164">適用于 AGPM 4.0 SP1 用戶端的支援配置</span><span class="sxs-lookup"><span data-stu-id="0a253-164">Supported Configurations for AGPM 4.0 SP1 Client</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0a253-165">AGPM 4.0 SP1 支援</span><span class="sxs-lookup"><span data-stu-id="0a253-165">AGPM 4.0 SP1 Support</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a253-166">Windows 8 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0a253-166">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-167">Windows 8 或 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0a253-167">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-168">支援</span><span class="sxs-lookup"><span data-stu-id="0a253-168">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0a253-169">Windows Server 2008 R2 或 Windows 7</span><span class="sxs-lookup"><span data-stu-id="0a253-169">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-170">Windows Server 2008 R2 或 Windows 7</span><span class="sxs-lookup"><span data-stu-id="0a253-170">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-171">支援，但無法編輯僅存在於 Windows 8 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="0a253-171">Supported, but cannot edit policy settings or preference items that exist only in Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a253-172">Windows Server 2008 R2 或 Windows 7 或 Windows 8 或 windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0a253-172">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-173">Windows Server 2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="0a253-173">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-174">支援，但無法編輯僅存在於 Windows Server 2008 R2 或 windows 7 或 Windows 8 中的原則設定或喜好設定專案。</span><span class="sxs-lookup"><span data-stu-id="0a253-174">Supported, but cannot edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0a253-175">Windows Server 2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="0a253-175">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-176">Windows Server 2008 R2 或 Windows 7 或 Windows 8 或 windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0a253-176">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-177">支援</span><span class="sxs-lookup"><span data-stu-id="0a253-177">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0a253-178">Windows Server 2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="0a253-178">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-179">Windows Server 2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="0a253-179">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a253-180">支援，但無法報告或編輯僅存在於 Windows Server 2008 R2 或 windows 7 或 Windows 8 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="0a253-180">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0a253-181">安裝 AGPM 4.0 SP1 的先決條件</span><span class="sxs-lookup"><span data-stu-id="0a253-181">Prerequisites for installing AGPM 4.0 SP1</span></span>


<span data-ttu-id="0a253-182">下表說明當 .NET 3.5 或遠端伺服器管理工具（RSAT）中的群組原則管理主控台遺失時，在 AGPM 4.0 SP1 用戶端和伺服器安裝程式的 Windows 8 上的行為。</span><span class="sxs-lookup"><span data-stu-id="0a253-182">The following table describes the behavior on Windows 8 of AGPM 4.0 SP1 client and server installers when .NET 3.5 or the Group Policy Management Console in the Remote Server Administration Tools (RSAT) is missing.</span></span>

**<span data-ttu-id="0a253-183">AGPM 用戶端 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="0a253-183">AGPM Client 4.0 SP1</span></span>**

**<span data-ttu-id="0a253-184">AGPM Server 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="0a253-184">AGPM Server 4.0 SP1</span></span>**

**<span data-ttu-id="0a253-185">作業系統</span><span class="sxs-lookup"><span data-stu-id="0a253-185">Operating System</span></span>**

**<span data-ttu-id="0a253-186">.NET</span><span class="sxs-lookup"><span data-stu-id="0a253-186">.NET</span></span>**

**<span data-ttu-id="0a253-187">RSAT</span><span class="sxs-lookup"><span data-stu-id="0a253-187">RSAT</span></span>**

**<span data-ttu-id="0a253-188">.NET</span><span class="sxs-lookup"><span data-stu-id="0a253-188">.NET</span></span>**

**<span data-ttu-id="0a253-189">RSAT</span><span class="sxs-lookup"><span data-stu-id="0a253-189">RSAT</span></span>**

**<span data-ttu-id="0a253-190">Windows8</span><span class="sxs-lookup"><span data-stu-id="0a253-190">Windows 8</span></span>**

<span data-ttu-id="0a253-191">如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-191">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="0a253-192">如果系統上未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-192">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

<span data-ttu-id="0a253-193">如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-193">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="0a253-194">如果系統上未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-194">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

**<span data-ttu-id="0a253-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0a253-195">Windows Server 2012</span></span>**

<span data-ttu-id="0a253-196">如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-196">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="0a253-197">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="0a253-197">If GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="0a253-198">如果未啟用或未安裝 .NET 3.5，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="0a253-198">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="0a253-199">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="0a253-199">If GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="0a253-200">相關主題</span><span class="sxs-lookup"><span data-stu-id="0a253-200">Related topics</span></span>


[<span data-ttu-id="0a253-201">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="0a253-201">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="0a253-202">Microsoft 進階群組原則管理 4.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="0a253-202">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





