---
title: 如何部署 App-V 用戶端
description: 如何部署 App-V 用戶端
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800515"
---
# <span data-ttu-id="bf731-103">如何部署 App-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-103">How to Deploy the App-V Client</span></span>


<span data-ttu-id="bf731-104">使用下列程式來安裝 Microsoft Application Virtualization （App-v）5.1 用戶端和遠端桌面服務用戶端。</span><span class="sxs-lookup"><span data-stu-id="bf731-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 client and Remote Desktop Services client.</span></span> <span data-ttu-id="bf731-105">您必須安裝與目的電腦作業系統相符的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="bf731-105">You must install the version of the client that matches the operating system of the target computer.</span></span>

<a href="" id="bkmk-clt-install-prereqs"></a>**<span data-ttu-id="bf731-106">開始之前的做法</span><span class="sxs-lookup"><span data-stu-id="bf731-106">What to do before you start</span></span>**

1. <span data-ttu-id="bf731-107">審查並安裝軟體先決條件：</span><span class="sxs-lookup"><span data-stu-id="bf731-107">Review and install the software prerequisites:</span></span>

   <span data-ttu-id="bf731-108">安裝與您要安裝的 App-v 版本相對應的必備軟體：</span><span class="sxs-lookup"><span data-stu-id="bf731-108">Install the prerequisite software that corresponds to the version of App-V that you are installing:</span></span>

   -   [<span data-ttu-id="bf731-109">關於 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bf731-109">About App-V 5.1</span></span>](about-app-v-51.md)

   -   [<span data-ttu-id="bf731-110">App-V 5.1 必要條件</span><span class="sxs-lookup"><span data-stu-id="bf731-110">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)

2. <span data-ttu-id="bf731-111">查看用戶端共存與不支援的案例（適用于您的安裝）：</span><span class="sxs-lookup"><span data-stu-id="bf731-111">Review the client coexistence and unsupported scenarios, as applicable to your installation:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-112">部署共存的 App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-112">Deploying coexisting App-V clients</span></span></p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)"><span data-ttu-id="bf731-113">為 App-V 5.1 Sequencer 與 Client 部署進行規劃</span><span class="sxs-lookup"><span data-stu-id="bf731-113">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-114">不支援或有限的安裝案例</span><span class="sxs-lookup"><span data-stu-id="bf731-114">Unsupported or limited installation scenarios</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-115">請參閱 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 支援的設定中的 [用戶端] 區段</span><span class="sxs-lookup"><span data-stu-id="bf731-115">See the client section in <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 Supported Configurations</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="bf731-116">查看用戶端登錄的位置、記錄及疑難排解資訊：</span><span class="sxs-lookup"><span data-stu-id="bf731-116">Review the locations for client registry, log, and troubleshooting information:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bf731-117">用戶端登錄資訊</span><span class="sxs-lookup"><span data-stu-id="bf731-117">Client registry information</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bf731-118">根據預設，在您安裝 App-V 5.1 用戶端之後，用戶端資訊會儲存在下列登錄機碼中：</span><span class="sxs-lookup"><span data-stu-id="bf731-118">By default, after you install the App-V 5.1 client, the client information is stored in the registry in the following registry key:</span></span></p>
<p><strong><span data-ttu-id="bf731-119">HKEY_LOCAL_MACHINE \ 軟體 \ MICROSOFT \ APPV \ 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-119">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT</span></span></strong></p></li>
<li><p><span data-ttu-id="bf731-120">當您將虛擬化套件部署到執行 App-v 用戶端的電腦時，相關聯的套件資料會儲存在下列位置：</span><span class="sxs-lookup"><span data-stu-id="bf731-120">When you deploy a virtualized package to a computer that is running the App-V client, the associated package data is stored in the following location:</span></span></p>
<p><strong><span data-ttu-id="bf731-121">C： \ ProgramData \ App-V</span><span class="sxs-lookup"><span data-stu-id="bf731-121">C: \ ProgramData \ App-V</span></span></strong></p>
<p><span data-ttu-id="bf731-122">不過，您可以使用下列登錄機碼來重新設定此位置：</span><span class="sxs-lookup"><span data-stu-id="bf731-122">However, you can reconfigure this location with the following registry key:</span></span></p>
<p><strong><span data-ttu-id="bf731-123">HKEY_LOCAL_MACHINE \ 軟體 \ MICROSOFT \ 軟體 \ MICROSOFT \ APPV \ 用戶端 \ 資料流程 \ PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="bf731-123">HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ SOFTWARE \ MICROSOFT \ APPV \ CLIENT \ STREAMING \ PACKAGEINSTALLATIONROOT</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bf731-124">用戶端記錄檔</span><span class="sxs-lookup"><span data-stu-id="bf731-124">Client log files</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bf731-125">針對與 App-v 5.1 用戶端相關聯的記錄檔資訊，請在下列記錄中搜尋：</span><span class="sxs-lookup"><span data-stu-id="bf731-125">For log file information that is associated with the App-V 5.1 Client, search in the following log:</span></span></p>
<p><strong><span data-ttu-id="bf731-126">事件記錄/應用程式和服務記錄/Microsoft/AppV</span><span class="sxs-lookup"><span data-stu-id="bf731-126">Event logs / Applications and Services Logs / Microsoft / AppV</span></span></strong></p></li>
<li><p><span data-ttu-id="bf731-127">在 App-v 5.0 SP3 中，部分記錄已整合並移到下列位置：</span><span class="sxs-lookup"><span data-stu-id="bf731-127">In App-V 5.0 SP3, some logs were consolidated and moved to the following location:</span></span></p>
<p><strong><span data-ttu-id="bf731-128">事件記錄/應用程式和服務記錄/Microsoft/AppV/ServiceLog</span><span class="sxs-lookup"><span data-stu-id="bf731-128">Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</span></span></strong></p>
<p><span data-ttu-id="bf731-129">如需已移動之記錄的清單，請參閱 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> 關於 App-V 5.0 SP3 </a> 。</span><span class="sxs-lookup"><span data-stu-id="bf731-129">For a list of the moved logs, see <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)">About App-V 5.0 SP3</a>.</span></span></p></li>
<li><p><span data-ttu-id="bf731-130">在執行 App-v 5.1 用戶端的電腦上，目前儲存在電腦上的套件會儲存到下列位置：</span><span class="sxs-lookup"><span data-stu-id="bf731-130">Packages that are currently stored on computers that run the App-V 5.1 Client are saved to the following location:</span></span></p>
<p><strong><span data-ttu-id="bf731-131">C:\ProgramData\App-V &amp; lt; 封裝 id &gt; &amp; lt; 版本識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="bf731-131">C:\ProgramData\App-V&amp;lt;package id&gt;&amp;lt;version id&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bf731-132">用戶端安裝疑難排解資訊</span><span class="sxs-lookup"><span data-stu-id="bf731-132">Client installation troubleshooting information</span></span></p></td>
<td align="left"><p><span data-ttu-id="bf731-133">請參閱 <strong> % temp% 資料夾中的錯誤記錄 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bf731-133">See the error log in the <strong>%temp%</strong> folder.</span></span> <span data-ttu-id="bf731-134">若要查看記錄檔，請按一下 [ <strong> 開始] </strong> ，輸入 <strong> % temp% </strong> ，然後尋找 <strong> appv_ 記錄 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bf731-134">To review the log files, click <strong>Start</strong>, type <strong>%temp%</strong>, and then look for the <strong>appv_ log</strong>.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bf731-135">若要安裝應用程式-V 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-135">To install the App-V 5.1 Client</span></span>**

1.  <span data-ttu-id="bf731-136">將 App-v 5.1 用戶端安裝檔案複製到安裝該檔案的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bf731-136">Copy the App-V 5.1 client installation file to the computer on which it will be installed.</span></span> <span data-ttu-id="bf731-137">從下列用戶端類型中選擇：</span><span class="sxs-lookup"><span data-stu-id="bf731-137">Choose from the following client types:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="bf731-138">用戶端類型</span><span class="sxs-lookup"><span data-stu-id="bf731-138">Client type</span></span></th>
    <th align="left"><span data-ttu-id="bf731-139">要使用的檔案</span><span class="sxs-lookup"><span data-stu-id="bf731-139">File to use</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bf731-140">用戶端的標準版</span><span class="sxs-lookup"><span data-stu-id="bf731-140">Standard version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="bf731-141">appv_client_setup.exe</span><span class="sxs-lookup"><span data-stu-id="bf731-141">appv_client_setup.exe</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="bf731-142">用戶端的遠端桌面服務版本</span><span class="sxs-lookup"><span data-stu-id="bf731-142">Remote Desktop Services version of the client</span></span></p></td>
    <td align="left"><p><strong><span data-ttu-id="bf731-143">appv_client_setup_rds.exe</span><span class="sxs-lookup"><span data-stu-id="bf731-143">appv_client_setup_rds.exe</span></span></strong></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="bf731-144">按兩下安裝檔，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="bf731-144">Double-click the installation file, and click **Install**.</span></span> <span data-ttu-id="bf731-145">安裝開始之前，安裝程式會檢查電腦是否有任何缺少[的 app-v 5.1 先決條件](app-v-51-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="bf731-145">Before the installation begins, the installer checks the computer for any missing [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

3.  <span data-ttu-id="bf731-146">查看並接受軟體授權條款，選擇是否要使用 Microsoft Update，以及是否要參與 Microsoft 客戶經驗改進計畫，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="bf731-146">Review and accept the Software License Terms, choose whether to use Microsoft Update and whether to participate in the Microsoft Customer Experience Improvement Program, and click **Install**.</span></span>

4.  <span data-ttu-id="bf731-147">在 [**成功完成設定**] 頁面上，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bf731-147">On the **Setup completed successfully** page, click **Close**.</span></span>

    <span data-ttu-id="bf731-148">安裝會在**程式**中為 app-v 用戶端建立下列專案：</span><span class="sxs-lookup"><span data-stu-id="bf731-148">The installation creates the following entries for the App-V client in **Programs**:</span></span>

    -   **<span data-ttu-id="bf731-149">.exe</span><span class="sxs-lookup"><span data-stu-id="bf731-149">.exe</span></span>**

    -   **<span data-ttu-id="bf731-150">.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-150">.msi</span></span>**

    -   **<span data-ttu-id="bf731-151">語言套件</span><span class="sxs-lookup"><span data-stu-id="bf731-151">language pack</span></span>**

        **<span data-ttu-id="bf731-152">注意</span><span class="sxs-lookup"><span data-stu-id="bf731-152">Note</span></span>**  
        <span data-ttu-id="bf731-153">安裝之後，只能卸載 .exe 檔案。</span><span class="sxs-lookup"><span data-stu-id="bf731-153">After the installation, only the .exe file can be uninstalled.</span></span>



**<span data-ttu-id="bf731-154">使用腳本安裝 App-V 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-154">To install the App-V 5.1 client using a script</span></span>**

1. <span data-ttu-id="bf731-155">在目的電腦上安裝所有必要的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="bf731-155">Install all of the required prerequisite software on the target computers.</span></span> <span data-ttu-id="bf731-156">[開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。</span><span class="sxs-lookup"><span data-stu-id="bf731-156">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="bf731-157">如果您使用 .msi 檔案安裝用戶端，則如果缺少任何先決條件，安裝就會失敗。</span><span class="sxs-lookup"><span data-stu-id="bf731-157">If you install the client by using an .msi file, the installation will fail if any prerequisites are missing.</span></span>

2. <span data-ttu-id="bf731-158">若要使用腳本來安裝 App-V 5.1 用戶端，請在**appv\_client\_setup.exe**使用下列參數。</span><span class="sxs-lookup"><span data-stu-id="bf731-158">To use a script to install the App-V 5.1 client, use the following parameters with **appv\_client\_setup.exe**.</span></span>

   **<span data-ttu-id="bf731-159">注意</span><span class="sxs-lookup"><span data-stu-id="bf731-159">Note</span></span>**  
   <span data-ttu-id="bf731-160">用戶端 Windows 安裝程式（.msi）除了 **/log**參數以外，支援相同的一組開關。</span><span class="sxs-lookup"><span data-stu-id="bf731-160">The client Windows Installer (.msi) supports the same set of switches, except for the **/LOG** parameter.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-161">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="bf731-161">/INSTALLDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-162">指定安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="bf731-162">Specifies the installation directory.</span></span> <span data-ttu-id="bf731-163">範例用法： <strong> /INSTALLDIR = C:\Program Files\AppV 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-163">Example usage: <strong>/INSTALLDIR=C:\Program Files\AppV Client</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-164">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="bf731-164">/CEIPOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-165">可參與客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="bf731-165">Enables participation in the Customer Experience Improvement Program.</span></span> <span data-ttu-id="bf731-166">範例用法： <strong> /CEIPOPTIN = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-166">Example usage: <strong>/CEIPOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-167">/MUOPTIN</span><span class="sxs-lookup"><span data-stu-id="bf731-167">/MUOPTIN</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-168">啟用 Microsoft Update。</span><span class="sxs-lookup"><span data-stu-id="bf731-168">Enables Microsoft Update.</span></span> <span data-ttu-id="bf731-169">範例用法： <strong> /MUOPTIN = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-169">Example usage: <strong>/MUOPTIN=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-170">/PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="bf731-170">/PACKAGEINSTALLATIONROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-171">指定要安裝所有新應用程式和更新的目錄。</span><span class="sxs-lookup"><span data-stu-id="bf731-171">Specifies the directory in which to install all new applications and updates.</span></span> <span data-ttu-id="bf731-172">範例用法： <strong> /PACKAGEINSTALLATIONROOT =&#39;C:\App-V 套件&#39;</span><span class="sxs-lookup"><span data-stu-id="bf731-172">Example usage: <strong>/PACKAGEINSTALLATIONROOT=&#39;C:\App-V Packages&#39;</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-173">/PACKAGESOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="bf731-173">/PACKAGESOURCEROOT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-174">覆寫下載套件內容的來源位置。</span><span class="sxs-lookup"><span data-stu-id="bf731-174">Overrides the source location for downloading package content.</span></span> <span data-ttu-id="bf731-175">範例用法： <strong> /PACKAGESOURCEROOT =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</span><span class="sxs-lookup"><span data-stu-id="bf731-175">Example usage: <strong>/PACKAGESOURCEROOT=&#39;<a href="http://packageStore" data-raw-source="http://packageStore">http://packageStore</a>&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-176">/AUTOLOAD</span><span class="sxs-lookup"><span data-stu-id="bf731-176">/AUTOLOAD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-177">指定在特定電腦上由 App-v 5.1 載入新套件的方式。</span><span class="sxs-lookup"><span data-stu-id="bf731-177">Specifies how new packages will be loaded by App-V 5.1 on a specific computer.</span></span> <span data-ttu-id="bf731-178">已啟用下列選項： [1];自動載入所有套件 [2];或自動載入無套件 [0]。 <strong>範例用法：/AUTOLOAD = [0 | 1 | 2]</span><span class="sxs-lookup"><span data-stu-id="bf731-178">The following options are enabled: [1]; automatically load all packages [2]; or automatically load no packages [0].<strong>Example usage: /AUTOLOAD=[0|1|2]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-179">/SHAREDCONTENTSTOREMODE</span><span class="sxs-lookup"><span data-stu-id="bf731-179">/SHAREDCONTENTSTOREMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-180">指定不會將流式套件內容儲存到本機硬碟。</span><span class="sxs-lookup"><span data-stu-id="bf731-180">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span> <span data-ttu-id="bf731-181">範例用法： <strong> /SHAREDCONTENTSTOREMODE = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-181">Example usage: <strong>/SHAREDCONTENTSTOREMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-182">/MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="bf731-182">/MIGRATIONMODE</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-183">允許 App-v 5.1 用戶端修改與使用舊版建立之套件相關聯的快捷方式與 FTAs。</span><span class="sxs-lookup"><span data-stu-id="bf731-183">Allows the App-V 5.1 client to modify the shortcuts and FTAs that are associated with the packages that are created with a previous version.</span></span> <span data-ttu-id="bf731-184">範例用法： <strong> /MIGRATIONMODE = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-184">Example usage: <strong>/MIGRATIONMODE=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-185">/ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="bf731-185">/ENABLEPACKAGESCRIPTS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-186">啟用要執行的套件資訊清單檔案或設定檔中定義的腳本。</span><span class="sxs-lookup"><span data-stu-id="bf731-186">Enables the scripts that are defined in the package manifest file or configuration files that should run.</span></span> <span data-ttu-id="bf731-187">範例用法： <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-187">Example usage: <strong>/ENABLEPACKAGESCRIPTS=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-188">/ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="bf731-188">/ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-189">指定不會與使用者設定檔一起漫遊的登錄路徑。</span><span class="sxs-lookup"><span data-stu-id="bf731-189">Specifies the registry paths that will not roam with a user profile.</span></span> <span data-ttu-id="bf731-190">範例用法： <strong> /ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</span><span class="sxs-lookup"><span data-stu-id="bf731-190">Example usage: <strong>/ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-191">/ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="bf731-191">/ROAMINGFILEEXCLUSIONS</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-192">指定相對於% userprofile% （不會與使用者&#39;s 設定檔漫遊）的檔路徑。</span><span class="sxs-lookup"><span data-stu-id="bf731-192">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="bf731-193">範例用法： <strong> /ROAMINGFILEEXCLUSIONS &#39;桌面; 我的圖片&#39;</span><span class="sxs-lookup"><span data-stu-id="bf731-193">Example usage: <strong>/ROAMINGFILEEXCLUSIONS &#39;desktop;my pictures&#39;</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-194">/S [1-5] PUBLISHINGSERVERNAME</span><span class="sxs-lookup"><span data-stu-id="bf731-194">/S[1-5]PUBLISHINGSERVERNAME</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-195">顯示發佈伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="bf731-195">Displays the name of the publishing server.</span></span> <span data-ttu-id="bf731-196">範例用法： <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</span><span class="sxs-lookup"><span data-stu-id="bf731-196">Example usage: <strong>/S2PUBLISHINGSERVERNAME=MyPublishingServer</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-197">/S [1-5] PUBLISHINGSERVERURL</span><span class="sxs-lookup"><span data-stu-id="bf731-197">/S[1-5]PUBLISHINGSERVERURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-198">顯示發佈伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="bf731-198">Displays the URL of the publishing server.</span></span> <span data-ttu-id="bf731-199">範例用法： <strong> /S2PUBLISHINGSERVERURL = \pubserver</span><span class="sxs-lookup"><span data-stu-id="bf731-199">Example usage: <strong>/S2PUBLISHINGSERVERURL=\pubserver</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-200">/S [1-5] GLOBALREFRESHENABLED-</span><span class="sxs-lookup"><span data-stu-id="bf731-200">/S[1-5]GLOBALREFRESHENABLED -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-201">啟用全域發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-201">Enables a global publishing refresh.</span></span> <span data-ttu-id="bf731-202">範例用法： <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-202">Example usage: <strong>/S2GLOBALREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-203">/S [1-5] GLOBALREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="bf731-203">/S[1-5]GLOBALREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-204">在使用者登入時，啟動全域發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-204">Initiates a global publishing refresh when a user logs on.</span></span> <span data-ttu-id="bf731-205">範例用法： <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-205">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-206">/S [1-5] GLOBALREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="bf731-206">/S[1-5]GLOBALREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-207">指定發佈重新整理間隔，其中 <strong> 0 </strong> 代表不定期重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-207">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="bf731-208">範例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="bf731-208">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-209">/S [1-5] GLOBALREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="bf731-209">/S[1-5]GLOBALREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-210">指定間隔單位（小時 [0]，天 [1]）。</span><span class="sxs-lookup"><span data-stu-id="bf731-210">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="bf731-211">範例用法： <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-211">Example usage: <strong>/S2GLOBALREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-212">/S [1-5] USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="bf731-212">/S[1-5]USERREFRESHENABLED</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-213">啟用使用者發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-213">Enables user publishing refresh.</span></span> <span data-ttu-id="bf731-214">範例用法： <strong> /S2USERREFRESHENABLED = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-214">Example usage: <strong>/S2USERREFRESHENABLED=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-215">/S [1-5] USERREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="bf731-215">/S[1-5]USERREFRESHONLOGON</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-216">在使用者登入時，啟動使用者發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-216">Initiates a user publishing refresh when a user logs on.</span></span> <span data-ttu-id="bf731-217">範例用法： <strong> /S2LOGONREFRESH = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-217">Example usage: <strong>/S2LOGONREFRESH=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-218">/S [1-5] USERREFRESHINTERVAL-</span><span class="sxs-lookup"><span data-stu-id="bf731-218">/S[1-5]USERREFRESHINTERVAL -</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-219">指定發佈重新整理間隔，其中 <strong> 0 </strong> 代表不定期重新整理。</span><span class="sxs-lookup"><span data-stu-id="bf731-219">Specifies the publishing refresh interval, where <strong>0</strong> indicates do not periodically refresh.</span></span> <span data-ttu-id="bf731-220">範例用法： <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</span><span class="sxs-lookup"><span data-stu-id="bf731-220">Example usage: <strong>/S2PERIODICREFRESHINTERVAL=[0-744]</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-221">/S [1-5] USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="bf731-221">/S[1-5]USERREFRESHINTERVALUNIT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-222">指定間隔單位（小時 [0]，天 [1]）。</span><span class="sxs-lookup"><span data-stu-id="bf731-222">Specifies the interval unit (Hours[0], Days[1]).</span></span> <span data-ttu-id="bf731-223">範例用法： <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</span><span class="sxs-lookup"><span data-stu-id="bf731-223">Example usage: <strong>/S2USERREFRESHINTERVALUNIT=[0|1]</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-224">/Log</span><span class="sxs-lookup"><span data-stu-id="bf731-224">/Log</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-225">指定儲存記錄資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="bf731-225">Specifies a location where the log information is saved.</span></span> <span data-ttu-id="bf731-226">預設位置是% Temp%。</span><span class="sxs-lookup"><span data-stu-id="bf731-226">The default location is %Temp%.</span></span> <span data-ttu-id="bf731-227">範例用法： <strong> /Log C:\logs\log.log</span><span class="sxs-lookup"><span data-stu-id="bf731-227">Example usage: <strong>/log C:\logs\log.log</span></span></strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-228">/q</span><span class="sxs-lookup"><span data-stu-id="bf731-228">/q</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-229">指定無人參與的安裝。</span><span class="sxs-lookup"><span data-stu-id="bf731-229">Specifies an unattended installation.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-230">/REPAIR</span><span class="sxs-lookup"><span data-stu-id="bf731-230">/REPAIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-231">修復先前的用戶端安裝。</span><span class="sxs-lookup"><span data-stu-id="bf731-231">Repairs a previous client installation.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-232">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="bf731-232">/NORESTART</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-233">防止電腦在用戶端安裝之後重新開機。</span><span class="sxs-lookup"><span data-stu-id="bf731-233">Prevents the computer from rebooting after the client installation.</span></span></p>
   <p><span data-ttu-id="bf731-234">在安裝每個更新之後，此參數會防止使用者電腦重新開機，並可讓您在方便時排程重新開機。</span><span class="sxs-lookup"><span data-stu-id="bf731-234">The parameter prevents the end-user computer from rebooting after each update is installed and lets you schedule the reboot at your convenience.</span></span> <span data-ttu-id="bf731-235">例如，您可以安裝 App-v 5.1，然後安裝修複程式套件 Y，而不在 Service Pack 安裝之後重新開機。</span><span class="sxs-lookup"><span data-stu-id="bf731-235">For example, you can install App-V 5.1 and then install Hotfix Package Y without rebooting after the Service Pack installation.</span></span> <span data-ttu-id="bf731-236">安裝之後，您必須先重新開機，才能開始使用 app-v。</span><span class="sxs-lookup"><span data-stu-id="bf731-236">After the installation, you must reboot before you start using App-V.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-237">/UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="bf731-237">/UNINSTALL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-238">卸載用戶端。</span><span class="sxs-lookup"><span data-stu-id="bf731-238">Uninstalls the client.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-239">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="bf731-239">/ACCEPTEULA</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-240">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="bf731-240">Accepts the license agreement.</span></span> <span data-ttu-id="bf731-241">這對於無操作安裝是必要的。</span><span class="sxs-lookup"><span data-stu-id="bf731-241">This is required for an unattended installation.</span></span> <span data-ttu-id="bf731-242">範例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bf731-242">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-243">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="bf731-243">/LAYOUT</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-244">指定相關聯的版面配置動作。</span><span class="sxs-lookup"><span data-stu-id="bf731-244">Specifies the associated layout action.</span></span> <span data-ttu-id="bf731-245">它也會將 Windows Installer （.msi）及腳本檔案解壓縮至資料夾，但不安裝 App-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="bf731-245">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.1.</span></span> <span data-ttu-id="bf731-246">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="bf731-246">No value is expected.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bf731-247">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="bf731-247">/LAYOUTDIR</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-248">指定版面配置目錄。</span><span class="sxs-lookup"><span data-stu-id="bf731-248">Specifies the layout directory.</span></span> <span data-ttu-id="bf731-249">需要字串值。</span><span class="sxs-lookup"><span data-stu-id="bf731-249">Requires a string value.</span></span> <span data-ttu-id="bf731-250">範例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 用戶端" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="bf731-250">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bf731-251">/？、/h、/help</span><span class="sxs-lookup"><span data-stu-id="bf731-251">/?, /h, /help</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bf731-252">要求上一個安裝參數的相關協助。</span><span class="sxs-lookup"><span data-stu-id="bf731-252">Requests help about the previous installation parameters.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="bf731-253">使用 Windows Installer （.msi）檔案安裝 App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-253">To install the App-V 5.1 client by using the Windows Installer (.msi) file</span></span>**

1.  <span data-ttu-id="bf731-254">在目的電腦上安裝必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="bf731-254">Install the required prerequisites on the target computers.</span></span> <span data-ttu-id="bf731-255">[開始之前，](#bkmk-clt-install-prereqs)請參閱處理方式。</span><span class="sxs-lookup"><span data-stu-id="bf731-255">See [What to do before you start](#bkmk-clt-install-prereqs).</span></span> <span data-ttu-id="bf731-256">如果未滿足任何先決條件，安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="bf731-256">If any prerequisites are not met, the installation will fail.</span></span>

2.  <span data-ttu-id="bf731-257">在使用 App-v 5.1 Windows 安裝程式（.msi）檔案安裝用戶端之前，請確定目的電腦沒有任何掛起的重新開機。</span><span class="sxs-lookup"><span data-stu-id="bf731-257">Ensure that the target computers do not have any pending restarts before you install the client using the App-V 5.1 Windows Installer (.msi) files.</span></span> <span data-ttu-id="bf731-258">Windows Installer 檔案不會標示掛起的重新開機。</span><span class="sxs-lookup"><span data-stu-id="bf731-258">The Windows Installer files do not flag a pending restart.</span></span>

3.  <span data-ttu-id="bf731-259">將下列其中一個 Windows 安裝程式檔案部署到目的電腦。</span><span class="sxs-lookup"><span data-stu-id="bf731-259">Deploy one of the following Windows Installer files to the target computer.</span></span> <span data-ttu-id="bf731-260">您指定的檔案必須符合目的電腦的設定。</span><span class="sxs-lookup"><span data-stu-id="bf731-260">The file that you specify must match the configuration of the target computer.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="bf731-261">部署類型</span><span class="sxs-lookup"><span data-stu-id="bf731-261">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="bf731-262">部署此檔案</span><span class="sxs-lookup"><span data-stu-id="bf731-262">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bf731-263">電腦正在執行32位 Microsoft Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="bf731-263">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bf731-264">appv_client_MSI_x86.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-264">appv_client_MSI_x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="bf731-265">電腦正在執行64位 Microsoft Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="bf731-265">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bf731-266">appv_client_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-266">appv_client_MSI_x64.msi</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bf731-267">您要部署 App-v 5.1 遠端桌面服務用戶端</span><span class="sxs-lookup"><span data-stu-id="bf731-267">You are deploying the App-V 5.1 Remote Desktop Services client</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bf731-268">appv_client_rds_MSI_x64.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-268">appv_client_rds_MSI_x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="bf731-269">使用下表中的資訊，根據目的電腦所需的語言選取適當的語言套件（msi）來安裝 **。**</span><span class="sxs-lookup"><span data-stu-id="bf731-269">Using the information in the following table, select the appropriate language pack **.msi** to install, based on the desired language for the target computer.</span></span> <span data-ttu-id="bf731-270">資料表中的**xxxx**參照語言套件的目的地區域設定。</span><span class="sxs-lookup"><span data-stu-id="bf731-270">The **xxxx** in the table refers to the target locale of the language pack.</span></span>

    **<span data-ttu-id="bf731-271">開始之前的須知：</span><span class="sxs-lookup"><span data-stu-id="bf731-271">What to know before you start:</span></span>**

    -   <span data-ttu-id="bf731-272">標準 App-V 5.1 用戶端和 App-V 5.1 用戶端的遠端桌面服務版本都有語言套件。</span><span class="sxs-lookup"><span data-stu-id="bf731-272">The language packs are common to both the standard App-V 5.1 client and the Remote Desktop Services version of the App-V 5.1 client.</span></span>

    -   <span data-ttu-id="bf731-273">如果您使用 **.exe**安裝 app-v 5.1 用戶端，安裝程式將只部署與目的電腦上執行之作業系統相符的語言套件。</span><span class="sxs-lookup"><span data-stu-id="bf731-273">If you install the App-V 5.1 client using the **.exe**, the installer will deploy only the language pack that matches the operating system running on the target computer.</span></span>

    -   <span data-ttu-id="bf731-274">若要在目的電腦上部署其他語言套件，請使用**Windows 安裝程式（.msi）檔案，使用安裝 app-v 5.1 用戶端的程式**。</span><span class="sxs-lookup"><span data-stu-id="bf731-274">To deploy additional language packs on a target computer, use the procedure **To install the App-V 5.1 client by using Windows Installer (.msi) file**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="bf731-275">部署類型</span><span class="sxs-lookup"><span data-stu-id="bf731-275">Type of deployment</span></span></th>
    <th align="left"><span data-ttu-id="bf731-276">部署此檔案</span><span class="sxs-lookup"><span data-stu-id="bf731-276">Deploy this file</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="bf731-277">電腦正在執行32位 Microsoft Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="bf731-277">Computer is running a 32-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bf731-278">appv_client_LP_xxxx_ x86.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-278">appv_client_LP_xxxx_ x86.msi</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="bf731-279">電腦正在執行64位 Microsoft Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="bf731-279">Computer is running a 64-bit Microsoft Windows operating system</span></span></p></td>
    <td align="left"><p><span data-ttu-id="bf731-280">appv_client_LP_xxxx_ x64.msi</span><span class="sxs-lookup"><span data-stu-id="bf731-280">appv_client_LP_xxxx_ x64.msi</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="bf731-281">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf731-281">Related topics</span></span>


[<span data-ttu-id="bf731-282">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bf731-282">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="bf731-283">關於 Client 組態設定</span><span class="sxs-lookup"><span data-stu-id="bf731-283">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

[<span data-ttu-id="bf731-284">如何解除安裝 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="bf731-284">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)









