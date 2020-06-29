---
title: 選取封裝加速器頁面
description: 選取封裝加速器頁面
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800850"
---
# <span data-ttu-id="7f669-103">選取封裝加速器頁面</span><span class="sxs-lookup"><span data-stu-id="7f669-103">Select Package Accelerator Page</span></span>


<span data-ttu-id="7f669-104">使用 [**選取套件加速器**] 頁面來選取將用來建立新的虛擬應用程式套件的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7f669-104">Use the **Select Package Accelerator** page to select the Package Accelerator that will be used to create the new virtual application package.</span></span> <span data-ttu-id="7f669-105">您必須將套件加速器複製到執行 App-v 排序器的電腦上的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7f669-105">You must copy the Package Accelerator to a folder on the computer running the App-V Sequencer.</span></span> <span data-ttu-id="7f669-106">如需詳細資訊，請參閱[關於 app-v 封裝加速器（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="7f669-106">For more information, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="7f669-107">只能從您信任的發行者執行套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7f669-107">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="7f669-108">套件加速器通常包含數位簽章。</span><span class="sxs-lookup"><span data-stu-id="7f669-108">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="7f669-109">數位簽章是一種電子安全標記，可協助說明軟體的發行者，以及封裝轉換為最初簽署後是否已被篡改。</span><span class="sxs-lookup"><span data-stu-id="7f669-109">A digital signature is an electronic security mark that can help indicate the publisher of the software, and whether the package has been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="7f669-110">如果您使用的轉換是由發行商數位簽署的，且發行商已透過憑證授權單位驗證其身分識別，您就可以更有把握該轉換來自該特定的發行者，而且尚未變更。</span><span class="sxs-lookup"><span data-stu-id="7f669-110">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="7f669-111">如果下列任一條件成立，App-v 排序器會通知您：</span><span class="sxs-lookup"><span data-stu-id="7f669-111">The App-V Sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="7f669-112">選取的轉換尚未經過數位簽署。</span><span class="sxs-lookup"><span data-stu-id="7f669-112">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="7f669-113">所選的轉換是由尚未使用憑證授權單位驗證其身分識別的發行者所簽署。</span><span class="sxs-lookup"><span data-stu-id="7f669-113">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="7f669-114">所選取的轉換在經過數位簽署及放開後已變更。</span><span class="sxs-lookup"><span data-stu-id="7f669-114">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="7f669-115">如果您在使用套件加速器時顯示這些訊息中的任何一種，請造訪封裝加速器發行者的網站，以取得經過數位簽章的轉換版本。</span><span class="sxs-lookup"><span data-stu-id="7f669-115">If any of these messages are displayed when using a Package Accelerators, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

<span data-ttu-id="7f669-116">此頁面包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="7f669-116">This page contains the following elements:</span></span>

<a href="" id="browse"></a>**<span data-ttu-id="7f669-117">瀏覽</span><span class="sxs-lookup"><span data-stu-id="7f669-117">Browse</span></span>**  
<span data-ttu-id="7f669-118">按一下 **[流覽]** ，指定您將用來建立虛擬應用程式套件的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7f669-118">Click **Browse** to specify the Package Accelerator that you will use to create the virtual application package.</span></span> <span data-ttu-id="7f669-119">在執行排序器的電腦上，儲存您所指定的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7f669-119">Save the Package Accelerator you specified locally on the computer that is running the Sequencer.</span></span>

## <span data-ttu-id="7f669-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f669-120">Related topics</span></span>


[<span data-ttu-id="7f669-121">Sequencer 精靈 - 封裝加速器 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="7f669-121">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





