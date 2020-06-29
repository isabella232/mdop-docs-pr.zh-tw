---
title: 管理封存
description: 管理封存
author: dansimp
ms.assetid: b11a3d71-74ea-4dd7-b243-6f2880b7af2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 682d720b4095dbfa6a7cc4d868109f57c4f54641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802665"
---
# <span data-ttu-id="ac7bb-103">管理封存</span><span class="sxs-lookup"><span data-stu-id="ac7bb-103">Managing the Archive</span></span>


<span data-ttu-id="ac7bb-104">在先進的群組原則管理（AGPM）中，以 AGPM 管理員（完全控制）為目標，您可以管理封存的存取權，以及限制儲存在封存中的每個群組原則物件（GPO）版本數的選項。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-104">In Advanced Group Policy Management (AGPM), as an AGPM Administrator (Full Control), you manage access to the archive and have the option to limit the number of versions of each Group Policy Object (GPO) stored in the archive.</span></span> <span data-ttu-id="ac7bb-105">您可以在網域層級或 GPO 層級，委派對封存中 Gpo 的存取權。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-105">You can delegate access to GPOs in the archive at the domain level or GPO level.</span></span> <span data-ttu-id="ac7bb-106">此外，您也可以備份封存，讓您可以在發生災難時將它復原。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-106">Additionally, you can back up the archive so that you may be able to recover it if a disaster occurs.</span></span>

<span data-ttu-id="ac7bb-107">在 AGPM 系統管理員中，您可以將 GPO 匯出至檔案、將檔案複製到另一個樹林，然後將該 GPO 匯入到該目錄林中的網域。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-107">As an AGPM Administrator, you can export a GPO to a file, copy the file to another forest, and then import the GPO into a domain in that forest.</span></span> <span data-ttu-id="ac7bb-108">與編輯工具不同，您可以在建立 GPO 備份時，將原則設定直接匯入到新的受管理 GPO 中。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-108">Unlike an Editor, you can import policy settings from a GPO backup directly into a new controlled GPO when you create it.</span></span> <span data-ttu-id="ac7bb-109">如需如何匯出 GPO 的相關資訊，請參閱[將 Gpo 匯出至](export-a-gpo-to-a-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-109">For information about how to export a GPO, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

-   [<span data-ttu-id="ac7bb-110">委派管理封存的網域層級存取權</span><span class="sxs-lookup"><span data-stu-id="ac7bb-110">Delegate Domain-Level Access to the Archive</span></span>](delegate-domain-level-access-to-the-archive-agpm40.md)

-   [<span data-ttu-id="ac7bb-111">委派管理封存中個別 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="ac7bb-111">Delegate Access to an Individual GPO in the Archive</span></span>](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)

-   [<span data-ttu-id="ac7bb-112">限制儲存的 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="ac7bb-112">Limit the GPO Versions Stored</span></span>](limit-the-gpo-versions-stored-agpm40.md)

-   [<span data-ttu-id="ac7bb-113">從檔案匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="ac7bb-113">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-agpmadmin.md)

-   [<span data-ttu-id="ac7bb-114">備份封存</span><span class="sxs-lookup"><span data-stu-id="ac7bb-114">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="ac7bb-115">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="ac7bb-115">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

### <span data-ttu-id="ac7bb-116">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="ac7bb-116">Additional references</span></span>

-   <span data-ttu-id="ac7bb-117">如需有關如何委派對生產環境中 Gpo 的存取權的資訊，請參閱[委派生產環境的存取權](delegate-access-to-the-production-environment-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-117">For information about how to delegate access to GPOs in the production environment, see [Delegate Access to the Production Environment](delegate-access-to-the-production-environment-agpm40.md).</span></span>

-   <span data-ttu-id="ac7bb-118">如需如何移動封存的相關資訊，請參閱[移動 AGPM 服務器和](move-the-agpm-server-and-the-archive-agpm40.md)封存。</span><span class="sxs-lookup"><span data-stu-id="ac7bb-118">For information about how to move the archive, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

-   [<span data-ttu-id="ac7bb-119">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="ac7bb-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 





