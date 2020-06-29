---
title: 備份封存
description: 備份封存
author: dansimp
ms.assetid: 400176da-3518-4475-ad19-c96cda6ca7ba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a75099e7a6624850ee0511cf65feddf63909a0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802125"
---
# <span data-ttu-id="feaa8-103">備份封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-103">Back Up the Archive</span></span>


<span data-ttu-id="feaa8-104">若要在災難發生時協助恢復高級群組原則管理（AGPM），請經常備份 AGPM 系統管理員（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="feaa8-104">To help in the recovery of the archive for Advanced Group Policy Management (AGPM) if there is a disaster, an AGPM Administrator (Full Control) should back up the archive frequently.</span></span> <span data-ttu-id="feaa8-105">根據預設，會在%ProgramData%\\Microsoft\\AGPM. 中建立封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-105">By default, the archive is created in %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="feaa8-106">不過，您可以在設定 Microsoft 高級群組原則管理-伺服器期間指定不同的路徑。</span><span class="sxs-lookup"><span data-stu-id="feaa8-106">However, you can specify a different path during the setup of Microsoft Advanced Group Policy Management - Server.</span></span>

<span data-ttu-id="feaa8-107">可存取 AGPM 服務器的使用者帳戶（已安裝 AGPM 服務的電腦），以及包含封存的資料夾需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="feaa8-107">A user account that has access to both the AGPM Server—the computer on which the AGPM Service is installed—and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="feaa8-108">若要備份封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-108">To back up the archive</span></span>**

1.  <span data-ttu-id="feaa8-109">停止 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="feaa8-109">Stop the AGPM Service.</span></span> <span data-ttu-id="feaa8-110">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="feaa8-110">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

2.  <span data-ttu-id="feaa8-111">使用 Windows 資源管理器、Xcopy、Windows Server®備份或其他備份工具來備份 [封存] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="feaa8-111">Back up the archive folder by using Windows Explorer, Xcopy, Windows Server® Backup, or another backup tool.</span></span> <span data-ttu-id="feaa8-112">請務必備份隱藏、系統和唯讀檔案。</span><span class="sxs-lookup"><span data-stu-id="feaa8-112">Make sure that you back up hidden, system, and read-only files.</span></span>

3.  <span data-ttu-id="feaa8-113">將封存備份儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="feaa8-113">Store the archive backup in a secure location.</span></span>

4.  <span data-ttu-id="feaa8-114">重新開機 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="feaa8-114">Restart the AGPM Service.</span></span> <span data-ttu-id="feaa8-115">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="feaa8-115">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

<span data-ttu-id="feaa8-116">**記事** 如果 AGPM 管理員不經常備份封存，則封存備份中的群組原則物件（Gpo）不會是最新的。</span><span class="sxs-lookup"><span data-stu-id="feaa8-116">**Note** If an AGPM Administrator backs up the archive infrequently, the Group Policy Objects (GPOs) in the archive backup will not be current.</span></span> <span data-ttu-id="feaa8-117">若要更有效地確保封存備份是最新的，請在組織的每日備份策略中備份封存。</span><span class="sxs-lookup"><span data-stu-id="feaa8-117">To better ensure that the archive backup is current, back up the archive as part of your organization’s daily backup strategy.</span></span>

 

### <span data-ttu-id="feaa8-118">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="feaa8-118">Additional references</span></span>

-   [<span data-ttu-id="feaa8-119">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-119">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup.md)

-   [<span data-ttu-id="feaa8-120">移動 AGPM 伺服器和封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-120">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive.md)

-   [<span data-ttu-id="feaa8-121">管理封存</span><span class="sxs-lookup"><span data-stu-id="feaa8-121">Managing the Archive</span></span>](managing-the-archive.md)

 

 





