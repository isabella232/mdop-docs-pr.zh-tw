---
title: App-V 封裝 WMI 類別
description: App-V 封裝 WMI 類別
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802361"
---
# <span data-ttu-id="f13ae-103">App-V 封裝 WMI 類別</span><span class="sxs-lookup"><span data-stu-id="f13ae-103">App-V Package WMI Class</span></span>


<span data-ttu-id="f13ae-104">在應用程式虛擬化（App-v）用戶端中， **Package**類別是代表用戶端上所有虛擬套件的 Windows 管理規範（WMI）類別。</span><span class="sxs-lookup"><span data-stu-id="f13ae-104">In the Application Virtualization (App-V) Client, the **Package** class is a Windows Management Instrumentation (WMI) class that represents all the virtual packages on the client.</span></span> <span data-ttu-id="f13ae-105">虛擬套件可以包含許多虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="f13ae-105">The virtual packages can contain many virtual applications.</span></span>

## <span data-ttu-id="f13ae-106">語法</span><span class="sxs-lookup"><span data-stu-id="f13ae-106">Syntax</span></span>


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## <span data-ttu-id="f13ae-107">屬性</span><span class="sxs-lookup"><span data-stu-id="f13ae-107">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="f13ae-108">名稱</span><span class="sxs-lookup"><span data-stu-id="f13ae-108">Name</span></span>**  
<span data-ttu-id="f13ae-109">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="f13ae-109">Data type: **String**</span></span>

<span data-ttu-id="f13ae-110">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-110">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-111">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-111">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-112">虛擬套件的方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="f13ae-112">The user-friendly name of the virtual package.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="f13ae-113">版本</span><span class="sxs-lookup"><span data-stu-id="f13ae-113">Version</span></span>**  
<span data-ttu-id="f13ae-114">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="f13ae-114">Data type: **String**</span></span>

<span data-ttu-id="f13ae-115">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-115">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-116">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-116">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-117">虛擬套件的版本。</span><span class="sxs-lookup"><span data-stu-id="f13ae-117">The version of the virtual package.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="f13ae-118">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="f13ae-118">PackageGUID</span></span>**  
<span data-ttu-id="f13ae-119">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="f13ae-119">Data type: **String**</span></span>

<span data-ttu-id="f13ae-120">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-120">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-121">限定詞：金鑰</span><span class="sxs-lookup"><span data-stu-id="f13ae-121">Qualifiers: Key</span></span>

<span data-ttu-id="f13ae-122">套件配置和來源檔案的 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="f13ae-122">The GUID identifier of the package configuration and source files.</span></span>

<a href="" id="sftpath"></a>**<span data-ttu-id="f13ae-123">SftPath</span><span class="sxs-lookup"><span data-stu-id="f13ae-123">SftPath</span></span>**  
<span data-ttu-id="f13ae-124">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="f13ae-124">Data type: **String**</span></span>

<span data-ttu-id="f13ae-125">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-125">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-126">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-126">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-127">SFT 檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="f13ae-127">The file path of the SFT file.</span></span>

<a href="" id="totalsize"></a>**<span data-ttu-id="f13ae-128">TotalSize</span><span class="sxs-lookup"><span data-stu-id="f13ae-128">TotalSize</span></span>**  
<span data-ttu-id="f13ae-129">資料類型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="f13ae-129">Data type: **UInt64**</span></span>

<span data-ttu-id="f13ae-130">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-130">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-131">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-131">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-132">虛擬套件的總大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="f13ae-132">The total size of the virtual package, in kilobytes.</span></span>

<a href="" id="cachedsize"></a>**<span data-ttu-id="f13ae-133">CachedSize</span><span class="sxs-lookup"><span data-stu-id="f13ae-133">CachedSize</span></span>**  
<span data-ttu-id="f13ae-134">資料類型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="f13ae-134">Data type: **UInt64**</span></span>

<span data-ttu-id="f13ae-135">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-135">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-136">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-136">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-137">虛擬套件的快取總大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="f13ae-137">The total size of the cache for the virtual package, in kilobytes.</span></span>

<a href="" id="launchsize"></a>**<span data-ttu-id="f13ae-138">LaunchSize</span><span class="sxs-lookup"><span data-stu-id="f13ae-138">LaunchSize</span></span>**  
<span data-ttu-id="f13ae-139">資料類型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="f13ae-139">Data type: **UInt64**</span></span>

<span data-ttu-id="f13ae-140">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-140">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-141">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-141">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-142">虛擬套件主要功能區塊的總大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="f13ae-142">The total size of the virtual package’s primary feature block, in kilobytes.</span></span>

<a href="" id="cachedlaunchsize"></a>**<span data-ttu-id="f13ae-143">CachedLaunchSize</span><span class="sxs-lookup"><span data-stu-id="f13ae-143">CachedLaunchSize</span></span>**  
<span data-ttu-id="f13ae-144">資料類型： **UInt64**</span><span class="sxs-lookup"><span data-stu-id="f13ae-144">Data type: **UInt64**</span></span>

<span data-ttu-id="f13ae-145">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-145">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-146">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-146">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-147">已快取的虛擬套件主要功能區塊總大小（以 kb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="f13ae-147">Total size of the virtual package’s primary feature block that has been cached, in kilobytes.</span></span>

<a href="" id="inuse"></a>**<span data-ttu-id="f13ae-148">InUse</span><span class="sxs-lookup"><span data-stu-id="f13ae-148">InUse</span></span>**  
<span data-ttu-id="f13ae-149">資料類型：**布林值**</span><span class="sxs-lookup"><span data-stu-id="f13ae-149">Data type: **Boolean**</span></span>

<span data-ttu-id="f13ae-150">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-150">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-151">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-151">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-152">如果虛擬套件中的任何虛擬應用程式正在執行，**則為 true** ;否則**為 false**。</span><span class="sxs-lookup"><span data-stu-id="f13ae-152">**true** if any virtual application in the virtual package is running; otherwise **false**.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="f13ae-153">已鎖定</span><span class="sxs-lookup"><span data-stu-id="f13ae-153">Locked</span></span>**  
<span data-ttu-id="f13ae-154">資料類型：**布林值**</span><span class="sxs-lookup"><span data-stu-id="f13ae-154">Data type: **Boolean**</span></span>

<span data-ttu-id="f13ae-155">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-155">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-156">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-156">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-157">如果虛擬套件已鎖定，**則為 true** ;否則**為 false**。</span><span class="sxs-lookup"><span data-stu-id="f13ae-157">**true** if the virtual package is locked; otherwise **false**.</span></span>

<a href="" id="cachedpercentage"></a>**<span data-ttu-id="f13ae-158">CachedPercentage</span><span class="sxs-lookup"><span data-stu-id="f13ae-158">CachedPercentage</span></span>**  
<span data-ttu-id="f13ae-159">資料類型： **UInt16**</span><span class="sxs-lookup"><span data-stu-id="f13ae-159">Data type: **UInt16**</span></span>

<span data-ttu-id="f13ae-160">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-160">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-161">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-161">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-162">快取檔案的百分比。</span><span class="sxs-lookup"><span data-stu-id="f13ae-162">The percentage of the cache files.</span></span> <span data-ttu-id="f13ae-163">根據下列公式： CachedSize/TotalSize ×100。</span><span class="sxs-lookup"><span data-stu-id="f13ae-163">Based on the following formula: CachedSize / TotalSize × 100.</span></span>

<a href="" id="versionguid"></a>**<span data-ttu-id="f13ae-164">VersionGUID</span><span class="sxs-lookup"><span data-stu-id="f13ae-164">VersionGUID</span></span>**  
<span data-ttu-id="f13ae-165">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="f13ae-165">Data type: **String**</span></span>

<span data-ttu-id="f13ae-166">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="f13ae-166">Access type: Read-only</span></span>

<span data-ttu-id="f13ae-167">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="f13ae-167">Qualifiers: None</span></span>

<span data-ttu-id="f13ae-168">套件版本的 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="f13ae-168">The GUID identifier of the package version.</span></span>

 

 





