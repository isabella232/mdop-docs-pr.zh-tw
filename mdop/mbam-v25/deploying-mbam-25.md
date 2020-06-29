---
title: 部署 MBAM 2.5
description: 部署 MBAM 2.5
author: dansimp
ms.assetid: 45403607-1f4d-42fe-8413-0d4da01808a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0cfa0a190530186211cd96884b2e32e9c65881f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811661"
---
# <span data-ttu-id="3720a-103">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3720a-103">Deploying MBAM 2.5</span></span>


<span data-ttu-id="3720a-104">使用這項資訊來找出您可以遵循的程式來部署並設定 Microsoft BitLocker 管理與監控（MBAM）2.5 伺服器功能，以升級至舊版的 MBAM 2.5，或移除 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="3720a-104">Use this information to identify the procedures you can follow to deploy and configure Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features to upgrade to MBAM 2.5 from previous versions, or to remove MBAM Server features.</span></span>

## <span data-ttu-id="3720a-105">部署資訊</span><span class="sxs-lookup"><span data-stu-id="3720a-105">Deployment information</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3720a-106">主題描述</span><span class="sxs-lookup"><span data-stu-id="3720a-106">Topic description</span></span></th>
<th align="left"><span data-ttu-id="3720a-107">主題的連結</span><span class="sxs-lookup"><span data-stu-id="3720a-107">Links to topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="3720a-108">部署拓撲選項。</span><span class="sxs-lookup"><span data-stu-id="3720a-108">Deployment topology options.</span></span></p></li>
<li><p><span data-ttu-id="3720a-109">如何安裝 MBAM Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="3720a-109">How to install the MBAM Server software.</span></span></p></li>
<li><p><span data-ttu-id="3720a-110">如何設定 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="3720a-110">How to configure the MBAM Server features.</span></span></p></li>
</ul></td>
<td align="left"><p><a href="deploying-the-mbam-25-server-infrastructure.md" data-raw-source="[Deploying the MBAM 2.5 Server Infrastructure](deploying-the-mbam-25-server-infrastructure.md)"><span data-ttu-id="3720a-111">部署 MBAM 2.5 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="3720a-111">Deploying the MBAM 2.5 Server Infrastructure</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3720a-112">如何下載及部署 MBAM 群組原則範本，這些範本是在企業中管理 MBAM 用戶端和 BitLocker 加密原則所需的。</span><span class="sxs-lookup"><span data-stu-id="3720a-112">How to download and deploy the MBAM Group Policy Templates, which are required to manage MBAM Clients and BitLocker encryption policies in the enterprise.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-25-group-policy-objects.md" data-raw-source="[Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md)"><span data-ttu-id="3720a-113">部署 MBAM 2.5 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="3720a-113">Deploying MBAM 2.5 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3720a-114">如何使用 MBAM 用戶端 Windows 安裝程式檔案來部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="3720a-114">How to use the MBAM Client Windows Installer files to deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="3720a-115">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="3720a-115">Deploying the MBAM 2.5 Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3720a-116">可協助您部署 MBAM Server 功能與 MBAM 用戶端的檢查清單。</span><span class="sxs-lookup"><span data-stu-id="3720a-116">Checklist that can assist you in deploying the MBAM Server features and MBAM Client.</span></span></p></td>
<td align="left"><p><a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"><span data-ttu-id="3720a-117">MBAM 2.5 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3720a-117">MBAM 2.5 Deployment Checklist</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3720a-118">如何從先前的版本升級 MBAM。</span><span class="sxs-lookup"><span data-stu-id="3720a-118">How to upgrade MBAM from previous versions.</span></span></p></td>
<td align="left"><p><a href="upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md" data-raw-source="[Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)"><span data-ttu-id="3720a-119">從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3720a-119">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3720a-120">如何移除 MBAM 伺服器功能或軟體。</span><span class="sxs-lookup"><span data-stu-id="3720a-120">How to remove MBAM Server features or software.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="3720a-121">移除 MBAM 伺服器功能或軟體</span><span class="sxs-lookup"><span data-stu-id="3720a-121">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3720a-122">部署 MBAM 的其他資源</span><span class="sxs-lookup"><span data-stu-id="3720a-122">Other resources for deploying MBAM</span></span>


[<span data-ttu-id="3720a-123">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="3720a-123">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="3720a-124">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3720a-124">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="3720a-125">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="3720a-125">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="3720a-126">適用於 MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="3720a-126">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

[<span data-ttu-id="3720a-127">MBAM 2.5 疑難排解</span><span class="sxs-lookup"><span data-stu-id="3720a-127">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)

[<span data-ttu-id="3720a-128">MBAM 2.5 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="3720a-128">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="3720a-129">以獨立設定進行 MBAM 2.5 部署</span><span class="sxs-lookup"><span data-stu-id="3720a-129">Deploying MBAM 2.5 in a stand-alone configuration</span></span>](https://support.microsoft.com/kb/3046555)

## <span data-ttu-id="3720a-130">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3720a-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3720a-131">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3720a-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3720a-132">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3720a-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





