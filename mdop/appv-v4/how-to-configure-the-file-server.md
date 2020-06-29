---
title: 如何設定檔案伺服器
description: 如何設定檔案伺服器
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801554"
---
# <span data-ttu-id="4e0b5-103">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="4e0b5-103">How to Configure the File Server</span></span>


<span data-ttu-id="4e0b5-104">您可以使用下列程式，將本機電腦設定為檔案共用，並將應用程式流式處理到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-104">You can use the following procedure to configure a local computer that is used as a file share and streams applications to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="4e0b5-105">當您不想要將其他伺服器基礎結構新增到您現有的硬體環境時，就會用到此案例。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-105">This scenario is used when you do not want to add an additional server infrastructure to your existing hardware environment.</span></span>

<span data-ttu-id="4e0b5-106">如果您是使用應用程式虛擬化管理伺服器作為在本機辦公室中安裝之檔案共用的發佈點，則您必須先設定此伺服器，才能將虛擬應用程式流式傳送到用作檔案共用的電腦。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-106">If you are using an Application Virtualization Management Server as a distribution point to the file share installed in local offices, you must configure this server before virtual applications can be streamed to the computers that are used as file shares.</span></span> <span data-ttu-id="4e0b5-107">當您設定伺服器與檔案共用時，您將會設定在其中載入並儲存 SFT 檔案的內容目錄。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-107">When you configure the servers and the file shares, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="4e0b5-108">SFT 檔案包含虛擬應用程式（或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-108">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="4e0b5-109">**重要** 若要將應用程式正確地資料流程傳送到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端，SFT 檔案會從您儲存虛擬應用程式的伺服器上的內容目錄傳送資料流程;.ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從其他伺服器進行資料流程。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-109">**Important** For applications to stream properly to the Application Virtualization Desktop Client and the Client for Remote Desktop Services, the SFT file streams from the content directory on the server where you store the virtual application; the ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different server.</span></span>

 

**<span data-ttu-id="4e0b5-110">設定應用程式虛擬化檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="4e0b5-110">To configure the Application Virtualization file server</span></span>**

1.  <span data-ttu-id="4e0b5-111">完成下列安裝程式，以設定用來做為發佈點的伺服器：</span><span class="sxs-lookup"><span data-stu-id="4e0b5-111">Complete the following installation procedure to configure the server that is used as the distribution point:</span></span>

    [<span data-ttu-id="4e0b5-112">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="4e0b5-112">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="4e0b5-113">**記事** 在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-113">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="4e0b5-114">建立 \\Content 目錄，該目錄會對應到您在安裝伺服器時所指定的目錄，並在您要做為檔案共用的每個電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-114">Create a \\Content directory, which corresponds to the directory you specified when you installed the server, on each computer that you are using as a file share.</span></span>

    <span data-ttu-id="4e0b5-115">**重要** 設定應用程式虛擬化桌面用戶端，以從您要做為檔案共用的電腦（而不是從應用程式虛擬化伺服器或 IIS 伺服器）來資料流應用程式。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-115">**Important** Configure the Application Virtualization Desktop Clients to stream applications from the computer you are using as a file share rather than from an Application Virtualization Server or IIS server.</span></span>

     

3.  <span data-ttu-id="4e0b5-116">建立 \\Content 目錄時，請將此目錄設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="4e0b5-116">When the \\Content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="4e0b5-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="4e0b5-117">Related topics</span></span>


[<span data-ttu-id="4e0b5-118">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="4e0b5-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="4e0b5-119">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="4e0b5-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="4e0b5-120">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="4e0b5-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="4e0b5-121">如何設定 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="4e0b5-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="4e0b5-122">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="4e0b5-122">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





