---
title: 獨立傳遞案例概觀
description: 獨立傳遞案例概觀
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800793"
---
# <span data-ttu-id="fe4cc-103">獨立傳遞案例概觀</span><span class="sxs-lookup"><span data-stu-id="fe4cc-103">Stand-Alone Delivery Scenario Overview</span></span>


<span data-ttu-id="fe4cc-104">獨立傳遞案例是適用于低頻寬連接或無連線性的環境的理想應用程式虛擬化方案，可限制應用程式虛擬化桌面用戶端從集中式伺服器對流應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-104">The stand-alone delivery scenario is an ideal application virtualization solution for environments where either low bandwidth connectivity or no connectivity limits the ability of the Application Virtualization Desktop Client to stream applications from centralized servers.</span></span> <span data-ttu-id="fe4cc-105">在這些環境中，使用者通常會使用 Windows 安裝程式檔案，在遠端和裝置擁有者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-105">In these environments, users often work remotely and device owners install applications by using Windows Installer files.</span></span>

<span data-ttu-id="fe4cc-106">您可以使用應用程式虛擬化 Sequencer 來建立包含 Windows 安裝程式檔案的順序應用程式。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-106">You can use the Application Virtualization Sequencer to create sequenced applications that include Windows Installer files.</span></span> <span data-ttu-id="fe4cc-107">這些套件包括虛擬化應用程式、發佈資訊，以及在用戶端系統上安裝套件所需的安裝程式常式。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-107">These packages include the virtualized applications, publication information, and the necessary installer routines for installing the packages on the client systems.</span></span> <span data-ttu-id="fe4cc-108">安裝程式會將虛擬應用程式套件新增至 Microsoft Application Virtualization 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-108">The installer adds the virtual application package to the Microsoft Application Virtualization Desktop Client.</span></span> <span data-ttu-id="fe4cc-109">發佈資訊被設定為從本機位置載入應用程式，而不是在 WAN 上對流進行資料流。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-109">The publication information is configured to load applications from a local location rather than stream them across a WAN.</span></span> <span data-ttu-id="fe4cc-110">使用者可以暫時連線到網路，以取得 Windows 安裝程式檔案，或從 DVD 執行這些檔案。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-110">Users can temporarily connect to a network to retrieve the Windows Installer files or can run them from a DVD.</span></span>

<span data-ttu-id="fe4cc-111">獨立的交付案例會為使用者提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="fe4cc-111">The stand-alone delivery scenario provides users the following benefits:</span></span>

-   <span data-ttu-id="fe4cc-112">簡單的部署作業。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-112">Simple deployment operation.</span></span>

-   <span data-ttu-id="fe4cc-113">在執行時間中不需要網路和伺服器。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-113">Network and servers not needed at runtime.</span></span>

-   <span data-ttu-id="fe4cc-114">已預先快取並可供所有使用者使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-114">Applications pre-cached and available to all users.</span></span>

<span data-ttu-id="fe4cc-115">獨立傳遞案例有下列限制：</span><span class="sxs-lookup"><span data-stu-id="fe4cc-115">The stand-alone delivery scenario has the following limitations:</span></span>

-   <span data-ttu-id="fe4cc-116">內建的自動報告功能無法使用;報表必須是使用外部報表工具產生的。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-116">Built-in, automated reporting is unavailable; reports must be generated with external reporting tools.</span></span>

-   <span data-ttu-id="fe4cc-117">應用程式必須手動傳送到用戶端，就像原始的 Windows 安裝程式檔案一樣。</span><span class="sxs-lookup"><span data-stu-id="fe4cc-117">Applications must be delivered to the client manually like the original Windows Installer files.</span></span>

## <span data-ttu-id="fe4cc-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="fe4cc-118">Related topics</span></span>


[<span data-ttu-id="fe4cc-119">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="fe4cc-119">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="fe4cc-120">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="fe4cc-120">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





