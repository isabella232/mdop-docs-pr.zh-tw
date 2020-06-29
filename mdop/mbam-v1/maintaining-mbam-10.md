---
title: 維護 MBAM 1.0
description: 維護 MBAM 1.0
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811355"
---
# <span data-ttu-id="82e6b-103">維護 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="82e6b-103">Maintaining MBAM 1.0</span></span>


<span data-ttu-id="82e6b-104">完成所有必要的規劃，然後部署 Microsoft BitLocker 管理與監控（MBAM）之後，您就可以將 MBAM 設定為在使用它來管理企業 BitLocker 加密作業時，以高度可用的方式執行。</span><span class="sxs-lookup"><span data-stu-id="82e6b-104">After you complete all the necessary planning and then deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure MBAM to run in a highly available fashion while using it to manage enterprise BitLocker encryption operations.</span></span> <span data-ttu-id="82e6b-105">本節中的資訊說明 MBAM 的高可用性選項，以及如何在必要時移動 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="82e6b-105">The information in this section describes high availability options for MBAM, as well as how to move MBAM Server features if necessary.</span></span>

## <span data-ttu-id="82e6b-106">MBAM 管理套件</span><span class="sxs-lookup"><span data-stu-id="82e6b-106">MBAM Management Pack</span></span>


<span data-ttu-id="82e6b-107">您可以從 Microsoft 下載中心下載 MBAM 的 MicrosoftSystemCenterOperationsManager 管理套件。</span><span class="sxs-lookup"><span data-stu-id="82e6b-107">The MicrosoftSystemCenterOperationsManager Management Pack for MBAM is available for download from the Microsoft Download Center.</span></span>

<span data-ttu-id="82e6b-108">此管理套件會監視伺服器端基礎結構中的重要互動，例如 web 服務與資料庫之間的連線，以及網站與其可進行的 web 服務之間的運營通話。</span><span class="sxs-lookup"><span data-stu-id="82e6b-108">This management pack monitors the critical interactions in the server-side infrastructure, such as the connections between the web services and databases and the operational calls between websites and their supportive web service.</span></span> <span data-ttu-id="82e6b-109">它也會上傳桌面用戶端與其各自的接收 web 服務端點之間的要求。</span><span class="sxs-lookup"><span data-stu-id="82e6b-109">It also uploads the requests between desktop clients and their respective receiving web service endpoints.</span></span>

[<span data-ttu-id="82e6b-110">Microsoft BitLocker 管理和監視管理套件</span><span class="sxs-lookup"><span data-stu-id="82e6b-110">Microsoft BitLocker Administration And Monitoring Management Pack</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## <span data-ttu-id="82e6b-111">確保 MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="82e6b-111">Ensure high availability for MBAM 1.0</span></span>


<span data-ttu-id="82e6b-112">MBAM 已設計成可容錯。</span><span class="sxs-lookup"><span data-stu-id="82e6b-112">MBAM is designed to be fault-tolerant.</span></span> <span data-ttu-id="82e6b-113">如果伺服器無法使用，使用者就不應該受到負面影響。</span><span class="sxs-lookup"><span data-stu-id="82e6b-113">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="82e6b-114">本節中的資訊可用來設定高可用性的 MBAM 安裝。</span><span class="sxs-lookup"><span data-stu-id="82e6b-114">The information in this section can be used to configure a highly available MBAM installation.</span></span>

[<span data-ttu-id="82e6b-115">MBAM 1.0 的高可用性</span><span class="sxs-lookup"><span data-stu-id="82e6b-115">High Availability for MBAM 1.0</span></span>](high-availability-for-mbam-10.md)

## <span data-ttu-id="82e6b-116">將 MBAM 1.0 功能移至另一個伺服器</span><span class="sxs-lookup"><span data-stu-id="82e6b-116">Move MBAM 1.0 features to another server</span></span>


<span data-ttu-id="82e6b-117">當您需要將 MBAM 伺服器功能從一台伺服器電腦移到另一個伺服器時，必須遵循特定的順序及必要步驟，以免損失生產力或資料。</span><span class="sxs-lookup"><span data-stu-id="82e6b-117">When you need to move an MBAM Server feature from one server computer to another, there is a specific order and required steps that you should follow to avoid loss of productivity or data.</span></span> <span data-ttu-id="82e6b-118">本節說明將一或多個 MBAM 伺服器功能移至不同電腦時應採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="82e6b-118">This section describes the steps that you should take to move one or more MBAM Server features to a different computer.</span></span>

[<span data-ttu-id="82e6b-119">如何將 MBAM 1.0 功能移到其他電腦</span><span class="sxs-lookup"><span data-stu-id="82e6b-119">How to Move MBAM 1.0 Features to Another Computer</span></span>](how-to-move-mbam-10-features-to-another-computer.md)

## <span data-ttu-id="82e6b-120">維護 MBAM 的其他資源</span><span class="sxs-lookup"><span data-stu-id="82e6b-120">Other resources for maintaining MBAM</span></span>


[<span data-ttu-id="82e6b-121">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="82e6b-121">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





