---
title: 檢查清單管理 AGPM 服務器與封存
description: 檢查清單管理 AGPM 服務器與封存
author: dansimp
ms.assetid: 0b2eb536-c3cc-462f-a42f-27a53f57bc55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f872a476a4a8ddd93546778c6278c175ec715850
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802102"
---
# <span data-ttu-id="9d7f3-103">檢查清單︰管理 AGPM 伺服器與封存</span><span class="sxs-lookup"><span data-stu-id="9d7f3-103">Checklist: Administer the AGPM Server and Archive</span></span>


<span data-ttu-id="9d7f3-104">在 [高級組原則管理] （AGPM）中，AGPM 服務和封存都是由 AGPM 管理員（完全控制）來管理。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-104">In Advanced Group Policy Management (AGPM), both the AGPM Service and the archive are managed by AGPM Administrators (Full Control).</span></span> <span data-ttu-id="9d7f3-105">下列是 AGPM 系統管理員的一般工作。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-105">The following are typical tasks for an AGPM Administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9d7f3-106">常用任務</span><span class="sxs-lookup"><span data-stu-id="9d7f3-106">Frequent Task</span></span></th>
<th align="left"><span data-ttu-id="9d7f3-107">參考</span><span class="sxs-lookup"><span data-stu-id="9d7f3-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7f3-108">委派對封存中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-108">Delegate access to Group Policy Objects (GPOs) in the archive.</span></span></p></td>
<td align="left"><p><a href="delegate-domain-level-access-to-the-archive-agpm30ops.md" data-raw-source="[Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm30ops.md)"><span data-ttu-id="9d7f3-109">委派管理封存的網域層級存取權</span><span class="sxs-lookup"><span data-stu-id="9d7f3-109">Delegate Domain-Level Access to the Archive</span></span></a></p>
<p><a href="delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md" data-raw-source="[Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md)"><span data-ttu-id="9d7f3-110">委派管理封存中個別 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="9d7f3-110">Delegate Access to an Individual GPO in the Archive</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9d7f3-111">備份封存以啟用災害復原。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-111">Back up the archive to enable disaster recovery.</span></span></p></td>
<td align="left"><p><a href="back-up-the-archive.md" data-raw-source="[Back Up the Archive](back-up-the-archive.md)"><span data-ttu-id="9d7f3-112">備份封存</span><span class="sxs-lookup"><span data-stu-id="9d7f3-112">Back Up the Archive</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9d7f3-113">不常見的任務</span><span class="sxs-lookup"><span data-stu-id="9d7f3-113">Infrequent Task</span></span></th>
<th align="left"><span data-ttu-id="9d7f3-114">參考</span><span class="sxs-lookup"><span data-stu-id="9d7f3-114">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7f3-115">從備份還原封存，以從災難中復原。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-115">Restore the archive from a backup to recover from a disaster.</span></span></p></td>
<td align="left"><p><a href="restore-the-archive-from-a-backup.md" data-raw-source="[Restore the Archive from a Backup](restore-the-archive-from-a-backup.md)"><span data-ttu-id="9d7f3-116">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="9d7f3-116">Restore the Archive from a Backup</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9d7f3-117">將 AGPM 服務、封存或兩者移至不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-117">Move the AGPM Service, the archive, or both to a different server.</span></span></p></td>
<td align="left"><p><a href="move-the-agpm-server-and-the-archive.md" data-raw-source="[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive.md)"><span data-ttu-id="9d7f3-118">移動 AGPM 伺服器和封存</span><span class="sxs-lookup"><span data-stu-id="9d7f3-118">Move the AGPM Server and the Archive</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7f3-119">變更封存路徑、AGPM 服務帳戶或 AGPM 服務偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-119">Change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span></p></td>
<td align="left"><p><a href="modify-the-agpm-service-agpm30ops.md" data-raw-source="[Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md)"><span data-ttu-id="9d7f3-120">修改 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9d7f3-120">Modify the AGPM Service</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9d7f3-121">疑難排解 AGPM 服務器的常見問題。</span><span class="sxs-lookup"><span data-stu-id="9d7f3-121">Troubleshoot common problems with the AGPM Server.</span></span></p></td>
<td align="left"><p><a href="troubleshooting-advanced-group-policy-management-agpm30ops.md" data-raw-source="[Troubleshooting Advanced Group Policy Management](troubleshooting-advanced-group-policy-management-agpm30ops.md)"><span data-ttu-id="9d7f3-122">疑難排解進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="9d7f3-122">Troubleshooting Advanced Group Policy Management</span></span></a></p>
<p><a href="configure-logging-and-tracing-agpm30ops.md" data-raw-source="[Configure Logging and Tracing](configure-logging-and-tracing-agpm30ops.md)"><span data-ttu-id="9d7f3-123">設定記錄和追蹤</span><span class="sxs-lookup"><span data-stu-id="9d7f3-123">Configure Logging and Tracing</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="9d7f3-124">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="9d7f3-124">Additional references</span></span>

-   [<span data-ttu-id="9d7f3-125">Microsoft 進階群組原則管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="9d7f3-125">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





