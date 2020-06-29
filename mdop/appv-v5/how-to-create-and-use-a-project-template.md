---
title: 如何建立及使用專案範本
description: 如何建立及使用專案範本
author: dansimp
ms.assetid: 2063f0b3-47a1-4090-bf99-0f26b107331c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e7640b9dc1e7baec194315400ee5672dfa83f394
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800549"
---
# <span data-ttu-id="c0ec1-103">如何建立及使用專案範本</span><span class="sxs-lookup"><span data-stu-id="c0ec1-103">How to Create and Use a Project Template</span></span>


<span data-ttu-id="c0ec1-104">您可以使用 App-v 5.0 專案範本來儲存與現有虛擬應用程式套件相關聯的一般套用設定。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-104">You can use an App-V 5.0 project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="c0ec1-105">當您在您的環境中建立新的虛擬應用程式套件時，就可以套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-105">These settings can then be applied when you create new virtual application packages in your environment.</span></span> <span data-ttu-id="c0ec1-106">使用專案範本可以簡化建立虛擬應用程式套件的過程。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-106">Using a project template can streamline the process of creating virtual application packages.</span></span>

<span data-ttu-id="c0ec1-107">**記事** 您可以，通常應該在套件升級期間套用 app-v 5.0 專案範本。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-107">**Note** You can, and often should apply an App-V 5.0 project template during a package upgrade.</span></span> <span data-ttu-id="c0ec1-108">例如，如果您以自訂排除清單為應用程式排序，建議您在升級已排序的應用程式時，會建立並儲存相關的範本供日後使用。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-108">For example, if you sequenced an application with a custom exclusion list, it is recommended that an associated template is created and saved for later use while upgrading the sequenced application.</span></span>

<span data-ttu-id="c0ec1-109">App-v 5.0 專案範本與 App-v 5.0 應用程式加速器不同，因為 App-v 5.0 應用程式加速器是應用程式專用的，而 App-v 5.0 專案範本可以套用到多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-109">App-V 5.0 project templates differ from App-V 5.0 Application Accelerators because App-V 5.0 Application Accelerators are application-specific, and App-V 5.0 project templates can be applied to multiple applications.</span></span>

<span data-ttu-id="c0ec1-110">使用下列程式來建立並套用新範本。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-110">Use the following procedures to create and apply a new template.</span></span>

**<span data-ttu-id="c0ec1-111">建立專案範本</span><span class="sxs-lookup"><span data-stu-id="c0ec1-111">To create a project template</span></span>**

1.  <span data-ttu-id="c0ec1-112">若要啟動 app-v 5.0 排序器，請在執行排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-112">To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

<span data-ttu-id="c0ec1-113">**記事** 如果應用程式套件目前已在 App-v 5.0 排序器主控台中開啟，請跳至此程式的步驟3。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-113">**Note** If the virtual application package is currently open in the App-V 5.0 Sequencer console, skip to step 3 of this procedure.</span></span>

2. <span data-ttu-id="c0ec1-114">若要開啟包含您想要儲存 App-V 5.0 專案範本之設定的現有虛擬應用程式套件，**請按一下 [**  /  **開啟**檔案]，然後按一下 [**編輯套件**]。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-114">To open the existing virtual application package that contains the settings you want to save with the App-V 5.0 project template, click **File** / **Open**, and then click **Edit Package**.</span></span> <span data-ttu-id="c0ec1-115">在 [**選取套件**] 頁面上，按一下 **[流覽]** 並找出您要開啟的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-115">On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open.</span></span> <span data-ttu-id="c0ec1-116">按一下**編輯**。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-116">Click **Edit**.</span></span>

3. <span data-ttu-id="c0ec1-117">在 app-v 5.0 Sequencer 主機中，若要儲存範本檔案，**請按一下 [** 檔案  /  **另存為範本**]。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-117">In the App-V 5.0 Sequencer console, to save the template file, click **File** / **Save As Template**.</span></span> <span data-ttu-id="c0ec1-118">在您檢查將與新範本一起儲存的設定後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-118">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="c0ec1-119">指定將與新的 App-v 5.0 專案範本相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-119">Specify a name that will be associated with the new App-V 5.0 project template.</span></span> <span data-ttu-id="c0ec1-120">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-120">Click Save.</span></span>
   <span data-ttu-id="c0ec1-121">新的 App-v 5.0 專案範本會儲存在此程式步驟3中所指定的目錄中。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-121">The new App-V 5.0 project template is saved in the directory specified in step 3 of this procedure.</span></span>

**<span data-ttu-id="c0ec1-122">若要套用專案範本</span><span class="sxs-lookup"><span data-stu-id="c0ec1-122">To apply a project template</span></span>**

<span data-ttu-id="c0ec1-123">**重要** 不支援使用專案範本與套件加速器結合建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-123">**Important** Creating a virtual application package using a project template in conjunction with a Package Accelerator is not supported.</span></span>

1.  <span data-ttu-id="c0ec1-124">若要啟動 app-v 5.0 排序器，請在執行排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-124">To start the App-V 5.0 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="c0ec1-125">若要使用 app-v 5.0 專案範本來建立或升級新的虛擬應用程式套件，**請按一下 [**  /  **從範本新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-125">To create or upgrade a new virtual application package by using an App-V 5.0 project template, click **File** / **New From Template**.</span></span>

3.  <span data-ttu-id="c0ec1-126">若要選取您要使用的專案範本，請流覽至儲存專案範本的目錄，選取專案範本，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-126">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

    <span data-ttu-id="c0ec1-127">建立新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-127">Create the new virtual application package.</span></span> <span data-ttu-id="c0ec1-128">儲存在指定範本的設定將會套用至您要建立的新虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-128">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span>

    <span data-ttu-id="c0ec1-129">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="c0ec1-129">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="c0ec1-130">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-130">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="c0ec1-131">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="c0ec1-131">Got an App-V issue?</span></span>** <span data-ttu-id="c0ec1-132">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="c0ec1-132">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="c0ec1-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="c0ec1-133">Related topics</span></span>


[<span data-ttu-id="c0ec1-134">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="c0ec1-134">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









