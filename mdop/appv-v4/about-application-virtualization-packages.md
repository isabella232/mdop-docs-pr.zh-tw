---
title: 關於 Application Virtualization 封裝
description: 關於 Application Virtualization 封裝
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802474"
---
# <span data-ttu-id="0be83-103">關於 Application Virtualization 封裝</span><span class="sxs-lookup"><span data-stu-id="0be83-103">About Application Virtualization Packages</span></span>


<span data-ttu-id="0be83-104">在應用程式虛擬化中，*套件*是先後順序程式的輸出。</span><span class="sxs-lookup"><span data-stu-id="0be83-104">In Application Virtualization, a *package* is the output of the sequencing process.</span></span> <span data-ttu-id="0be83-105">當您第一次在伺服器上部署應用程式，且使用新版本升級應用程式時，就會使用套件。</span><span class="sxs-lookup"><span data-stu-id="0be83-105">You use packages when you first deploy applications on your servers and when you upgrade applications with a new version.</span></span> <span data-ttu-id="0be83-106">套件可讓您控制應用程式虛擬化管理伺服器上的虛擬應用程式版本。</span><span class="sxs-lookup"><span data-stu-id="0be83-106">Packages enable you to control virtual application versions on your Application Virtualization Management Servers.</span></span> <span data-ttu-id="0be83-107">單一套件可以包含一或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="0be83-107">A single package can contain one or more applications.</span></span> <span data-ttu-id="0be83-108">每個應用程式套件都包含一組檔案，作為自包含的單元。</span><span class="sxs-lookup"><span data-stu-id="0be83-108">Each application package contains a set of files as a self-contained unit.</span></span>

## <span data-ttu-id="0be83-109">管理套件</span><span class="sxs-lookup"><span data-stu-id="0be83-109">Managing Packages</span></span>


<span data-ttu-id="0be83-110">在排序器建立一個或多個應用程式的套件做為其進程的一部分之後，您可以將 Sequencer 產生的檔案複製到應用程式虛擬化管理伺服器，並讓它們可供流式處理使用。</span><span class="sxs-lookup"><span data-stu-id="0be83-110">After the Sequencer creates a package of one or more applications as part of its process, you can copy the Sequencer-generated files to a Application Virtualization Management Server and make them available for streaming.</span></span>

<span data-ttu-id="0be83-111">可用的套件會出現在應用程式虛擬化管理主控台左窗格中的 [**套件**] 容器底下。</span><span class="sxs-lookup"><span data-stu-id="0be83-111">Available packages appear under the **Packages** container in the left pane of the Application Virtualization Management Console.</span></span> <span data-ttu-id="0be83-112">當您匯入含有 Sequencer 專案（SPRJ）檔案或開啟軟體描述項（OSD）檔案的應用程式時，會在 [**套件**] 容器中出現相關專案。</span><span class="sxs-lookup"><span data-stu-id="0be83-112">When you import an application with a Sequencer Project (SPRJ) file or an Open Software Descriptor (OSD) file, a related entry appears in the **Packages** container.</span></span> <span data-ttu-id="0be83-113">您可以從應用程式虛擬化伺服器管理主控台，部署、升級或刪除套件及版本。</span><span class="sxs-lookup"><span data-stu-id="0be83-113">From the Application Virtualization Server Management Console, you can then deploy, upgrade, or delete packages and versions of them.</span></span>

<span data-ttu-id="0be83-114">每個虛擬應用程式都有一個相關聯的套件。</span><span class="sxs-lookup"><span data-stu-id="0be83-114">Each virtual application has an associated package.</span></span> <span data-ttu-id="0be83-115">此套件包含下列檔案：</span><span class="sxs-lookup"><span data-stu-id="0be83-115">This package includes the following files:</span></span>

-   <span data-ttu-id="0be83-116">SFT：將應用程式流向用戶端的檔案。</span><span class="sxs-lookup"><span data-stu-id="0be83-116">SFT—The file that streams the application to clients.</span></span>

-   <span data-ttu-id="0be83-117">OSD —開啟的軟體描述項檔案包含尋找及啟動應用程式所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="0be83-117">OSD—The Open Software Descriptor file contains the information needed to find and launch the application.</span></span>

-   <span data-ttu-id="0be83-118">.ICO：圖示檔案，以視覺方式代表使用者介面和快速鍵中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0be83-118">ICO—The icon file that visually represents the application in user interfaces and shortcuts.</span></span>

-   <span data-ttu-id="0be83-119">SPRJ-Sequencer 專案檔案。</span><span class="sxs-lookup"><span data-stu-id="0be83-119">SPRJ—The Sequencer Project file.</span></span>

<span data-ttu-id="0be83-120">當您匯入 SPRJ 檔案時，預設會提供所有已排序的應用程式，但不會啟用應用程式來進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="0be83-120">When you import the SPRJ file, all sequenced applications are available for deployment, by default, but the applications are not enabled for streaming.</span></span> <span data-ttu-id="0be83-121">您可以選擇在套件中傳輸所有或部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="0be83-121">You can choose to stream all or some of the applications in the package.</span></span> <span data-ttu-id="0be83-122">例如，如果您已排序並匯入 Microsoft Office，您可以選擇不部署某些應用程式（例如 [儲存我的設定] 嚮導）。</span><span class="sxs-lookup"><span data-stu-id="0be83-122">For example, if you sequenced and imported Microsoft Office, you can choose not to deploy some applications, such as the Save My Settings Wizard.</span></span> <span data-ttu-id="0be83-123">在這種情況下，以滑鼠右鍵按一下您要部署的每個應用程式，選擇 [**屬性**]，並確認已清除 [**啟用**] 方塊（空白）。</span><span class="sxs-lookup"><span data-stu-id="0be83-123">In this case, right-click each application you want to deploy, choose **Properties**, and make sure that the **Enabled** box is cleared (blank).</span></span> <span data-ttu-id="0be83-124">只有已選取 [**啟用**] 方塊的應用程式才會資料流程至用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="0be83-124">Only the applications with the **Enabled** box selected will stream to client computers.</span></span>

<span data-ttu-id="0be83-125">在您 resequence 套件並產生新的 SFT 檔案以進行流式處理之後，您就可以透過應用程式虛擬化伺服器管理主控台快速且輕鬆地升級舊套件。</span><span class="sxs-lookup"><span data-stu-id="0be83-125">After you resequence a package and produce a new SFT file for streaming, you can upgrade the old package quickly and easily through the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="0be83-126">需要您使用 [**套件**] 節點的唯一操作案例就是當您為套件推出新版本（SFT 檔案）時。</span><span class="sxs-lookup"><span data-stu-id="0be83-126">The only operational scenario that requires you to use the **Packages** node is when you introduce a new version (SFT file) for the package.</span></span> <span data-ttu-id="0be83-127">每當您匯入應用程式、將存取權和授權指派給應用程式等，應用程式虛擬化系統就會在封裝層級追蹤此資訊。</span><span class="sxs-lookup"><span data-stu-id="0be83-127">Whenever you import applications, assign access and licenses to applications, and so on, the Application Virtualization System tracks this information at the package level.</span></span> <span data-ttu-id="0be83-128">這表示當您授權使用者使用應用程式時，您會給予使用者許可權，以在同一個套件中執行任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="0be83-128">This means that when you authorize a user to use an application, you are giving the user permission to run any application in the same package.</span></span>

### <span data-ttu-id="0be83-129">套件版本</span><span class="sxs-lookup"><span data-stu-id="0be83-129">Package Version</span></span>

<span data-ttu-id="0be83-130">套件版本是由特定的 SFT 檔案所代表。</span><span class="sxs-lookup"><span data-stu-id="0be83-130">A package version is represented by a specific SFT file.</span></span> <span data-ttu-id="0be83-131">當您升級套件時（將更新套用至應用程式或將應用程式新增到套件），您會產生新的 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="0be83-131">When you upgrade a package (apply an update to an application or add an application to a package), you generate a new SFT file.</span></span> <span data-ttu-id="0be83-132">每當您建立新的 SFT 檔案時，就會建立新的套件版本。</span><span class="sxs-lookup"><span data-stu-id="0be83-132">Each time you create a new SFT file, you are creating a new package version.</span></span>

<span data-ttu-id="0be83-133">當您透過應用程式虛擬化伺服器管理主控台匯入應用程式時，軟體會自動建立套件和套件版本（如果它們尚不存在的話）。</span><span class="sxs-lookup"><span data-stu-id="0be83-133">When you import applications through the Application Virtualization Server Management Console, the software automatically creates a package and a package version if they do not already exist.</span></span>

## <span data-ttu-id="0be83-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="0be83-134">Related topics</span></span>


[<span data-ttu-id="0be83-135">關於 Application Virtualization 應用程式</span><span class="sxs-lookup"><span data-stu-id="0be83-135">About Application Virtualization Applications</span></span>](about-application-virtualization-applications.md)

[<span data-ttu-id="0be83-136">關於 Application Virtualization 伺服器管理主控台</span><span class="sxs-lookup"><span data-stu-id="0be83-136">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="0be83-137">如何在伺服器管理主控台中管理封裝</span><span class="sxs-lookup"><span data-stu-id="0be83-137">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





