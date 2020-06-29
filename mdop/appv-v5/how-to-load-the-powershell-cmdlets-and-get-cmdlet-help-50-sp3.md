---
title: 如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明
description: 如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明
author: dansimp
ms.assetid: 0624495b-943e-485b-9e54-b50e4ee6591c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 7692d3e36aabc4f3142f664e94d9d71b2cfc1bd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800473"
---
# <span data-ttu-id="f7001-103">如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="f7001-103">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span>


<span data-ttu-id="f7001-104">本主題涵蓋的內容：</span><span class="sxs-lookup"><span data-stu-id="f7001-104">What this topic covers:</span></span>

-   [<span data-ttu-id="f7001-105">使用 PowerShell Cmdlet 的需求</span><span class="sxs-lookup"><span data-stu-id="f7001-105">Requirements for using PowerShell cmdlets</span></span>](#bkmk-reqs-using-posh)

-   [<span data-ttu-id="f7001-106">載入 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f7001-106">Loading the PowerShell cmdlets</span></span>](#bkmk-load-cmdlets)

-   [<span data-ttu-id="f7001-107">取得 PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="f7001-107">Getting help for the PowerShell cmdlets</span></span>](#bkmk-get-cmdlet-help)

-   [<span data-ttu-id="f7001-108">顯示 PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="f7001-108">Displaying the help for a PowerShell cmdlet</span></span>](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a><span data-ttu-id="f7001-109">使用 PowerShell Cmdlet 的需求</span><span class="sxs-lookup"><span data-stu-id="f7001-109">Requirements for using PowerShell cmdlets</span></span>


<span data-ttu-id="f7001-110">請參閱下列使用 App-v PowerShell Cmdlet 的需求：</span><span class="sxs-lookup"><span data-stu-id="f7001-110">Review the following requirements for using the App-V PowerShell cmdlets:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7001-111">需求</span><span class="sxs-lookup"><span data-stu-id="f7001-111">Requirement</span></span></th>
<th align="left"><span data-ttu-id="f7001-112">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f7001-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-113">只有當您使用下列其中一種方法，才能執行 App-v Server Cmdlet 的授權：</span><span class="sxs-lookup"><span data-stu-id="f7001-113">Users can run App-V Server cmdlets only if you grant them access by using one of the following methods:</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="f7001-114">當您部署並設定 App-v Server 時 </strong> ：</span><span class="sxs-lookup"><span data-stu-id="f7001-114">When you are deploying and configuring the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="f7001-115">指定擁有管理 App V 環境許可權的 Active Directory 群組或個別使用者。</span><span class="sxs-lookup"><span data-stu-id="f7001-115">Specify an Active Directory group or individual user that has permissions to manage the App-V environment.</span></span> <span data-ttu-id="f7001-116">瞭解 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> 如何部署 app-v 5.0 伺服器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f7001-116">See <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">How to Deploy the App-V 5.0 Server</a>.</span></span></p></li>
<li><p><strong><span data-ttu-id="f7001-117">在您部署 App-v Server 後 </strong> ：</span><span class="sxs-lookup"><span data-stu-id="f7001-117">After you’ve deployed the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="f7001-118">使用 App-v 管理主控台新增其他 Active Directory 群組或使用者。</span><span class="sxs-lookup"><span data-stu-id="f7001-118">Use the App-V Management console to add an additional Active Directory group or user.</span></span> <span data-ttu-id="f7001-119">瞭解 <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)"> 如何使用管理主控台新增或移除系統管理員 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f7001-119">See <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)">How to Add or Remove an Administrator by Using the Management Console</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7001-120">需要提升許可權的命令提示字元的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f7001-120">Cmdlets that require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f7001-121">附加 AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="f7001-121">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="f7001-122">移除-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="f7001-122">Remove-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="f7001-123">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="f7001-123">Set-AppvClientConfiguration</span></span></p></li>
<li><p><span data-ttu-id="f7001-124">附加 AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="f7001-124">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="f7001-125">移除-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="f7001-125">Remove-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="f7001-126">附加 AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="f7001-126">Add-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="f7001-127">移除-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="f7001-127">Remove-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="f7001-128">傳送 AppvClientReport</span><span class="sxs-lookup"><span data-stu-id="f7001-128">Send-AppvClientReport</span></span></p></li>
<li><p><span data-ttu-id="f7001-129">Set-AppvClientMode</span><span class="sxs-lookup"><span data-stu-id="f7001-129">Set-AppvClientMode</span></span></p></li>
<li><p><span data-ttu-id="f7001-130">Set-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="f7001-130">Set-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="f7001-131">Set-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="f7001-131">Set-AppvPublishingServer</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-132">最終使用者可以執行的 Cmdlet，除非您將其設定為需要提升的命令提示字元</span><span class="sxs-lookup"><span data-stu-id="f7001-132">Cmdlets that end users can run, unless you configure them to require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f7001-133">發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="f7001-133">Publish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="f7001-134">取消發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="f7001-134">Unpublish-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="f7001-135">若要將這些 Cmdlet 設定為需要提升許可權的命令提示字元，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="f7001-135">To configure these cmdlets to require an elevated command prompt, use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7001-136">方法</span><span class="sxs-lookup"><span data-stu-id="f7001-136">Method</span></span></th>
<th align="left"><span data-ttu-id="f7001-137">更多資源</span><span class="sxs-lookup"><span data-stu-id="f7001-137">More resources</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-138"><strong> </strong> 使用 <strong> -RequirePublishAsAdmin 參數執行 AppvClientConfiguration Cmdlet </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f7001-138">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>-RequirePublishAsAdmin</strong> parameter.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="f7001-139">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="f7001-139">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="f7001-140">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="f7001-140">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7001-141">針對應用程式 V 用戶端啟用 [需要以系統管理員身分發布] 群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="f7001-141">Enable the “Require publish as administrator” Group Policy setting for App-V Clients.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)"><span data-ttu-id="f7001-142">如何使用 Management Console 發佈套件</span><span class="sxs-lookup"><span data-stu-id="f7001-142">How to Publish a Package by Using the Management Console</span></span></a> </p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a><span data-ttu-id="f7001-143">載入 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f7001-143">Loading the PowerShell cmdlets</span></span>
<span data-ttu-id="f7001-144">載入 PowerShell Cmdlet 模組：</span><span class="sxs-lookup"><span data-stu-id="f7001-144">To load the PowerShell cmdlet modules:</span></span>

1.  <span data-ttu-id="f7001-145">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="f7001-145">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="f7001-146">輸入下列其中一個命令來載入您想要的模組的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7001-146">Type one of the following commands to load the cmdlets for the module you want:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7001-147">App-v 元件</span><span class="sxs-lookup"><span data-stu-id="f7001-147">App-V component</span></span></th>
<th align="left"><span data-ttu-id="f7001-148">輸入的命令</span><span class="sxs-lookup"><span data-stu-id="f7001-148">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-149">App-v Server</span><span class="sxs-lookup"><span data-stu-id="f7001-149">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-150">匯入-模組 AppvServer</span><span class="sxs-lookup"><span data-stu-id="f7001-150">Import-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7001-151">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="f7001-151">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-152">匯入-模組 AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="f7001-152">Import-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-153">App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="f7001-153">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-154">匯入-模組 AppvClient</span><span class="sxs-lookup"><span data-stu-id="f7001-154">Import-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="f7001-155">取得 PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="f7001-155">Getting help for the PowerShell cmdlets</span></span>
<span data-ttu-id="f7001-156">從 App-v 5.0 SP3 開始，以下兩種格式可提供 Cmdlet 說明：</span><span class="sxs-lookup"><span data-stu-id="f7001-156">Starting in App-V 5.0 SP3, cmdlet help is available in two formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7001-157">格式</span><span class="sxs-lookup"><span data-stu-id="f7001-157">Format</span></span></th>
<th align="left"><span data-ttu-id="f7001-158">說明</span><span class="sxs-lookup"><span data-stu-id="f7001-158">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-159">以可下載的模組</span><span class="sxs-lookup"><span data-stu-id="f7001-159">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-160">下載 Cmdlet 模組後，請下載最新的協助：</span><span class="sxs-lookup"><span data-stu-id="f7001-160">To download the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="f7001-161">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="f7001-161">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="f7001-162">輸入下列其中一個命令來載入您想要的模組的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7001-162">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7001-163">App-v 元件</span><span class="sxs-lookup"><span data-stu-id="f7001-163">App-V component</span></span></th>
<th align="left"><span data-ttu-id="f7001-164">輸入的命令</span><span class="sxs-lookup"><span data-stu-id="f7001-164">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-165">App-v Server</span><span class="sxs-lookup"><span data-stu-id="f7001-165">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-166">更新-協助-模組 AppvServer</span><span class="sxs-lookup"><span data-stu-id="f7001-166">Update-Help -Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7001-167">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="f7001-167">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-168">更新-協助-模組 AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="f7001-168">Update-Help -Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7001-169">App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="f7001-169">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-170">更新-協助-模組 AppvClient</span><span class="sxs-lookup"><span data-stu-id="f7001-170">Update-Help -Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7001-171">在 TechNet 上為網頁</span><span class="sxs-lookup"><span data-stu-id="f7001-171">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7001-172">請參閱 Microsoft 桌上出版 [優化套件自動化] 下的 app-v 節點， <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> 以使用 Windows PowerShell </a> 。</span><span class="sxs-lookup"><span data-stu-id="f7001-172">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-display-help-cmdlet"></a><span data-ttu-id="f7001-173">顯示 PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="f7001-173">Displaying the help for a PowerShell cmdlet</span></span>
<span data-ttu-id="f7001-174">若要顯示特定 PowerShell Cmdlet 的說明：</span><span class="sxs-lookup"><span data-stu-id="f7001-174">To display help for a specific PowerShell cmdlet:</span></span>

1.  <span data-ttu-id="f7001-175">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="f7001-175">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="f7001-176">輸入**get-help** &lt; *Cmdlet* &gt; ，例如， **get-help AppvClientPackage**。</span><span class="sxs-lookup"><span data-stu-id="f7001-176">Type **Get-Help** &lt;*cmdlet*&gt;, for example, **Get-Help Publish-AppvClientPackage**.</span></span>

<span data-ttu-id="f7001-177">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="f7001-177">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f7001-178">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f7001-178">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> <span data-ttu-id="f7001-179">**有應用程式-V 問題**嗎？</span><span class="sxs-lookup"><span data-stu-id="f7001-179">**Got an App-V issue**?</span></span> <span data-ttu-id="f7001-180">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="f7001-180">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

 

 





