---
title: 管理 MED-V 工作區的軟體更新
description: 管理 MED-V 工作區的軟體更新
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810779"
---
# <span data-ttu-id="e5a5e-103">管理 MED-V 工作區的軟體更新</span><span class="sxs-lookup"><span data-stu-id="e5a5e-103">Managing Software Updates for MED-V Workspaces</span></span>


<span data-ttu-id="e5a5e-104">您有幾種不同的選項可供您在已部署的 MED-V 工作區中提供應用程式的軟體更新。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-104">You have several different options available to you for providing software updates for the applications in the deployed MED-V workspace.</span></span>

<span data-ttu-id="e5a5e-105">**記事** 如需如何指定配置設定以定義 MED-V 如何接收自動更新的相關資訊，請參閱[管理 Med-v 工作區的自動更新](managing-automatic-updates-for-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-105">**Note** For information about how to specify the configuration settings that define how MED-V receives automatic updates, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

 

**<span data-ttu-id="e5a5e-106">更新 MED-V 工作區中的軟體</span><span class="sxs-lookup"><span data-stu-id="e5a5e-106">Updating Software in a MED-V Workspace</span></span>**

1.  **<span data-ttu-id="e5a5e-107">使用電子軟體發佈系統</span><span class="sxs-lookup"><span data-stu-id="e5a5e-107">Using an Electronic Software Distribution System</span></span>**

    <span data-ttu-id="e5a5e-108">如果您的組織使用電子軟體發佈系統（ESD）系統來部署軟體，您就可以使用它來提供在 MED-V 工作區上應用程式的軟體更新，就像您在物理電腦上提供應用程式的更新一樣。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-108">If your organization uses an Electronic Software Distribution System (ESD) system to deploy software, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

2.  **<span data-ttu-id="e5a5e-109">使用群組原則</span><span class="sxs-lookup"><span data-stu-id="e5a5e-109">Using Group Policy</span></span>**

    <span data-ttu-id="e5a5e-110">如果您的組織使用 [群組原則] 部署軟體，您就可以使用它來提供 MED-V 工作區上應用程式的軟體更新，就像您在物理電腦上提供應用程式的更新一樣。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-110">If your organization deploys software by using Group Policy, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

3.  **<span data-ttu-id="e5a5e-111">使用應用程式虛擬化（APP-V）</span><span class="sxs-lookup"><span data-stu-id="e5a5e-111">Using Application Virtualization (APP-V)</span></span>**

    <span data-ttu-id="e5a5e-112">如果您使用 MED-V 搭配 App-v，您可以在 MED-V 工作區中提供應用程式的軟體更新，方法是執行更新軟體所需的 app-v 工作區中的相關步驟。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-112">If you use MED-V together with App-V, you can provide software updates to applications in the MED-V workspace by following the steps that are required by App-V for updating software.</span></span> <span data-ttu-id="e5a5e-113">如需詳細資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-113">For more information, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

4.  **<span data-ttu-id="e5a5e-114">更新核心影像中的軟體</span><span class="sxs-lookup"><span data-stu-id="e5a5e-114">Updating Software in the Core Image</span></span>**

    <span data-ttu-id="e5a5e-115">雖然不會被視為 MED-V 最佳做法，但您可以將軟體更新安裝至核心影像上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-115">Although not considered a MED-V best practice, you can install software updates to applications on the core image.</span></span> <span data-ttu-id="e5a5e-116">安裝更新之後，您就可以將 MED-V 工作區重新部署到您的企業，就像當初部署它一樣。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-116">After you have installed the updates, you can then redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

    <span data-ttu-id="e5a5e-117">**重要** 我們不建議這個管理軟體更新的方法。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-117">**Important** We do not recommend this method of managing software updates.</span></span> <span data-ttu-id="e5a5e-118">此外，如果您更新核心影像中的軟體，並重新部署 MED-V 工作區到您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器中的任何資料都會遺失。</span><span class="sxs-lookup"><span data-stu-id="e5a5e-118">In addition, if you update software in the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="e5a5e-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5a5e-119">Related topics</span></span>


[<span data-ttu-id="e5a5e-120">管理 MED-V 工作區的自動更新</span><span class="sxs-lookup"><span data-stu-id="e5a5e-120">Managing Automatic Updates for MED-V Workspaces</span></span>](managing-automatic-updates-for-med-v-workspaces.md)

[<span data-ttu-id="e5a5e-121">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="e5a5e-121">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="e5a5e-122">如何發佈與取消發佈 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="e5a5e-122">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





