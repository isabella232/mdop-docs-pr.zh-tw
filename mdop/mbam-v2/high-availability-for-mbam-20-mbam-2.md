---
title: MBAM 2.0 的高可用性
description: MBAM 2.0 的高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810730"
---
# <span data-ttu-id="411a9-103">MBAM 2.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="411a9-103">High Availability for MBAM 2.0</span></span>


<span data-ttu-id="411a9-104">本主題提供有關高可用性的 Microsoft BitLocker 管理和監控（MBAM）安裝的基本資訊。</span><span class="sxs-lookup"><span data-stu-id="411a9-104">This topic provides basic information about a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="411a9-105">在這個版本的 MBAM 中並不完全支援高可用性案例，所以這裡並未說明它們。</span><span class="sxs-lookup"><span data-stu-id="411a9-105">High-availability scenarios are not fully supported in this version of MBAM, so they are not described here.</span></span> <span data-ttu-id="411a9-106">建議您搜尋相關的博客和論壇，讓使用者描述他們在其環境中如何成功設定高可用性 MBAM。</span><span class="sxs-lookup"><span data-stu-id="411a9-106">It is recommended that you search related blogs and forums, where users describe how they have successfully configured high availability for MBAM in their environments.</span></span>

## <span data-ttu-id="411a9-107">MBAM 的高可用性案例</span><span class="sxs-lookup"><span data-stu-id="411a9-107">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="411a9-108">Microsoft BitLocker 管理和監視是以容錯的設計。</span><span class="sxs-lookup"><span data-stu-id="411a9-108">Microsoft BitLocker Administration and Monitoring is designed to be fault-tolerant.</span></span> <span data-ttu-id="411a9-109">如果伺服器無法使用，使用者就不應該受到負面影響。</span><span class="sxs-lookup"><span data-stu-id="411a9-109">If a server becomes unavailable, users should not be negatively affected.</span></span> <span data-ttu-id="411a9-110">例如，如果 MBAM 代理程式無法連線至 MBAM web 伺服器，則不應提示使用者執行動作。</span><span class="sxs-lookup"><span data-stu-id="411a9-110">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="411a9-111">規劃 MBAM 安裝時，請考慮下列專案，這可能會影響 MBAM 服務的可用性：</span><span class="sxs-lookup"><span data-stu-id="411a9-111">When you plan your MBAM installation, consider the following items, which can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="411a9-112">磁片磁碟機加密和復原密碼–如果無法 escrowed 復原密碼，就不會在用戶端電腦上啟動加密。</span><span class="sxs-lookup"><span data-stu-id="411a9-112">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption does not start on the client computer.</span></span>

-   <span data-ttu-id="411a9-113">相容性狀態資料上傳–如果無法使用託管合規性狀態報表服務的伺服器，則合規性資料不會保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="411a9-113">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data does not remain current.</span></span>

-   <span data-ttu-id="411a9-114">協助桌面復原金鑰存取-如果技術支援人員無法存取 MBAM 資料庫資訊，說明服務台無法提供復原金鑰給使用者。</span><span class="sxs-lookup"><span data-stu-id="411a9-114">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, the Help Desk cannot provide recovery keys to users.</span></span>

-   <span data-ttu-id="411a9-115">報表的可用性–如果無法使用託管合規性和審核報告的伺服器，則無法使用報告。</span><span class="sxs-lookup"><span data-stu-id="411a9-115">Availability of reports –If the server that hosts the Compliance and Audit Reports is not available, reports will not be available.</span></span>

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a><span data-ttu-id="411a9-116">MBAM 備份如何使用卷影複製服務（VSS）</span><span class="sxs-lookup"><span data-stu-id="411a9-116">How the MBAM Backup Uses the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="411a9-117">MBAM 2.0 提供了一個卷陰影複製服務（VSS）寫入程式，稱為 Microsoft BitLocker 管理與管理寫入程式，可協助您備份合規性和審核資料庫及恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="411a9-117">MBAM2.0 provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer, which facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="411a9-118">MBAM Server Windows 安裝程式會註冊 MBAM VSS 寫入程式。</span><span class="sxs-lookup"><span data-stu-id="411a9-118">The MBAM Server Windows Installer registers the MBAM VSS Writer.</span></span> <span data-ttu-id="411a9-119">在 VSS 寫入程式註冊期間發生任何失敗，都會導致 MBAM 伺服器安裝回滾。</span><span class="sxs-lookup"><span data-stu-id="411a9-119">Any failure during the VSS writer registration causes the MBAM Server installation to roll back.</span></span> <span data-ttu-id="411a9-120">在已將合規性與審計資料庫及復原資料庫安裝在不同伺服器的拓撲中，會在每個伺服器上登錄單獨的 MBAM VSS 書寫器實例。</span><span class="sxs-lookup"><span data-stu-id="411a9-120">In a topology where the Compliance and Audit Database and the Recovery Database are installed on different servers, a separate instance of MBAM VSS Writer is registered on each server.</span></span> <span data-ttu-id="411a9-121">MBAM VSS 書寫器依賴于 SQL Server VSS 寫入程式。</span><span class="sxs-lookup"><span data-stu-id="411a9-121">The MBAM VSS Writer is dependent on the SQL Server VSS Writer.</span></span> <span data-ttu-id="411a9-122">SQL Server VSS 書寫器已註冊為 Microsoft SQL Server 安裝的一部分。</span><span class="sxs-lookup"><span data-stu-id="411a9-122">The SQL Server VSS Writer is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="411a9-123">任何使用 VSS 寫入程式來執行備份的備份技術，都可以探索 MBAM VSS 寫入程式。</span><span class="sxs-lookup"><span data-stu-id="411a9-123">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS Writer.</span></span>

## <span data-ttu-id="411a9-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="411a9-124">Related topics</span></span>


[<span data-ttu-id="411a9-125">維護 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="411a9-125">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)

 

 





