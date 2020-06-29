---
title: 使用 App-V 部署 Microsoft Office 2013
description: 使用 App-V 部署 Microsoft Office 2013
author: dansimp
ms.assetid: 9a7be05e-2a7a-4874-af25-09c0f5037876
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: f6a54cadce79ff3680fd69206eba8ac3fbe83a68
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800641"
---
# <span data-ttu-id="9a552-103">使用 App-V 部署 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-103">Deploying Microsoft Office 2013 by Using App-V</span></span>


<span data-ttu-id="9a552-104">您可以使用本文中的資訊來使用 Microsoft Application Virtualization （App-v）5.1 或更新版本，將 Microsoft Office 2013 做為您組織中的電腦提供虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-104">Use the information in this article to use Microsoft Application Virtualization (App-V) 5.1, or later versions, to deliver Microsoft Office 2013 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="9a552-105">如需使用 App-v 來傳送 Office 2010 的詳細資訊，請參閱[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v51.md)。</span><span class="sxs-lookup"><span data-stu-id="9a552-105">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v51.md).</span></span> <span data-ttu-id="9a552-106">若要在應用程式中成功部署 Office 2013，您必須熟悉 Office 2013 和 App-v。</span><span class="sxs-lookup"><span data-stu-id="9a552-106">To successfully deploy Office 2013 with App-V, you need to be familiar with Office 2013 and App-V.</span></span>

<span data-ttu-id="9a552-107">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="9a552-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="9a552-108">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="9a552-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="9a552-109">使用 Office 部署工具為 App-v 建立 Office 2013 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-109">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="9a552-110">發佈應用程式的 Office 套件-V 5。1</span><span class="sxs-lookup"><span data-stu-id="9a552-110">Publishing the Office package for App-V 5.1</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="9a552-111">自訂及管理 Office App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="9a552-112">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="9a552-112">What to know before you start</span></span>


<span data-ttu-id="9a552-113">在使用 App-v 部署 Office 2013 之前，請先查看下列規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="9a552-113">Before you deploy Office 2013 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="9a552-114">支援的 Office 版本與 Office 共存</span><span class="sxs-lookup"><span data-stu-id="9a552-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="9a552-115">您可以使用下表來取得支援的 Office 版本相關資訊，以及如何執行共存的 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="9a552-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-116">要查看的資訊</span><span class="sxs-lookup"><span data-stu-id="9a552-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="9a552-117">描述</span><span class="sxs-lookup"><span data-stu-id="9a552-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="9a552-118">為搭配 Office 使用 App-V 進行規劃</span><span class="sxs-lookup"><span data-stu-id="9a552-118">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-119">支援的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="9a552-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="9a552-120">支援的部署類型（例如，桌面、個人虛擬桌面基礎結構（VDI）、彙集的 VDI）</span><span class="sxs-lookup"><span data-stu-id="9a552-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="9a552-121">Office 授權選項</span><span class="sxs-lookup"><span data-stu-id="9a552-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting)"><span data-ttu-id="9a552-122">為搭配 Office 使用 App-V 進行規劃</span><span class="sxs-lookup"><span data-stu-id="9a552-122">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="9a552-123">在同一部電腦上安裝不同版本的 Office 時的考慮</span><span class="sxs-lookup"><span data-stu-id="9a552-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>


### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="9a552-124">封裝、發佈和部署需求</span><span class="sxs-lookup"><span data-stu-id="9a552-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="9a552-125">在使用 App-v 部署 Office 之前，請先檢查下列需求。</span><span class="sxs-lookup"><span data-stu-id="9a552-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-126">工作</span><span class="sxs-lookup"><span data-stu-id="9a552-126">Task</span></span></th>
<th align="left"><span data-ttu-id="9a552-127">需求</span><span class="sxs-lookup"><span data-stu-id="9a552-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-128">封裝</span><span class="sxs-lookup"><span data-stu-id="9a552-128">Packaging</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-129">您要部署至使用者的所有 Office 應用程式必須位於單一套件中。</span><span class="sxs-lookup"><span data-stu-id="9a552-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="9a552-130">在 App-v 5.1 及更新版本中，您必須使用 Office 部署工具來建立套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-130">In App-V 5.1 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="9a552-131">您無法使用排序器。</span><span class="sxs-lookup"><span data-stu-id="9a552-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="9a552-132">如果您要部署 Microsoft Visio 2013，以及 Office 的 Microsoft Project 2013，您必須將它們包含在 Office 的同一個套件中。</span><span class="sxs-lookup"><span data-stu-id="9a552-132">If you are deploying Microsoft Visio 2013 and Microsoft Project 2013 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="9a552-133">如需詳細資訊，請參閱 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)"> 使用 Office 部署 Visio 2013 和 Project 2013 </a> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2013 and Project 2013 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-134">發行</span><span class="sxs-lookup"><span data-stu-id="9a552-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-135">您只能將一個 Office 套件發佈至每個用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="9a552-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="9a552-136">您必須全域發佈 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-136">You must publish the Office package globally.</span></span> <span data-ttu-id="9a552-137">您無法發佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="9a552-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-138">使用遠端桌面服務將下列任何產品部署到共用電腦，例如：</span><span class="sxs-lookup"><span data-stu-id="9a552-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="9a552-139">適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="9a552-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="9a552-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="9a552-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="9a552-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="9a552-142">您必須啟用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共用電腦啟用 </a> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
<p><span data-ttu-id="9a552-143">如果您要部署大量授權產品，請不要使用共用電腦啟用，例如：</span><span class="sxs-lookup"><span data-stu-id="9a552-143">You don’t use shared computer activation if you’re deploying a volume licensed product, such as:</span></span></p>
<ul>
<li><p><span data-ttu-id="9a552-144">Office 專業增強版2013</span><span class="sxs-lookup"><span data-stu-id="9a552-144">Office Professional Plus 2013</span></span></p></li>
<li><p><span data-ttu-id="9a552-145">Visio 專業版2013</span><span class="sxs-lookup"><span data-stu-id="9a552-145">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="9a552-146">Project 專業版2013</span><span class="sxs-lookup"><span data-stu-id="9a552-146">Project Professional 2013</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="9a552-147">從套件中排除 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-147">Excluding Office applications from a package</span></span>

<span data-ttu-id="9a552-148">下表說明從套件中排除特定 Office 應用程式的建議方法。</span><span class="sxs-lookup"><span data-stu-id="9a552-148">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-149">工作</span><span class="sxs-lookup"><span data-stu-id="9a552-149">Task</span></span></th>
<th align="left"><span data-ttu-id="9a552-150">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9a552-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-151">使用 <strong> </strong> Office 部署工具建立套件時，請使用 ExcludeApp 設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-151">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-152">可讓您在 Office 部署工具建立套件時，從套件中排除特定的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-152">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="9a552-153">例如，您可以使用這個設定來建立只包含 Microsoft Word 的套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-153">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="9a552-154">如需詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-154">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-155">修改 DeploymentConfig.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="9a552-155">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-156">建立套件之後，請修改 DeploymentConfig.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="9a552-156">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="9a552-157">此檔案包含執行 App-v 用戶端之電腦上所有使用者的預設套件設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-157">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="9a552-158">如需詳細資訊，請參閱 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)"> 停用 Office 2013 應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-158">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)">Disabling Office 2013 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="9a552-159">使用 Office 部署工具為 App-v 建立 Office 2013 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-159">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="9a552-160">完成下列步驟，以針對 App-v 5.1 或更新版本建立 Office 2013 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-160">Complete the following steps to create an Office 2013 package for App-V 5.1 or later.</span></span>

**<span data-ttu-id="9a552-161">重要</span><span class="sxs-lookup"><span data-stu-id="9a552-161">Important</span></span>**  
<span data-ttu-id="9a552-162">在 App-v 5.1 及更新版本中，您必須使用 Office 部署工具來建立套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-162">In App-V 5.1 and later, you must the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="9a552-163">您無法使用 Sequencer 來建立套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-163">You cannot use the Sequencer to create packages.</span></span>



### <span data-ttu-id="9a552-164">查看使用 Office 部署工具的先決條件</span><span class="sxs-lookup"><span data-stu-id="9a552-164">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="9a552-165">您要安裝 Office 部署工具的電腦必須具備：</span><span class="sxs-lookup"><span data-stu-id="9a552-165">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-166">必備</span><span class="sxs-lookup"><span data-stu-id="9a552-166">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="9a552-167">描述</span><span class="sxs-lookup"><span data-stu-id="9a552-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-168">必備軟體</span><span class="sxs-lookup"><span data-stu-id="9a552-168">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-169">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="9a552-169">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-170">支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="9a552-170">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9a552-171">64位版本的 Windows 8 或更新版本</span><span class="sxs-lookup"><span data-stu-id="9a552-171">64-bit version of Windows 8 or later</span></span></p></li>
<li><p><span data-ttu-id="9a552-172">64位版本的 Windows 7</span><span class="sxs-lookup"><span data-stu-id="9a552-172">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="9a552-173">注意</span><span class="sxs-lookup"><span data-stu-id="9a552-173">Note</span></span>**  
<span data-ttu-id="9a552-174">在本主題中，「Office 2013 App-v 套件」一詞是指訂閱授權和大量授權。</span><span class="sxs-lookup"><span data-stu-id="9a552-174">In this topic, the term “Office 2013 App-V package” refers to subscription licensing and volume licensing.</span></span>



### <span data-ttu-id="9a552-175">使用 Office 部署工具建立 Office 2013 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-175">Create Office 2013 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="9a552-176">您可以使用 Office 部署工具來建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-176">You create Office 2013 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="9a552-177">下列指示將說明如何使用大量授權或訂閱授權來建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-177">The following instructions explain how to create an Office 2013 App-V package with Volume Licensing or Subscription Licensing.</span></span>

<span data-ttu-id="9a552-178">在64位 Windows 電腦上建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-178">Create Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="9a552-179">建立之後，Office 2013 App-v 套件將會在32位和64位的 Windows 7、Windows 8.1 和 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="9a552-179">Once created, the Office 2013 App-V package will run on 32-bit and 64-bit Windows 7, Windows 8.1, and Windows 10 computers.</span></span>

### <span data-ttu-id="9a552-180">下載 Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="9a552-180">Download the Office Deployment Tool</span></span>

<span data-ttu-id="9a552-181">系統會使用 Office 部署工具建立 office 2013 App-v 套件，該工具會產生 Office 2013 App-v 封裝。</span><span class="sxs-lookup"><span data-stu-id="9a552-181">Office 2013 App-V Packages are created using the Office Deployment Tool, which generates an Office 2013 App-V Package.</span></span> <span data-ttu-id="9a552-182">無法透過 App-v 排序器建立或修改套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-182">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="9a552-183">開始建立套件：</span><span class="sxs-lookup"><span data-stu-id="9a552-183">To begin package creation:</span></span>

1.  <span data-ttu-id="9a552-184">下載「隨選即用」的[Office 部署工具](https://www.microsoft.com/download/details.aspx?id=36778)。</span><span class="sxs-lookup"><span data-stu-id="9a552-184">Download the [Office Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=36778).</span></span>

2.  <span data-ttu-id="9a552-185">執行 .exe 檔案，並將其功能解壓至想要的位置。</span><span class="sxs-lookup"><span data-stu-id="9a552-185">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="9a552-186">若要簡化這個程式，您可以建立共用網路資料夾，以儲存功能。</span><span class="sxs-lookup"><span data-stu-id="9a552-186">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    <span data-ttu-id="9a552-187">範例： \\\\Server\\Office2013</span><span class="sxs-lookup"><span data-stu-id="9a552-187">Example: \\\\Server\\Office2013</span></span>

3.  <span data-ttu-id="9a552-188">檢查 setup.exe 和 configuration.xml 檔案是否存在，且位於您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="9a552-188">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="9a552-189">下載 Office 2013 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-189">Download Office 2013 applications</span></span>

<span data-ttu-id="9a552-190">下載 Office 部署工具之後，您就可以使用它來取得最新的 Office 2013 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-190">After you download the Office Deployment Tool, you can use it to get the latest Office 2013 applications.</span></span> <span data-ttu-id="9a552-191">在取得 Office 應用程式之後，您會建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-191">After getting the Office applications, you create the Office 2013 App-V package.</span></span>

<span data-ttu-id="9a552-192">Office 部署工具中包含的 XML 檔案會指定產品詳細資料，例如隨附的語言和 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-192">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1.  <span data-ttu-id="9a552-193">**自訂範例 XML 設定檔：** 使用您使用 Office 部署工具下載的範例 XML 設定檔，來自訂 Office 應用程式：</span><span class="sxs-lookup"><span data-stu-id="9a552-193">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

    1.  <span data-ttu-id="9a552-194">在記事本或您最愛的文字編輯器中開啟範例 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="9a552-194">Open the sample XML file in Notepad or your favorite text editor.</span></span>

    2.  <span data-ttu-id="9a552-195">在範例 configuration.xml 檔案開啟並準備好進行編輯時，您可以指定產品、語言及儲存 Office 2013 應用程式的路徑。</span><span class="sxs-lookup"><span data-stu-id="9a552-195">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2013 applications.</span></span> <span data-ttu-id="9a552-196">下列是 configuration.xml 檔案的基本範例：</span><span class="sxs-lookup"><span data-stu-id="9a552-196">The following is a basic example of the configuration.xml file:</span></span>

        ```xml
        <Configuration>
           <Add SourcePath= ”\\Server\Office2013” OfficeClientEdition="32" >
            <Product ID="O365ProPlusRetail ">
              <Language ID="en-us" />
            </Product>
            <Product ID="VisioProRetail">
              <Language ID="en-us" />
            </Product>
          </Add>
        </Configuration>
        ```

        **<span data-ttu-id="9a552-197">注意</span><span class="sxs-lookup"><span data-stu-id="9a552-197">Note</span></span>**  
        <span data-ttu-id="9a552-198">[配置 XML] 是範例 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="9a552-198">The configuration XML is a sample XML file.</span></span> <span data-ttu-id="9a552-199">檔案包含已加上注釋的線條。您可以「取消注釋」這些線條，以自訂檔案的其他設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-199">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span>



~~~
    The above XML configuration file specifies that Office 2013 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2013, which is the location where Office applications will be saved to. Note that the Product ID of the applications will not affect the final licensing of Office. Office 2013 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage. The table below summarizes the customizable attributes and elements of XML file:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Input</th>
    <th align="left">Description</th>
    <th align="left">Example</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Add element</p></td>
    <td align="left"><p>Specifies the products and languages to include in the package.</p></td>
    <td align="left"><p>N/A</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>OfficeClientEdition (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the edition of Office 2013 product to use: 32-bit or 64-bit. The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</p></td>
    <td align="left"><p><strong>OfficeClientEdition</strong>=&quot;32&quot;</p>
    <p><strong>OfficeClientEdition</strong>=&quot;64&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Product element</p></td>
    <td align="left"><p>Specifies the application. Project 2013 and Visio 2013 must be specified here as an added product to be included in the applications.</p></td>
    <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
    <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProPlusVolume&quot;</code></p>
    <p><code>Product ID =&quot;VisioProVolume&quot;</code></p>
    <p><code>Product ID = &quot;ProjectProVolume&quot;</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Language element</p></td>
    <td align="left"><p>Specifies the language supported in the applications</p></td>
    <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Version (attribute of Add element)</p></td>
    <td align="left"><p>Optional. Specifies a build to use for the package</p>
    <p>Defaults to latest advertised build (as defined in v32.CAB at the Office source).</p></td>
    <td align="left"><p><code>15.1.2.3</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>SourcePath (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the location in which the applications will be saved to.</p></td>
    <td align="left"><p><code>Sourcepath = &quot;\\Server\Office2013”</code></p></td>
    </tr>
    </tbody>
    </table>



    After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2013 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.
~~~

2. <span data-ttu-id="9a552-200">**將應用程式下載到指定位置：** 使用提升許可權的命令提示字元與64位作業系統，下載稍後將轉換成 App-v 套件的 Office 2013 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-200">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2013 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="9a552-201">以下是包含詳細說明的範例命令：</span><span class="sxs-lookup"><span data-stu-id="9a552-201">Below is an example command with description of details:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /download \\server\Office2013\Customconfig.xml
   ```

   <span data-ttu-id="9a552-202">在範例中：</span><span class="sxs-lookup"><span data-stu-id="9a552-202">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-203">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="9a552-203">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-204">是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="9a552-204">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-205">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="9a552-205">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-206">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="9a552-206">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-207">/download</span><span class="sxs-lookup"><span data-stu-id="9a552-207">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-208">下載您在 customConfig.xml 檔案中指定的 Office 2013 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-208">downloads the Office 2013 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="9a552-209">這些 bits 可以在 Office 2013 App-v 套件中以大量授權進行轉換。</span><span class="sxs-lookup"><span data-stu-id="9a552-209">These bits can be later converted in an Office 2013 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-210">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="9a552-210">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-211">傳遞完成下載程式所需的 XML 設定檔，在此範例中 customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="9a552-211">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="9a552-212">使用 [下載] 命令之後，請在配置 xml 檔案中指定的位置找到 Office 應用程式，此範例 \Server\Office2013。</span><span class="sxs-lookup"><span data-stu-id="9a552-212">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2013.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="9a552-213">將 Office 應用程式轉換成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-213">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="9a552-214">透過 Office 部署工具下載 Office 2013 應用程式之後，請使用 Office 部署工具，將它們轉換成 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-214">After you download the Office 2013 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2013 App-V package.</span></span> <span data-ttu-id="9a552-215">完成與您的授權模型相對應的步驟。</span><span class="sxs-lookup"><span data-stu-id="9a552-215">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="9a552-216">您需要執行的作業摘要：</span><span class="sxs-lookup"><span data-stu-id="9a552-216">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="9a552-217">在64位 Windows 電腦上建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-217">Create the Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="9a552-218">不過，套件將在32位和64位的 Windows 7、Windows 8 和 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="9a552-218">However, the package will run on 32-bit and 64-bit Windows 7, Windows 8, and Windows 10 computers.</span></span>

-   <span data-ttu-id="9a552-219">使用 Office 部署工具建立訂閱授權套件或大量授權的 Office App-v 套件，然後修改 CustomConfig.xml 設定檔。</span><span class="sxs-lookup"><span data-stu-id="9a552-219">Create an Office App-V package for either Subscription Licensing package or Volume Licensing by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="9a552-220">下表摘要列出您所使用的授權模型 CustomConfig.xml 檔案中所需輸入的值。</span><span class="sxs-lookup"><span data-stu-id="9a552-220">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="9a552-221">表格後續各節中的步驟將會指定您所需的確切專案。</span><span class="sxs-lookup"><span data-stu-id="9a552-221">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-222">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="9a552-222">Product ID</span></span></th>
<th align="left"><span data-ttu-id="9a552-223">大量授權</span><span class="sxs-lookup"><span data-stu-id="9a552-223">Volume Licensing</span></span></th>
<th align="left"><span data-ttu-id="9a552-224">訂閱授權</span><span class="sxs-lookup"><span data-stu-id="9a552-224">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9a552-225">Office 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-225">Office 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9a552-226">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-226">ProPlusVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-227">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-227">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9a552-228">Office 2013 與 Visio 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-228">Office 2013 with Visio 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9a552-229">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-229">ProPlusVolume</span></span></p>
<p><span data-ttu-id="9a552-230">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-230">VisioProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-231">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-231">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="9a552-232">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-232">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9a552-233">Office 2013 與 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-233">Office 2013 with Visio 2013 and Project 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9a552-234">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-234">ProPlusVolume</span></span></p>
<p><span data-ttu-id="9a552-235">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-235">VisioProVolume</span></span></p>
<p><span data-ttu-id="9a552-236">ProjectProVolume</span><span class="sxs-lookup"><span data-stu-id="9a552-236">ProjectProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-237">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-237">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="9a552-238">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-238">VisioProRetail</span></span></p>
<p><span data-ttu-id="9a552-239">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="9a552-239">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="9a552-240">如何將 Office 應用程式轉換成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-240">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="9a552-241">在 [記事本] 中，重新開啟 CustomConfig.xml 檔案，然後對檔案進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="9a552-241">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="9a552-242">參數</span><span class="sxs-lookup"><span data-stu-id="9a552-242">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="9a552-243">要變更值的專案</span><span class="sxs-lookup"><span data-stu-id="9a552-243">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9a552-244">SourcePath</span><span class="sxs-lookup"><span data-stu-id="9a552-244">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9a552-245">指向先前下載的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-245">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9a552-246">ProductID</span><span class="sxs-lookup"><span data-stu-id="9a552-246">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9a552-247">指定授權類型，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="9a552-247">Specify the type of licensing, as shown in the following examples:</span></span></p>
   <ul>
   <li><p><span data-ttu-id="9a552-248">訂閱授權</span><span class="sxs-lookup"><span data-stu-id="9a552-248">Subscription Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="9a552-249">在這個範例中，建立含訂閱授權的套件的下列變更：</span><span class="sxs-lookup"><span data-stu-id="9a552-249">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-250">SourcePath</span><span class="sxs-lookup"><span data-stu-id="9a552-250">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-251">路徑，該路徑已變更為指向先前下載的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-251">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-252">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="9a552-252">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-253">[Office 的變更為] <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-253">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-254">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="9a552-254">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-255">Visio 的 [變更為] <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-255">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   <li><p><span data-ttu-id="9a552-256">大量授權</span><span class="sxs-lookup"><span data-stu-id="9a552-256">Volume Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\Server\Office2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;ProPlusVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt;</code></pre>
   <p><span data-ttu-id="9a552-257">在這個範例中，建立含大量授權的套件的下列變更：</span><span class="sxs-lookup"><span data-stu-id="9a552-257">In this example, the following changes were made to create a package with Volume licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-258">SourcePath</span><span class="sxs-lookup"><span data-stu-id="9a552-258">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-259">路徑，該路徑已變更為指向先前下載的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-259">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-260">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="9a552-260">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-261">[Office 的變更為] <code>ProPlusVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-261">for Office was changed to <code>ProPlusVolume</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-262">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="9a552-262">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-263">Visio 的 [變更為] <code>VisioProVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="9a552-263">for Visio was changed to <code>VisioProVolume</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   </ul></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="9a552-264">ExcludeApp （選用）</span><span class="sxs-lookup"><span data-stu-id="9a552-264">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9a552-265">可讓您指定您不想要包含在 Office 部署工具所建立的 App-v 套件中的 Office 程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-265">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="9a552-266">例如，您可以排除 Access 和 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="9a552-266">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="9a552-267">PACKAGEGUID （選用）</span><span class="sxs-lookup"><span data-stu-id="9a552-267">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="9a552-268">根據預設，Office 部署工具所建立的所有 app-v 套件都共用相同的 App-v 套件識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a552-268">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="9a552-269">您可以使用 PACKAGEGUID 為每個套件指定不同的套件識別碼，這可讓您發佈由 Office 部署工具所建立的多個 App-v 套件，並使用 App-v 伺服器來管理它們。</span><span class="sxs-lookup"><span data-stu-id="9a552-269">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="9a552-270">若要在不同的使用者建立不同的套件時，使用這個參數的範例。</span><span class="sxs-lookup"><span data-stu-id="9a552-270">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="9a552-271">例如，您可以建立一個包含適用于部分使用者之 Office 2013 的套件，並使用 Office 2013 和 Visio 2013 為其他使用者組建立另一個套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-271">For example, you can create a package with just Office 2013 for some users, and create another package with Office 2013 and Visio 2013 for another set of users.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="9a552-272">注意</span><span class="sxs-lookup"><span data-stu-id="9a552-272">Note</span></span></strong><br/><p><span data-ttu-id="9a552-273">即使您使用的是唯一的套件識別碼，您仍然可以只將一個 App-v 套件部署到單一裝置。</span><span class="sxs-lookup"><span data-stu-id="9a552-273">Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="9a552-274">使用/packager 命令，將 Office 應用程式轉換為 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-274">Use the /packager command to convert the Office applications to an Office 2013 App-V package.</span></span>

   <span data-ttu-id="9a552-275">例如：</span><span class="sxs-lookup"><span data-stu-id="9a552-275">For example:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /packager \\server\Office2013\Customconfig.xml  \\server\share\Office2013AppV
   ```

   <span data-ttu-id="9a552-276">在範例中：</span><span class="sxs-lookup"><span data-stu-id="9a552-276">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-277">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="9a552-277">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-278">是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="9a552-278">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-279">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="9a552-279">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-280">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="9a552-280">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-281">/packager</span><span class="sxs-lookup"><span data-stu-id="9a552-281">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-282">使用 customConfig.xml 檔案中指定的大量授權建立 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-282">creates the Office 2013 App-V package with Volume Licensing as specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="9a552-283">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="9a552-283">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-284">傳送已針對封裝階段準備的設定 XML 檔案（在此案例中為 customConfig）。</span><span class="sxs-lookup"><span data-stu-id="9a552-284">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="9a552-285">\server\share\Office 2013AppV</span><span class="sxs-lookup"><span data-stu-id="9a552-285">\server\share\Office 2013AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="9a552-286">指定新建立的 Office App-v 封裝的位置。</span><span class="sxs-lookup"><span data-stu-id="9a552-286">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2013 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note**  
To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="9a552-287">確認 Office 2013 App-v 套件正常運作：</span><span class="sxs-lookup"><span data-stu-id="9a552-287">Verify that the Office 2013 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="9a552-288">將您全域建立的 Office 2013 App-v 套件發佈至測試電腦，並確認 [Office 2013] 快捷方式隨即出現。</span><span class="sxs-lookup"><span data-stu-id="9a552-288">Publish the Office 2013 App-V package, which you created globally, to a test computer, and verify that the Office 2013 shortcuts appear.</span></span>

   2.  <span data-ttu-id="9a552-289">啟動幾個 Office 2013 應用程式（例如 Excel 或 Word），以確保您的套件如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="9a552-289">Start a few Office 2013 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="9a552-290">發佈應用程式的 Office 套件-V 5。1</span><span class="sxs-lookup"><span data-stu-id="9a552-290">Publishing the Office package for App-V 5.1</span></span>


<span data-ttu-id="9a552-291">使用下列資訊發佈 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-291">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="9a552-292">發佈 Office App-v 套件的方法</span><span class="sxs-lookup"><span data-stu-id="9a552-292">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="9a552-293">使用您用於任何其他套件的相同方法，部署適用于 Office 2013 的 app-v 套件：</span><span class="sxs-lookup"><span data-stu-id="9a552-293">Deploy the App-V package for Office 2013 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="9a552-294">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9a552-294">System Center Configuration Manager</span></span>

-   <span data-ttu-id="9a552-295">App-v Server</span><span class="sxs-lookup"><span data-stu-id="9a552-295">App-V Server</span></span>

-   <span data-ttu-id="9a552-296">從 PowerShell 命令中獨立</span><span class="sxs-lookup"><span data-stu-id="9a552-296">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="9a552-297">發佈先決條件與需求</span><span class="sxs-lookup"><span data-stu-id="9a552-297">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-298">先決條件或需求</span><span class="sxs-lookup"><span data-stu-id="9a552-298">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="9a552-299">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9a552-299">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-300">在 App-V 用戶端上啟用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="9a552-300">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-301">若要發佈 Office 2013 套件，您必須執行腳本。</span><span class="sxs-lookup"><span data-stu-id="9a552-301">To publish Office 2013 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="9a552-302">預設會停用 App-v 用戶端上的套件腳本。</span><span class="sxs-lookup"><span data-stu-id="9a552-302">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="9a552-303">若要啟用腳本，請執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="9a552-303">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-304">全域發佈 Office 2013 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-304">Publish the Office 2013 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-305">Office App-v 套件中的延伸點需要在電腦層級進行安裝。</span><span class="sxs-lookup"><span data-stu-id="9a552-305">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="9a552-306">當您在電腦層級發佈時，不需要任何必備動作或可轉散發元件，而且 Office 2013 套件全域可讓其應用程式像是原本安裝的 Office，而不需要系統管理員自訂套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-306">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2013 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="9a552-307">如何發佈 Office 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-307">How to publish an Office package</span></span>

<span data-ttu-id="9a552-308">執行下列命令以全域發佈 Office 套件：</span><span class="sxs-lookup"><span data-stu-id="9a552-308">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="9a552-309">從 App-v Server 上的 Web 管理主控台，您可以將許可權新增至電腦群組，而不是使用者群組，以便將套件全域發佈至對應群組中的電腦。</span><span class="sxs-lookup"><span data-stu-id="9a552-309">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="9a552-310">自訂及管理 Office App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-310">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="9a552-311">若要管理您的 Office App-v 套件，請使用與任何其他套件相同的作業，但有幾個例外狀況，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="9a552-311">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="9a552-312">使用連線群組啟用 Office 外掛程式</span><span class="sxs-lookup"><span data-stu-id="9a552-312">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="9a552-313">停用 Office 2013 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-313">Disabling Office 2013 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="9a552-314">停用 Office 2013 快速鍵</span><span class="sxs-lookup"><span data-stu-id="9a552-314">Disabling Office 2013 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="9a552-315">管理 Office 2013 套件升級</span><span class="sxs-lookup"><span data-stu-id="9a552-315">Managing Office 2013 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="9a552-316">管理 Office 2013 授權升級</span><span class="sxs-lookup"><span data-stu-id="9a552-316">Managing Office 2013 licensing upgrades</span></span>](#bkmk-manage-office-lic-upgrd)

-   [<span data-ttu-id="9a552-317">使用 Office 部署 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-317">Deploying Visio 2013 and Project 2013 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="9a552-318">使用連線群組啟用 Office 外掛程式</span><span class="sxs-lookup"><span data-stu-id="9a552-318">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="9a552-319">使用本節中的步驟，啟用 office 外掛程式與您的 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-319">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="9a552-320">若要使用 Office 外掛程式，您必須使用 App-v 排序器來建立只包含外掛程式的個別套件。您無法使用 Office 部署工具來建立外掛程式封裝。</span><span class="sxs-lookup"><span data-stu-id="9a552-320">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="9a552-321">接著，您可以建立包含 Office 套件和外掛程式套件的連線群組，如以下步驟所述。</span><span class="sxs-lookup"><span data-stu-id="9a552-321">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="9a552-322">若要啟用 Office App-v 的外掛程式套件</span><span class="sxs-lookup"><span data-stu-id="9a552-322">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="9a552-323">透過 App-V Server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。</span><span class="sxs-lookup"><span data-stu-id="9a552-323">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="9a552-324">使用 App-v 5.1 排序器來排序您的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-324">Sequence your plug-ins using the App-V 5.1 Sequencer.</span></span> <span data-ttu-id="9a552-325">確定使用的電腦上已安裝 Office 2013 來為外掛程式進行排序。</span><span class="sxs-lookup"><span data-stu-id="9a552-325">Ensure that Office 2013 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="9a552-326">我們建議您在順序電腦上使用 Microsoft 365 App for enterprise （非虛擬），當您依序排列 Office 2013 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-326">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2013 plug-ins.</span></span>

3.  <span data-ttu-id="9a552-327">建立包含所需外掛程式的 app-v 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-327">Create an App-V 5.1 package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="9a552-328">透過 App-V server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。</span><span class="sxs-lookup"><span data-stu-id="9a552-328">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="9a552-329">新增 Office 2013 App-v 套件，以及您已排序到您所建立之連線群組的外掛程式套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-329">Add the Office 2013 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    **<span data-ttu-id="9a552-330">重要</span><span class="sxs-lookup"><span data-stu-id="9a552-330">Important</span></span>**  
    <span data-ttu-id="9a552-331">[連線] 群組中的套件順序決定了套件內容的合併順序。</span><span class="sxs-lookup"><span data-stu-id="9a552-331">The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="9a552-332">在您的連線群組描述項檔案中，先新增 Office 2013 App-v 套件，然後再新增外掛程式 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-332">In your Connection group descriptor file, add the Office 2013 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="9a552-333">請確定這兩個套件都發佈到目的電腦，且該外掛程式套件是以全域方式發佈，以符合已發佈的 Office 2013 App-v 套件的全域設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-333">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2013 App-V package.</span></span>

7.  <span data-ttu-id="9a552-334">確認外掛程式套件的部署設定檔與 Office 2013 App-v 套件具有相同的設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-334">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2013 App-V package has.</span></span>

    <span data-ttu-id="9a552-335">因為 Office 2013 App-v 套件與作業系統整合，所以外掛程式套件設定應該會相符。</span><span class="sxs-lookup"><span data-stu-id="9a552-335">Since the Office 2013 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="9a552-336">您可以在部署設定檔中搜尋「COM Mode」，並確保您的外掛程式套件將此值設定為「整合」，且 "InProcessEnabled" 和 "OutOfProcessEnabled" 與您發佈的 Office 2013 App-v 套件的設定相符。</span><span class="sxs-lookup"><span data-stu-id="9a552-336">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2013 App-V package you published.</span></span>

8.  <span data-ttu-id="9a552-337">開啟部署設定檔，並將**物件**的值設為**false**。</span><span class="sxs-lookup"><span data-stu-id="9a552-337">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="9a552-338">如果您在排序之後對部署設定檔進行任何變更，請確定該外掛程式套件是與檔案一起發佈。</span><span class="sxs-lookup"><span data-stu-id="9a552-338">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="9a552-339">確定您所建立的連線群組已啟用至所需的電腦上。</span><span class="sxs-lookup"><span data-stu-id="9a552-339">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="9a552-340">如果啟用連線群組時，所建立的連線群組可能會「待定」，如果是使用 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-340">The Connection Group created will likely “pend” if the Office 2013 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="9a552-341">如果發生這種情況，您必須重新開機，才能成功啟用連線群組。</span><span class="sxs-lookup"><span data-stu-id="9a552-341">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="9a552-342">當您成功發佈這兩個套件並啟用連線群組之後，請啟動目標 Office 2013 應用程式，並確認您發佈並新增至連線群組的外掛程式會如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="9a552-342">After you successfully publish both packages and enable the Connection Group, start the target Office 2013 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="9a552-343">停用 Office 2013 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-343">Disabling Office 2013 applications</span></span>

<span data-ttu-id="9a552-344">您可能會想要停用 Office App-v 封裝中的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-344">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="9a552-345">例如，您可以停用 Access，但讓所有其他 Office 應用程式成為主要的可用。</span><span class="sxs-lookup"><span data-stu-id="9a552-345">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="9a552-346">當您停用應用程式時，最終使用者將不再看到該應用程式的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="9a552-346">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="9a552-347">您不需要重新排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-347">You do not have to re-sequence the application.</span></span> <span data-ttu-id="9a552-348">當您在 Office 2013 App-v 套件發佈之後變更部署設定檔之後，您將會儲存變更、新增 Office 2013 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2013 App-v 封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-348">When you change the Deployment Configuration File after the Office 2013 App-V package has been published, you will save the changes, add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

**<span data-ttu-id="9a552-349">注意</span><span class="sxs-lookup"><span data-stu-id="9a552-349">Note</span></span>**  
<span data-ttu-id="9a552-350">若要排除特定的 Office 應用程式（例如，Access 和 InfoPath），當您使用 Office 部署工具建立 App-v 套件時，請使用**ExcludeApp**設定。</span><span class="sxs-lookup"><span data-stu-id="9a552-350">To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span> <span data-ttu-id="9a552-351">如需詳細資訊，請參閱隨選[即用 configuration.xml 檔案的參考](https://technet.microsoft.com/library/jj219426.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9a552-351">For more information, see [Reference for Click-to-Run configuration.xml file](https://technet.microsoft.com/library/jj219426.aspx).</span></span>



**<span data-ttu-id="9a552-352">停用 Office 2013 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a552-352">To disable an Office 2013 application</span></span>**

1.  <span data-ttu-id="9a552-353">使用文字編輯器（如**記事本**）開啟部署設定檔，然後搜尋「應用程式」。</span><span class="sxs-lookup"><span data-stu-id="9a552-353">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="9a552-354">搜尋您想要停用的 Office 應用程式，例如 Access 2013。</span><span class="sxs-lookup"><span data-stu-id="9a552-354">Search for the Office application you want to disable, for example, Access 2013.</span></span>

3.  <span data-ttu-id="9a552-355">將 [Enabled] 的值從 "true" 變更為 "false"。</span><span class="sxs-lookup"><span data-stu-id="9a552-355">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="9a552-356">儲存部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="9a552-356">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="9a552-357">使用新的部署設定檔新增 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-357">Add the Office 2013 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot)]\officefl5\INFOPATH.EXE" Enabled="true">
      <VisualElements>
        <Name>InfoPath Filler 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[{AppVPackageRoot}]\office15\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office15\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="9a552-358">重新新增 Office 2013 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2013 App-v 封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a552-358">Re-add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="9a552-359">停用 Office 2013 快速鍵</span><span class="sxs-lookup"><span data-stu-id="9a552-359">Disabling Office 2013 shortcuts</span></span>

<span data-ttu-id="9a552-360">您可能會想要針對特定的 Office 應用程式停用快速鍵，而不是取消發佈或移除套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-360">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="9a552-361">下列範例顯示如何停用 Microsoft Access 的快速鍵。</span><span class="sxs-lookup"><span data-stu-id="9a552-361">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="9a552-362">若要停用 Office 2013 應用程式的快速鍵</span><span class="sxs-lookup"><span data-stu-id="9a552-362">To disable shortcuts for Office 2013 applications</span></span>**

1.  <span data-ttu-id="9a552-363">在記事本中開啟部署設定檔案，然後搜尋 [快速鍵]。</span><span class="sxs-lookup"><span data-stu-id="9a552-363">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="9a552-364">若要停用某些快速鍵，請刪除或批註您不想要的特定快速鍵。</span><span class="sxs-lookup"><span data-stu-id="9a552-364">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="9a552-365">您必須讓子系統保持存在且已啟用。</span><span class="sxs-lookup"><span data-stu-id="9a552-365">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="9a552-366">例如，在下列範例中，刪除 Microsoft Access 快速鍵，同時保持子系統 &lt; 快捷方式/shortcut， &gt; &lt; &gt; 以停用 Microsoft Access 快速鍵。</span><span class="sxs-lookup"><span data-stu-id="9a552-366">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2013\Access 2013.lnk</File>
           <Target>[{AppvPackageRoot}])office15\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office15\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="9a552-367">儲存部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="9a552-367">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="9a552-368">使用新的部署設定檔重新發佈 Office 2013 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-368">Republish Office 2013 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="9a552-369">您可以透過修改 App-v 套件的部署設定來變更許多其他設定，例如，檔案類型關聯、虛擬檔案系統等。</span><span class="sxs-lookup"><span data-stu-id="9a552-369">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="9a552-370">如需如何使用部署設定檔來變更 app-v 套件設定的其他資訊，請參閱本文結尾的 [其他資源] 區段。</span><span class="sxs-lookup"><span data-stu-id="9a552-370">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="9a552-371">管理 Office 2013 套件升級</span><span class="sxs-lookup"><span data-stu-id="9a552-371">Managing Office 2013 package upgrades</span></span>

<span data-ttu-id="9a552-372">若要升級 Office 2013 套件，請使用 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="9a552-372">To upgrade an Office 2013 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="9a552-373">若要升級先前部署的 Office 2013 套件，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="9a552-373">To upgrade a previously deployed Office 2013 package, perform the following steps.</span></span>

**<span data-ttu-id="9a552-374">如何升級先前部署的 Office 2013 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-374">How to upgrade a previously deployed Office 2013 package</span></span>**

1.  <span data-ttu-id="9a552-375">使用最新的 Office 2013 應用程式軟體，透過 Office 部署工具建立新的 Office 2013 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-375">Create a new Office 2013 package through the Office Deployment Tool that uses the most recent Office 2013 application software.</span></span> <span data-ttu-id="9a552-376">最新的 Office 2013 bits 隨時都可以透過建立 Office 2013 App-v 套件的下載階段取得。</span><span class="sxs-lookup"><span data-stu-id="9a552-376">The most recent Office 2013 bits can always be obtained through the download stage of creating an Office 2013 App-V Package.</span></span> <span data-ttu-id="9a552-377">新建立的 Office 2013 套件將會有最新的更新及新的版本 ID。</span><span class="sxs-lookup"><span data-stu-id="9a552-377">The newly created Office 2013 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="9a552-378">使用 Office 部署工具所建立的所有套件都有相同的沿襲。</span><span class="sxs-lookup"><span data-stu-id="9a552-378">All packages created using the Office Deployment Tool have the same lineage.</span></span>

    **<span data-ttu-id="9a552-379">注意</span><span class="sxs-lookup"><span data-stu-id="9a552-379">Note</span></span>**  
    <span data-ttu-id="9a552-380">Office App-v 封裝有兩個版本識別碼：</span><span class="sxs-lookup"><span data-stu-id="9a552-380">Office App-V packages have two Version IDs:</span></span>

    -   <span data-ttu-id="9a552-381">在使用 Office 部署工具所建立的所有套件中，都是唯一的 Office 2013 App-v 套件版本 ID。</span><span class="sxs-lookup"><span data-stu-id="9a552-381">An Office 2013 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span>

    -   <span data-ttu-id="9a552-382">第二個 App-v 套件版本 ID： x.x.x.x （例如，在 AppX 資訊清單中，只要有新版 Office 本身，就只會變更）。</span><span class="sxs-lookup"><span data-stu-id="9a552-382">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="9a552-383">例如，如果有可升級的新 Office 2013 版本，且已透過 Office 部署工具建立套件以納入這些升級，則 X.x.x.x 版本 ID 將會變更，以反映 Office 版本本身已變更。</span><span class="sxs-lookup"><span data-stu-id="9a552-383">For example, if a new Office 2013 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="9a552-384">App-v server 會使用 X.x.x.x 版本 ID 來區分此套件，並辨識它包含先前已發佈套件的新升級，因此，將其發佈為現有 Office 2013 套件的升級。。</span><span class="sxs-lookup"><span data-stu-id="9a552-384">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2013 package.</span></span>



2.  <span data-ttu-id="9a552-385">將新建立的 Office 2013 App-v 套件，全域發佈到您想要套用新更新的電腦上。</span><span class="sxs-lookup"><span data-stu-id="9a552-385">Globally publish the newly created Office 2013 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="9a552-386">由於新的套件與舊版 Office 2013 App-v 套件有相同的沿襲，所以發佈含有更新的新套件只會將新的變更套用至舊的套件，因此會快速進行。</span><span class="sxs-lookup"><span data-stu-id="9a552-386">Since the new package has the same lineage of the older Office 2013 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3.  <span data-ttu-id="9a552-387">將會以任何全域發佈的 app-v 套件相同的方式來套用升級。</span><span class="sxs-lookup"><span data-stu-id="9a552-387">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="9a552-388">因為應用程式可能正在使用，所以升級可能會延遲，直到電腦重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="9a552-388">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>

### <a href="" id="bkmk-manage-office-lic-upgrd"></a><span data-ttu-id="9a552-389">管理 Office 2013 授權升級</span><span class="sxs-lookup"><span data-stu-id="9a552-389">Managing Office 2013 licensing upgrades</span></span>

<span data-ttu-id="9a552-390">如果新的 Office 2013 App-v 套件的授權與目前部署的 Office 2013 App-v 套件不同。</span><span class="sxs-lookup"><span data-stu-id="9a552-390">If a new Office 2013 App-V Package has a different license than the Office 2013 App-V Package currently deployed.</span></span> <span data-ttu-id="9a552-391">例如，部署的 Office 2013 套件是一種 Office 2013，而新的 Office 2013 套件是以大量授權為基礎的，必須遵循下列指示，以確保授權升級順利進行：</span><span class="sxs-lookup"><span data-stu-id="9a552-391">For instance, the Office 2013 package deployed is a subscription based Office 2013 and the new Office 2013 package is Volume Licensing based, the following instructions must be followed to ensure smooth licensing upgrade:</span></span>

**<span data-ttu-id="9a552-392">如何升級 Office 2013 授權</span><span class="sxs-lookup"><span data-stu-id="9a552-392">How to upgrade an Office 2013 License</span></span>**

1.  <span data-ttu-id="9a552-393">取消發佈已部署的 Office 2013 訂閱授權 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-393">Unpublish the already deployed Office 2013 Subscription Licensing App-V package.</span></span>

2.  <span data-ttu-id="9a552-394">移除未發佈的 Office 2013 訂閱授權 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-394">Remove the unpublished Office 2013 Subscription Licensing App-V package.</span></span>

3.  <span data-ttu-id="9a552-395">重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="9a552-395">Restart the computer.</span></span>

4.  <span data-ttu-id="9a552-396">新增新的 Office 2013 App-v 套件大量授權。</span><span class="sxs-lookup"><span data-stu-id="9a552-396">Add the new Office 2013 App-V Package Volume Licensing.</span></span>

5.  <span data-ttu-id="9a552-397">發佈已新增的 Office 2013 App-v 套件（含大量授權）。</span><span class="sxs-lookup"><span data-stu-id="9a552-397">Publish the added Office 2013 App-V Package with Volume Licensing.</span></span>

<span data-ttu-id="9a552-398">您所選授權的 Office 2013 App-v 套件將會成功部署。</span><span class="sxs-lookup"><span data-stu-id="9a552-398">An Office 2013 App-V Package with your chosen licensing will be successfully deployed.</span></span>

### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="9a552-399">使用 Office 部署 Visio 2013 和 Project 2013</span><span class="sxs-lookup"><span data-stu-id="9a552-399">Deploying Visio 2013 and Project 2013 with Office</span></span>

<span data-ttu-id="9a552-400">下表說明使用 Office 部署 Visio 2013 和 Project 2013 的需求和選項。</span><span class="sxs-lookup"><span data-stu-id="9a552-400">The following table describes the requirements and options for deploying Visio 2013 and Project 2013 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-401">工作</span><span class="sxs-lookup"><span data-stu-id="9a552-401">Task</span></span></th>
<th align="left"><span data-ttu-id="9a552-402">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9a552-402">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-403">我要如何使用 Office 封裝及發佈 Visio 2013 和 Project 2013？</span><span class="sxs-lookup"><span data-stu-id="9a552-403">How do I package and publish Visio 2013 and Project 2013 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-404">您必須在與 Office 相同的套件中包含 Visio 2013 和 Project 2013。</span><span class="sxs-lookup"><span data-stu-id="9a552-404">You must include Visio 2013 and Project 2013 in the same package with Office.</span></span></p>
<p><span data-ttu-id="9a552-405">如果您不是部署 Office，您可以建立內含 Visio 與/或專案的套件，只要遵循 <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)"> 使用 App-v 部署 Microsoft Office 2010， </a></span><span class="sxs-lookup"><span data-stu-id="9a552-405">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)">Deploying Microsoft Office 2010 by Using App-V</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-406">我要如何將 Visio 2013 和 Project 2013 部署至特定使用者？</span><span class="sxs-lookup"><span data-stu-id="9a552-406">How can I deploy Visio 2013 and Project 2013 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-407">使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="9a552-407">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a552-408">如果您想要 .。。</span><span class="sxs-lookup"><span data-stu-id="9a552-408">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="9a552-409">...然後使用此方法</span><span class="sxs-lookup"><span data-stu-id="9a552-409">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a552-410">建立兩個不同的套件，並將每個套件部署至不同的使用者群組</span><span class="sxs-lookup"><span data-stu-id="9a552-410">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-411">建立及部署下列套件：</span><span class="sxs-lookup"><span data-stu-id="9a552-411">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="9a552-412">僅包含 Office 部署至使用者只需要 Office 的電腦的套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-412">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="9a552-413">包含 Office、Visio 和 Project-部署至使用者需要所有三個應用程式的電腦的套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-413">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a552-414">如果您只想在整個組織中使用一個套件，或者如果您有共用電腦的使用者：</span><span class="sxs-lookup"><span data-stu-id="9a552-414">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a552-415">遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9a552-415">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="9a552-416">建立包含 Office、Visio 和 Project 的套件。</span><span class="sxs-lookup"><span data-stu-id="9a552-416">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="9a552-417">將套件部署到所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9a552-417">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="9a552-418">使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 來防止特定使用者使用 Visio 和 Project。</span><span class="sxs-lookup"><span data-stu-id="9a552-418">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="9a552-419">其他資源</span><span class="sxs-lookup"><span data-stu-id="9a552-419">Additional resources</span></span>


**<span data-ttu-id="9a552-420">Office 2013 App-V 封裝其他資源</span><span class="sxs-lookup"><span data-stu-id="9a552-420">Office 2013 App-V Packages Additional Resources</span></span>**

[<span data-ttu-id="9a552-421">「隨選即用」的 Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="9a552-421">Office Deployment Tool for Click-to-Run</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=330672)

[<span data-ttu-id="9a552-422">將 Microsoft Office 部署為已排序的 App-v 套件所支援的案例</span><span class="sxs-lookup"><span data-stu-id="9a552-422">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="9a552-423">Office 2010 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="9a552-423">Office 2010 App-V Packages</span></span>**

[<span data-ttu-id="9a552-424">Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序套件</span><span class="sxs-lookup"><span data-stu-id="9a552-424">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="9a552-425">建立或使用 App-v 5.0 Office 2010 套件時的已知問題</span><span class="sxs-lookup"><span data-stu-id="9a552-425">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="9a552-426">如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="9a552-426">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="9a552-427">連線群組</span><span class="sxs-lookup"><span data-stu-id="9a552-427">Connection Groups</span></span>**

[<span data-ttu-id="9a552-428">在 Microsoft App 中部署連線群組-V v5</span><span class="sxs-lookup"><span data-stu-id="9a552-428">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="9a552-429">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="9a552-429">Managing Connection Groups</span></span>](managing-connection-groups51.md)

**<span data-ttu-id="9a552-430">動態設定</span><span class="sxs-lookup"><span data-stu-id="9a552-430">Dynamic Configuration</span></span>**

[<span data-ttu-id="9a552-431">關於 App-V 5.1 動態組態</span><span class="sxs-lookup"><span data-stu-id="9a552-431">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)














