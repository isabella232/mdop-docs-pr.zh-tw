---
title: 使用 App-V 部署 Microsoft Office 2016
description: 使用 App-V 部署 Microsoft Office 2016
author: dansimp
ms.assetid: e0f4876-da99-4b89-977e-2fb6e89ea3d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: b47fd46c8dc368bbce819b24f18fa30328fbbaf0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800636"
---
# <span data-ttu-id="360b1-103">使用 App-V 部署 Microsoft Office 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-103">Deploying Microsoft Office 2016 by Using App-V</span></span>


<span data-ttu-id="360b1-104">您可以使用本文中的資訊來使用 Microsoft Application Virtualization （App-v）5.1 或更新版本，將 Microsoft Office 2016 做為您組織中的電腦提供虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-104">Use the information in this article to use Microsoft Application Virtualization (App-V) 5.1, or later versions, to deliver Microsoft Office 2016 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="360b1-105">如需使用 App-v 來傳送 Office 2013 的詳細資訊，請參閱[使用 App-v 部署 Microsoft Office 2013](deploying-microsoft-office-2013-by-using-app-v51.md)。</span><span class="sxs-lookup"><span data-stu-id="360b1-105">For information about using App-V to deliver Office 2013, see [Deploying Microsoft Office 2013 by Using App-V](deploying-microsoft-office-2013-by-using-app-v51.md).</span></span> <span data-ttu-id="360b1-106">如需使用 App-v 來傳送 Office 2010 的詳細資訊，請參閱[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v51.md)。</span><span class="sxs-lookup"><span data-stu-id="360b1-106">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v51.md).</span></span>

<span data-ttu-id="360b1-107">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="360b1-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="360b1-108">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="360b1-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="360b1-109">使用 Office 部署工具為 App-v 建立 Office 2016 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-109">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="360b1-110">發佈應用程式的 Office 套件-V 5。1</span><span class="sxs-lookup"><span data-stu-id="360b1-110">Publishing the Office package for App-V 5.1</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="360b1-111">自訂及管理 Office App-v 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="360b1-112">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="360b1-112">What to know before you start</span></span>


<span data-ttu-id="360b1-113">在使用 App-v 部署 Office 2016 之前，請先查看下列規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="360b1-113">Before you deploy Office 2016 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="360b1-114">支援的 Office 版本與 Office 共存</span><span class="sxs-lookup"><span data-stu-id="360b1-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="360b1-115">您可以使用下表來取得支援的 Office 版本相關資訊，以及如何執行共存的 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="360b1-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-116">要查看的資訊</span><span class="sxs-lookup"><span data-stu-id="360b1-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="360b1-117">描述</span><span class="sxs-lookup"><span data-stu-id="360b1-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Supported versions of Microsoft Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="360b1-118">支援的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="360b1-118">Supported versions of Microsoft Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="360b1-119">支援的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="360b1-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="360b1-120">支援的部署類型（例如，桌面、個人虛擬桌面基礎結構（VDI）、彙集的 VDI）</span><span class="sxs-lookup"><span data-stu-id="360b1-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="360b1-121">Office 授權選項</span><span class="sxs-lookup"><span data-stu-id="360b1-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with coexisting versions of Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)"><span data-ttu-id="360b1-122">規劃與共存版本的 Office 一起使用 App-v</span><span class="sxs-lookup"><span data-stu-id="360b1-122">Planning for Using App-V with coexisting versions of Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="360b1-123">在同一部電腦上安裝不同版本的 Office 時的考慮</span><span class="sxs-lookup"><span data-stu-id="360b1-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="360b1-124">封裝、發佈和部署需求</span><span class="sxs-lookup"><span data-stu-id="360b1-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="360b1-125">在使用 App-v 部署 Office 之前，請先檢查下列需求。</span><span class="sxs-lookup"><span data-stu-id="360b1-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-126">工作</span><span class="sxs-lookup"><span data-stu-id="360b1-126">Task</span></span></th>
<th align="left"><span data-ttu-id="360b1-127">需求</span><span class="sxs-lookup"><span data-stu-id="360b1-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-128">封裝</span><span class="sxs-lookup"><span data-stu-id="360b1-128">Packaging</span></span></p></td>
<td align="left">
<ul>
<li><p><span data-ttu-id="360b1-129">您要部署至使用者的所有 Office 應用程式必須位於單一套件中。</span><span class="sxs-lookup"><span data-stu-id="360b1-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="360b1-130">在 App-v 5.1 及更新版本中，您必須使用 Office 部署工具來建立套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-130">In App-V 5.1 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="360b1-131">您無法使用排序器。</span><span class="sxs-lookup"><span data-stu-id="360b1-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="360b1-132">如果您要部署 Microsoft Visio 2016，以及 Office 的 Microsoft Project 2016，您必須將它們包含在 Office 的同一個套件中。</span><span class="sxs-lookup"><span data-stu-id="360b1-132">If you are deploying Microsoft Visio 2016 and Microsoft Project 2016 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="360b1-133">如需詳細資訊，請參閱 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)"> 使用 Office 部署 Visio 2016 和 Project 2016 </a> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2016 and Project 2016 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-134">發行</span><span class="sxs-lookup"><span data-stu-id="360b1-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="360b1-135">您只能將一個 Office 套件發佈至每個用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="360b1-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="360b1-136">您必須全域發佈 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-136">You must publish the Office package globally.</span></span> <span data-ttu-id="360b1-137">您無法發佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="360b1-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-138">使用遠端桌面服務將下列任何產品部署到共用電腦，例如：</span><span class="sxs-lookup"><span data-stu-id="360b1-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="360b1-139">適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="360b1-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="360b1-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="360b1-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="360b1-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="360b1-142">您必須啟用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共用電腦啟用 </a> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
</td>
</tr>
</tbody>
</table>



### <span data-ttu-id="360b1-143">從套件中排除 Office 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-143">Excluding Office applications from a package</span></span>

<span data-ttu-id="360b1-144">下表說明從套件中排除特定 Office 應用程式的建議方法。</span><span class="sxs-lookup"><span data-stu-id="360b1-144">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-145">工作</span><span class="sxs-lookup"><span data-stu-id="360b1-145">Task</span></span></th>
<th align="left"><span data-ttu-id="360b1-146">詳細資料</span><span class="sxs-lookup"><span data-stu-id="360b1-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-147">使用 <strong> </strong> Office 部署工具建立套件時，請使用 ExcludeApp 設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-147">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="360b1-148">可讓您在 Office 部署工具建立套件時，從套件中排除特定的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-148">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="360b1-149">例如，您可以使用這個設定來建立只包含 Microsoft Word 的套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-149">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="360b1-150">如需詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-150">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-151">修改 DeploymentConfig.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="360b1-151">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="360b1-152">建立套件之後，請修改 DeploymentConfig.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="360b1-152">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="360b1-153">此檔案包含執行 App-v 用戶端之電腦上所有使用者的預設套件設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-153">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="360b1-154">如需詳細資訊，請參閱 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)"> 停用 Office 2016 應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-154">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)">Disabling Office 2016 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="360b1-155">使用 Office 部署工具為 App-v 建立 Office 2016 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-155">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="360b1-156">完成下列步驟，以針對 App-v 5.1 或更新版本建立 Office 2016 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-156">Complete the following steps to create an Office 2016 package for App-V 5.1 or later.</span></span>

><span data-ttu-id="360b1-157">**Important** &nbsp; 重要 &nbsp;在 App-V 5.1 及更新版本中，您必須使用 Office 部署工具來建立套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-157">**Important**&nbsp;&nbsp;In App-V 5.1 and later, you must use the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="360b1-158">您無法使用 Sequencer 來建立套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-158">You cannot use the Sequencer to create packages.</span></span>

### <span data-ttu-id="360b1-159">查看使用 Office 部署工具的先決條件</span><span class="sxs-lookup"><span data-stu-id="360b1-159">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="360b1-160">您要安裝 Office 部署工具的電腦必須具備：</span><span class="sxs-lookup"><span data-stu-id="360b1-160">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-161">必備</span><span class="sxs-lookup"><span data-stu-id="360b1-161">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="360b1-162">描述</span><span class="sxs-lookup"><span data-stu-id="360b1-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-163">必備軟體</span><span class="sxs-lookup"><span data-stu-id="360b1-163">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-164">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="360b1-164">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-165">支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="360b1-165">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="360b1-166">64位版本的 Windows 10</span><span class="sxs-lookup"><span data-stu-id="360b1-166">64-bit version of Windows 10</span></span></p></li>
<li><p><span data-ttu-id="360b1-167">64位版本的 Windows 8 或8。1</span><span class="sxs-lookup"><span data-stu-id="360b1-167">64-bit version of Windows 8 or 8.1</span></span></p></li>
<li><p><span data-ttu-id="360b1-168">64位版本的 Windows 7</span><span class="sxs-lookup"><span data-stu-id="360b1-168">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


><span data-ttu-id="360b1-169">**記事** 在本主題中，「Office 2016 App-V 封裝」一詞是指訂閱授權。</span><span class="sxs-lookup"><span data-stu-id="360b1-169">**Note**  In this topic, the term “Office 2016 App-V package” refers to subscription licensing.</span></span>


### <span data-ttu-id="360b1-170">使用 Office 部署工具建立 Office 2016 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-170">Create Office 2016 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="360b1-171">您可以使用 Office 部署工具來建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-171">You create Office 2016 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="360b1-172">下列指示說明如何使用訂閱授權建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-172">The following instructions explain how to create an Office 2016 App-V package with Subscription Licensing.</span></span>

<span data-ttu-id="360b1-173">在64位 Windows 電腦上建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-173">Create Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="360b1-174">建立之後，Office 2016 App-v 套件將會在32位和64位的 Windows 7、Windows 8.1 和 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="360b1-174">Once created, the Office 2016 App-V package will run on 32-bit and 64-bit Windows 7, Windows 8.1, and Windows 10 computers.</span></span>

### <span data-ttu-id="360b1-175">下載 Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="360b1-175">Download the Office Deployment Tool</span></span>

<span data-ttu-id="360b1-176">系統會使用 Office 部署工具建立 office 2016 App-v 套件，該工具會產生 Office 2016 App-v 封裝。</span><span class="sxs-lookup"><span data-stu-id="360b1-176">Office 2016 App-V Packages are created using the Office Deployment Tool, which generates an Office 2016 App-V Package.</span></span> <span data-ttu-id="360b1-177">無法透過 App-v 排序器建立或修改套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-177">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="360b1-178">開始建立套件：</span><span class="sxs-lookup"><span data-stu-id="360b1-178">To begin package creation:</span></span>

1.  <span data-ttu-id="360b1-179">下載適用于隨選即用的[Office 2016 部署工具](https://www.microsoft.com/download/details.aspx?id=49117)。</span><span class="sxs-lookup"><span data-stu-id="360b1-179">Download the [Office 2016 Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>

> <span data-ttu-id="360b1-180">**重要**您必須使用 Office 2016 部署工具來建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-180">**Important** You must use the Office 2016 Deployment Tool to create Office 2016 App-V Packages.</span></span>
> 2. <span data-ttu-id="360b1-181">執行 .exe 檔案，並將其功能解壓至想要的位置。</span><span class="sxs-lookup"><span data-stu-id="360b1-181">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="360b1-182">若要簡化這個程式，您可以建立共用網路資料夾，以儲存功能。</span><span class="sxs-lookup"><span data-stu-id="360b1-182">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    Example: \\\\Server\\Office2016

3. <span data-ttu-id="360b1-183">檢查 setup.exe 和 configuration.xml 檔案是否存在，且位於您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="360b1-183">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="360b1-184">下載 Office 2016 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-184">Download Office 2016 applications</span></span>

<span data-ttu-id="360b1-185">下載 Office 部署工具之後，您就可以使用它來取得最新的 Office 2016 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-185">After you download the Office Deployment Tool, you can use it to get the latest Office 2016 applications.</span></span> <span data-ttu-id="360b1-186">在取得 Office 應用程式之後，您會建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-186">After getting the Office applications, you create the Office 2016 App-V package.</span></span>

<span data-ttu-id="360b1-187">Office 部署工具中包含的 XML 檔案會指定產品詳細資料，例如隨附的語言和 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-187">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1. <span data-ttu-id="360b1-188">**自訂範例 XML 設定檔：** 使用您使用 Office 部署工具下載的範例 XML 設定檔，來自訂 Office 應用程式：</span><span class="sxs-lookup"><span data-stu-id="360b1-188">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

   1. <span data-ttu-id="360b1-189">在記事本或您最愛的文字編輯器中開啟範例 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="360b1-189">Open the sample XML file in Notepad or your favorite text editor.</span></span>

   2. <span data-ttu-id="360b1-190">在範例 configuration.xml 檔案開啟並準備好進行編輯時，您可以指定產品、語言及儲存 Office 2016 應用程式的路徑。</span><span class="sxs-lookup"><span data-stu-id="360b1-190">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2016 applications.</span></span> <span data-ttu-id="360b1-191">下列是 configuration.xml 檔案的基本範例：</span><span class="sxs-lookup"><span data-stu-id="360b1-191">The following is a basic example of the configuration.xml file:</span></span>

      ```xml
      <Configuration>
         <Add SourcePath= ”\\Server\Office2016” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      ><span data-ttu-id="360b1-192">**記事** [配置 XML] 是範例 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="360b1-192">**Note**  The configuration XML is a sample XML file.</span></span> <span data-ttu-id="360b1-193">檔案包含已加上注釋的線條。您可以「取消注釋」這些線條，以自訂檔案的其他設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-193">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span> <span data-ttu-id="360b1-194">若要 "取消注釋" 這些線條，請移除「<！</span><span class="sxs-lookup"><span data-stu-id="360b1-194">To “uncomment” these lines, remove the "<!</span></span> <span data-ttu-id="360b1-195">--從行開頭，然後從行尾的 "-->"。</span><span class="sxs-lookup"><span data-stu-id="360b1-195">- -" from the beginning of the line, and the "-- >" from the end of the line.</span></span>

      <span data-ttu-id="360b1-196">上述 XML 設定檔指定 Office 2016 專業增強版32位版本（包括 Visio 專業增強版）將會以英文下載至 \\\\server\\Office 2016，這是儲存 Office 應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="360b1-196">The above XML configuration file specifies that Office 2016 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2016, which is the location where Office applications will be saved to.</span></span> <span data-ttu-id="360b1-197">請注意，應用程式的產品識別碼不會影響 Office 的最終授權。</span><span class="sxs-lookup"><span data-stu-id="360b1-197">Note that the Product ID of the applications will not affect the final licensing of Office.</span></span> <span data-ttu-id="360b1-198">您可以透過在後續階段指定授權，從相同的應用程式建立具有各種授權的 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-198">Office 2016 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage.</span></span> <span data-ttu-id="360b1-199">下表摘要列出了 XML 檔案的可自訂屬性和元素：</span><span class="sxs-lookup"><span data-stu-id="360b1-199">The table below summarizes the customizable attributes and elements of XML file:</span></span>

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left"><span data-ttu-id="360b1-200">輸入</span><span class="sxs-lookup"><span data-stu-id="360b1-200">Input</span></span></th>
      <th align="left"><span data-ttu-id="360b1-201">描述</span><span class="sxs-lookup"><span data-stu-id="360b1-201">Description</span></span></th>
      <th align="left"><span data-ttu-id="360b1-202">範例</span><span class="sxs-lookup"><span data-stu-id="360b1-202">Example</span></span></th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="360b1-203">Add 元素</span><span class="sxs-lookup"><span data-stu-id="360b1-203">Add element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-204">指定套件中要包含的產品和語言。</span><span class="sxs-lookup"><span data-stu-id="360b1-204">Specifies the products and languages to include in the package.</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-205">無</span><span class="sxs-lookup"><span data-stu-id="360b1-205">N/A</span></span></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="360b1-206">OfficeClientEdition （Add 元素的屬性）</span><span class="sxs-lookup"><span data-stu-id="360b1-206">OfficeClientEdition (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-207">指定要使用的 Office 2016 產品版本：32位或64位。</span><span class="sxs-lookup"><span data-stu-id="360b1-207">Specifies the edition of Office 2016 product to use: 32-bit or 64-bit.</span></span> <span data-ttu-id="360b1-208">如果 <strong> OfficeClientEdition 未 </strong> 設定為有效的值，則操作會失敗。</span><span class="sxs-lookup"><span data-stu-id="360b1-208">The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</span></span></p></td>
      <td align="left"><p><strong><span data-ttu-id="360b1-209">OfficeClientEdition </strong> = &quot; 32&quot;</span><span class="sxs-lookup"><span data-stu-id="360b1-209">OfficeClientEdition</strong>=&quot;32&quot;</span></span></p>
      <p><strong><span data-ttu-id="360b1-210">OfficeClientEdition </strong> = &quot; 64&quot;</span><span class="sxs-lookup"><span data-stu-id="360b1-210">OfficeClientEdition</strong>=&quot;64&quot;</span></span></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="360b1-211">Product 元素</span><span class="sxs-lookup"><span data-stu-id="360b1-211">Product element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-212">指定應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-212">Specifies the application.</span></span> <span data-ttu-id="360b1-213">若要在應用程式中加入，您必須在此處將 Project 2016 和 Visio 2016 指定為已新增的產品。</span><span class="sxs-lookup"><span data-stu-id="360b1-213">Project 2016 and Visio 2016 must be specified here as an added product to be included in the applications.</span></span>

      <span data-ttu-id="360b1-214">如需產品識別碼的詳細資訊，請參閱 <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)"> Office 部署工具支援的隨選即用的產品識別碼</span><span class="sxs-lookup"><span data-stu-id="360b1-214">For more information about the product IDs, see <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)">Product IDs that are supported by the Office Deployment Tool for Click-to-Run</span></span></a>
      </p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      </td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="360b1-215">語言元素</span><span class="sxs-lookup"><span data-stu-id="360b1-215">Language element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-216">指定應用程式中支援的語言</span><span class="sxs-lookup"><span data-stu-id="360b1-216">Specifies the language supported in the applications</span></span></p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="360b1-217">版本（Add 元素的屬性）</span><span class="sxs-lookup"><span data-stu-id="360b1-217">Version (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-218">選用。</span><span class="sxs-lookup"><span data-stu-id="360b1-218">Optional.</span></span> <span data-ttu-id="360b1-219">指定套件要使用的組建</span><span class="sxs-lookup"><span data-stu-id="360b1-219">Specifies a build to use for the package</span></span></p>
      <p><span data-ttu-id="360b1-220">預設為最新的播發組建（在 Office 來源 v32.CAB 中定義）。</span><span class="sxs-lookup"><span data-stu-id="360b1-220">Defaults to latest advertised build (as defined in v32.CAB at the Office source).</span></span></p></td>
      <td align="left"><p><code>16.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="360b1-221">SourcePath （Add 元素的屬性）</span><span class="sxs-lookup"><span data-stu-id="360b1-221">SourcePath (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-222">指定要將應用程式儲存到哪個位置。</span><span class="sxs-lookup"><span data-stu-id="360b1-222">Specifies the location in which the applications will be saved to.</span></span></p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2016”</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="360b1-223">分支（Add 元素的屬性）</span><span class="sxs-lookup"><span data-stu-id="360b1-223">Branch (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="360b1-224">選用。</span><span class="sxs-lookup"><span data-stu-id="360b1-224">Optional.</span></span> <span data-ttu-id="360b1-225">指定您要下載或安裝之產品的更新分支。</span><span class="sxs-lookup"><span data-stu-id="360b1-225">Specifies the update branch for the product that you want to download or install.</span></span> </p><p><span data-ttu-id="360b1-226">如需更新分支的詳細資訊，請參閱適用于企業的 Microsoft 365 應用程式更新分支的概覽。</span><span class="sxs-lookup"><span data-stu-id="360b1-226">For more information about update branches, see Overview of update branches for Microsoft 365 Apps for enterprise.</span></span></p></td>
      <td align="left"><p><code>Branch = &quot;Business&quot;</code></p></td>
      </tr>
      </tbody>
      </table>

      <span data-ttu-id="360b1-227">在編輯 configuration.xml 檔案以指定所需的產品、語言，以及 Office 2016 應用程式儲存到的位置之後，您可以儲存設定檔，例如 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="360b1-227">After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2016 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.</span></span>

2. <span data-ttu-id="360b1-228">**將應用程式下載到指定位置：** 使用提升許可權的命令提示字元與64位作業系統，下載稍後將轉換成 App-v 套件的 Office 2016 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-228">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2016 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="360b1-229">以下是包含詳細描述的範例命令：</span><span class="sxs-lookup"><span data-stu-id="360b1-229">Below is an example command with a description of details:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /download \\server\Office2016\Customconfig.xml
   ```

   <span data-ttu-id="360b1-230">在範例中：</span><span class="sxs-lookup"><span data-stu-id="360b1-230">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-231">\server\Office2016</span><span class="sxs-lookup"><span data-stu-id="360b1-231">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-232">是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="360b1-232">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="360b1-233">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="360b1-233">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-234">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="360b1-234">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-235">/download</span><span class="sxs-lookup"><span data-stu-id="360b1-235">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-236">下載您在 customConfig.xml 檔案中指定的 Office 2016 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-236">downloads the Office 2016 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="360b1-237">這些 bits 可以在 Office 2016 App-v 套件中以大量授權進行轉換。</span><span class="sxs-lookup"><span data-stu-id="360b1-237">These bits can be later converted in an Office 2016 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="360b1-238">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="360b1-238">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-239">傳遞完成下載程式所需的 XML 設定檔，在此範例中 customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="360b1-239">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="360b1-240">使用 [下載] 命令之後，請在配置 xml 檔案中指定的位置找到 Office 應用程式，此範例 \Server\Office2016。</span><span class="sxs-lookup"><span data-stu-id="360b1-240">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2016.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="360b1-241">將 Office 應用程式轉換成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-241">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="360b1-242">透過 Office 部署工具下載 Office 2016 應用程式之後，請使用 Office 部署工具，將它們轉換成 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-242">After you download the Office 2016 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2016 App-V package.</span></span> <span data-ttu-id="360b1-243">完成與您的授權模型相對應的步驟。</span><span class="sxs-lookup"><span data-stu-id="360b1-243">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="360b1-244">您需要執行的作業摘要：</span><span class="sxs-lookup"><span data-stu-id="360b1-244">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="360b1-245">在64位 Windows 電腦上建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-245">Create the Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="360b1-246">不過，套件將在32位和64位 Windows 7、Windows 8 或8.1 以及 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="360b1-246">However, the package will run on 32-bit and 64-bit Windows 7, Windows 8 or 8.1, and Windows 10 computers.</span></span>

-   <span data-ttu-id="360b1-247">使用 Office 部署工具建立訂閱授權套件的 Office App-v 套件，然後修改 CustomConfig.xml 設定檔。</span><span class="sxs-lookup"><span data-stu-id="360b1-247">Create an Office App-V package for Subscription Licensing package by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="360b1-248">下表摘要列出您所使用的授權模型 CustomConfig.xml 檔案中所需輸入的值。</span><span class="sxs-lookup"><span data-stu-id="360b1-248">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="360b1-249">表格後續各節中的步驟將會指定您所需的確切專案。</span><span class="sxs-lookup"><span data-stu-id="360b1-249">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

><span data-ttu-id="360b1-250">**Note** &nbsp; 記事 &nbsp;您可以使用 Office 部署工具來為適用于企業的 Microsoft 365 應用程式建立 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-250">**Note**&nbsp;&nbsp;You can use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="360b1-251">不支援為大量授權版本的 Office 專業增強版或 Office Standard 建立套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-251">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-252">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="360b1-252">Product ID</span></span></th>
<th align="left"><span data-ttu-id="360b1-253">訂閱授權</span><span class="sxs-lookup"><span data-stu-id="360b1-253">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="360b1-254">Office 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-254">Office 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="360b1-255">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-255">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="360b1-256">Office 2016 與 Visio 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-256">Office 2016 with Visio 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="360b1-257">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-257">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="360b1-258">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-258">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="360b1-259">Office 2016 與 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-259">Office 2016 with Visio 2016 and Project 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="360b1-260">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-260">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="360b1-261">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-261">VisioProRetail</span></span></p>
<p><span data-ttu-id="360b1-262">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="360b1-262">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="360b1-263">如何將 Office 應用程式轉換成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-263">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="360b1-264">在 [記事本] 中，重新開啟 CustomConfig.xml 檔案，然後對檔案進行下列變更：</span><span class="sxs-lookup"><span data-stu-id="360b1-264">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="360b1-265">參數</span><span class="sxs-lookup"><span data-stu-id="360b1-265">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="360b1-266">要變更值的專案</span><span class="sxs-lookup"><span data-stu-id="360b1-266">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="360b1-267">SourcePath</span><span class="sxs-lookup"><span data-stu-id="360b1-267">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="360b1-268">指向先前下載的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-268">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="360b1-269">ProductID</span><span class="sxs-lookup"><span data-stu-id="360b1-269">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="360b1-270">指定訂閱授權，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="360b1-270">Specify Subscription licensing, as shown in the following example:</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2016&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="360b1-271">在這個範例中，建立含訂閱授權的套件的下列變更：</span><span class="sxs-lookup"><span data-stu-id="360b1-271">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-272">SourcePath</span><span class="sxs-lookup"><span data-stu-id="360b1-272">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-273">路徑，該路徑已變更為指向先前下載的 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-273">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="360b1-274">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="360b1-274">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-275">[Office 的變更為] <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-275">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-276">產品識別碼</span><span class="sxs-lookup"><span data-stu-id="360b1-276">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-277">Visio 的 [變更為] <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="360b1-277">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p></p>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="360b1-278">ExcludeApp （選用）</span><span class="sxs-lookup"><span data-stu-id="360b1-278">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="360b1-279">可讓您指定您不想要包含在 Office 部署工具所建立的 App-v 套件中的 Office 程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-279">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="360b1-280">例如，您可以排除 Access 和 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="360b1-280">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="360b1-281">PACKAGEGUID （選用）</span><span class="sxs-lookup"><span data-stu-id="360b1-281">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="360b1-282">根據預設，Office 部署工具所建立的所有 app-v 套件都共用相同的 App-v 套件識別碼。</span><span class="sxs-lookup"><span data-stu-id="360b1-282">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="360b1-283">您可以使用 PACKAGEGUID 為每個套件指定不同的套件識別碼，這可讓您發佈由 Office 部署工具所建立的多個 App-v 套件，並使用 App-v 伺服器來管理它們。</span><span class="sxs-lookup"><span data-stu-id="360b1-283">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="360b1-284">若要在不同的使用者建立不同的套件時，使用這個參數的範例。</span><span class="sxs-lookup"><span data-stu-id="360b1-284">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="360b1-285">例如，您可以建立一個包含適用于部分使用者之 Office 2016 的套件，並使用 Office 2016 和 Visio 2016 為其他使用者組建立另一個套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-285">For example, you can create a package with just Office 2016 for some users, and create another package with Office 2016 and Visio 2016 for another set of users.</span></span></p>

   <span data-ttu-id="360b1-286">&gt;<strong>注意 </strong> 即使您使用的是唯一的套件識別碼，您仍然可以只將一個 app-v 套件部署到單一裝置。</span><span class="sxs-lookup"><span data-stu-id="360b1-286">&gt;<strong>Note</strong> Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span>
   </td>
   </tr>
   </tbody>
   </table>


2. <span data-ttu-id="360b1-287">使用/packager 命令，將 Office 應用程式轉換為 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-287">Use the /packager command to convert the Office applications to an Office 2016 App-V package.</span></span>

   <span data-ttu-id="360b1-288">例如：</span><span class="sxs-lookup"><span data-stu-id="360b1-288">For example:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /packager \\server\Office2016\Customconfig.xml  \\server\share\Office2016AppV
   ```

   <span data-ttu-id="360b1-289">在範例中：</span><span class="sxs-lookup"><span data-stu-id="360b1-289">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-290">\server\Office2016</span><span class="sxs-lookup"><span data-stu-id="360b1-290">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-291">是包含 Office 部署工具以及自訂 Configuration.xml 檔案的網路共用位置 Customconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="360b1-291">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="360b1-292">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="360b1-292">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-293">是 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="360b1-293">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-294">/packager</span><span class="sxs-lookup"><span data-stu-id="360b1-294">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-295">使用 customConfig.xml 檔案中指定的授權類型建立 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-295">creates the Office 2016 App-V package with the type of licensing specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="360b1-296">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="360b1-296">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-297">傳送已針對封裝階段準備的設定 XML 檔案（在此案例中為 customConfig）。</span><span class="sxs-lookup"><span data-stu-id="360b1-297">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="360b1-298">\server\share\Office 2016AppV</span><span class="sxs-lookup"><span data-stu-id="360b1-298">\server\share\Office 2016AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="360b1-299">指定新建立的 Office App-v 封裝的位置。</span><span class="sxs-lookup"><span data-stu-id="360b1-299">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2016 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note** To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="360b1-300">確認 Office 2016 App-v 套件正常運作：</span><span class="sxs-lookup"><span data-stu-id="360b1-300">Verify that the Office 2016 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="360b1-301">將您全域建立的 Office 2016 App-v 套件發佈至測試電腦，並確認 [Office 2016] 快捷方式隨即出現。</span><span class="sxs-lookup"><span data-stu-id="360b1-301">Publish the Office 2016 App-V package, which you created globally, to a test computer, and verify that the Office 2016 shortcuts appear.</span></span>

   2.  <span data-ttu-id="360b1-302">啟動幾個 Office 2016 應用程式（例如 Excel 或 Word），以確保您的套件如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="360b1-302">Start a few Office 2016 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="360b1-303">發佈應用程式的 Office 套件-V</span><span class="sxs-lookup"><span data-stu-id="360b1-303">Publishing the Office package for App-V</span></span>


<span data-ttu-id="360b1-304">使用下列資訊發佈 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-304">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="360b1-305">發佈 Office App-v 套件的方法</span><span class="sxs-lookup"><span data-stu-id="360b1-305">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="360b1-306">使用您用於任何其他套件的相同方法，部署適用于 Office 2016 的 app-v 套件：</span><span class="sxs-lookup"><span data-stu-id="360b1-306">Deploy the App-V package for Office 2016 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="360b1-307">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="360b1-307">System Center Configuration Manager</span></span>

-   <span data-ttu-id="360b1-308">App-v Server</span><span class="sxs-lookup"><span data-stu-id="360b1-308">App-V Server</span></span>

-   <span data-ttu-id="360b1-309">從 PowerShell 命令中獨立</span><span class="sxs-lookup"><span data-stu-id="360b1-309">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="360b1-310">發佈先決條件與需求</span><span class="sxs-lookup"><span data-stu-id="360b1-310">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-311">先決條件或需求</span><span class="sxs-lookup"><span data-stu-id="360b1-311">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="360b1-312">詳細資料</span><span class="sxs-lookup"><span data-stu-id="360b1-312">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-313">在 App-V 用戶端上啟用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="360b1-313">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-314">若要發佈 Office 2016 套件，您必須執行腳本。</span><span class="sxs-lookup"><span data-stu-id="360b1-314">To publish Office 2016 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="360b1-315">預設會停用 App-v 用戶端上的套件腳本。</span><span class="sxs-lookup"><span data-stu-id="360b1-315">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="360b1-316">若要啟用腳本，請執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="360b1-316">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-317">全域發佈 Office 2016 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-317">Publish the Office 2016 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-318">Office App-v 套件中的延伸點需要在電腦層級進行安裝。</span><span class="sxs-lookup"><span data-stu-id="360b1-318">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="360b1-319">當您在電腦層級發佈時，不需要任何必備動作或可轉散發元件，而且 Office 2016 套件全域可讓其應用程式像是原本安裝的 Office，而不需要系統管理員自訂套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-319">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2016 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="360b1-320">如何發佈 Office 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-320">How to publish an Office package</span></span>

<span data-ttu-id="360b1-321">執行下列命令以全域發佈 Office 套件：</span><span class="sxs-lookup"><span data-stu-id="360b1-321">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="360b1-322">從 App-v Server 上的 Web 管理主控台，您可以將許可權新增至電腦群組，而不是使用者群組，以便將套件全域發佈至對應群組中的電腦。</span><span class="sxs-lookup"><span data-stu-id="360b1-322">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="360b1-323">自訂及管理 Office App-v 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-323">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="360b1-324">若要管理您的 Office App-v 套件，請使用與任何其他套件相同的作業，但有幾個例外狀況，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="360b1-324">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="360b1-325">使用連線群組啟用 Office 外掛程式</span><span class="sxs-lookup"><span data-stu-id="360b1-325">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="360b1-326">停用 Office 2016 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-326">Disabling Office 2016 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="360b1-327">停用 Office 2016 快速鍵</span><span class="sxs-lookup"><span data-stu-id="360b1-327">Disabling Office 2016 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="360b1-328">管理 Office 2016 套件升級</span><span class="sxs-lookup"><span data-stu-id="360b1-328">Managing Office 2016 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="360b1-329">使用 Office 部署 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-329">Deploying Visio 2016 and Project 2016 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="360b1-330">使用連線群組啟用 Office 外掛程式</span><span class="sxs-lookup"><span data-stu-id="360b1-330">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="360b1-331">使用本節中的步驟，啟用 office 外掛程式與您的 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-331">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="360b1-332">若要使用 Office 外掛程式，您必須使用 App-v 排序器來建立只包含外掛程式的個別套件。您無法使用 Office 部署工具來建立外掛程式封裝。</span><span class="sxs-lookup"><span data-stu-id="360b1-332">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="360b1-333">接著，您可以建立包含 Office 套件和外掛程式套件的連線群組，如以下步驟所述。</span><span class="sxs-lookup"><span data-stu-id="360b1-333">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="360b1-334">若要啟用 Office App-v 的外掛程式套件</span><span class="sxs-lookup"><span data-stu-id="360b1-334">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="360b1-335">透過 App-V Server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。</span><span class="sxs-lookup"><span data-stu-id="360b1-335">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="360b1-336">使用 App-v 排序器來排序您的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-336">Sequence your plug-ins using the App-V Sequencer.</span></span> <span data-ttu-id="360b1-337">確定使用的電腦上已安裝 Office 2016 來為外掛程式進行排序。</span><span class="sxs-lookup"><span data-stu-id="360b1-337">Ensure that Office 2016 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="360b1-338">我們建議您在順序電腦上使用 Microsoft 365 App for enterprise （非虛擬），當您依序排列 Office 2016 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-338">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2016 plug-ins.</span></span>

3.  <span data-ttu-id="360b1-339">建立包含所需外掛程式的 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-339">Create an App-V package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="360b1-340">透過 App-V server、System Center Configuration Manager 或 PowerShell Cmdlet 新增連線群組。</span><span class="sxs-lookup"><span data-stu-id="360b1-340">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="360b1-341">新增 Office 2016 App-v 套件，以及您已排序到您所建立之連線群組的外掛程式套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-341">Add the Office 2016 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    ><span data-ttu-id="360b1-342">**重要**[連線] 群組中的套件順序決定了套件內容的合併順序。</span><span class="sxs-lookup"><span data-stu-id="360b1-342">**Important** The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="360b1-343">在您的連線群組描述項檔案中，先新增 Office 2016 App-v 套件，然後再新增外掛程式 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-343">In your Connection group descriptor file, add the Office 2016 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="360b1-344">請確定這兩個套件都發佈到目的電腦，且該外掛程式套件是以全域方式發佈，以符合已發佈的 Office 2016 App-v 套件的全域設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-344">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2016 App-V package.</span></span>

7.  <span data-ttu-id="360b1-345">確認外掛程式套件的部署設定檔與 Office 2016 App-v 套件具有相同的設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-345">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2016 App-V package has.</span></span>

    <span data-ttu-id="360b1-346">因為 Office 2016 App-v 套件與作業系統整合，所以外掛程式套件設定應該會相符。</span><span class="sxs-lookup"><span data-stu-id="360b1-346">Since the Office 2016 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="360b1-347">您可以在部署設定檔中搜尋「COM Mode」，並確保您的外掛程式套件將此值設定為「整合」，且 "InProcessEnabled" 和 "OutOfProcessEnabled" 與您發佈的 Office 2016 App-v 套件的設定相符。</span><span class="sxs-lookup"><span data-stu-id="360b1-347">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2016 App-V package you published.</span></span>

8.  <span data-ttu-id="360b1-348">開啟部署設定檔，並將**物件**的值設為**false**。</span><span class="sxs-lookup"><span data-stu-id="360b1-348">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="360b1-349">如果您在排序之後對部署設定檔進行任何變更，請確定該外掛程式套件是與檔案一起發佈。</span><span class="sxs-lookup"><span data-stu-id="360b1-349">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="360b1-350">確定您所建立的連線群組已啟用至所需的電腦上。</span><span class="sxs-lookup"><span data-stu-id="360b1-350">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="360b1-351">如果啟用連線群組時，所建立的連線群組可能會「待定」，如果是使用 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-351">The Connection Group created will likely “pend” if the Office 2016 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="360b1-352">如果發生這種情況，您必須重新開機，才能成功啟用連線群組。</span><span class="sxs-lookup"><span data-stu-id="360b1-352">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="360b1-353">當您成功發佈這兩個套件並啟用連線群組之後，請啟動目標 Office 2016 應用程式，並確認您發佈並新增至連線群組的外掛程式會如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="360b1-353">After you successfully publish both packages and enable the Connection Group, start the target Office 2016 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="360b1-354">停用 Office 2016 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-354">Disabling Office 2016 applications</span></span>

<span data-ttu-id="360b1-355">您可能會想要停用 Office App-v 封裝中的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-355">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="360b1-356">例如，您可以停用 Access，但讓所有其他 Office 應用程式成為主要的可用。</span><span class="sxs-lookup"><span data-stu-id="360b1-356">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="360b1-357">當您停用應用程式時，最終使用者將不再看到該應用程式的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="360b1-357">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="360b1-358">您不需要重新排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-358">You do not have to re-sequence the application.</span></span> <span data-ttu-id="360b1-359">當您在 Office 2016 App-v 套件發佈之後變更部署設定檔之後，您將會儲存變更、新增 Office 2016 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2016 App-v 封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-359">When you change the Deployment Configuration File after the Office 2016 App-V package has been published, you will save the changes, add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

><span data-ttu-id="360b1-360">**記事**若要排除特定的 Office 應用程式（例如，Access 和 InfoPath），當您使用 Office 部署工具建立 App-v 套件時，請使用**ExcludeApp**設定。</span><span class="sxs-lookup"><span data-stu-id="360b1-360">**Note** To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span>


**<span data-ttu-id="360b1-361">停用 Office 2016 應用程式</span><span class="sxs-lookup"><span data-stu-id="360b1-361">To disable an Office 2016 application</span></span>**

1.  <span data-ttu-id="360b1-362">使用文字編輯器（如**記事本**）開啟部署設定檔，然後搜尋「應用程式」。</span><span class="sxs-lookup"><span data-stu-id="360b1-362">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="360b1-363">搜尋您想要停用的 Office 應用程式，例如 Access 2016。</span><span class="sxs-lookup"><span data-stu-id="360b1-363">Search for the Office application you want to disable, for example, Access 2016.</span></span>

3.  <span data-ttu-id="360b1-364">將 [Enabled] 的值從 "true" 變更為 "false"。</span><span class="sxs-lookup"><span data-stu-id="360b1-364">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="360b1-365">儲存部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="360b1-365">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="360b1-366">使用新的部署設定檔新增 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-366">Add the Office 2016 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot}]\office16\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office16\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="360b1-367">重新新增 Office 2016 App-v 套件，然後使用新的部署設定檔重新發佈，以將新設定套用至 Office 2016 App-v 封裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="360b1-367">Re-add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="360b1-368">停用 Office 2016 快速鍵</span><span class="sxs-lookup"><span data-stu-id="360b1-368">Disabling Office 2016 shortcuts</span></span>

<span data-ttu-id="360b1-369">您可能會想要針對特定的 Office 應用程式停用快速鍵，而不是取消發佈或移除套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-369">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="360b1-370">下列範例顯示如何停用 Microsoft Access 的快速鍵。</span><span class="sxs-lookup"><span data-stu-id="360b1-370">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="360b1-371">若要停用 Office 2016 應用程式的快速鍵</span><span class="sxs-lookup"><span data-stu-id="360b1-371">To disable shortcuts for Office 2016 applications</span></span>**

1.  <span data-ttu-id="360b1-372">在記事本中開啟部署設定檔案，然後搜尋 [快速鍵]。</span><span class="sxs-lookup"><span data-stu-id="360b1-372">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="360b1-373">若要停用某些快速鍵，請刪除或批註您不想要的特定快速鍵。</span><span class="sxs-lookup"><span data-stu-id="360b1-373">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="360b1-374">您必須讓子系統保持存在且已啟用。</span><span class="sxs-lookup"><span data-stu-id="360b1-374">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="360b1-375">例如，在下列範例中，刪除 Microsoft Access 快速鍵，同時保持子系統 &lt; 快捷方式/shortcut， &gt; &lt; &gt; 以停用 Microsoft Access 快速鍵。</span><span class="sxs-lookup"><span data-stu-id="360b1-375">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2016\Access 2016.lnk</File>
           <Target>[{AppvPackageRoot}])office16\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office16\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="360b1-376">儲存部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="360b1-376">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="360b1-377">使用新的部署設定檔重新發佈 Office 2016 App-v 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-377">Republish Office 2016 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="360b1-378">您可以透過修改 App-v 套件的部署設定來變更許多其他設定，例如，檔案類型關聯、虛擬檔案系統等。</span><span class="sxs-lookup"><span data-stu-id="360b1-378">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="360b1-379">如需如何使用部署設定檔來變更 app-v 套件設定的其他資訊，請參閱本文結尾的 [其他資源] 區段。</span><span class="sxs-lookup"><span data-stu-id="360b1-379">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="360b1-380">管理 Office 2016 套件升級</span><span class="sxs-lookup"><span data-stu-id="360b1-380">Managing Office 2016 package upgrades</span></span>

<span data-ttu-id="360b1-381">若要升級 Office 2016 套件，請使用 Office 部署工具。</span><span class="sxs-lookup"><span data-stu-id="360b1-381">To upgrade an Office 2016 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="360b1-382">若要升級先前部署的 Office 2016 套件，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="360b1-382">To upgrade a previously deployed Office 2016 package, perform the following steps.</span></span>

**<span data-ttu-id="360b1-383">如何升級先前部署的 Office 2016 套件</span><span class="sxs-lookup"><span data-stu-id="360b1-383">How to upgrade a previously deployed Office 2016 package</span></span>**

1. <span data-ttu-id="360b1-384">使用最新的 Office 2016 應用程式軟體，透過 Office 部署工具建立新的 Office 2016 套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-384">Create a new Office 2016 package through the Office Deployment Tool that uses the most recent Office 2016 application software.</span></span> <span data-ttu-id="360b1-385">最新的 Office 2016 bits 隨時都可以透過建立 Office 2016 App-v 套件的下載階段取得。</span><span class="sxs-lookup"><span data-stu-id="360b1-385">The most recent Office 2016 bits can always be obtained through the download stage of creating an Office 2016 App-V Package.</span></span> <span data-ttu-id="360b1-386">新建立的 Office 2016 套件將會有最新的更新及新的版本 ID。</span><span class="sxs-lookup"><span data-stu-id="360b1-386">The newly created Office 2016 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="360b1-387">使用 Office 部署工具所建立的所有套件都有相同的沿襲。</span><span class="sxs-lookup"><span data-stu-id="360b1-387">All packages created using the Office Deployment Tool have the same lineage.</span></span>

   > <span data-ttu-id="360b1-388">**記事**Office App-v 封裝有兩個版本識別碼：</span><span class="sxs-lookup"><span data-stu-id="360b1-388">**Note** Office App-V packages have two Version IDs:</span></span>
   > <ul>
   > <li><span data-ttu-id="360b1-389">在使用 Office 部署工具所建立的所有套件中，都是唯一的 Office 2016 App-v 套件版本 ID。</span><span class="sxs-lookup"><span data-stu-id="360b1-389">An Office 2016 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span></li>
   > <li><span data-ttu-id="360b1-390">第二個 App-v 套件版本 ID： x.x.x.x （例如，在 AppX 資訊清單中，只要有新版 Office 本身，就只會變更）。</span><span class="sxs-lookup"><span data-stu-id="360b1-390">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="360b1-391">例如，如果有可升級的新 Office 2016 版本，且已透過 Office 部署工具建立套件以納入這些升級，則 X.x.x.x 版本 ID 將會變更，以反映 Office 版本本身已變更。</span><span class="sxs-lookup"><span data-stu-id="360b1-391">For example, if a new Office 2016 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="360b1-392">App-v server 會使用 X.x.x.x 版本 ID 來區分此套件，並辨識它包含先前已發佈套件的新升級，因此，將其發佈為現有 Office 2016 套件的升級。。</span><span class="sxs-lookup"><span data-stu-id="360b1-392">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2016 package.</span></span></li>
   > </ul>


2. <span data-ttu-id="360b1-393">將新建立的 Office 2016 App-v 套件，全域發佈到您想要套用新更新的電腦上。</span><span class="sxs-lookup"><span data-stu-id="360b1-393">Globally publish the newly created Office 2016 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="360b1-394">由於新的套件與舊版 Office 2016 App-v 套件有相同的沿襲，所以發佈含有更新的新套件只會將新的變更套用至舊的套件，因此會快速進行。</span><span class="sxs-lookup"><span data-stu-id="360b1-394">Since the new package has the same lineage of the older Office 2016 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3. <span data-ttu-id="360b1-395">將會以任何全域發佈的 app-v 套件相同的方式來套用升級。</span><span class="sxs-lookup"><span data-stu-id="360b1-395">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="360b1-396">因為應用程式可能正在使用，所以升級可能會延遲，直到電腦重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="360b1-396">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>


### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="360b1-397">使用 Office 部署 Visio 2016 和 Project 2016</span><span class="sxs-lookup"><span data-stu-id="360b1-397">Deploying Visio 2016 and Project 2016 with Office</span></span>

<span data-ttu-id="360b1-398">下表說明使用 Office 部署 Visio 2016 和 Project 2016 的需求和選項。</span><span class="sxs-lookup"><span data-stu-id="360b1-398">The following table describes the requirements and options for deploying Visio 2016 and Project 2016 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-399">工作</span><span class="sxs-lookup"><span data-stu-id="360b1-399">Task</span></span></th>
<th align="left"><span data-ttu-id="360b1-400">詳細資料</span><span class="sxs-lookup"><span data-stu-id="360b1-400">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-401">我要如何使用 Office 封裝及發佈 Visio 2016 和 Project 2016？</span><span class="sxs-lookup"><span data-stu-id="360b1-401">How do I package and publish Visio 2016 and Project 2016 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-402">您必須在與 Office 相同的套件中包含 Visio 2016 和 Project 2016。</span><span class="sxs-lookup"><span data-stu-id="360b1-402">You must include Visio 2016 and Project 2016 in the same package with Office.</span></span></p>
<p><span data-ttu-id="360b1-403">如果您不是部署 Office，只要遵循本主題中所述的封裝、發佈和部署需求，就可以建立內含 Visio 與/或專案的套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-403">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow the packaging, publishing, and deployment requirements described in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-404">我要如何將 Visio 2016 和 Project 2016 部署至特定使用者？</span><span class="sxs-lookup"><span data-stu-id="360b1-404">How can I deploy Visio 2016 and Project 2016 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-405">使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="360b1-405">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="360b1-406">如果您想要 .。。</span><span class="sxs-lookup"><span data-stu-id="360b1-406">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="360b1-407">...然後使用此方法</span><span class="sxs-lookup"><span data-stu-id="360b1-407">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="360b1-408">建立兩個不同的套件，並將每個套件部署至不同的使用者群組</span><span class="sxs-lookup"><span data-stu-id="360b1-408">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-409">建立及部署下列套件：</span><span class="sxs-lookup"><span data-stu-id="360b1-409">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="360b1-410">僅包含 Office 部署至使用者只需要 Office 的電腦的套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-410">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="360b1-411">包含 Office、Visio 和 Project-部署至使用者需要所有三個應用程式的電腦的套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-411">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="360b1-412">如果您只想在整個組織中使用一個套件，或者如果您有共用電腦的使用者：</span><span class="sxs-lookup"><span data-stu-id="360b1-412">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="360b1-413">遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="360b1-413">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="360b1-414">建立包含 Office、Visio 和 Project 的套件。</span><span class="sxs-lookup"><span data-stu-id="360b1-414">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="360b1-415">將套件部署到所有使用者。</span><span class="sxs-lookup"><span data-stu-id="360b1-415">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="360b1-416">使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 來防止特定使用者使用 Visio 和 Project。</span><span class="sxs-lookup"><span data-stu-id="360b1-416">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>


## <span data-ttu-id="360b1-417">其他資源</span><span class="sxs-lookup"><span data-stu-id="360b1-417">Additional resources</span></span>


[<span data-ttu-id="360b1-418">使用 App-V 部署 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="360b1-418">Deploying Microsoft Office 2013 by Using App-V</span></span>](deploying-microsoft-office-2013-by-using-app-v.md)

[<span data-ttu-id="360b1-419">使用 App-V 部署 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="360b1-419">Deploying Microsoft Office 2010 by Using App-V</span></span>](deploying-microsoft-office-2010-by-using-app-v.md)

[<span data-ttu-id="360b1-420">「隨選即用」的 Office 2016 部署工具</span><span class="sxs-lookup"><span data-stu-id="360b1-420">Office 2016 Deployment Tool for Click-to-Run</span></span>](https://www.microsoft.com/download/details.aspx?id=49117)

**<span data-ttu-id="360b1-421">連線群組</span><span class="sxs-lookup"><span data-stu-id="360b1-421">Connection Groups</span></span>**

[<span data-ttu-id="360b1-422">在 Microsoft App 中部署連線群組-V v5</span><span class="sxs-lookup"><span data-stu-id="360b1-422">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="360b1-423">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="360b1-423">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="360b1-424">動態設定</span><span class="sxs-lookup"><span data-stu-id="360b1-424">Dynamic Configuration</span></span>**

[<span data-ttu-id="360b1-425">關於 App-V 5.1 動態組態</span><span class="sxs-lookup"><span data-stu-id="360b1-425">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)





