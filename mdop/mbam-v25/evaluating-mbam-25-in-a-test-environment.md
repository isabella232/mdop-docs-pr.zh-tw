---
title: 在測試環境中評估 MBAM 2.5
description: 在測試環境中評估 MBAM 2.5
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809783"
---
# <span data-ttu-id="3362d-103">在測試環境中評估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3362d-103">Evaluating MBAM 2.5 in a Test Environment</span></span>


<span data-ttu-id="3362d-104">本主題描述如何在獨立或 System Center Configuration Manager 整合拓撲中設定測試環境來評估 Microsoft BitLocker 管理和監控（MBAM）2.5。</span><span class="sxs-lookup"><span data-stu-id="3362d-104">This topic describes how you can set up a test environment to evaluate Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in the Stand-alone or System Center Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="3362d-105">使用獨立拓朴評估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="3362d-105">Evaluating MBAM 2.5 by using the Stand-alone topology</span></span>


<span data-ttu-id="3362d-106">若要使用獨立拓朴評估 MBAM，請使用下清單格中的資訊來安裝 MBAM 伺服器軟體，然後在測試環境中設定 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-106">To evaluate MBAM by using the Stand-alone topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span>

**<span data-ttu-id="3362d-107">使用獨立拓朴評估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="3362d-107">To evaluate MBAM 2.5 by using the Stand-alone topology</span></span>**

1. <span data-ttu-id="3362d-108">在安裝 MBAM 前，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-108">Before installing MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-109">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-109">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-110">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-110">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-111">確定您已安裝所有必備軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-111">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="3362d-112">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="3362d-112">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-113">檢查所需的硬體、RAM 及其他規格。</span><span class="sxs-lookup"><span data-stu-id="3362d-113">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="3362d-114">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="3362d-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-115">如果您打算使用 Cmdlet 來設定 MBAM，請查看使用 Windows PowerShell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="3362d-115">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="3362d-116">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="3362d-116">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="3362d-117">安裝 MBAM Server 軟體，然後設定您想要的功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-117">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-118">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-118">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-119">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-119">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-120">在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-120">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="3362d-121">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="3362d-121">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-122">設定合規性和審核資料庫及恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="3362d-122">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="3362d-123">如何設定 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="3362d-123">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-124">設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-124">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="3362d-125">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="3362d-125">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-126">設定 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3362d-126">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="3362d-127">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="3362d-127">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="3362d-128">在用戶端電腦上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-128">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="3362d-129">在用戶端電腦上安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3362d-129">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="3362d-130">將 MBAM 群組原則物件（Gpo）套用到電腦。</span><span class="sxs-lookup"><span data-stu-id="3362d-130">Apply the MBAM Group Policy Objects (GPOs) to the computer.</span></span>

   3.  <span data-ttu-id="3362d-131">設定下列登錄機碼，強制 MBAM 用戶端更快速地喚醒，且定期進行：</span><span class="sxs-lookup"><span data-stu-id="3362d-131">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="3362d-132">注意</span><span class="sxs-lookup"><span data-stu-id="3362d-132">Note</span></span>**  
       <span data-ttu-id="3362d-133">由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在測試環境中使用這些登錄金鑰設定。</span><span class="sxs-lookup"><span data-stu-id="3362d-133">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="3362d-134">重新開機**BitLocker 管理用戶端服務**。</span><span class="sxs-lookup"><span data-stu-id="3362d-134">Restart the **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="3362d-135">使用 System Center 2012 Configuration Manager 整合拓朴來評估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="3362d-135">Evaluating MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>


<span data-ttu-id="3362d-136">若要使用 Configuration Manager 整合拓撲來評估 MBAM，請使用下清單格中的資訊來安裝 MBAM 伺服器軟體，然後在測試環境中設定 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-136">To evaluate MBAM by using the Configuration Manager Integration topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span> <span data-ttu-id="3362d-137">在用戶端電腦上安裝 MBAM 用戶端之後，您將會完成其他步驟，強制 MBAM 用戶端更快速地向 MBAM 報告電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="3362d-137">After installing the MBAM Client on a client computer, you will complete additional steps to force the MBAM Client to report the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="3362d-138">使用系統中心 2012 Configuration Manager 整合拓撲來評估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="3362d-138">To evaluate MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>**

1. <span data-ttu-id="3362d-139">在安裝 MBAM 之前，請先查看必備軟體和支援的設定。</span><span class="sxs-lookup"><span data-stu-id="3362d-139">Before installing MBAM, review the prerequisite software and supported configuration.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-140">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-140">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-141">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-141">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-142">確定您已安裝所有必備軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-142">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="3362d-143">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="3362d-143">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="3362d-144">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="3362d-144">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-145">檢查所需的硬體、RAM 及其他規格。</span><span class="sxs-lookup"><span data-stu-id="3362d-145">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="3362d-146">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="3362d-146">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-147">如果您打算使用 Cmdlet 來設定 MBAM，請查看使用 Windows PowerShell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="3362d-147">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="3362d-148">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="3362d-148">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-149">建立或編輯 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="3362d-149">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="3362d-150">編輯 Configuration.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="3362d-150">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="3362d-151">建立或編輯 Sms_def.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="3362d-151">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="3362d-152">安裝 MBAM Server 軟體，然後設定您想要的功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-152">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-153">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-153">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-154">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-154">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-155">在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-155">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="3362d-156">注意</span><span class="sxs-lookup"><span data-stu-id="3362d-156">Note</span></span></strong><br/><p><span data-ttu-id="3362d-157">您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="3362d-157">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="3362d-158">如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3362d-158">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="3362d-159">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="3362d-159">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-160">設定合規性和審核資料庫及恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="3362d-160">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="3362d-161">如何設定 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="3362d-161">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-162">設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-162">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="3362d-163">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="3362d-163">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-164">設定 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3362d-164">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="3362d-165">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="3362d-165">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-166">設定系統中心 Configuration Manager 來安裝 Configuration Manager 物件。</span><span class="sxs-lookup"><span data-stu-id="3362d-166">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="3362d-167">如何設定 MBAM 2.5 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="3362d-167">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="3362d-168">在用戶端電腦上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-168">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="3362d-169">在用戶端電腦上安裝 MBAM 用戶端和 Configuration Manager 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3362d-169">Install the MBAM Client and the Configuration Manager Client on a client computer.</span></span>

   2.  <span data-ttu-id="3362d-170">將 MBAM 群組原則物件套用到電腦。</span><span class="sxs-lookup"><span data-stu-id="3362d-170">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="3362d-171">設定下列登錄機碼，強制 MBAM 用戶端更快速地喚醒，且定期進行：</span><span class="sxs-lookup"><span data-stu-id="3362d-171">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="3362d-172">注意</span><span class="sxs-lookup"><span data-stu-id="3362d-172">Note</span></span>**  
       <span data-ttu-id="3362d-173">由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在測試環境中使用這些登錄金鑰設定。</span><span class="sxs-lookup"><span data-stu-id="3362d-173">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="3362d-174">重新開機**BitLocker 管理用戶端服務**。</span><span class="sxs-lookup"><span data-stu-id="3362d-174">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="3362d-175">在 [控制台] 中，開啟 [ **Configuration Manager**]，然後按一下 [**動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3362d-175">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="3362d-176">選取 [**硬體清查週期**]，然後按一下 [**立即執行**]。</span><span class="sxs-lookup"><span data-stu-id="3362d-176">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="3362d-177">這個步驟會使用您匯入到 mof 檔案中的新類別來執行硬體清查，然後將資料傳送到 Configuration Manager 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3362d-177">This step runs the hardware inventory by using the new classes that you imported to your .mof files, and then sends the data to the Configuration Manager server.</span></span>

   7.  <span data-ttu-id="3362d-178">選取 [**機器原則檢索] & 評估週期**]，然後按一下 [**立即執行**] 來套用與該用戶端電腦相關的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="3362d-178">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>



4. <span data-ttu-id="3362d-179">在 Configuration Manager 主控台中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-179">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="3362d-180">在 [功能窗格] 中，以滑鼠右鍵按一下 [ **MBAM 支援的電腦**]，按一下 [**更新成員資格**]，然後按一下 **[是]** 強迫用戶端電腦立即報告其成員資格。</span><span class="sxs-lookup"><span data-stu-id="3362d-180">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="3362d-181">在 [功能窗格] 中，按一下 [ **MBAM 支援的電腦**]，確認該用戶端電腦出現在集合中。</span><span class="sxs-lookup"><span data-stu-id="3362d-181">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="3362d-182">在用戶端電腦上，按一下 [控制台] 中的 [再次開啟**Configuration Manager** ]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-182">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="3362d-183">按一下 [**動作**] 索引標籤，然後重新執行**電腦原則檢索 & 評估週期**。</span><span class="sxs-lookup"><span data-stu-id="3362d-183">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="3362d-184">按一下 [**設定**] 索引標籤，選取 [BitLocker 比較基準]，然後按一下 [**評估**]。</span><span class="sxs-lookup"><span data-stu-id="3362d-184">Click the **Configurations** tab, select the BitLocker baseline, and then click **Evaluate**.</span></span>

6. <span data-ttu-id="3362d-185">在 Configuration Manager 主控台中，確認用戶端電腦出現在企業合規性報告上：如下所示：</span><span class="sxs-lookup"><span data-stu-id="3362d-185">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report: as follows:</span></span>

   1.  <span data-ttu-id="3362d-186">在 [功能窗格] 中，選取 [**監視**] 工作區。</span><span class="sxs-lookup"><span data-stu-id="3362d-186">In the navigation pane, select the **Monitoring** workspace.</span></span>

   2.  <span data-ttu-id="3362d-187">在主控台樹中，展開 **[一覽** &gt; **報告** &gt; **報告]** &gt; **MBAM**。</span><span class="sxs-lookup"><span data-stu-id="3362d-187">In the console tree, expand **Overview** &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

   3.  <span data-ttu-id="3362d-188">選取代表您要在其中查看報表之語言的資料夾，然後在 [結果] 窗格中選取報表。</span><span class="sxs-lookup"><span data-stu-id="3362d-188">Select the folder that represents the language in which you want to view reports, and then select the report in the results pane.</span></span>

## <span data-ttu-id="3362d-189">使用 System Center Configuration Manager 2007 整合拓朴來評估 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="3362d-189">Evaluating MBAM 2.5 by using the System Center Configuration Manager 2007 Integration topology</span></span>


<span data-ttu-id="3362d-190">若要使用 Configuration Manager 整合拓撲來評估 MBAM，請遵循相同的步驟，在您的測試環境中安裝和設定 MBAM，就像在生產環境中使用一樣。</span><span class="sxs-lookup"><span data-stu-id="3362d-190">To evaluate MBAM by using the Configuration Manager Integration topology, follow the same steps to install and configure MBAM in your test environment as you use in a production environment.</span></span> <span data-ttu-id="3362d-191">在用戶端電腦上安裝 MBAM 用戶端之後，請完成本主題中的其他步驟，以讓 MBAM 用戶端開始將電腦的狀態報表到 MBAM 的速度。</span><span class="sxs-lookup"><span data-stu-id="3362d-191">After installing the MBAM Client on a client computer, complete the additional steps in this topic to enable the MBAM Client to start reporting the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="3362d-192">使用 Configuration Manager 2007 整合拓撲來評估 MBAM</span><span class="sxs-lookup"><span data-stu-id="3362d-192">To evaluate MBAM by using the Configuration Manager 2007 Integration topology</span></span>**

1. <span data-ttu-id="3362d-193">在安裝 MBAM 之前，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-193">Before you install MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-194">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-194">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-195">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-195">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-196">確定您已安裝所有必備軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-196">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="3362d-197">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="3362d-197">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="3362d-198">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="3362d-198">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-199">檢查所需的硬體、RAM 及其他規格。</span><span class="sxs-lookup"><span data-stu-id="3362d-199">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="3362d-200">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="3362d-200">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-201">建立或編輯 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="3362d-201">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="3362d-202">編輯 Configuration.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="3362d-202">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="3362d-203">建立或編輯 Sms_def.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="3362d-203">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="3362d-204">安裝 MBAM Server 軟體，然後設定您想要的功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-204">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="3362d-205">工作</span><span class="sxs-lookup"><span data-stu-id="3362d-205">Task</span></span></th>
   <th align="left"><span data-ttu-id="3362d-206">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="3362d-206">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-207">在您想要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="3362d-207">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="3362d-208">注意</span><span class="sxs-lookup"><span data-stu-id="3362d-208">Note</span></span></strong><br/><p><span data-ttu-id="3362d-209">您可以使用 Windows PowerShell 或匯出的資料層應用程式（DAC）套件，將資料庫安裝至遠端 SQL Server 電腦。</span><span class="sxs-lookup"><span data-stu-id="3362d-209">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="3362d-210">如需有關 DAC 套件的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> 資料層應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="3362d-210">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="3362d-211">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="3362d-211">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-212">設定合規性和審核資料庫及恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="3362d-212">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="3362d-213">如何設定 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="3362d-213">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-214">設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="3362d-214">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="3362d-215">如何設定 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="3362d-215">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="3362d-216">設定 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3362d-216">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="3362d-217">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="3362d-217">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="3362d-218">設定系統中心 Configuration Manager 來安裝 Configuration Manager 物件。</span><span class="sxs-lookup"><span data-stu-id="3362d-218">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="3362d-219">如何設定 MBAM 2.5 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="3362d-219">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="3362d-220">在用戶端電腦上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-220">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="3362d-221">在用戶端電腦上安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3362d-221">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="3362d-222">將 MBAM 群組原則物件套用到電腦。</span><span class="sxs-lookup"><span data-stu-id="3362d-222">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="3362d-223">設定下列登錄機碼，強制 MBAM 用戶端更快速地醒來，並以更快的間隔進行：</span><span class="sxs-lookup"><span data-stu-id="3362d-223">Set the following registry keys to force the MBAM Client to wake up more quickly and at faster intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="3362d-224">注意</span><span class="sxs-lookup"><span data-stu-id="3362d-224">Note</span></span>**  
       <span data-ttu-id="3362d-225">由於這些金鑰會在每分鐘喚醒 MBAM 用戶端，因此我們建議您只在評估環境中使用這些登錄金鑰設定。</span><span class="sxs-lookup"><span data-stu-id="3362d-225">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in an evaluation environment.</span></span>



   4.  <span data-ttu-id="3362d-226">重新開機**BitLocker 管理用戶端服務**。</span><span class="sxs-lookup"><span data-stu-id="3362d-226">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="3362d-227">在 [控制台] 中，開啟 [ **Configuration Manager**]，然後按一下 [**動作**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3362d-227">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="3362d-228">選取 [**機器原則檢索] & 評估週期**]，然後按一下 [**立即執行**] 來套用與該用戶端電腦相關的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="3362d-228">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>

   7.  <span data-ttu-id="3362d-229">選取 [**硬體清查週期**]，然後按一下 [**立即執行**]。</span><span class="sxs-lookup"><span data-stu-id="3362d-229">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="3362d-230">這個步驟會使用您匯入到 mof 檔案中的新類別來執行硬體清查，然後將資料傳送到 Configuration Manager 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3362d-230">This step runs the hardware inventory by using the new classes that you imported to your .mof files and then sends the data to the Configuration Manager server.</span></span>

4. <span data-ttu-id="3362d-231">在 Configuration Manager 主控台中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-231">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="3362d-232">在 [功能窗格] 中，以滑鼠右鍵按一下 [ **MBAM 支援的電腦**]，按一下 [**更新成員資格**]，然後按一下 **[是]** 強迫用戶端電腦立即報告其成員資格。</span><span class="sxs-lookup"><span data-stu-id="3362d-232">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="3362d-233">在 [功能窗格] 中，按一下 [ **MBAM 支援的電腦**]，確認該用戶端電腦出現在集合中。</span><span class="sxs-lookup"><span data-stu-id="3362d-233">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="3362d-234">在用戶端電腦上，按一下 [控制台] 中的 [再次開啟**Configuration Manager** ]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3362d-234">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="3362d-235">按一下 [**動作**] 索引標籤，然後重新執行**電腦原則檢索 & 評估週期**。</span><span class="sxs-lookup"><span data-stu-id="3362d-235">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="3362d-236">按一下 [**設定**] 索引標籤，選取 [BitLocker 比較基準]，然後按一下 [**評估**]。</span><span class="sxs-lookup"><span data-stu-id="3362d-236">Click the **Configurations** tab, select the BitLocker baseline, and click **Evaluate**.</span></span>

6. <span data-ttu-id="3362d-237">在 Configuration Manager 主控台中，確認用戶端電腦出現在企業合規性報告上，如下所示</span><span class="sxs-lookup"><span data-stu-id="3362d-237">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report, as follows</span></span>

   1.  <span data-ttu-id="3362d-238">在 [功能窗格] 中，展開 [**電腦管理** &gt; **報告** &gt; **服務** &gt; \*\* &lt; 伺服器名稱 &gt; MBAM\*\*]。</span><span class="sxs-lookup"><span data-stu-id="3362d-238">In the navigation pane, expand **Computer Management** &gt; **Reporting** &gt; **Reporting Services** &gt; **&lt;server name&gt;MBAM**.</span></span>

   2.  <span data-ttu-id="3362d-239">在**MBAM**節點中，選取代表您要在其中查看報表之語言的資料夾，然後從 [結果] 窗格中選取報表。</span><span class="sxs-lookup"><span data-stu-id="3362d-239">Within the **MBAM** node, select the folder that represents the language in which you want to view reports, and then select the report from the results pane.</span></span>


## <span data-ttu-id="3362d-240">相關主題</span><span class="sxs-lookup"><span data-stu-id="3362d-240">Related topics</span></span>


[<span data-ttu-id="3362d-241">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3362d-241">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)


## <span data-ttu-id="3362d-242">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3362d-242">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3362d-243">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3362d-243">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="3362d-244">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3362d-244">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>





