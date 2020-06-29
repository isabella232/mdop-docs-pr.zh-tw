---
title: 如何只允許系統管理員啟用連線群組
description: 如何只允許系統管理員啟用連線群組
author: dansimp
ms.assetid: 42ca3157-5d85-467b-a148-09404f8f737a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 083d6386f02996d35255f90958705798f2cd5fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800597"
---
# <span data-ttu-id="5b328-103">如何只允許系統管理員啟用連線群組</span><span class="sxs-lookup"><span data-stu-id="5b328-103">How to Allow Only Administrators to Enable Connection Groups</span></span>


<span data-ttu-id="5b328-104">您可以設定 App-v 用戶端，讓只有系統管理員（而非最終使用者）可以啟用或停用連線群組。</span><span class="sxs-lookup"><span data-stu-id="5b328-104">You can configure the App-V client so that only administrators (not end users) can enable or disable connection groups.</span></span> <span data-ttu-id="5b328-105">在舊版 App-v 中，您不能防止使用者執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="5b328-105">In earlier versions of App-V, you could not prevent end users from performing these tasks.</span></span>

<span data-ttu-id="5b328-106">**記事** 
**從 app-v 5.0 SP3 開始，支援這項功能。**</span><span class="sxs-lookup"><span data-stu-id="5b328-106">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="5b328-107">使用下列其中一種方法，只允許系統管理員啟用或停用連線群組。</span><span class="sxs-lookup"><span data-stu-id="5b328-107">Use one of the following methods to allow only administrators to enable or disable connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5b328-108">方法</span><span class="sxs-lookup"><span data-stu-id="5b328-108">Method</span></span></th>
<th align="left"><span data-ttu-id="5b328-109">步驟</span><span class="sxs-lookup"><span data-stu-id="5b328-109">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5b328-110">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="5b328-110">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="5b328-111">啟用位於下列 [群群組原則物件] 節點中的 [必須發佈為系統管理員] 群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="5b328-111">Enable the “Require publish as administrator” Group Policy setting, which is located in the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="5b328-112">[電腦設定 &gt; 原則] &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈</span><span class="sxs-lookup"><span data-stu-id="5b328-112">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5b328-113">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5b328-113">PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="5b328-114"><strong> </strong> 使用 <strong> – RequirePublishAsAdmin 參數執行 AppvClientConfiguration Cmdlet </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5b328-114">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>–RequirePublishAsAdmin</strong> parameter.</span></span></p>
<p><span data-ttu-id="5b328-115">參數值：</span><span class="sxs-lookup"><span data-stu-id="5b328-115">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b328-116">0-False</span><span class="sxs-lookup"><span data-stu-id="5b328-116">0 - False</span></span></p></li>
<li><p><span data-ttu-id="5b328-117">1-True</span><span class="sxs-lookup"><span data-stu-id="5b328-117">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="5b328-118">範例： </strong> ： Set-AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="5b328-118">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5b328-119">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="5b328-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="5b328-120">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="5b328-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="5b328-121">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="5b328-121">Got an App-V issue?</span></span>** <span data-ttu-id="5b328-122">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="5b328-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="5b328-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="5b328-123">Related topics</span></span>


[<span data-ttu-id="5b328-124">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="5b328-124">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





