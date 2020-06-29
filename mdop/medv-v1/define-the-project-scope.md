---
title: 定義專案範圍
description: 定義專案範圍
author: dansimp
ms.assetid: 84637d2a-2e30-417d-b150-dc81f414b3a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f33562452327bba9036f56d9f6f96650f00c1f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810077"
---
# <span data-ttu-id="3cce0-103">定義專案範圍</span><span class="sxs-lookup"><span data-stu-id="3cce0-103">Define the Project Scope</span></span>


<span data-ttu-id="3cce0-104">定義專案範圍時，請判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="3cce0-104">When defining the project scope, determine the following:</span></span>

1.  <span data-ttu-id="3cce0-105">MED-V 的使用者-使用者在判斷 MED-V 用戶端安裝的位置和 MED-V 實例的數目，以及 MED-V 影像儲存庫的數量和位置，使用使用者的位置和數目。</span><span class="sxs-lookup"><span data-stu-id="3cce0-105">The MED-V end users—the location and number of end users are used in determining the location of MED-V client installations and the number of MED-V instances, as well as the number and placement of MED-V image repositories.</span></span>

2.  <span data-ttu-id="3cce0-106">由 MED-V 管理的虛擬機器（VM）影像，以判斷發佈影像及放置影像存放庫的方法。</span><span class="sxs-lookup"><span data-stu-id="3cce0-106">The virtual machine (VM) images to be managed by MED-V—to determine the method of distributing images and placement of image repositories.</span></span>

3.  <span data-ttu-id="3cce0-107">組織的服務層級預期-可判斷 MED-V 伺服器和資料庫以及影像存放庫的效能與容錯需求。</span><span class="sxs-lookup"><span data-stu-id="3cce0-107">The organization’s service level expectations—to determine the performance and fault-tolerance requirements for the MED-V server and database as well as the image repository.</span></span>

4.  <span data-ttu-id="3cce0-108">與業務驗證-確保規劃的基礎結構對企業有何影響的完整瞭解。</span><span class="sxs-lookup"><span data-stu-id="3cce0-108">Validate with the business—ensure there is a complete understanding of how the planned infrastructure affects the business.</span></span>

## <span data-ttu-id="3cce0-109">定義 MED-V 端使用者</span><span class="sxs-lookup"><span data-stu-id="3cce0-109">Define the MED-V End Users</span></span>


<span data-ttu-id="3cce0-110">首先，決定最終使用者的位置，以及每個位置的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="3cce0-110">First, determine where the end users are located, as well as the number of users in each location.</span></span> <span data-ttu-id="3cce0-111">接著，取得網路基礎結構圖表，以顯示使用者位置，以及這些位置的可用頻寬。</span><span class="sxs-lookup"><span data-stu-id="3cce0-111">Second, obtain a network infrastructure diagram that displays the user locations and the available bandwidth to those locations.</span></span> <span data-ttu-id="3cce0-112">第三，找出使用者是否在不同位置間出差。</span><span class="sxs-lookup"><span data-stu-id="3cce0-112">Third, find out if users travel between locations.</span></span> <span data-ttu-id="3cce0-113">如果使用者出差，可能需要在伺服器基礎結構和影像儲存庫的設計中使用額外的容量。</span><span class="sxs-lookup"><span data-stu-id="3cce0-113">If users travel, additional capacity may be required in the design of the server infrastructure and image repositories.</span></span>

## <span data-ttu-id="3cce0-114">決定由 MED-V 管理的 MED-V 圖像</span><span class="sxs-lookup"><span data-stu-id="3cce0-114">Determine the MED-V Images to Be Managed by MED-V</span></span>


<span data-ttu-id="3cce0-115">在已定義 MED-V 使用者之後，決定將由 MED-V 針對每個位置的使用者管理哪些 Vm。</span><span class="sxs-lookup"><span data-stu-id="3cce0-115">After the MED-V end users have been defined, determine which VMs will be managed by MED-V for the users in each location.</span></span>

<span data-ttu-id="3cce0-116">如果有任何 Vm 儲存在集中式文件庫中，請判斷文件庫的位置，以便將它評估成可做為 MED-V 儲存庫使用。</span><span class="sxs-lookup"><span data-stu-id="3cce0-116">If any of the VMs are stored in a centralized library, determine the location of the library so that it may be evaluated for use as a MED-V repository.</span></span>

## <a href="" id="determine-the-organization-s-service-level-expectations"></a><span data-ttu-id="3cce0-117">判斷組織的服務層級預期</span><span class="sxs-lookup"><span data-stu-id="3cce0-117">Determine the Organization’s Service Level Expectations</span></span>


<span data-ttu-id="3cce0-118">針對每個 MED-V 工作區，請注意要載入新影像的可接受時間，以及要部署重要更新的時間範圍。</span><span class="sxs-lookup"><span data-stu-id="3cce0-118">For each MED-V workspace, note the acceptable time for a new image to load and the timeframe for critical updates to be deployed.</span></span>

<span data-ttu-id="3cce0-119">如果適用的話，請記錄 MED-V 報告的服務層級預期，以用於伺服器基礎結構的設計。</span><span class="sxs-lookup"><span data-stu-id="3cce0-119">If applicable, record the service level expectations for MED-V reporting, to be used in the design of the server infrastructure.</span></span>

## <span data-ttu-id="3cce0-120">使用業務進行驗證</span><span class="sxs-lookup"><span data-stu-id="3cce0-120">Validate with the Business</span></span>


<span data-ttu-id="3cce0-121">詢問商業專案關係人及應用程式擁有者下列問題：</span><span class="sxs-lookup"><span data-stu-id="3cce0-121">Ask business stakeholders and application owners the following questions:</span></span>

-   <span data-ttu-id="3cce0-122">是否有任何現有的圖像可結合使用？</span><span class="sxs-lookup"><span data-stu-id="3cce0-122">Are there any existing images that can be combined?</span></span> <span data-ttu-id="3cce0-123">例如，如果應用程式 A on WindowsXP 是一個 VPC 影像，而 WindowsXP 上的應用程式 B 是另一個 VPC 影像，可能是因為單一影像可以包含這兩個應用程式，因而減少了影像下載所需的儲存庫空間和頻寬。</span><span class="sxs-lookup"><span data-stu-id="3cce0-123">For example, if application A on WindowsXP is one VPC image and application B on WindowsXP is another VPC image, perhaps a single image can contain both applications, thereby reducing repository space and bandwidth required for image download.</span></span>

-   <span data-ttu-id="3cce0-124">如果由 MED-V 在 VM 中傳送，則是由作用中的應用程式授權並支援嗎？</span><span class="sxs-lookup"><span data-stu-id="3cce0-124">Are the in-scope applications licensable and supportable if delivered in a VM by MED-V?</span></span> <span data-ttu-id="3cce0-125">透過 MED-V 提供應用程式，與應用程式供應商確認不會違反授權和支援條款。</span><span class="sxs-lookup"><span data-stu-id="3cce0-125">Check with the application supplier to ensure that licensing and support terms will not be violated by delivering the application through MED-V.</span></span>

 

 





