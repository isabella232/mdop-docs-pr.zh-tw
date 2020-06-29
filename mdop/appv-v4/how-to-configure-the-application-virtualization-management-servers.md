---
title: 如何設定 Application Virtualization Management Server
description: 如何設定 Application Virtualization Management Server
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801578"
---
# <span data-ttu-id="011c8-103">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="011c8-103">How to Configure the Application Virtualization Management Servers</span></span>


<span data-ttu-id="011c8-104">您必須先設定應用程式虛擬化管理伺服器，才能將虛擬化應用程式流式傳送到應用程式虛擬化桌面用戶端或用戶端以進行遠端桌面服務（舊稱終端服務）。</span><span class="sxs-lookup"><span data-stu-id="011c8-104">Before virtualized applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Management Server must be configured.</span></span> <span data-ttu-id="011c8-105">當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [*內容目錄*]。</span><span class="sxs-lookup"><span data-stu-id="011c8-105">When you configure the server, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="011c8-106">SFT 檔案包含虛擬化的應用程式（或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="011c8-106">The SFT files contain the virtualized application (or applications).</span></span>

<span data-ttu-id="011c8-107">**重要** 應用程式虛擬化伺服器會以 RTSP 或 RTSPS 通訊協定，將 SFT 檔案串流給桌面用戶端和遠端桌面服務的用戶端。</span><span class="sxs-lookup"><span data-stu-id="011c8-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="011c8-108">.ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從不同的檔案或 HTTP 伺服器進行資料流。</span><span class="sxs-lookup"><span data-stu-id="011c8-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="011c8-109">設定應用程式虛擬化管理伺服器</span><span class="sxs-lookup"><span data-stu-id="011c8-109">To configure the Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="011c8-110">完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="011c8-110">Complete the following procedure:</span></span>

    [<span data-ttu-id="011c8-111">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="011c8-111">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="011c8-112">**記事** 在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="011c8-112">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="011c8-113">流覽至您為 \\Content 目錄指定的位置，並視需要建立目錄。</span><span class="sxs-lookup"><span data-stu-id="011c8-113">Navigate to the location that you specified for the \\Content directory, and if necessary, create the directory.</span></span>

3.  <span data-ttu-id="011c8-114">建立內容目錄時，請將此目錄設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="011c8-114">When the content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="011c8-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="011c8-115">Related topics</span></span>


[<span data-ttu-id="011c8-116">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="011c8-116">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="011c8-117">Application Virtualization 系統需求</span><span class="sxs-lookup"><span data-stu-id="011c8-117">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="011c8-118">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="011c8-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="011c8-119">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="011c8-119">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





