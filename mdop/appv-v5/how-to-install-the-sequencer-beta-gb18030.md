---
title: 如何安裝 Sequencer
description: 如何安裝 Sequencer
author: dansimp
ms.assetid: a122caf0-f408-458c-b119-dc84123c1d58
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8542abfecd7f1d543228ab1a86a59b9ee918947
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800472"
---
# <span data-ttu-id="62901-103">如何安裝 Sequencer</span><span class="sxs-lookup"><span data-stu-id="62901-103">How to Install the Sequencer</span></span>


<span data-ttu-id="62901-104">使用下列程式來安裝 Microsoft Application Virtualization （App-v） 5.0 sequencer。</span><span class="sxs-lookup"><span data-stu-id="62901-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.0 sequencer.</span></span> <span data-ttu-id="62901-105">執行 sequencer 的電腦必須不執行 App-v 5.0 用戶端的任何版本。</span><span class="sxs-lookup"><span data-stu-id="62901-105">The computer that will run the sequencer must not be running any version of the App-V 5.0 client.</span></span>

<span data-ttu-id="62901-106">不支援升級 App-v 排序器的前一個安裝。</span><span class="sxs-lookup"><span data-stu-id="62901-106">Upgrading a previous installation of the App-V sequencer is not supported.</span></span>

<span data-ttu-id="62901-107">**重要** 如需 sequencer 需求的完整清單，請參閱[app-v 5.0 先決條件](app-v-50-prerequisites.md)和[app-v 5.0 支援](app-v-50-supported-configurations.md)的設定的排序器區段。</span><span class="sxs-lookup"><span data-stu-id="62901-107">**Important** For a full list of the sequencer requirements see sequencer sections of [App-V 5.0 Prerequisites](app-v-50-prerequisites.md) and [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

 

<span data-ttu-id="62901-108">您也可以使用命令列來安裝 App-v 5.0 排序器。</span><span class="sxs-lookup"><span data-stu-id="62901-108">You can also use the command line to install the App-V 5.0 sequencer.</span></span> <span data-ttu-id="62901-109">下列清單會顯示使用命令列和**appv\_sequencer\_setup.exe**安裝排序器選項的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="62901-109">The following list displays information about options for installing the sequencer using the command line and **appv\_sequencer\_setup.exe**:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="62901-110">命令</span><span class="sxs-lookup"><span data-stu-id="62901-110">Command</span></span></th>
<th align="left"><span data-ttu-id="62901-111">描述</span><span class="sxs-lookup"><span data-stu-id="62901-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62901-112">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="62901-112">/INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-113">指定安裝目錄。</span><span class="sxs-lookup"><span data-stu-id="62901-113">Specifies the installation directory.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62901-114">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="62901-114">/CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-115">可參與 Microsoft 客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="62901-115">Enables participation in the Microsoft Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62901-116">/Log</span><span class="sxs-lookup"><span data-stu-id="62901-116">/Log</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-117">指定安裝記錄的儲存位置，預設位置是 <strong> % Temp% </strong> 。</span><span class="sxs-lookup"><span data-stu-id="62901-117">Specifies where the installation log will be saved, the default location is <strong>%Temp%</strong>.</span></span> <span data-ttu-id="62901-118">例如， <strong> C：\登入 </strong> 記錄。</span><span class="sxs-lookup"><span data-stu-id="62901-118">For example, <strong>C:\ Logs \ log.log</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62901-119">/q</span><span class="sxs-lookup"><span data-stu-id="62901-119">/q</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-120">指定安靜或無提示的安裝。</span><span class="sxs-lookup"><span data-stu-id="62901-120">Specifies a quiet or silent installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62901-121">/Uninstall</span><span class="sxs-lookup"><span data-stu-id="62901-121">/Uninstall</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-122">指定移除排序器。</span><span class="sxs-lookup"><span data-stu-id="62901-122">Specifies the removal of the sequencer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62901-123">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="62901-123">/ACCEPTEULA</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-124">接受授權合約。</span><span class="sxs-lookup"><span data-stu-id="62901-124">Accepts the license agreement.</span></span> <span data-ttu-id="62901-125">這對於無操作安裝是必要的。</span><span class="sxs-lookup"><span data-stu-id="62901-125">This is required for an unattended installation.</span></span> <span data-ttu-id="62901-126">範例用法： <strong> /ACCEPTEULA </strong> 或 <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="62901-126">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62901-127">/LAYOUT</span><span class="sxs-lookup"><span data-stu-id="62901-127">/LAYOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-128">指定相關聯的版面配置動作。</span><span class="sxs-lookup"><span data-stu-id="62901-128">Specifies the associated layout action.</span></span> <span data-ttu-id="62901-129">它也會將 Windows Installer （.msi）及腳本檔案解壓縮至資料夾，但不安裝 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="62901-129">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.0.</span></span> <span data-ttu-id="62901-130">不需要任何值。</span><span class="sxs-lookup"><span data-stu-id="62901-130">No value is expected.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62901-131">/LAYOUTDIR</span><span class="sxs-lookup"><span data-stu-id="62901-131">/LAYOUTDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-132">指定版面配置目錄。</span><span class="sxs-lookup"><span data-stu-id="62901-132">Specifies the layout directory.</span></span> <span data-ttu-id="62901-133">需要字串值。</span><span class="sxs-lookup"><span data-stu-id="62901-133">Requires a string value.</span></span> <span data-ttu-id="62901-134">範例用法： <strong> /LAYOUTDIR = "C:\Application Virtualization 用戶端" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="62901-134">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62901-135">/?</span><span class="sxs-lookup"><span data-stu-id="62901-135">/?</span></span> <span data-ttu-id="62901-136">或/h 或/help</span><span class="sxs-lookup"><span data-stu-id="62901-136">Or /h or /help</span></span></p></td>
<td align="left"><p><span data-ttu-id="62901-137">顯示相關的說明。</span><span class="sxs-lookup"><span data-stu-id="62901-137">Displays associated help.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="62901-138">安裝 App-v 5.0 排序器</span><span class="sxs-lookup"><span data-stu-id="62901-138">To install the App-V 5.0 sequencer</span></span>**

1.  <span data-ttu-id="62901-139">將 App-v 5.0 sequencer 安裝檔案複製到安裝該檔案的電腦上。</span><span class="sxs-lookup"><span data-stu-id="62901-139">Copy the App-V 5.0 sequencer installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="62901-140">按兩下**appv\_sequencer\_setup.exe**然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="62901-140">Double-click **appv\_sequencer\_setup.exe** and then click **Install**.</span></span>

2.  <span data-ttu-id="62901-141">在 [**軟體授權條款**] 頁面上，您應該查看授權條款。</span><span class="sxs-lookup"><span data-stu-id="62901-141">On the **Software License Terms** page, you should review the license terms.</span></span> <span data-ttu-id="62901-142">若要接受授權條款，請選取 **[我接受授權條款]。**</span><span class="sxs-lookup"><span data-stu-id="62901-142">To accept the license terms select **I accept the license terms.**</span></span> <span data-ttu-id="62901-143">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="62901-143">Click **Next**.</span></span>

3.  <span data-ttu-id="62901-144">在 [**使用 Microsoft update]，協助保護您的電腦安全性且最新的**頁面，若要啟用 microsoft 更新，請選取 **[在我檢查更新時使用 microsoft Update （建議）]。**</span><span class="sxs-lookup"><span data-stu-id="62901-144">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="62901-145">若要從執行中停用 Microsoft 更新，請選取 [**我不想使用 Microsoft Update**]。</span><span class="sxs-lookup"><span data-stu-id="62901-145">To disable Microsoft updates from running select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="62901-146">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="62901-146">Click **Next**.</span></span>

4.  <span data-ttu-id="62901-147">在 [**客戶經驗改進計畫**] 頁面上，若要參與程式，請選取 [**加入客戶經驗改進計畫**]。</span><span class="sxs-lookup"><span data-stu-id="62901-147">On the **Customer Experience Improvement Program** page, to participate in the program select **Join the Customer Experience Improvement Program**.</span></span> <span data-ttu-id="62901-148">這可讓您收集有關如何使用 App-v 5.0 的資訊。</span><span class="sxs-lookup"><span data-stu-id="62901-148">This will allow information to be collected about how you are using App-V 5.0.</span></span> <span data-ttu-id="62901-149">如果您不想參與程式，請選取 [**我現在不想加入計畫**]。</span><span class="sxs-lookup"><span data-stu-id="62901-149">If you don’t want to participate in the program select **I don’t want to join the program at this time**.</span></span> <span data-ttu-id="62901-150">按一下 **\[安裝\]**。</span><span class="sxs-lookup"><span data-stu-id="62901-150">Click **Install**.</span></span>

5.  <span data-ttu-id="62901-151">若要開啟排序器，請按一下 [**開始**]，然後按一下 [ **Microsoft Application Virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="62901-151">To open the sequencer, click **Start** and then click **Microsoft Application Virtualization Sequencer**.</span></span>

**<span data-ttu-id="62901-152">若要排查 App-v 5.0 sequencer 的安裝問題</span><span class="sxs-lookup"><span data-stu-id="62901-152">To troubleshoot the App-V 5.0 sequencer installation</span></span>**

-   <span data-ttu-id="62901-153">如需有關 sequencer 安裝的詳細資訊，您可以在 **% temp%** 資料夾中查看錯誤記錄。</span><span class="sxs-lookup"><span data-stu-id="62901-153">For more information regarding the sequencer installation, you can view the error log in the **%temp%** folder.</span></span> <span data-ttu-id="62901-154">若要查看記錄檔，請按一下 [**開始**]，輸入 **% temp%**，然後尋找**appv\_ 記錄**。</span><span class="sxs-lookup"><span data-stu-id="62901-154">To review the log files, click **Start**, type **%temp%**, and then look for the **appv\_ log**.</span></span>

    <span data-ttu-id="62901-155">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="62901-155">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="62901-156">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="62901-156">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="62901-157">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="62901-157">Got an App-V issue?</span></span>** <span data-ttu-id="62901-158">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="62901-158">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="62901-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="62901-159">Related topics</span></span>


[<span data-ttu-id="62901-160">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="62901-160">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





