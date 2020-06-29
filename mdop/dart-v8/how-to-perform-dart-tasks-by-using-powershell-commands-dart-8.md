---
title: 如何使用 PowerShell 命令執行 DaRT 工作
description: 如何使用 PowerShell 命令執行 DaRT 工作
author: dansimp
ms.assetid: bc788b00-38c7-4f57-a832-916b68264d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f8ff87aa09555b93ca04a6ec7fa5dd4ba8504514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810473"
---
# <span data-ttu-id="d4127-103">如何使用 PowerShell 命令執行 DaRT 工作</span><span class="sxs-lookup"><span data-stu-id="d4127-103">How to Perform DaRT Tasks by Using PowerShell Commands</span></span>


<span data-ttu-id="d4127-104">Microsoft Diagnostics 與修復工具組（DaRT）8.0 提供下列所列的 Windows PowerShell Cmdlet 集合。</span><span class="sxs-lookup"><span data-stu-id="d4127-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d4127-105">系統管理員可以使用這些 PowerShell Cmdlet，從命令提示字元執行各種 DaRT 8.0 伺服器工作，而不是從 DaRT 復原影像嚮導執行。</span><span class="sxs-lookup"><span data-stu-id="d4127-105">Administrators can use these PowerShell cmdlets to perform various DaRT 8.0 server tasks from the command prompt rather than from the DaRT Recovery Image wizard.</span></span>

## <span data-ttu-id="d4127-106">使用 PowerShell 命令來管理 DaRT</span><span class="sxs-lookup"><span data-stu-id="d4127-106">To administer DaRT by using PowerShell commands</span></span>


<span data-ttu-id="d4127-107">使用這裡所述的 PowerShell Cmdlet 來管理 DaRT。</span><span class="sxs-lookup"><span data-stu-id="d4127-107">Use the PowerShell cmdlets described here to administer DaRT.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d4127-108">名稱</span><span class="sxs-lookup"><span data-stu-id="d4127-108">Name</span></span></th>
<th align="left"><span data-ttu-id="d4127-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4127-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d4127-110">複製 DartImage</span><span class="sxs-lookup"><span data-stu-id="d4127-110">Copy-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="d4127-111">在 CD、DVD 或 USB 磁片磁碟機上使用 ISO。</span><span class="sxs-lookup"><span data-stu-id="d4127-111">Burns an ISO to a CD, DVD, or USB drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d4127-112">Export-DartImage</span><span class="sxs-lookup"><span data-stu-id="d4127-112">Export-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="d4127-113">允許包含 DaRT 映射的來源 WIM 檔案轉換成 ISO 檔案。</span><span class="sxs-lookup"><span data-stu-id="d4127-113">Allows the source WIM file, which contains a DaRT image, to be converted into an ISO file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d4127-114">新-DartConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4127-114">New-DartConfiguration</span></span></p></td>
<td align="left"><p><span data-ttu-id="d4127-115">建立將 DaRT 工具組套用到 Windows 影像所需的 DaRT 設定物件。</span><span class="sxs-lookup"><span data-stu-id="d4127-115">Creates a DaRT configuration object that is needed to apply a DaRT toolset to a Windows Image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d4127-116">Set-DartImage</span><span class="sxs-lookup"><span data-stu-id="d4127-116">Set-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="d4127-117">將 DartConfiguration 物件套用至已安裝的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="d4127-117">Applies a DartConfiguration object to a mounted Windows Image.</span></span> <span data-ttu-id="d4127-118">這包括新增所有檔案、配置及套件相依性。</span><span class="sxs-lookup"><span data-stu-id="d4127-118">This includes adding all files, configuration, and package dependencies.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d4127-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4127-119">Related topics</span></span>


[<span data-ttu-id="d4127-120">使用 PowerShell 管理 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d4127-120">Administering DaRT 8.0 Using PowerShell</span></span>](administering-dart-80-using-powershell-dart-8.md)

 

 





