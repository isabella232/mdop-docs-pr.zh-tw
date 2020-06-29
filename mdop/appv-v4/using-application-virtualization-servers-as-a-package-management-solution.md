---
title: 使用 Application Virtualization 伺服器做為封裝管理解決方案
description: 使用 Application Virtualization 伺服器做為封裝管理解決方案
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800756"
---
# <span data-ttu-id="e7bf3-103">使用 Application Virtualization 伺服器做為封裝管理解決方案</span><span class="sxs-lookup"><span data-stu-id="e7bf3-103">Using Application Virtualization Servers as a Package Management Solution</span></span>


<span data-ttu-id="e7bf3-104">如果您沒有要部署應用程式虛擬化解決方案或不想要使用的 ESD 系統，您必須安裝一或多個應用程式虛擬化管理伺服器作為系統架構的核心。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-104">If you do not have an existing ESD system to deploy your Application Virtualization solution or do not wish to use one, you will need to install one or more Application Virtualization Management Servers as the core of your system architecture.</span></span> <span data-ttu-id="e7bf3-105">應用程式虛擬化管理伺服器需要專用的伺服器電腦，且需要 Microsoft SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-105">The Application Virtualization Management Server requires a dedicated server computer and needs a Microsoft SQL Server database.</span></span> <span data-ttu-id="e7bf3-106">資料庫可以位於同一個伺服器上，或者可以在可在應用程式虛擬化管理伺服器（在高速局域網連線）上存取的企業資料庫伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-106">The database can be on the same server, or it can be configured on a corporate database server that is accessible to the Application Virtualization Management Server over a high-speed LAN connection.</span></span> <span data-ttu-id="e7bf3-107">此外，您必須在應用程式虛擬化管理伺服器或指定的管理工作站上安裝 Microsoft Application Virtualization 管理主控台，而且您必須安裝 Microsoft Application Virtualization Management Web 服務，這也可以安裝在應用程式虛擬化管理伺服器或個別的 IIS 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-107">In addition, you will need to install the Microsoft Application Virtualization Management Console, on either the Application Virtualization Management Server or on a designated management workstation, and you will need to install the Microsoft Application Virtualization Management Web Service, which can also be installed on the Application Virtualization Management Server or on a separate IIS server.</span></span> <span data-ttu-id="e7bf3-108">應用程式虛擬化管理主控台是用來連線到應用程式虛擬化管理 Web 服務，讓系統管理員可以與應用程式虛擬化管理伺服器互動。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-108">The Application Virtualization Management Console is used to connect to the Application Virtualization Management Web Service, enabling the system administrator to interact with the Application Virtualization Management Server.</span></span>

<span data-ttu-id="e7bf3-109">**記事** 應用程式的存取權是由 Active Directory 網域服務中的安全性群組所控制，因此您必須規劃一個處理常式，為每個虛擬化的應用程式設定安全性群組，以及管理每個群組中新增的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-109">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process to set up a security group for each virtualized application and for managing which users are added to each group.</span></span> <span data-ttu-id="e7bf3-110">應用程式虛擬化管理伺服器管理員會將伺服器設定為使用這些 Active Directory 群組，然後伺服器就會根據 Active Directory 群組成員資格，自動控制對套件的存取權。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-110">The Application Virtualization Management Server administrator configures the server to use these Active Directory groups, and the server then automatically controls access to the packages based on Active Directory group membership.</span></span>

 

## <span data-ttu-id="e7bf3-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="e7bf3-111">In This Section</span></span>


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[<span data-ttu-id="e7bf3-112">Application Virtualization 系統元件概觀</span><span class="sxs-lookup"><span data-stu-id="e7bf3-112">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)  
<span data-ttu-id="e7bf3-113">列出並描述 Microsoft Application Virtualization 管理系統的主要元件。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-113">Lists and describes the primary components of the Microsoft Application Virtualization Management System.</span></span>

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[<span data-ttu-id="e7bf3-114">使用 Application Virtualization Management Server 發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="e7bf3-114">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
<span data-ttu-id="e7bf3-115">提供虛擬應用程式在應用程式虛擬化伺服器部署案例中發佈的方式的簡短概覽。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-115">Provides a brief overview of how virtual applications are published in an Application Virtualization Server-based deployment scenario.</span></span>

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[<span data-ttu-id="e7bf3-116">在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案</span><span class="sxs-lookup"><span data-stu-id="e7bf3-116">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
<span data-ttu-id="e7bf3-117">說明搭配使用應用程式虛擬化流程伺服器與您的應用程式虛擬化管理伺服器部署的可用選項。</span><span class="sxs-lookup"><span data-stu-id="e7bf3-117">Describes available options for using Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation.</span></span>

## <span data-ttu-id="e7bf3-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7bf3-118">Related topics</span></span>


[<span data-ttu-id="e7bf3-119">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="e7bf3-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="e7bf3-120">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="e7bf3-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





