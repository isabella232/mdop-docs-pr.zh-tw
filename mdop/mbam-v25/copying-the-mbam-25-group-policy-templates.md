---
title: 複製 MBAM 2.5 群組原則範本
description: 複製 MBAM 2.5 群組原則範本
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811025"
---
# <span data-ttu-id="92540-103">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="92540-103">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="92540-104">在部署 MBAM 用戶端安裝之前，您必須下載 MBAM 群組原則範本，其中包含定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="92540-104">Before deploying the MBAM Client installation, you must download the MBAM Group Policy Templates, which contain Group Policy settings that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="92540-105">下載範本之後，您可以將群組原則設定設定為在整個企業中實現。</span><span class="sxs-lookup"><span data-stu-id="92540-105">After downloading the templates, you then set the Group Policy settings to implement across your enterprise.</span></span>

## <span data-ttu-id="92540-106">下載並部署 MDOP 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="92540-106">Downloading and deploying the MDOP Group Policy templates</span></span>


<span data-ttu-id="92540-107">您可以在自解壓縮、壓縮檔案中下載 MDOP 群組原則範本，並依技術和版本分組。</span><span class="sxs-lookup"><span data-stu-id="92540-107">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

**<span data-ttu-id="92540-108">如何下載及部署 MDOP 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="92540-108">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="92540-109">從[Microsoft Desktop 最優化 Pack 群群組原則管理範本](https://www.microsoft.com/download/details.aspx?id=55531)下載 MDOP 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="92540-109">Download the MDOP Group Policy templates from [Microsoft Desktop Optimization Pack Group Policy Administrative Templates](https://www.microsoft.com/download/details.aspx?id=55531).</span></span>

2. <span data-ttu-id="92540-110">執行已下載的檔案，以解壓範本資料夾。</span><span class="sxs-lookup"><span data-stu-id="92540-110">Run the downloaded file to extract the template folders.</span></span>

   **<span data-ttu-id="92540-111">警告</span><span class="sxs-lookup"><span data-stu-id="92540-111">Warning</span></span>**  
   <span data-ttu-id="92540-112">請勿將範本直接解壓縮至 [群組原則] 部署目錄。</span><span class="sxs-lookup"><span data-stu-id="92540-112">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="92540-113">在此檔案中捆綁了多種技術與版本。</span><span class="sxs-lookup"><span data-stu-id="92540-113">Multiple technologies and versions are bundled in this file.</span></span>



3. <span data-ttu-id="92540-114">在解壓縮的資料夾中，找出技術版本的 admx 檔案。</span><span class="sxs-lookup"><span data-stu-id="92540-114">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="92540-115">某些 MDOP 技術有多組群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="92540-115">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="92540-116">例如，MBAM 包括 MBAM 管理設定和 MBAM 使用者設定。</span><span class="sxs-lookup"><span data-stu-id="92540-116">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="92540-117">依語言區域性（也就是*en* -美國）來找出適當的 adml 檔案。</span><span class="sxs-lookup"><span data-stu-id="92540-117">Locate the appropriate .adml file by language-culture (that is, *en* for English-United States).</span></span>

5. <span data-ttu-id="92540-118">將 admx 與 adml 檔案複製到原則定義資料夾中。</span><span class="sxs-lookup"><span data-stu-id="92540-118">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="92540-119">根據您儲存範本的位置，您可以從本機裝置或網域上的任何電腦來設定群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="92540-119">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   **<span data-ttu-id="92540-120">本機檔案。</span><span class="sxs-lookup"><span data-stu-id="92540-120">Local files.</span></span>** <span data-ttu-id="92540-121">若要從本機裝置設定群組原則設定，請將範本檔案複製到下列位置：</span><span class="sxs-lookup"><span data-stu-id="92540-121">To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="92540-122">檔案類型</span><span class="sxs-lookup"><span data-stu-id="92540-122">File type</span></span></th>
   <th align="left"><span data-ttu-id="92540-123">檔案位置</span><span class="sxs-lookup"><span data-stu-id="92540-123">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="92540-124">群組原則範本（admx）</span><span class="sxs-lookup"><span data-stu-id="92540-124">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="92540-125">&lt;強勁 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="92540-125">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="92540-126">群組原則語言檔（adml）</span><span class="sxs-lookup"><span data-stu-id="92540-126">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="92540-127">&lt;強勁 &gt; policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="92540-127">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. <span data-ttu-id="92540-128">使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）編輯群組原則設定，以設定 MDOP 技術的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="92540-128">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span> <span data-ttu-id="92540-129">如需詳細資訊，請參閱[編輯 MBAM 2.5 群組原則設定](editing-the-mbam-25-group-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="92540-129">See [Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md) for more information.</span></span>

   <span data-ttu-id="92540-130">如需群組原則設定的說明，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92540-130">For descriptions of the Group Policy settings, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>


## <span data-ttu-id="92540-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="92540-131">Related topics</span></span>


[<span data-ttu-id="92540-132">部署 MBAM 2.5 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="92540-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)


## <span data-ttu-id="92540-133">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="92540-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="92540-134">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="92540-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="92540-135">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="92540-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






