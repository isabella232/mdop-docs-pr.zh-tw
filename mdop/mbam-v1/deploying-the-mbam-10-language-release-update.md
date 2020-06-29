---
title: 部署 MBAM 1.0 語言版本更新
description: 部署 MBAM 1.0 語言版本更新
author: dansimp
ms.assetid: 9dbd85c3-e470-4752-a90f-25754dd46dab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a819be81594efd9349e3f6c0f6559c2b810bdc9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800190"
---
# <span data-ttu-id="d5b76-103">部署 MBAM 1.0 語言版本更新</span><span class="sxs-lookup"><span data-stu-id="d5b76-103">Deploying the MBAM 1.0 Language Release Update</span></span>


<span data-ttu-id="d5b76-104">Microsoft BitLocker 管理和監控（MBAM）1.0 語言發行是 MBAM 的更新，包含新語言的支援。</span><span class="sxs-lookup"><span data-stu-id="d5b76-104">Microsoft BitLocker Administration and Monitoring (MBAM)1.0 Language Release is an update to MBAM and includes the support of new languages.</span></span> <span data-ttu-id="d5b76-105">新的語言為：</span><span class="sxs-lookup"><span data-stu-id="d5b76-105">The new languages are:</span></span>

-   <span data-ttu-id="d5b76-106">英文（zh-cn）</span><span class="sxs-lookup"><span data-stu-id="d5b76-106">English (en-us)</span></span>

-   <span data-ttu-id="d5b76-107">法文（fr）</span><span class="sxs-lookup"><span data-stu-id="d5b76-107">French (fr)</span></span>

-   <span data-ttu-id="d5b76-108">義大利文（it）</span><span class="sxs-lookup"><span data-stu-id="d5b76-108">Italian (it)</span></span>

-   <span data-ttu-id="d5b76-109">德文（de）</span><span class="sxs-lookup"><span data-stu-id="d5b76-109">German (de)</span></span>

-   <span data-ttu-id="d5b76-110">西班牙文（es）</span><span class="sxs-lookup"><span data-stu-id="d5b76-110">Spanish (es)</span></span>

-   <span data-ttu-id="d5b76-111">朝鮮文（ko）</span><span class="sxs-lookup"><span data-stu-id="d5b76-111">Korean (ko)</span></span>

-   <span data-ttu-id="d5b76-112">日文（ja）</span><span class="sxs-lookup"><span data-stu-id="d5b76-112">Japanese (ja)</span></span>

-   <span data-ttu-id="d5b76-113">巴西葡萄牙文（pt-br）</span><span class="sxs-lookup"><span data-stu-id="d5b76-113">Brazilian Portuguese (pt-br)</span></span>

-   <span data-ttu-id="d5b76-114">俄文（ru）</span><span class="sxs-lookup"><span data-stu-id="d5b76-114">Russian (ru)</span></span>

-   <span data-ttu-id="d5b76-115">繁體中文（zh-cn&platform-幼圓）</span><span class="sxs-lookup"><span data-stu-id="d5b76-115">Chinese Traditional (zh-tw)</span></span>

-   <span data-ttu-id="d5b76-116">簡體中文（zh-cn&platform-cn）</span><span class="sxs-lookup"><span data-stu-id="d5b76-116">Chinese Simplified (zh-cn)</span></span>

<span data-ttu-id="d5b76-117">MBAM 1.0 語言更新會將版本號碼從 MBAM 1.0.1237.1 變更為 MBAM 1.0.2001。</span><span class="sxs-lookup"><span data-stu-id="d5b76-117">The MBAM1.0 language update will change the version number from MBAM 1.0.1237.1 to MBAM 1.0.2001.</span></span>

<span data-ttu-id="d5b76-118">您不需要重新安裝所有的 MBAM 功能，就能新增這些其他語言。</span><span class="sxs-lookup"><span data-stu-id="d5b76-118">You do not need to reinstall all of the MBAM features in order to add these additional languages.</span></span> <span data-ttu-id="d5b76-119">本主題定義新增新支援之語言所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="d5b76-119">This topic defines the steps required to add the newly supported languages.</span></span>

## <span data-ttu-id="d5b76-120">部署 MBAM 國際發行版本以 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="d5b76-120">Deploy the MBAM international release to MBAM Server features</span></span>


<span data-ttu-id="d5b76-121">若要開始，您必須更新下列 MBAM 伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="d5b76-121">To begin, you must update the following MBAM server features:</span></span>

-   <span data-ttu-id="d5b76-122">合規性與審查報告</span><span class="sxs-lookup"><span data-stu-id="d5b76-122">Compliance and Audit Report</span></span>

-   <span data-ttu-id="d5b76-123">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="d5b76-123">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="d5b76-124">原則範本</span><span class="sxs-lookup"><span data-stu-id="d5b76-124">Policy Templates</span></span>

<span data-ttu-id="d5b76-125">接著，您必須執行**MbamSetup.exe** ，升級在同一台伺服器上執行的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="d5b76-125">Then, you must run **MbamSetup.exe** to upgrade the MBAM features that run on the same server at the same time.</span></span>

[<span data-ttu-id="d5b76-126">如何在單一伺服器上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="d5b76-126">How to Install the MBAM Language Update on a Single Server</span></span>](how-to-install-the-mbam-language-update-on-a-single-server-mbam-1.md)

[<span data-ttu-id="d5b76-127">如何在分散式伺服器上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="d5b76-127">How to Install the MBAM Language Update on Distributed Servers</span></span>](how-to-install-the-mbam-language-update-on-distributed-servers-mbam-1.md)

## <span data-ttu-id="d5b76-128">安裝群組原則的 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="d5b76-128">Install the MBAM language update for Group Policies</span></span>


<span data-ttu-id="d5b76-129">您可以在每個管理工作站上安裝 MBAM 群組原則範本，或將其複製到 [群組原則中央存放區]，讓所有群組原則管理員都能使用這些範本。</span><span class="sxs-lookup"><span data-stu-id="d5b76-129">The MBAM Group Policy templates can be installed on each management workstation or they can be copied to the Group Policy central store, in order to make the templates available to all Group Policy administrators.</span></span> <span data-ttu-id="d5b76-130">原則範本無法直接安裝在網網域控制站上。</span><span class="sxs-lookup"><span data-stu-id="d5b76-130">The policy templates cannot be directly installed on a domain controller.</span></span> <span data-ttu-id="d5b76-131">如果您不使用群組原則中央存放區，則必須將原則手動複製到管理 MBAM 群組原則的每個網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="d5b76-131">If you do not use a Group Policy central store, then you must copy the policies manually to each domain controller that manages MBAM Group Policy.</span></span>

<span data-ttu-id="d5b76-132">若要新增 MBAM 語言原則範本，請將群組原則語言檔案從安裝「原則範本」角色的電腦上的%SystemRoot%\\PolicyDefinitions 複製到工作站電腦上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="d5b76-132">To add the MBAM language policies templates, copy the Group Policy language files from %SystemRoot%\\PolicyDefinitions on the computer where the “Policy Templates” role was installed to the same location on the workstation computer.</span></span> <span data-ttu-id="d5b76-133">以下是群組原則檔案的一些範例：</span><span class="sxs-lookup"><span data-stu-id="d5b76-133">Here are some examples of Group Policy files:</span></span>

-   <span data-ttu-id="d5b76-134">BitLockerManagement admx</span><span class="sxs-lookup"><span data-stu-id="d5b76-134">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="d5b76-135">BitLockerUserManagement admx</span><span class="sxs-lookup"><span data-stu-id="d5b76-135">BitLockerUserManagement.admx</span></span>

-   <span data-ttu-id="d5b76-136">en-us\\BitLockerManagement.adml</span><span class="sxs-lookup"><span data-stu-id="d5b76-136">en-us\\BitLockerManagement.adml</span></span>

-   <span data-ttu-id="d5b76-137">en-us\\BitLockerUserManagement.adml</span><span class="sxs-lookup"><span data-stu-id="d5b76-137">en-us\\BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="d5b76-138">fr-fr\\ BitLockerManagement adml</span><span class="sxs-lookup"><span data-stu-id="d5b76-138">fr-fr\\ BitLockerManagement.adml</span></span>

-   <span data-ttu-id="d5b76-139">fr-fr\\ BitLockerUserManagement adml</span><span class="sxs-lookup"><span data-stu-id="d5b76-139">fr-fr\\ BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="d5b76-140">（同樣適用于每個支援的語言）</span><span class="sxs-lookup"><span data-stu-id="d5b76-140">(and similarly for each supported language)</span></span>

## <span data-ttu-id="d5b76-141">MBAM 國際版中的已知問題</span><span class="sxs-lookup"><span data-stu-id="d5b76-141">Known issues in the MBAM international release</span></span>


<span data-ttu-id="d5b76-142">本主題包含 Microsoft BitLocker 管理和監控國際發行的已知問題。</span><span class="sxs-lookup"><span data-stu-id="d5b76-142">This topic contains known issues for Microsoft BitLocker Administration and Monitoring International Release.</span></span>

[<span data-ttu-id="d5b76-143">MBAM 國際版本的已知問題</span><span class="sxs-lookup"><span data-stu-id="d5b76-143">Known Issues in the MBAM International Release</span></span>](known-issues-in-the-mbam-international-release-mbam-1.md)

## <span data-ttu-id="d5b76-144">部署 MBAM 1.0 語言更新的其他資源</span><span class="sxs-lookup"><span data-stu-id="d5b76-144">Other resources for deploying the MBAM 1.0 Language Update</span></span>


[<span data-ttu-id="d5b76-145">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="d5b76-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





