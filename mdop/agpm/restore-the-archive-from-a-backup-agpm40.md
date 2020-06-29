---
title: 從備份還原封存
description: 從備份還原封存
author: dansimp
ms.assetid: b83f6173-a236-4da2-b16e-8df20920d4cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a1b7039ad587cf9c8d7f914fe3b963e12ba8949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801801"
---
# <span data-ttu-id="194e2-103">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="194e2-103">Restore the Archive from a Backup</span></span>


<span data-ttu-id="194e2-104">如果發生災難，且 [高級] 群組原則管理（AGPM）的封存遭到損毀或損毀，則 AGPM 管理員（完全控制）可以先預先準備好的備份複本，然後從網域的生產環境中匯入，而不是封存中的任何群組原則物件（Gpo），或是生產環境中的版本比封存中的版本要更新。</span><span class="sxs-lookup"><span data-stu-id="194e2-104">If a disaster occurs and the archive for Advanced Group Policy Management (AGPM) is damaged or destroyed, an AGPM Administrator (Full Control) can restore the archive from a backup copy prepared in advance and then import from the production environment of the domain any Group Policy Objects (GPOs) that are not in the archive or for which the version in production is more current than that in the archive.</span></span> <span data-ttu-id="194e2-105">如需有關如何將封存備份還原到其他伺服器的詳細資訊，請參閱[移動 AGPM 服務器和](move-the-agpm-server-and-the-archive-agpm40.md)封存。</span><span class="sxs-lookup"><span data-stu-id="194e2-105">For information about how to restore an archive backup to a different server, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

<span data-ttu-id="194e2-106">可存取 AGPM 服務器的使用者帳戶（安裝 AGPM 服務的電腦），以及包含封存的資料夾必須完成此程式。</span><span class="sxs-lookup"><span data-stu-id="194e2-106">A user account that has access to the AGPM Server (the computer on which the AGPM Service is installed) and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="194e2-107">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="194e2-107">To restore the archive from a backup</span></span>**

1.  <span data-ttu-id="194e2-108">停止 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="194e2-108">Stop the AGPM Service.</span></span> <span data-ttu-id="194e2-109">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="194e2-109">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

2.  <span data-ttu-id="194e2-110">移除現有封存。</span><span class="sxs-lookup"><span data-stu-id="194e2-110">Remove the existing archive.</span></span> <span data-ttu-id="194e2-111">根據預設，[封存] 資料夾是%ProgramData%\\Microsoft\\AGPM，不過安裝 Microsoft 高級群組原則管理的 AGPM 管理員，伺服器可能在安裝期間輸入了不同的位置。</span><span class="sxs-lookup"><span data-stu-id="194e2-111">By default, the archive folder is %ProgramData%\\Microsoft\\AGPM, however the AGPM Administrator who installed Microsoft Advanced Group Policy Management - Server may have entered a different location during setup.</span></span>

3.  <span data-ttu-id="194e2-112">設定封存路徑、AGPM 服務帳戶、封存擁有者和偵聽埠，以重新建立 [封存] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="194e2-112">Re-create the archive folder by configuring the archive path, AGPM Service Account, Archive Owner, and listening port.</span></span> <span data-ttu-id="194e2-113">您不需要使用在原始安裝期間所使用的相同值。</span><span class="sxs-lookup"><span data-stu-id="194e2-113">Using the same values as used during the original installation is not necessary.</span></span> <span data-ttu-id="194e2-114">如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="194e2-114">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

4.  <span data-ttu-id="194e2-115">將封存備份的內容複寫到 [封存] 資料夾，複製子資料夾和檔案，以確定每個子資料夾和檔案都繼承 [封存] 資料夾的許可權。</span><span class="sxs-lookup"><span data-stu-id="194e2-115">Copy the contents of the archive backup to the archive folder, copying the subfolders and files to make sure that each subfolder and file inherits the permissions of the archive folder.</span></span> <span data-ttu-id="194e2-116">請小心不要覆寫 [封存] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="194e2-116">Be careful not to overwrite the archive folder.</span></span>

5.  <span data-ttu-id="194e2-117">如果您不確定封存備份中的 GPO 是否比生產中該 GPO 的複本還新，請產生差異報告並比較其設定。</span><span class="sxs-lookup"><span data-stu-id="194e2-117">If you not sure about whether a GPO in the archive backup is more current than the copy of that GPO in production, generate a difference report and compare their settings.</span></span> <span data-ttu-id="194e2-118">如需詳細資訊，請參閱[識別 gpo、Gpo 版本或範本之間的差異](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="194e2-118">For more information, see [Identify Differences Between GPOs, GPO Versions, or Templates](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md).</span></span>

6.  <span data-ttu-id="194e2-119">重新開機 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="194e2-119">Restart the AGPM Service.</span></span> <span data-ttu-id="194e2-120">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="194e2-120">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

### <span data-ttu-id="194e2-121">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="194e2-121">Additional references</span></span>

-   [<span data-ttu-id="194e2-122">備份封存</span><span class="sxs-lookup"><span data-stu-id="194e2-122">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="194e2-123">移動 AGPM 伺服器和封存</span><span class="sxs-lookup"><span data-stu-id="194e2-123">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive-agpm40.md)

-   [<span data-ttu-id="194e2-124">管理封存</span><span class="sxs-lookup"><span data-stu-id="194e2-124">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





