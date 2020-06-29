---
title: 如何建立 App-V 專案範本 (App-V 4.6 SP1)
description: 如何建立 App-V 專案範本 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801501"
---
# <span data-ttu-id="25238-103">如何建立 App-V 專案範本 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="25238-103">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="25238-104">您可以使用 App-v 專案範本來儲存與現有虛擬應用程式套件相關聯的一般套用設定。</span><span class="sxs-lookup"><span data-stu-id="25238-104">You can use an App-V project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="25238-105">當您在您的環境中建立新的虛擬應用程式套件時，就可以套用這些設定，這有助於簡化建立虛擬應用程式套件的程式。</span><span class="sxs-lookup"><span data-stu-id="25238-105">These settings can then be applied when you create new virtual application packages in your environment which can help streamline the process of creating virtual application packages.</span></span>

<span data-ttu-id="25238-106">**記事** 您可以在建立新的虛擬應用程式套件時，套用 V 專案範本。</span><span class="sxs-lookup"><span data-stu-id="25238-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="25238-107">不支援將專案範本套用至現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="25238-107">Applying project templates to existing virtual application packages is not supported.</span></span>

 

<span data-ttu-id="25238-108">如需有關套用 app-v 專案範本的詳細資訊，請參閱[如何套用 App-v 專案範本（app-v 4.6 SP1）](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="25238-108">For more information about applying an App-V project template, see [How to Apply an App-V Project Template (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="25238-109">App-v 專案範本與 App-v 應用程式加速器有所不同，因為 App-v 應用程式加速器是應用程式專用的，而 app-v 專案範本可以套用到多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="25238-109">App-V project templates differ from App-V Application Accelerators because App-V Application Accelerators are application-specific, and App-V project templates can be applied to multiple applications.</span></span> <span data-ttu-id="25238-110">此外，當您使用套件加速器建立虛擬應用程式套件時，您無法使用專案範本。</span><span class="sxs-lookup"><span data-stu-id="25238-110">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span>

<span data-ttu-id="25238-111">下列一般設定會儲存為 App-v 專案範本：</span><span class="sxs-lookup"><span data-stu-id="25238-111">The following general settings are saved with an App-V project template:</span></span>

-   <span data-ttu-id="25238-112">[**高級監視] 選項**。</span><span class="sxs-lookup"><span data-stu-id="25238-112">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="25238-113">可讓 Microsoft 更新在監視、變基 **.dll**中執行。</span><span class="sxs-lookup"><span data-stu-id="25238-113">Enables Microsoft Update to run during monitoring, Rebase **.dll’s**.</span></span>

-   <span data-ttu-id="25238-114">**封裝部署設定**。</span><span class="sxs-lookup"><span data-stu-id="25238-114">**Package Deployment Settings**.</span></span> <span data-ttu-id="25238-115">包含**通訊協定**、**主機名稱**、**埠**、**路徑**、**作業系統**、**強制安全性描述項**、**建立 MSI**、**壓縮套件**。</span><span class="sxs-lookup"><span data-stu-id="25238-115">Contains **Protocol**, **Host Name**, **Port**, **Path**, **Operating Systems**, **Enforce Security Descriptors**, **Create MSI**, **Compress Package**.</span></span>

-   <span data-ttu-id="25238-116">**一般選項**。</span><span class="sxs-lookup"><span data-stu-id="25238-116">**General Options**.</span></span> <span data-ttu-id="25238-117">可讓您**產生 Microsoft Windows Installer （MSI）** 套件、**允許虛擬化事件**、**允許虛擬化服務**、**將套件版本附加至 Filename**。</span><span class="sxs-lookup"><span data-stu-id="25238-117">Allows you to **Generate Microsoft Windows Installer (MSI)** package, **Allow Virtualization of Events**, **Allow Virtualization of Services**, **Append Package Version to Filename**.</span></span>

-   <span data-ttu-id="25238-118">**排除專案**。</span><span class="sxs-lookup"><span data-stu-id="25238-118">**Exclusion Items**.</span></span> <span data-ttu-id="25238-119">包含 [排除] 模式清單。</span><span class="sxs-lookup"><span data-stu-id="25238-119">Contains the Exclusion pattern list.</span></span>

**<span data-ttu-id="25238-120">建立專案範本</span><span class="sxs-lookup"><span data-stu-id="25238-120">To create a project template</span></span>**

1.  <span data-ttu-id="25238-121">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="25238-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="25238-122">如果應用程式套件目前已在 App-v 排序器中開啟，請跳至此程式的步驟3。</span><span class="sxs-lookup"><span data-stu-id="25238-122">If the virtual application package is currently open in the App-V Sequencer, skip to step 3 of this procedure.</span></span> <span data-ttu-id="25238-123">若要開啟現有的虛擬應用程式套件，其中包含您想要使用 app-v 專案範本儲存的設定，請**按一下 [**  /  **開啟**檔案]，然後按一下 [**編輯\*\*\*\*套件**]。</span><span class="sxs-lookup"><span data-stu-id="25238-123">To open the existing virtual application package that contains the settings you want to save with the App-V project template, click **File** / **Open** and click **Edit** **Package**.</span></span> <span data-ttu-id="25238-124">在 [**選取套件**] 頁面上，按一下 **[流覽]** 並找出您要開啟的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="25238-124">On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open.</span></span> <span data-ttu-id="25238-125">按一下**編輯**。</span><span class="sxs-lookup"><span data-stu-id="25238-125">Click **Edit**.</span></span>

3.  <span data-ttu-id="25238-126">在 app-v 排序器主控台中 **，按一下 [**  /  **儲存為範本**]。</span><span class="sxs-lookup"><span data-stu-id="25238-126">In the App-V Sequencer console, click **File** / **Save As Template**.</span></span> <span data-ttu-id="25238-127">在您檢查將與新範本一起儲存的設定後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="25238-127">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="25238-128">指定將與新的 App-v 專案範本相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="25238-128">Specify a name that will be associated with the new App-V project template.</span></span> <span data-ttu-id="25238-129">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="25238-129">Click **Save**.</span></span>

    <span data-ttu-id="25238-130">新的 App-v 專案範本會儲存在此程式步驟3中所指定的目錄中。</span><span class="sxs-lookup"><span data-stu-id="25238-130">The new App-V project template is saved in the directory specified in step 3 of this procedure.</span></span>

## <span data-ttu-id="25238-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="25238-131">Related topics</span></span>


[<span data-ttu-id="25238-132">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="25238-132">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="25238-133">如何套用 App-V 專案範本 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="25238-133">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





