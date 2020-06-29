---
title: 從 MBAM 2.5 升級至 MBAM 2.5 SP1 服務版本更新
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800176"
---
# <span data-ttu-id="a026f-102">從 MBAM 2.5 升級至 MBAM 2.5 SP1 服務版本更新</span><span class="sxs-lookup"><span data-stu-id="a026f-102">Upgrade from MBAM 2.5 to MBAM 2.5 SP1 Servicing Release Update</span></span>

<span data-ttu-id="a026f-103">本文提供逐步指示，以升級 Microsoft BitLocker 管理和監控（MBAM）2.5，以 MBAM 2.5 Service Pack 1 （SP1）搭配[Microsoft 桌面優化套件（MDOP），在獨立設定中可能會2019服務更新](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)。</span><span class="sxs-lookup"><span data-stu-id="a026f-103">This article provides step-by-step instructions to upgrade Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 to MBAM 2.5 Service Pack 1 (SP1) together with the [Microsoft Desktop Optimization Pack (MDOP) May 2019 servicing update](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack) in a standalone configuration.</span></span>

<span data-ttu-id="a026f-104">在本指南中，我們將使用雙伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="a026f-104">In this guide, we will use a two-server configuration.</span></span> <span data-ttu-id="a026f-105">一台伺服器將是執行 Microsoft SQL Server 2016 的資料庫伺服器。</span><span class="sxs-lookup"><span data-stu-id="a026f-105">One server will be a database server that's running Microsoft SQL Server 2016.</span></span> <span data-ttu-id="a026f-106">這個伺服器將裝載 MBAM 資料庫與報告。</span><span class="sxs-lookup"><span data-stu-id="a026f-106">This server will host the MBAM databases and reports.</span></span> <span data-ttu-id="a026f-107">另一台伺服器將是 Windows Server 2012 R2 web 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a026f-107">The other server will be a Windows Server 2012 R2 web server.</span></span> <span data-ttu-id="a026f-108">這個伺服器將主持「管理和監控」和「自助服務入口網站」。</span><span class="sxs-lookup"><span data-stu-id="a026f-108">This server will host "Administration and Monitoring" and "Self-Service Portal."</span></span>

## <span data-ttu-id="a026f-109">準備升級 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a026f-109">Prepare to upgrade MBAM 2.5 SP1</span></span>

### <span data-ttu-id="a026f-110">瞭解您環境中的 MBAM 伺服器</span><span class="sxs-lookup"><span data-stu-id="a026f-110">Know the MBAM servers in your environment</span></span>

1. <span data-ttu-id="a026f-111">SQL Server 資料庫引擎：託管 MBAM 資料庫的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a026f-111">SQL Server Database Engine: Server that hosts the MBAM databases.</span></span>
2. <span data-ttu-id="a026f-112">SQL Server Reporting Services：託管 MBAM 報表的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a026f-112">SQL Server Reporting Services: Server that hosts the MBAM reports.</span></span>
3. <span data-ttu-id="a026f-113">網際網路 Information Services （IIS） web 伺服器：託管 MBAM Web 應用程式和 MBAM 服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a026f-113">Internet Information Services (IIS) web servers: Server that hosts MBAM Web Applications and MBAM services.</span></span>
4. <span data-ttu-id="a026f-114">可選Microsoft System Center Configuration Manager 主要網站伺服器：此伺服器上執行的 MBAM 設定應用程式，可將 MBAM 報表與 Configuration Manager 整合。</span><span class="sxs-lookup"><span data-stu-id="a026f-114">(Optional) Microsoft System Center Configuration Manager primary site server: The MBAM configuration application is run on this server to integrate MBAM reports with Configuration Manager.</span></span> <span data-ttu-id="a026f-115">然後，這些報告就會與 Configuration Manager SQL Server Reporting Services （SSRS）實例上的現有 Configuration Manager 報告合併。</span><span class="sxs-lookup"><span data-stu-id="a026f-115">These reports are then merged with existing Configuration Manager reports on the Configuration Manager SQL Server Reporting Services (SSRS) instance.</span></span>

### <span data-ttu-id="a026f-116">識別服務帳戶、群組、伺服器名稱和報告 URL</span><span class="sxs-lookup"><span data-stu-id="a026f-116">Identify service accounts, groups, server name, and reports URL</span></span>

1. <span data-ttu-id="a026f-117">找出 IIS web 伺服器所用的 MBAM 應用程式池服務帳戶，以讀取並將資料寫入 MBAM 的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a026f-117">Identify the MBAM application pool service account that's used by IIS web servers to read and write data to MBAM databases.</span></span>
2. <span data-ttu-id="a026f-118">找出在 MBAM web 功能配置和報告 web 服務 URL 期間所使用的群組。</span><span class="sxs-lookup"><span data-stu-id="a026f-118">Identify the groups that are used during the MBAM web features configuration and the reports web service URL.</span></span>
3. <span data-ttu-id="a026f-119">找出 SQL Server 名稱和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="a026f-119">Identify the SQL Server name and instance name.</span></span> <span data-ttu-id="a026f-120">觀看這段影片以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="a026f-120">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. <span data-ttu-id="a026f-121">找出用來從合規性和審核資料庫讀取合規性資料的 SQL Server Reporting Services 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a026f-121">Identify the SQL Server Reporting Services Account that's used for reading compliance data from the Compliance and Audit database.</span></span> <span data-ttu-id="a026f-122">觀看這段影片以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="a026f-122">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## <span data-ttu-id="a026f-123">將 MBAM 基礎結構升級至最新版本</span><span class="sxs-lookup"><span data-stu-id="a026f-123">Upgrade the MBAM infrastructure to the latest version available</span></span>

<span data-ttu-id="a026f-124">MBAM Server 基礎結構的安裝或升級總是依下列循序執行：</span><span class="sxs-lookup"><span data-stu-id="a026f-124">MBAM Server infrastructure installation or upgrade is always performed in the order listed below:</span></span>

- <span data-ttu-id="a026f-125">SQL Server 資料庫引擎：資料庫</span><span class="sxs-lookup"><span data-stu-id="a026f-125">SQL Server Database Engine: Databases</span></span>
- <span data-ttu-id="a026f-126">SQL Server Reporting Services：報表</span><span class="sxs-lookup"><span data-stu-id="a026f-126">SQL Server Reporting Services: Reports</span></span>
- <span data-ttu-id="a026f-127">Web 服務器： Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="a026f-127">Web Server: Web Applications</span></span>
- <span data-ttu-id="a026f-128">SCCM Server：適用的 SCCM 整合報表</span><span class="sxs-lookup"><span data-stu-id="a026f-128">SCCM Server: SCCM Integrated Reports if applicable</span></span>
- <span data-ttu-id="a026f-129">用戶端： MBAM 代理程式或用戶端更新</span><span class="sxs-lookup"><span data-stu-id="a026f-129">Clients: MBAM Agent or Client Update</span></span>
- <span data-ttu-id="a026f-130">群組原則範本：使用新的範本更新現有的群組原則，並啟用現有 MBAM 組原則上的新設定</span><span class="sxs-lookup"><span data-stu-id="a026f-130">Group Policy Templates: Update the existing Group Policy with new templates and enable new settings on existing MBAM Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="a026f-131">我們建議您在執行升級前，先建立 MBAM 資料庫的完整資料庫備份。</span><span class="sxs-lookup"><span data-stu-id="a026f-131">We recommend that you create a full database backup of the MBAM databases before you run the upgrades.</span></span>

### <span data-ttu-id="a026f-132">升級 MBAM SQL Server</span><span class="sxs-lookup"><span data-stu-id="a026f-132">Upgrade the MBAM SQL Server</span></span>

<span data-ttu-id="a026f-133">觀看這段影片，瞭解如何升級 MBAM SQL Server：</span><span class="sxs-lookup"><span data-stu-id="a026f-133">Watch this video to learn how to upgrade the MBAM SQL Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### <span data-ttu-id="a026f-134">升級 MBAM Web 服務器</span><span class="sxs-lookup"><span data-stu-id="a026f-134">Upgrade the MBAM Web Server</span></span>

<span data-ttu-id="a026f-135">觀看這段影片，瞭解如何升級 MBAM Web 服務器：</span><span class="sxs-lookup"><span data-stu-id="a026f-135">Watch this video to learn how to upgrade the MBAM Web Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## <span data-ttu-id="a026f-136">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a026f-136">More information</span></span>

<span data-ttu-id="a026f-137">如需有關 MBAM 2.5 SP1 中已知問題的詳細資訊，請參閱[MBAM 2.5 SP1 的版本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)資訊。</span><span class="sxs-lookup"><span data-stu-id="a026f-137">For more information about known issues in MBAM 2.5 SP1, see [Release Notes for MBAM 2.5 SP1](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1).</span></span>
