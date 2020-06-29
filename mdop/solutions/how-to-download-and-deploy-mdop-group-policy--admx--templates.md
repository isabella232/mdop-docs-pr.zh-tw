---
title: 如何下載及部署 MDOP 群組原則 (.admx) 範本
description: 如何下載及部署 MDOP 群組原則 (.admx) 範本
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812044"
---
# <span data-ttu-id="26f76-103">如何下載及部署 MDOP 群組原則 (.admx) 範本</span><span class="sxs-lookup"><span data-stu-id="26f76-103">How to Download and Deploy MDOP Group Policy (.admx) Templates</span></span>


<span data-ttu-id="26f76-104">您可以使用群組原則範本（admx 與 adml 檔案），管理某些 Microsoft 桌面優化套件（MDOP）技術（例如，App-v、UE-V 或 MBAM）的功能設定。</span><span class="sxs-lookup"><span data-stu-id="26f76-104">You can manage the feature settings of certain Microsoft Desktop Optimization Pack (MDOP) technologies (for example, App-V, UE-V, or MBAM) by using Group Policy templates, the .admx and .adml files.</span></span> <span data-ttu-id="26f76-105">您可以在自解壓縮、壓縮檔案中下載 MDOP 群組原則範本，並依技術和版本分組。</span><span class="sxs-lookup"><span data-stu-id="26f76-105">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

## <span data-ttu-id="26f76-106">MDOP 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="26f76-106">MDOP Group Policy templates</span></span>

**<span data-ttu-id="26f76-107">如何下載及部署 MDOP 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="26f76-107">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="26f76-108">下載最新的[MDOP 群組原則範本](https://www.microsoft.com/download/details.aspx?id=55531)</span><span class="sxs-lookup"><span data-stu-id="26f76-108">Download the latest [MDOP Group Policy templates](https://www.microsoft.com/download/details.aspx?id=55531)</span></span> 

2. <span data-ttu-id="26f76-109">透過執行來展開已下載的 .cab 檔案</span><span class="sxs-lookup"><span data-stu-id="26f76-109">Expand the downloaded .cab file by running</span></span> `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **<span data-ttu-id="26f76-110">警告</span><span class="sxs-lookup"><span data-stu-id="26f76-110">Warning</span></span>**  
   <span data-ttu-id="26f76-111">請勿將範本直接解壓縮至 [群組原則] 部署目錄。</span><span class="sxs-lookup"><span data-stu-id="26f76-111">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="26f76-112">在此檔案中捆綁了多種技術與版本。</span><span class="sxs-lookup"><span data-stu-id="26f76-112">Multiple technologies and versions are bundled in this file.</span></span>

3. <span data-ttu-id="26f76-113">在解壓縮的資料夾中，找出技術版本的 admx 檔案。</span><span class="sxs-lookup"><span data-stu-id="26f76-113">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="26f76-114">某些 MDOP 技術有多組群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="26f76-114">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="26f76-115">例如，MBAM 包括 MBAM 管理設定和 MBAM 使用者設定。</span><span class="sxs-lookup"><span data-stu-id="26f76-115">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="26f76-116">依語言區域性（也就是*en-us* -美國）來找出適當的 adml 檔案。</span><span class="sxs-lookup"><span data-stu-id="26f76-116">Locate the appropriate .adml file by language-culture (that is, *en-us* for English-United States).</span></span>

5. <span data-ttu-id="26f76-117">將 admx 與 adml 檔案複製到原則定義資料夾中。</span><span class="sxs-lookup"><span data-stu-id="26f76-117">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="26f76-118">根據您儲存範本的位置，您可以從本機裝置或網域上的任何電腦來設定群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="26f76-118">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   - <span data-ttu-id="26f76-119">**本機檔案：** 若要從本機裝置設定群組原則設定，請將範本檔案複製到下列位置：</span><span class="sxs-lookup"><span data-stu-id="26f76-119">**Local files:** To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="26f76-120">檔案類型</span><span class="sxs-lookup"><span data-stu-id="26f76-120">File type</span></span></th>
   <th align="left"><span data-ttu-id="26f76-121">檔案位置</span><span class="sxs-lookup"><span data-stu-id="26f76-121">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="26f76-122">群組原則範本（admx）</span><span class="sxs-lookup"><span data-stu-id="26f76-122">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="26f76-123">&lt;強勁 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="26f76-123">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="26f76-124">群組原則語言檔（adml）</span><span class="sxs-lookup"><span data-stu-id="26f76-124">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="26f76-125">&lt;強勁 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="26f76-125">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>

   - <span data-ttu-id="26f76-126">**網域中央商店：** 若要從網域上任何電腦的群群組原則管理員啟用群組原則設定，請將檔案複製到網網域控制站上的下列位置：</span><span class="sxs-lookup"><span data-stu-id="26f76-126">**Domain central store:** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="26f76-127">檔案類型</span><span class="sxs-lookup"><span data-stu-id="26f76-127">File type</span></span></th>
   <th align="left"><span data-ttu-id="26f76-128">檔案位置</span><span class="sxs-lookup"><span data-stu-id="26f76-128">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="26f76-129">群組原則範本（admx）</span><span class="sxs-lookup"><span data-stu-id="26f76-129">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="26f76-130">&lt;強勁 &gt; sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="26f76-130">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="26f76-131">群組原則語言檔（adml）</span><span class="sxs-lookup"><span data-stu-id="26f76-131">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="26f76-132">&lt;強勁 &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</span><span class="sxs-lookup"><span data-stu-id="26f76-132">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions[MUIculture]</span></span></strong><code>[MUIculture]</code></p>
   <p><span data-ttu-id="26f76-133">例如，美國英文 ADML 語言專用檔案將會儲存在%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us。</span><span class="sxs-lookup"><span data-stu-id="26f76-133">For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</span></span></p></td>
   </tr>
   </tbody>
   </table>

6. <span data-ttu-id="26f76-134">使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）編輯群組原則設定，以設定 MDOP 技術的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="26f76-134">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span>

### <span data-ttu-id="26f76-135">MDOP 群組原則（依技術）</span><span class="sxs-lookup"><span data-stu-id="26f76-135">MDOP Group Policy by technology</span></span>

<span data-ttu-id="26f76-136">如需支援的 MDOP 群組原則的詳細資訊，請參閱該技術的特定檔。</span><span class="sxs-lookup"><span data-stu-id="26f76-136">For more information about supported MDOP Group Policy, see the specific documentation for the technology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="26f76-137">MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="26f76-137">MDOP Technology</span></span></th>
<th align="left"><span data-ttu-id="26f76-138">版本束</span><span class="sxs-lookup"><span data-stu-id="26f76-138">Version bundles</span></span></th>
<th align="left"><span data-ttu-id="26f76-139">附註</span><span class="sxs-lookup"><span data-stu-id="26f76-139">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="26f76-140">Application Virtualization (App-V)</span><span class="sxs-lookup"><span data-stu-id="26f76-140">Application Virtualization (App-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="26f76-141">App-v 5.0 和 App-v 5.0 Service Pack</span><span class="sxs-lookup"><span data-stu-id="26f76-141">App-V 5.0 and App-V 5.0 Service Packs</span></span></p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)"><span data-ttu-id="26f76-142">如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態</span><span class="sxs-lookup"><span data-stu-id="26f76-142">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="26f76-143">User Experience Virtualization (UE-V)</span><span class="sxs-lookup"><span data-stu-id="26f76-143">User Experience Virtualization (UE-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="26f76-144">UE-V 2.0 和 UE-V 2。1</span><span class="sxs-lookup"><span data-stu-id="26f76-144">UE-V 2.0 and UE-V 2.1</span></span></p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)"><span data-ttu-id="26f76-145">使用群組原則物件設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="26f76-145">Configuring UE-V 2.x with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26f76-146">UE-V 1.0 （包括 1.0 SP1）</span><span class="sxs-lookup"><span data-stu-id="26f76-146">UE-V 1.0 including 1.0 SP1</span></span></p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)"><span data-ttu-id="26f76-147">使用群組原則物件來設定 UE-V</span><span class="sxs-lookup"><span data-stu-id="26f76-147">Configuring UE-V with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="26f76-148">Microsoft BitLocker 管理和監視 (MBAM)</span><span class="sxs-lookup"><span data-stu-id="26f76-148">Microsoft BitLocker Administration and Monitoring (MBAM)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="26f76-149">MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="26f76-149">MBAM 2.5</span></span></p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="26f76-150">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="26f76-150">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26f76-151">MBAM 2.0 （含 2.0 SP1）</span><span class="sxs-lookup"><span data-stu-id="26f76-151">MBAM 2.0 including 2.0 SP1</span></span></p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="26f76-152">MBAM 2.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="26f76-152">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="26f76-153">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="26f76-153">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="26f76-154">MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="26f76-154">MBAM 1.0</span></span></p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)"><span data-ttu-id="26f76-155">如何編輯 MBAM 1.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="26f76-155">How to Edit MBAM 1.0 GPO Settings</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





