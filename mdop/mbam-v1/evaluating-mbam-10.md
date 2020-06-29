---
title: 評估 MBAM 1.0
description: 評估 MBAM 1.0
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811043"
---
# <span data-ttu-id="8ace0-103">評估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="8ace0-103">Evaluating MBAM 1.0</span></span>


<span data-ttu-id="8ace0-104">在您將 Microsoft BitLocker 管理和監控（MBAM）部署到生產環境之前，您應該先在實驗室環境中評估它。</span><span class="sxs-lookup"><span data-stu-id="8ace0-104">Before you deploy Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a lab environment.</span></span> <span data-ttu-id="8ace0-105">您可以使用本主題中的資訊，在單一伺服器實驗室環境中設定 MBAM，僅供評估之用。</span><span class="sxs-lookup"><span data-stu-id="8ace0-105">You can use the information in this topic to set up MBAM in a single server lab environment for evaluation purposes only.</span></span>

<span data-ttu-id="8ace0-106">雖然實際的部署步驟與在[單一伺服器上安裝和設定 MBAM](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)的案例非常類似，本主題包含其他資訊，讓您在最少的時間內設定 MBAM 評估環境。</span><span class="sxs-lookup"><span data-stu-id="8ace0-106">While the actual deployment steps are very similar to the scenario that is described in [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md), this topic contains additional information to enable you to set up an MBAM evaluation environment in the least amount of time.</span></span>

## <span data-ttu-id="8ace0-107">設定實驗室環境</span><span class="sxs-lookup"><span data-stu-id="8ace0-107">Set up the Lab Environment</span></span>


<span data-ttu-id="8ace0-108">即使在實驗室環境中設定非生產的 MBAM 實例，您仍然應該確認您已滿足部署的先決條件以及硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="8ace0-108">Even when you set up a non-production instance of MBAM to evaluate in a lab environment, you should still verify that you have met the deployment prerequisites and the hardware and software requirements.</span></span> <span data-ttu-id="8ace0-109">如需詳細資訊，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="8ace0-109">For more information, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="8ace0-110">您也應該在開始 MBAM 評估部署之前，先複習[準備 MBAM 1.0 的環境](preparing-your-environment-for-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="8ace0-110">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM evaluation deployment.</span></span>

### <span data-ttu-id="8ace0-111">規劃 MBAM 評估部署</span><span class="sxs-lookup"><span data-stu-id="8ace0-111">Plan for an MBAM Evaluation Deployment</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="8ace0-112">工作</span><span class="sxs-lookup"><span data-stu-id="8ace0-112">Task</span></span></th>
<th align="left"><span data-ttu-id="8ace0-113">參考資料</span><span class="sxs-lookup"><span data-stu-id="8ace0-113">References</span></span></th>
<th align="left"><span data-ttu-id="8ace0-114">附註</span><span class="sxs-lookup"><span data-stu-id="8ace0-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-115">在開始進行部署規劃之前，請先查看 MBAM 的快速入門資訊，以深入瞭解產品。</span><span class="sxs-lookup"><span data-stu-id="8ace0-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before you begin your deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)"><span data-ttu-id="8ace0-116">開始使用 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="8ace0-116">Getting Started with MBAM 1.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p><span data-ttu-id="8ace0-117">為 MBAM 安裝準備您的計算環境。</span><span class="sxs-lookup"><span data-stu-id="8ace0-117">Prepare your computing environment for the MBAM installation.</span></span> <span data-ttu-id="8ace0-118">若要這樣做，您必須在將裝載 MBAM 資料庫的 SQL Server 實例上啟用透明資料加密（TDE）。</span><span class="sxs-lookup"><span data-stu-id="8ace0-118">To do so, you must enable the Transparent Data Encryption (TDE) on the SQL Server instances that will host MBAM databases.</span></span> <span data-ttu-id="8ace0-119">若要在您的實驗室環境中啟用 TDE，您可以建立一個 .sql 檔案，以針對在 MBAM 將使用之 SQL Server 實例上裝載的主資料庫執行。</span><span class="sxs-lookup"><span data-stu-id="8ace0-119">To enable TDE in your lab environment, you can create a .sql file to run against the master database that is hosted on the instance of the SQL Server that MBAM will use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8ace0-120">注意</span><span class="sxs-lookup"><span data-stu-id="8ace0-120">Note</span></span></strong><br/><p><span data-ttu-id="8ace0-121">您可以使用下列範例，為您的實驗室環境建立 .sql 檔案，以便在將裝載 MBAM 資料庫的 SQL Server 實例上快速啟用 TDE。</span><span class="sxs-lookup"><span data-stu-id="8ace0-121">You can use the following example to create a .sql file for your lab environment to quickly enable TDE on the SQL Server instance that will host the MBAM databases.</span></span> <span data-ttu-id="8ace0-122">這些 SQL Server 命令會使用本機簽署的 SQL Server 憑證來啟用 TDE。</span><span class="sxs-lookup"><span data-stu-id="8ace0-122">These SQL Server commands will enable TDE by using a locally signed SQL Server certificate.</span></span> <span data-ttu-id="8ace0-123">請務必將 TDE 憑證及其相關的加密金鑰備份到 C:\Backup 的本機備份路徑 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="8ace0-123">Make sure to back up the TDE certificate and its associated encryption key to the example local backup path of <em>C:\Backup</em>.</span></span> <span data-ttu-id="8ace0-124">當復原資料庫或將憑證和金鑰移至有適當的 TDE 加密的另一台伺服器時，必須有 TDE 憑證和金鑰。</span><span class="sxs-lookup"><span data-stu-id="8ace0-124">The TDE certificate and key are required when recover the database or move the certificate and key to another server that has TDE encryption in place.</span></span></p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)"><span data-ttu-id="8ace0-125">MBAM 1.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="8ace0-125">MBAM 1.0 Deployment Prerequisites</span></span></a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)"><span data-ttu-id="8ace0-126">SQL Server 2008 企業版中的資料庫加密</span><span class="sxs-lookup"><span data-stu-id="8ace0-126">Database Encryption in SQL Server 2008 Enterprise Edition</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-127">規劃及設定 MBAM 群組原則需求。</span><span class="sxs-lookup"><span data-stu-id="8ace0-127">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)"><span data-ttu-id="8ace0-128">MBAM 1.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="8ace0-128">Planning for MBAM 1.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-129">規劃及建立必要的 Active Directory 網域服務安全性群組，並規劃 MBAM 的本地安全性群組成員資格需求。</span><span class="sxs-lookup"><span data-stu-id="8ace0-129">Plan for and create the necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="8ace0-130">MBAM 1.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="8ace0-130">Planning for MBAM 1.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-131">規劃 MBAM Server 功能部署。</span><span class="sxs-lookup"><span data-stu-id="8ace0-131">Plan for MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)"><span data-ttu-id="8ace0-132">MBAM 1.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="8ace0-132">Planning for MBAM 1.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-133">規劃 MBAM 用戶端部署。</span><span class="sxs-lookup"><span data-stu-id="8ace0-133">Plan for MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)"><span data-ttu-id="8ace0-134">MBAM 1.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="8ace0-134">Planning for MBAM 1.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8ace0-135">執行 MBAM 評估部署</span><span class="sxs-lookup"><span data-stu-id="8ace0-135">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="8ace0-136">完成所需的規劃和軟體必備元件安裝後，若要為 MBAM 安裝準備您的計算環境，您可以開始進行 MBAM 評估部署。</span><span class="sxs-lookup"><span data-stu-id="8ace0-136">After you complete the necessary planning and software prerequisite installations to prepare your computing environment for an MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-137">查看 MBAM 支援的設定資訊，以確保 MBAM 功能安裝支援所選取的用戶端和伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="8ace0-137">Review the MBAM supported configurations information to make sure that the selected client and server computers are supported for the MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="8ace0-138">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="8ace0-138">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-139">若要評估，請執行 MBAM 安裝程式，在單一伺服器上部署 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="8ace0-139">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)"><span data-ttu-id="8ace0-140">如何在單一伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="8ace0-140">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-141">將您在規劃階段建立的 Active Directory 網域服務安全性群組新增至新 MBAM 伺服器上適當的本機 MBAM 伺服器功能本機群組。</span><span class="sxs-lookup"><span data-stu-id="8ace0-141">Add the Active Directory Domain Services security groups that you created during the planning phase to the appropriate local MBAM Server feature local groups on the new MBAM server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="8ace0-142">規劃 MBAM 1.0 系統管理員角色 </a> ，以及 <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> 如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8ace0-142">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-143">建立及部署所需的 MBAM 群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="8ace0-143">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="8ace0-144">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="8ace0-144">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="8ace0-145">部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="8ace0-145">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="8ace0-146">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="8ace0-146">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8ace0-147">設定實驗室電腦進行 MBAM 評估</span><span class="sxs-lookup"><span data-stu-id="8ace0-147">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="8ace0-148">您可以使用 [登錄編輯程式] 變更 MBAM 用戶端狀態報表上的頻率設定。</span><span class="sxs-lookup"><span data-stu-id="8ace0-148">You can change the frequency settings on the MBAM Client status reporting by using Registry Editor.</span></span> <span data-ttu-id="8ace0-149">不過，這些修改只能用於測試目的。</span><span class="sxs-lookup"><span data-stu-id="8ace0-149">However, these modifications should be used for testing purposes only.</span></span>

**<span data-ttu-id="8ace0-150">警告</span><span class="sxs-lookup"><span data-stu-id="8ace0-150">Warning</span></span>**  
<span data-ttu-id="8ace0-151">本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="8ace0-151">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="8ace0-152">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="8ace0-152">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="8ace0-153">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="8ace0-153">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="8ace0-154">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="8ace0-154">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="8ace0-155">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="8ace0-155">Change the registry at your own risk.</span></span>



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a><span data-ttu-id="8ace0-156">在 MBAM 用戶端狀態報表上修改頻率設定</span><span class="sxs-lookup"><span data-stu-id="8ace0-156">Modify the Frequency Settings on MBAM Client Status Reporting</span></span>

<span data-ttu-id="8ace0-157">當 MBAM 用戶端的 [喚醒] 和 [狀態報表] 頻率設定為使用 [群組原則] 時，其最小值為90分鐘。</span><span class="sxs-lookup"><span data-stu-id="8ace0-157">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set to use Group Policy.</span></span> <span data-ttu-id="8ace0-158">您可以在 MBAM 用戶端電腦上變更這些頻率，方法是將 Windows 登錄編輯為較低的值，這有助於加快測試速度。</span><span class="sxs-lookup"><span data-stu-id="8ace0-158">You can change these frequencies on MBAM client computers by editing the Windows registry to lower values, which will help speed up the testing.</span></span> <span data-ttu-id="8ace0-159">若要在 MBAM 用戶端狀態報表上修改頻率設定，請使用登錄編輯程式流覽至**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**，將**ClientWakeupFrequency**和**StatusReportingFrequency**的值變更為**1** ，以取得最小用戶端支援的值，然後重新開機 BitLocker 管理用戶端服務。</span><span class="sxs-lookup"><span data-stu-id="8ace0-159">To modify the frequency settings on MBAM Client status reporting, use a registry editor to navigate to **HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**, change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client supported value, and then restart BitLocker Management Client Service.</span></span> <span data-ttu-id="8ace0-160">當您進行此變更時，MBAM 用戶端會每分鐘報告一次。</span><span class="sxs-lookup"><span data-stu-id="8ace0-160">When you make this change, the MBAM Client will report every minute.</span></span> <span data-ttu-id="8ace0-161">您可以在登錄中手動執行此動作時，將值設定為 [低]。</span><span class="sxs-lookup"><span data-stu-id="8ace0-161">You can set values this low only when you do so manually in the registry.</span></span>

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a><span data-ttu-id="8ace0-162">修改 MBAM 用戶端服務的啟動延遲</span><span class="sxs-lookup"><span data-stu-id="8ace0-162">Modify the Startup Delay on MBAM Client Service</span></span>

<span data-ttu-id="8ace0-163">除了 MBAM 用戶端喚醒和狀態報表頻率之外，在用戶端電腦上啟動 MBAM 用戶端代理服務時，會有最多90分鐘的隨機延遲。</span><span class="sxs-lookup"><span data-stu-id="8ace0-163">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="8ace0-164">如果您不想要隨機延遲，請在 [ **HKLM\\Software\\Microsoft\\MBAM**] 下建立**NoStartupDelay**的**DWORD**值，將它的值設定為**1**，然後重新開機 BitLocker 管理用戶端服務。</span><span class="sxs-lookup"><span data-stu-id="8ace0-164">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart BitLocker Management Client Service.</span></span>

## <span data-ttu-id="8ace0-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="8ace0-165">Related topics</span></span>


[<span data-ttu-id="8ace0-166">開始使用 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="8ace0-166">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)









