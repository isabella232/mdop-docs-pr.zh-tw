---
title: 關於應用程式授權
description: 關於應用程式授權
author: dansimp
ms.assetid: 6b487641-1627-4e91-b829-04f001008176
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546bc630b95fe52f960c7bdfb771d3e2561f9318
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802481"
---
# <span data-ttu-id="b2426-103">關於應用程式授權</span><span class="sxs-lookup"><span data-stu-id="b2426-103">About Application Licensing</span></span>


<span data-ttu-id="b2426-104">您可以直接從應用程式虛擬化伺服器管理主控台管理應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="b2426-104">You can manage application licenses directly from the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="b2426-105">授權類型</span><span class="sxs-lookup"><span data-stu-id="b2426-105">License Types</span></span>


<span data-ttu-id="b2426-106">系統中心應用程式虛擬化系統目前支援下列授權類型：</span><span class="sxs-lookup"><span data-stu-id="b2426-106">The System Center Application Virtualization System currently supports the following license types:</span></span>

-   <span data-ttu-id="b2426-107">[**無限制的授權**]：允許任意數量的並行使用者存取應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2426-107">**Unlimited License**—Allows access to the application by any number of simultaneous users.</span></span> <span data-ttu-id="b2426-108">當您想要將企業範圍的授權與應用程式建立關聯時，此授權方法相當適合。</span><span class="sxs-lookup"><span data-stu-id="b2426-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="b2426-109">**併發授權**-可讓您定義允許使用應用程式的併發使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="b2426-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="b2426-110">[**署名授權**]：可讓您指派授權給個別使用者。</span><span class="sxs-lookup"><span data-stu-id="b2426-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="b2426-111">已命名的授權可以用來確保特定的使用者永遠能夠執行該應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2426-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="b2426-112">您可以將併發與命名的授權合併至同一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2426-112">You can combine concurrent and named licenses for the same application.</span></span>

<span data-ttu-id="b2426-113">授權預設為停用，但您可以從 [**提供者屬性**] 對話方塊的 [**提供者管道**] 索引標籤啟用它。</span><span class="sxs-lookup"><span data-stu-id="b2426-113">Licensing is disabled by default, but you can enable it from the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span> <span data-ttu-id="b2426-114">如需啟用和停用授權的詳細資料，請參閱[如何設定或停用應用程式授權](how-to-set-up-or-disable-application-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="b2426-114">For details about enabling and disabling licensing, see [How to Set Up or Disable Application Licensing](how-to-set-up-or-disable-application-licensing.md).</span></span>

## <span data-ttu-id="b2426-115">提供者原則</span><span class="sxs-lookup"><span data-stu-id="b2426-115">Provider Policies</span></span>


<span data-ttu-id="b2426-116">已針對應用程式服務提供者（ASP）模型開發提供者原則。</span><span class="sxs-lookup"><span data-stu-id="b2426-116">Provider policies were developed for the Application Service Provider (ASP) model.</span></span> <span data-ttu-id="b2426-117">在這個模型中，單一的 ASP 可以為多個用戶端託管單一應用程式虛擬化系統，而每個用戶端都需要保持隔離。</span><span class="sxs-lookup"><span data-stu-id="b2426-117">In this model, a single ASP can host a single Application Virtualization System for multiple clients, where each client needs to remain isolated.</span></span> <span data-ttu-id="b2426-118">用戶端可能會有極大的需求，例如，一個用戶端可能需要驗證，而另一個無法進行驗證。</span><span class="sxs-lookup"><span data-stu-id="b2426-118">Clients might have dramatically different requirements—for example, one client might require authentication while another does not.</span></span> <span data-ttu-id="b2426-119">您可以使用提供者原則，將許可權與用戶端產生關聯，以便只有已核准的使用者才能存取每個虛擬應用程式或虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="b2426-119">You can use provider policies to associate permissions with clients so that only the approved users can access each virtual application or virtual application package.</span></span>

<span data-ttu-id="b2426-120">針對企業客戶，您可以在一或多個應用程式有嚴格的授權需求時，使用這個功能。</span><span class="sxs-lookup"><span data-stu-id="b2426-120">For the enterprise customer, you can use this feature when you have strict licensing requirements for one or more applications.</span></span> <span data-ttu-id="b2426-121">在這種情況下，[**提供者屬性**] 對話方塊的 [**提供者管道**] 索引標籤上已停用授權元件。</span><span class="sxs-lookup"><span data-stu-id="b2426-121">Under this situation, the licensing component is disabled on the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span>

<span data-ttu-id="b2426-122">[**提供者管線**] 索引標籤也有可啟用驗證、授權（**強制存取許可權設定**）和測光（**記錄使用方式資訊**）的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b2426-122">The **Provider Pipeline** tab also has check boxes to enable authentication, authorization (**Enforce Access Permission Settings**), and metering (**Log Usage Information**).</span></span> <span data-ttu-id="b2426-123">如果您的設定有特殊需求，您可以透過按一下 [**高級**] 按鈕，撰寫您自己的管線元件，並將它們新增到系統中。</span><span class="sxs-lookup"><span data-stu-id="b2426-123">If your configuration has special requirements, you can write your own pipeline components and add them to the system by clicking the **Advanced** button.</span></span>

## <span data-ttu-id="b2426-124">帳戶頒發機構</span><span class="sxs-lookup"><span data-stu-id="b2426-124">Account Authorities</span></span>


<span data-ttu-id="b2426-125">[帳戶頒發機構] 是安裝應用程式虛擬化伺服器的網域。</span><span class="sxs-lookup"><span data-stu-id="b2426-125">The account authority is the domain in which the Application Virtualization Server is installed.</span></span> <span data-ttu-id="b2426-126">當您在伺服器安裝過程中進行時，系統會提示您提供功能變數名稱;系統會在已安裝電腦的網域上偵測並使用預設值。</span><span class="sxs-lookup"><span data-stu-id="b2426-126">As you proceed through the server installation, you are prompted to supply a domain name; the domain in which the computer is installed is detected and used by default.</span></span> <span data-ttu-id="b2426-127">當使用者嘗試登入系統時，系統會提示他們輸入認證，然後才能存取該網域。</span><span class="sxs-lookup"><span data-stu-id="b2426-127">When users attempt to log in to the system, they are prompted for their credentials before they can access that domain.</span></span>

<span data-ttu-id="b2426-128">應用程式虛擬化系統支援多個網域。</span><span class="sxs-lookup"><span data-stu-id="b2426-128">The Application Virtualization System supports multiple domains.</span></span> <span data-ttu-id="b2426-129">如果信任關係是在網域之間建立，您可以將應用程式存取權授予其他網域中的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b2426-129">You can grant application access to user groups in other domains if a trust relationship is established between domains.</span></span> <span data-ttu-id="b2426-130">使用者必須提供每個網域可識別的認證。</span><span class="sxs-lookup"><span data-stu-id="b2426-130">Users must supply credentials that are recognized by each domain.</span></span>

<span data-ttu-id="b2426-131">在應用程式虛擬化伺服器管理主控台中，您可以變更主要網域（帳戶頒發機構），以及用來存取它的認證。</span><span class="sxs-lookup"><span data-stu-id="b2426-131">In the Application Virtualization Server Management Console, you can change the primary domain (account authority) and the credentials that are used to access it.</span></span>

## <span data-ttu-id="b2426-132">驗證</span><span class="sxs-lookup"><span data-stu-id="b2426-132">Authentication</span></span>


<span data-ttu-id="b2426-133">驗證是用來確認使用者身分識別的機制。</span><span class="sxs-lookup"><span data-stu-id="b2426-133">Authentication is the mechanism used to confirm a user's identity.</span></span> <span data-ttu-id="b2426-134">任何擁有可識別的使用者名稱和密碼的使用者都可以存取。</span><span class="sxs-lookup"><span data-stu-id="b2426-134">Any user with a recognized user name and password has access.</span></span>

<span data-ttu-id="b2426-135">在應用程式虛擬化系統中，您可以透過 [**提供者管線**] 索引標籤上的核取方塊來啟用或停用驗證。根據預設，會啟用 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="b2426-135">In the Application Virtualization System, you can enable or disable authentication through a check box on the **Provider Pipeline** tab. By default, Windows Authentication is enabled.</span></span>

## <span data-ttu-id="b2426-136">授權</span><span class="sxs-lookup"><span data-stu-id="b2426-136">Authorization</span></span>


<span data-ttu-id="b2426-137">[授權] 是用來確認使用者身分識別的程式。</span><span class="sxs-lookup"><span data-stu-id="b2426-137">Authorization is the process used to confirm a user’s identity.</span></span> <span data-ttu-id="b2426-138">確認使用者的身分識別之後，系統會判斷使用者是否已獲權存取系統，以及使用者被授與哪些應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="b2426-138">After confirming the user's identity, the system determines whether the user was granted access to the system and to which applications the user was granted access.</span></span> <span data-ttu-id="b2426-139">應用程式虛擬化伺服器管理主控台在 [**提供者管線**] 索引標籤上有 [**強制執行存取許可權設定**] 核取方塊，以啟用或停用授權。</span><span class="sxs-lookup"><span data-stu-id="b2426-139">The Application Virtualization Server Management Console has an **Enforce Access Permission Settings** check box on the **Provider Pipeline** tab to enable or disable authorization.</span></span>

<span data-ttu-id="b2426-140">在應用程式虛擬化系統中，只能將存取權授予使用者群組，不適用於個別使用者。</span><span class="sxs-lookup"><span data-stu-id="b2426-140">In the Application Virtualization System, access is granted to a user group only, not to individual users.</span></span>

## <span data-ttu-id="b2426-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2426-141">Related topics</span></span>


[<span data-ttu-id="b2426-142">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="b2426-142">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="b2426-143">如何設定或停用應用程式授權</span><span class="sxs-lookup"><span data-stu-id="b2426-143">How to Set Up or Disable Application Licensing</span></span>](how-to-set-up-or-disable-application-licensing.md)

[<span data-ttu-id="b2426-144">伺服器管理主控台：提供者原則節點</span><span class="sxs-lookup"><span data-stu-id="b2426-144">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





