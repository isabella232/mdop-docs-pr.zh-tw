---
title: App-V 5.1 的高階架構
description: App-V 5.1 的高階架構
author: dansimp
ms.assetid: 90406361-55b8-40b7-85c0-449436789d4c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8044c6ae9af4673ec12b47cf3b8fa73a134d9cca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800614"
---
# <span data-ttu-id="687f4-103">App-V 5.1 的高階架構</span><span class="sxs-lookup"><span data-stu-id="687f4-103">High Level Architecture for App-V 5.1</span></span>


<span data-ttu-id="687f4-104">使用下列資訊來協助您簡化 Microsoft Application Virtualization （App-v）5.1 部署。</span><span class="sxs-lookup"><span data-stu-id="687f4-104">Use the following information to help you simplify you Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

## <span data-ttu-id="687f4-105">架構概述</span><span class="sxs-lookup"><span data-stu-id="687f4-105">Architecture Overview</span></span>


<span data-ttu-id="687f4-106">典型的 App-v 5.1 實現是由下列元素所組成。</span><span class="sxs-lookup"><span data-stu-id="687f4-106">A typical App-V 5.1 implementation consists of the following elements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="687f4-107">元素</span><span class="sxs-lookup"><span data-stu-id="687f4-107">Element</span></span></th>
<th align="left"><span data-ttu-id="687f4-108">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="687f4-108">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="687f4-109">App-V 5.1 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="687f4-109">App-V 5.1 Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="687f4-110">App-v 5.1 管理伺服器提供 App-V 5.1 基礎結構的整體管理功能。</span><span class="sxs-lookup"><span data-stu-id="687f4-110">The App-V 5.1 Management server provides overall management functionality for the App-V 5.1 infrastructure.</span></span> <span data-ttu-id="687f4-111">此外，您也可以在您的環境中安裝一個以上的管理伺服器實例，提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="687f4-111">Additionally, you can install more than one instance of the management server in your environment which provides the following benefits:</span></span></p>
<ul>
<li><p><span data-ttu-id="687f4-112">容錯與高可用性–在兩部不同的電腦上安裝和設定 App-v 5.1 管理伺服器，可在其中一個伺服器無法使用或離線時協助進行。</span><span class="sxs-lookup"><span data-stu-id="687f4-112">Fault Tolerance and High Availability – Installing and configuring the App-V 5.1 Management server on two separate computers can help in situations when one of the servers is unavailable or offline.</span></span></p>
<p><span data-ttu-id="687f4-113">您也可以在多部電腦上安裝管理伺服器，以協助增加 App-V 5.1 的可用性。</span><span class="sxs-lookup"><span data-stu-id="687f4-113">You can also help increase App-V 5.1 availability by installing the Management server on multiple computers.</span></span> <span data-ttu-id="687f4-114">在這種情況下，您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="687f4-114">In this scenario, a network load balancer should also be considered so that server requests are balanced.</span></span></p></li>
<li><p><span data-ttu-id="687f4-115">可伸縮性：您可以根據需要新增額外的管理伺服器以支援高負荷，例如，您可以在負載平衡器後面安裝多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="687f4-115">Scalability – You can add additional management servers as necessary to support a high load, for example you can install multiple servers behind a load balancer.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="687f4-116">App-V 5.1 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="687f4-116">App-V 5.1 Publishing Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="687f4-117">App-v 5.1 發佈伺服器提供虛擬應用程式裝載與流式處理的功能。</span><span class="sxs-lookup"><span data-stu-id="687f4-117">The App-V 5.1 publishing server provides functionality for virtual application hosting and streaming.</span></span> <span data-ttu-id="687f4-118">發佈伺服器不需要資料庫連線，且支援下列通訊協定：</span><span class="sxs-lookup"><span data-stu-id="687f4-118">The publishing server does not require a database connection and supports the following protocols:</span></span></p>
<ul>
<li><p><span data-ttu-id="687f4-119">HTTP 和 HTTPS</span><span class="sxs-lookup"><span data-stu-id="687f4-119">HTTP, and HTTPS</span></span></p></li>
</ul>
<p><span data-ttu-id="687f4-120">您也可以在多部電腦上安裝發佈伺服器，以協助增加 App-v 5.1 的可用性。</span><span class="sxs-lookup"><span data-stu-id="687f4-120">You can also help increase App-V 5.1 availability by installing the Publishing server on multiple computers.</span></span> <span data-ttu-id="687f4-121">您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="687f4-121">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="687f4-122">App-V 5.1 報表伺服器</span><span class="sxs-lookup"><span data-stu-id="687f4-122">App-V 5.1 Reporting Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="687f4-123">App-V 5.1 報表服務器可讓獲授權的使用者執行並查看現有的 App-v 5.1 報告，以及可協助其管理 App-v 5.1 基礎結構的特定報告。</span><span class="sxs-lookup"><span data-stu-id="687f4-123">The App-V 5.1 Reporting server enables authorized users to run and view existing App-V 5.1 reports and ad hoc reports that can help them manage the App-V 5.1 infrastructure.</span></span> <span data-ttu-id="687f4-124">報表伺服器需要連線到 App-v 5.1 報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="687f4-124">The Reporting server requires a connection to the App-V 5.1 reporting database.</span></span> <span data-ttu-id="687f4-125">您也可以在多部電腦上安裝報表伺服器，以協助增加 App V 5.1 的可用性。</span><span class="sxs-lookup"><span data-stu-id="687f4-125">You can also help increase App-V 5.1 availability by installing the Reporting server on multiple computers.</span></span> <span data-ttu-id="687f4-126">您也應該考慮使用網路負載平衡器，以便平衡伺服器的要求。</span><span class="sxs-lookup"><span data-stu-id="687f4-126">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="687f4-127">App-V 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="687f4-127">App-V 5.1 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="687f4-128">App-V 5.1 用戶端可讓使用 App-v 5.1 建立的套件在目的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="687f4-128">The App-V 5.1 client enables packages created using App-V 5.1 to run on target computers.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="687f4-129">**記事** 如果您使用的是 App-v 5.1 搭配電子軟體發佈（ESD），則您不需要使用 app-v 5.1 管理伺服器，但是您仍然可以利用 App-v 5.1 的報告與資料流程功能。</span><span class="sxs-lookup"><span data-stu-id="687f4-129">**Note** If you are using App-V 5.1 with Electronic Software Distribution (ESD) you are not required to use the App-V 5.1 Management server, however you can still utilize the reporting and streaming functionality of App-V 5.1.</span></span>

 






## <span data-ttu-id="687f4-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="687f4-130">Related topics</span></span>


[<span data-ttu-id="687f4-131">App-V 5.1 入門</span><span class="sxs-lookup"><span data-stu-id="687f4-131">Getting Started with App-V 5.1</span></span>](getting-started-with-app-v-51.md)

 

 





