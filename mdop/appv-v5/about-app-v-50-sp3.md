---
title: 關於 App-V 5.0 SP3
description: 關於 App-V 5.0 SP3
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800726"
---
# <span data-ttu-id="78328-103">關於 App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="78328-103">About App-V 5.0 SP3</span></span>


<span data-ttu-id="78328-104">使用下列各節，查看適用于 Microsoft Application Virtualization （App-v） 5.0 SP3 的重大變更資訊：</span><span class="sxs-lookup"><span data-stu-id="78328-104">Use the following sections to review information about significant changes that apply to Microsoft Application Virtualization (App-V) 5.0 SP3:</span></span>

-   [<span data-ttu-id="78328-105">App-V 5.0 SP3 軟體先決條件及支援的設定</span><span class="sxs-lookup"><span data-stu-id="78328-105">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>](#bkmk-sp3-prereq-configs)

-   [<span data-ttu-id="78328-106">遷移至 App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="78328-106">Migrating to App-V 5.0 SP3</span></span>](#bkmk-migrate-to-50sp3)

-   [<span data-ttu-id="78328-107">手動建立的連線群組 xml 檔案需要更新至架構</span><span class="sxs-lookup"><span data-stu-id="78328-107">Manually created connection group xml file requires update to schema</span></span>](#bkmk-update-schema-cg)

-   [<span data-ttu-id="78328-108">連線群組的改良功能</span><span class="sxs-lookup"><span data-stu-id="78328-108">Improvements to connection groups</span></span>](#bkmk-cg-improvements)

-   [<span data-ttu-id="78328-109">系統管理員可以發佈及取消發佈特定使用者的套件</span><span class="sxs-lookup"><span data-stu-id="78328-109">Administrators can publish and unpublish packages for a specific user</span></span>](#bkmk-usersid-pub-pkgs-specf-user)

-   [<span data-ttu-id="78328-110">僅允許系統管理員發佈及取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="78328-110">Enable only administrators to publish and unpublish packages</span></span>](#bkmk-admins-only-pub-unpub-pkgs)

-   [<span data-ttu-id="78328-111">RunVirtual 登錄機碼支援發佈給使用者的套件</span><span class="sxs-lookup"><span data-stu-id="78328-111">RunVirtual registry key supports packages that are published to the user</span></span>](#bkmk-runvirtual-reg-key)

-   [<span data-ttu-id="78328-112">新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="78328-112">New PowerShell cmdlets and updateable cmdlet help</span></span>](#bkmk-posh-cmdlets-help)

-   [<span data-ttu-id="78328-113">主要虛擬應用程式目錄（PVAD）已隱藏，但可以開啟</span><span class="sxs-lookup"><span data-stu-id="78328-113">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>](#bkmk-pvad-hidden)

-   [<span data-ttu-id="78328-114">需要 ClientVersion，才能查看 App-v 發佈中繼資料</span><span class="sxs-lookup"><span data-stu-id="78328-114">ClientVersion is required to view App-V publishing metadata</span></span>](#bkmk-pub-metadata-clientversion)

-   [<span data-ttu-id="78328-115">App-v 事件記錄已合併</span><span class="sxs-lookup"><span data-stu-id="78328-115">App-V event logs have been consolidated</span></span>](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a><span data-ttu-id="78328-116">App-V 5.0 SP3 軟體先決條件及支援的設定</span><span class="sxs-lookup"><span data-stu-id="78328-116">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>


<span data-ttu-id="78328-117">請參閱 App-V 5.0 SP3 軟體必備元件及支援的設定的下列連結。</span><span class="sxs-lookup"><span data-stu-id="78328-117">See the following links for the App-V 5.0 SP3 software prerequisites and supported configurations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-118">連結至先決條件和支援的設定</span><span class="sxs-lookup"><span data-stu-id="78328-118">Links to prerequisites and supported configurations</span></span></th>
<th align="left"><span data-ttu-id="78328-119">描述</span><span class="sxs-lookup"><span data-stu-id="78328-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)"><span data-ttu-id="78328-120">App-V 5.0 SP3 必要條件</span><span class="sxs-lookup"><span data-stu-id="78328-120">App-V 5.0 SP3 Prerequisites</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="78328-121">在啟動 App-v 5.0 SP3 安裝之前必須安裝的必備軟體</span><span class="sxs-lookup"><span data-stu-id="78328-121">Prerequisite software that you must install before starting the App-V 5.0 SP3 installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"><span data-ttu-id="78328-122">App-V 5.0 SP3 支援的組態</span><span class="sxs-lookup"><span data-stu-id="78328-122">App-V 5.0 SP3 Supported Configurations</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="78328-123">支援的作業系統與 App-v Server、Sequencer 及用戶端元件的硬體需求</span><span class="sxs-lookup"><span data-stu-id="78328-123">Supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client components</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a><span data-ttu-id="78328-124">遷移至 App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="78328-124">Migrating to App-V 5.0 SP3</span></span>


<span data-ttu-id="78328-125">使用下列資訊升級到舊版的 App-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="78328-125">Use the following information to upgrade to App-V 5.0 SP3 from earlier versions.</span></span>

### <span data-ttu-id="78328-126">開始升級前</span><span class="sxs-lookup"><span data-stu-id="78328-126">Before you start the upgrade</span></span>

<span data-ttu-id="78328-127">在您開始升級前，請先查看下列資訊：</span><span class="sxs-lookup"><span data-stu-id="78328-127">Review the following information before you start the upgrade:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-128">升級前要檢查的專案</span><span class="sxs-lookup"><span data-stu-id="78328-128">Items to review before upgrading</span></span></th>
<th align="left"><span data-ttu-id="78328-129">描述</span><span class="sxs-lookup"><span data-stu-id="78328-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-130">要升級的元件</span><span class="sxs-lookup"><span data-stu-id="78328-130">Components to upgrade</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="78328-131">App-v Server</span><span class="sxs-lookup"><span data-stu-id="78328-131">App-V Server</span></span></p></li>
<li><p><span data-ttu-id="78328-132">Midi</span><span class="sxs-lookup"><span data-stu-id="78328-132">Sequencer</span></span></p></li>
<li><p><span data-ttu-id="78328-133">App-V 用戶端或 App-v 遠端桌面服務（RDS）用戶端</span><span class="sxs-lookup"><span data-stu-id="78328-133">App-V client or App-V Remote Desktop Services (RDS) client</span></span></p></li>
<li><p><span data-ttu-id="78328-134">連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-134">Connection groups</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="78328-135">注意</span><span class="sxs-lookup"><span data-stu-id="78328-135">Note</span></span></strong><br/><p><span data-ttu-id="78328-136">若要使用應用程式-V 用戶端使用者介面，請從 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 用戶端 UI 應用程式下載現有版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-136">To use the App-V client user interface, download the existing version from <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)">Microsoft Application Virtualization 5.0 Client UI Application</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-137">從 App-v （V）升級</span><span class="sxs-lookup"><span data-stu-id="78328-137">Upgrading from App-V 4.x</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-138">您必須先升級到 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="78328-138">You must first upgrade to App-V 5.0.</span></span> <span data-ttu-id="78328-139">您無法直接從 App-v （即 app-v）升級到 App-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="78328-139">You cannot upgrade directly from App-V 4.x to App-V 5.0 SP3.</span></span></p>
<p><span data-ttu-id="78328-140">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="78328-140">For more information, see:</span></span></p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)"><span data-ttu-id="78328-141">關於 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="78328-141">About App-V 5.0</span></span></a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)"><span data-ttu-id="78328-142">規劃從舊版 App-V 移轉</span><span class="sxs-lookup"><span data-stu-id="78328-142">Planning for Migrating from a Previous Version of App-V</span></span></a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-143">從 App-v 5.0 或更新版本升級</span><span class="sxs-lookup"><span data-stu-id="78328-143">Upgrading from App-V 5.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-144">您可以直接從下列任何一個版本升級到 app-v 5.0 SP3：</span><span class="sxs-lookup"><span data-stu-id="78328-144">You can upgrade to App-V 5.0 SP3 directly from any of the following versions:</span></span></p>
<ul>
<li><p><span data-ttu-id="78328-145">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="78328-145">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="78328-146">App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="78328-146">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="78328-147">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="78328-147">App-V 5.0 SP2</span></span></p></li>
</ul>
<p><span data-ttu-id="78328-148">若要升級至 App-v 5.0 SP3，請按照本文其餘章節中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="78328-148">To upgrade to App-V 5.0 SP3, follow the steps in the remaining sections of this article.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-149">升級後對套件和連線群組所需的變更</span><span class="sxs-lookup"><span data-stu-id="78328-149">Required changes to packages and connection groups after upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-150">無。</span><span class="sxs-lookup"><span data-stu-id="78328-150">None.</span></span> <span data-ttu-id="78328-151">套件和連線群組會像目前一樣繼續運作。</span><span class="sxs-lookup"><span data-stu-id="78328-151">Packages and connection groups will continue to work as they currently do.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a><span data-ttu-id="78328-152">升級 App-v 基礎結構的步驟</span><span class="sxs-lookup"><span data-stu-id="78328-152">Steps to upgrade the App-V infrastructure</span></span>

<span data-ttu-id="78328-153">完成下列步驟，將 App-v 基礎結構的每個元件升級至 App-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="78328-153">Complete the following steps to upgrade each component of the App-V infrastructure to App-V 5.0 SP3.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-154">步驟</span><span class="sxs-lookup"><span data-stu-id="78328-154">Step</span></span></th>
<th align="left"><span data-ttu-id="78328-155">其他資訊</span><span class="sxs-lookup"><span data-stu-id="78328-155">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-156">步驟1：升級 App-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="78328-156">Step 1: Upgrade the App-V Server.</span></span></p>
<p><span data-ttu-id="78328-157">如果您不是使用 App-v Server，請跳過這個步驟，然後移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="78328-157">If you are not using the App-V Server, skip this step and go to the next step.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="78328-158">注意</span><span class="sxs-lookup"><span data-stu-id="78328-158">Note</span></span></strong><br/><p><span data-ttu-id="78328-159">App-V 5.0 SP3 用戶端與 App-v 5.0 SP1 Server 相容。</span><span class="sxs-lookup"><span data-stu-id="78328-159">The App-V 5.0 SP3 client is compatible with the App-V 5.0 SP1 Server.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="78328-160">請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="78328-160">Follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="78328-161">請參閱 <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> app-v 5.0 SP3 的版本資訊， </a> 以瞭解可能會影響 App V 伺服器安裝的問題。</span><span class="sxs-lookup"><span data-stu-id="78328-161">Review the <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)">Release Notes for App-V 5.0 SP3</a> for issues that may affect the App-V Server installation.</span></span></p></li>
<li><p><span data-ttu-id="78328-162">視您用來升級管理資料庫和/或報告資料庫的方法而定，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="78328-162">Do one of the following, depending on the method you are using to upgrade the Management database and/or Reporting database:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-163">資料庫升級方法</span><span class="sxs-lookup"><span data-stu-id="78328-163">Database upgrade method</span></span></th>
<th align="left"><span data-ttu-id="78328-164">步驟</span><span class="sxs-lookup"><span data-stu-id="78328-164">Step</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-165">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="78328-165">Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-166">跳過這個步驟，移至步驟3： [如果您要升級 App-v Server ...]</span><span class="sxs-lookup"><span data-stu-id="78328-166">Skip this step and go to step 3, “If you are upgrading the App-V Server...”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-167">SQL 腳本</span><span class="sxs-lookup"><span data-stu-id="78328-167">SQL scripts</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78328-168">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="78328-168">Management database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-169">若要安裝或升級，請參閱 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 安裝或升級 app-v 5.0 SP3 管理伺服器資料庫失敗的 SQL 腳本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-169">To install or upgrade, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78328-170">報表資料庫</span><span class="sxs-lookup"><span data-stu-id="78328-170">Reporting database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-171">依照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 腳本部署 App-v 資料庫的步驟進行 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-171">Follow the steps in <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">How to Deploy the App-V Databases by Using SQL Scripts</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p><span data-ttu-id="78328-172">如果您要從 App-v 5.0 SP1 修復程式套件3或更新版本升級 app-v Server，請完成 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> 安裝 app-v 5.0 SP3 Server 後檢查登錄機碼一節中的步驟 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-172">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in section <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)">Check registry keys after installing the App-V 5.0 SP3 Server</a>.</span></span></p></li>
<li><p><span data-ttu-id="78328-173">遵循 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> 如何部署 app-v 5.0 Server 的步驟進行 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-173">Follow the steps in <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">How to Deploy the App-V 5.0 Server</a>.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-174">步驟2：升級 App-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="78328-174">Step 2: Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-175">瞭解 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安裝排序器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-175">See <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">How to Install the Sequencer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-176">步驟3：升級 App-v 用戶端或 App-v RDS 用戶端。</span><span class="sxs-lookup"><span data-stu-id="78328-176">Step 3: Upgrade the App-V client or App-V RDS client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-177">瞭解 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 用戶端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-177">See <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a><span data-ttu-id="78328-178">安裝 App-v 5.0 SP3 Server 之前檢查登錄機碼</span><span class="sxs-lookup"><span data-stu-id="78328-178">Check registry keys before installing the App-V 5.0 SP3 Server</span></span>

<span data-ttu-id="78328-179">這是上表中的步驟3。</span><span class="sxs-lookup"><span data-stu-id="78328-179">This is step 3 from the previous table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78328-180">需要此步驟時</span><span class="sxs-lookup"><span data-stu-id="78328-180">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-181">您要從 App-v SP1 升級到您使用 .msp 檔案安裝的任何後續修復程式套件。</span><span class="sxs-lookup"><span data-stu-id="78328-181">You are upgrading from App-V SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78328-182">哪些元件需要您執行此步驟</span><span class="sxs-lookup"><span data-stu-id="78328-182">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-183">僅限您要升級的 App-v Server 元件。</span><span class="sxs-lookup"><span data-stu-id="78328-183">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78328-184">當您需要執行此步驟時</span><span class="sxs-lookup"><span data-stu-id="78328-184">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-185">將 App-v Server 升級至 App-v 5.0 SP3 之前</span><span class="sxs-lookup"><span data-stu-id="78328-185">Before you upgrade the App-V Server to App-V 5.0 SP3</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78328-186">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="78328-186">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-187">使用下清單格中的資訊， <code>HKLM\Software\Microsoft\AppV\Server</code> 以您在原始伺服器安裝中所提供的值來更新每個登錄項的值。</span><span class="sxs-lookup"><span data-stu-id="78328-187">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="78328-188">完成此步驟會還原在安裝 App-v SP1 修復程式套件時可能已移除的註冊表值。</span><span class="sxs-lookup"><span data-stu-id="78328-188">Completing this step restores registry values that may have been removed when App-V SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="78328-189">ManagementDatabase 鍵</span><span class="sxs-lookup"><span data-stu-id="78328-189">ManagementDatabase key</span></span>**

<span data-ttu-id="78328-190">如果您要安裝管理資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="78328-190">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-191">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="78328-191">Key name</span></span></th>
<th align="left"><span data-ttu-id="78328-192">描述</span><span class="sxs-lookup"><span data-stu-id="78328-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="78328-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-194">說明是否需要公用存取帳戶才能存取非本地管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="78328-194">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="78328-195">如果需要，值會設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="78328-195">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-196">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="78328-196">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-197">管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="78328-197">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-199">用於讀取（公開）管理資料庫存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="78328-199">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="78328-200">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="78328-200">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="78328-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-202">用來讀取（公開）管理資料庫存取權的帳戶的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="78328-202">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="78328-203">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="78328-203">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-204">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="78328-204">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-205">管理資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="78328-205">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="78328-206">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="78328-206">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-208">用於寫入管理資料庫（系統管理員）存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="78328-208">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="78328-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-210">用來撰寫（系統管理員）存取管理資料庫之帳戶的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="78328-210">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-212">管理伺服器遠端電腦帳戶（[域 \ 帳戶]）。</span><span class="sxs-lookup"><span data-stu-id="78328-212">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-214">管理伺服器（域 \ 帳戶）的安裝管理員登入。</span><span class="sxs-lookup"><span data-stu-id="78328-214">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="78328-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-216">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="78328-216">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="78328-217">1 </strong> -此管理服務是在本機電腦上，也就是 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 是空白的。</span><span class="sxs-lookup"><span data-stu-id="78328-217">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="78328-218">0 </strong> - 管理服務與本機電腦位於不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="78328-218">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="78328-219">ManagementService 鍵</span><span class="sxs-lookup"><span data-stu-id="78328-219">ManagementService key</span></span>**

<span data-ttu-id="78328-220">如果您要安裝管理伺服器，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。</span><span class="sxs-lookup"><span data-stu-id="78328-220">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-221">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="78328-221">Key name</span></span></th>
<th align="left"><span data-ttu-id="78328-222">描述</span><span class="sxs-lookup"><span data-stu-id="78328-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-223">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-223">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-224">已授權管理 App-v （網域 \ 帳戶）的 Active Directory 網域服務（AD DS）群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="78328-224">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-225">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="78328-225">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-226">包含管理資料庫的 SQL server 實例。</span><span class="sxs-lookup"><span data-stu-id="78328-226">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="78328-227">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="78328-227">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-228">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="78328-228">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-229">包含管理資料庫的遠端 SQL 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="78328-229">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="78328-230">如果此值為空白，則會使用本機電腦。</span><span class="sxs-lookup"><span data-stu-id="78328-230">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="78328-231">ReportingDatabase 鍵</span><span class="sxs-lookup"><span data-stu-id="78328-231">ReportingDatabase key</span></span>**

<span data-ttu-id="78328-232">如果您要安裝報告資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="78328-232">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-233">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="78328-233">Key name</span></span></th>
<th align="left"><span data-ttu-id="78328-234">描述</span><span class="sxs-lookup"><span data-stu-id="78328-234">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="78328-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-236">說明存取非本地報告資料庫是否需要公用存取帳戶。</span><span class="sxs-lookup"><span data-stu-id="78328-236">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="78328-237">如果需要，值會設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="78328-237">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-238">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="78328-238">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-239">報告資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="78328-239">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-241">用於讀取（公開）存取報表資料庫的帳戶。</span><span class="sxs-lookup"><span data-stu-id="78328-241">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="78328-242">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="78328-242">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="78328-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-244">帳戶的安全識別碼（SID），用於讀取（公開）的報表資料庫存取權。</span><span class="sxs-lookup"><span data-stu-id="78328-244">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="78328-245">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="78328-245">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-246">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="78328-246">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-247">報表資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="78328-247">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="78328-248">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="78328-248">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="78328-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-252">報表伺服器遠端電腦帳戶（[域 \ 帳戶]）。</span><span class="sxs-lookup"><span data-stu-id="78328-252">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="78328-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-254">報表服務器（域 \ 帳戶）的安裝管理員登入。</span><span class="sxs-lookup"><span data-stu-id="78328-254">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="78328-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-256">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="78328-256">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="78328-257">1 </strong> -報表服務位於本機電腦上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 為空白。</span><span class="sxs-lookup"><span data-stu-id="78328-257">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="78328-258">0 </strong> - 報表服務與本機電腦在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="78328-258">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="78328-259">ReportingService 鍵</span><span class="sxs-lookup"><span data-stu-id="78328-259">ReportingService key</span></span>**

<span data-ttu-id="78328-260">如果您要安裝報表伺服器，請在中設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。</span><span class="sxs-lookup"><span data-stu-id="78328-260">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-261">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="78328-261">Key name</span></span></th>
<th align="left"><span data-ttu-id="78328-262">描述</span><span class="sxs-lookup"><span data-stu-id="78328-262">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-263">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="78328-263">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-264">報表資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="78328-264">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="78328-265">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="78328-265">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-266">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="78328-266">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-267">具有報告資料庫之遠端 SQL 伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="78328-267">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="78328-268">如果此值為空白，則會使用本機電腦。</span><span class="sxs-lookup"><span data-stu-id="78328-268">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a><span data-ttu-id="78328-269">手動建立的連線群組 xml 檔案需要更新至架構</span><span class="sxs-lookup"><span data-stu-id="78328-269">Manually created connection group xml file requires update to schema</span></span>


<span data-ttu-id="78328-270">如果您要手動建立連線群組 XML 檔案，且想要使用新的「選用套件」和「使用任何版本」功能（在連線群組的[改善](#bkmk-cg-improvements)中所述），您必須在 XML 檔案中指定下列架構：</span><span class="sxs-lookup"><span data-stu-id="78328-270">If you are manually creating the connection group XML file, and want to use the new “optional packages” and “use any version” features that are described in [Improvements to connection groups](#bkmk-cg-improvements), you must specify the following schema in the XML file:</span></span>

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

<span data-ttu-id="78328-271">如需範例及詳細資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="78328-271">For examples and more information, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

## <a href="" id="bkmk-cg-improvements"></a><span data-ttu-id="78328-272">連線群組的改良功能</span><span class="sxs-lookup"><span data-stu-id="78328-272">Improvements to connection groups</span></span>


<span data-ttu-id="78328-273">您可以使用應用程式 V 5.0 SP3 中新增的選用套件和其他改進，更輕鬆地管理連線群組。</span><span class="sxs-lookup"><span data-stu-id="78328-273">You can manage connection groups more easily by using optional packages and other improvements that have been added in App-V 5.0 SP3.</span></span> <span data-ttu-id="78328-274">下表摘要列出您可以使用新的連線群組功能執行的工作，以及每個任務的詳細資訊連結。</span><span class="sxs-lookup"><span data-stu-id="78328-274">The following table summarizes the tasks that you can perform by using the new connection group features, and links to more detailed information about each task.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-275">任務/功能</span><span class="sxs-lookup"><span data-stu-id="78328-275">Task/feature</span></span></th>
<th align="left"><span data-ttu-id="78328-276">描述</span><span class="sxs-lookup"><span data-stu-id="78328-276">Description</span></span></th>
<th align="left"><span data-ttu-id="78328-277">詳細資訊的連結</span><span class="sxs-lookup"><span data-stu-id="78328-277">Links to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-278">讓連線群組包含選用套件</span><span class="sxs-lookup"><span data-stu-id="78328-278">Enable a connection group to include optional packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-279">在連線群組中包含選用套件，可讓您動態判斷哪些應用程式將包含在連線群組的虛擬環境中（根據使用者有資格使用的應用程式而定）。</span><span class="sxs-lookup"><span data-stu-id="78328-279">Including optional packages in a connection group enables you to dynamically determine which applications will be included in the connection group’s virtual environment, based on the applications that users are entitled to.</span></span></p>
<p><span data-ttu-id="78328-280">您不需要管理多個連線群組，因為您可以在同一個連接群組中混合選用和非選用的套件。</span><span class="sxs-lookup"><span data-stu-id="78328-280">You don’t need to manage as many connection groups because you can mix optional and non-optional packages in the same connection group.</span></span> <span data-ttu-id="78328-281">混合套件可讓不同的使用者群組使用相同的連線群組，即使使用者可能只有一個相同的套件也一樣。</span><span class="sxs-lookup"><span data-stu-id="78328-281">Mixing packages allows different groups of users to use the same connection group, even though users might have only one package in common.</span></span></p>
<p><strong><span data-ttu-id="78328-282">範例 </strong> ：您可以在 Microsoft Office 中為所有使用者啟用套件，但啟用不同的選擇性套件（包含不同的 Office 外掛程式）至不同的使用者子集。</span><span class="sxs-lookup"><span data-stu-id="78328-282">Example</strong>: You can enable a package with Microsoft Office for all users, but enable different optional packages, which contain different Office plug-ins, to different subsets of users.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="78328-283">如何在連線群組中使用選用套件</span><span class="sxs-lookup"><span data-stu-id="78328-283">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-284">取消發佈或刪除選用的套件，而不變更連接群組</span><span class="sxs-lookup"><span data-stu-id="78328-284">Unpublish or delete an optional package without changing the connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-285">取消發佈或刪除或取消發佈並重新發佈在連線群組中的選擇性套件，而不需要停用或重新啟用 App-v 用戶端的連線群組。</span><span class="sxs-lookup"><span data-stu-id="78328-285">Unpublish or delete, or unpublish and republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V client.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="78328-286">如何在連線群組中使用選用套件</span><span class="sxs-lookup"><span data-stu-id="78328-286">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-287">發佈包含使用者發佈及全域發佈套件的連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-287">Publish connection groups that contain user-published and globally published packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-288">建立使用者發佈的連線群組，其中包含使用者發佈及全域發佈的套件。</span><span class="sxs-lookup"><span data-stu-id="78328-288">Create a user-published connection group that contains user-published and globally published packages.</span></span></p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="78328-289">如何以使用者發佈的套件與全域發佈的套件建立連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-289">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-290">建立連線群組以忽略套件版本</span><span class="sxs-lookup"><span data-stu-id="78328-290">Make a connection group ignore the package version</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-291">將連線群組設定為接受任何版本的套件，這可讓您在不需停用連接群組的情況下升級套件。</span><span class="sxs-lookup"><span data-stu-id="78328-291">Configure a connection group to accept any version of a package, which enables you to upgrade a package without having to disable the connection group.</span></span> <span data-ttu-id="78328-292">此外，如果有選擇性套件的 [連線] 群組中有不正確的版本，套件會被忽略，而且不會封鎖連線群組的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="78328-292">In addition, if there is an optional package with an incorrect version in the connection group, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)"><span data-ttu-id="78328-293">如何讓連線群組略過套件版本</span><span class="sxs-lookup"><span data-stu-id="78328-293">How to Make a Connection Group Ignore the Package Version</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-294">限制最終使用者的發佈功能</span><span class="sxs-lookup"><span data-stu-id="78328-294">Limit end users’ publishing capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-295">僅允許系統管理員（而非最終使用者）發佈套件及啟用連線群組。</span><span class="sxs-lookup"><span data-stu-id="78328-295">Enable only administrators (not end users) to publish packages and to enable connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-296">如需連線群組的相關資訊，請參閱 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 如何只允許系統管理員啟用連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-296">For information about connection groups, see <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)">How to Allow Only Administrators to Enable Connection Groups</span></span></a></p>
<p><span data-ttu-id="78328-297">如需套件的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="78328-297">For information about packages, see the following articles:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-298">方法</span><span class="sxs-lookup"><span data-stu-id="78328-298">Method</span></span></th>
<th align="left"><span data-ttu-id="78328-299">連結至詳細資訊</span><span class="sxs-lookup"><span data-stu-id="78328-299">Link to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-300">管理主控台</span><span class="sxs-lookup"><span data-stu-id="78328-300">Management console</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)"><span data-ttu-id="78328-301">如何使用 Management Console 發佈套件</span><span class="sxs-lookup"><span data-stu-id="78328-301">How to Publish a Package by Using the Management Console</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-302">PowerShell</span><span class="sxs-lookup"><span data-stu-id="78328-302">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="78328-303">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-303">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-304">協力廠商電子軟體傳遞系統</span><span class="sxs-lookup"><span data-stu-id="78328-304">Third-party electronic software delivery system</span></span></p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)"><span data-ttu-id="78328-305">如何只讓系統管理員使用 ESD 來發佈套件</span><span class="sxs-lookup"><span data-stu-id="78328-305">How to Enable Only Administrators to Publish Packages by Using an ESD</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-306">啟用或停用特定使用者的連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-306">Enable or disable a connection group for a specific user</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-307">系統管理員可以使用 optional <strong> （UserSID） </strong> 參數與下列 Cmdlet 來啟用或停用特定使用者的連線群組：</span><span class="sxs-lookup"><span data-stu-id="78328-307">Administrators can enable or disable a connection group for a specific user by using the optional <strong>–UserSID</strong> parameter with the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="78328-308">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="78328-308">Enable-AppVClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="78328-309">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="78328-309">Disable-AppVClientConnectionGroup</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)"><span data-ttu-id="78328-310">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="78328-310">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-311">將相同的套件路徑合併成連接群組中的一個虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="78328-311">Merging identical package paths into one virtual directory in connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-312">如果連線群組中有兩個以上的套件包含完全相同的目錄路徑，則會將這些路徑合併到連線群組虛擬環境內的單一虛擬目錄中。</span><span class="sxs-lookup"><span data-stu-id="78328-312">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span></p>
<p><span data-ttu-id="78328-313">這種路徑合併可讓一個套件中的應用程式存取不同套件中的檔案。</span><span class="sxs-lookup"><span data-stu-id="78328-313">This merging of paths allows an application in one package to access files that are in a different package.</span></span></p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)"><span data-ttu-id="78328-314">關於連線群組虛擬環境</span><span class="sxs-lookup"><span data-stu-id="78328-314">About the Connection Group Virtual Environment</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a><span data-ttu-id="78328-315">系統管理員可以發佈及取消發佈特定使用者的套件</span><span class="sxs-lookup"><span data-stu-id="78328-315">Administrators can publish and unpublish packages for a specific user</span></span>


<span data-ttu-id="78328-316">系統管理員可以使用下列 Cmdlet 來發佈或取消發佈特定使用者的套件。</span><span class="sxs-lookup"><span data-stu-id="78328-316">Administrators can use the following cmdlets to publish or unpublish packages for a specific user.</span></span> <span data-ttu-id="78328-317">若要使用 Cmdlet，請輸入 **-UserSID**參數，後面接著使用者的安全性識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="78328-317">To use the cmdlets, enter the **–UserSID** parameter, followed by the user’s security identifier (SID).</span></span> <span data-ttu-id="78328-318">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="78328-318">For more information, see:</span></span>

-   [<span data-ttu-id="78328-319">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="78328-319">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="78328-320">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="78328-320">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-321">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78328-321">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="78328-322">範例</span><span class="sxs-lookup"><span data-stu-id="78328-322">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-323">發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="78328-323">Publish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-324">發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="78328-324">Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-325">取消發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="78328-325">Unpublish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-326">取消發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="78328-326">Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a><span data-ttu-id="78328-327">僅允許系統管理員發佈及取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="78328-327">Enable only administrators to publish and unpublish packages</span></span>


<span data-ttu-id="78328-328">您可以使用下列其中一種方法，僅啟用系統管理員（而非最終使用者）來發佈及取消發佈套件：</span><span class="sxs-lookup"><span data-stu-id="78328-328">You can enable only administrators (not end users) to publish and unpublish packages by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-329">方法</span><span class="sxs-lookup"><span data-stu-id="78328-329">Method</span></span></th>
<th align="left"><span data-ttu-id="78328-330">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="78328-330">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-331">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="78328-331">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-332">流覽至下列群群組原則物件節點：</span><span class="sxs-lookup"><span data-stu-id="78328-332">Navigate to the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="78328-333">[電腦設定 &gt; 原則] &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="78328-333">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</strong>.</span></span></p>
<p><span data-ttu-id="78328-334">啟用 [ <strong> 需要發佈為系統管理員] </strong> 群群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="78328-334">Enable the <strong>Require publish as administrator</strong> Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-335">PowerShell</span><span class="sxs-lookup"><span data-stu-id="78328-335">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)"><span data-ttu-id="78328-336">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="78328-336">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a><span data-ttu-id="78328-337">RunVirtual 登錄機碼支援發佈給使用者的套件</span><span class="sxs-lookup"><span data-stu-id="78328-337">RunVirtual registry key supports packages that are published to the user</span></span>


<span data-ttu-id="78328-338">App-v 5.0 SP3 新增了對使用**RunVirtual**登錄機碼與使用者發佈套件中的虛擬化應用程式的支援。</span><span class="sxs-lookup"><span data-stu-id="78328-338">App-V 5.0 SP3 adds support for using the **RunVirtual** registry key with virtualized applications that are in user-published packages.</span></span> <span data-ttu-id="78328-339">**RunVirtual**登錄機碼可讓您在虛擬環境中執行本機安裝的應用程式，以及使用 app-v 已虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="78328-339">The **RunVirtual** registry key lets you run a locally installed application in a virtual environment, along with applications that have been virtualized by using App-V.</span></span>

<span data-ttu-id="78328-340">之前，App-v 中的虛擬化應用程式必須全域發佈。</span><span class="sxs-lookup"><span data-stu-id="78328-340">Previously, the virtualized applications in App-V packages had to be published globally.</span></span> <span data-ttu-id="78328-341">如需更多關於**RunVirtual**和其他在虛擬環境中使用虛擬化應用程式執行本機安裝應用程式的方法，請參閱[使用虛擬化應用程式在虛擬環境中執行本機安裝的應用程式](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="78328-341">For more about **RunVirtual** and about other methods of running locally installed applications in a virtual environment with virtualized applications, see [Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md).</span></span>

## <a href="" id="bkmk-posh-cmdlets-help"></a><span data-ttu-id="78328-342">新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="78328-342">New PowerShell cmdlets and updateable cmdlet help</span></span>


<span data-ttu-id="78328-343">App-V 5.0 SP3 中包含新的 PowerShell Cmdlet 及可更新的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="78328-343">New PowerShell cmdlets and updateable cmdlet help are included in App-V 5.0 SP3.</span></span> <span data-ttu-id="78328-344">若要下載 Cmdlet 模組，請參閱[如何載入 PowerShell Cmdlet 及取得 Cmdlet](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)說明。</span><span class="sxs-lookup"><span data-stu-id="78328-344">To download the cmdlet modules, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets).</span></span>

### <span data-ttu-id="78328-345">新的 App-V 5.0 SP3 Server PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78328-345">New App-V 5.0 SP3 Server PowerShell cmdlets</span></span>

<span data-ttu-id="78328-346">已新增適用于 App-v Server 的新 Windows PowerShell Cmdlet，以協助您管理連線群組。</span><span class="sxs-lookup"><span data-stu-id="78328-346">New Windows PowerShell cmdlets for the App-V Server have been added to help you manage connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-347">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78328-347">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="78328-348">描述</span><span class="sxs-lookup"><span data-stu-id="78328-348">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-349">附加 AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="78328-349">Add-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-350">將套件附加到連線群組的結尾&#39;s 套件清單，並讓您將套件設定為選用，且在連線群組中不使用任何版本。</span><span class="sxs-lookup"><span data-stu-id="78328-350">Appends a package to the end of a connection group&#39;s package list and enables you to configure the package as optional and/or with no version within the connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-351">Set-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="78328-351">Set-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-352">可讓您編輯連線群組套件的詳細資料，例如，是否選用此選項。</span><span class="sxs-lookup"><span data-stu-id="78328-352">Enables you to edit details about the connection group package, such as whether it is optional.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-353">移除-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="78328-353">Remove-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-354">從連線群組中移除套件。</span><span class="sxs-lookup"><span data-stu-id="78328-354">Removes a package from a connection group.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="78328-355">取得 PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="78328-355">Getting help for the PowerShell cmdlets</span></span>

<span data-ttu-id="78328-356">以下格式提供 Cmdlet 說明：</span><span class="sxs-lookup"><span data-stu-id="78328-356">Cmdlet help is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-357">格式</span><span class="sxs-lookup"><span data-stu-id="78328-357">Format</span></span></th>
<th align="left"><span data-ttu-id="78328-358">說明</span><span class="sxs-lookup"><span data-stu-id="78328-358">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-359">以可下載的模組</span><span class="sxs-lookup"><span data-stu-id="78328-359">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-360">若要在下載 Cmdlet 模組之後取得最新的協助：</span><span class="sxs-lookup"><span data-stu-id="78328-360">To get the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="78328-361">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="78328-361">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="78328-362">輸入下列其中一個命令來載入您想要的模組的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="78328-362">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-363">App-v 元件</span><span class="sxs-lookup"><span data-stu-id="78328-363">App-V component</span></span></th>
<th align="left"><span data-ttu-id="78328-364">輸入的命令</span><span class="sxs-lookup"><span data-stu-id="78328-364">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-365">App-v Server</span><span class="sxs-lookup"><span data-stu-id="78328-365">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-366">更新-協助-模組 AppvServer</span><span class="sxs-lookup"><span data-stu-id="78328-366">Update-Help-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-367">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="78328-367">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-368">更新-協助-模組 AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="78328-368">Update-Help-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-369">App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="78328-369">App-V client</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-370">更新-協助-模組 AppvClient</span><span class="sxs-lookup"><span data-stu-id="78328-370">Update-Help-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-371">在 TechNet 上為網頁</span><span class="sxs-lookup"><span data-stu-id="78328-371">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-372">請參閱 Microsoft 桌上出版 [優化套件自動化] 下的 app-v 節點， <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> 以使用 Windows PowerShell </a> 。</span><span class="sxs-lookup"><span data-stu-id="78328-372">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="78328-373">如需詳細資訊，請參閱[如何載入 PowerShell Cmdlet 及取得 Cmdlet](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)說明。</span><span class="sxs-lookup"><span data-stu-id="78328-373">For more information, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md).</span></span>

## <a href="" id="bkmk-pvad-hidden"></a><span data-ttu-id="78328-374">主要虛擬應用程式目錄（PVAD）已隱藏，但可以開啟</span><span class="sxs-lookup"><span data-stu-id="78328-374">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>


<span data-ttu-id="78328-375">主虛擬應用程式目錄（PVAD）在 App-v 5.0 SP3 中是隱藏的，但您可以重新開啟它，並使用下列其中一種方法讓它可見：</span><span class="sxs-lookup"><span data-stu-id="78328-375">The primary virtual application directory (PVAD) is hidden in App-V 5.0 SP3, but you can turn it back on and make it visible by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-376">方法</span><span class="sxs-lookup"><span data-stu-id="78328-376">Method</span></span></th>
<th align="left"><span data-ttu-id="78328-377">步驟</span><span class="sxs-lookup"><span data-stu-id="78328-377">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78328-378">使用命令列參數</span><span class="sxs-lookup"><span data-stu-id="78328-378">Use a command line parameter</span></span></p></td>
<td align="left"><p><span data-ttu-id="78328-379">將 <strong> – EnablePVADControl </strong> 參數傳遞到 <strong>Sequencer.exe</strong> 。</span><span class="sxs-lookup"><span data-stu-id="78328-379">Pass the <strong>–EnablePVADControl</strong> parameter to the <strong>Sequencer.exe</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78328-380">建立登錄子機碼</span><span class="sxs-lookup"><span data-stu-id="78328-380">Create a registry subkey</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="78328-381">在 [登錄編輯程式] 中，流覽至：</span><span class="sxs-lookup"><span data-stu-id="78328-381">In the Registry Editor, navigate to:</span></span> <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong><span data-ttu-id="78328-382">注意</span><span class="sxs-lookup"><span data-stu-id="78328-382">Note</span></span></strong><br/><p><span data-ttu-id="78328-383">如果 <code>Compatibility</code> 該子機不存在，您就必須建立它。</span><span class="sxs-lookup"><span data-stu-id="78328-383">If the <code>Compatibility</code> subkey doesn’t exist, you must create it.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="78328-384">建立名為 EnablePVADControl 的 DWORD 值 <strong> </strong> ，並將該值設定為 <strong> 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="78328-384">Create a DWORD Value named <strong>EnablePVADControl</strong>, and set the value to <strong>1</strong>.</span></span></p>
<p><span data-ttu-id="78328-385">值為 <strong> 0 </strong> 表示 PVAD 已隱藏。</span><span class="sxs-lookup"><span data-stu-id="78328-385">A value of <strong>0</strong> means that PVAD is hidden.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>



<span data-ttu-id="78328-386">**更多關於 PVAD 的資訊：** 當您使用 Sequencer 建立套件時，您可以輸入套件的任何安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="78328-386">**More about PVAD:** When you use the Sequencer to create a package, you can enter any installation path for the package.</span></span> <span data-ttu-id="78328-387">在過去的 App-v 版本中，您必須指定應用程式的主要虛擬應用程式目錄（PVAD）作為路徑。</span><span class="sxs-lookup"><span data-stu-id="78328-387">In past versions of App-V, you were required to specify the primary virtual application directory (PVAD) of the application as the path.</span></span> <span data-ttu-id="78328-388">PVAD 是您通常在本機電腦上安裝應用程式的目錄（如果您使用的是 App-v）。</span><span class="sxs-lookup"><span data-stu-id="78328-388">PVAD is the directory to which you would typically install an application on your local computer if you weren’t using App-V.</span></span> <span data-ttu-id="78328-389">例如，如果您在電腦上安裝 Office，則 PVAD 通常會 C:\\program files Files\\Microsoft Office\\。</span><span class="sxs-lookup"><span data-stu-id="78328-389">For example, if you were installing Office on a computer, the PVAD typically would be C:\\Program Files\\Microsoft Office\\.</span></span>

## <a href="" id="bkmk-pub-metadata-clientversion"></a><span data-ttu-id="78328-390">需要 ClientVersion，才能查看 App-v 發佈中繼資料</span><span class="sxs-lookup"><span data-stu-id="78328-390">ClientVersion is required to view App-V publishing metadata</span></span>


<span data-ttu-id="78328-391">在 App-V 5.0 SP3 中，當您查詢 app-v 發佈伺服器以取得中繼資料時，您必須在位址中提供下列值：</span><span class="sxs-lookup"><span data-stu-id="78328-391">In App-V 5.0 SP3, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78328-392">值</span><span class="sxs-lookup"><span data-stu-id="78328-392">Value</span></span></th>
<th align="left"><span data-ttu-id="78328-393">其他詳細資料</span><span class="sxs-lookup"><span data-stu-id="78328-393">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="78328-394">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="78328-394">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-395">如果您省略 <strong> 查詢的 ClientVersion </strong> 參數，中繼資料會排除新的 APP-V 5.0 SP3 功能。</span><span class="sxs-lookup"><span data-stu-id="78328-395">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the new App-V 5.0 SP3 features.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="78328-396">ClientOS</span><span class="sxs-lookup"><span data-stu-id="78328-396">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="78328-397">您必須在順序套件時選取特定用戶端作業系統，才能提供這個值。</span><span class="sxs-lookup"><span data-stu-id="78328-397">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="78328-398">如果您選取 [預設（所有作業系統）]，請勿在查詢中指定這個值。</span><span class="sxs-lookup"><span data-stu-id="78328-398">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="78328-399">如果您在查詢中省略 <strong> ClientOS </strong> 參數，則只有已排序支援任何作業系統的套件才會出現在中繼資料中。</span><span class="sxs-lookup"><span data-stu-id="78328-399">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="78328-400">如需此查詢的語法及範例，請參閱[查看 App-v Server 發佈中繼資料](viewing-app-v-server-publishing-metadata.md)。</span><span class="sxs-lookup"><span data-stu-id="78328-400">For syntax and examples of this query, see [Viewing App-V Server Publishing Metadata](viewing-app-v-server-publishing-metadata.md).</span></span>

## <a href="" id="bkmk-event-logs-moved"></a><span data-ttu-id="78328-401">App-v 事件記錄已合併</span><span class="sxs-lookup"><span data-stu-id="78328-401">App-V event logs have been consolidated</span></span>


<span data-ttu-id="78328-402">已將下列事件記錄（先前位於**應用程式和服務記錄/microsoft/appv/ &lt; app-v 元件 &gt; **）移至**應用程式和服務記錄/microsoft/appv/ServiceLog**。</span><span class="sxs-lookup"><span data-stu-id="78328-402">The following event logs, previously located at **Applications and Services Logs/Microsoft/AppV/&lt;App-V component&gt;**, have been moved to **Applications and Services Logs/Microsoft/AppV/ServiceLog**.</span></span>

<span data-ttu-id="78328-403">若要查看記錄，請**選取** &gt; [事件檢視器] 應用程式中的 [**顯示分析記錄及調試記錄**]。</span><span class="sxs-lookup"><span data-stu-id="78328-403">To view the logs, select **View** &gt; **Show Analytic and Debug Logs** in the Event Viewer application.</span></span>

<span data-ttu-id="78328-404">用戶端-目錄用戶端整合用戶端-Orchestration 用戶端-PackageConfig 用戶端-腳本用戶端-服務用戶端-Vemgr 用戶端-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary 子系統-ActiveX 子系統-AppPath 子系統-Com 子系統-fta</span><span class="sxs-lookup"><span data-stu-id="78328-404">Client-Catalog Client-Integration Client-Orchestration Client-PackageConfig Client-Scripting Client-Service Client-Vemgr Client-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary Subsystems-ActiveX Subsystems-AppPath Subsystems-Com Subsystems-fta</span></span>

## <span data-ttu-id="78328-405">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="78328-405">How to Get MDOP Technologies</span></span>


<span data-ttu-id="78328-406">App-v 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="78328-406">App-V is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="78328-407">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="78328-407">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="78328-408">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="78328-408">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="78328-409">相關主題</span><span class="sxs-lookup"><span data-stu-id="78328-409">Related topics</span></span>


[<span data-ttu-id="78328-410">App-V 5.0 SP3 版本資訊</span><span class="sxs-lookup"><span data-stu-id="78328-410">Release Notes for App-V 5.0 SP3</span></span>](release-notes-for-app-v-50-sp3.md)









