---
title: 設定分散式環境的 App-V 系統管理
description: 設定分散式環境的 App-V 系統管理
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809039"
---
# <span data-ttu-id="7bb07-103">設定分散式環境的 App-V 系統管理</span><span class="sxs-lookup"><span data-stu-id="7bb07-103">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="7bb07-104">針對您的特定組織設計基礎結構時，您可以在安裝 App-v Management Server 的電腦以外的電腦上安裝 App-v Management Web 服務。</span><span class="sxs-lookup"><span data-stu-id="7bb07-104">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="7bb07-105">分隔這些 App V 元件的常見原因包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7bb07-105">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="7bb07-106">效能</span><span class="sxs-lookup"><span data-stu-id="7bb07-106">Performance</span></span>

-   <span data-ttu-id="7bb07-107">可靠性</span><span class="sxs-lookup"><span data-stu-id="7bb07-107">Reliability</span></span>

-   <span data-ttu-id="7bb07-108">可用性</span><span class="sxs-lookup"><span data-stu-id="7bb07-108">Availability</span></span>

-   <span data-ttu-id="7bb07-109">延展性</span><span class="sxs-lookup"><span data-stu-id="7bb07-109">Scalability</span></span>

<span data-ttu-id="7bb07-110">若要將管理伺服器與管理 Web 服務分開，需要基礎結構的其他配置才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="7bb07-110">Separating the Management Server and Management Web Service requires additional configuration for the infrastructure to operate correctly.</span></span> <span data-ttu-id="7bb07-111">當您將這兩個功能分開，但沒有完成本主題中所述的程式時，系統會將管理主控台連線至管理 Web 服務，但無法正確驗證資料存放區。</span><span class="sxs-lookup"><span data-stu-id="7bb07-111">When you separate these two features but do not complete the procedures described in this topic, the Management Console will connect to the Management Web Service but will not be able to properly authenticate with the data store.</span></span> <span data-ttu-id="7bb07-112">系統不會正確載入管理主控台，而且管理員將無法完成任何管理作業。</span><span class="sxs-lookup"><span data-stu-id="7bb07-112">The Management Console will not load properly, and the administrator will not be able to complete any administrative tasks.</span></span>

<span data-ttu-id="7bb07-113">之所以會發生此行為，是因為管理 Web 服務無法使用從管理主控台傳給它的認證來存取資料存放區。</span><span class="sxs-lookup"><span data-stu-id="7bb07-113">This behavior occurs because the Management Web Service cannot use the credentials, passed to it from the Management Console, to access the data store.</span></span> <span data-ttu-id="7bb07-114">解決方案是將管理 Web 服務伺服器設定為「信任委派」。</span><span class="sxs-lookup"><span data-stu-id="7bb07-114">The solution is to configure the Management Web Service server to be “Trusted for delegation.”</span></span>

## <span data-ttu-id="7bb07-115">正在設定 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="7bb07-115">Configuring Active Directory Domain Services</span></span>


<span data-ttu-id="7bb07-116">您也必須設定 Active Directory 網域服務，才能正確地在分散式環境中運作。</span><span class="sxs-lookup"><span data-stu-id="7bb07-116">It is also necessary to configure Active Directory Domain Services properly to work in a distributed environment.</span></span> <span data-ttu-id="7bb07-117">本節包含您設定 Active Directory 網域服務所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="7bb07-117">This section includes the information you need configure Active Directory Domain Services.</span></span>

### <span data-ttu-id="7bb07-118">SQL 服務使用本機系統帳戶時</span><span class="sxs-lookup"><span data-stu-id="7bb07-118">When SQL Service Uses Local System account</span></span>

<span data-ttu-id="7bb07-119">若要設定 SQL 服務使用本機系統帳戶的環境，請將管理 Web 服務的電腦帳戶的屬性變更為信任委派。</span><span class="sxs-lookup"><span data-stu-id="7bb07-119">To set up the environment where the SQL Service uses the local system account, change the properties of the machine account of the Management Web Service to be trusted for delegation.</span></span> <span data-ttu-id="7bb07-120">如需如何執行此動作的詳細程式，請參閱[如何將伺服器設定為信任委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)</span><span class="sxs-lookup"><span data-stu-id="7bb07-120">For detailed procedures about how to do this, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)</span></span>

### <span data-ttu-id="7bb07-121">SQL 服務使用網域帳戶時</span><span class="sxs-lookup"><span data-stu-id="7bb07-121">When SQL Service Uses Domain-Based Account</span></span>

<span data-ttu-id="7bb07-122">若要設定 SQL Server 使用網域服務帳戶的環境，您必須考慮是否要套用各種不同的因素，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="7bb07-122">To set up the environment where SQL Servers use domain-based service accounts, you need to consider whether or not a variety of factors apply, including the following:</span></span>

-   <span data-ttu-id="7bb07-123">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="7bb07-123">Clustering of SQL Server</span></span>

-   <span data-ttu-id="7bb07-124">複寫</span><span class="sxs-lookup"><span data-stu-id="7bb07-124">Replication</span></span>

-   <span data-ttu-id="7bb07-125">自動化工作</span><span class="sxs-lookup"><span data-stu-id="7bb07-125">Automated tasks</span></span>

-   <span data-ttu-id="7bb07-126">連結伺服器</span><span class="sxs-lookup"><span data-stu-id="7bb07-126">Linked servers</span></span>

<span data-ttu-id="7bb07-127">如需在 SQL 服務使用網域帳戶時設定 Active Directory 網域服務的相關資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151968> 。</span><span class="sxs-lookup"><span data-stu-id="7bb07-127">For information about configuring Active Directory Domain Services when the SQL service uses a domain-based account, see <https://go.microsoft.com/fwlink/?LinkId=151968>.</span></span>

 

 





