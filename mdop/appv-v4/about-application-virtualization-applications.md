---
title: 關於 Application Virtualization 應用程式
description: 關於 Application Virtualization 應用程式
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802477"
---
# <span data-ttu-id="e9865-103">關於 Application Virtualization 應用程式</span><span class="sxs-lookup"><span data-stu-id="e9865-103">About Application Virtualization Applications</span></span>


<span data-ttu-id="e9865-104">在應用程式虛擬化中，*應用程式*是從應用程式虛擬化管理伺服器傳送到應用程式虛擬化桌面用戶端或用戶端（舊稱終端服務）的可執行程式，例如 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="e9865-104">In Application Virtualization, an *application* is an executable program, such as Microsoft Visio, that is streamed to the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) from an Application Virtualization Management Server.</span></span> <span data-ttu-id="e9865-105">在將應用程式流入用戶端之前，必須先透過應用程式虛擬化排序器處理應用程式，才能進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="e9865-105">Before an application can be streamed to a client, the application must be prepared for streaming by processing it with the Application Virtualization Sequencer.</span></span>

## <span data-ttu-id="e9865-106">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="e9865-106">Managing Applications</span></span>


<span data-ttu-id="e9865-107">您必須先將應用程式新增至系統，才能讓使用者使用這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-107">You must add applications to the system before you can make the applications available to users.</span></span> <span data-ttu-id="e9865-108">在系統中新增應用程式最常見的方法是匯入。</span><span class="sxs-lookup"><span data-stu-id="e9865-108">The most common method for adding applications to the system is to import them.</span></span> <span data-ttu-id="e9865-109">若要存取此功能，請以滑鼠右鍵按一下應用程式虛擬化伺服器管理主控台中的**應用程式**節點，然後選擇 [匯**入應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="e9865-109">To access this feature, right-click the **Applications** node in the Application Virtualization Server Management Console and choose **Import Applications**.</span></span>

<span data-ttu-id="e9865-110">您可以一次匯入一個以上的開啟軟體描述項（OSD）檔案，或者您可以匯入一個可包含多個 OSD 檔案的 Sequencer 專案檔案（SPRJ）。</span><span class="sxs-lookup"><span data-stu-id="e9865-110">You can import more than one Open Software Descriptor (OSD) file at the same time, or you can import a Sequencer Project file (SPRJ) that can contain multiple OSD files.</span></span> <span data-ttu-id="e9865-111">此功能可讓您以類似的方式設定相關的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-111">This functionality enables you to configure related applications similarly.</span></span>

<span data-ttu-id="e9865-112">您也可以使用下列功能來協助您管理您的應用程式：</span><span class="sxs-lookup"><span data-stu-id="e9865-112">You can also use the following features to help you manage your applications:</span></span>

-   <span data-ttu-id="e9865-113">[**應用程式群組**]-可讓您建立應用程式的邏輯群組，以簡化管理。</span><span class="sxs-lookup"><span data-stu-id="e9865-113">**Application Groups**—Enables you to create logical groups of applications for simplified management.</span></span> <span data-ttu-id="e9865-114">對群組進行變更時（例如，存取許可權），這些變更會套用到群組中的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-114">When changes are made to a group (for example, access permissions), the changes are applied to all applications in the group.</span></span> <span data-ttu-id="e9865-115">群組中的應用程式可以來自不同的套件。</span><span class="sxs-lookup"><span data-stu-id="e9865-115">Applications in a group can come from different packages.</span></span>

-   <span data-ttu-id="e9865-116">**多重選取**-可讓您在按一下應用程式來修改應用程式屬性時，按住 CTRL 鍵，同時選取多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-116">**Multi Select**—Enables you to select multiple applications at once by holding the CTRL key when you click an application to modify the application properties.</span></span> <span data-ttu-id="e9865-117">不過，如果您想要維持應用程式之間的關係，您應該建立應用程式群組來存放應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-117">However, if you want to maintain a relationship between the applications, you should create an application group to hold the applications.</span></span>

-   <span data-ttu-id="e9865-118">**跨系統複本**-可讓您將應用程式從一個環境複製到另一個在一個步驟中執行相同版本 App-V 的環境。</span><span class="sxs-lookup"><span data-stu-id="e9865-118">**Cross System Copy**—Enables you to copy applications from one environment to another environment that is running the same version of App-V in one step.</span></span> <span data-ttu-id="e9865-119">例如，您可能會有一個使用者驗收測試環境，您可以在這裡開始部署和設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9865-119">For example, you might have a user acceptance test environment where you initially deploy and configure applications.</span></span> <span data-ttu-id="e9865-120">完成測試階段之後，您可能會想要將一組相同的應用程式（包括許可權）複製到生產環境。</span><span class="sxs-lookup"><span data-stu-id="e9865-120">After you finish your testing phase, you might want to replicate the same set of applications (including permissions) to the production environment.</span></span>

## <span data-ttu-id="e9865-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9865-121">Related topics</span></span>


[<span data-ttu-id="e9865-122">關於 Application Virtualization 封裝</span><span class="sxs-lookup"><span data-stu-id="e9865-122">About Application Virtualization Packages</span></span>](about-application-virtualization-packages.md)

[<span data-ttu-id="e9865-123">關於 Application Virtualization 伺服器管理主控台</span><span class="sxs-lookup"><span data-stu-id="e9865-123">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="e9865-124">如何在伺服器管理主控台中管理應用程式群組</span><span class="sxs-lookup"><span data-stu-id="e9865-124">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="e9865-125">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="e9865-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





