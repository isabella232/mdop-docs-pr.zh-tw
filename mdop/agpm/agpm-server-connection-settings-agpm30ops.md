---
title: AGPM 伺服器連線設定
description: AGPM 伺服器連線設定
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800231"
---
# <span data-ttu-id="1728e-103">AGPM 伺服器連線設定</span><span class="sxs-lookup"><span data-stu-id="1728e-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="1728e-104">您可以使用 [系統管理範本] 設定來針對高級群組原則管理（AGPM），集中設定適用于群組原則物件（GPO）的 [群組原則管理員] 的 [AGPM 服務器連線]。</span><span class="sxs-lookup"><span data-stu-id="1728e-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy Object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="1728e-105">編輯 GPO 時，[User Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。</span><span class="sxs-lookup"><span data-stu-id="1728e-105">The following settings are available under User Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1728e-106">設定</span><span class="sxs-lookup"><span data-stu-id="1728e-106">Setting</span></span></th>
<th align="left"><span data-ttu-id="1728e-107">效果</span><span class="sxs-lookup"><span data-stu-id="1728e-107">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1728e-108">AGPM：指定預設的 AGPM 服務器（所有網域）</span><span class="sxs-lookup"><span data-stu-id="1728e-108">AGPM: Specify default AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1728e-109">此原則設定可讓您為所有網域指定預設的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="1728e-109">This policy setting allows you to specify a default AGPM Server for all domains.</span></span> <span data-ttu-id="1728e-110">此功能僅供 AGPM 用戶端使用，且限制群組原則管理員連線到另一個封存。</span><span class="sxs-lookup"><span data-stu-id="1728e-110">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to another archive.</span></span> <span data-ttu-id="1728e-111">您可以使用 <strong> AGPM： [指定 Agpm 伺服器] 設定來覆寫個別網域的此預設值 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1728e-111">You can override this default for individual domains using the <strong>AGPM: Specify AGPM Servers</strong> setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1728e-112">AGPM：指定 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="1728e-112">AGPM: Specify AGPM Servers</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1728e-113">此原則設定可讓您指定個別網域的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="1728e-113">This policy setting allows you to specify the AGPM Servers for individual domains.</span></span> <span data-ttu-id="1728e-114">此功能僅供 AGPM 用戶端使用，且限制群組原則管理員連線到指定網域的其他封存。</span><span class="sxs-lookup"><span data-stu-id="1728e-114">This is used only by AGPM Clients, and restricts Group Policy administrators from connecting to a different archive for the specified domain.</span></span> <span data-ttu-id="1728e-115">若要指定預設的 AGPM 服務器，請使用 <strong> AGPM： [指定預設的 Agpm 伺服器（所有網域）] </strong> 設定，並使用此原則設定來覆寫每個網域的預設值。</span><span class="sxs-lookup"><span data-stu-id="1728e-115">To specify a default AGPM Server, use the <strong>AGPM: Specify default AGPM Server (all domains)</strong> setting and use this policy setting to override the default on a per domain basis.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="1728e-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="1728e-116">Additional references</span></span>

-   [<span data-ttu-id="1728e-117">系統管理範本資料夾</span><span class="sxs-lookup"><span data-stu-id="1728e-117">Administrative Templates Folder</span></span>](administrative-templates-folder-agpm30ops.md)

-   [<span data-ttu-id="1728e-118">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="1728e-118">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





