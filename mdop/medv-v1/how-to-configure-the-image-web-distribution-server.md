---
title: 如何設定映像 Web 發佈伺服器
description: 如何設定映像 Web 發佈伺服器
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810988"
---
# <span data-ttu-id="30c63-103">如何設定映像 Web 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="30c63-103">How to Configure the Image Web Distribution Server</span></span>


<span data-ttu-id="30c63-104">影像儲存庫是用來進行影像發佈的選用伺服器（在此情況下，系統管理員上傳新影像和用戶端電腦每15分鐘檢查一次伺服器，並在有新的映射時更新它）。</span><span class="sxs-lookup"><span data-stu-id="30c63-104">An image repository is an optional server that is used for image distribution (where administrators upload new images and client computers check the server every 15 minutes and update their image if a new one is available).</span></span>

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


<span data-ttu-id="30c63-105">影像發佈伺服器需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="30c63-105">An image distribution server requires the following:</span></span>

-   <span data-ttu-id="30c63-106">網際網路資訊服務（IIS）：如需詳細資訊，請參閱[網際網路資訊服務](https://go.microsoft.com/fwlink/?LinkId=142995)。</span><span class="sxs-lookup"><span data-stu-id="30c63-106">Internet Information Services (IIS)—For information, see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=142995).</span></span>

    <span data-ttu-id="30c63-107">在 IIS 安裝期間，在新增角色服務時，請選取下列支援的驗證方法：</span><span class="sxs-lookup"><span data-stu-id="30c63-107">During the IIS installation, when adding role services, select the following supported authentication methods:</span></span>

    -   **<span data-ttu-id="30c63-108">基本驗證</span><span class="sxs-lookup"><span data-stu-id="30c63-108">Basic Authentication</span></span>**

    -   **<span data-ttu-id="30c63-109">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="30c63-109">Windows Authentication</span></span>**

    -   **<span data-ttu-id="30c63-110">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="30c63-110">Client Certificate Mapping Authentication</span></span>**

    <span data-ttu-id="30c63-111">配置 IIS 時，請包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="30c63-111">When configuring IIS, include the following:</span></span>

    -   <span data-ttu-id="30c63-112">使用名為**MEDVImages**的別名新增虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="30c63-112">Add a virtual directory, with the alias named **MEDVImages**.</span></span> <span data-ttu-id="30c63-113">實體路徑應該指向影像的位置。</span><span class="sxs-lookup"><span data-stu-id="30c63-113">The physical path should point to the location of the images.</span></span>

    -   <span data-ttu-id="30c63-114">啟用 BITS。</span><span class="sxs-lookup"><span data-stu-id="30c63-114">Enable BITS.</span></span>

    -   <span data-ttu-id="30c63-115">新增下列 MIME 類型：</span><span class="sxs-lookup"><span data-stu-id="30c63-115">Add the following MIME types:</span></span>

        -   **<span data-ttu-id="30c63-116">. ckm （應用程式/八進位資料流程）</span><span class="sxs-lookup"><span data-stu-id="30c63-116">.ckm (application/octet-stream)</span></span>**

        -   <span data-ttu-id="30c63-117">**. index （應用程式/八進位資料流程**）</span><span class="sxs-lookup"><span data-stu-id="30c63-117">**.index (application/octet-stream**)</span></span>

    -   <span data-ttu-id="30c63-118">在 MED-V 網站上，新增 [讀取] 許可權給**所有人**。</span><span class="sxs-lookup"><span data-stu-id="30c63-118">On the MED-V site, add read permissions to **Everyone**.</span></span>

    -   <span data-ttu-id="30c63-119">重新開機 IIS。</span><span class="sxs-lookup"><span data-stu-id="30c63-119">Restart IIS.</span></span>

-   <span data-ttu-id="30c63-120">BITS 伺服器的 IIS 擴展：如需詳細資訊，請參閱[安裝 BITS 伺服器延伸](https://go.microsoft.com/fwlink/?LinkId=142996)。</span><span class="sxs-lookup"><span data-stu-id="30c63-120">BITS Server Extensions for IIS—For information, see [Install BITS Server Extensions](https://go.microsoft.com/fwlink/?LinkId=142996).</span></span>

## <span data-ttu-id="30c63-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="30c63-121">Related topics</span></span>


[<span data-ttu-id="30c63-122">支援的設定</span><span class="sxs-lookup"><span data-stu-id="30c63-122">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="30c63-123">設計 MED-V 映像存放庫</span><span class="sxs-lookup"><span data-stu-id="30c63-123">Design the MED-V Image Repositories</span></span>](design-the-med-v-image-repositories.md)

 

 





