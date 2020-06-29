---
title: 設計 MED-V 映像存放庫
description: 設計 MED-V 映像存放庫
author: dansimp
ms.assetid: e153154d-2751-4990-b94d-a2d76242c15f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0c59a0dd2d1b3a78bd211c6a6353a86c77d8fc2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810059"
---
# <span data-ttu-id="43c3f-103">設計 MED-V 映像存放庫</span><span class="sxs-lookup"><span data-stu-id="43c3f-103">Design the MED-V Image Repositories</span></span>


<span data-ttu-id="43c3f-104">在建立並封裝 MED-V 影像之後，就可以將它們儲存在任何位置的檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="43c3f-104">After MED-V images are created and packed, they can be stored on a file server in any location.</span></span> <span data-ttu-id="43c3f-105">檔案可能是透過 HTTP 或來自一或多個 IIS 伺服器的 HTTPS 傳送。</span><span class="sxs-lookup"><span data-stu-id="43c3f-105">The files may be sent over HTTP or HTTPS by one or more IIS servers.</span></span> <span data-ttu-id="43c3f-106">影像儲存庫可由多個 MED-V 實例共用。</span><span class="sxs-lookup"><span data-stu-id="43c3f-106">The image repository can be shared by multiple MED-V instances.</span></span>

<span data-ttu-id="43c3f-107">若要設計影像資料庫，您必須先決定要將影像部署到每個用戶端的方式，以及該用戶端是否需要本機映射存放庫。</span><span class="sxs-lookup"><span data-stu-id="43c3f-107">To design the image repositories, you must first decide how the images will be deployed to each client and then whether that client requires a local image repository.</span></span> <span data-ttu-id="43c3f-108">接著會設計並放置每個知識庫，以及隨附的 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="43c3f-108">Each repository is then designed and placed, along with its accompanying IIS server.</span></span>

## <span data-ttu-id="43c3f-109">決定要部署影像的方式</span><span class="sxs-lookup"><span data-stu-id="43c3f-109">Determine How Images Will Be Deployed</span></span>


<span data-ttu-id="43c3f-110">針對每個 MED-V 工作區，決定如何規劃將 MED-V 影像部署到用戶端。</span><span class="sxs-lookup"><span data-stu-id="43c3f-110">For each MED-V workspace, decide how you plan to deploy MED-V images to the client.</span></span> <span data-ttu-id="43c3f-111">這對於決定要儲存打包的影像所需多少儲存庫（存放這些資料庫的位置），然後再設計這些資料庫是很重要的。</span><span class="sxs-lookup"><span data-stu-id="43c3f-111">This is important in determining how many repositories are necessary to store the packed images, where those repositories will be placed, and then to design those repositories.</span></span>

<span data-ttu-id="43c3f-112">您可以透過下列方式部署打包的影像：</span><span class="sxs-lookup"><span data-stu-id="43c3f-112">Packed images can be deployed in the following ways:</span></span>

-   <span data-ttu-id="43c3f-113">透過網路從影像發佈伺服器下載，由檔案伺服器與 IIS 伺服器組成。</span><span class="sxs-lookup"><span data-stu-id="43c3f-113">Downloaded over the network from an image distribution server, which comprises a file server and IIS server.</span></span>

-   <span data-ttu-id="43c3f-114">在卸除式媒體（例如 USB 磁片磁碟機或 DVD）上。</span><span class="sxs-lookup"><span data-stu-id="43c3f-114">On removable media, such as a USB drive or DVD.</span></span>

-   <span data-ttu-id="43c3f-115">使用企業軟體發行中心，預先暫存到用戶端電腦上的影像存放區目錄。</span><span class="sxs-lookup"><span data-stu-id="43c3f-115">Pre-staged to an image store directory on the client computer using an enterprise software distribution center.</span></span>

<span data-ttu-id="43c3f-116">決定要使用哪一種方法或方法，將 MED-V 影像部署到每個用戶端，以及該位置是否需要影像儲存庫。</span><span class="sxs-lookup"><span data-stu-id="43c3f-116">Decide which method, or methods, will be used to deploy MED-V images to each of the clients and whether the location will require an image repository.</span></span>

## <span data-ttu-id="43c3f-117">決定影像存放庫的數目</span><span class="sxs-lookup"><span data-stu-id="43c3f-117">Determine the Number of Image Repositories</span></span>


<span data-ttu-id="43c3f-118">現在您已經決定了您所需的最小儲存庫數，請在下列任一準則適用時新增更多專案：</span><span class="sxs-lookup"><span data-stu-id="43c3f-118">Now that you have determined the minimum number of repositories you need, add more if any of the following criteria apply:</span></span>

-   <span data-ttu-id="43c3f-119">組織或管理的理由若要分隔 MED-V 影像，一些 MED-V 影像可能無法在同一個儲存庫中共存。</span><span class="sxs-lookup"><span data-stu-id="43c3f-119">Organizational or regulatory reasons to separate the MED-V images—some MED-V images may not be able to coexist in the same repository.</span></span> <span data-ttu-id="43c3f-120">例如，機密的個人資料可能需要只提供給需要存取資料之一組有限員工的伺服器儲存空間。</span><span class="sxs-lookup"><span data-stu-id="43c3f-120">For example, sensitive personal data may require storage on a server that is only available to a limited set of employees who need access to the data.</span></span>

-   <span data-ttu-id="43c3f-121">隔離網路中的用戶端：如果影像將在網路上部署，請判斷是否有任何網路是隔離的，而且需要個別的儲存庫。</span><span class="sxs-lookup"><span data-stu-id="43c3f-121">Clients in isolated networks—if images will be deployed over the network, determine whether any networks are isolated and require a separate repository.</span></span> <span data-ttu-id="43c3f-122">例如，組織通常會將實驗室網路與生產網路隔離。</span><span class="sxs-lookup"><span data-stu-id="43c3f-122">For example, organizations often isolate lab networks from production networks.</span></span>

-   <span data-ttu-id="43c3f-123">遠端網路中的用戶端（如果影像將透過網路部署），某些用戶端電腦可能會以沒有足夠頻寬的網路連結分隔，在用戶端載入 MED-V 工作區時提供適當的體驗。</span><span class="sxs-lookup"><span data-stu-id="43c3f-123">Clients in remote networks—if images will be deployed over the network, some client machines may be separated from the repository by network links that have insufficient bandwidth to provide an adequate experience when a client loads a MED-V workspace.</span></span> <span data-ttu-id="43c3f-124">如有需要，請設計其他 MED-V 實例來解決此需求。</span><span class="sxs-lookup"><span data-stu-id="43c3f-124">If necessary, design additional MED-V instances to address this need.</span></span>

<span data-ttu-id="43c3f-125">將這些資料庫新增到設計中。</span><span class="sxs-lookup"><span data-stu-id="43c3f-125">Add these repositories to the design.</span></span> <span data-ttu-id="43c3f-126">針對每個存放庫選擇一個名稱，以及設計原因。</span><span class="sxs-lookup"><span data-stu-id="43c3f-126">Decide on a name for each repository and the reason for designing it.</span></span> <span data-ttu-id="43c3f-127">決定存放資料庫將保留哪些 MED-V 影像，以及哪些 MED-V 用戶端將使用知識庫中的圖像載入 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="43c3f-127">Decide which MED-V images the repositories will hold and which MED-V clients will load MED-V workspaces with images from the repository.</span></span>

## <span data-ttu-id="43c3f-128">設計並放置影像存放庫</span><span class="sxs-lookup"><span data-stu-id="43c3f-128">Design and Place the Image Repositories</span></span>


<span data-ttu-id="43c3f-129">當用戶端可以使用新的影像時，用戶端開始下載影像，可能同時進行。</span><span class="sxs-lookup"><span data-stu-id="43c3f-129">When a new image is available to clients, clients begin downloading the image, possibly simultaneously.</span></span> <span data-ttu-id="43c3f-130">這會在儲存庫中產生高需求，且必須在設計影像存放庫時納入考慮。</span><span class="sxs-lookup"><span data-stu-id="43c3f-130">This creates a high demand on the repository and must be taken into account when designing the image repository.</span></span>

<span data-ttu-id="43c3f-131">針對每個存放庫，決定要儲存的資料量。</span><span class="sxs-lookup"><span data-stu-id="43c3f-131">For each repository, determine the amount of data it will store.</span></span> <span data-ttu-id="43c3f-132">加總將儲存在儲存庫中的影像大小。</span><span class="sxs-lookup"><span data-stu-id="43c3f-132">Sum the sizes of images that will be stored in the repository.</span></span> <span data-ttu-id="43c3f-133">這是檔案伺服器上所需的磁碟空間值。</span><span class="sxs-lookup"><span data-stu-id="43c3f-133">This is the value of the disk space required on the file server.</span></span>

<span data-ttu-id="43c3f-134">接下來，新增可能從儲存庫下載 MED-V 影像的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="43c3f-134">Next, add up the number of clients that may download MED-V images from the repository.</span></span> <span data-ttu-id="43c3f-135">這是將新的 MED-V 影像載入到知識庫時，可能會發生的併發下載數目上限。</span><span class="sxs-lookup"><span data-stu-id="43c3f-135">This is the maximum number of concurrent downloads that can occur when a new MED-V image is loaded into the repository.</span></span> <span data-ttu-id="43c3f-136">檔案伺服器必須用可滿足此建立的 IO 需求的磁片子系統設計。</span><span class="sxs-lookup"><span data-stu-id="43c3f-136">The file server must be designed with a disk subsystem that can meet the IO demands this will create.</span></span>

<span data-ttu-id="43c3f-137">影像存放庫可以與 MED-V 伺服器以及執行 SQL Server 的伺服器，或是在遠端檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="43c3f-137">The image repository can reside on the same system as the MED-V server and the server running SQL Server, or on a remote file share.</span></span> <span data-ttu-id="43c3f-138">您也可以在 Windows Server2008 Hyper-v VM 中執行它。</span><span class="sxs-lookup"><span data-stu-id="43c3f-138">You can also run it in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="43c3f-139">檢查影像存放庫將提供服務的用戶端的網路位置，然後將知識庫放在具有足夠頻寬的網路位置，以符合這些用戶端的服務層級預期。</span><span class="sxs-lookup"><span data-stu-id="43c3f-139">Check the network location of the clients that the image repository will service, and place the repository in a network location where it will have sufficient bandwidth to meet the service level expectations of those clients.</span></span>

### <span data-ttu-id="43c3f-140">容錯</span><span class="sxs-lookup"><span data-stu-id="43c3f-140">Fault Tolerance</span></span>

<span data-ttu-id="43c3f-141">如果影像儲存庫無法使用，用戶端將無法下載新的或更新的 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="43c3f-141">If the image repository is unavailable, clients will not be able to download new or updated MED-V images.</span></span> <span data-ttu-id="43c3f-142">若要針對檔案伺服器和容錯磁片設計容錯選項，請參閱[基礎結構規劃與設計 MICROSOFT SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南。</span><span class="sxs-lookup"><span data-stu-id="43c3f-142">To design fault-tolerance options for the file server and fault-tolerant disks, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide.</span></span>

## <span data-ttu-id="43c3f-143">設計並放置 IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="43c3f-143">Design and Place the IIS Servers</span></span>


<span data-ttu-id="43c3f-144">此區段僅在用戶端將在使用 HTTP 或 HTTPS 的網路上下載影像檔案時才適用。</span><span class="sxs-lookup"><span data-stu-id="43c3f-144">This section is only relevant if clients will download image files over the network using HTTP or HTTPS.</span></span>

<span data-ttu-id="43c3f-145">IIS 伺服器可以與 MED-V 伺服器以及執行 SQL Server 的伺服器共存于同一個系統上。</span><span class="sxs-lookup"><span data-stu-id="43c3f-145">The IIS server can coexist on the same system as the MED-V server and the server running SQL Server.</span></span> <span data-ttu-id="43c3f-146">它也可以在 Windows Server2008 Hyper-v VM 中執行。</span><span class="sxs-lookup"><span data-stu-id="43c3f-146">It can also run in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="43c3f-147">IIS 伺服器基礎結構必須具備足夠的輸送量，才能將影像傳送給組織中服務層級預期的用戶端。</span><span class="sxs-lookup"><span data-stu-id="43c3f-147">The IIS server infrastructure must have sufficient throughput to deliver images to clients within the service level expectations of the organization.</span></span> <span data-ttu-id="43c3f-148">它必須設計在能滿足此建立的 IO 需求的磁片子系統上。</span><span class="sxs-lookup"><span data-stu-id="43c3f-148">It must be designed with a disk subsystem that can meet the IO demands this creates.</span></span>

<span data-ttu-id="43c3f-149">針對每個影像儲存庫，加總可使用 IIS 下載 MED-V 影像的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="43c3f-149">For each image repository, sum the number of clients that may download MED-V images using IIS.</span></span> <span data-ttu-id="43c3f-150">這是將影像載入到存放庫時，可能會發生的併發下載數目上限。</span><span class="sxs-lookup"><span data-stu-id="43c3f-150">This is the maximum number of concurrent downloads that can occur when an image is loaded into the repository.</span></span> <span data-ttu-id="43c3f-151">使用 [輸送量總和] 和 [服務層級預期][定義專案範圍](define-the-project-scope.md)來規劃 IIS 伺服器基礎結構的設計，並判斷要為儲存庫配置適當的頻寬量。</span><span class="sxs-lookup"><span data-stu-id="43c3f-151">Use the throughput sum and the service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to plan the design of the IIS server infrastructure and to determine the appropriate amount of bandwidth to allocate for the repository.</span></span>

<span data-ttu-id="43c3f-152">若要設計 IIS 基礎結構，請參閱[基礎結構規劃及設計 Microsoft 網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=160826)指南。</span><span class="sxs-lookup"><span data-stu-id="43c3f-152">To design the IIS infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

### <span data-ttu-id="43c3f-153">容錯</span><span class="sxs-lookup"><span data-stu-id="43c3f-153">Fault Tolerance</span></span>

<span data-ttu-id="43c3f-154">如果 IIS 伺服器基礎結構無法使用，用戶端將無法下載新的或更新的影像。</span><span class="sxs-lookup"><span data-stu-id="43c3f-154">If the IIS server infrastructure is unavailable, clients will not be able to download new or updated images.</span></span> <span data-ttu-id="43c3f-155">若要設定容錯，可以將 Windows Server2008 的 IIS 伺服器放在容錯移轉叢集中。</span><span class="sxs-lookup"><span data-stu-id="43c3f-155">To configure fault tolerance, the Windows Server2008-based IIS server can be placed in a failover cluster.</span></span> <span data-ttu-id="43c3f-156">若要為 IIS 伺服器基礎結構設計容錯性，請參閱[基礎結構規劃及設計 Microsoft 網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=160826)指南。</span><span class="sxs-lookup"><span data-stu-id="43c3f-156">To design the fault tolerance for the IIS server infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

## <span data-ttu-id="43c3f-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="43c3f-157">Related topics</span></span>


[<span data-ttu-id="43c3f-158">使用企業軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="43c3f-158">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)

[<span data-ttu-id="43c3f-159">使用部署套件來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="43c3f-159">Deploying a MED-V Workspace Using a Deployment Package</span></span>](deploying-a-med-v-workspace-using-a-deployment-package.md)

 

 





