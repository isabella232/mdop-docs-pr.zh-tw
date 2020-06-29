---
title: 如何設定 MBAM 2.5 System Center Configuration Manager 整合
description: 如何設定 MBAM 2.5 System Center Configuration Manager 整合
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800095"
---
# <span data-ttu-id="62048-103">如何設定 MBAM 2.5 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="62048-103">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span>


<span data-ttu-id="62048-104">本主題說明如何設定 Microsoft BitLocker 管理與監視（MBAM），以使用系統中心 Configuration Manager 整合拓朴，將 MBAM 與 Configuration Manager 整合。</span><span class="sxs-lookup"><span data-stu-id="62048-104">This topic explains how to configure Microsoft BitLocker Administration and Monitoring (MBAM) to use the System Center Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span>

<span data-ttu-id="62048-105">這些指示說明如何使用以下專案來設定 Configuration Manager 整合：</span><span class="sxs-lookup"><span data-stu-id="62048-105">The instructions explain how to configure Configuration Manager Integration by using:</span></span>

-   <span data-ttu-id="62048-106">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="62048-106">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="62048-107">[MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="62048-107">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="62048-108">指示是以[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)中的建議架構為基礎。</span><span class="sxs-lookup"><span data-stu-id="62048-108">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="62048-109">開始設定前：</span><span class="sxs-lookup"><span data-stu-id="62048-109">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="62048-110">步驟</span><span class="sxs-lookup"><span data-stu-id="62048-110">Step</span></span></th>
<th align="left"><span data-ttu-id="62048-111">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="62048-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62048-112">針對 MBAM 查看建議的架構。</span><span class="sxs-lookup"><span data-stu-id="62048-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)"><span data-ttu-id="62048-113">MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構</span><span class="sxs-lookup"><span data-stu-id="62048-113">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62048-114">查看 MBAM 支援的設定。</span><span class="sxs-lookup"><span data-stu-id="62048-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="62048-115">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="62048-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62048-116">在每個伺服器上完成必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="62048-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="62048-117">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="62048-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="62048-118">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="62048-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62048-119">在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="62048-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="62048-120">注意</span><span class="sxs-lookup"><span data-stu-id="62048-120">Note</span></span></strong><br/><p><span data-ttu-id="62048-121">針對此拓朴，您必須在安裝 MBAM Server 軟體的電腦上安裝 Configuration Manager 主控台。</span><span class="sxs-lookup"><span data-stu-id="62048-121">For this topology, you must install the Configuration Manager console on the computer where you are installing the MBAM Server software.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="62048-122">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="62048-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62048-123">審查 Windows PowerShell 先決條件（只有在您要使用 Windows PowerShell Cmdlet 來設定 MBAM）時才適用。</span><span class="sxs-lookup"><span data-stu-id="62048-123">Review Windows PowerShell prerequisites (applicable only if you are going to use Windows PowerShell cmdlets to configure MBAM).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="62048-124">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="62048-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="62048-125">使用 Windows PowerShell 來設定 Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="62048-125">To configure Configuration Manager Integration by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="62048-126">開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="62048-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="62048-127">使用**Enable-MbamCMIntegration** Windows PowerShell Cmdlet 來設定報告。</span><span class="sxs-lookup"><span data-stu-id="62048-127">Use the **Enable-MbamCMIntegration** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="62048-128">若要取得此 Cmdlet 的相關資訊，請輸入**Get-help Enable-MbamCMIntegration**。</span><span class="sxs-lookup"><span data-stu-id="62048-128">To get information about this cmdlet, type **Get-Help Enable-MbamCMIntegration**.</span></span>

**<span data-ttu-id="62048-129">使用嚮導設定系統中心 Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="62048-129">To configure the System Center Configuration Manager Integration by using the wizard</span></span>**

1.  <span data-ttu-id="62048-130">在您想要設定 System Center Configuration Manager 整合功能的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="62048-130">On the server where you want to configure the System Center Configuration Manager Integration feature, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="62048-131">您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="62048-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2.  <span data-ttu-id="62048-132">按一下 [**新增功能**]，選取 [ **System Center Configuration Manager 整合**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="62048-132">Click **Add New Features**, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

    <span data-ttu-id="62048-133">嚮導會檢查是否符合 Configuration Manager 整合的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="62048-133">The wizard checks that all prerequisites for the Configuration Manager Integration have been met.</span></span>

3.  <span data-ttu-id="62048-134">如果先決條件檢查成功，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="62048-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="62048-135">否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="62048-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4.  <span data-ttu-id="62048-136">使用下列描述在嚮導中輸入欄位值：</span><span class="sxs-lookup"><span data-stu-id="62048-136">Use the following descriptions to enter the field values in the wizard:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="62048-137">欄位</span><span class="sxs-lookup"><span data-stu-id="62048-137">Field</span></span></th>
    <th align="left"><span data-ttu-id="62048-138">描述</span><span class="sxs-lookup"><span data-stu-id="62048-138">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="62048-139">SQL Server Reporting Services 伺服器</span><span class="sxs-lookup"><span data-stu-id="62048-139">SQL Server Reporting Services server</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="62048-140">具有 Reporting Services point 角色之伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="62048-140">Fully qualified domain name (FQDN) of the server with the Reporting Service point role.</span></span> <span data-ttu-id="62048-141">這是部署 MBAM Configuration Manager 報告的伺服器。</span><span class="sxs-lookup"><span data-stu-id="62048-141">This is the server to which the MBAM Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="62048-142">如果您沒有指定伺服器，Configuration Manager 報告將會部署到本機伺服器。</span><span class="sxs-lookup"><span data-stu-id="62048-142">If you don’t specify a server, the Configuration Manager Reports will be deployed to the local server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="62048-143">SQL Server Reporting Services 實例</span><span class="sxs-lookup"><span data-stu-id="62048-143">SQL Server Reporting Services instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="62048-144">部署 Configuration Manager 報表之 SQL Server Reporting Services （SSRS）實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="62048-144">Name of the SQL Server Reporting Services (SSRS) instance where the Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="62048-145">如果您沒有指定實例，Configuration Manager 報告將會部署到預設的 SSRS 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="62048-145">If you don’t specify an instance, the Configuration Manager Reports will be deployed to the default SSRS instance name.</span></span> <span data-ttu-id="62048-146">如果伺服器已安裝 System Center 2012 Configuration Manager，則會忽略您輸入的值。</span><span class="sxs-lookup"><span data-stu-id="62048-146">The value you enter is ignored if the server has System Center 2012 Configuration Manager installed.</span></span></p></td>
    </tr>
    </tbody>
    </table>



5.  <span data-ttu-id="62048-147">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="62048-147">On the **Summary** page, review the features that will be added.</span></span>

    **<span data-ttu-id="62048-148">注意</span><span class="sxs-lookup"><span data-stu-id="62048-148">Note</span></span>**  
    <span data-ttu-id="62048-149">若要建立您剛建立的專案的 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**] 並儲存腳本。</span><span class="sxs-lookup"><span data-stu-id="62048-149">To create a Windows PowerShell script of the entries you just made, click **Export PowerShell Script** and save the script.</span></span>



6.  <span data-ttu-id="62048-150">按一下 [**新增**]，將 Configuration Manager 整合功能新增至伺服器，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="62048-150">Click **Add** to add the Configuration Manager Integration feature to the server, and then click **Close**.</span></span>



## <span data-ttu-id="62048-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="62048-151">Related topics</span></span>


[<span data-ttu-id="62048-152">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="62048-152">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="62048-153">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="62048-153">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="62048-154">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="62048-154">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="62048-155">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="62048-155">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="62048-156">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="62048-156">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






