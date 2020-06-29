---
title: App-V 5.0 的高階架構
description: App-V 5.0 的高階架構
author: dansimp
ms.assetid: fdf8b841-918f-4672-b352-0f2b9519581b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0ec105ffcc3213e488615603484b2de6bafce4d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800623"
---
# <span data-ttu-id="73149-103">App-V 5.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="73149-103">High Level Architecture for App-V 5.0</span></span>


<span data-ttu-id="73149-104">使用下列資訊來協助您簡化 Microsoft Application Virtualization （App-v）5.0 部署。</span><span class="sxs-lookup"><span data-stu-id="73149-104">Use the following information to help you simplify you Microsoft Application Virtualization (App-V) 5.0 deployment.</span></span>

## <span data-ttu-id="73149-105">架構概述</span><span class="sxs-lookup"><span data-stu-id="73149-105">Architecture Overview</span></span>


<span data-ttu-id="73149-106">典型的 App-v 5.0 實現是由下列元素所組成。</span><span class="sxs-lookup"><span data-stu-id="73149-106">A typical App-V 5.0 implementation consists of the following elements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="73149-107">元素</span><span class="sxs-lookup"><span data-stu-id="73149-107">Element</span></span></th>
<th align="left"><span data-ttu-id="73149-108">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="73149-108">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="73149-109">App-V 5.0 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="73149-109">App-V 5.0 Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="73149-110">App-v 5.0 管理伺服器提供 App-V 5.0 基礎結構的整體管理功能。</span><span class="sxs-lookup"><span data-stu-id="73149-110">The App-V 5.0 Management server provides overall management functionality for the App-V 5.0 infrastructure.</span></span> <span data-ttu-id="73149-111">此外，您也可以在您的環境中安裝一個以上的管理伺服器實例，提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="73149-111">Additionally, you can install more than one instance of the management server in your environment which provides the following benefits:</span></span></p>
<ul>
<li><p><span data-ttu-id="73149-112">容錯與高可用性–在兩部不同的電腦上安裝和設定 App-v 5.0 管理伺服器，可在其中一個伺服器無法使用或離線時協助進行。</span><span class="sxs-lookup"><span data-stu-id="73149-112">Fault Tolerance and High Availability – Installing and configuring the App-V 5.0 Management server on two separate computers can help in situations when one of the servers is unavailable or offline.</span></span></p>
<p><span data-ttu-id="73149-113">您也可以在多部電腦上安裝管理伺服器，以協助增加 App-V 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="73149-113">You can also help increase App-V 5.0 availability by installing the Management server on multiple computers.</span></span> <span data-ttu-id="73149-114">在這種情況下，您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="73149-114">In this scenario, a network load balancer should also be considered so that server requests are balanced.</span></span></p></li>
<li><p><span data-ttu-id="73149-115">可伸縮性：您可以根據需要新增額外的管理伺服器以支援高負荷，例如，您可以在負載平衡器後面安裝多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="73149-115">Scalability – You can add additional management servers as necessary to support a high load, for example you can install multiple servers behind a load balancer.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="73149-116">App-V 5.0 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="73149-116">App-V 5.0 Publishing Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="73149-117">App-v 5.0 發佈伺服器提供虛擬應用程式裝載與流式處理的功能。</span><span class="sxs-lookup"><span data-stu-id="73149-117">The App-V 5.0 publishing server provides functionality for virtual application hosting and streaming.</span></span> <span data-ttu-id="73149-118">發佈伺服器不需要資料庫連線，且支援下列通訊協定：</span><span class="sxs-lookup"><span data-stu-id="73149-118">The publishing server does not require a database connection and supports the following protocols:</span></span></p>
<ul>
<li><p><span data-ttu-id="73149-119">HTTP 和 HTTPS</span><span class="sxs-lookup"><span data-stu-id="73149-119">HTTP, and HTTPS</span></span></p></li>
</ul>
<p><span data-ttu-id="73149-120">您也可以在多部電腦上安裝發佈伺服器，以協助增加 App-v 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="73149-120">You can also help increase App-V 5.0 availability by installing the Publishing server on multiple computers.</span></span> <span data-ttu-id="73149-121">您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="73149-121">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="73149-122">App-V 5.0 報表伺服器</span><span class="sxs-lookup"><span data-stu-id="73149-122">App-V 5.0 Reporting Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="73149-123">App-V 5.0 報表服務器可讓獲授權的使用者執行並查看現有的 App-v 5.0 報告，以及可協助其管理 App-v 5.0 基礎結構的特定報告。</span><span class="sxs-lookup"><span data-stu-id="73149-123">The App-V 5.0 Reporting server enables authorized users to run and view existing App-V 5.0 reports and ad hoc reports that can help them manage the App-V 5.0 infrastructure.</span></span> <span data-ttu-id="73149-124">報表伺服器需要連線到 App-v 5.0 報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="73149-124">The Reporting server requires a connection to the App-V 5.0 reporting database.</span></span> <span data-ttu-id="73149-125">您也可以在多部電腦上安裝報表伺服器，以協助增加 App V 5.0 的可用性。</span><span class="sxs-lookup"><span data-stu-id="73149-125">You can also help increase App-V 5.0 availability by installing the Reporting server on multiple computers.</span></span> <span data-ttu-id="73149-126">您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="73149-126">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="73149-127">App-V 5.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="73149-127">App-V 5.0 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="73149-128">App-V 5.0 用戶端可讓使用 App-v 5.0 建立的套件在目的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="73149-128">The App-V 5.0 client enables packages created using App-V 5.0 to run on target computers.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="73149-129">**記事** 如果您使用的是 App-v 5.0 搭配電子軟體發佈（ESD），則您不需要使用 app-v 5.0 管理伺服器，但是您仍然可以利用 App-v 5.0 的報告與資料流程功能。</span><span class="sxs-lookup"><span data-stu-id="73149-129">**Note** If you are using App-V 5.0 with Electronic Software Distribution (ESD) you are not required to use the App-V 5.0 Management server, however you can still utilize the reporting and streaming functionality of App-V 5.0.</span></span>

 






## <span data-ttu-id="73149-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="73149-130">Related topics</span></span>


[<span data-ttu-id="73149-131">App-V 5.0 入門</span><span class="sxs-lookup"><span data-stu-id="73149-131">Getting Started with App-V 5.0</span></span>](getting-started-with-app-v-50--rtm.md)

 

 





