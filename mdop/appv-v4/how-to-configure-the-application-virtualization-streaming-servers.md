---
title: 如何設定 Application Virtualization Streaming Server
description: 如何設定 Application Virtualization Streaming Server
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801570"
---
# <span data-ttu-id="f5377-103">如何設定 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="f5377-103">How to Configure the Application Virtualization Streaming Servers</span></span>


<span data-ttu-id="f5377-104">在虛擬應用程式可以傳送到應用程式虛擬化桌面用戶端或遠端桌面服務的用戶端（以前稱為終端服務）之前，必須先設定應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="f5377-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Streaming Servers must be configured.</span></span> <span data-ttu-id="f5377-105">當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [*內容目錄*]。</span><span class="sxs-lookup"><span data-stu-id="f5377-105">When you configure the servers, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="f5377-106">SFT 檔案包含虛擬應用程式（或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="f5377-106">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="f5377-107">**重要** 應用程式虛擬化伺服器會以 RTSP 或 RTSPS 通訊協定，將 SFT 檔案串流給桌面用戶端和遠端桌面服務的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5377-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="f5377-108">.ICO （圖示）檔案和 OSD （開放式軟體描述項）檔案可以設定為從不同的檔案或 HTTP 伺服器進行資料流。</span><span class="sxs-lookup"><span data-stu-id="f5377-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="f5377-109">設定應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="f5377-109">To configure the Application Virtualization Streaming Servers</span></span>**

1.  <span data-ttu-id="f5377-110">完成應用程式虛擬化流程伺服器的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f5377-110">Complete the installation procedure for the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="f5377-111">在安裝過程中，您會在 [**內容路徑**] 畫面上指定 \\Content 目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="f5377-111">During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

2.  <span data-ttu-id="f5377-112">流覽至您為 \\Content 目錄指定的位置，如果您需要，請建立目錄。</span><span class="sxs-lookup"><span data-stu-id="f5377-112">Navigate to the location that you specified for the \\Content directory, and if you have to, create the directory.</span></span>

3.  <span data-ttu-id="f5377-113">建立內容目錄時，請將此目錄設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="f5377-113">When the Content directory is created, configure this directory as a standard file share.</span></span>

4.  <span data-ttu-id="f5377-114">將 NTFS 檔案系統許可權設定為 [內容目錄]，以及 [內容目錄] 底下的 [套件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f5377-114">Configure the NTFS file system permissions to the Content directory and the package folders under the Content directory.</span></span> <span data-ttu-id="f5377-115">您應該在 Active Directory 網域服務中使用安全性群組，定義哪些使用者可以存取每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5377-115">You should use Security Groups in Active Directory Domain Services that define which users can access each application.</span></span>

## <span data-ttu-id="f5377-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="f5377-116">Related topics</span></span>


[<span data-ttu-id="f5377-117">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="f5377-117">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="f5377-118">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="f5377-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="f5377-119">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="f5377-119">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="f5377-120">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="f5377-120">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

[<span data-ttu-id="f5377-121">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="f5377-121">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





