---
title: 找出 MED-V 執行個體數目
description: 找出 MED-V 執行個體數目
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810448"
---
# <span data-ttu-id="83115-103">找出 MED-V 執行個體數目</span><span class="sxs-lookup"><span data-stu-id="83115-103">Identify the Number of MED-V Instances</span></span>


<span data-ttu-id="83115-104">您必須判斷 MED-V 實例數，並為每個實例定義範圍，以便設計伺服器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="83115-104">You need to determine the number of MED-V instances, as well as define the scope for each instance so that you can design the server infrastructure.</span></span> <span data-ttu-id="83115-105">MED-V 實例包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="83115-105">A MED-V instance includes the following:</span></span>

-   <span data-ttu-id="83115-106">在伺服器上儲存的 MED-V 伺服器和 MED-V 工作區，包括 Active Directory 許可權。</span><span class="sxs-lookup"><span data-stu-id="83115-106">The MED-V server and the MED-V workspaces stored on the server, including Active Directory permissions.</span></span>

-   <span data-ttu-id="83115-107">儲存用戶端事件的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="83115-107">A SQL Server database that stores client events.</span></span> <span data-ttu-id="83115-108">資料庫可能是由多個 MED-V 實例所共用。</span><span class="sxs-lookup"><span data-stu-id="83115-108">The database may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="83115-109">封裝的 MED-V 影像的影像存放庫。</span><span class="sxs-lookup"><span data-stu-id="83115-109">The image repository for the packed MED-V images.</span></span> <span data-ttu-id="83115-110">您可以透過多個 MED-V 實例來共用知識庫。</span><span class="sxs-lookup"><span data-stu-id="83115-110">The repository may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="83115-111">用來建立及打包影像及建立 MED-V 工作區的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="83115-111">The management console used to create and pack images and to create MED-V workspaces.</span></span> <span data-ttu-id="83115-112">主機不能同時由多個 MED-V 實例使用，但它可以中斷與一個 MED-V 伺服器的連線，然後再連接到不同的 MED-V 伺服器。</span><span class="sxs-lookup"><span data-stu-id="83115-112">The console cannot be used simultaneously by multiple MED-V instances, but it can be disconnected from one MED-V server and then connected to a different MED-V server.</span></span>

-   <span data-ttu-id="83115-113">從伺服器接收 MED-V 工作區並授權使用的 MED-V 用戶端。</span><span class="sxs-lookup"><span data-stu-id="83115-113">MED-V clients that receive MED-V workspaces, and authorization to use them, from the server.</span></span>

<span data-ttu-id="83115-114">個別的 MED-V 實例不能整合或共用 MED-V-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="83115-114">Separate MED-V instances cannot be integrated or share MED-V workspaces.</span></span> <span data-ttu-id="83115-115">因此，每個額外的實例 decentralizes 虛擬化管理。</span><span class="sxs-lookup"><span data-stu-id="83115-115">Therefore, each additional instance decentralizes the virtualization management.</span></span>

## <span data-ttu-id="83115-116">決定所需的 MED-V 實例數</span><span class="sxs-lookup"><span data-stu-id="83115-116">Determine the Number of MED-V Instances Required</span></span>


<span data-ttu-id="83115-117">首先，假設您使用的是一個 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-117">Start by assuming you are using one MED-V instance.</span></span> <span data-ttu-id="83115-118">接著，請考慮下列條件，並針對每個適用于您基礎結構的條件，新增其他實例。</span><span class="sxs-lookup"><span data-stu-id="83115-118">Then, consider the following conditions, and add additional instances for each condition that applies to your infrastructure.</span></span>

-   <span data-ttu-id="83115-119">支援的使用者數目，每個 MED-V 實例最多可支援5000個併發活動用戶端。</span><span class="sxs-lookup"><span data-stu-id="83115-119">Number of supported users—Each MED-V instance can support up to 5,000 concurrently active clients.</span></span> <span data-ttu-id="83115-120">[同時作用中] 表示用戶端與 MED-V 伺服器連線，並將輪詢傳送到伺服器以進行原則與影像更新，以及事件。</span><span class="sxs-lookup"><span data-stu-id="83115-120">Concurrently active means the client is online with the MED-V server and sending polls to the server for policy and image updates, as well as events.</span></span> <span data-ttu-id="83115-121">如果您的基礎結構將包含超過5000個作用中的使用者，請為每個5000使用者新增一個實例。</span><span class="sxs-lookup"><span data-stu-id="83115-121">If your infrastructure will include more than 5,000 active users, add one instance for every 5,000 users.</span></span>

-   <span data-ttu-id="83115-122">不受信任網域中的使用者-MED-V 伺服器會將 MED-V 工作區許可權與 Active Directory 使用者和/或群組建立關聯。</span><span class="sxs-lookup"><span data-stu-id="83115-122">Users in untrusted domains—The MED-V server associates MED-V workspace permissions with Active Directory users and/or groups.</span></span> <span data-ttu-id="83115-123">這需要在 MED-V 伺服器的信任界限記憶體在 MED-V 使用者。</span><span class="sxs-lookup"><span data-stu-id="83115-123">This requires MED-V users to exist within the trust boundary of the MED-V server.</span></span> <span data-ttu-id="83115-124">針對個別、不受信任網域中的每個 MED-V 使用者組，新增一個 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-124">Add one MED-V instance for each group of MED-V users that is in a separate, untrusted domain.</span></span>

-   <span data-ttu-id="83115-125">隔離網路中的用戶端，判斷是否有任何用戶端位於隔離的網路中，因此需要個別的 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-125">Clients in isolated networks—Determine whether any clients reside in networks that are isolated and therefore require a separate MED-V instance.</span></span> <span data-ttu-id="83115-126">例如，組織通常會將實驗室網路與生產網路隔離。</span><span class="sxs-lookup"><span data-stu-id="83115-126">For example, organizations often isolate lab networks from production networks.</span></span> <span data-ttu-id="83115-127">針對將包含 MED-V 用戶端的每個隔離網路，新增 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-127">Add a MED-V instance for each isolated network that will contain MED-V clients.</span></span>

-   <span data-ttu-id="83115-128">組織需求-組織可能需要由個別的 MED-V 實例來管理一組用戶端，以確保安全性，例如，只將機密應用程式傳遞到網域中受限制的使用者組。</span><span class="sxs-lookup"><span data-stu-id="83115-128">Organizational requirements—The organization may require that a group of clients be managed by a separate MED-V instance for security reasons, such as when sensitive applications are delivered only to a restricted set of users within a domain.</span></span> <span data-ttu-id="83115-129">例如，工資部門可能會拒絕其他部門的使用者存取儲存用於工資處理原則的 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-129">For example, the payroll department may deny users from other departments access to the MED-V instance that stores policy for payroll processing.</span></span> <span data-ttu-id="83115-130">此外，如果組織使用分散式管理模型，則可能需要有 MED-V 用戶端的每個商務群組都需要個別的 MED-V 實例，才能讓群組管理自己的虛擬化環境。</span><span class="sxs-lookup"><span data-stu-id="83115-130">Additionally, if the organization uses a distributed management model, a separate MED-V instance may be required for each business group having MED-V clients in order to enable the group to manage its own virtualized environment.</span></span> <span data-ttu-id="83115-131">針對每個個別的組織需求，新增一個 MED-V 實例。</span><span class="sxs-lookup"><span data-stu-id="83115-131">Add one MED-V instance for each separate organizational requirement.</span></span>

-   <span data-ttu-id="83115-132">法律考慮-國內安全性或隱私權問題及 fiduciary 定律可能需要分隔特定資料，或避免其他資料跨越全國框線。</span><span class="sxs-lookup"><span data-stu-id="83115-132">Legal considerations—National security or privacy issues and fiduciary laws could require the separation of certain data or prevent other data from crossing national borders.</span></span> <span data-ttu-id="83115-133">如有需要，請新增其他 MED-V 實例以滿足此需求。</span><span class="sxs-lookup"><span data-stu-id="83115-133">If necessary, add additional MED-V instances to address this need.</span></span>

<span data-ttu-id="83115-134">在您決定基礎結構所需的 MED-V 實例數之後，以及每個實例的理由，為每個實例提供名稱。</span><span class="sxs-lookup"><span data-stu-id="83115-134">After you determine the number of MED-V instances required for your infrastructure, as well as the reasoning for each one, provide a name for each instance.</span></span>

 

 





