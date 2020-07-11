---
title: App-V 應用程式 WMI 類別
description: App-V 應用程式 WMI 類別
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809285"
---
# <span data-ttu-id="c662f-103">App-V 應用程式 WMI 類別</span><span class="sxs-lookup"><span data-stu-id="c662f-103">App-V Application WMI Class</span></span>


<span data-ttu-id="c662f-104">在應用程式虛擬化 (App-v) 用戶端中，**應用程式**類別是 Windows 管理規範 (WMI) 類別，代表用戶端上的所有虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="c662f-104">In the Application Virtualization (App-V) Client, the **Application** class is a Windows Management Instrumentation (WMI) class that represents all the virtual applications on the client.</span></span>

<span data-ttu-id="c662f-105">您可從 (MOF) 程式碼的 Managed 物件格式簡化下列語法。</span><span class="sxs-lookup"><span data-stu-id="c662f-105">The following syntax is simplified from Managed Object Format (MOF) code.</span></span> <span data-ttu-id="c662f-106">程式碼包含所有繼承的屬性。</span><span class="sxs-lookup"><span data-stu-id="c662f-106">The code includes all the inherited properties.</span></span>

## <span data-ttu-id="c662f-107">語法</span><span class="sxs-lookup"><span data-stu-id="c662f-107">Syntax</span></span>


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## <span data-ttu-id="c662f-108">需求</span><span class="sxs-lookup"><span data-stu-id="c662f-108">Requirements</span></span>


## <span data-ttu-id="c662f-109">屬性</span><span class="sxs-lookup"><span data-stu-id="c662f-109">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="c662f-110">名稱</span><span class="sxs-lookup"><span data-stu-id="c662f-110">Name</span></span>**  
<span data-ttu-id="c662f-111">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="c662f-111">Data type: **String**</span></span>

<span data-ttu-id="c662f-112">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-112">Access type: Read-only</span></span>

<span data-ttu-id="c662f-113">限定詞：金鑰</span><span class="sxs-lookup"><span data-stu-id="c662f-113">Qualifiers: Key</span></span>

<span data-ttu-id="c662f-114">虛擬應用程式的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="c662f-114">The display name of the virtual application.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="c662f-115">版本</span><span class="sxs-lookup"><span data-stu-id="c662f-115">Version</span></span>**  
<span data-ttu-id="c662f-116">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="c662f-116">Data type: **String**</span></span>

<span data-ttu-id="c662f-117">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-117">Access type: Read-only</span></span>

<span data-ttu-id="c662f-118">限定詞：金鑰</span><span class="sxs-lookup"><span data-stu-id="c662f-118">Qualifiers: Key</span></span>

<span data-ttu-id="c662f-119">虛擬應用程式的版本。</span><span class="sxs-lookup"><span data-stu-id="c662f-119">The version of the virtual application.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="c662f-120">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="c662f-120">PackageGUID</span></span>**  
<span data-ttu-id="c662f-121">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="c662f-121">Data type: **String**</span></span>

<span data-ttu-id="c662f-122">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-122">Access type: Read-only</span></span>

<span data-ttu-id="c662f-123">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-123">Qualifiers: None</span></span>

<span data-ttu-id="c662f-124">與虛擬應用程式相關聯之套件的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c662f-124">The GUID of the package that the virtual application is associated with.</span></span>

<a href="" id="lastlaunchonsystem"></a>**<span data-ttu-id="c662f-125">LastLaunchOnSystem</span><span class="sxs-lookup"><span data-stu-id="c662f-125">LastLaunchOnSystem</span></span>**  
<span data-ttu-id="c662f-126">資料類型： **DateTime**</span><span class="sxs-lookup"><span data-stu-id="c662f-126">Data type: **DateTime**</span></span>

<span data-ttu-id="c662f-127">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-127">Access type: Read-only</span></span>

<span data-ttu-id="c662f-128">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-128">Qualifiers: None</span></span>

<span data-ttu-id="c662f-129">啟動虛擬應用程式的最後日期和時間。</span><span class="sxs-lookup"><span data-stu-id="c662f-129">The last date and time that the virtual application was launched.</span></span>

<a href="" id="globalrunningcount"></a>**<span data-ttu-id="c662f-130">GlobalRunningCount</span><span class="sxs-lookup"><span data-stu-id="c662f-130">GlobalRunningCount</span></span>**  
<span data-ttu-id="c662f-131">資料類型： **UInt32**</span><span class="sxs-lookup"><span data-stu-id="c662f-131">Data type: **UInt32**</span></span>

<span data-ttu-id="c662f-132">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-132">Access type: Read-only</span></span>

<span data-ttu-id="c662f-133">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-133">Qualifiers: None</span></span>

<span data-ttu-id="c662f-134">直接啟動之虛擬應用程式的執行實例數。</span><span class="sxs-lookup"><span data-stu-id="c662f-134">A count of the running instances of the virtual application that were started directly.</span></span>

<a href="" id="loading"></a>**<span data-ttu-id="c662f-135">正在載入</span><span class="sxs-lookup"><span data-stu-id="c662f-135">Loading</span></span>**  
<span data-ttu-id="c662f-136">資料類型：**布林值**</span><span class="sxs-lookup"><span data-stu-id="c662f-136">Data type: **Boolean**</span></span>

<span data-ttu-id="c662f-137">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-137">Access type: Read-only</span></span>

<span data-ttu-id="c662f-138">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-138">Qualifiers: None</span></span>

<span data-ttu-id="c662f-139">如果正在啟動虛擬應用程式，**則為 true** ;否則**為 false**。</span><span class="sxs-lookup"><span data-stu-id="c662f-139">**true** if the virtual application is being started; otherwise **false**.</span></span>

<a href="" id="originalosdpath"></a>**<span data-ttu-id="c662f-140">OriginalOsdPath</span><span class="sxs-lookup"><span data-stu-id="c662f-140">OriginalOsdPath</span></span>**  
<span data-ttu-id="c662f-141">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="c662f-141">Data type: **String**</span></span>

<span data-ttu-id="c662f-142">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-142">Access type: Read-only</span></span>

<span data-ttu-id="c662f-143">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-143">Qualifiers: None</span></span>

<span data-ttu-id="c662f-144">在 App-V 用戶端註冊之 OSD 檔案的原始檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="c662f-144">The original file path of the OSD file that was registered with the App-V Client.</span></span>

<a href="" id="cachedosdpath"></a>**<span data-ttu-id="c662f-145">CachedOsdPath</span><span class="sxs-lookup"><span data-stu-id="c662f-145">CachedOsdPath</span></span>**  
<span data-ttu-id="c662f-146">資料類型：**字串**</span><span class="sxs-lookup"><span data-stu-id="c662f-146">Data type: **String**</span></span>

<span data-ttu-id="c662f-147">Access 類型：唯讀</span><span class="sxs-lookup"><span data-stu-id="c662f-147">Access type: Read-only</span></span>

<span data-ttu-id="c662f-148">限定詞：無</span><span class="sxs-lookup"><span data-stu-id="c662f-148">Qualifiers: None</span></span>

<span data-ttu-id="c662f-149">如果 App-v 檔案已在本機緩存 OSD 檔案，則為 OSD 檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="c662f-149">The file path of the OSD file if the App-V Client has cached the OSD file locally.</span></span>

 

 





