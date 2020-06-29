---
title: 關於 App-V 封裝加速器 (App-V 4.6 SP1)
description: 關於 App-V 封裝加速器 (App-V 4.6 SP1)
author: manikadhiman
ms.assetid: fc2d2375-8f17-4a6d-b374-771cb947cb8c
ms.reviewer: ''
manager: dansimp
ms.author: v-madhi
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cb7b8e6fa9482838283257843caf4b291c03bf2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802478"
---
# <span data-ttu-id="8c773-103">關於 App-V 封裝加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="8c773-103">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="8c773-104">您可以使用 App-v 封裝加速器來自動序列化大型、複雜的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c773-104">You can use App-V Package Accelerators to automatically sequence large, complex applications.</span></span> <span data-ttu-id="8c773-105">此外，當您套用 app-v 套件加速器時，您不一定必須手動安裝應用程式，才能建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="8c773-105">Additionally, when you apply an App-V Package Accelerator, you are not always required to manually install an application to create the virtual application package.</span></span>

<span data-ttu-id="8c773-106">**記事** 在某些情況下，系統會提示您在執行 App-v 排序器的電腦上本機安裝應用程式，然後才能使用套件加速器。</span><span class="sxs-lookup"><span data-stu-id="8c773-106">**Note** In some cases, you are prompted to install an application locally to the computer running the App-V Sequencer before you can use the Package Accelerator.</span></span> <span data-ttu-id="8c773-107">如果您必須安裝應用程式，您必須安裝應用程式至應用程式的預設位置。</span><span class="sxs-lookup"><span data-stu-id="8c773-107">If you have to install an application, you must install the application to the application’s default location.</span></span> <span data-ttu-id="8c773-108">App-v 排序器不會監視此安裝。</span><span class="sxs-lookup"><span data-stu-id="8c773-108">This installation is not monitored by App-V Sequencer.</span></span> <span data-ttu-id="8c773-109">建立 App-v 套件加速器時，套件加速器的作者決定是否需要在本機安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c773-109">When the App-V Package Accelerator is created, the author of the Package Accelerator determines whether to install an application locally is required.</span></span>

 

<span data-ttu-id="8c773-110">App-v 排序器會從 App-v 套件加速器和相關安裝媒體提取所需的檔案，以建立虛擬套件，而不需要監視應用程式的安裝。</span><span class="sxs-lookup"><span data-stu-id="8c773-110">App-V Sequencer extracts the required files from the App-V Package Accelerator and associated installation media to create a virtual package without having to monitor the installation of the application.</span></span>

<span data-ttu-id="8c773-111">**重要** 免責聲明： Microsoft Application Virtualization Sequencer 不會提供您用來建立套件加速器之軟體應用程式的授權權利。</span><span class="sxs-lookup"><span data-stu-id="8c773-111">**Important** Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="8c773-112">您必須遵守此類應用程式的所有使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="8c773-112">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="8c773-113">您有責任確認軟體應用程式的授權條款可讓您使用 Application Virtualization 排序器建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="8c773-113">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>

 

<span data-ttu-id="8c773-114">App-v 和專案範本彼此不同。</span><span class="sxs-lookup"><span data-stu-id="8c773-114">App-V Package Accelerators and project templates differ from each other.</span></span> <span data-ttu-id="8c773-115">套件加速器是特定于應用程式的。</span><span class="sxs-lookup"><span data-stu-id="8c773-115">Package Accelerators are application-specific.</span></span> <span data-ttu-id="8c773-116">[專案範本] 可讓使用者儲存組織專用的常用設定，並將它們套用至多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c773-116">Project templates enable users to save commonly used settings specific to an organization and apply them to multiple applications.</span></span> <span data-ttu-id="8c773-117">您也可以在命令提示字元中建立專案範本，而相反地，您必須使用 App-v 排序器主控台來建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="8c773-117">You can also create project templates at the command prompt, while in contrast, you must use the App-V Sequencer console to create Package Accelerators.</span></span> <span data-ttu-id="8c773-118">此外，不支援使用套件加速器建立套件及套用專案範本。</span><span class="sxs-lookup"><span data-stu-id="8c773-118">Additionally, creating a package by using a Package Accelerator and applying a project template is not supported.</span></span>

## <span data-ttu-id="8c773-119">共用 app-v 套件加速器</span><span class="sxs-lookup"><span data-stu-id="8c773-119">Sharing App-V Package Accelerators</span></span>


<span data-ttu-id="8c773-120">本節提供有關如何共用套件加速器的最佳做法資訊。</span><span class="sxs-lookup"><span data-stu-id="8c773-120">This section provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="8c773-121">如果您打算共用套件加速器，諸如電腦名稱稱、使用者帳戶資訊等資訊，以及相關聯應用程式的相關資訊，都可能包含在套件加速器中。下列清單說明您在建立套件加速器時應考慮的方法：</span><span class="sxs-lookup"><span data-stu-id="8c773-121">If you plan to share Package Accelerators, information such as computer names, user account information, and information about the associated applications might be included in the Package Accelerators.The following list describes methods you should consider when creating Package Accelerators:</span></span>

-   <span data-ttu-id="8c773-122">[**使用者名稱**]。</span><span class="sxs-lookup"><span data-stu-id="8c773-122">**User name**.</span></span> <span data-ttu-id="8c773-123">當您登入執行 App-v 排序器的電腦時，您應該使用一般的使用者帳戶，例如管理電腦/網域的內建**管理員**帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c773-123">When you log on to the computer running App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account for administering the computer / domain.</span></span> <span data-ttu-id="8c773-124">您不應該使用以現有的使用者名稱為基礎的帳戶。</span><span class="sxs-lookup"><span data-stu-id="8c773-124">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="8c773-125">[**電腦名稱稱**]。</span><span class="sxs-lookup"><span data-stu-id="8c773-125">**Computer Name**.</span></span> <span data-ttu-id="8c773-126">指定執行排序器之電腦的一般、非鑒別名稱。</span><span class="sxs-lookup"><span data-stu-id="8c773-126">Specify a general, non-identifying name for the computer running the Sequencer.</span></span>

-   <span data-ttu-id="8c773-127">**伺服器 URL**。</span><span class="sxs-lookup"><span data-stu-id="8c773-127">**Server URL**.</span></span> <span data-ttu-id="8c773-128">在 Sequencer 主控台的 [**部署**] 索引標籤上，使用伺服器 URL 設定資訊的預設設定。</span><span class="sxs-lookup"><span data-stu-id="8c773-128">In the Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="8c773-129">**應用程式**。</span><span class="sxs-lookup"><span data-stu-id="8c773-129">**Applications**.</span></span> <span data-ttu-id="8c773-130">如果您不想在建立套件加速器時共用執行 Sequencer 之電腦上所安裝的應用程式清單，您必須刪除**appv\_manifest.xml**檔案。</span><span class="sxs-lookup"><span data-stu-id="8c773-130">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="8c773-131">此檔案位於虛擬應用程式套件的套件根目錄中。</span><span class="sxs-lookup"><span data-stu-id="8c773-131">This file is located in the package root directory of the virtual application package.</span></span>

<span data-ttu-id="8c773-132">您也應該檢查與虛擬應用程式套件相關聯的任何設定或設定檔，以確保應用程式不包含任何個人資訊。</span><span class="sxs-lookup"><span data-stu-id="8c773-132">You should also review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.</span></span>

## <span data-ttu-id="8c773-133">保護 App-v 套件加速器</span><span class="sxs-lookup"><span data-stu-id="8c773-133">Securing App-V Package Accelerators</span></span>


<span data-ttu-id="8c773-134">在網路上的安全位置，請務必將 app-v 封裝快速鍵及任何關聯的安裝媒體儲存在網路上，以保護 App-v 套件加速器以及安裝檔案不受損害或遭到損毀。</span><span class="sxs-lookup"><span data-stu-id="8c773-134">Always save App-V Package Accelerators and any associated installation media in a secure location on the network to protect the App-V Package Accelerators and the installation files from being tampered with or becoming corrupted.</span></span> <span data-ttu-id="8c773-135">因為套件加速器也可以包含密碼和使用者專用的資訊，所以您必須將 App-v 套件加速器儲存在安全的位置，而且您必須在建立套件加速器之後進行數位簽章，以便在應用套件加速器時驗證發行者。</span><span class="sxs-lookup"><span data-stu-id="8c773-135">Because Package Accelerators can also contain password and user-specific information, you must save App-V Package Accelerators in a secure location, and you must digitally sign the Package Accelerator after you create it so that the publisher can be verified when the Package Accelerator is applied.</span></span> <span data-ttu-id="8c773-136">如需數位簽章的詳細資訊，請參閱[常見準則安全性的數位簽章慣例的應用程式指導方針](https://go.microsoft.com/fwlink/?LinkId=204705)（ https://go.microsoft.com/fwlink/?LinkId=204705) 。</span><span class="sxs-lookup"><span data-stu-id="8c773-136">For more information about digital signatures, see [Application Guidelines on Digital Signature Practices for Common Criteria Security](https://go.microsoft.com/fwlink/?LinkId=204705) (https://go.microsoft.com/fwlink/?LinkId=204705).</span></span>

## <span data-ttu-id="8c773-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="8c773-137">Related topics</span></span>


[<span data-ttu-id="8c773-138">如何建立 App-V 封裝加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="8c773-138">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)

[<span data-ttu-id="8c773-139">如何套用套件加速器以建立虛擬應用程式套件（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="8c773-139">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)

 

 





