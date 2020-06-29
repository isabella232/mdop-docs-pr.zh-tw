---
title: 如何套用 App-V 專案範本 (App-V 4.6 SP1)
description: 如何套用 App-V 專案範本 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 8ef120ab-8cfb-438c-8136-671167b7bd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b5f04f3f31838bfb13c19eee5f2314c3a3d291f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808715"
---
# <span data-ttu-id="2c18f-103">如何套用 App-V 專案範本 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="2c18f-103">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="2c18f-104">您可以使用 App-v 專案範本，將與現有虛擬應用程式套件相關聯的一般設定套用至新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2c18f-104">You can use an App-V project template to apply common settings associated with an existing virtual application package to a new virtual application package.</span></span> <span data-ttu-id="2c18f-105">使用 App-v 專案範本，您可以在開始排序應用程式之前，先設定一般設定，以協助簡化建立虛擬應用程式套件的程式。</span><span class="sxs-lookup"><span data-stu-id="2c18f-105">Using App-V project templates can help streamline the process of creating virtual application packages by configuring common settings before you begin sequencing an application.</span></span>

<span data-ttu-id="2c18f-106">**記事** 您可以在建立新的虛擬應用程式套件時，套用 V 專案範本。</span><span class="sxs-lookup"><span data-stu-id="2c18f-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="2c18f-107">不支援將專案範本套用至現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2c18f-107">Applying project templates to existing virtual application packages is not supported.</span></span> <span data-ttu-id="2c18f-108">此外，您無法將專案範本與套件加速器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2c18f-108">Additionally, you cannot use a project template in conjunction with a Package Accelerator.</span></span>

 

<span data-ttu-id="2c18f-109">如需有關建立 App-v 專案範本的詳細資訊，請參閱[如何建立 App-v 專案範本（app-v 4.6 SP1）](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="2c18f-109">For more information about creating App-V project templates, see [How to Create an App-V Project Template (App-V 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="2c18f-110">套用 app-v 專案範本</span><span class="sxs-lookup"><span data-stu-id="2c18f-110">To apply an App-V project template</span></span>**

1.  <span data-ttu-id="2c18f-111">若要啟動 Microsoft application Virtualization 排序器，請在安裝 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="2c18f-111">To start the Microsoft Application Virtualization Sequencer, on the computer on which App-V Sequencer is installed, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="2c18f-112">若要使用 app-v 專案範本來建立新的虛擬應用程式套件，**請按一下 [**  /  **從範本新增**檔案]。</span><span class="sxs-lookup"><span data-stu-id="2c18f-112">To create a new virtual application package by using an App-V project template, click **File** / **New From Template**.</span></span>

3.  <span data-ttu-id="2c18f-113">若要選取您要使用的專案範本，請流覽至儲存專案範本的目錄，選取專案範本，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2c18f-113">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

4.  <span data-ttu-id="2c18f-114">建立新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2c18f-114">Create the new virtual application package.</span></span> <span data-ttu-id="2c18f-115">儲存在指定範本的設定將會套用至您要建立的新虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2c18f-115">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span> <span data-ttu-id="2c18f-116">如需建立新的虛擬應用程式套件的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)，然後選取適當的程式。</span><span class="sxs-lookup"><span data-stu-id="2c18f-116">For more information about creating a new virtual application package, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md), and select the appropriate procedure.</span></span>

## <span data-ttu-id="2c18f-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="2c18f-117">Related topics</span></span>


[<span data-ttu-id="2c18f-118">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="2c18f-118">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="2c18f-119">如何建立 App-V 專案範本 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="2c18f-119">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)

 

 





