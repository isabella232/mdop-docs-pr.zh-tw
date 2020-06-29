---
title: 如何設定 MBAM 2.5 Web 應用程式
description: 如何設定 MBAM 2.5 Web 應用程式
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810592"
---
# <span data-ttu-id="36997-103">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="36997-103">How to Configure the MBAM 2.5 Web Applications</span></span>


<span data-ttu-id="36997-104">本主題說明如何使用下列其中一種方法，將 Microsoft BitLocker 管理和監控（MBAM） 2.5 web 應用程式設定為適用于[MBAM 2.5 的最高層次架構](high-level-architecture-for-mbam-25.md)：</span><span class="sxs-lookup"><span data-stu-id="36997-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 web applications for the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md) by using one of the following methods:</span></span>

-   <span data-ttu-id="36997-105">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="36997-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="36997-106">[MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="36997-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="36997-107">Web 應用程式包含下列網站及其對應的 web 服務：</span><span class="sxs-lookup"><span data-stu-id="36997-107">The web applications comprise the following websites and their corresponding web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36997-108">Website</span><span class="sxs-lookup"><span data-stu-id="36997-108">Website</span></span></th>
<th align="left"><span data-ttu-id="36997-109">描述</span><span class="sxs-lookup"><span data-stu-id="36997-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36997-110">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="36997-110">Administration and Monitoring Website</span></span></p></td>
<td align="left"><p><span data-ttu-id="36997-111">已指定使用者可以在其中查看報告並協助使用者在忘記 PIN 或密碼時復原電腦的網站</span><span class="sxs-lookup"><span data-stu-id="36997-111">Website where specified users can view reports and help end users recover their computers when they forget their PIN or password</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36997-112">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="36997-112">Self-Service Portal</span></span></p></td>
<td align="left"><p><span data-ttu-id="36997-113">如果使用者忘記其 PIN 或密碼，就能獨立地重新取得其電腦存取權的網站</span><span class="sxs-lookup"><span data-stu-id="36997-113">Website that end users can access to independently regain access to their computers if they forget their PIN or password</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="36997-114">開始設定前：</span><span class="sxs-lookup"><span data-stu-id="36997-114">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36997-115">步驟</span><span class="sxs-lookup"><span data-stu-id="36997-115">Step</span></span></th>
<th align="left"><span data-ttu-id="36997-116">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="36997-116">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36997-117">針對 MBAM 查看建議的架構。</span><span class="sxs-lookup"><span data-stu-id="36997-117">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="36997-118">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="36997-118">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36997-119">查看 MBAM 支援的設定。</span><span class="sxs-lookup"><span data-stu-id="36997-119">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="36997-120">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="36997-120">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36997-121">在每個伺服器上完成必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="36997-121">Complete the required prerequisites on each server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="36997-122">注意</span><span class="sxs-lookup"><span data-stu-id="36997-122">Note</span></span></strong><br/><p><span data-ttu-id="36997-123">在設定管理和監視網站之前，請務必將 SQL ServerReporting Services （SSRS）設定為使用安全通訊端層（SSL）。</span><span class="sxs-lookup"><span data-stu-id="36997-123">Ensure that you configure SQL ServerReporting Services (SSRS) to use the Secure Sockets Layer (SSL) before you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="36997-124">否則，報表功能將會使用 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="36997-124">Otherwise, the Reports feature will use HTTP instead of HTTPS.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="36997-125">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="36997-125">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="36997-126">僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件 </a> （如果適用）</span><span class="sxs-lookup"><span data-stu-id="36997-126">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36997-127">針對網站的應用程式池帳戶，註冊服務主要名稱（Spn）。</span><span class="sxs-lookup"><span data-stu-id="36997-127">Register service principal names (SPNs) for the application pool account for the websites.</span></span> <span data-ttu-id="36997-128">如果您在 Active Directory 網域服務（AD DS）中沒有系統管理網域許可權，您就必須執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="36997-128">You need to do this step only if you do not have administrative domain rights in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="36997-129">如果您在 AD DS 中有這些許可權，MBAM 會為您建立 Spn。</span><span class="sxs-lookup"><span data-stu-id="36997-129">If you do have these rights in AD DS, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)"><span data-ttu-id="36997-130">如何保護 MBAM 網站的規劃</span><span class="sxs-lookup"><span data-stu-id="36997-130">Planning How to Secure the MBAM Websites</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36997-131">在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="36997-131">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="36997-132">注意</span><span class="sxs-lookup"><span data-stu-id="36997-132">Note</span></span></strong><br/><p><span data-ttu-id="36997-133">如果您打算在一台伺服器上安裝網站，並在另一台伺服器上安裝 web 服務，您就可以使用 <strong> Enable-MbamWebApplication </strong> Windows PowerShell Cmdlet 來設定它們。</span><span class="sxs-lookup"><span data-stu-id="36997-133">If you plan to install the websites on one server and the web services on another, you will be able to configure them only by using the <strong>Enable-MbamWebApplication</strong> Windows PowerShell cmdlet.</span></span> <span data-ttu-id="36997-134">MBAM Server 設定向導不支援在個別伺服器上設定這些專案。</span><span class="sxs-lookup"><span data-stu-id="36997-134">The MBAM Server Configuration wizard does not support configuring these items on separate servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="36997-135">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="36997-135">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36997-136">如果您打算使用 Cmdlet 來設定 MBAM 伺服器功能，請參閱使用 Windows PowerShell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="36997-136">Review the prerequisites for using Windows PowerShell if you plan to use cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="36997-137">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="36997-137">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="36997-138">使用 Windows PowerShell 來設定 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="36997-138">To configure the web applications by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="36997-139">開始設定前，請參閱[使用 Windows powershell 設定 MBAM 2.5 Server 功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)，以查看使用 windows powershell 的先決條件。</span><span class="sxs-lookup"><span data-stu-id="36997-139">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="36997-140">使用**Enable-MbamWebApplication** Cmdlet 來設定使用 Windows PowerShell 的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="36997-140">Use the **Enable-MbamWebApplication** cmdlet to configure the web applications using Windows PowerShell.</span></span> <span data-ttu-id="36997-141">若要取得此 Cmdlet 的相關資訊，請輸入**Get-help Enable-MbamWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="36997-141">To get information about this cmdlet, type **Get-Help Enable-MbamWebApplication**.</span></span>

**<span data-ttu-id="36997-142">使用嚮導設定所有 web 應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="36997-142">To configure the settings for all web applications using the wizard</span></span>**

1. <span data-ttu-id="36997-143">在您想要設定 web 應用程式的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="36997-143">On the server where you want to configure the web applications, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="36997-144">您可以從 [**開始**] 功能表選取 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="36997-144">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="36997-145">按一下 [**新增功能**]，選取 [**管理及監視網站**與**自助式入口**網站]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36997-145">Click **Add New Features**, select **Administration and Monitoring Website** and **Self-Service Portal**, and then click **Next**.</span></span> <span data-ttu-id="36997-146">嚮導會檢查是否符合 web 應用程式的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="36997-146">The wizard checks that all prerequisites for the web applications have been met.</span></span>

3. <span data-ttu-id="36997-147">如果先決條件檢查成功，請按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="36997-147">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="36997-148">否則，請解決任何缺少的先決條件，然後**再次按一下 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="36997-148">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="36997-149">使用下列描述在嚮導中輸入欄位值。</span><span class="sxs-lookup"><span data-stu-id="36997-149">Use the following descriptions to enter the field values in the wizard.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong><span data-ttu-id="36997-150">欄位</span><span class="sxs-lookup"><span data-stu-id="36997-150">Field</span></span></strong></th>
   <th align="left"><span data-ttu-id="36997-151">描述</span><span class="sxs-lookup"><span data-stu-id="36997-151">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-152">安全性憑證</span><span class="sxs-lookup"><span data-stu-id="36997-152">Security certificate</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-153">選取先前建立的憑證，以選擇性地加密 web 服務與您要設定網站之伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="36997-153">Select a previously created certificate to optionally encrypt the communication between the web services and the server on which you are configuring the websites.</span></span> <span data-ttu-id="36997-154">如果您選擇 [不要 <strong> 使用憑證] </strong> ，您的 web 通訊可能不安全。</span><span class="sxs-lookup"><span data-stu-id="36997-154">If you choose <strong>Do not use a certificate</strong>, your web communication may not be secure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="36997-155">主機名稱</span><span class="sxs-lookup"><span data-stu-id="36997-155">Host name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-156">您正在設定網站的主機名稱稱。</span><span class="sxs-lookup"><span data-stu-id="36997-156">Name of the host computer where you are configuring the websites.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-157">安裝路徑</span><span class="sxs-lookup"><span data-stu-id="36997-157">Installation path</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-158">您要安裝網站的路徑。</span><span class="sxs-lookup"><span data-stu-id="36997-158">Path where you are installing the websites.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="36997-159">連接埠</span><span class="sxs-lookup"><span data-stu-id="36997-159">Port</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-160">要用於網站與服務通訊的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="36997-160">Port number to use for website and service communication.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="36997-161">注意</span><span class="sxs-lookup"><span data-stu-id="36997-161">Note</span></span></strong><br/><p><span data-ttu-id="36997-162">您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="36997-162">You must set a firewall exception to enable communication through the specified port.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-163">Web 服務應用程式池網域帳戶和密碼</span><span class="sxs-lookup"><span data-stu-id="36997-163">Web service application pool domain account and password</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-164">[Web 服務] 應用程式池的網域使用者帳戶和密碼。</span><span class="sxs-lookup"><span data-stu-id="36997-164">Domain user account and password for the web service application pool.</span></span></p>
   <p><span data-ttu-id="36997-165">如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取權網域使用者或群組] 欄位中輸入使用者名稱 </strong> <strong> </strong> ，您必須在這個欄位中輸入相同的值。</span><span class="sxs-lookup"><span data-stu-id="36997-165">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="36997-166">如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取網域] 或 [群組] 欄位中輸入組名 </strong> <strong> </strong> ，您在這個欄位中輸入的值必須是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="36997-166">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="36997-167">如果您沒有指定認證，則會使用為先前啟用的任何 web 應用程式所指定的認證。</span><span class="sxs-lookup"><span data-stu-id="36997-167">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="36997-168">所有 web 應用程式都必須使用相同的應用程式池認證。</span><span class="sxs-lookup"><span data-stu-id="36997-168">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="36997-169">如果您針對不同的 web 應用程式指定不同的認證，則會使用最近指定的值。</span><span class="sxs-lookup"><span data-stu-id="36997-169">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="36997-170">重要</span><span class="sxs-lookup"><span data-stu-id="36997-170">Important</span></span></strong><br/><p><span data-ttu-id="36997-171">若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="36997-171">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span> <span data-ttu-id="36997-172">此外，將帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="36997-172">Also, set the password of the account to never expire.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="36997-173">確認內建的 IIS \ _IUSRS 帳戶或應用程式池帳戶已新增至**驗證之後類比用戶端**，並以**批次工作**的本機安全性設定登入。</span><span class="sxs-lookup"><span data-stu-id="36997-173">Verify that the built-in IIS\_IUSRS account or the application pool account has been added to the **Impersonate a client after authentication** and the **Log on as a batch job** local security settings.</span></span>

   <span data-ttu-id="36997-174">若要檢查是否已將它新增到本機安全性設定，請開啟 [**本機安全性原則編輯器**]，展開 [**本機原則**] 節點，按一下 [**使用者權利指派**] 節點，然後按兩下 [**在驗證之後類比用戶端**]，然後在右窗格中**以批次工作原則登**入。</span><span class="sxs-lookup"><span data-stu-id="36997-174">To check whether it has been added to the local security settings, open the **Local Security Policy editor**, expand the **Local Policies** node, click the **User Rights Assignment** node, and double-click **Impersonate a client after authentication** and **Log on as a batch job** policies in the right pane.</span></span>

**<span data-ttu-id="36997-175">使用嚮導設定資料庫的連線資訊</span><span class="sxs-lookup"><span data-stu-id="36997-175">To configure connection information for the databases by using the wizard</span></span>**

1.  <span data-ttu-id="36997-176">使用下欄欄位描述來設定合規性和審核資料庫的嚮導中的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="36997-176">Use the following field descriptions to configure the connection information in the wizard for the Compliance and Audit Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="36997-177">欄位</span><span class="sxs-lookup"><span data-stu-id="36997-177">Field</span></span></th>
    <th align="left"><span data-ttu-id="36997-178">描述</span><span class="sxs-lookup"><span data-stu-id="36997-178">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36997-179">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="36997-179">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-180">已設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-180">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="36997-181">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="36997-181">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-182">在其中設定合規性和審核資料庫的 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-182">SQL Server instance name where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36997-183">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="36997-183">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-184">合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-184">Name of the Compliance and Audit Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="36997-185">使用下欄欄位描述來設定恢復資料庫的嚮導中的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="36997-185">Use the following field descriptions to configure the connection information in the wizard for the Recovery Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="36997-186">欄位</span><span class="sxs-lookup"><span data-stu-id="36997-186">Field</span></span></th>
    <th align="left"><span data-ttu-id="36997-187">描述</span><span class="sxs-lookup"><span data-stu-id="36997-187">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36997-188">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="36997-188">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-189">在其中設定恢復資料庫的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-189">Name of the server where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="36997-190">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="36997-190">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-191">在其中設定復原資料庫的 SQL Server 實例名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-191">SQL Server instance name where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="36997-192">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="36997-192">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="36997-193">恢復資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="36997-193">Name of the Recovery Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="36997-194">使用嚮導來設定 web 應用程式</span><span class="sxs-lookup"><span data-stu-id="36997-194">To configure the web applications by using the wizard</span></span>**

1. <span data-ttu-id="36997-195">使用下列描述在嚮導中輸入欄位值，以設定管理和監視網站。</span><span class="sxs-lookup"><span data-stu-id="36997-195">Use the following descriptions to enter the field values in the wizard to configure the Administration and Monitoring Website.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="36997-196">欄位</span><span class="sxs-lookup"><span data-stu-id="36997-196">Field</span></span></th>
   <th align="left"><span data-ttu-id="36997-197">描述</span><span class="sxs-lookup"><span data-stu-id="36997-197">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-198">[高級支援人員] 角色網域群組</span><span class="sxs-lookup"><span data-stu-id="36997-198">Advanced Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-199">網域使用者群組，其成員可以存取管理和監控網站的所有區域（[報表] 區域除外）。</span><span class="sxs-lookup"><span data-stu-id="36997-199">Domain user group whose members have access to all areas of the Administration and Monitoring Website except the Reports area.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="36997-200">支援人員角色網域群組</span><span class="sxs-lookup"><span data-stu-id="36997-200">Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-201">網域使用者群組，其成員可以存取 <strong> </strong> 管理和監控網站的 [管理 TPM] 和 [ <strong> 磁碟機恢復] </strong> 區域。</span><span class="sxs-lookup"><span data-stu-id="36997-201">Domain user group whose members have access to the <strong>Manage TPM</strong> and <strong>Drive Recovery</strong> areas of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-202">使用 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="36997-202">Use System Center Configuration Manager Integration</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-203">如果您是使用 Configuration Manager 整合拓撲設定 MBAM，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="36997-203">Select this check box if you are configuring MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="36997-204">選取此核取方塊後，除了復原審核報告之外，所有的報告都會出現在 Configuration Manager 中，而不是在 [管理] 和 [監視] 網站中顯示。</span><span class="sxs-lookup"><span data-stu-id="36997-204">Selecting this check box makes all reports, except the Recovery Audit report, appear in Configuration Manager instead of in the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="36997-205">報告角色網域群組</span><span class="sxs-lookup"><span data-stu-id="36997-205">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-206">其成員擁有 [管理] 和 [監視] 網站 [報告] 區域之唯讀存取權的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="36997-206">Domain user group whose members have read-only access to the Reports area of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-207">SQL Server Reporting Services URL</span><span class="sxs-lookup"><span data-stu-id="36997-207">SQL Server Reporting Services URL</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-208">已設定 MBAM 報告之 SSRS 伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="36997-208">URL for the SSRS server where the MBAM Reports are configured.</span></span></p>
   <p><span data-ttu-id="36997-209">報表 Url 的範例：</span><span class="sxs-lookup"><span data-stu-id="36997-209">Examples of report URLs:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="36997-210">主機名稱類型</span><span class="sxs-lookup"><span data-stu-id="36997-210">Type of host name</span></span></th>
   <th align="left"><span data-ttu-id="36997-211">範例</span><span class="sxs-lookup"><span data-stu-id="36997-211">Example</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="36997-212">含完全限定功能變數名稱的範例</span><span class="sxs-lookup"><span data-stu-id="36997-212">Example with a fully qualified domain name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="36997-213">含自訂主機名稱的範例</span><span class="sxs-lookup"><span data-stu-id="36997-213">Example with a custom host name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="36997-214">虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="36997-214">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-215">[管理] 和 [監視] 網站的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="36997-215">Virtual directory of the Administration and Monitoring Website.</span></span> <span data-ttu-id="36997-216">這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱，例如：</span><span class="sxs-lookup"><span data-stu-id="36997-216">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="36997-217">HTTP （s）// &lt; <em> hostname </em> &gt; ： &lt; <em> 埠 </em> &gt; /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="36997-217">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/HelpDesk/</span></span></p>
   <p><span data-ttu-id="36997-218">如果您沒有指定虛擬目錄，就會使用 [價值 <strong> 支援人員] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="36997-218">If you do not specify a virtual directory, the value <strong>HelpDesk</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-219">資料移轉角色網域群組 </strong> （選用）</span><span class="sxs-lookup"><span data-stu-id="36997-219">Data Migration role domain group</strong> (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-220">其成員有權使用 Mbam \* 資訊 Cmdlet 來透過此端點寫入復原資訊的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="36997-220">Domain user group whose members have access to use the Write-Mbam\*Information Cmdlets to write recovery information via this endpoint.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="36997-221">使用下列描述在嚮導中輸入欄位值以設定自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="36997-221">Use the following description to enter the field values in the wizard to configure the Self-Service Portal.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="36997-222">欄位</span><span class="sxs-lookup"><span data-stu-id="36997-222">Field</span></span></th>
   <th align="left"><span data-ttu-id="36997-223">描述</span><span class="sxs-lookup"><span data-stu-id="36997-223">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="36997-224">虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="36997-224">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="36997-225">Web 應用程式的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="36997-225">Virtual directory of the web application.</span></span> <span data-ttu-id="36997-226">這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱，例如：</span><span class="sxs-lookup"><span data-stu-id="36997-226">This name corresponds to the website’s physical directory on the server, and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="36997-227">HTTP （s）// &lt; <em> hostname </em> &gt; ： &lt; <em> 埠 </em> &gt; /SelfService/</span><span class="sxs-lookup"><span data-stu-id="36997-227">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/SelfService/</span></span></p>
   <p><span data-ttu-id="36997-228">如果您沒有指定虛擬目錄，將會使用 [值 <strong> SelfService] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="36997-228">If you do not specify a virtual directory, the value <strong>SelfService</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="36997-229">公司名稱</span><span class="sxs-lookup"><span data-stu-id="36997-229">Company name</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-230">為自助服務入口網站指定公司名稱，例如：</span><span class="sxs-lookup"><span data-stu-id="36997-230">Specify a company name for the Self-Service Portal, for example:</span></span></p>
   <p><span data-ttu-id="36997-231">Contoso IT</span><span class="sxs-lookup"><span data-stu-id="36997-231">Contoso IT</span></span></p>
   <p><span data-ttu-id="36997-232">此公司名稱是由所有自助門戶使用者查看。</span><span class="sxs-lookup"><span data-stu-id="36997-232">This company name is viewed by all Self-Service Portal users.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="36997-233">支援人員 URL 文字</span><span class="sxs-lookup"><span data-stu-id="36997-233">Helpdesk URL text</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-234">指定將使用者引導至貴組織的技術支援網站的文字語句，例如：</span><span class="sxs-lookup"><span data-stu-id="36997-234">Specify a text statement that directs users to your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="36997-235">聯絡支援人員或 IT 部門</span><span class="sxs-lookup"><span data-stu-id="36997-235">Contact Helpdesk or IT department</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="36997-236">支援人員 URL</span><span class="sxs-lookup"><span data-stu-id="36997-236">Helpdesk URL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-237">指定貴組織的技術支援網站的 URL，例如：</span><span class="sxs-lookup"><span data-stu-id="36997-237">Specify the URL for your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="36997-238">HTTP （s）// &lt; <em> companyHelpdeskURL</em>&gt;/</span><span class="sxs-lookup"><span data-stu-id="36997-238">http(s)://&lt;<em>companyHelpdeskURL</em>&gt;/</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="36997-239">[注意事項] 文字檔</span><span class="sxs-lookup"><span data-stu-id="36997-239">Notice text file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-240">在自助入口網站登陸頁面上，選取包含您想要向使用者顯示之通知的檔案。</span><span class="sxs-lookup"><span data-stu-id="36997-240">Select a file that contains the notice you want displayed to users on the Self-Service Portal landing page.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="36997-241">不要向使用者顯示通知文字</span><span class="sxs-lookup"><span data-stu-id="36997-241">Do not display notice text to users</span></span></p></td>
   <td align="left"><p><span data-ttu-id="36997-242">選取此核取方塊，以指定不會向使用者顯示通知文字。</span><span class="sxs-lookup"><span data-stu-id="36997-242">Select this check box to specify that the notice text is not displayed to users.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="36997-243">完成專案後，請按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="36997-243">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="36997-244">嚮導會檢查是否符合 web 應用程式的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="36997-244">The wizard checks that all prerequisites for the web applications have been met.</span></span>

4. <span data-ttu-id="36997-245">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="36997-245">Click **Next** to continue.</span></span>

5. <span data-ttu-id="36997-246">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="36997-246">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="36997-247">注意</span><span class="sxs-lookup"><span data-stu-id="36997-247">Note</span></span>**  
   <span data-ttu-id="36997-248">若要為您所製作的專案建立 Windows PowerShell 腳本，請按一下 [**匯出 PowerShell 腳本**] 並儲存腳本。</span><span class="sxs-lookup"><span data-stu-id="36997-248">To create a Windows PowerShell script for the entries you made, click **Export PowerShell Script** and save the script.</span></span>



6. <span data-ttu-id="36997-249">按一下 [**新增**]，將 web 應用程式新增至伺服器，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="36997-249">Click **Add** to add the web applications to the server, and then click **Close**.</span></span>

   <span data-ttu-id="36997-250">若要自訂自助式入口網站，只要新增自訂的指示文字、您的公司名稱、指向詳細資訊的指標等，請參閱[自訂貴組織的自助入口網站](customizing-the-self-service-portal-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="36997-250">To customize the Self-Service Portal by adding custom notice text, your company name, pointers to more information, and so on, see [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md).</span></span>

**<span data-ttu-id="36997-251">在用戶端電腦無法存取 CDN 的情況下，設定自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="36997-251">To configure the Self-Service Portal if client computers cannot access the CDN</span></span>**

1.  <span data-ttu-id="36997-252">判斷您是否正在執行 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="36997-252">Determine whether you are running Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="36997-253">如果是這樣，請不要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="36997-253">If so, do nothing.</span></span> <span data-ttu-id="36997-254">您的自助入口網站設定已完成。</span><span class="sxs-lookup"><span data-stu-id="36997-254">Your Self-Service Portal configuration is complete.</span></span>

    **<span data-ttu-id="36997-255">注意</span><span class="sxs-lookup"><span data-stu-id="36997-255">Note</span></span>**  
    <span data-ttu-id="36997-256">Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 會在安裝程式中安裝 JavaScript 檔案，因此不需要連線至 Microsoft Ajax 內容傳遞網路，就能設定自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="36997-256">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 installs the JavaScript files in setup, and so does not need to be connected to the Microsoft Ajax Content Delivery Network in order to configure the Self-Service Portal.</span></span> <span data-ttu-id="36997-257">只有在 SP1 之前使用版本的 Microsoft BitLocker 管理和監控（MBAM）2.5 時，才能執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="36997-257">The following steps are necessary only if you are using a version of Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 previous to SP1.</span></span>



2.  <span data-ttu-id="36997-258">判斷您的用戶端電腦是否有權存取 Microsoft Ajax 內容傳遞網路（CDN）。</span><span class="sxs-lookup"><span data-stu-id="36997-258">Determine if your client computers have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

    <span data-ttu-id="36997-259">CDN 為自助入口網站提供對某些 JavaScript 檔案所需的存取權。</span><span class="sxs-lookup"><span data-stu-id="36997-259">The CDN gives the Self-Service Portal the access it requires to certain JavaScript files.</span></span> <span data-ttu-id="36997-260">如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只會顯示公司名稱和使用者登入的帳戶。</span><span class="sxs-lookup"><span data-stu-id="36997-260">If you don’t configure the Self-Service Portal when client computers cannot access the CDN, only the company name and the account under which the end user signed in will be displayed.</span></span> <span data-ttu-id="36997-261">不會顯示任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="36997-261">No error message will be shown.</span></span>

3.  <span data-ttu-id="36997-262">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="36997-262">Do one of the following:</span></span>

    -   <span data-ttu-id="36997-263">如果您的用戶端電腦具有 CDN 的存取權，請執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="36997-263">If your client computers have access to the CDN, do nothing.</span></span> <span data-ttu-id="36997-264">您的自助入口網站設定已完成。</span><span class="sxs-lookup"><span data-stu-id="36997-264">Your Self-Service Portal configuration is complete.</span></span>

    -   <span data-ttu-id="36997-265">如果您的用戶端電腦沒有 CDN 的存取權，請完成在[用戶端電腦無法存取 Microsoft 內容傳遞網路時，如何設定自助入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="36997-265">If your client computers do not have access to the CDN, complete the steps in [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>


## <span data-ttu-id="36997-266">相關主題</span><span class="sxs-lookup"><span data-stu-id="36997-266">Related topics</span></span>


[<span data-ttu-id="36997-267">伺服器事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="36997-267">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="36997-268">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="36997-268">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="36997-269">如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站</span><span class="sxs-lookup"><span data-stu-id="36997-269">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[<span data-ttu-id="36997-270">為組織自訂自助入口網站</span><span class="sxs-lookup"><span data-stu-id="36997-270">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

[<span data-ttu-id="36997-271">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="36997-271">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="36997-272">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="36997-272">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="36997-273">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="36997-273">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="36997-274">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="36997-274">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





