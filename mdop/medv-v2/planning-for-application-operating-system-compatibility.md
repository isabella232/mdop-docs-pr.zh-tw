---
title: 規劃應用程式作業系統相容性
description: 規劃應用程式作業系統相容性
author: dansimp
ms.assetid: cdb0a7f0-9da4-4562-8277-12972eb0fea8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b10da2c870e5ddc32098136225515cdd0523809
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811174"
---
# <span data-ttu-id="5dccf-103">規劃應用程式作業系統相容性</span><span class="sxs-lookup"><span data-stu-id="5dccf-103">Planning for Application Operating System Compatibility</span></span>


<span data-ttu-id="5dccf-104">本主題可協助您判斷如何解決應用程式作業系統相容性問題，並討論 Microsoft 企業版桌面虛擬化（MED-V）2.0 作為貴組織的解決方案的運作方式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-104">This topic helps determine how to resolve application operating system compatibility issues, and discusses how Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 works as a solution for your organization.</span></span>

<span data-ttu-id="5dccf-105">本主題討論 MED-V 的商業需求，並將 MED-V 與 Windows XP 模式及 Microsoft Application Virtualization （App-v）進行比較：</span><span class="sxs-lookup"><span data-stu-id="5dccf-105">This topic discusses the business requirements for MED-V and compares MED-V to Windows XP Mode and Microsoft Application Virtualization (App-V):</span></span>

-   [<span data-ttu-id="5dccf-106">MED-V 的業務需求</span><span class="sxs-lookup"><span data-stu-id="5dccf-106">Business Requirements for MED-V</span></span>](#bkmk-whenmedv)

-   [<span data-ttu-id="5dccf-107">MED-V 與 Windows XP 模式的優點</span><span class="sxs-lookup"><span data-stu-id="5dccf-107">Benefits of MED-V versus Windows XP Mode</span></span>](#bkmk-medvvsxp)

-   [<span data-ttu-id="5dccf-108">MED-V 與 app-v 的優點</span><span class="sxs-lookup"><span data-stu-id="5dccf-108">Benefits of MED-V versus App-V</span></span>](#bkmk-medvvsappv)

## <a href="" id="bkmk-whenmedv"></a><span data-ttu-id="5dccf-109">MED-V 的業務需求</span><span class="sxs-lookup"><span data-stu-id="5dccf-109">Business Requirements for MED-V</span></span>


<span data-ttu-id="5dccf-110">當貴公司的 IT 部門決定是否要升級至 Windows 7 時，必須注意其行業應用程式和 web 的商務線應用程式，以確保這些功能可以在新作業系統上執行。</span><span class="sxs-lookup"><span data-stu-id="5dccf-110">When your company’s IT department is determining whether to upgrade to Windows 7, it must pay attention to its line-of-business applications and web-based line-of-business applications to make certain that these can run on the new operating system.</span></span> <span data-ttu-id="5dccf-111">通常，這些應用程式和 Url 是透過舊版 Windows 或 Internet Explorer 建立的，在新的作業系統中嘗試使用它們時，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="5dccf-111">Often, these applications and URLs were created to work specifically with an older version of Windows or Internet Explorer, and problems can occur when trying to use them in the new operating system.</span></span> <span data-ttu-id="5dccf-112">Microsoft 提供多種不同的方法來處理升級時可能發生的各種相容性問題，例如應用程式相容性工具箱（ACT）和 Windows 7 程式相容性小幫手。</span><span class="sxs-lookup"><span data-stu-id="5dccf-112">Microsoft offers many different methods for handling the various compatibility issues that can occur when you upgrade, such as the Application Compatibility Toolkit (ACT) and the Windows 7 Program Compatibility Assistant.</span></span> <span data-ttu-id="5dccf-113">但即使已針對相容性測試所有應用程式且已確定，某些應用程式仍無法在 Windows 7 上正常運作，或因成本太高而無法解決。</span><span class="sxs-lookup"><span data-stu-id="5dccf-113">But even after all applications have been tested for compatibility and fixes have been determined, some applications still do not work correctly on Windows 7 or are too costly to resolve.</span></span>

<span data-ttu-id="5dccf-114">使用 MED-V，您可以透過執行 Windows XP 的 Windows 虛擬電腦環境來執行這些繼承應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-114">By using MED-V, you can run these legacy applications through a Windows Virtual PC environment that is running Windows XP.</span></span> <span data-ttu-id="5dccf-115">因為您不需要在升級之前在新作業系統上測試和驗證這些問題應用程式，所以您的遷移至 Windows 7 會更順利且更快速。</span><span class="sxs-lookup"><span data-stu-id="5dccf-115">Because you no longer have to test and validate these problem applications on the new operating system before upgrading, your migration to Windows 7 is much smoother and quicker.</span></span>

### <span data-ttu-id="5dccf-116">使用 MED-V 檢查清單</span><span class="sxs-lookup"><span data-stu-id="5dccf-116">Using MED-V Checklist</span></span>

<span data-ttu-id="5dccf-117">如果下列任何一種情況適用于您，請考慮使用 MED-V：</span><span class="sxs-lookup"><span data-stu-id="5dccf-117">Consider MED-V if any of the following scenarios apply to you:</span></span>

-   <span data-ttu-id="5dccf-118">您是大型組織（例如，500的使用者等等）、與 Microsoft 有企業協定，以及規劃升級至 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="5dccf-118">You are a large organization (for example, 500 users and more), have an Enterprise Agreement with Microsoft, and plan to upgrade to Windows 7.</span></span>

-   <span data-ttu-id="5dccf-119">您已測試您的商務用行應用程式，但發現與 Windows 7 不相容的專案。</span><span class="sxs-lookup"><span data-stu-id="5dccf-119">You have tested your line-of-business applications and have found some that are incompatible with Windows 7.</span></span>

-   <span data-ttu-id="5dccf-120">您已透過升級應用程式或使用 Microsoft 提供的墊片（例如應用程式相容性工具箱（ACT）），解決了這些問題應用程式的相容性問題，但某些應用程式的相容性問題仍會保留。</span><span class="sxs-lookup"><span data-stu-id="5dccf-120">You have resolved the compatibility issues for some of these problem applications by upgrading the application or by using a Microsoft-provided shim, such as the Application Compatibility Toolkit (ACT), but compatibility issues remain for some applications.</span></span>

-   <span data-ttu-id="5dccf-121">您已考慮使用 App-v 作為傳遞不相容的應用程式的選項，並在您實現 App-v 之後結束，您仍有必須解決的應用程式作業系統相容性問題。</span><span class="sxs-lookup"><span data-stu-id="5dccf-121">You have considered App-V as an option for delivering the incompatible applications and have concluded that even after you implement App-V, you still have application operating system compatibility issues that you must address.</span></span>

-   <span data-ttu-id="5dccf-122">您已將 Windows XP 模式視為方案，並已確定它不是有效的選項，因為：</span><span class="sxs-lookup"><span data-stu-id="5dccf-122">You have considered Windows XP Mode as a solution and have determined that it is not an efficient option because:</span></span>

    -   <span data-ttu-id="5dccf-123">您想要同時將包含問題應用程式的虛擬影像部署到所有的使用者，而不是個別的方式，並讓虛擬影像自動加入至網域。</span><span class="sxs-lookup"><span data-stu-id="5dccf-123">You want to be able to deploy virtual images that contain the problem applications to all end users at the same time, instead of individually, and have the virtual images automatically joined to the domain.</span></span>

    -   <span data-ttu-id="5dccf-124">您已決定管理這些繼承應用程式（實際提供）並從集中位置（而不是每個使用者的桌面）控制 Windows 虛擬電腦設定。</span><span class="sxs-lookup"><span data-stu-id="5dccf-124">You have decided it is much more cost effective to manage these legacy applications (that are delivered virtually) and control the Windows Virtual PC settings from a centralized location instead of on each end user’s desktop.</span></span>

    -   <span data-ttu-id="5dccf-125">您想要能夠以比例（而不是每個桌面）來更新和支援虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="5dccf-125">You want to be able to update and support the virtual machines in scale instead of per desktop.</span></span>

    -   <span data-ttu-id="5dccf-126">您想要重新導向較舊版本 Internet Explorer 的 Url 在虛擬機器上的執行方式，並在稍後輕鬆管理 URL 重新導向。</span><span class="sxs-lookup"><span data-stu-id="5dccf-126">You want the ability to redirect URLs that run better on an older version of Internet Explorer to the virtual machines and to easily manage URL redirection later.</span></span>

-   <span data-ttu-id="5dccf-127">您已認為，您可以儘快升級至 Windows 7，且決定要推遲解決您剩餘的應用程式相容性問題，直到您在 MED-V 中找到可用的解決方案為止。</span><span class="sxs-lookup"><span data-stu-id="5dccf-127">You have determined that it would be more cost effective and helpful to upgrade to Windows 7 as soon as possible and have decided to postpone resolving your remaining application compatibility issues until a later date, knowing that you have a solution available in MED-V.</span></span>

## <a href="" id="bkmk-medvvsxp"></a> <span data-ttu-id="5dccf-128">MED-V 與 Windows XP 模式的優點</span><span class="sxs-lookup"><span data-stu-id="5dccf-128">Benefits of MED-V versus Windows XP Mode</span></span>


<span data-ttu-id="5dccf-129">Windows 7 版 windows 版電腦可讓您同時在單一裝置上執行不同版本的作業系統，且包含在 Windows 7 專業版及更新版本中。</span><span class="sxs-lookup"><span data-stu-id="5dccf-129">Windows Virtual PC for Windows 7 lets you run different versions of an operating system at the same time on a single device and is included in Windows 7 Professional Edition and higher.</span></span>

<span data-ttu-id="5dccf-130">Windows XP 模式功能提供預先配置的 Windows XP 映射，讓您可以建立虛擬 Windows XP 環境，以利用 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="5dccf-130">Windows XP Mode functionality takes advantage of Windows Virtual PC by providing a preconfigured Windows XP image that lets you create a virtual Windows XP environment.</span></span> <span data-ttu-id="5dccf-131">在這個虛擬環境中，您可以手動安裝與 Windows 7 不相容且無法透過 Windows 虛擬電腦順暢執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-131">In this virtual environment, you can manually install applications that are incompatible with Windows 7 and that run seamlessly from your desktop through Windows Virtual PC.</span></span>

**<span data-ttu-id="5dccf-132">使用 Windows XP 模式，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5dccf-132">By using Windows XP Mode, you can do the following:</span></span>**

-   <span data-ttu-id="5dccf-133">在執行 Windows Virtual 電腦的虛擬機器內，執行與 Windows XP 相容的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-133">Run applications that are compatible with Windows XP inside a virtual machine that runs in Windows Virtual PC.</span></span>

-   <span data-ttu-id="5dccf-134">將這些應用程式發佈到主機的桌面或程式功能表。</span><span class="sxs-lookup"><span data-stu-id="5dccf-134">Publish these applications to the host’s desktop or Program menu.</span></span>

<span data-ttu-id="5dccf-135">如果您想要將這些虛擬機器以大型規模的方式提供給 Windows 7，您必須能夠快速部署虛擬機器、提供及自訂它們、控制其設定並輕鬆支援。</span><span class="sxs-lookup"><span data-stu-id="5dccf-135">When you want to deliver these virtual machines on a large scale as part of an enterprise migration to Windows 7, you must be able to deploy the virtual machines quickly, provision, and customize them efficiently, control their settings, and support them easily.</span></span>

<span data-ttu-id="5dccf-136">MED-V 建立在 Windows XP 模式上，以提供企業範圍的應用程式相容性。</span><span class="sxs-lookup"><span data-stu-id="5dccf-136">MED-V builds upon Windows XP Mode to deliver enterprise-wide application compatibility.</span></span> <span data-ttu-id="5dccf-137">雖然 Windows XP 模式僅限為個人和小型企業提供虛擬的應用程式功能，但 MED-V 可讓您在公司網路中的預先設定的 Windows XP 映射大規模部署。</span><span class="sxs-lookup"><span data-stu-id="5dccf-137">Whereas Windows XP mode is limited to providing virtual application functionality to individuals and small businesses, MED-V allows for large-scale deployments of preconfigured Windows XP images throughout your corporate network.</span></span> <span data-ttu-id="5dccf-138">它為您提供企業版的管理解決方案，以供您設定、部署及維護這些虛擬 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="5dccf-138">It gives you an enterprise-ready management solution for the configuration, deployment, and maintenance of these virtual MED-V workspaces.</span></span> <span data-ttu-id="5dccf-139">MED-V 也提供 enterpriseadministrators 用來控制影像使用的一組原則。</span><span class="sxs-lookup"><span data-stu-id="5dccf-139">MED-V also gives enterpriseadministrators a set of policies to control image use.</span></span> <span data-ttu-id="5dccf-140">這包括哪些使用者將能夠存取這些影像中的哪些特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-140">This includes which users will have access to which specific applications within these images.</span></span>

**<span data-ttu-id="5dccf-141">使用 MED-V，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5dccf-141">By using MED-V, you can do the following:</span></span>**

-   <span data-ttu-id="5dccf-142">升級到您的新作業系統，而不需要測試並解決每個不相容的應用程式和 URL。</span><span class="sxs-lookup"><span data-stu-id="5dccf-142">Upgrade to your new operating system without having to test and resolve every incompatible application and URL.</span></span>

-   <span data-ttu-id="5dccf-143">部署自動以網域連接並針對每個使用者進行自訂的虛擬 Windows XP 影像。</span><span class="sxs-lookup"><span data-stu-id="5dccf-143">Deploy virtual Windows XP images that are automatically domain-joined and customized per user.</span></span>

-   <span data-ttu-id="5dccf-144">將應用程式和 URL 重新導向資訊提供給使用者。</span><span class="sxs-lookup"><span data-stu-id="5dccf-144">Provision applications and URL redirection information to users.</span></span>

-   <span data-ttu-id="5dccf-145">控制 Windows 虛擬電腦設定。</span><span class="sxs-lookup"><span data-stu-id="5dccf-145">Control the Windows Virtual PC settings.</span></span>

-   <span data-ttu-id="5dccf-146">透過監視和疑難排解來維護和支援端點。</span><span class="sxs-lookup"><span data-stu-id="5dccf-146">Maintain and support endpoints through monitoring and troubleshooting.</span></span>

-   <span data-ttu-id="5dccf-147">確定來賓電腦已修補，即使是處於暫停狀態也一樣。</span><span class="sxs-lookup"><span data-stu-id="5dccf-147">Ensure that guest computers are patched, even if in a suspended state.</span></span>

-   <span data-ttu-id="5dccf-148">自動化每個使用者的虛擬機器建立與 sysprep 初始化。</span><span class="sxs-lookup"><span data-stu-id="5dccf-148">Automate per-user virtual machine creation and sysprep initialization.</span></span>

-   <span data-ttu-id="5dccf-149">輕鬆診斷主機和來賓電腦上的問題。</span><span class="sxs-lookup"><span data-stu-id="5dccf-149">Easily diagnose issues on the host and guest computers.</span></span>

-   <span data-ttu-id="5dccf-150">透過 Windows Virtual PC NAT 模式，無縫管理連線的來賓電腦。</span><span class="sxs-lookup"><span data-stu-id="5dccf-150">Seamlessly manage guest computers that are connected through Windows Virtual PC NAT mode.</span></span>

## <a href="" id="bkmk-medvvsappv"></a><span data-ttu-id="5dccf-151">MED-V 與 app-v 的優點</span><span class="sxs-lookup"><span data-stu-id="5dccf-151">Benefits of MED-V versus App-V</span></span>


<span data-ttu-id="5dccf-152">MED-V 和 App-v 是兩種非常不同的技術，可以輕鬆地共同解決您的應用程式作業系統相容性問題。</span><span class="sxs-lookup"><span data-stu-id="5dccf-152">MED-V and App-V are two very different technologies that can easily work together to solve your application operating system compatibility issues.</span></span> <span data-ttu-id="5dccf-153">使用 App-v，您可以為每個應用程式建立個人化的套件，每個應用程式都要與其他應用程式分開。</span><span class="sxs-lookup"><span data-stu-id="5dccf-153">By using App-V, you create an individualized package for each application, each of which is then kept separate from the others.</span></span> <span data-ttu-id="5dccf-154">然後，您就可以將每個虛擬應用程式立即傳送給使用者，這對於 Windows 7 部署策略非常有用。</span><span class="sxs-lookup"><span data-stu-id="5dccf-154">Each virtual application can then be immediately delivered to the end user, which is very useful for a Windows 7 deployment strategy.</span></span>

<span data-ttu-id="5dccf-155">MED-V 不會個別處理應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-155">MED-V does not handle applications individually.</span></span> <span data-ttu-id="5dccf-156">相反地，它會在執行 Windows 7 的同一台電腦上建立另一個 Windows XP 實例。</span><span class="sxs-lookup"><span data-stu-id="5dccf-156">Instead, it creates an additional instance of Windows XP on the same desktop that is running Windows 7.</span></span> <span data-ttu-id="5dccf-157">您可以視需要在這個虛擬影像中安裝任意多個應用程式，並像管理貴組織中的任何其他桌面一樣來管理影像。</span><span class="sxs-lookup"><span data-stu-id="5dccf-157">You can install as many applications as necessary into this virtual image and manage the image just as you would any other desktop in your organization.</span></span>

<span data-ttu-id="5dccf-158">此外，您也可以將 MED-V 搭配 App-v 搭配使用，以使用 MED-V 來安裝、發佈和管理依應用程式排序的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="5dccf-158">In addition, you can use MED-V together with App-V so that virtual applications that are sequenced through App-V are installed, published, and managed by using MED-V.</span></span>

## <span data-ttu-id="5dccf-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="5dccf-159">Related topics</span></span>


[<span data-ttu-id="5dccf-160">定義和規劃 MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="5dccf-160">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

 

 





