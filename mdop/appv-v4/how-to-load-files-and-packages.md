---
title: 如何載入檔案和封裝
description: 如何載入檔案和封裝
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801337"
---
# <span data-ttu-id="29900-103">如何載入檔案和封裝</span><span class="sxs-lookup"><span data-stu-id="29900-103">How to Load Files and Packages</span></span>


<span data-ttu-id="29900-104">您可以使用下列程式，在應用程式虛擬化伺服器上載入檔案和套件。</span><span class="sxs-lookup"><span data-stu-id="29900-104">You can use the following procedure to load files and packages on Application Virtualization Servers.</span></span>

<span data-ttu-id="29900-105">**記事** 在安裝過程中，您已在 [**內容路徑**] 頁面上指定 \\Content 目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="29900-105">**Note** During the installation process, you specified the location of the \\Content directory on the **Content Path** page.</span></span> <span data-ttu-id="29900-106">在您指向其位置之前，應該先建立並將此目錄設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="29900-106">This directory should be created and configured as a standard file share before you point to its location.</span></span>

 

**<span data-ttu-id="29900-107">載入檔案和套件</span><span class="sxs-lookup"><span data-stu-id="29900-107">To load files and packages</span></span>**

1.  <span data-ttu-id="29900-108">在您要將應用程式流式處理的電腦上，流覽至您為 \\Content 目錄指定的位置。</span><span class="sxs-lookup"><span data-stu-id="29900-108">On the computer from which you will stream applications, navigate to the location that you specified for the \\Content directory.</span></span> <span data-ttu-id="29900-109">如有需要，請建立目錄並將它設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="29900-109">If necessary, create the directory and configure it as a standard file share.</span></span>

2.  <span data-ttu-id="29900-110">將虛擬應用程式和套件的 SFT 檔案移至 \\Content 目錄。</span><span class="sxs-lookup"><span data-stu-id="29900-110">Move the SFT files for the virtual applications and packages to the \\Content directory.</span></span> <span data-ttu-id="29900-111">若要讓 SFT 檔案保持井然有序並避免混淆，請將應用程式和套件放在專用的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="29900-111">To keep the SFT files organized and to avoid confusion, put applications and packages in dedicated subfolders.</span></span>

3.  <span data-ttu-id="29900-112">根據案例和設定的需求載入應用程式和套件，考慮下列情況：</span><span class="sxs-lookup"><span data-stu-id="29900-112">Load the applications and packages according to the requirements of your scenario and configuration, considering the following conditions:</span></span>

    -   <span data-ttu-id="29900-113">如果您的應用程式和套件儲存在應用程式虛擬化（App-v）管理伺服器上，請透過管理主控台載入它們。</span><span class="sxs-lookup"><span data-stu-id="29900-113">If your applications and packages are stored on an Application Virtualization (App-V) Management Server, load them through the Management Console.</span></span> <span data-ttu-id="29900-114">如需詳細資訊，請參閱[如何載入或卸載應用程式](how-to-load-or-unload-an-application.md)，或[如何從桌面通知區域載入虛擬應用程式](how-to-load-virtual-applications-from-the-desktop-notification-area.md)。</span><span class="sxs-lookup"><span data-stu-id="29900-114">For more information, see [How to Load or Unload an Application](how-to-load-or-unload-an-application.md) or [How to Load Virtual Applications from the Desktop Notification Area](how-to-load-virtual-applications-from-the-desktop-notification-area.md).</span></span>

    -   <span data-ttu-id="29900-115">如果您的應用程式儲存在 App-v 流式處理伺服器、Web 服務器或設定為檔案伺服器的電腦上，則可以自動載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="29900-115">If your applications are stored on an App-V Streaming Server, a Web server, or a computer configured as a file server, the applications can be automatically loaded.</span></span>

        <span data-ttu-id="29900-116">**記事** App-v 流式處理伺服器會自動為應用程式和套件輪詢 \\Content 目錄，並將此資訊放在 RAM 中以服務于應用程式要求。</span><span class="sxs-lookup"><span data-stu-id="29900-116">**Note** The App-V Streaming Server automatically polls the \\Content directory for applications and packages and puts this information in RAM to service application requests.</span></span>

        <span data-ttu-id="29900-117">App-v 用戶端必須正確設定，才能從 Web 服務器與檔案伺服器中檢索應用程式和套件。</span><span class="sxs-lookup"><span data-stu-id="29900-117">The App-V Clients must be properly configured to retrieve applications and packages from Web servers and file servers.</span></span> <span data-ttu-id="29900-118">如需詳細資訊，請參閱[如何針對應用程式套件檢索設定用戶端](how-to-configure-the-client-for-application-package-retrieval.md)。</span><span class="sxs-lookup"><span data-stu-id="29900-118">For more information, see [How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md).</span></span>

         

## <span data-ttu-id="29900-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="29900-119">Related topics</span></span>


[<span data-ttu-id="29900-120">Application Virtualization 伺服器</span><span class="sxs-lookup"><span data-stu-id="29900-120">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





