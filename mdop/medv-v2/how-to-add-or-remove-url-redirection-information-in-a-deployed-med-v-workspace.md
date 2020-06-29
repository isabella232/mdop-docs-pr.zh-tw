---
title: 如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊
description: 如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811757"
---
# <span data-ttu-id="04765-103">如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊</span><span class="sxs-lookup"><span data-stu-id="04765-103">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>


<span data-ttu-id="04765-104">若要在已部署的 MED-V 工作區中編輯 URL 重新導向資訊，建議您使用 [群組原則] 來更新系統註冊。</span><span class="sxs-lookup"><span data-stu-id="04765-104">To edit URL redirection information in a deployed MED-V workspace, we recommend that you update the system registry by using Group Policy.</span></span> <span data-ttu-id="04765-105">雖然我們不建議這樣做，但您也可以使用更新的 URL 重新導向資訊來重建並重新部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="04765-105">Although we do not recommend it, you can also rebuild and redeploy the MED-V workspace with the updated URL redirection information.</span></span>

<span data-ttu-id="04765-106">登錄機碼通常位於：</span><span class="sxs-lookup"><span data-stu-id="04765-106">The registry key is usually located at:</span></span>

<span data-ttu-id="04765-107">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="04765-107">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="04765-108">必須存在下列多字串值：</span><span class="sxs-lookup"><span data-stu-id="04765-108">The following multi-string value must be present:</span></span> `RedirectUrls`

<span data-ttu-id="04765-109">[值資料] `RedirectUrls` 是您在使用**Med-v 工作區包裝**程式建立 med-v 工作區套件時，為重新導向所指定的所有 url 清單。</span><span class="sxs-lookup"><span data-stu-id="04765-109">The value data for `RedirectUrls` is a list of all of the URLs that you specified for redirection when you built the MED-V workspace package by using the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="04765-110">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="04765-110">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="04765-111">您可以執行下列其中一項工作來新增和移除 URL 重新導向資訊：</span><span class="sxs-lookup"><span data-stu-id="04765-111">You can add and remove URL redirection information by performing one of the following tasks:</span></span>

-   [<span data-ttu-id="04765-112">編輯 URL 重新導向登錄機碼，並使用群組原則進行部署</span><span class="sxs-lookup"><span data-stu-id="04765-112">Edit the URL Redirection Registry Key and Deploy Using Group Policy</span></span>](#bkmk-editreg)

-   [<span data-ttu-id="04765-113">編輯 URL 重新導向文字檔並重建 MED-V-V 工作區</span><span class="sxs-lookup"><span data-stu-id="04765-113">Edit the URL Redirection Text File and Rebuild the MED-V Workspace</span></span>](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**<span data-ttu-id="04765-114">使用群組原則更新 URL 重新導向資訊</span><span class="sxs-lookup"><span data-stu-id="04765-114">To update URL Redirection information by using Group Policy</span></span>**

1.  <span data-ttu-id="04765-115">編輯名為的 [登錄金鑰多重字串] 值 `RedirectUrls` 。</span><span class="sxs-lookup"><span data-stu-id="04765-115">Edit the registry key multi-string value that is named `RedirectUrls`.</span></span> <span data-ttu-id="04765-116">此值通常位於：</span><span class="sxs-lookup"><span data-stu-id="04765-116">This value is typically located at:</span></span>

    <span data-ttu-id="04765-117">Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span><span class="sxs-lookup"><span data-stu-id="04765-117">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

    <span data-ttu-id="04765-118">如果您要新增 Url 至登錄機碼，請在您建立 MED-V 工作區套件時，每行輸入一個 Url。</span><span class="sxs-lookup"><span data-stu-id="04765-118">If you are adding URLs to the registry key, enter them one per line, as was required when you built the MED-V workspace package.</span></span> <span data-ttu-id="04765-119">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="04765-119">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

2.  <span data-ttu-id="04765-120">使用 [群組原則] 部署更新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="04765-120">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="04765-121">如需如何使用群組原則的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="04765-121">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

<span data-ttu-id="04765-122">**記事** 這個編輯 URL 重新導向資訊的方法是 MED-V 最佳做法。</span><span class="sxs-lookup"><span data-stu-id="04765-122">**Note** This method of editing URL redirection information is a MED-V best practice.</span></span>

 

<a href="" id="bkmk-edittext"></a>**<span data-ttu-id="04765-123">使用更新的 URL 文字檔重建 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="04765-123">To rebuild the MED-V workspace by using an updated URL text file</span></span>**

-   <span data-ttu-id="04765-124">從重新導向清單中新增及移除 Url 的另一種方法是更新 URL 重新導向文字檔，然後使用它來建立新的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="04765-124">Another method of adding and removing URLs from the redirection list is to update the URL redirection text file and then use it to build a new MED-V workspace.</span></span> <span data-ttu-id="04765-125">接著，您可以使用部署的標準程式（例如 ESD 系統），預先重新部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="04765-125">You can then redeploy the MED-V workspace as before, by using your standard process of deployment, such as an ESD system.</span></span>

    <span data-ttu-id="04765-126">**重要** 我們不建議您編輯 URL 重新導向資訊的方法。</span><span class="sxs-lookup"><span data-stu-id="04765-126">**Important** We do not recommend this method of editing URL redirection information.</span></span> <span data-ttu-id="04765-127">此外，您可以隨時將 MED-V 工作區重新部署到您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器中的任何資料都會遺失。</span><span class="sxs-lookup"><span data-stu-id="04765-127">In addition, any time that you redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="04765-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="04765-128">Related topics</span></span>


[<span data-ttu-id="04765-129">如何測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="04765-129">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="04765-130">管理部署到 MED-V 工作區的應用程式</span><span class="sxs-lookup"><span data-stu-id="04765-130">Managing Applications Deployed to MED-V Workspaces</span></span>](managing-applications-deployed-to-med-v-workspaces.md)

[<span data-ttu-id="04765-131">建立 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="04765-131">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

 

 





