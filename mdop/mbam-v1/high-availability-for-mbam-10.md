---
title: MBAM 1.0 的高可用性
description: MBAM 1.0 的高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811109"
---
# <span data-ttu-id="a13ee-103">MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="a13ee-103">High Availability for MBAM 1.0</span></span>


<span data-ttu-id="a13ee-104">本主題說明如何設定高可用性的 Microsoft BitLocker 管理和監控安裝（MBAM）。</span><span class="sxs-lookup"><span data-stu-id="a13ee-104">This topic describes how to configure a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

## <span data-ttu-id="a13ee-105">MBAM 的高可用性案例</span><span class="sxs-lookup"><span data-stu-id="a13ee-105">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="a13ee-106">Microsoft BitLocker 管理和監控（MBAM）的設計是可容錯的。</span><span class="sxs-lookup"><span data-stu-id="a13ee-106">Microsoft BitLocker Administration and Monitoring (MBAM) is designed to be fault-tolerant.</span></span> <span data-ttu-id="a13ee-107">如果伺服器無法使用，使用者就不應該受到負面影響。</span><span class="sxs-lookup"><span data-stu-id="a13ee-107">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="a13ee-108">例如，如果 MBAM 代理程式無法連線至 MBAM web 伺服器，則不應提示使用者執行動作。</span><span class="sxs-lookup"><span data-stu-id="a13ee-108">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="a13ee-109">規劃 MBAM 安裝時，請考慮下列可能會影響 MBAM 服務可用性的問題：</span><span class="sxs-lookup"><span data-stu-id="a13ee-109">When you plan your MBAM installation, consider the following concerns that can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="a13ee-110">磁片磁碟機加密和復原密碼–如果無法 escrowed 復原密碼，則不會在用戶端電腦上啟動加密。</span><span class="sxs-lookup"><span data-stu-id="a13ee-110">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption will not start on the client computer.</span></span>

-   <span data-ttu-id="a13ee-111">相容性狀態資料上傳–如果無法使用託管合規性狀態報表服務的伺服器，規範資料將不會保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="a13ee-111">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data will not remain current.</span></span>

-   <span data-ttu-id="a13ee-112">協助桌面復原金鑰存取-如果技術支援人員無法存取 MBAM 資料庫資訊，他們將無法提供復原金鑰給使用者。</span><span class="sxs-lookup"><span data-stu-id="a13ee-112">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, they will be unable to provide recovery keys to users.</span></span>

-   <span data-ttu-id="a13ee-113">如果無法使用託管合規性和審核報告的伺服器，則無法使用報表的可用性。</span><span class="sxs-lookup"><span data-stu-id="a13ee-113">Availability of reports – Reports will not be available if the server that hosts the Compliance and Audit Reports is not available.</span></span>

<span data-ttu-id="a13ee-114">MBAM 高可用性的主要考慮是 BitLocker 金鑰復原可用性。</span><span class="sxs-lookup"><span data-stu-id="a13ee-114">The main concern for MBAM high availability is BitLocker key recovery availability.</span></span> <span data-ttu-id="a13ee-115">如果技術支援人員無法提供復原金鑰，鎖定的使用者就無法解除鎖定電腦。</span><span class="sxs-lookup"><span data-stu-id="a13ee-115">If the help desk cannot provide recovery keys, users who are locked out cannot unlock their computers.</span></span> <span data-ttu-id="a13ee-116">若要避免此問題，請考慮執行冗余的 web 伺服器和資料庫，以確保高可用性。</span><span class="sxs-lookup"><span data-stu-id="a13ee-116">To avoid this problem, consider implementing redundant web servers and databases to ensure high availability.</span></span>

<span data-ttu-id="a13ee-117">如需 MBAM 可伸縮性和高可用性的詳細資訊，請參閱[MBAM 可伸縮性白皮書](https://go.microsoft.com/fwlink/p/?LinkId=229025)（ https://go.microsoft.com/fwlink/p/?LinkId=229025) 。</span><span class="sxs-lookup"><span data-stu-id="a13ee-117">For more information about MBAM scalability and high availability, see the [MBAM Scalability White Paper](https://go.microsoft.com/fwlink/p/?LinkId=229025) (https://go.microsoft.com/fwlink/p/?LinkId=229025).</span></span>

<span data-ttu-id="a13ee-118">如需 Microsoft SQL Server 高可用性的一般指導方針，請參閱[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)（ https://go.microsoft.com/fwlink/p/?LinkId=221504) 。</span><span class="sxs-lookup"><span data-stu-id="a13ee-118">For general guidance on high availability for Microsoft SQL Server, see [High Availability](https://go.microsoft.com/fwlink/p/?LinkId=221504) (https://go.microsoft.com/fwlink/p/?LinkId=221504).</span></span>

<span data-ttu-id="a13ee-119">如需 web 伺服器可用性與伸縮性的一般指導方針，請參閱[可用性與伸縮性](https://go.microsoft.com/fwlink/p/?LinkId=221503)（ https://go.microsoft.com/fwlink/p/?LinkId=221503) 。</span><span class="sxs-lookup"><span data-stu-id="a13ee-119">For general guidance on availability and scalability for web servers, see [Availability and Scalability](https://go.microsoft.com/fwlink/p/?LinkId=221503) (https://go.microsoft.com/fwlink/p/?LinkId=221503).</span></span>

## <span data-ttu-id="a13ee-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="a13ee-120">Related topics</span></span>


[<span data-ttu-id="a13ee-121">維護 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="a13ee-121">Maintaining MBAM 1.0</span></span>](maintaining-mbam-10.md)

 

 





