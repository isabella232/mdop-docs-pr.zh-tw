---
title: 規劃排序器安全性
description: 規劃排序器安全性
author: dansimp
ms.assetid: 8043cb02-476d-4c28-a850-903a8ac5b2d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf1e85e24d93d373add38b5efe51ceb40faae24e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800914"
---
# <span data-ttu-id="d383b-103">規劃排序器安全性</span><span class="sxs-lookup"><span data-stu-id="d383b-103">Planning for Sequencer Security</span></span>


<span data-ttu-id="d383b-104">您可以在設定應用程式虛擬化（App-v）時儘早納入推薦的實施做法，讓您的排序器實現運作正常且更安全。</span><span class="sxs-lookup"><span data-stu-id="d383b-104">Incorporate recommended implementation practices as early as possible when configuring Application Virtualization (App-V) so that your Sequencer implementation is functional and more secure.</span></span> <span data-ttu-id="d383b-105">如果您已設定排序器，請使用下列最佳做法指導方針，以重新審視您的設計決策，並從安全形度分析它們。</span><span class="sxs-lookup"><span data-stu-id="d383b-105">If you have already configured the Sequencer, use the following best-practice guidelines to revisit your design decisions and analyze them from a security perspective.</span></span>

**<span data-ttu-id="d383b-106">重要</span><span class="sxs-lookup"><span data-stu-id="d383b-106">Important</span></span>**  
<span data-ttu-id="d383b-107">App-v 排序器會收集並部署執行排序器之電腦上錄製的所有應用程式資訊。</span><span class="sxs-lookup"><span data-stu-id="d383b-107">The App-V Sequencer collects and deploys all application information recorded on the computer running the sequencer.</span></span> <span data-ttu-id="d383b-108">您應該確保所有存取執行排序器的電腦的使用者都有管理認證。</span><span class="sxs-lookup"><span data-stu-id="d383b-108">You should ensure that all users accessing the computer running the Sequencer have administrative credentials.</span></span> <span data-ttu-id="d383b-109">擁有使用者帳號憑證的使用者，不應該有控制套件內容和套件檔案的存取權。</span><span class="sxs-lookup"><span data-stu-id="d383b-109">Users with user account credentials should not have access to control package contents and package files.</span></span> <span data-ttu-id="d383b-110">如果您是在執行遠端桌面服務（舊稱終端服務）的電腦上進行排序，請確認該電腦是專門進行排序的電腦，且在進行排序期間，擁有使用者帳號憑證的使用者並未連線至該電腦。</span><span class="sxs-lookup"><span data-stu-id="d383b-110">If you are sequencing on a computer running Remote Desktop Services (formerly Terminal Services), make sure it is a computer that is dedicated to sequencing and that users with user account credentials are not connected to it during sequencing.</span></span>



## <span data-ttu-id="d383b-111">排序器安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="d383b-111">Sequencer Security Best Practices</span></span>


<span data-ttu-id="d383b-112">在實施及使用 Application Virtualization （App-v） Sequencer 時，請考慮下列案例和相關的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="d383b-112">Consider the following scenarios and the associated best practices when implementing and using the Application Virtualization (App-V) Sequencer:</span></span>

-   <span data-ttu-id="d383b-113">**在執行排序器的電腦上進行病毒掃描**，建議您先掃描執行排序器的電腦以尋找病毒，然後在先後順序程式期間停用執行排序器的電腦上的所有防病毒及惡意程式碼檢測軟體。</span><span class="sxs-lookup"><span data-stu-id="d383b-113">**Virus scanning on the computer running the Sequencer**—It is recommended that you scan the computer running the Sequencer for viruses and then disable all antivirus and malware detection software on the computer running the Sequencer during the sequencing process.</span></span> <span data-ttu-id="d383b-114">這會加快排序程式，並防止防毒軟體元件與反惡意程式碼軟體元件干擾排序程式。</span><span class="sxs-lookup"><span data-stu-id="d383b-114">This will speed the sequencing process and prevent the antivirus and anti-malware software components from interfering with the sequencing process.</span></span> <span data-ttu-id="d383b-115">接著，在未執行排序器的電腦上安裝排序的套件，並在成功安裝之後，掃描該電腦是否有病毒。</span><span class="sxs-lookup"><span data-stu-id="d383b-115">Next install the sequenced package on a computer not running the Sequencer, and after successful installation, scan that computer for viruses.</span></span> <span data-ttu-id="d383b-116">如果發現病毒，請聯絡軟體的製造商，告知受感染的來源檔案，並在沒有病毒的情況下要求更新的安裝來源。</span><span class="sxs-lookup"><span data-stu-id="d383b-116">If viruses are found, the manufacturer of the software should be contacted to inform them of the infected source files and request an updated installation source without viruses.</span></span> <span data-ttu-id="d383b-117">或者，您也可以在安裝階段之後掃描 Sequencer，如果發現有病毒，請依照上述所述的方式聯繫軟體製造商。</span><span class="sxs-lookup"><span data-stu-id="d383b-117">Optionally, the Sequencer could be scanned after the installation phase and if a virus is found, the software manufacturer should be contacted as mentioned above.</span></span>

    **<span data-ttu-id="d383b-118">注意</span><span class="sxs-lookup"><span data-stu-id="d383b-118">Note</span></span>**  
    <span data-ttu-id="d383b-119">如果在應用程式中偵測到病毒，則不應將應用程式部署到目的電腦。</span><span class="sxs-lookup"><span data-stu-id="d383b-119">If a virus is detected in an application, the application should not be deployed to target computers.</span></span>



-   <span data-ttu-id="d383b-120">**在 NTFS 檔案上捕獲存取控制清單（acl）**： app-v 排序器會捕獲安裝產品期間監視之檔案的 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="d383b-120">**Capturing access control lists (ACLs) on NTFS files**—The App-V Sequencer captures NTFS file system permissions for the files that are monitored during the installation of the product.</span></span> <span data-ttu-id="d383b-121">這項功能可讓您更精確地複製應用程式的預期行為，就像它是在本機安裝且未虛擬化。</span><span class="sxs-lookup"><span data-stu-id="d383b-121">This capability allows you to more accurately replicate the intended behavior of the application, as if it were installed locally and not virtualized.</span></span> <span data-ttu-id="d383b-122">在某些情況下，應用程式可能會儲存使用者不想要在應用程式檔案中存取的資訊。</span><span class="sxs-lookup"><span data-stu-id="d383b-122">In some scenarios, an application might store information that users were not intended to access within the application files.</span></span> <span data-ttu-id="d383b-123">例如，應用程式可以在應用程式內的檔案中儲存身分認證資訊。</span><span class="sxs-lookup"><span data-stu-id="d383b-123">For example, an application could store credentials information in a file inside of the application.</span></span> <span data-ttu-id="d383b-124">如果不是在套件上強制執行 Acl，使用者可能會在應用程式之外查看並使用這項資訊。</span><span class="sxs-lookup"><span data-stu-id="d383b-124">If ACLs are not enforced on the package, a user could potentially view and then use this information outside of the application.</span></span>

    **<span data-ttu-id="d383b-125">注意</span><span class="sxs-lookup"><span data-stu-id="d383b-125">Note</span></span>**  
    <span data-ttu-id="d383b-126">您不應該將儲存未加密之安全特定資訊（例如密碼等）的應用程式序列化。</span><span class="sxs-lookup"><span data-stu-id="d383b-126">You should not sequence applications that store unencrypted security-specific information, such as passwords, and so on.</span></span>



~~~
During the installation phase, you can modify the default permissions of the files if necessary. After completion of the sequencing process, but before saving the package, you can choose whether to enforce security descriptors that were captured during the installation of the application. By default, App-V will enforce the security descriptors specified during the installation of the application. If you turn off security descriptor enforcement, you should test the application to ensure the removal of associated Access Control Lists (ACL) will not cause the application to perform unexpectedly.
~~~

-   <span data-ttu-id="d383b-127">**Sequencer 不會捕獲登錄 acl**，雖然排序器會在排序期間的安裝階段捕獲 NTFS 檔案系統 acl，但無法捕獲註冊表的 acl。</span><span class="sxs-lookup"><span data-stu-id="d383b-127">**Sequencer doesn’t capture registry ACLs**—Although the Sequencer captures the NTFS file system ACLs during the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="d383b-128">除了服務之外，使用者將擁有虛擬應用程式的所有登錄機碼的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="d383b-128">Users will have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="d383b-129">不過，如果使用者修改虛擬應用程式的登錄，該變更將會儲存在特定的書店（**uservol _sftfs \ _v1**）中，而不會影響其他使用者。</span><span class="sxs-lookup"><span data-stu-id="d383b-129">However, if a user modifies the registry of a virtual application, the change will be stored in a specific store (**uservol\_sftfs\_v1.pkg**) and will not affect other users.</span></span>

-   <span data-ttu-id="d383b-130">**應用程式服務**-app-v 針對屬於虛擬化應用程式的應用程式服務提供支援。</span><span class="sxs-lookup"><span data-stu-id="d383b-130">**Application services**—App-V provides support for application services that are part of a virtualized application.</span></span> <span data-ttu-id="d383b-131">不過，在虛擬環境中，它們將會執行的安全性內容受到限制。</span><span class="sxs-lookup"><span data-stu-id="d383b-131">However, in the virtual environment, the security context that they will run as is limited.</span></span> <span data-ttu-id="d383b-132">虛擬環境中唯一支援的安全性內容是本機系統、本機服務和網路服務。</span><span class="sxs-lookup"><span data-stu-id="d383b-132">The only security contexts supported in a virtual environment are Local System, Local Service, and Network Service.</span></span> <span data-ttu-id="d383b-133">在排序期間，如果為所支援的三種應用程式服務指定了安全性內容，則會在虛擬環境中套用本機系統安全性內容。</span><span class="sxs-lookup"><span data-stu-id="d383b-133">During sequencing, if a security context is specified for an application service other than the three supported, the Local System security context will be applied in the virtual environment.</span></span> <span data-ttu-id="d383b-134">如果應用程式服務設定為使用本機服務或網路服務，則會在虛擬環境中生效。</span><span class="sxs-lookup"><span data-stu-id="d383b-134">If the application service is configured to use either Local Service or Network Service, it will be honored in the virtual environment.</span></span> <span data-ttu-id="d383b-135">您可以使用這三個安全上下文，在排序程式期間完成設定服務帳戶的操作。</span><span class="sxs-lookup"><span data-stu-id="d383b-135">Configuring the service account can be done during the sequencing process using these three security contexts.</span></span>

-   <span data-ttu-id="d383b-136">**保留的安全性資訊**：在排序應用程式時，您可以將應用程式作為使用者安裝，或者您可以開發自動方法來安裝應用程式，同時監視。</span><span class="sxs-lookup"><span data-stu-id="d383b-136">**Persisted security information**—When sequencing applications, you can install the application as a user would or you can develop an automated method for installing the application while being monitored.</span></span> <span data-ttu-id="d383b-137">不會從套件中排除的所有專案都會被捕獲為該套件的一部分，因此應用程式將會有必要的資產在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="d383b-137">Everything that is not being excluded from the package will be captured as part of that package so that the application will have the necessary assets to run in a virtualized environment.</span></span> <span data-ttu-id="d383b-138">某些應用程式會在安裝期間儲存機密的安全性資訊（例如密碼）;如果持久保持不受保護，則其他可存取套件的使用者就能存取此安全性資訊。</span><span class="sxs-lookup"><span data-stu-id="d383b-138">Some applications store sensitive security information (such as passwords) during the installation; if persisted unprotected, this security information could be accessed by other users with access to the package.</span></span> <span data-ttu-id="d383b-139">在安裝期間，如果應用程式安裝要求輸入密碼或其他安全性敏感資訊，請檢查檔，以確保它不會繼續（在安裝之後移除），或在已保留的狀態下（已加密）。</span><span class="sxs-lookup"><span data-stu-id="d383b-139">During installation, if an application installation asks for a password or other security-sensitive information, check with the documentation to ensure that it is either not persisted (removed after installation) or, if persisted, that it is protected (encrypted).</span></span>

-   <span data-ttu-id="d383b-140">**保護虛擬應用程式套件**（安全）：請務必將虛擬應用程式套件儲存在網路上的安全位置，以防止套件遭到篡改或損毀。</span><span class="sxs-lookup"><span data-stu-id="d383b-140">**Securing virtual application packages**—Always save virtual application packages in a secure location on the network to protect the package from being tampered with or corrupted.</span></span>

## <span data-ttu-id="d383b-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="d383b-141">Related topics</span></span>


[<span data-ttu-id="d383b-142">規劃安全性與保護</span><span class="sxs-lookup"><span data-stu-id="d383b-142">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)









