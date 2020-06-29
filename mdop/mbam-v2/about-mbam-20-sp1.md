---
title: 關於 MBAM 2.0 SP1
description: 關於 MBAM 2.0 SP1
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810023"
---
# <span data-ttu-id="54c04-103">關於 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="54c04-103">About MBAM 2.0 SP1</span></span>

<span data-ttu-id="54c04-104">本主題描述 Microsoft BitLocker 管理和監控（MBAM） 2.0 Service Pack 1 （SP1）中的變更。</span><span class="sxs-lookup"><span data-stu-id="54c04-104">This topic describes the changes in Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="54c04-105">如需 MBAM 的一般描述，請參閱[MBAM 2.0 快速入門](getting-started-with-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="54c04-105">For a general description of MBAM, see [Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md).</span></span>

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a><span data-ttu-id="54c04-106">MBAM 2.0 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="54c04-106">What’s new in MBAM 2.0 SP1</span></span>

<span data-ttu-id="54c04-107">這個版本的 MBAM 會提供下列新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="54c04-107">This version of MBAM provides the following new features and functionality.</span></span>

### <span data-ttu-id="54c04-108">Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 Configuration Manager 支援</span><span class="sxs-lookup"><span data-stu-id="54c04-108">Support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="54c04-109">Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）新增 Windows 8.1、Windows Server 2012 R2 和 System Center 2012 R2 建構管理員的支援。</span><span class="sxs-lookup"><span data-stu-id="54c04-109">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager.</span></span>

### <span data-ttu-id="54c04-110">Microsoft SQL Server 2008 R2 SP2 支援</span><span class="sxs-lookup"><span data-stu-id="54c04-110">Support for Microsoft SQL Server 2008 R2 SP2</span></span>

<span data-ttu-id="54c04-111">Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）為 Microsoft SQL Server 2008 R2 SP2 新增支援。</span><span class="sxs-lookup"><span data-stu-id="54c04-111">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Microsoft SQL Server 2008 R2 SP2.</span></span> <span data-ttu-id="54c04-112">如果您正在執行 Microsoft System Center Configuration Manager 2007 R2，您必須使用 Microsoft SQL Server 2008 R2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="54c04-112">You must use Microsoft SQL Server 2008 R2 or higher if you are running Microsoft System Center Configuration Manager 2007 R2.</span></span>

### <span data-ttu-id="54c04-113">客戶意見反應匯總</span><span class="sxs-lookup"><span data-stu-id="54c04-113">Customer feedback rollup</span></span>

<span data-ttu-id="54c04-114">MBAM 2.0 SP1 包含一個修正程式，以解決從 Microsoft BitLocker 管理和監控（MBAM）2.0 發行後發現的問題。</span><span class="sxs-lookup"><span data-stu-id="54c04-114">MBAM 2.0 SP1 includes a rollup of fixes to address issues that were found since the Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 release.</span></span> <span data-ttu-id="54c04-115">在這些變更中，[電腦名稱稱] 欄位現在會出現在 [BitLocker 電腦合規性] 和 [BitLocker Enterprise 合規性詳細資料] 中，當您使用 Microsoft System Center Configuration Manager 2007 執行 MBAM 時就會顯示。</span><span class="sxs-lookup"><span data-stu-id="54c04-115">As part of these changes, the Computer Name field now appears in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007.</span></span>

### <span data-ttu-id="54c04-116">您必須在自助服務入口網站和 [管理與監控] 網站的埠上設定防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="54c04-116">Firewall exception must be set on ports for the Self-Service Portal and the Administration and Monitoring website</span></span>

<span data-ttu-id="54c04-117">當您設定自助入口網站和管理和監控網站時，您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="54c04-117">When you configure the Self-Service Portal and the Administration and Monitoring website, you must set a firewall exception to enable communication through the specified ports.</span></span> <span data-ttu-id="54c04-118">之前，MBAM 伺服器安裝會自動在 Windows 防火牆中開啟埠。</span><span class="sxs-lookup"><span data-stu-id="54c04-118">Previously, the MBAM server installation opened the ports automatically in Windows Firewall.</span></span>

### <span data-ttu-id="54c04-119">MBAM 報表的位置在 Configuration Manager 中已變更</span><span class="sxs-lookup"><span data-stu-id="54c04-119">Location of MBAM reports has changed in Configuration Manager</span></span>

<span data-ttu-id="54c04-120">您現在可以在 [MBAM] 節點中的子資料夾下取得 Configuration Manager 整合拓撲的 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-120">MBAM reports for the Configuration Manager integrated topology are now available under subfolders within the MBAM node.</span></span> <span data-ttu-id="54c04-121">子資料夾名稱代表子資料夾中報表的語言。</span><span class="sxs-lookup"><span data-stu-id="54c04-121">The subfolder names represent the language of the reports within the subfolder.</span></span>

### <span data-ttu-id="54c04-122">當您使用 Configuration Manager 安裝 MBAM 時，在主要網站伺服器上安裝 MBAM 的能力</span><span class="sxs-lookup"><span data-stu-id="54c04-122">Ability to install MBAM on a primary site server when you install MBAM with Configuration Manager</span></span>

<span data-ttu-id="54c04-123">當您使用 Configuration Manager 整合拓朴安裝 MBAM 時，您可以在主要的網站伺服器或管理中心網站伺服器上安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="54c04-123">You can install MBAM on a primary site server or a central administration site server when you install MBAM with the Configuration Manager integrated topology.</span></span> <span data-ttu-id="54c04-124">之前，您必須在管理中心網站伺服器上安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="54c04-124">Previously, you were required to install MBAM on a central administration site server.</span></span>

**<span data-ttu-id="54c04-125">重要</span><span class="sxs-lookup"><span data-stu-id="54c04-125">Important</span></span>**  
<span data-ttu-id="54c04-126">您在其上安裝 MBAM 的伺服器必須是階層中的最上層伺服器。</span><span class="sxs-lookup"><span data-stu-id="54c04-126">The server on which you install MBAM must be the top-tier server in your hierarchy.</span></span>



<span data-ttu-id="54c04-127">MBAM 安裝的運作方式適用于 Microsoft System Center Configuration Manager 2007 和 Microsoft System Center 2012 Configuration Manager，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54c04-127">The MBAM installation works differently for Microsoft System Center Configuration Manager 2007 and Microsoft System Center 2012 Configuration Manager as follows:</span></span>

-   <span data-ttu-id="54c04-128">**Configuration Manager 2007** ：如果您在屬於較大型 Configuration manager 階層的主要網站伺服器上安裝 MBAM，且擁有中央網站父伺服器，則 MBAM 會解析中心網站的父伺服器，並在該父伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="54c04-128">**Configuration Manager 2007** : If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy and has a central site parent server, MBAM resolves the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="54c04-129">安裝動作包括檢查先決條件及安裝 Configuration Manager 物件和報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-129">The installation actions include checking prerequisites and installing the Configuration Manager objects and reports.</span></span> <span data-ttu-id="54c04-130">例如，如果您在主要網站伺服器上安裝 MBAM，而該伺服器是中央網站父伺服器的子網站，MBAM 會在父伺服器上安裝所有 Configuration Manager 物件和報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-130">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="54c04-131">如果您在父伺服器上安裝 MBAM，MBAM 會在該父伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="54c04-131">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span>

-   <span data-ttu-id="54c04-132">**System Center 2012 Configuration Manager** ：如果您在主要的網站伺服器或管理中心伺服器上安裝 MBAM，MBAM 會在該網站伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="54c04-132">**System Center 2012 Configuration Manager** : If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span>

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> <span data-ttu-id="54c04-133">Configuration Manager 主控台必須安裝在您安裝 MBAM Server 的電腦上</span><span class="sxs-lookup"><span data-stu-id="54c04-133">Configuration Manager Console must be installed on the computer on which you install the MBAM Server</span></span>

<span data-ttu-id="54c04-134">當您使用 Configuration Manager 整合拓朴安裝 MBAM 時，您必須在安裝 MBAM 的同一部電腦上安裝 Configuration Manager 主控台。</span><span class="sxs-lookup"><span data-stu-id="54c04-134">When you install MBAM with the Configuration Manager integrated topology, you must install the Configuration Manager Console on the same computer on which MBAM will be installed.</span></span> <span data-ttu-id="54c04-135">如果您使用的是 [[開始使用 MBAM 搭配 Configuration manager](getting-started---using-mbam-with-configuration-manager.md)] 中所述的建議結構，您可以在 Configuration Manager 主要網站伺服器上安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="54c04-135">If you use the recommended architecture, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md), you would install MBAM on the Configuration Manager Primary Site Server.</span></span>

### <span data-ttu-id="54c04-136">Configuration Manager 整合拓朴的新設定命令列參數</span><span class="sxs-lookup"><span data-stu-id="54c04-136">New setup command-line parameters for the Configuration Manager integrated topology</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="54c04-137">命令列參數</span><span class="sxs-lookup"><span data-stu-id="54c04-137">Command-Line Parameter</span></span></th>
<th align="left"><span data-ttu-id="54c04-138">描述</span><span class="sxs-lookup"><span data-stu-id="54c04-138">Description</span></span></th>
<th align="left"><span data-ttu-id="54c04-139">範例</span><span class="sxs-lookup"><span data-stu-id="54c04-139">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="54c04-140">CM_SSRS_REMOTE_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="54c04-140">CM_SSRS_REMOTE_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-141">可讓您在遠端 SQL Server Reporting Services （SSRS）伺服器上安裝 Configuration Manager 報告，該伺服器屬於安裝 MBAM 的相同 Configuration Manager 網站。</span><span class="sxs-lookup"><span data-stu-id="54c04-141">Enables you to install the Configuration Manager reports on a remote SQL Server Reporting Services (SSRS) server that is part of the same Configuration Manager site to which MBAM is installed.</span></span> <span data-ttu-id="54c04-142">您可以將值設定為遠端 SSRS 點角色服務器的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="54c04-142">You can set the value to the fully qualified domain name of the remote SSRS point role server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer</span><span class="sxs-lookup"><span data-stu-id="54c04-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME=ssrsServer.Contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="54c04-144">CM_REPORTS_ONLY</span><span class="sxs-lookup"><span data-stu-id="54c04-144">CM_REPORTS_ONLY</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-145">可讓您只安裝 Configuration Manager 報表，而不需要其他 Configuration Manager 物件，例如比較基準、集合及設定專案。</span><span class="sxs-lookup"><span data-stu-id="54c04-145">Enables you to install only the Configuration Manager reports, without other Configuration Manager objects, such as the baseline, collection, and configuration items.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="54c04-146">注意</span><span class="sxs-lookup"><span data-stu-id="54c04-146">Note</span></span></strong><br/><p><span data-ttu-id="54c04-147">您必須將此參數與 CM_REPORTS_COLLECTION_ID 參數結合。</span><span class="sxs-lookup"><span data-stu-id="54c04-147">You must combine this parameter with the CM_REPORTS_COLLECTION_ID parameter.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="54c04-148">有效的參數值：</span><span class="sxs-lookup"><span data-stu-id="54c04-148">Valid parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="54c04-149">True</span><span class="sxs-lookup"><span data-stu-id="54c04-149">True</span></span></p></li>
<li><p><span data-ttu-id="54c04-150">False</span><span class="sxs-lookup"><span data-stu-id="54c04-150">False</span></span></p></li>
</ul>
<p><span data-ttu-id="54c04-151">如果您想要將報表只安裝至遠端 SSRS 點角色服務器，您可以將此參數與 CM_SSRS_REMOTE_SERVER_NAME 參數結合。</span><span class="sxs-lookup"><span data-stu-id="54c04-151">You can combine this parameter with the CM_SSRS_REMOTE_SERVER_NAME parameter if you want to install the reports only to a remote SSRS point role server.</span></span></p>
<p><span data-ttu-id="54c04-152">如果您沒有設定參數，或者如果您將它設為 False，MBAM 安裝程式會安裝所有 Configuration Manager 物件，包括報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-152">If you do not set the parameter or if you set it to False, MBAM Setup installs all of the Configuration Manager objects, including the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-153">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="54c04-153">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="54c04-154">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="54c04-154">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="54c04-155">CM_REPORTS_COLLECTION_ID</span><span class="sxs-lookup"><span data-stu-id="54c04-155">CM_REPORTS_COLLECTION_ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-156">現有的集合識別碼，可識別要顯示其報告合規性資料的集合。</span><span class="sxs-lookup"><span data-stu-id="54c04-156">An existing collection ID that identifies the collection for which reporting compliance data will be displayed.</span></span> <span data-ttu-id="54c04-157">您可以指定任何集合 ID。</span><span class="sxs-lookup"><span data-stu-id="54c04-157">You can specify any collection ID.</span></span> <span data-ttu-id="54c04-158">您不需要使用「MBAM 支援的電腦」集合 ID。</span><span class="sxs-lookup"><span data-stu-id="54c04-158">You are not required to use the “MBAM Supported Computers” collection ID.</span></span></p></td>
<td align="left"><p><span data-ttu-id="54c04-159">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="54c04-159">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="54c04-160">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="54c04-160">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="54c04-161">開啟或關閉自助入口網站通知文字的功能</span><span class="sxs-lookup"><span data-stu-id="54c04-161">Ability to turn Self-Service Portal notice text on or off</span></span>

<span data-ttu-id="54c04-162">MBAM 2.0 SP1 可讓您在自助服務入口網站上關閉通知文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-162">MBAM 2.0 SP1 enables you to turn off the notice text on the Self-Service Portal.</span></span> <span data-ttu-id="54c04-163">之前，預設會顯示通知文字，您無法將它關閉。</span><span class="sxs-lookup"><span data-stu-id="54c04-163">Previously, the notice text displayed by default, and you could not turn it off.</span></span>

**<span data-ttu-id="54c04-164">若要關閉通知文字</span><span class="sxs-lookup"><span data-stu-id="54c04-164">To turn off the notice text</span></span>**

1.  <span data-ttu-id="54c04-165">在您安裝自助入口網站的伺服器上，開啟 [網際網路資訊服務（IIS）]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="54c04-165">On the server where you installed the Self-Service Portal, open Internet Information Services (IIS) and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="54c04-166">從 [ **Name** ] （名稱）欄選取 [ **DisplayNotice**]，然後將值設定為**false**。</span><span class="sxs-lookup"><span data-stu-id="54c04-166">From the **Name** column, select **DisplayNotice**, and set the value to **false**.</span></span>

### <span data-ttu-id="54c04-167">能夠當地語系化將使用者指向更多自助入口網站資訊的 HelpdeskText 語句</span><span class="sxs-lookup"><span data-stu-id="54c04-167">Ability to localize the HelpdeskText statement that points users to more Self-Service Portal information</span></span>

<span data-ttu-id="54c04-168">您可以設定當地語系化版本的自助入口 "HelpdeskText" 語句，這會告訴使用者當他們使用自助入口網站時，如何取得其他協助。</span><span class="sxs-lookup"><span data-stu-id="54c04-168">You can configure a localized version of the Self-Service Portal “HelpdeskText” statement, which tells end users how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="54c04-169">如果您為語句設定當地語系化的文字，如下列指示所述，MBAM 將會顯示當地語系化版本。</span><span class="sxs-lookup"><span data-stu-id="54c04-169">If you configure localized text for the statement, as described in the following instructions, MBAM will display the localized version.</span></span> <span data-ttu-id="54c04-170">如果 MBAM 找不到已當地語系化的版本，則會顯示**HelpdeskText**參數中的值。</span><span class="sxs-lookup"><span data-stu-id="54c04-170">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

**<span data-ttu-id="54c04-171">顯示 HelpdeskText 語句的當地語系化版本</span><span class="sxs-lookup"><span data-stu-id="54c04-171">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="54c04-172">在您安裝自助入口網站的伺服器上，開啟 [IIS]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="54c04-172">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="54c04-173">在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="54c04-173">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="54c04-174">在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskText**\ _ &lt; *語言* &gt; ，其中 [ &lt; *語言*] &gt; 是該文字的適當語言代碼。</span><span class="sxs-lookup"><span data-stu-id="54c04-174">In the **Name** field, type **HelpdeskText**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the text.</span></span> <span data-ttu-id="54c04-175">例如，若要在西班牙文中建立當地語系化的 HelpdeskText 語句，您可以將參數命名為 HelpdeskText \ _es。</span><span class="sxs-lookup"><span data-stu-id="54c04-175">For example, to create a localized HelpdeskText statement in Spanish, you would name the parameter HelpdeskText\_es-es.</span></span> <span data-ttu-id="54c04-176">如需您可以使用之有效語言代碼的清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="54c04-176">For a list of the valid language codes that you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="54c04-177">在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-177">In the **Value** field, type the localized text that you want to display to end users.</span></span>

### <span data-ttu-id="54c04-178">當地語系化自助入口 HelpdeskURL 的能力</span><span class="sxs-lookup"><span data-stu-id="54c04-178">Ability to localize the Self-Service Portal HelpdeskURL</span></span>

<span data-ttu-id="54c04-179">您可以設定當地語系化版本的自助入口網站 HelpdeskURL，預設會顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="54c04-179">You can configure a localized version of the Self-Service Portal HelpdeskURL to display to end users by default.</span></span> <span data-ttu-id="54c04-180">如果您建立當地語系化版本，請參閱下列指示中的 MBAM 找出並顯示當地語系化版本。</span><span class="sxs-lookup"><span data-stu-id="54c04-180">If you create a localized version, as described in the following instructions, MBAM finds and displays the localized version.</span></span> <span data-ttu-id="54c04-181">如果 MBAM 找不到當地語系化版本，則會顯示針對 HelpDeskURL 參數設定的 URL。</span><span class="sxs-lookup"><span data-stu-id="54c04-181">If MBAM does not find a localized version, it displays the URL that is configured for the HelpDeskURL parameter.</span></span>

**<span data-ttu-id="54c04-182">若要顯示當地語系化的 HelpdeskURL</span><span class="sxs-lookup"><span data-stu-id="54c04-182">To display a localized HelpdeskURL</span></span>**

1.  <span data-ttu-id="54c04-183">在您安裝自助入口網站的伺服器上，開啟 [IIS]，然後流覽至 [**網站 &gt; Microsoft BitLocker 管理及監視 &gt; SelfService &gt; 應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="54c04-183">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="54c04-184">在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="54c04-184">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="54c04-185">在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskURL**\ _ &lt; *語言* &gt; ，其中 &lt; [*語言*] &gt; 是 URL 的適當語言代碼。</span><span class="sxs-lookup"><span data-stu-id="54c04-185">In the **Name** field, type **HelpdeskURL**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the URL.</span></span> <span data-ttu-id="54c04-186">例如，若要在西班牙文中建立當地語系化的 HelpdeskURL，您將會將參數命名為 HelpdeskURL \ _es。</span><span class="sxs-lookup"><span data-stu-id="54c04-186">For example, to create a localized HelpdeskURL in Spanish, you would name the parameter HelpdeskURL\_es-es.</span></span> <span data-ttu-id="54c04-187">如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="54c04-187">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="54c04-188">在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化 HelpdeskURL。</span><span class="sxs-lookup"><span data-stu-id="54c04-188">In the **Value** field, type the localized HelpdeskURL that you want to display to end users.</span></span>

### <span data-ttu-id="54c04-189">能夠當地語系化自助入口網站注意事項文字</span><span class="sxs-lookup"><span data-stu-id="54c04-189">Ability to localize the Self-Service Portal notice text</span></span>

<span data-ttu-id="54c04-190">您可以設定在自助入口網站中預設顯示給使用者的當地語系化通知文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-190">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="54c04-191">顯示通知文字的 notice.txt 檔案位於下列根目錄中：</span><span class="sxs-lookup"><span data-stu-id="54c04-191">The notice.txt file, which displays the notice text, is located in the following root directory:</span></span>

<span data-ttu-id="54c04-192">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="54c04-192">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="54c04-193">若要顯示當地語系化的聲明文字，您需要建立當地語系化的 notice.txt 檔案，並將它儲存在下列目錄中的特定語言資料夾中：</span><span class="sxs-lookup"><span data-stu-id="54c04-193">To display localized notice text, you create a localized notice.txt file and save it under a specific language folder in the following directory:</span></span>

<span data-ttu-id="54c04-194">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="54c04-194">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="54c04-195">MBAM 會根據下列規則顯示通知文字：</span><span class="sxs-lookup"><span data-stu-id="54c04-195">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="54c04-196">如果您在適當的語言資料夾中建立當地語系化的 notice.txt 檔案，MBAM 會顯示當地語系化的聲明文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-196">If you create a localized notice.txt file in the appropriate language folder, MBAM displays the localized notice text.</span></span>

-   <span data-ttu-id="54c04-197">如果 MBAM 找不到 notice.txt 檔案的當地語系化版本，則會顯示預設 notice.txt 檔案中的文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-197">If MBAM does not find a localized version of the notice.txt file, it displays the text in the default notice.txt file.</span></span>

-   <span data-ttu-id="54c04-198">如果 MBAM 找不到預設的 notice.txt 檔案，它會在自助入口網站中顯示預設文字。</span><span class="sxs-lookup"><span data-stu-id="54c04-198">If MBAM does not find a default notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

**<span data-ttu-id="54c04-199">注意</span><span class="sxs-lookup"><span data-stu-id="54c04-199">Note</span></span>**  
<span data-ttu-id="54c04-200">如果最終使用者的瀏覽器設定為沒有對應的語言子資料夾或 notice.txt 的語言，則會顯示位於下列根目錄中 notice.txt 檔案中的文字：</span><span class="sxs-lookup"><span data-stu-id="54c04-200">If an end user’s browser is set to a language that does not have a corresponding language subfolder or notice.txt, the text that is in the notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="54c04-201">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="54c04-201">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\



**<span data-ttu-id="54c04-202">建立當地語系化的 notice.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="54c04-202">To create a localized notice.txt file</span></span>**

1.  <span data-ttu-id="54c04-203">在您安裝自助入口網站的伺服器上，于 &lt; *language* &gt; 下列目錄中建立語言資料夾，其中的 &lt; *語言* &gt; 代表當地語系化語言的名稱：</span><span class="sxs-lookup"><span data-stu-id="54c04-203">On the server where you installed the Self-Service Portal, create a &lt;*language*&gt; folder in the following directory, where &lt;*language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="54c04-204">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="54c04-204">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    **<span data-ttu-id="54c04-205">注意</span><span class="sxs-lookup"><span data-stu-id="54c04-205">Note</span></span>**  
    <span data-ttu-id="54c04-206">某些語言資料夾已經存在，因此您可能不需要建立一個。</span><span class="sxs-lookup"><span data-stu-id="54c04-206">Some language folders already exist, so you may not have to create one.</span></span> <span data-ttu-id="54c04-207">如果您需要建立語言資料夾，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)，瞭解您可以用於 [語言] 資料夾的有效名稱清單 &lt; *language* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="54c04-207">If you do need to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*language*&gt; folder.</span></span>



2.  <span data-ttu-id="54c04-208">建立包含當地語系化通知文字的 notice.txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="54c04-208">Create a notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="54c04-209">將 notice.txt 檔案儲存于 [ &lt; *語言*] &gt; 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="54c04-209">Save the notice.txt file in the &lt;*language*&gt; folder.</span></span> <span data-ttu-id="54c04-210">例如，若要在西班牙文中建立當地語系化的 notice.txt 檔案，您可以將當地語系化的 notice.txt 檔案儲存在下列資料夾中：</span><span class="sxs-lookup"><span data-stu-id="54c04-210">For example, to create a localized notice.txt file in Spanish, you would save the localized notice.txt file in the following folder:</span></span>

    <span data-ttu-id="54c04-211">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\es-es</span><span class="sxs-lookup"><span data-stu-id="54c04-211">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\es-es</span></span>

## <span data-ttu-id="54c04-212">升級至 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="54c04-212">Upgrading to MBAM 2.0 SP1</span></span>


<span data-ttu-id="54c04-213">您可以從任何舊版的 MBAM 升級至 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="54c04-213">You can upgrade to MBAM 2.0 SP1 from any previous version of MBAM.</span></span>

### <span data-ttu-id="54c04-214">升級 MBAM 基礎結構</span><span class="sxs-lookup"><span data-stu-id="54c04-214">Upgrading the MBAM infrastructure</span></span>

<span data-ttu-id="54c04-215">您可以將 MBAM 伺服器基礎結構升級為 MBAM 2.0 SP1，如下所示：</span><span class="sxs-lookup"><span data-stu-id="54c04-215">You can upgrade the MBAM Server infrastructure to MBAM 2.0 SP1 as follows:</span></span>

<span data-ttu-id="54c04-216">**手動就地伺服器取代**：您必須手動卸載現有的 MBAM 伺服器基礎結構，然後再安裝 MBAM 2.0 SP1 server 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="54c04-216">**Manual in-place server replacement**: You must manually uninstall the existing MBAM Server infrastructure, and then install the MBAM 2.0 SP1 Server infrastructure.</span></span> <span data-ttu-id="54c04-217">您不需要移除資料庫即可進行升級。</span><span class="sxs-lookup"><span data-stu-id="54c04-217">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="54c04-218">相反地，您會選取先前版本的 MBAM 所建立的現有資料庫。</span><span class="sxs-lookup"><span data-stu-id="54c04-218">Instead, you select the existing databases, which the previous version of MBAM created.</span></span> <span data-ttu-id="54c04-219">MBAM 2.0 SP1 升級安裝，然後將現有的資料庫移轉至 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="54c04-219">The MBAM 2.0 SP1 upgrade installation then migrates the existing databases to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="54c04-220">**分散式用戶端升級**：如果您使用的是獨立 MBAM 拓朴，您可以在安裝 MBAM 2.0 SP1 伺服器基礎結構之後，逐漸升級 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="54c04-220">**Distributed client upgrade**: If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 SP1 Server infrastructure.</span></span>

<span data-ttu-id="54c04-221">在您升級 MBAM 伺服器基礎結構之後，MBAM 1.0 或2.0 用戶端會成功向 MBAM 2.0 SP1 伺服器報告並儲存修復資料，但合規性將根據目前已安裝的 MBAM 用戶端版本所提供的原則而定。</span><span class="sxs-lookup"><span data-stu-id="54c04-221">After you upgrade the MBAM Server infrastructure, MBAM 1.0 or 2.0 Clients will report to the MBAM 2.0 SP1 Server successfully and will store the recovery data, but compliance will be based on the policies available for the MBAM Client version that is currently installed.</span></span> <span data-ttu-id="54c04-222">若要針對 MBAM 2.0 SP1 原則啟用報告功能，您必須將用戶端電腦升級為 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="54c04-222">To enable reporting against MBAM 2.0 SP1 policies, you must upgrade client computers to MBAM 2.0 SP1.</span></span> <span data-ttu-id="54c04-223">您可以將用戶端電腦升級至 MBAM 2.0 SP1 用戶端，而不卸載先前的用戶端，而且用戶端將根據 MBAM 2.0 SP1 原則，開始套用並報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-223">You can upgrade the client computers to the MBAM 2.0 SP1 Client without uninstalling the previous Client, and the Client will start to apply and report, based on the MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="54c04-224">如需升級 MBAM 伺服器的詳細資訊，請參閱[從先前版本的 MBAM 升級](upgrading-from-previous-versions-of-mbam.md)。</span><span class="sxs-lookup"><span data-stu-id="54c04-224">For more information about upgrading the MBAM servers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

### <span data-ttu-id="54c04-225">將 MBAM 用戶端升級為 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="54c04-225">Upgrading the MBAM Client to MBAM 2.0 SP1</span></span>

<span data-ttu-id="54c04-226">若要將使用者電腦升級至 MBAM 2.0 SP1 用戶端，請在每個用戶端電腦上執行**MbamClientSetup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="54c04-226">To upgrade end-user computers to the MBAM 2.0 SP1 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="54c04-227">安裝程式會自動將用戶端更新至 MBAM 2.0 SP1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="54c04-227">The installer automatically updates the Client to the MBAM 2.0 SP1 Client.</span></span> <span data-ttu-id="54c04-228">安裝之後，用戶端電腦不需要重新開機，且 MBAM 2.0 SP1 用戶端就會開始套用 MBAM 2.0 SP1 原則，並針對其進行報告。</span><span class="sxs-lookup"><span data-stu-id="54c04-228">After the installation, client computers do not have to be rebooted, and the MBAM 2.0 SP1 Client starts to apply and report against MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="54c04-229">如果您使用的是 Configuration Manager 的 MBAM，您必須將 MBAM 用戶端電腦升級至 MBAM 2.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="54c04-229">If you are using MBAM with Configuration Manager, you must upgrade the MBAM client computers to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="54c04-230">如需升級 MBAM 用戶端電腦的詳細資訊，請參閱[從先前版本的 MBAM 升級](upgrading-from-previous-versions-of-mbam.md)。</span><span class="sxs-lookup"><span data-stu-id="54c04-230">For more information about upgrading the MBAM client computers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

## <span data-ttu-id="54c04-231">使用 Configuration Manager 安裝或升級至 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="54c04-231">Installing or upgrading to MBAM 2.0 SP1 with Configuration Manager</span></span>


<span data-ttu-id="54c04-232">本節說明當您安裝 MBAM 2.0 SP1 做為新安裝或升級到舊版 MBAM 2.0 SP1 時的需求。</span><span class="sxs-lookup"><span data-stu-id="54c04-232">This section describes the requirements when you are installing MBAM 2.0 SP1 as a new installation or as an upgrade to a previous MBAM 2.0 SP1 installation.</span></span>

### <span data-ttu-id="54c04-233">如果您使用 MBAM 與 Configuration Manager，請安裝 MBAM 2.0 SP1 所需的檔案</span><span class="sxs-lookup"><span data-stu-id="54c04-233">Required files for installing MBAM 2.0 SP1 if you are using MBAM with Configuration Manager</span></span>

<span data-ttu-id="54c04-234">如果您是第一次安裝 MBAM，而您是使用 MBAM 2.0 SP1 搭配 System Center Configuration Manager，您必須建立或編輯 mof 檔案，讓 MBAM 能夠正確地使用 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="54c04-234">If you are installing MBAM for the first time and you are using MBAM 2.0 SP1 with System Center Configuration Manager, you must create or edit mof files to enable MBAM to work correctly with Configuration Manager.</span></span>

-   **<span data-ttu-id="54c04-235">configuration mof 檔案</span><span class="sxs-lookup"><span data-stu-id="54c04-235">configuration.mof file</span></span>**

    -   <span data-ttu-id="54c04-236">如果您使用的是 Configuration Manager 2007，您必須編輯 configuration （mof 檔案）：**如果您升級至 MBAM 2.0 SP1，且您將 MBAM 與 Configuration Manager 2007 結合使用**（遵循此專案），則必須先更新 configuration （mof）檔。</span><span class="sxs-lookup"><span data-stu-id="54c04-236">If you are using Configuration Manager 2007, you must edit the configuration.mof file by completing step 3 from the item **Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007**, which follows this item.</span></span>

    -   <span data-ttu-id="54c04-237">如果您使用的是系統中心 2012 Configuration Manager，請按照[編輯 configuration. mof](edit-the-configurationmof-file.md)檔案中的指示編輯 configuration mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="54c04-237">If you are using System Center 2012 Configuration Manager, edit the configuration.mof file by following the instructions in [Edit the Configuration.mof File](edit-the-configurationmof-file.md).</span></span>

-   <span data-ttu-id="54c04-238">**sms \ _def 的 mof**檔案-依照[建立或編輯 sms \ _def mof](create-or-edit-the-sms-defmof-file.md)檔案中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="54c04-238">**sms\_def.mof file** – follow the instructions in [Create or Edit the Sms\_def.mof File](create-or-edit-the-sms-defmof-file.md).</span></span>

### <span data-ttu-id="54c04-239">如果您升級至 MBAM 2.0 SP1，且您將 MBAM 與 Configuration Manager 2007 結合使用，請更新 configuration mof 檔案</span><span class="sxs-lookup"><span data-stu-id="54c04-239">Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007</span></span>

<span data-ttu-id="54c04-240">如果您要升級至 MBAM 2.0 SP1，且您是使用 MBAM 搭配 Configuration Manager 2007，則您必須更新 configuration mof 檔案，以確保 MBAM 2.0 SP1 正常運作。</span><span class="sxs-lookup"><span data-stu-id="54c04-240">If you are upgrading to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007, you must update the configuration.mof file to ensure that MBAM 2.0 SP1 works correctly.</span></span>

**<span data-ttu-id="54c04-241">更新 configuration （mof）檔：</span><span class="sxs-lookup"><span data-stu-id="54c04-241">To update the configuration.mof file:</span></span>**

1.  <span data-ttu-id="54c04-242">在 Configuration Manager 伺服器上，流覽至 Configuration （mof）檔案的位置：</span><span class="sxs-lookup"><span data-stu-id="54c04-242">On the Configuration Manager Server, browse to the location of the Configuration.mof file:</span></span>

    <span data-ttu-id="54c04-243">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="54c04-243">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="54c04-244">在預設安裝中，安裝位置是%systemdrive%\\Program Files （x86） \\Microsoft Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="54c04-244">On a default installation, the installation location is %systemdrive%\\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="54c04-245">查看您在 configuration. mof 檔案中附加的程式碼區塊，然後將它刪除。</span><span class="sxs-lookup"><span data-stu-id="54c04-245">Review the block of code that you appended to the configuration.mof file, and delete it.</span></span> <span data-ttu-id="54c04-246">程式碼區塊會與下列步驟中所示類似。</span><span class="sxs-lookup"><span data-stu-id="54c04-246">The block of code will be similar to the one shown in the following step.</span></span>

3.  <span data-ttu-id="54c04-247">複製下列程式碼塊，然後將它附加到 configuration. mof 檔案中，將下列所需的 MBAM 類別新增到檔案中：</span><span class="sxs-lookup"><span data-stu-id="54c04-247">Copy the following block of code, and then append it to the configuration.mof file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### <span data-ttu-id="54c04-248">MBAM 2.0 SP1 的翻譯</span><span class="sxs-lookup"><span data-stu-id="54c04-248">Translation of MBAM 2.0 SP1</span></span>

<span data-ttu-id="54c04-249">MBAM 2.0 SP1 現已提供下列語言：</span><span class="sxs-lookup"><span data-stu-id="54c04-249">MBAM 2.0 SP1 is now available in the following languages:</span></span>

-   <span data-ttu-id="54c04-250">英文（美國） en</span><span class="sxs-lookup"><span data-stu-id="54c04-250">English (United States) en-US</span></span>
-   <span data-ttu-id="54c04-251">法文（法國） fr-fr</span><span class="sxs-lookup"><span data-stu-id="54c04-251">French (France) fr-FR</span></span>
-   <span data-ttu-id="54c04-252">義大利文（義大利） it</span><span class="sxs-lookup"><span data-stu-id="54c04-252">Italian (Italy) it-IT</span></span>
-   <span data-ttu-id="54c04-253">德國（德國） de</span><span class="sxs-lookup"><span data-stu-id="54c04-253">German (Germany) de-DE</span></span>
-   <span data-ttu-id="54c04-254">西班牙文，國際排序（西班牙） es</span><span class="sxs-lookup"><span data-stu-id="54c04-254">Spanish, International Sort (Spain) es-ES</span></span>
-   <span data-ttu-id="54c04-255">韓文（韓國） ko-KR</span><span class="sxs-lookup"><span data-stu-id="54c04-255">Korean (Korea) ko-KR</span></span>
-   <span data-ttu-id="54c04-256">日文（日本） ja-jp</span><span class="sxs-lookup"><span data-stu-id="54c04-256">Japanese (Japan) ja-JP</span></span>
-   <span data-ttu-id="54c04-257">葡萄牙文（巴西） pt-BR</span><span class="sxs-lookup"><span data-stu-id="54c04-257">Portuguese (Brazil) pt-BR</span></span>
-   <span data-ttu-id="54c04-258">俄文（俄羅斯） ru-RU</span><span class="sxs-lookup"><span data-stu-id="54c04-258">Russian (Russia) ru-RU</span></span>
-   <span data-ttu-id="54c04-259">繁體中文 zh-cn&platform-幼圓</span><span class="sxs-lookup"><span data-stu-id="54c04-259">Chinese Traditional zh-TW</span></span>
-   <span data-ttu-id="54c04-260">簡體中文 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="54c04-260">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="54c04-261">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="54c04-261">How to Get MDOP Technologies</span></span>

<span data-ttu-id="54c04-262">MBAM 2.0 SP1 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="54c04-262">MBAM 2.0 SP1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="54c04-263">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="54c04-263">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="54c04-264">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="54c04-264">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="54c04-265">相關主題</span><span class="sxs-lookup"><span data-stu-id="54c04-265">Related topics</span></span>

[<span data-ttu-id="54c04-266">MBAM 2.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="54c04-266">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)









