---
title: 規劃如何儲存和部署 DaRT 7.0 復原映像
description: 規劃如何儲存和部署 DaRT 7.0 復原映像
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809572"
---
# <span data-ttu-id="99fb1-103">規劃如何儲存和部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="99fb1-103">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="99fb1-104">當您規劃儲存及部署 Microsoft Diagnostics 和復原工具集（DaRT）7復原影像時，請使用本節中的資訊。</span><span class="sxs-lookup"><span data-stu-id="99fb1-104">Use the information in this section when you plan for saving and deploying the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="99fb1-105">規劃如何儲存和部署 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="99fb1-105">Planning How to Save and Deploy the DaRT Recovery Image</span></span>


<span data-ttu-id="99fb1-106">您可以使用下列方法儲存及部署 DaRT 復原影像。</span><span class="sxs-lookup"><span data-stu-id="99fb1-106">You can save and deploy the DaRT recovery image by using the following methods.</span></span> <span data-ttu-id="99fb1-107">當您決定要使用的方法時，請考慮每個方法的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="99fb1-107">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="99fb1-108">此外，請考慮您想要在企業中使用 DaRT 的方式。</span><span class="sxs-lookup"><span data-stu-id="99fb1-108">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="99fb1-109">**記事** 您可能會想要在您的組織中使用一個以上的方法。</span><span class="sxs-lookup"><span data-stu-id="99fb1-109">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="99fb1-110">例如，在大多數情況下，您可以從遠端分區引導至 DaRT，並在使用者電腦無法連線到網路時，有可用的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="99fb1-110">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="99fb1-111">下表顯示在貴組織中使用 DaRT 的每個方法的一些優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="99fb1-111">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99fb1-112">啟動到 DaRT 的方法</span><span class="sxs-lookup"><span data-stu-id="99fb1-112">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="99fb1-113">優點</span><span class="sxs-lookup"><span data-stu-id="99fb1-113">Advantages</span></span></th>
<th align="left"><span data-ttu-id="99fb1-114">缺點</span><span class="sxs-lookup"><span data-stu-id="99fb1-114">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99fb1-115">從 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="99fb1-115">From a CD or DVD</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-116">支援主要開機記錄（MBR）損毀且無法存取硬碟的情況。</span><span class="sxs-lookup"><span data-stu-id="99fb1-116">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk.</span></span> <span data-ttu-id="99fb1-117">也支援沒有網路連線的情況。</span><span class="sxs-lookup"><span data-stu-id="99fb1-117">Also supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="99fb1-118">這對於舊版 DaRT 的使用者而言是最熟悉的，而且可以直接從 DaRT 復原映射嚮導燒錄 CD 或 DVD <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="99fb1-118">This is most familiar to users of earlier versions of DaRT, and a CD or DVD can be burned directly from the <strong>DaRT Recovery Image Wizard</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-119">需要擁有 CD 或 DVD 存取權的人在物理位置是在最終使用者電腦上啟動到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="99fb1-119">Requires that someone with access to the CD or DVD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99fb1-120">從 USB 快閃記憶體磁片磁碟機（UFD）</span><span class="sxs-lookup"><span data-stu-id="99fb1-120">From a USB flash drive (UFD)</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-121">提供從 CD 或 DVD 開機的相同優點，同時也為沒有 CD 或 DVD 磁片磁碟機的電腦提供支援。</span><span class="sxs-lookup"><span data-stu-id="99fb1-121">Provides same advantages as booting from a CD or DVD and also provides support to computers that have no CD or DVD drive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-122">需要您先格式化 UFD，才能使用它來引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="99fb1-122">Requires you to format the UFD before you can use it to boot into DaRT.</span></span> <span data-ttu-id="99fb1-123">此外，您也需要擁有 UFD 存取權的人在物理位置是在最終使用者電腦上引導至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="99fb1-123">Also requires that someone with access to the UFD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99fb1-124">從遠端（網路）分區</span><span class="sxs-lookup"><span data-stu-id="99fb1-124">From a remote (network) partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-125">可讓您在不需要 CD、DVD 或 UFD 的情況下，啟動到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="99fb1-125">Lets you boot into DaRT without needing a CD, DVD, or UFD.</span></span> <span data-ttu-id="99fb1-126">還可讓您輕鬆升級 DaRT，因為只有一個要更新的檔案位置。</span><span class="sxs-lookup"><span data-stu-id="99fb1-126">Also allows for easy upgrades of DaRT because there is only one file location to update.</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-127">如果最終使用者電腦未連線至網路，則無法運作。</span><span class="sxs-lookup"><span data-stu-id="99fb1-127">Does not work if the end-user computer is not connected to the network.</span></span></p>
<p><span data-ttu-id="99fb1-128">廣泛提供給使用者，並且可能需要在建立恢復影像時，進行其他安全性考慮。</span><span class="sxs-lookup"><span data-stu-id="99fb1-128">Widely available to end users and might require additional security considerations when you are creating the recovery image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99fb1-129">從還原分區</span><span class="sxs-lookup"><span data-stu-id="99fb1-129">From a recovery partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-130">可讓您啟動到 DaRT，而不需要 CD、DVD 或 UFD，包括沒有網路連接的情況。</span><span class="sxs-lookup"><span data-stu-id="99fb1-130">Lets you boot into DaRT without needing a CD, DVD, or UFD that includes instances in which there is no network connectivity.</span></span></p>
<p><span data-ttu-id="99fb1-131">此外，您也可以使用自動化的發佈工具（例如 Microsoft 端點設定管理員），來實現和管理標準 Windows 影像程式。</span><span class="sxs-lookup"><span data-stu-id="99fb1-131">Also, can be implemented and managed as part of your standard Windows image process by using automated distribution tools, such as Microsoft Endpoint Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="99fb1-132">更新 DaRT 時，需要您更新企業中的所有電腦，而不是只有一個分區（在網路上）或裝置（CD、DVD 或 UFD）。</span><span class="sxs-lookup"><span data-stu-id="99fb1-132">When updating DaRT, requires you to update all computers in your enterprise instead of just one partition (on the network) or device (CD, DVD, or UFD).</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="99fb1-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="99fb1-133">Related topics</span></span>


[<span data-ttu-id="99fb1-134">規劃部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="99fb1-134">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





