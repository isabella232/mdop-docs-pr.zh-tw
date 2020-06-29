---
title: AGPM 伺服器連線設定
description: AGPM 伺服器連線設定
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800239"
---
# <span data-ttu-id="e5763-103">AGPM 伺服器連線設定</span><span class="sxs-lookup"><span data-stu-id="e5763-103">AGPM Server Connection Settings</span></span>


<span data-ttu-id="e5763-104">您可以使用 [系統管理範本] 設定來針對高級群組原則管理（AGPM），集中設定適用于群組原則物件（GPO）的 [群組原則管理員] 的 [AGPM 服務器連線]。</span><span class="sxs-lookup"><span data-stu-id="e5763-104">You can use Administrative template settings for Advanced Group Policy Management (AGPM) to centrally configure AGPM Server connections for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="e5763-105">編輯 GPO 時，[User Configuration\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。</span><span class="sxs-lookup"><span data-stu-id="e5763-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\AGPM when editing a GPO.</span></span> <span data-ttu-id="e5763-106">如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。</span><span class="sxs-lookup"><span data-stu-id="e5763-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5763-107">設定</span><span class="sxs-lookup"><span data-stu-id="e5763-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="e5763-108">效果</span><span class="sxs-lookup"><span data-stu-id="e5763-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e5763-109">AGPM 服務器（所有網域）</span><span class="sxs-lookup"><span data-stu-id="e5763-109">AGPM Server (all domains)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e5763-110">如果啟用，此設定會集中設定一個 AGPM 服務器連線供所有網域使用，並停用 <strong> 群組原則管理員的 [AGPM 服務器] 索引標籤上的設定 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e5763-110">If enabled, this setting centrally configures one AGPM Server connection for use by all domains and disables the settings on the <strong>AGPM Server</strong> tab for Group Policy administrators.</span></span> <span data-ttu-id="e5763-111">針對多個 AGPM 服務器，請使用預設的伺服器設定此設定，然後 <strong> </strong> 在 [系統管理範本] 中設定 [AGPM 服務器] 設定，以覆寫其他網域的此伺服器。</span><span class="sxs-lookup"><span data-stu-id="e5763-111">For multiple AGPM Servers, configure this setting with a default server and then configure the <strong>AGPM Server</strong> setting in the Administrative template to override this server for other domains.</span></span></p>
<p><span data-ttu-id="e5763-112">如果停用或未設定，每個群組原則管理員都必須在 AGPM 的 [ <strong> Agpm 伺服器] 索引標籤上，選取要顯示每個網域的 AGPM 服務器 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e5763-112">If disabled or not configured, each Group Policy administrator must select the AGPM Server to display for each domain on the <strong>AGPM Server</strong> tab in AGPM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e5763-113">AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="e5763-113">AGPM Server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e5763-114">如果啟用，此設定會集中設定多個網域專用的 AGPM 服務器，並覆寫 <strong> 管理範本中的 [AGPM 服務器（所有網域）] </strong> 設定。</span><span class="sxs-lookup"><span data-stu-id="e5763-114">If enabled, this setting centrally configures multiple domain-specific AGPM Servers, overriding the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span> <span data-ttu-id="e5763-115">如果您的環境只需要單一的 AGPM 服務器，請 <strong> 在 [系統管理範本] 中只使用 [AGPM 服務器（所有網域）] </strong> 設定。</span><span class="sxs-lookup"><span data-stu-id="e5763-115">If your environment requires only a single AGPM Server, use only the <strong>AGPM Server (all domains)</strong> setting in the Administrative template.</span></span></p>
<p><span data-ttu-id="e5763-116">如果停用或未設定，系統會在系統 <strong> 管理範本中的 [AGPM server （所有網域）] </strong> 設定設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="e5763-116">If disabled or not configured, the <strong>AGPM Server (all domains)</strong> setting in the Administrative template configures the AGPM Server connection.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e5763-117">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e5763-117">Additional references</span></span>

-   [<span data-ttu-id="e5763-118">系統管理範本設定</span><span class="sxs-lookup"><span data-stu-id="e5763-118">Administrative Template Settings</span></span>](administrative-template-settings.md)

-   [<span data-ttu-id="e5763-119">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="e5763-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





