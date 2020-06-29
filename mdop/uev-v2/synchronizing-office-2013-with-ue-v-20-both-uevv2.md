---
title: 將 Office 2013 與 UE-V 2.0 同步處理
description: 將 Office 2013 與 UE-V 2.0 同步處理
author: dansimp
ms.assetid: c46feb6d-28a8-4799-888d-053531dc5842
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9b079d3f21e6ced689fa2101f5321fa9b1406c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812026"
---
# <span data-ttu-id="88645-103">將 Office 2013 與 UE-V 2.0 同步處理</span><span class="sxs-lookup"><span data-stu-id="88645-103">Synchronizing Office 2013 with UE-V 2.0</span></span>


<span data-ttu-id="88645-104">Microsoft 使用者體驗虛擬化（UE-V）2.0 支援使用 UE-V 範本庫中提供的範本來同步處理 Microsoft Office 2013 應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="88645-104">Microsoft User Experience Virtualization (UE-V) 2.0 supports the synchronization of Microsoft Office 2013 application setting using a template available from the UE-V template gallery.</span></span> <span data-ttu-id="88645-105">UE-V 2 和 App V 5.0 SP2 支援 Office 2013 專業增強版，在任何 UE-V 啟用的裝置或虛擬化的電腦上，都能在虛擬化的 Office 2013 實例上獲得相同的體驗。</span><span class="sxs-lookup"><span data-stu-id="88645-105">The combination of UE-V 2 and App-V 5.0 SP2 support of Office 2013 Professional Plus enables the same experience on virtualized instance of Office 2013 from any UE-V-enabled device or virtualized desktop.</span></span>

<span data-ttu-id="88645-106">若要啟用 Office 2013 的 UE-V 應用程式設定支援，您可以從[Microsoft 使用者體驗虛擬化（ue-v）2範本庫](https://go.microsoft.com/fwlink/p/?LinkId=246589)下載官方 ue-v Office 2013 範本。</span><span class="sxs-lookup"><span data-stu-id="88645-106">To activate UE-V application settings support of Office 2013, you can download official UE-V Office 2013 templates from the [Microsoft User Experience Virtualization (UE-V) 2 Template Gallery](https://go.microsoft.com/fwlink/p/?LinkId=246589).</span></span> <span data-ttu-id="88645-107">此資源提供 Microsoft 撰寫的 UE-V 設定位置範本，以及社區開發的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="88645-107">This resource provides Microsoft-authored UE-V settings location templates as well as community-developed settings location templates.</span></span>

## <span data-ttu-id="88645-108">UE-V 中的 Microsoft Office 支援</span><span class="sxs-lookup"><span data-stu-id="88645-108">Microsoft Office support in UE-V</span></span>


<span data-ttu-id="88645-109">UE-V 1.0 和 UE-V 2 包含 Microsoft Office 2010 的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="88645-109">UE-V 1.0 and UE-V 2 include settings location templates for Microsoft Office 2010.</span></span> <span data-ttu-id="88645-110">這些範本是作為 UE-V Agent 安裝程式的一部分進行發佈和註冊。</span><span class="sxs-lookup"><span data-stu-id="88645-110">These templates are distributed and registered as part of the UE-V Agent installation process.</span></span> <span data-ttu-id="88645-111">這些範本可協助在裝置之間同步處理使用者的 Office 體驗。</span><span class="sxs-lookup"><span data-stu-id="88645-111">These templates help synchronize users’ Office experience between devices.</span></span> <span data-ttu-id="88645-112">Office 2013 的 UE-V 範本提供對 Office 2010 範本的非常類似的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="88645-112">The UE-V templates for Office 2013 provide a very similar settings experience to the templates for Office 2010.</span></span> <span data-ttu-id="88645-113">在這些設定中不會包含 Office 365 體驗的 Microsoft Office 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="88645-113">Microsoft Office 2013 settings roamed by Office 365 experience are not included in these settings.</span></span> <span data-ttu-id="88645-114">如需 Office 365 特定設定的清單，請參閱[office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkId=391220)。</span><span class="sxs-lookup"><span data-stu-id="88645-114">For a list of Office 365-specific settings, see [Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkId=391220).</span></span>

## <span data-ttu-id="88645-115">已同步處理的 Office 2013 設定</span><span class="sxs-lookup"><span data-stu-id="88645-115">Synchronized Office 2013 Settings</span></span>


<span data-ttu-id="88645-116">下表包含 UE-V 中 Office 2013 支援的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="88645-116">The following tables contain the details for Office 2013 support in UE-V:</span></span>

### <span data-ttu-id="88645-117">Microsoft Office 支援的 UE-V 範本</span><span class="sxs-lookup"><span data-stu-id="88645-117">Supported UE-V templates for Microsoft Office</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="88645-118">在 UE-V 圖庫上提供的 Office 2013 範本（UE-V 2.0）：</span><span class="sxs-lookup"><span data-stu-id="88645-118">Office 2013 templates (UE-V 2.0, available on UE-V gallery):</span></span></th>
<th align="left"><span data-ttu-id="88645-119">Office 2010 範本（UE-V 1.0 &amp; 1.0 SP1）：</span><span class="sxs-lookup"><span data-stu-id="88645-119">Office 2010 templates (UE-V 1.0 &amp; 1.0 SP1):</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="88645-120">MicrosoftOffice2013Win32.xml</span><span class="sxs-lookup"><span data-stu-id="88645-120">MicrosoftOffice2013Win32.xml</span></span></p>
<p><span data-ttu-id="88645-121">MicrosoftOffice2013Win64.xml</span><span class="sxs-lookup"><span data-stu-id="88645-121">MicrosoftOffice2013Win64.xml</span></span></p>
<p><span data-ttu-id="88645-122">MicrosoftLync2013Win32.xml</span><span class="sxs-lookup"><span data-stu-id="88645-122">MicrosoftLync2013Win32.xml</span></span></p>
<p><span data-ttu-id="88645-123">MicrosoftLync2013Win64.xml</span><span class="sxs-lookup"><span data-stu-id="88645-123">MicrosoftLync2013Win64.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="88645-124">MicrosoftOffice2010Win32.xml</span><span class="sxs-lookup"><span data-stu-id="88645-124">MicrosoftOffice2010Win32.xml</span></span></p>
<p><span data-ttu-id="88645-125">MicrosoftOffice2010Win64.xml</span><span class="sxs-lookup"><span data-stu-id="88645-125">MicrosoftOffice2010Win64.xml</span></span></p>
<p><span data-ttu-id="88645-126">MicrosoftLync2010.xml</span><span class="sxs-lookup"><span data-stu-id="88645-126">MicrosoftLync2010.xml</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="88645-127">UE-V 範本支援的 Microsoft Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="88645-127">Microsoft Office Applications supported by the UE-V templates</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="88645-128">Microsoft Access 2013</span><span class="sxs-lookup"><span data-stu-id="88645-128">Microsoft Access 2013</span></span></p>
<p><span data-ttu-id="88645-129">Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="88645-129">Microsoft Lync 2013</span></span></p>
<p><span data-ttu-id="88645-130">Microsoft Excel 2013</span><span class="sxs-lookup"><span data-stu-id="88645-130">Microsoft Excel 2013</span></span></p>
<p><span data-ttu-id="88645-131">Microsoft InfoPath 2013</span><span class="sxs-lookup"><span data-stu-id="88645-131">Microsoft InfoPath 2013</span></span></p>
<p><span data-ttu-id="88645-132">Microsoft OneNote 2013</span><span class="sxs-lookup"><span data-stu-id="88645-132">Microsoft OneNote 2013</span></span></p>
<p><span data-ttu-id="88645-133">Microsoft Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="88645-133">Microsoft Outlook 2013</span></span></p>
<p><span data-ttu-id="88645-134">Microsoft PowerPoint 2013</span><span class="sxs-lookup"><span data-stu-id="88645-134">Microsoft PowerPoint 2013</span></span></p>
<p><span data-ttu-id="88645-135">Microsoft Project 2013</span><span class="sxs-lookup"><span data-stu-id="88645-135">Microsoft Project 2013</span></span></p>
<p><span data-ttu-id="88645-136">Microsoft Publisher 2013</span><span class="sxs-lookup"><span data-stu-id="88645-136">Microsoft Publisher 2013</span></span></p>
<p><span data-ttu-id="88645-137">Microsoft SharePoint Designer 2013</span><span class="sxs-lookup"><span data-stu-id="88645-137">Microsoft SharePoint Designer 2013</span></span></p>
<p><span data-ttu-id="88645-138">Microsoft Visio 2013</span><span class="sxs-lookup"><span data-stu-id="88645-138">Microsoft Visio 2013</span></span></p>
<p><span data-ttu-id="88645-139">Microsoft Word 2013</span><span class="sxs-lookup"><span data-stu-id="88645-139">Microsoft Word 2013</span></span></p>
<p><span data-ttu-id="88645-140">Microsoft Office 上傳管理員</span><span class="sxs-lookup"><span data-stu-id="88645-140">Microsoft Office Upload Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="88645-141">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="88645-141">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="88645-142">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="88645-142">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="88645-143">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="88645-143">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="88645-144">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="88645-144">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="88645-145">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="88645-145">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="88645-146">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="88645-146">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="88645-147">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="88645-147">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="88645-148">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="88645-148">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="88645-149">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="88645-149">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="88645-150">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="88645-150">Microsoft SharePoint Designer 2010</span></span></p>
<p><span data-ttu-id="88645-151">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="88645-151">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="88645-152">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="88645-152">Microsoft Word 2010</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="88645-153">部署 Office 2013 範本</span><span class="sxs-lookup"><span data-stu-id="88645-153">Deploying the Office 2013 templates</span></span>


<span data-ttu-id="88645-154">您可以使用下列方法來部署 UE-V 設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="88645-154">You can deploy UE-V settings location template with the following methods:</span></span>

-   <span data-ttu-id="88645-155">透過**PowerShell 註冊範本**。</span><span class="sxs-lookup"><span data-stu-id="88645-155">**Registering template via PowerShell**.</span></span> <span data-ttu-id="88645-156">如果您使用 Windows PowerShell 來管理電腦，請執行下列 Windows PowerShell 命令以系統管理員的身分開啟，以註冊此設定位置範本：</span><span class="sxs-lookup"><span data-stu-id="88645-156">If you use Windows PowerShell to manage computers, run the following Windows PowerShell command open as an administrator to register this settings location template:</span></span>

    ``` syntax
    Register-UevTemplate -Path <Path_to_Template>
    ```

    <span data-ttu-id="88645-157">如需使用 UE-V 和 Windows PowerShell 的詳細資訊，請參閱[使用 Windows PowerShell 和 WMI 管理 ue-v A.x 設定位置範本](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="88645-157">For more information using UE-V and Windows PowerShell, see [Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md).</span></span>

-   <span data-ttu-id="88645-158">透過**範本目錄路徑註冊範本**。</span><span class="sxs-lookup"><span data-stu-id="88645-158">**Registering template via Template Catalog Path**.</span></span> <span data-ttu-id="88645-159">如果您使用設定範本目錄路徑來管理使用者電腦上的範本，請將 Office 2013 範本複製到 UE-V Agent 中定義的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="88645-159">If you use the Settings Template Catalog Path to manage templates on users’ computers, copy the Office 2013 template into the folder defined in the UE-V Agent.</span></span> <span data-ttu-id="88645-160">下次範本自動更新（ApplySettingsCatalog.exe）排程的任務執行時，就會在裝置上註冊設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="88645-160">The next time the Template Auto Update (ApplySettingsCatalog.exe) scheduled task runs, the settings location template will be registered on the device.</span></span> <span data-ttu-id="88645-161">如需詳細資訊，請參閱[部署 ue-v 2 的設定範本目錄](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)。</span><span class="sxs-lookup"><span data-stu-id="88645-161">For more information, see [Deploying the Settings Template Catalog for UE-V 2](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue).</span></span>

-   <span data-ttu-id="88645-162">透過**Configuration Manager 註冊範本**。</span><span class="sxs-lookup"><span data-stu-id="88645-162">**Registering template via Configuration Manager**.</span></span> <span data-ttu-id="88645-163">如果您使用 Configuration Manager 來管理 UE-V 設定的儲存範本，請重新建立範本基線 CAB，然後將其匯入 Configuration Manager，然後將比較基準部署到您的用戶端。</span><span class="sxs-lookup"><span data-stu-id="88645-163">If you use Configuration Manager to manage your UE-V settings storage templates, then recreate the Template Baseline CAB, import it into Configuration Manager, and then deploy the baseline to your clients.</span></span> <span data-ttu-id="88645-164">如需詳細資訊，請參閱適用于[Microsoft 使用者經驗 Virtualization 2 之 System Center 2012 Configuration Pack](https://go.microsoft.com/fwlink/?LinkId=317263)的檔中所提供的指導方針。</span><span class="sxs-lookup"><span data-stu-id="88645-164">For more information, see the guidance provided in the documentation for the [System Center 2012 Configuration Pack for Microsoft User Experience Virtualization 2](https://go.microsoft.com/fwlink/?LinkId=317263).</span></span>






 

 





