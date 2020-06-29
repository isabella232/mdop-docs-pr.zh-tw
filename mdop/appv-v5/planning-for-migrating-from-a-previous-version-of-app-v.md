---
title: 規劃從舊版 App-V 移轉
description: 規劃從舊版 App-V 移轉
author: dansimp
ms.assetid: d4ca8f09-86fd-456f-8ec2-242ff94ae9a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2242f58a29473e116506ec013b94a79d1bb814a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800352"
---
# <span data-ttu-id="b4110-103">規劃從舊版 App-V 移轉</span><span class="sxs-lookup"><span data-stu-id="b4110-103">Planning for Migrating from a Previous Version of App-V</span></span>


<span data-ttu-id="b4110-104">您可以使用下列資訊來規劃如何從舊版 App-v 升級到 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="b4110-104">Use the following information to plan how to migrate to App-V 5.0 from previous versions of App-V.</span></span>

## <span data-ttu-id="b4110-105">遷移需求</span><span class="sxs-lookup"><span data-stu-id="b4110-105">Migration requirements</span></span>


<span data-ttu-id="b4110-106">開始進行任何升級前，請先檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="b4110-106">Before you start any upgrades, review the following requirements:</span></span>

-   <span data-ttu-id="b4110-107">如果您要從 App-v 4.6 SP2 之前的版本進行升級，請先升級到版本 App-V 4.6 SP3，再升級到 App-v 5.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b4110-107">If you are upgrading from a version earlier than App-V 4.6 SP2, upgrade to version App-V 4.6 SP3 first before upgrading to App-V 5.0 or later.</span></span> <span data-ttu-id="b4110-108">在這種情況下，請先升級 App-v 用戶端，然後再升級伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="b4110-108">In this scenario, upgrade the App-V clients first, and then upgrade the server components.</span></span>
<span data-ttu-id="b4110-109">**注意：** App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="b4110-109">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

-   <span data-ttu-id="b4110-110">App-v 5.0 只支援使用 App-v 5.0 建立的套件，或已轉換成 App-v 5.0 （**appv**）格式的套件。</span><span class="sxs-lookup"><span data-stu-id="b4110-110">App-V 5.0 supports only packages that are created using App-V 5.0, or packages that have been converted to the App-V 5.0 (**.appv**) format.</span></span>

-   <span data-ttu-id="b4110-111">僅限 app-V 5.0 SP3：如果您要從 App-v 5.0 SP1 升級 app-v Server，請參閱[關於 app-v 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3) ，以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="b4110-111">App-V 5.0 SP3 only: If you are upgrading the App-V Server from App-V 5.0 SP1, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3) for instructions.</span></span>

## <span data-ttu-id="b4110-112">同時執行 App-v 5.0 用戶端與 app-v 4。6</span><span class="sxs-lookup"><span data-stu-id="b4110-112">Running the App-V 5.0 client concurrently with App-V 4.6</span></span>


<span data-ttu-id="b4110-113">您可以在使用 App-v 4.6 SP3 用戶端的同一台電腦上同時執行 App-v 5.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4110-113">You can run the App-V 5.0 client concurrently on the same computer with the App-V4.6SP3 client.</span></span>

<span data-ttu-id="b4110-114">當您執行共存的 App-v 用戶端時，您可以：</span><span class="sxs-lookup"><span data-stu-id="b4110-114">When you run coexisting App-V clients, you can:</span></span>

-   <span data-ttu-id="b4110-115">當您同時執行兩個用戶端時，請將 App-v 4.6 SP3 套件轉換成 App-v 5.0 格式，併發布這兩個套件。</span><span class="sxs-lookup"><span data-stu-id="b4110-115">Convert an App-V 4.6 SP3 package to the App-V 5.0 format and publish both packages, when you have both clients running.</span></span>

-   <span data-ttu-id="b4110-116">針對已轉換的套件定義遷移原則，以允許已轉換的 app-v 5.0 套件假設來自 App-v 4.6 套件的檔案類型關聯和快速鍵。</span><span class="sxs-lookup"><span data-stu-id="b4110-116">Define the migration policy for the converted package, which allows the converted App-V 5.0 package to assume the file type associations and shortcuts from the App-V 4.6 package.</span></span>

### <span data-ttu-id="b4110-117">支援的共存案例</span><span class="sxs-lookup"><span data-stu-id="b4110-117">Supported coexistence scenarios</span></span>

<span data-ttu-id="b4110-118">下表顯示受支援的 App-v 共存案例。</span><span class="sxs-lookup"><span data-stu-id="b4110-118">The following table shows the supported App-V coexistence scenarios.</span></span> <span data-ttu-id="b4110-119">我們建議您在執行共存的用戶端時，安裝特定發行的最新可用更新。</span><span class="sxs-lookup"><span data-stu-id="b4110-119">We recommend that you install the latest available updates of a given release when you are running coexisting clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b4110-120">App-v 4.6 用戶端類型</span><span class="sxs-lookup"><span data-stu-id="b4110-120">App-V 4.6 client type</span></span></th>
<th align="left"><span data-ttu-id="b4110-121">App-v 5.0 用戶端類型</span><span class="sxs-lookup"><span data-stu-id="b4110-121">App-V 5.0 client type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b4110-122">App-V 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="b4110-122">App-V 4.6 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="b4110-123">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="b4110-123">App-V 5.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b4110-124">App-V 4.6 SP3 RDS</span><span class="sxs-lookup"><span data-stu-id="b4110-124">App-V 4.6 SP3 RDS</span></span></p></td>
<td align="left"><p><span data-ttu-id="b4110-125">App-v 5.0 RDS</span><span class="sxs-lookup"><span data-stu-id="b4110-125">App-V 5.0 RDS</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b4110-126">運行共存用戶端的需求</span><span class="sxs-lookup"><span data-stu-id="b4110-126">Requirements for running coexisting clients</span></span>

<span data-ttu-id="b4110-127">若要執行共存的用戶端，您必須：</span><span class="sxs-lookup"><span data-stu-id="b4110-127">To run coexisting clients, you must:</span></span>

-   <span data-ttu-id="b4110-128">安裝 App-v 4.6 用戶端，然後再安裝應用程式-V 5.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4110-128">Install the App-V4.6 client before you install the App-V 5.0 client.</span></span>

-   <span data-ttu-id="b4110-129">啟用**App-V**用戶端共存節點中的 [**啟用移轉模式]** 群組原則設定 &gt; **Client Coexistence** 。</span><span class="sxs-lookup"><span data-stu-id="b4110-129">Enable the **Enable Migration Mode** Group Policy setting, which is in the **App-V** &gt; **Client Coexistence** node.</span></span> <span data-ttu-id="b4110-130">若要取得 .deploy 範本的部署，請參閱[如何下載和部署 MDOP 組原則（admx）範本](https://technet.microsoft.com/library/dn659707.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b4110-130">To get the deploy the .admx template, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

### <span data-ttu-id="b4110-131">用戶端下載和檔</span><span class="sxs-lookup"><span data-stu-id="b4110-131">Client downloads and documentation</span></span>

<span data-ttu-id="b4110-132">下表提供有關發行版本 TechNet 檔的連結。</span><span class="sxs-lookup"><span data-stu-id="b4110-132">The following table provides link to the TechNet documentation about the releases.</span></span> <span data-ttu-id="b4110-133">除非另行說明，否則應用程式-V 用戶端的 TechNet 檔會套用至這兩個用戶端。</span><span class="sxs-lookup"><span data-stu-id="b4110-133">The TechNet documentation about the App-V client applies to both clients, unless stated otherwise.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b4110-134">App-V 版本</span><span class="sxs-lookup"><span data-stu-id="b4110-134">App-V version</span></span></th>
<th align="left"><span data-ttu-id="b4110-135">連結至 TechNet 檔</span><span class="sxs-lookup"><span data-stu-id="b4110-135">Link to TechNet documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b4110-136">App-V 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="b4110-136">App-V 4.6SP3</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)"><span data-ttu-id="b4110-137">關於 Microsoft Application Virtualization 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="b4110-137">About Microsoft Application Virtualization 4.6 SP3</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b4110-138">App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="b4110-138">App-V 5.0SP3</span></span></p></td>
<td align="left"><p><a href="about-app-v-50-sp3.md" data-raw-source="[About Microsoft Application Virtualization 5.0 SP3](about-app-v-50-sp3.md)"><span data-ttu-id="b4110-139">關於 Microsoft Application Virtualization 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="b4110-139">About Microsoft Application Virtualization 5.0 SP3</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b4110-140">如需如何設定 App-V 5.0 用戶端共存的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b4110-140">For more information about how to configure App-V 5.0 client coexistence, see:</span></span>

-   [<span data-ttu-id="b4110-141">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="b4110-141">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

-   [<span data-ttu-id="b4110-142">App-v 5.0 共存與遷移</span><span class="sxs-lookup"><span data-stu-id="b4110-142">App-V 5.0 Coexistence and Migration</span></span>](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a><span data-ttu-id="b4110-143">使用套件轉換器轉換「舊版本」套件</span><span class="sxs-lookup"><span data-stu-id="b4110-143">Converting “previous-version” packages using the package converter</span></span>


<span data-ttu-id="b4110-144">在將使用 App-v 4.6 SP3 或較舊版本的套件建立到 App-v 5.0 之前，請先檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="b4110-144">Before migrating a package, created using App-V4.6SP3 or earlier, to App-V 5.0, review the following requirements:</span></span>

-   <span data-ttu-id="b4110-145">您必須將套件轉換為**appv**檔案格式。</span><span class="sxs-lookup"><span data-stu-id="b4110-145">You must convert the package to the **.appv** file format.</span></span>

-   <span data-ttu-id="b4110-146">套件轉換器只支援使用 App-v 4.5 和更新版本所建立之套件的直接轉換。</span><span class="sxs-lookup"><span data-stu-id="b4110-146">The Package Converter supports only the direct conversion of packages that were created by using App-V 4.5 and later.</span></span> <span data-ttu-id="b4110-147">若要在使用舊版本建立的套件上使用套件轉換器，您必須使用 sequencer 或更新版本的 sequencer 來升級套件，然後您就可以執行套件轉換。</span><span class="sxs-lookup"><span data-stu-id="b4110-147">To use the package converter on a package that was created using a previous version, you must use an App-V4.5 or later version of the sequencer to upgrade the package, and then you can perform the package conversion.</span></span>

<span data-ttu-id="b4110-148">如需使用套件轉換器轉換套件的詳細資訊，請參閱[如何轉換在舊版 app-v 中建立的套件](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)。</span><span class="sxs-lookup"><span data-stu-id="b4110-148">For more information about using the package converter to convert a package, see [How to Convert a Package Created in a Previous Version of App-V](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md).</span></span> <span data-ttu-id="b4110-149">轉換檔案之後，您可以將它部署到執行 App-v 5.0 用戶端的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="b4110-149">After you convert the file, you can deploy it to target computers that run the App-V 5.0 client.</span></span>






## <span data-ttu-id="b4110-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="b4110-150">Related topics</span></span>


[<span data-ttu-id="b4110-151">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="b4110-151">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





