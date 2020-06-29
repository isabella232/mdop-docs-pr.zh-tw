---
title: 使用 PowerShell 管理 App-V
description: 使用 PowerShell 管理 App-V
author: dansimp
ms.assetid: 1ff4686a-1e19-4eff-b648-ada091281094
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e7f9171e0ac5589d8f1935e715dfdb9c349192d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800699"
---
# <span data-ttu-id="cf9a2-103">使用 PowerShell 管理 App-V</span><span class="sxs-lookup"><span data-stu-id="cf9a2-103">Administering App-V by Using PowerShell</span></span>


<span data-ttu-id="cf9a2-104">Microsoft Application Virtualization （App-v）5.0 提供 Windows PowerShell Cmdlet，可協助系統管理員執行各種應用程式 V 5.0 任務。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-104">Microsoft Application Virtualization (App-V) 5.0 provides Windows PowerShell cmdlets, which can help administrators perform various App-V 5.0 tasks.</span></span> <span data-ttu-id="cf9a2-105">下列各節提供在 App-v 5.0 中使用 PowerShell 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-105">The following sections provide more information about using PowerShell with App-V 5.0.</span></span>

## <span data-ttu-id="cf9a2-106">如何使用 PowerShell 管理 App-v 5。0</span><span class="sxs-lookup"><span data-stu-id="cf9a2-106">How to administer App-V 5.0 by using PowerShell</span></span>


<span data-ttu-id="cf9a2-107">使用下列 PowerShell 程式來執行各種應用程式 V 5.0 任務。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-107">Use the following PowerShell procedures to perform various App-V 5.0 tasks.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cf9a2-108">名稱</span><span class="sxs-lookup"><span data-stu-id="cf9a2-108">Name</span></span></th>
<th align="left"><span data-ttu-id="cf9a2-109">描述</span><span class="sxs-lookup"><span data-stu-id="cf9a2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)"><span data-ttu-id="cf9a2-110">如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="cf9a2-110">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-111">說明如何安裝 PowerShell Cmdlet 及尋找 Cmdlet 說明和範例。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-111">Describes how to install the PowerShell cmdlets and find cmdlet help and examples.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="cf9a2-112">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="cf9a2-112">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-113">說明如何使用 PowerShell 在獨立電腦上管理用戶端套件生命週期。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-113">Describes how to manage the client package lifecycle on a stand-alone computer using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="cf9a2-114">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="cf9a2-114">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-115">說明如何使用 PowerShell 管理連線群組。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-115">Describes how to manage connection groups using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md)"><span data-ttu-id="cf9a2-116">如何使用 PowerShell 來修改用戶端組態</span><span class="sxs-lookup"><span data-stu-id="cf9a2-116">How to Modify Client Configuration by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-117">說明如何使用 PowerShell 修改用戶端。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-117">Describes how to modify the client using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell.md)"><span data-ttu-id="cf9a2-118">如何使用 PowerShell 來套用使用者設定檔案</span><span class="sxs-lookup"><span data-stu-id="cf9a2-118">How to Apply the User Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-119">說明如何使用 PowerShell 來套用使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-119">Describes how to apply a user configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)"><span data-ttu-id="cf9a2-120">如何使用 PowerShell 來套用部署設定檔案</span><span class="sxs-lookup"><span data-stu-id="cf9a2-120">How to Apply the Deployment Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-121">說明如何使用 PowerShell 來套用部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-121">Describes how to apply a deployment configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-50.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-50.md)"><span data-ttu-id="cf9a2-122">如何使用 PowerShell 對套件進行排序</span><span class="sxs-lookup"><span data-stu-id="cf9a2-122">How to Sequence a Package by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-123">說明如何使用 PowerShell 建立新的套件。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-123">Describes how to create a new package using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md)"><span data-ttu-id="cf9a2-124">如何使用 PowerShell 來建立封裝加速器</span><span class="sxs-lookup"><span data-stu-id="cf9a2-124">How to Create a Package Accelerator by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-125">說明如何使用 PowerShell 建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-125">Describes how to create a package accelerator using PowerShell.</span></span> <span data-ttu-id="cf9a2-126">您可以使用套件加速器自動序列化大型、複雜的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-126">You can use package accelerators automatically sequence large, complex applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)"><span data-ttu-id="cf9a2-127">如何使用 PowerShell 在 App-V 5.0 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="cf9a2-127">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-128">說明如何啟用執行 App-v 5.0 的電腦來傳送報告資訊。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-128">Describes how to enable the computer running the App-V 5.0 to send reporting information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)"><span data-ttu-id="cf9a2-129">如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="cf9a2-129">How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-130">說明如何取得帳戶名稱陣列，並將每個帳戶名稱轉換成標準及十六進位格式的對應 SID。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-130">Describes how to take an array of account names and to convert each of them to the corresponding SID in standard and hexadecimal formats.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="cf9a2-131">PowerShell 錯誤處理</span><span class="sxs-lookup"><span data-stu-id="cf9a2-131">PowerShell Error Handling</span></span>


<span data-ttu-id="cf9a2-132">請參閱下表以取得 App-v 5.0 PowerShell 錯誤處理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cf9a2-132">Use the following table for information about App-V 5.0 PowerShell error handling.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cf9a2-133">事件</span><span class="sxs-lookup"><span data-stu-id="cf9a2-133">Event</span></span></th>
<th align="left"><span data-ttu-id="cf9a2-134">動作</span><span class="sxs-lookup"><span data-stu-id="cf9a2-134">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf9a2-135">在內嵌腳本中使用 RollbackOnError 屬性</span><span class="sxs-lookup"><span data-stu-id="cf9a2-135">Using the RollbackOnError attribute with embedded scripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-136">當您將 <strong> RollbackOnError </strong> 屬性與內嵌腳本搭配使用時，系統會忽略下列事件的屬性：</span><span class="sxs-lookup"><span data-stu-id="cf9a2-136">When you use the <strong>RollbackOnError</strong> attribute with embedded scripts, the attribute is ignored for the following events:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf9a2-137">移除套件</span><span class="sxs-lookup"><span data-stu-id="cf9a2-137">Removing a package</span></span></p></li>
<li><p><span data-ttu-id="cf9a2-138">取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="cf9a2-138">Unpublishing a package</span></span></p></li>
<li><p><span data-ttu-id="cf9a2-139">終止虛擬環境</span><span class="sxs-lookup"><span data-stu-id="cf9a2-139">Terminating a virtual environment</span></span></p></li>
<li><p><span data-ttu-id="cf9a2-140">終止進程</span><span class="sxs-lookup"><span data-stu-id="cf9a2-140">Terminating a process</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cf9a2-141">套件名稱包含<strong>$</span><span class="sxs-lookup"><span data-stu-id="cf9a2-141">Package name contains <strong>$</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="cf9a2-142">如果套件名稱包含字元（ <strong> $ </strong> ），則必須使用單引號（ <strong> ' </strong> ），例如</span><span class="sxs-lookup"><span data-stu-id="cf9a2-142">If a package name contains the character ( <strong>$</strong> ), you must use a single-quote ( <strong>‘</strong> ), for example,</span></span></p>
<p><strong><span data-ttu-id="cf9a2-143">AppvClientPackage "Contoso $ App. appv"</span><span class="sxs-lookup"><span data-stu-id="cf9a2-143">Add-AppvClientPackage ‘Contoso$App.appv’</span></span></strong></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="cf9a2-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="cf9a2-144">Related topics</span></span>


[<span data-ttu-id="cf9a2-145">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="cf9a2-145">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





