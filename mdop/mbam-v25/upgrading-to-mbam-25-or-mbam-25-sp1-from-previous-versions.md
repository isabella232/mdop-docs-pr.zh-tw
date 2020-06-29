---
title: 從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1
description: 從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800172"
---
# <span data-ttu-id="52fe1-103">從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="52fe1-103">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>


<span data-ttu-id="52fe1-104">本主題描述升級 Microsoft BitLocker 管理和監控（MBAM）伺服器以及舊版 MBAM 的 MBAM 用戶端的程式。</span><span class="sxs-lookup"><span data-stu-id="52fe1-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server and the MBAM Client from earlier versions of MBAM.</span></span>

<span data-ttu-id="52fe1-105">**記事** 您可以從任何舊版的 MBAM 直接升級至 MBAM 2.5 或 MBAM 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="52fe1-105">**Note** You can upgrade directly to MBAM 2.5 or MBAM 2.5 SP1 from any previous version of MBAM.</span></span>

 

## <span data-ttu-id="52fe1-106">開始升級前</span><span class="sxs-lookup"><span data-stu-id="52fe1-106">Before you start the upgrade</span></span>


<span data-ttu-id="52fe1-107">在您開始升級前，請先查看下列資訊。</span><span class="sxs-lookup"><span data-stu-id="52fe1-107">Review the following information before you start the upgrade.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52fe1-108">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="52fe1-108">What to know before you start</span></span></th>
<th align="left"><span data-ttu-id="52fe1-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="52fe1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52fe1-110">如果您要在一台伺服器上安裝 MBAM 網站，並在另一部伺服器上執行 web 服務，您必須使用 Windows PowerShell Cmdlet 來進行設定。</span><span class="sxs-lookup"><span data-stu-id="52fe1-110">If you are installing the MBAM websites on one server and the web services on another server, you have to use Windows PowerShell cmdlets to configure them.</span></span></p></td>
<td align="left"><p><span data-ttu-id="52fe1-111">MBAM Server 設定向導不支援在另一台伺服器上設定網站，也不支援在其他伺服器上設定 web 服務。</span><span class="sxs-lookup"><span data-stu-id="52fe1-111">The MBAM Server Configuration wizard does not support configuring the websites on one server and the web services on a different server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="52fe1-112">如果您要升級至 MBAM 2.5 或 2.5 SP1 （從 Windows Server2008 R2 中的 MBAM 2.0 或 2.0 SP1）：</span><span class="sxs-lookup"><span data-stu-id="52fe1-112">If you are upgrading to MBAM2.5 or 2.5 SP1 from MBAM2.0 or 2.0 SP1 in Windows Server2008 R2:</span></span></p>
<p><span data-ttu-id="52fe1-113">如果您在已安裝 Internet Information Services （IIS）之後安裝所需的 .NET Framework 4.5 軟體，管理和監控網站和自助服務入口網站將無法運作。</span><span class="sxs-lookup"><span data-stu-id="52fe1-113">The Administration and Monitoring Website and the Self-Service Portal will not work if you install the required .NET Framework4.5 software after Internet Information Services (IIS) is already installed.</span></span></p>
<p><span data-ttu-id="52fe1-114">發生此問題的原因是，如果在安裝 IIS 之後安裝 .NET Framework，則無法正確註冊 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="52fe1-114">This issue occurs because ASP.NET cannot be registered correctly with IIS if the .NET Framework is installed after IIS has already been installed.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="52fe1-115">若要解決此問題：</span><span class="sxs-lookup"><span data-stu-id="52fe1-115">To resolve this issue:</span></span></strong></p>
<p><span data-ttu-id="52fe1-116"><strong>從下列位置執行 aspnet_regiis – i </strong> ：</span><span class="sxs-lookup"><span data-stu-id="52fe1-116">Run <strong>aspnet_regiis –i</strong> from the following location:</span></span></p>
<p><span data-ttu-id="52fe1-117">C:\windows\microsoft.net\Framework\v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="52fe1-117">C:\windows\microsoft.net\Framework\v4.0.30319</span></span></p>
<p><span data-ttu-id="52fe1-118">如需詳細資訊，請參閱： <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 註冊工具 </a> 。</span><span class="sxs-lookup"><span data-stu-id="52fe1-118">For more information, see: <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)">ASP.NET IIS Registration Tool</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52fe1-119">如果符合下列所有條件，請在應用程式池帳戶上註冊 SPN：</span><span class="sxs-lookup"><span data-stu-id="52fe1-119">Register an SPN on the application pool account if all of the following are true:</span></span></p>
<ul>
<li><p><span data-ttu-id="52fe1-120">您要從舊版的 MBAM 升級。</span><span class="sxs-lookup"><span data-stu-id="52fe1-120">You are upgrading from a previous version of MBAM.</span></span></p></li>
<li><p><span data-ttu-id="52fe1-121">目前您不是在負載平衡或分散式設定中執行 MBAM 網站，但是當您升級至 MBAM 2.5 或 2.5 SP1 時，您會想要這麼做。</span><span class="sxs-lookup"><span data-stu-id="52fe1-121">Currently, you are not running the MBAM websites in a load-balanced or distributed configuration, but you would like to do so when you upgrade to MBAM2.5 or 2.5 SP1.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="52fe1-122">如需相關指示，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> 規劃如何保護 MBAM 網站的安全 </a> 。</span><span class="sxs-lookup"><span data-stu-id="52fe1-122">For instructions, see <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)">Planning How to Secure the MBAM Websites</a>.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="52fe1-123">我們建議的專案</span><span class="sxs-lookup"><span data-stu-id="52fe1-123">What we recommend</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="52fe1-124">登錄應用程式池帳戶的服務主體名稱（SPN），即使您可能已經為電腦帳戶註冊了 Spn 也一樣。</span><span class="sxs-lookup"><span data-stu-id="52fe1-124">Register a service principal name (SPN) for the application pool account, even though you may already have registered SPNs for the machine account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="52fe1-125">我們建議的原因</span><span class="sxs-lookup"><span data-stu-id="52fe1-125">Why we recommend it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="52fe1-126">您必須在應用程式池帳戶上註冊 SPN，才能在負載平衡或散佈配置中設定網站。</span><span class="sxs-lookup"><span data-stu-id="52fe1-126">Registering an SPN on the application pool account is required to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="52fe1-127">如果已在電腦帳戶上設定 Spn，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="52fe1-127">What happens if SPNs are already configured on a machine account?</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="52fe1-128">MBAM 會使用您已註冊的 Spn，而且您不需要設定其他 Spn，但您無法在負載平衡或散佈配置中設定網站。</span><span class="sxs-lookup"><span data-stu-id="52fe1-128">MBAM will use the SPNs that you have already registered, and you don’t need to configure additional SPNs, but you are not able to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="52fe1-129">升級 MBAM Server 基礎結構的步驟</span><span class="sxs-lookup"><span data-stu-id="52fe1-129">Steps to upgrade the MBAM Server infrastructure</span></span>


<span data-ttu-id="52fe1-130">使用下列各節中的步驟來升級獨立拓撲或 System Center Configuration Manager 整合拓撲的 MBAM。</span><span class="sxs-lookup"><span data-stu-id="52fe1-130">Use the steps in the following sections to upgrade MBAM for the Stand-alone topology or the System Center Configuration Manager Integration topology.</span></span>

**<span data-ttu-id="52fe1-131">若要升級獨立拓朴的 MBAM 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="52fe1-131">To upgrade the MBAM Server infrastructure for Stand-alone topology</span></span>**

1.  <span data-ttu-id="52fe1-132">從 [**程式和功能**] 和 [web 伺服器] 卸載舊版 MBAM，以確保資訊不會從 MBAM 用戶端寫入 MBAM 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="52fe1-132">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="52fe1-133">如需相關指示，請參閱[移除 MBAM Server 功能或軟體](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。</span><span class="sxs-lookup"><span data-stu-id="52fe1-133">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="52fe1-134">備份您的資料庫。</span><span class="sxs-lookup"><span data-stu-id="52fe1-134">Back up your databases.</span></span>

3.  <span data-ttu-id="52fe1-135">使用**程式和功能**從 sql Server 卸載舊版的 MBAM，包括透過 Sql Server Reporting SERVICES 託管 MBAM 報告的 sql server。</span><span class="sxs-lookup"><span data-stu-id="52fe1-135">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="52fe1-136">從資料庫伺服器和 reporting services 移除任何剩餘的 MBAM 伺服器臨時檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="52fe1-136">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

    <span data-ttu-id="52fe1-137">**記事** 資料庫將不會移除，而且所有合規性和復原資料都會保留在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="52fe1-137">**Note** The databases will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

4.  <span data-ttu-id="52fe1-138">依照該順序安裝及設定 MBAM 2.5 或 2.5 SP1 資料庫、報表及 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="52fe1-138">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, and web applications, in that order.</span></span> <span data-ttu-id="52fe1-139">資料庫已就地升級。</span><span class="sxs-lookup"><span data-stu-id="52fe1-139">The databases are upgraded in place.</span></span>

5.  <span data-ttu-id="52fe1-140">使用 MBAM 2.5 範本更新群組原則物件（Gpo），以利用 MBAM 中的新功能，例如強制加密。</span><span class="sxs-lookup"><span data-stu-id="52fe1-140">Update the Group Policy Objects (GPOs) using the MBAM 2.5 Templates to leverage the new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="52fe1-141">如果您沒有更新 Gpo，且 MBAM 用戶端無法 MBAM 2.5，舊版的 MBAM 用戶端將會繼續針對您目前的 Gpo 提供精簡功能的報告。</span><span class="sxs-lookup"><span data-stu-id="52fe1-141">If you do not update the GPOs and the MBAM client to MBAM 2.5, earlier versions of MBAM clients will continue to report against your current GPOs with reduced functionality.</span></span> <span data-ttu-id="52fe1-142">瞭解[如何取得您的 MDOP 群組原則（admx）範本](https://www.microsoft.com/download/details.aspx?id=41183)，以下載最新的 admx 範本。</span><span class="sxs-lookup"><span data-stu-id="52fe1-142">See [How to Get MDOP Group Policy (.admx) Templates](https://www.microsoft.com/download/details.aspx?id=41183) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="52fe1-143">在您升級 MBAM 伺服器基礎結構之後，現有的用戶端電腦會繼續成功地向 MBAM 2.5 或 2.5 SP1 伺服器進行報告，並繼續儲存恢復資料。</span><span class="sxs-lookup"><span data-stu-id="52fe1-143">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

6.  <span data-ttu-id="52fe1-144">安裝最新的 MBAM 2.5 或 2.5 SP1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="52fe1-144">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="52fe1-145">部署之後，用戶端電腦不需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="52fe1-145">Client computers do not need to be rebooted after the deployment.</span></span>

**<span data-ttu-id="52fe1-146">若要升級 System Center Configuration Manager 整合拓朴的 MBAM 基礎結構</span><span class="sxs-lookup"><span data-stu-id="52fe1-146">To upgrade the MBAM infrastructure for System Center Configuration Manager Integration topology</span></span>**

1.  <span data-ttu-id="52fe1-147">從 [**程式和功能**] 和 [web 伺服器] 卸載舊版 MBAM，以確保資訊不會從 MBAM 用戶端寫入 MBAM 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="52fe1-147">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="52fe1-148">如需相關指示，請參閱[移除 MBAM Server 功能或軟體](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)。</span><span class="sxs-lookup"><span data-stu-id="52fe1-148">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="52fe1-149">備份您的資料庫。</span><span class="sxs-lookup"><span data-stu-id="52fe1-149">Back up your databases.</span></span>

3.  <span data-ttu-id="52fe1-150">使用**程式和功能**從 sql Server 卸載舊版的 MBAM，包括透過 Sql Server Reporting SERVICES 託管 MBAM 報告的 sql server。</span><span class="sxs-lookup"><span data-stu-id="52fe1-150">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="52fe1-151">從資料庫伺服器和 reporting services 移除任何剩餘的 MBAM 伺服器臨時檔案或資料夾。</span><span class="sxs-lookup"><span data-stu-id="52fe1-151">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

4.  <span data-ttu-id="52fe1-152">從 Configuration Manager 伺服器卸載 MBAM。</span><span class="sxs-lookup"><span data-stu-id="52fe1-152">Uninstall MBAM from the Configuration Manager server.</span></span>

    <span data-ttu-id="52fe1-153">**記事** 資料庫與 Configuration Manager 物件（比較基準、MBAM 支援的電腦集合及報告）不會被移除，而且所有合規性和復原資料都會保留在資料庫中。</span><span class="sxs-lookup"><span data-stu-id="52fe1-153">**Note** The databases and the Configuration Manager objects (baseline, MBAM supported computers collection, and Reports) will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

5.  <span data-ttu-id="52fe1-154">更新 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="52fe1-154">Update the .mof files.</span></span>

6.  <span data-ttu-id="52fe1-155">安裝並設定 MBAM 2.5 或 2.5 SP1 資料庫、報表、web 應用程式及 Configuration Manager 整合（依順序）。</span><span class="sxs-lookup"><span data-stu-id="52fe1-155">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, web applications, and Configuration Manager integration, in that order.</span></span> <span data-ttu-id="52fe1-156">資料庫與 Configuration Manager 物件已就地升級。</span><span class="sxs-lookup"><span data-stu-id="52fe1-156">The databases and Configuration Manager objects are upgraded in place.</span></span>

7.  <span data-ttu-id="52fe1-157">或者，您也可以更新群組原則物件（Gpo），如果您想要在 MBAM 中執行新功能（例如強制加密），請編輯設定。</span><span class="sxs-lookup"><span data-stu-id="52fe1-157">Optionally, update the Group Policy Objects (GPOs), and edit the settings if you want to implement new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="52fe1-158">如果您沒有更新 Gpo，MBAM 將會繼續針對您目前的 Gpo 進行報告。</span><span class="sxs-lookup"><span data-stu-id="52fe1-158">If you do not update the GPOs, MBAM will continue to report against your current GPOs.</span></span> <span data-ttu-id="52fe1-159">瞭解[如何取得您的 MDOP 群組原則（admx）範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)，以下載最新的 admx 範本。</span><span class="sxs-lookup"><span data-stu-id="52fe1-159">See [How to Get MDOP Group Policy (.admx) Templates](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="52fe1-160">在您升級 MBAM 伺服器基礎結構之後，現有的用戶端電腦會繼續成功地向 MBAM 2.5 或 2.5 SP1 伺服器進行報告，並繼續儲存恢復資料。</span><span class="sxs-lookup"><span data-stu-id="52fe1-160">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

8.  <span data-ttu-id="52fe1-161">安裝最新的 MBAM 2.5 或 2.5 SP1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="52fe1-161">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="52fe1-162">部署之後，用戶端電腦不需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="52fe1-162">Client computers do not need to be rebooted after the deployment.</span></span>

## <span data-ttu-id="52fe1-163">MBAM 用戶端的升級支援</span><span class="sxs-lookup"><span data-stu-id="52fe1-163">Upgrade support for the MBAM Client</span></span>


<span data-ttu-id="52fe1-164">MBAM 支援從任何舊版的 MBAM 用戶端升級至 MBAM 2.5 用戶端。</span><span class="sxs-lookup"><span data-stu-id="52fe1-164">MBAM supports upgrades to the MBAM2.5 Client from any earlier version of the MBAM Client.</span></span>

**<span data-ttu-id="52fe1-165">安裝 MBAM 用戶端的方法：</span><span class="sxs-lookup"><span data-stu-id="52fe1-165">Ways to install the MBAM Client:</span></span>**

-   <span data-ttu-id="52fe1-166">在安裝 MBAM 2.5 伺服器基礎結構之後，立即或逐步升級執行 MBAM 用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="52fe1-166">Upgrade the computers running MBAM Client all at once or gradually after you install the MBAM2.5 Server infrastructure.</span></span>

-   <span data-ttu-id="52fe1-167">透過電子軟體發佈系統或透過工具（例如 Active Directory 網域服務或 System Center Configuration Manager）來安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="52fe1-167">Install the MBAM Client through an electronic software distribution system or through tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>



## <span data-ttu-id="52fe1-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="52fe1-168">Related topics</span></span>


[<span data-ttu-id="52fe1-169">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="52fe1-169">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="52fe1-170">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="52fe1-170">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="52fe1-171">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="52fe1-171">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="52fe1-172">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="52fe1-172">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="52fe1-173">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="52fe1-173">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="52fe1-174">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="52fe1-174">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





