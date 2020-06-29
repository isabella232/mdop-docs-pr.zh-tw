---
title: 規劃如何儲存和部署 DaRT 10 復原映像
description: 規劃如何儲存和部署 DaRT 10 復原映像
author: dansimp
ms.assetid: 9a3e5413-2621-49ce-8bd2-992616691703
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbaa8c4160970de90561f5ff8cedcefd08ca1dd7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809686"
---
# <span data-ttu-id="e5243-103">規劃如何儲存和部署 DaRT 10 復原映像</span><span class="sxs-lookup"><span data-stu-id="e5243-103">Planning How to Save and Deploy the DaRT 10 Recovery Image</span></span>


<span data-ttu-id="e5243-104">您可以使用下列方法儲存及部署 Microsoft Diagnostics 和復原工具庫（DaRT）10復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-104">You can save and deploy the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image by using the following methods.</span></span> <span data-ttu-id="e5243-105">當您決定要使用的方法時，請考慮每個方法的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="e5243-105">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="e5243-106">您也應該考慮您的基礎結構及支援人員。</span><span class="sxs-lookup"><span data-stu-id="e5243-106">You should also consider your infrastructure and support staff.</span></span> <span data-ttu-id="e5243-107">如果您有小型基礎結構，您可能會想要使用 [卸除式媒體] 來部署 DaRT 10，因為當您將其安裝到本機硬碟時，系統會一直提供復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-107">If you have a small infrastructure, you might want to deploy DaRT 10 by using removable media, since the recovery image will always be available if you install it to the local hard drive.</span></span>

<span data-ttu-id="e5243-108">如果您的組織使用 Active Directory 網域服務（AD DS），您可能會想要使用 Windows DS 將復原影像部署為網路服務。</span><span class="sxs-lookup"><span data-stu-id="e5243-108">If your organization uses Active Directory Domain Services (AD DS), you may want to deploy recovery images as a network service by using Windows DS.</span></span> <span data-ttu-id="e5243-109">任何已連接的電腦都能使用復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-109">Recovery images are always available to any connected computer.</span></span> <span data-ttu-id="e5243-110">您可以從 Windows DS 部署多個影像，並將它們全部保留在同一個位置。</span><span class="sxs-lookup"><span data-stu-id="e5243-110">You can deploy multiple images from Windows DS and maintain them all in one place.</span></span>

<span data-ttu-id="e5243-111">**記事** 您可能會想要在組織中使用多個方法。</span><span class="sxs-lookup"><span data-stu-id="e5243-111">**Note** You may want to use more than one method in your organization.</span></span> <span data-ttu-id="e5243-112">例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="e5243-112">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="e5243-113">下表顯示在貴組織中使用 DaRT 的每個方法的一些優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="e5243-113">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5243-114">啟動到 DaRT 的方法</span><span class="sxs-lookup"><span data-stu-id="e5243-114">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="e5243-115">優點</span><span class="sxs-lookup"><span data-stu-id="e5243-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="e5243-116">缺點</span><span class="sxs-lookup"><span data-stu-id="e5243-116">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e5243-117">卸除式媒體</span><span class="sxs-lookup"><span data-stu-id="e5243-117">Removable Media</span></span></strong></p>
<p><span data-ttu-id="e5243-118">[復原] 影像會寫入 CD、DVD 或 USB 磁片磁碟機，以讓支援人員將恢復工具隨身攜帶到不穩定的電腦。</span><span class="sxs-lookup"><span data-stu-id="e5243-118">The recovery image is written to a CD, DVD, or USB drive to enable support staff to take the recovery tools with them to the unstable computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-119">支援主要開機記錄（MBR）損毀，而且您無法存取硬碟及支援沒有網路連線的情況。</span><span class="sxs-lookup"><span data-stu-id="e5243-119">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk and supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="e5243-120">可讓您使用不同的工具建立多個復原影像，以提供不同的支援層級。</span><span class="sxs-lookup"><span data-stu-id="e5243-120">Enables you to create multiple recovery images with different tools to provide different levels of support.</span></span></p>
<p><span data-ttu-id="e5243-121">提供將復原影像燒錄至卸除式媒體的內建工具。</span><span class="sxs-lookup"><span data-stu-id="e5243-121">Provides a built-in tool for burning recovery images to removable media.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-122">需要支援人員實際在最終使用者電腦上，才能引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="e5243-122">Requires that support staff are physically at the end-user computer to boot into DaRT.</span></span></p>
<p><span data-ttu-id="e5243-123">需要進行時間和維護，以針對32位和64位電腦建立多個不同的配置。</span><span class="sxs-lookup"><span data-stu-id="e5243-123">Requires time and maintenance to create multiple media with different configurations for 32-bit and 64-bit computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e5243-124">從遠端（網路）分區</span><span class="sxs-lookup"><span data-stu-id="e5243-124">From a remote (network) partition</span></span></strong></p>
<p><span data-ttu-id="e5243-125">復原影像是在網路啟動伺服器（例如 Windows 部署服務（Windows DS））上裝載，這可讓使用者或支援人員將它流式處理到電腦的需求。</span><span class="sxs-lookup"><span data-stu-id="e5243-125">The recovery image is hosted on a network boot server like Windows Deployment Services (Windows DS), which allows users or support staff to stream it to computers on demand.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-126">可供所有可存取網路啟動伺服器的電腦使用。</span><span class="sxs-lookup"><span data-stu-id="e5243-126">Available to all computers that have access to the network boot server.</span></span></p>
<p><span data-ttu-id="e5243-127">復原影像是以中央伺服器為宿主，可啟用集中式更新。</span><span class="sxs-lookup"><span data-stu-id="e5243-127">Recovery images are hosted on a central server, which enables centralized updates.</span></span></p>
<p><span data-ttu-id="e5243-128">中央技術支援人員可使用遠端連線來提供修復。</span><span class="sxs-lookup"><span data-stu-id="e5243-128">Centralized help desk staff can provide repairs by using remote connectivity.</span></span></p>
<p><span data-ttu-id="e5243-129">用戶端上沒有本機儲存需求。</span><span class="sxs-lookup"><span data-stu-id="e5243-129">No local storage requirement on the clients.</span></span></p>
<p><span data-ttu-id="e5243-130">能夠針對特定的支援層級，使用不同的工具來建立多個復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-130">Ability to create multiple recovery images with different tools for specific support levels.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-131">需要保護 Windows DS 基礎結構，以確保一般使用者只能啟動 DaRT 復原影像，而不能啟動完整的作業系統影像處理常式。</span><span class="sxs-lookup"><span data-stu-id="e5243-131">The need to secure Windows DS infrastructure to ensure that regular users can start only the DaRT recovery image and not the full operating system imaging process.</span></span></p>
<p></p>
<p></p>
<p><span data-ttu-id="e5243-132">要求使用者電腦在執行時間連線至網路。</span><span class="sxs-lookup"><span data-stu-id="e5243-132">Requires that the end-user computer is connected to the network at runtime.</span></span></p>
<p><span data-ttu-id="e5243-133">需要在網路上進行復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-133">Requires that the recovery image is brought across the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e5243-134">從本機硬碟上的 [恢復] 分區</span><span class="sxs-lookup"><span data-stu-id="e5243-134">From a recovery partition on the local hard drive</span></span></strong></p>
<p><span data-ttu-id="e5243-135">您可以手動或使用電子軟體發佈系統（例如 System Center Configuration Manager），在本機硬碟上安裝復原影像。</span><span class="sxs-lookup"><span data-stu-id="e5243-135">The recovery image is installed on a local hard drive either manually or by using electronic software distribution systems like System Center Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-136">復原影像永遠可供使用，因為它是在電腦上預先暫存。</span><span class="sxs-lookup"><span data-stu-id="e5243-136">The recovery image is always available because it is pre-staged on the computer.</span></span></p>
<p><span data-ttu-id="e5243-137">中央技術支援人員可使用遠端連線提供支援。</span><span class="sxs-lookup"><span data-stu-id="e5243-137">Centralized help desk staff can provide support by using Remote Connection.</span></span></p>
<p><span data-ttu-id="e5243-138">復原影像會集中管理並部署。</span><span class="sxs-lookup"><span data-stu-id="e5243-138">The recovery image is centrally managed and deployed.</span></span></p>
<p><span data-ttu-id="e5243-139">已消除由 Windows BitLocker 磁碟機加密所保護之電腦上的其他修復金鑰要求。</span><span class="sxs-lookup"><span data-stu-id="e5243-139">Additional recovery key requests on computers that are protected by Windows BitLocker drive encryption are eliminated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e5243-140">需要本機儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e5243-140">Local storage is required.</span></span></p>
<p><span data-ttu-id="e5243-141">建議使用專門的未加密分區來進行復原影像放置，以降低啟動磁碟分割失敗的風險。</span><span class="sxs-lookup"><span data-stu-id="e5243-141">A dedicated, unencrypted partition for recovery image placement is recommended to reduce the risk of a failed boot partition.</span></span></p>
<p><span data-ttu-id="e5243-142">更新 DaRT 時，您必須更新企業中的所有電腦，而不是只有一個分區（在網路上）或移除裝置。</span><span class="sxs-lookup"><span data-stu-id="e5243-142">When updating DaRT, you must update all computers in your enterprise instead of just one partition (on the network) or removable device.</span></span></p>
<p><span data-ttu-id="e5243-143">如果您在啟用 BitLocker 之後部署復原映像，則需要其他考慮。</span><span class="sxs-lookup"><span data-stu-id="e5243-143">Additional consideration is required if you deploy the recovery image after BitLocker has been enabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e5243-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5243-144">Related topics</span></span>


[<span data-ttu-id="e5243-145">規劃部署 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="e5243-145">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 





