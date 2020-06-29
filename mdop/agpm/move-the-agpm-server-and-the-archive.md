---
title: 移動 AGPM 伺服器和封存
description: 移動 AGPM 伺服器和封存
author: dansimp
ms.assetid: 13cb83c4-bb42-4e81-8660-5b7540f473d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6ae5ba9c2346caf81f5aff9f57f6b9dc97127ad1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809404"
---
# <span data-ttu-id="4f313-103">移動 AGPM 伺服器和封存</span><span class="sxs-lookup"><span data-stu-id="4f313-103">Move the AGPM Server and the Archive</span></span>


<span data-ttu-id="4f313-104">如果您要取代 AGPM 服務器和存放封存的伺服器，您必須移動 AGPM 服務和封存。</span><span class="sxs-lookup"><span data-stu-id="4f313-104">If you are replacing the AGPM Server and the server on which the archive is hosted, you must move the AGPM Service and the archive.</span></span> <span data-ttu-id="4f313-105">如果您想要的話，您可以將 AGPM 服務和封存分別放在一起。</span><span class="sxs-lookup"><span data-stu-id="4f313-105">If you prefer, you can move the AGPM Service and the archive separately.</span></span>

**<span data-ttu-id="4f313-106">注意</span><span class="sxs-lookup"><span data-stu-id="4f313-106">Note</span></span>**  
-   <span data-ttu-id="4f313-107">AGPM 服務器是主持 AGPM 服務的電腦，以及安裝 Microsoft 高級群組原則管理（伺服器）的電腦。</span><span class="sxs-lookup"><span data-stu-id="4f313-107">The AGPM Server is the computer that hosts the AGPM Service and the computer on which Microsoft Advanced Group Policy Management – Server is installed.</span></span>

-   <span data-ttu-id="4f313-108">根據預設，封存是存放在 AGPM 服務器上，但您可以指定封存路徑，將它裝載在另一個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4f313-108">By default, the archive is hosted on the AGPM Server, but you can specify an archive path to host it on another server instead.</span></span>

 

<span data-ttu-id="4f313-109">您必須擁有網域系統管理員群組成員的使用者帳戶，且有權存取前一個與新的 AGPM 服務器，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4f313-109">A user account that is a member of the Domain Admins group and has access to the previous and new AGPM Servers is required to complete this procedure.</span></span> <span data-ttu-id="4f313-110">此外，您必須為要由新的 AGPM 服務器使用的 AGPM 服務帳戶提供認證，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4f313-110">Additionally, you must provide credentials for the AGPM Service Account to be used by the new AGPM Server to complete this procedure.</span></span>

**<span data-ttu-id="4f313-111">將 AGPM 服務及封存移至不同的伺服器或伺服器</span><span class="sxs-lookup"><span data-stu-id="4f313-111">To move the AGPM Service and the archive to a different server or servers</span></span>**

1.  <span data-ttu-id="4f313-112">備份封存。</span><span class="sxs-lookup"><span data-stu-id="4f313-112">Back up the archive.</span></span> <span data-ttu-id="4f313-113">如需詳細資訊，請參閱[備份](back-up-the-archive.md)封存。</span><span class="sxs-lookup"><span data-stu-id="4f313-113">For more information, see [Back Up the Archive](back-up-the-archive.md).</span></span>

2.  <span data-ttu-id="4f313-114">移動 AGPM 服務：</span><span class="sxs-lookup"><span data-stu-id="4f313-114">Move the AGPM Service:</span></span>

    1.  <span data-ttu-id="4f313-115">停止 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="4f313-115">Stop the AGPM Service.</span></span> <span data-ttu-id="4f313-116">如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="4f313-116">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

    2.  <span data-ttu-id="4f313-117">在新伺服器上安裝 Microsoft 高級群組原則管理-伺服器，該伺服器將主持 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="4f313-117">Install Microsoft Advanced Group Policy Management - Server on the new server that will host the AGPM Service.</span></span> <span data-ttu-id="4f313-118">在此程式中，您會指定新的封存路徑、封存相對於 AGPM 服務器的位置。</span><span class="sxs-lookup"><span data-stu-id="4f313-118">During this process, you specify the new archive path, the location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="4f313-119">如需詳細資訊，請參閱 Microsoft 高級群組原則管理3.0 （ <https://go.microsoft.com/fwlink/?LinkId=132706> ）和 Microsoft 高級群組原則管理的規劃指南（）的逐步指南 <https://go.microsoft.com/fwlink/?LinkId=141871> 。</span><span class="sxs-lookup"><span data-stu-id="4f313-119">For more information, see Step-by-Step Guide for Microsoft Advanced Group Policy Management 3.0 (<https://go.microsoft.com/fwlink/?LinkId=132706>) and Planning Guide for Microsoft Advanced Group Policy Management (<https://go.microsoft.com/fwlink/?LinkId=141871>).</span></span>

    3.  <span data-ttu-id="4f313-120">AGPM 管理員（完全控制）必須針對將使用新的 AGPM 服務器並移除舊的 AGPM 服務器連線的所有群組原則管理員，設定 AGPM 服務器連線，否則每個群組原則管理員都必須手動設定新的 AGPM 服務器連線，並移除舊的 AGPM 服務器連線（適用于電腦上的 AGPM 管理單元）。</span><span class="sxs-lookup"><span data-stu-id="4f313-120">Either an AGPM Administrator (Full Control) must configure the AGPM Server connection for all Group Policy administrators who will use the new AGPM Server and remove the connection for the old AGPM Server, or else each Group Policy administrator must manually configure the new AGPM Server connection and remove the old AGPM Server connection for the AGPM snap-in on their computer.</span></span> <span data-ttu-id="4f313-121">如需詳細資訊，請參閱[設定 AGPM 服務器](configure-agpm-server-connections-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="4f313-121">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

        <span data-ttu-id="4f313-122">**記事** 最佳做法，您應該從先前的 AGPM 服務器卸載 Microsoft 高級群組原則管理-伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f313-122">**Note** As a best practice, you should uninstall Microsoft Advanced Group Policy Management – Server from the previous AGPM Server.</span></span> <span data-ttu-id="4f313-123">這可確保 AGPM 服務無法在該伺服器上無意間重新開機，而且如果有任何 AGPM 服務器連線，可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="4f313-123">This will ensure that the AGPM Service cannot be unintentionally restarted on that server and potentially cause confusion if any AGPM Server connections to it remain.</span></span>

         

3.  <span data-ttu-id="4f313-124">將封存從備份複製到將主持封存的新伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f313-124">Copy the archive from the backup to the new server that will host the archive.</span></span> <span data-ttu-id="4f313-125">如需詳細資訊，請參閱[從備份還原](restore-the-archive-from-a-backup.md)封存。</span><span class="sxs-lookup"><span data-stu-id="4f313-125">For more information, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup.md).</span></span>

    <span data-ttu-id="4f313-126">**重要** 如果您移動封存，但不同時移動 AGPM 服務：</span><span class="sxs-lookup"><span data-stu-id="4f313-126">**Important** If you moved the archive without moving the AGPM Service at the same time:</span></span>

    1.  <span data-ttu-id="4f313-127">您必須變更封存路徑，以指向與 AGPM 服務器相關的封存新位置。</span><span class="sxs-lookup"><span data-stu-id="4f313-127">You must change the archive path to point to the new location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="4f313-128">如需詳細資訊，請參閱[修改 AGPM 服務](modify-the-agpm-service-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="4f313-128">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md).</span></span>

    2.  <span data-ttu-id="4f313-129">您必須重新輸入並確認 [**網域委派**] 索引標籤上的密碼。如需詳細資訊，請參閱[設定電子郵件通知](configure-e-mail-notification-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="4f313-129">You must re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm30ops.md).</span></span>

     

### <span data-ttu-id="4f313-130">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4f313-130">Additional references</span></span>

-   [<span data-ttu-id="4f313-131">備份封存</span><span class="sxs-lookup"><span data-stu-id="4f313-131">Back Up the Archive</span></span>](back-up-the-archive.md)

-   [<span data-ttu-id="4f313-132">從備份還原封存</span><span class="sxs-lookup"><span data-stu-id="4f313-132">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup.md)

-   [<span data-ttu-id="4f313-133">設定 AGPM 伺服器連線</span><span class="sxs-lookup"><span data-stu-id="4f313-133">Configure AGPM Server Connections</span></span>](configure-agpm-server-connections-agpm30ops.md)

-   [<span data-ttu-id="4f313-134">修改 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="4f313-134">Modify the AGPM Service</span></span>](modify-the-agpm-service-agpm30ops.md)

-   <span data-ttu-id="4f313-135">Microsoft 高級群組原則管理3.0 （）的逐步指南 <https://go.microsoft.com/fwlink/?LinkId=132706></span><span class="sxs-lookup"><span data-stu-id="4f313-135">Step-by-Step Guide for Microsoft Advanced Group Policy Management 3.0 (<https://go.microsoft.com/fwlink/?LinkId=132706>)</span></span>

-   <span data-ttu-id="4f313-136">Microsoft 高級群組原則管理的規劃指南（ <https://go.microsoft.com/fwlink/?LinkId=141871> ）</span><span class="sxs-lookup"><span data-stu-id="4f313-136">Planning Guide for Microsoft Advanced Group Policy Management (<https://go.microsoft.com/fwlink/?LinkId=141871>)</span></span>

-   [<span data-ttu-id="4f313-137">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="4f313-137">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





