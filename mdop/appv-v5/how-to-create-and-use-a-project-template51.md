---
title: 如何建立及使用專案範本
description: 如何建立及使用專案範本
author: dansimp
ms.assetid: e5ac1dc8-a88f-4b16-8e3c-df07ef5e4c3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de3471eca39d3804e8c5f070c5ec37560fae5dc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800546"
---
# <span data-ttu-id="0d2f8-103">如何建立及使用專案範本</span><span class="sxs-lookup"><span data-stu-id="0d2f8-103">How to Create and Use a Project Template</span></span>


<span data-ttu-id="0d2f8-104">您可以使用 App-v 5.1 專案範本來儲存與現有虛擬應用程式套件相關聯的一般套用設定。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-104">You can use an App-V 5.1 project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="0d2f8-105">當您在您的環境中建立新的虛擬應用程式套件時，就可以套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-105">These settings can then be applied when you create new virtual application packages in your environment.</span></span> <span data-ttu-id="0d2f8-106">使用專案範本可以簡化建立虛擬應用程式套件的過程。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-106">Using a project template can streamline the process of creating virtual application packages.</span></span>

**<span data-ttu-id="0d2f8-107">注意</span><span class="sxs-lookup"><span data-stu-id="0d2f8-107">Note</span></span>**  
<span data-ttu-id="0d2f8-108">您可以，通常應該在套件升級期間套用 app-v 5.1 專案範本。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-108">You can, and often should apply an App-V 5.1 project template during a package upgrade.</span></span> <span data-ttu-id="0d2f8-109">例如，如果您以自訂排除清單為應用程式排序，建議您在升級已排序的應用程式時，會建立並儲存相關的範本供日後使用。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-109">For example, if you sequenced an application with a custom exclusion list, it is recommended that an associated template is created and saved for later use while upgrading the sequenced application.</span></span>



<span data-ttu-id="0d2f8-110">App-v 5.1 專案範本與 App-v 5.1 應用程式加速器不同，因為 App-v 5.1 應用程式加速器是應用程式專用的，而 App-v 5.1 專案範本可以套用到多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-110">App-V 5.1 project templates differ from App-V 5.1 Application Accelerators because App-V 5.1 Application Accelerators are application-specific, and App-V 5.1 project templates can be applied to multiple applications.</span></span>

<span data-ttu-id="0d2f8-111">使用下列程式來建立並套用新範本。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-111">Use the following procedures to create and apply a new template.</span></span>

**<span data-ttu-id="0d2f8-112">建立專案範本</span><span class="sxs-lookup"><span data-stu-id="0d2f8-112">To create a project template</span></span>**

1.  <span data-ttu-id="0d2f8-113">若要啟動 app-v 5.1 排序器，請在執行排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-113">To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  **<span data-ttu-id="0d2f8-114">注意</span><span class="sxs-lookup"><span data-stu-id="0d2f8-114">Note</span></span>**  
    <span data-ttu-id="0d2f8-115">如果應用程式套件目前已在 App-v 5.1 排序器主控台中開啟，請跳至此程式的步驟3。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-115">If the virtual application package is currently open in the App-V 5.1 Sequencer console, skip to step 3 of this procedure.</span></span>



~~~
To open the existing virtual application package that contains the settings you want to save with the App-V 5.1 project template, click **File** / **Open**, and then click **Edit Package**. On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open. Click **Edit**.
~~~

3. <span data-ttu-id="0d2f8-116">在 app-v 5.1 Sequencer 主機中，若要儲存範本檔案，**請按一下 [** 檔案  /  **另存為範本**]。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-116">In the App-V 5.1 Sequencer console, to save the template file, click **File** / **Save As Template**.</span></span> <span data-ttu-id="0d2f8-117">在您檢查將與新範本一起儲存的設定後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-117">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="0d2f8-118">指定將與新的 App-v 5.1 專案範本相關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-118">Specify a name that will be associated with the new App-V 5.1 project template.</span></span> <span data-ttu-id="0d2f8-119">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-119">Click Save.</span></span>

   <span data-ttu-id="0d2f8-120">新的 App-v 5.1 專案範本會儲存在此程式步驟3中所指定的目錄中。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-120">The new App-V 5.1 project template is saved in the directory specified in step 3 of this procedure.</span></span>

**<span data-ttu-id="0d2f8-121">若要套用專案範本</span><span class="sxs-lookup"><span data-stu-id="0d2f8-121">To apply a project template</span></span>**

1.  **<span data-ttu-id="0d2f8-122">重要</span><span class="sxs-lookup"><span data-stu-id="0d2f8-122">Important</span></span>**  
    <span data-ttu-id="0d2f8-123">不支援使用專案範本與套件加速器結合建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-123">Creating a virtual application package using a project template in conjunction with a Package Accelerator is not supported.</span></span>



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="0d2f8-124">若要使用 app-v 5.1 專案範本來建立或升級新的虛擬應用程式套件，**請按一下 [**  /  **從範本新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-124">To create or upgrade a new virtual application package by using an App-V 5.1 project template, click **File** / **New From Template**.</span></span>

3. <span data-ttu-id="0d2f8-125">若要選取您要使用的專案範本，請流覽至儲存專案範本的目錄，選取專案範本，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-125">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

   <span data-ttu-id="0d2f8-126">建立新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-126">Create the new virtual application package.</span></span> <span data-ttu-id="0d2f8-127">儲存在指定範本的設定將會套用至您要建立的新虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-127">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span>

   <span data-ttu-id="0d2f8-128">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="0d2f8-128">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0d2f8-129">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-129">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0d2f8-130">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="0d2f8-130">Got an App-V issue?</span></span>** <span data-ttu-id="0d2f8-131">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="0d2f8-131">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0d2f8-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="0d2f8-132">Related topics</span></span>


[<span data-ttu-id="0d2f8-133">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="0d2f8-133">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









