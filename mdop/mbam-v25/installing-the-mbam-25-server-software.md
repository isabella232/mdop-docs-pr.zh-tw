---
title: 安裝 MBAM 2.5 伺服器軟體
description: 安裝 MBAM 2.5 伺服器軟體
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809927"
---
# <span data-ttu-id="5d38f-103">安裝 MBAM 2.5 伺服器軟體</span><span class="sxs-lookup"><span data-stu-id="5d38f-103">Installing the MBAM 2.5 Server Software</span></span>


<span data-ttu-id="5d38f-104">本主題描述如何使用 Microsoft BitLocker 管理及監視設定向導或使用命令列參數，來安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 伺服器軟體。</span><span class="sxs-lookup"><span data-stu-id="5d38f-104">This topic describes how to install the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard or by using command-line parameters.</span></span> <span data-ttu-id="5d38f-105">針對您正在設定 MBAM 2.5 Server 功能的每個伺服器，重複執行伺服器安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5d38f-105">Repeat the server installation process for each server on which you are configuring MBAM 2.5 Server features.</span></span> <span data-ttu-id="5d38f-106">完成安裝之後，請參閱設定[MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)，以取得設定伺服器功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="5d38f-106">After you finish the installation, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md) for steps about configuring the Server features.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5d38f-107">開始之前</span><span class="sxs-lookup"><span data-stu-id="5d38f-107">Before you start</span></span></th>
<th align="left"><span data-ttu-id="5d38f-108">描述</span><span class="sxs-lookup"><span data-stu-id="5d38f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d38f-109">查看 MBAM 2.5 規劃資訊</span><span class="sxs-lookup"><span data-stu-id="5d38f-109">Review the MBAM 2.5 planning information</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="5d38f-110">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="5d38f-110">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="5d38f-111">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="5d38f-111">MBAM 2.5 Supported Configurations</span></span></a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="5d38f-112">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="5d38f-112">High-Level Architecture for MBAM 2.5</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d38f-113">閱讀如何取得記錄檔</span><span class="sxs-lookup"><span data-stu-id="5d38f-113">Read how to get log files</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-114">根據預設，會在本機電腦的% temp% 資料夾中建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="5d38f-114">By default, log files are created in the local computer’s %temp% folder.</span></span> <span data-ttu-id="5d38f-115">若要將記錄檔寫入特定位置，而不是寫入 <strong> % temp </strong> % 資料夾，請使用 <strong> /log </strong> &lt; <em> location </em> &gt; 引數。</span><span class="sxs-lookup"><span data-stu-id="5d38f-115">To write the log files to a specific location rather than to the <strong>%temp</strong>% folder, use the <strong>/log</strong> &lt;<em>location</em>&gt; argument.</span></span></p>
<p><span data-ttu-id="5d38f-116">在 [ <strong> </strong> <strong> </strong> <strong> 應用程式和服務記錄 &gt; Microsoft Windows] 下 &gt; </strong> ，可能會在事件檢視器的 [MBAM-設定] 或 MBAM 網頁節點中記錄其他事件。</span><span class="sxs-lookup"><span data-stu-id="5d38f-116">Additional events might be logged in Event Viewer in the <strong>MBAM-Setup</strong> or <strong>MBAM-Web</strong> nodes under <strong>Applications and Services Logs &gt; Microsoft &gt; Windows</strong>.</span></span> <span data-ttu-id="5d38f-117">例如，如果您卸載 MBAM，卸載程式也會在 EventViewer 中卸載 MBAM 設定和 MBAM Web 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d38f-117">For example, if you uninstall MBAM, the uninstaller will also uninstall the MBAM-Setup and MBAM-Web logs in EventViewer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5d38f-118">使用 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM 2.5 Server 軟體</span><span class="sxs-lookup"><span data-stu-id="5d38f-118">Installing the MBAM 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard</span></span>


<span data-ttu-id="5d38f-119">使用這些步驟，透過 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="5d38f-119">Use these steps to install the MBAM Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="5d38f-120">使用嚮導來安裝 MBAM 2.5 Server 軟體</span><span class="sxs-lookup"><span data-stu-id="5d38f-120">To install the MBAM 2.5 Server software by using the wizard</span></span>**

1.  <span data-ttu-id="5d38f-121">在您要安裝 MBAM 的伺服器上，執行**MBAMserversetup.exe**以啟動 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="5d38f-121">On the server where you want to install MBAM, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="5d38f-122">在 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d38f-122">On the **Welcome** page, click **Next**.</span></span>

3.  <span data-ttu-id="5d38f-123">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="5d38f-123">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="5d38f-124">選擇是否要在檢查更新時使用 Microsoft Update，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d38f-124">Choose whether to use Microsoft Update when you check for updates, and then click **Next**.</span></span>

5.  <span data-ttu-id="5d38f-125">選擇是否要參與客戶經驗改進計畫，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="5d38f-125">Choose whether to participate in the Customer Experience Improvement Program, and then click **Next**.</span></span>

6.  <span data-ttu-id="5d38f-126">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="5d38f-126">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="5d38f-127">若要在 MBAM Server 軟體完成安裝之後設定伺服器功能，請選取 [在**嚮導關閉後執行 MBAM 伺服器設定]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5d38f-127">To configure the server features after the MBAM Server software finishes installing, select the **Run MBAM Server Configuration after the wizard closes** check box.</span></span> <span data-ttu-id="5d38f-128">或者，您可以在稍後使用伺服器安裝在 [**開始**] 功能表上建立的 [ **MBAM 伺服器**設定] 快捷方式來設定 MBAM。</span><span class="sxs-lookup"><span data-stu-id="5d38f-128">Alternatively, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.</span></span>

8.  <span data-ttu-id="5d38f-129">按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="5d38f-129">Click **Finish**.</span></span>

## <span data-ttu-id="5d38f-130">使用命令提示字元視窗安裝 MBAM 2.5 Server 軟體</span><span class="sxs-lookup"><span data-stu-id="5d38f-130">Installing the MBAM 2.5 Server software by using a Command Prompt window</span></span>


<span data-ttu-id="5d38f-131">在命令提示字元中，輸入類似下列命令的命令來安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="5d38f-131">At a command prompt, type a command similar to the following command to install the MBAM Server software.</span></span>

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

<span data-ttu-id="5d38f-132">下表說明安裝 MBAM 2.5 Server 軟體的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="5d38f-132">The following table describes the command-line parameters for installing the MBAM 2.5 Server software.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5d38f-133">參數</span><span class="sxs-lookup"><span data-stu-id="5d38f-133">Parameter</span></span></th>
<th align="left"><span data-ttu-id="5d38f-134">參數值</span><span class="sxs-lookup"><span data-stu-id="5d38f-134">Parameter value</span></span></th>
<th align="left"><span data-ttu-id="5d38f-135">描述</span><span class="sxs-lookup"><span data-stu-id="5d38f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d38f-136">CEIPENABLED</span><span class="sxs-lookup"><span data-stu-id="5d38f-136">CEIPENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-137">True False</span><span class="sxs-lookup"><span data-stu-id="5d38f-137">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-138">True-參與客戶改進體驗計畫，協助 Microsoft 找出要改善哪些 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="5d38f-138">True - participate in the Customer Improvement Experience Program, which helps Microsoft identify which MBAM features to improve.</span></span></p>
<p><span data-ttu-id="5d38f-139">False –不參與客戶改進體驗計畫。</span><span class="sxs-lookup"><span data-stu-id="5d38f-139">False – do not participate in the Customer Improvement Experience Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d38f-140">OPTIN_FOR_MICROSOFT_UPDATES</span><span class="sxs-lookup"><span data-stu-id="5d38f-140">OPTIN_FOR_MICROSOFT_UPDATES</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-141">True False</span><span class="sxs-lookup"><span data-stu-id="5d38f-141">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-142">True-使用 Microsoft Update，讓您的電腦擁有最新的 Windows 和其他 Microsoft 產品，包括 MBAM。</span><span class="sxs-lookup"><span data-stu-id="5d38f-142">True - use Microsoft Update to keep your computer secure and up-to-date for Windows and other Microsoft products, including MBAM.</span></span></p>
<p><span data-ttu-id="5d38f-143">False –不使用 Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="5d38f-143">False – do not use Microsoft Update</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d38f-144">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="5d38f-144">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-145">&lt;路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="5d38f-145">&lt;Path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-146">您想要安裝 MBAM 的位置。</span><span class="sxs-lookup"><span data-stu-id="5d38f-146">Location where you want to install MBAM.</span></span></p>
<p><span data-ttu-id="5d38f-147">範例：</span><span class="sxs-lookup"><span data-stu-id="5d38f-147">Example:</span></span></p>
<p><span data-ttu-id="5d38f-148">INSTALLDIR = c:\mbaminstall</span><span class="sxs-lookup"><span data-stu-id="5d38f-148">INSTALLDIR=c:\mbaminstall</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d38f-149">FORCE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="5d38f-149">FORCE_UNINSTALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-150">True False</span><span class="sxs-lookup"><span data-stu-id="5d38f-150">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d38f-151">True-繼續卸載 MBAM 的程式，即使無法移除任何功能也一樣。</span><span class="sxs-lookup"><span data-stu-id="5d38f-151">True - continue the process of uninstalling MBAM, even if any features fail to be removed.</span></span></p>
<p><span data-ttu-id="5d38f-152">False （預設）如果卸載自訂動作無法移除已新增的 MBAM 伺服器功能，則卸載會失敗，而 MBAM 仍會保持安裝狀態。</span><span class="sxs-lookup"><span data-stu-id="5d38f-152">False (default) if the uninstallation custom action fails to remove an added MBAM Server feature, the uninstallation fails, and MBAM remains installed.</span></span></p>
<p><span data-ttu-id="5d38f-153">在這兩個實例中，嘗試卸載 MBAM 期間已成功移除的任何功能都會保持移除。</span><span class="sxs-lookup"><span data-stu-id="5d38f-153">In both instances, any features that were successfully removed during the attempt to uninstall MBAM stay removed.</span></span></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="5d38f-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="5d38f-154">Related topics</span></span>


[<span data-ttu-id="5d38f-155">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="5d38f-155">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="5d38f-156">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="5d38f-156">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="5d38f-157">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="5d38f-157">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="5d38f-158">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="5d38f-158">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="5d38f-159">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="5d38f-159">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





