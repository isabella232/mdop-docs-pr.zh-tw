---
title: 記錄和追蹤設定
description: 記錄和追蹤設定
author: dansimp
ms.assetid: 66d03306-80d8-4132-bf71-2827157b1fc9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c58da00e7030c5e4cb3e4d5c4e5bbffa0c754233
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802681"
---
# <span data-ttu-id="4ebc6-103">記錄和追蹤設定</span><span class="sxs-lookup"><span data-stu-id="4ebc6-103">Logging and Tracing Settings</span></span>


<span data-ttu-id="4ebc6-104">[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定適用于您的 AGPM 服務器和用戶端的記錄和追蹤選項，這些設定會套用至其中的群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="4ebc6-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure logging and tracing options for AGPM Servers and clients to which a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="4ebc6-105">編輯 GPO 時，在 [電腦 Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。</span><span class="sxs-lookup"><span data-stu-id="4ebc6-105">The following setting is available under Computer Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span>

<span data-ttu-id="4ebc6-106">**追蹤檔案位置**：</span><span class="sxs-lookup"><span data-stu-id="4ebc6-106">**Trace file locations**:</span></span>

-   <span data-ttu-id="4ebc6-107">用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="4ebc6-107">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

-   <span data-ttu-id="4ebc6-108">伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="4ebc6-108">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ebc6-109">設定</span><span class="sxs-lookup"><span data-stu-id="4ebc6-109">Setting</span></span></th>
<th align="left"><span data-ttu-id="4ebc6-110">效果</span><span class="sxs-lookup"><span data-stu-id="4ebc6-110">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4ebc6-111">AGPM：設定記錄</span><span class="sxs-lookup"><span data-stu-id="4ebc6-111">AGPM: Configure logging</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ebc6-112">此原則設定可讓您開啟和設定 AGPM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="4ebc6-112">This policy setting allows you to turn on and configure logging for AGPM.</span></span> <span data-ttu-id="4ebc6-113">此設定會影響 AGPM 的用戶端和伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="4ebc6-113">This setting affects both client and server components of AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4ebc6-114">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4ebc6-114">Additional references</span></span>

-   [<span data-ttu-id="4ebc6-115">系統管理範本資料夾</span><span class="sxs-lookup"><span data-stu-id="4ebc6-115">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm40.md)

 

 





