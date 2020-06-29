---
title: 使用 PowerShell 管理 App-V 5.1
description: 使用 PowerShell 管理 App-V 5.1
author: dansimp
ms.assetid: 9e10ff07-2cd9-4dc1-9e99-582f90c36081
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0c64d7e0330ff5d737dfa02d87f156cc3236b04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800702"
---
# <span data-ttu-id="e44c8-103">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="e44c8-103">Administering App-V 5.1 by Using PowerShell</span></span>


<span data-ttu-id="e44c8-104">Microsoft Application Virtualization （App-v）5.1 提供 Windows PowerShell Cmdlet，可協助系統管理員執行各種應用程式 V 5.1 任務。</span><span class="sxs-lookup"><span data-stu-id="e44c8-104">Microsoft Application Virtualization (App-V) 5.1 provides Windows PowerShell cmdlets, which can help administrators perform various App-V 5.1 tasks.</span></span> <span data-ttu-id="e44c8-105">下列各節提供在 App-v 5.1 中使用 PowerShell 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e44c8-105">The following sections provide more information about using PowerShell with App-V 5.1.</span></span>

## <span data-ttu-id="e44c8-106">如何使用 PowerShell 管理 App-v 5。1</span><span class="sxs-lookup"><span data-stu-id="e44c8-106">How to administer App-V 5.1 by using PowerShell</span></span>


<span data-ttu-id="e44c8-107">使用下列 PowerShell 程式來執行各種應用程式 V 5.1 任務。</span><span class="sxs-lookup"><span data-stu-id="e44c8-107">Use the following PowerShell procedures to perform various App-V 5.1 tasks.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e44c8-108">名稱</span><span class="sxs-lookup"><span data-stu-id="e44c8-108">Name</span></span></th>
<th align="left"><span data-ttu-id="e44c8-109">描述</span><span class="sxs-lookup"><span data-stu-id="e44c8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)"><span data-ttu-id="e44c8-110">如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="e44c8-110">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-111">說明如何安裝 PowerShell Cmdlet 及尋找 Cmdlet 說明和範例。</span><span class="sxs-lookup"><span data-stu-id="e44c8-111">Describes how to install the PowerShell cmdlets and find cmdlet help and examples.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="e44c8-112">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="e44c8-112">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-113">說明如何使用 PowerShell 在獨立電腦上管理用戶端套件生命週期。</span><span class="sxs-lookup"><span data-stu-id="e44c8-113">Describes how to manage the client package lifecycle on a stand-alone computer using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)"><span data-ttu-id="e44c8-114">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="e44c8-114">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-115">說明如何使用 PowerShell 管理連線群組。</span><span class="sxs-lookup"><span data-stu-id="e44c8-115">Describes how to manage connection groups using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell51.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell51.md)"><span data-ttu-id="e44c8-116">如何使用 PowerShell 來修改用戶端組態</span><span class="sxs-lookup"><span data-stu-id="e44c8-116">How to Modify Client Configuration by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-117">說明如何使用 PowerShell 修改用戶端。</span><span class="sxs-lookup"><span data-stu-id="e44c8-117">Describes how to modify the client using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell51.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell51.md)"><span data-ttu-id="e44c8-118">如何使用 PowerShell 來套用使用者設定檔案</span><span class="sxs-lookup"><span data-stu-id="e44c8-118">How to Apply the User Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-119">說明如何使用 PowerShell 來套用使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="e44c8-119">Describes how to apply a user configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell51.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)"><span data-ttu-id="e44c8-120">如何使用 PowerShell 來套用部署設定檔案</span><span class="sxs-lookup"><span data-stu-id="e44c8-120">How to Apply the Deployment Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-121">說明如何使用 PowerShell 來套用部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="e44c8-121">Describes how to apply a deployment configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-51.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-51.md)"><span data-ttu-id="e44c8-122">如何使用 PowerShell 對套件進行排序</span><span class="sxs-lookup"><span data-stu-id="e44c8-122">How to Sequence a Package by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-123">說明如何使用 PowerShell 建立新的套件。</span><span class="sxs-lookup"><span data-stu-id="e44c8-123">Describes how to create a new package using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell51.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell51.md)"><span data-ttu-id="e44c8-124">如何使用 PowerShell 來建立封裝加速器</span><span class="sxs-lookup"><span data-stu-id="e44c8-124">How to Create a Package Accelerator by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-125">說明如何使用 PowerShell 建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="e44c8-125">Describes how to create a package accelerator using PowerShell.</span></span> <span data-ttu-id="e44c8-126">您可以使用套件加速器自動序列化大型、複雜的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e44c8-126">You can use package accelerators automatically sequence large, complex applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.1 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)"><span data-ttu-id="e44c8-127">如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="e44c8-127">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-128">說明如何啟用執行 App-v 5.1 的電腦來傳送報告資訊。</span><span class="sxs-lookup"><span data-stu-id="e44c8-128">Describes how to enable the computer running the App-V 5.1 to send reporting information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)"><span data-ttu-id="e44c8-129">如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="e44c8-129">How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e44c8-130">說明如何取得帳戶名稱陣列，並將每個帳戶名稱轉換成標準及十六進位格式的對應 SID。</span><span class="sxs-lookup"><span data-stu-id="e44c8-130">Describes how to take an array of account names and to convert each of them to the corresponding SID in standard and hexadecimal formats.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e44c8-131">**重要** 請確定您使用 App-v 套件執行的任何腳本都符合您針對 PowerShell 設定的執行原則。</span><span class="sxs-lookup"><span data-stu-id="e44c8-131">**Important** Make sure that any script you execute with your App-V packages matches the execution policy that you have configured for PowerShell.</span></span>

 

## <span data-ttu-id="e44c8-132">PowerShell 錯誤處理</span><span class="sxs-lookup"><span data-stu-id="e44c8-132">PowerShell Error Handling</span></span>


<span data-ttu-id="e44c8-133">請參閱下表以取得 App-v 5.1 PowerShell 錯誤處理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e44c8-133">Use the following table for information about App-V 5.1 PowerShell error handling.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e44c8-134">事件</span><span class="sxs-lookup"><span data-stu-id="e44c8-134">Event</span></span></th>
<th align="left"><span data-ttu-id="e44c8-135">動作</span><span class="sxs-lookup"><span data-stu-id="e44c8-135">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e44c8-136">在內嵌腳本中使用 RollbackOnError 屬性</span><span class="sxs-lookup"><span data-stu-id="e44c8-136">Using the RollbackOnError attribute with embedded scripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="e44c8-137">當您將 <strong> RollbackOnError </strong> 屬性與內嵌腳本搭配使用時，系統會忽略下列事件的屬性：</span><span class="sxs-lookup"><span data-stu-id="e44c8-137">When you use the <strong>RollbackOnError</strong> attribute with embedded scripts, the attribute is ignored for the following events:</span></span></p>
<ul>
<li><p><span data-ttu-id="e44c8-138">移除套件</span><span class="sxs-lookup"><span data-stu-id="e44c8-138">Removing a package</span></span></p></li>
<li><p><span data-ttu-id="e44c8-139">取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="e44c8-139">Unpublishing a package</span></span></p></li>
<li><p><span data-ttu-id="e44c8-140">終止虛擬環境</span><span class="sxs-lookup"><span data-stu-id="e44c8-140">Terminating a virtual environment</span></span></p></li>
<li><p><span data-ttu-id="e44c8-141">終止進程</span><span class="sxs-lookup"><span data-stu-id="e44c8-141">Terminating a process</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e44c8-142">套件名稱包含<strong>$</span><span class="sxs-lookup"><span data-stu-id="e44c8-142">Package name contains <strong>$</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e44c8-143">如果套件名稱包含字元（ <strong> $ </strong> ），則必須使用單引號（ <strong> ' </strong> ），例如</span><span class="sxs-lookup"><span data-stu-id="e44c8-143">If a package name contains the character ( <strong>$</strong> ), you must use a single-quote ( <strong>‘</strong> ), for example,</span></span></p>
<p><strong><span data-ttu-id="e44c8-144">AppvClientPackage "Contoso $ App. appv"</span><span class="sxs-lookup"><span data-stu-id="e44c8-144">Add-AppvClientPackage ‘Contoso$App.appv’</span></span></strong></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="e44c8-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="e44c8-145">Related topics</span></span>


[<span data-ttu-id="e44c8-146">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="e44c8-146">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





