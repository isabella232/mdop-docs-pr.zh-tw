---
title: 為 App-V 5.1 Sequencer 與 Client 部署進行規劃
description: 為 App-V 5.1 Sequencer 與 Client 部署進行規劃
author: dansimp
ms.assetid: d92f8773-fa7d-4926-978a-433978f91202
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 31a0296814b16ba1c776dca522423fc7b6b6ed96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800349"
---
# <span data-ttu-id="65043-103">為 App-V 5.1 Sequencer 與 Client 部署進行規劃</span><span class="sxs-lookup"><span data-stu-id="65043-103">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span>


<span data-ttu-id="65043-104">在您開始使用 Microsoft Application Virtualization （App-v）5.1 之前，您必須安裝 App-v 5.1 排序器、App-v 5.1 用戶端，以及（選擇性） app-v 5.1 共用內容儲存區。</span><span class="sxs-lookup"><span data-stu-id="65043-104">Before you can start to use Microsoft Application Virtualization (App-V) 5.1, you must install the App-V 5.1 sequencer, the App-V 5.1 client, and optionally the App-V 5.1 shared content store.</span></span> <span data-ttu-id="65043-105">下列各節將針對這些安裝進行規劃。</span><span class="sxs-lookup"><span data-stu-id="65043-105">The following sections address planning for these installations.</span></span>

## <span data-ttu-id="65043-106">規劃 app-v 5.1 sequencer 部署</span><span class="sxs-lookup"><span data-stu-id="65043-106">Planning for App-V 5.1 sequencer deployment</span></span>


<span data-ttu-id="65043-107">App-V 5.1 使用名為「排序」的程式來建立虛擬化應用程式和應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="65043-107">App-V 5.1 uses a process called sequencing to create virtualized applications and application packages.</span></span> <span data-ttu-id="65043-108">排序需要使用執行 App-v 5.1 排序器的電腦。</span><span class="sxs-lookup"><span data-stu-id="65043-108">Sequencing requires the use of a computer that runs the App-V 5.1 sequencer.</span></span>

<span data-ttu-id="65043-109">**記事** 如需 App-v 5.1 排序器新功能的相關資訊，請參閱[關於 app-v 5.1](about-app-v-51.md)的 [ **sequencer 改進**] 區段。</span><span class="sxs-lookup"><span data-stu-id="65043-109">**Note** For information about the new functionality of App-V 5.1 sequencer, see the **Sequencer Improvements** section of [About App-V 5.1](about-app-v-51.md).</span></span>

 

<span data-ttu-id="65043-110">執行 App-v 5.1 sequencer 的電腦必須符合最低系統需求。</span><span class="sxs-lookup"><span data-stu-id="65043-110">The computer that runs the App-V 5.1 sequencer must meet the minimum system requirements.</span></span> <span data-ttu-id="65043-111">如需這些需求的清單，請參閱[App-V 5.1 支援的](app-v-51-supported-configurations.md)設定。</span><span class="sxs-lookup"><span data-stu-id="65043-111">For a list of these requirements, see [App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md).</span></span>

<span data-ttu-id="65043-112">在理想的情況下，您應該在執行為虛擬機器的電腦上安裝排序器。</span><span class="sxs-lookup"><span data-stu-id="65043-112">Ideally, you should install the sequencer on a computer running as a virtual machine.</span></span> <span data-ttu-id="65043-113">這可讓您更輕鬆地將執行 sequencer 的電腦還原為「乾淨」狀態，然後再將另一個應用程式排序。</span><span class="sxs-lookup"><span data-stu-id="65043-113">This enables you to more easily revert the computer running the sequencer to a “clean” state before sequencing another application.</span></span> <span data-ttu-id="65043-114">當您使用虛擬機器安裝排序器時，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="65043-114">When you install the sequencer using a virtual machine, you should perform the following steps:</span></span>

1.  <span data-ttu-id="65043-115">安裝所有關聯的排序器必備元件。</span><span class="sxs-lookup"><span data-stu-id="65043-115">Install all associated sequencer prerequisites.</span></span>

2.  <span data-ttu-id="65043-116">安裝排序器。</span><span class="sxs-lookup"><span data-stu-id="65043-116">Install the sequencer.</span></span>

3.  <span data-ttu-id="65043-117">拍攝環境的「快照」。</span><span class="sxs-lookup"><span data-stu-id="65043-117">Take a “snapshot” of the environment.</span></span>

<span data-ttu-id="65043-118">**重要** 您應該讓貴公司的安全小組審查並核准連續處理程式規劃。</span><span class="sxs-lookup"><span data-stu-id="65043-118">**Important** You should have your corporate security team review and approve the sequencing process plan.</span></span> <span data-ttu-id="65043-119">出於安全性考慮，您應該將 sequencer 作業保持在與生產環境不同的實驗中。</span><span class="sxs-lookup"><span data-stu-id="65043-119">For security reasons, you should keep the sequencer operations in a lab that is separate from the production environment.</span></span> <span data-ttu-id="65043-120">根據您的業務需求，分隔相片順序可以簡單或完整地進行。</span><span class="sxs-lookup"><span data-stu-id="65043-120">The separation arrangement can be as simple or as comprehensive as necessary, based on your business requirements.</span></span> <span data-ttu-id="65043-121">先後順序電腦必須能夠連線到公司網路，才能將完成的套件複製到生產伺服器。</span><span class="sxs-lookup"><span data-stu-id="65043-121">The sequencing computers must be able to connect to the corporate network to copy finished packages to the production servers.</span></span> <span data-ttu-id="65043-122">不過，因為先後順序電腦通常不使用防防毒保護，所以不能在未受保護的商業網路上運作。</span><span class="sxs-lookup"><span data-stu-id="65043-122">However, because the sequencing computers are typically operated without antivirus protection, they must not be on the corporate network unprotected.</span></span> <span data-ttu-id="65043-123">例如，您可能可以在防火牆之後或在隔離的網段上運作。</span><span class="sxs-lookup"><span data-stu-id="65043-123">For example, you might be able to operate behind a firewall or on an isolated network segment.</span></span> <span data-ttu-id="65043-124">您也可以使用被設定為共用隔離虛擬網路的虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="65043-124">You might also be able to use virtual machines that are configured to share an isolated virtual network.</span></span> <span data-ttu-id="65043-125">依照您的公司安全性原則來安全地解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="65043-125">Follow your corporate security policies to safely address these concerns.</span></span>

 

## <span data-ttu-id="65043-126">規劃 App-v 5.1 用戶端部署</span><span class="sxs-lookup"><span data-stu-id="65043-126">Planning for App-V 5.1 client deployment</span></span>


<span data-ttu-id="65043-127">若要在目的電腦上執行虛擬化套件，您必須在目的電腦上安裝 App-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="65043-127">To run virtualized packages on target computers, you must install the App-V 5.1 client on the target computers.</span></span> <span data-ttu-id="65043-128">App-V 5.1 用戶端是在目的電腦上執行虛擬化應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="65043-128">The App-V 5.1 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="65043-129">用戶端可讓使用者與圖示和特定檔案類型互動，以啟動虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="65043-129">The client enables users to interact with icons and specific file types to start virtualized applications.</span></span> <span data-ttu-id="65043-130">用戶端也可協助從管理伺服器取得應用程式內容，並在用戶端啟動應用程式之前，先緩存內容。</span><span class="sxs-lookup"><span data-stu-id="65043-130">The client also helps obtain application content from the management server and caches the content before the client starts the application.</span></span> <span data-ttu-id="65043-131">以下是兩種不同的用戶端類型：遠端桌面服務的用戶端，在遠端桌面工作階段主機（RD 工作階段主機）伺服器系統和應用程式-V 5.1 用戶端（適用于所有其他電腦）上使用。</span><span class="sxs-lookup"><span data-stu-id="65043-131">There are two different client types: the client for Remote Desktop Services, which is used on Remote Desktop Session Host (RD Session Host) server systems and the App-V 5.1 client, which is used for all other computers.</span></span>

<span data-ttu-id="65043-132">App-V 5.1 用戶端應該使用安裝程式命令列，或在安裝完成後使用 PowerShell 腳本進行設定。</span><span class="sxs-lookup"><span data-stu-id="65043-132">The App-V 5.1 client should be configured by using either the installer command line or by using a PowerShell script after the installation has been completed.</span></span>

<span data-ttu-id="65043-133">您必須小心地定義這些設定，才能加速 App-V 5.1 用戶端軟體的部署。</span><span class="sxs-lookup"><span data-stu-id="65043-133">The settings must be defined carefully in advance in order to expedite the deployment of the App-V 5.1 client software.</span></span> <span data-ttu-id="65043-134">當您的電腦位於不同的辦公室，且用戶端必須設定為使用不同的來源位置時，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="65043-134">This is especially important when you have computers in different offices where the clients must be configured to use different source locations.</span></span>

<span data-ttu-id="65043-135">您也必須決定將如何部署用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="65043-135">You must also determine how you will deploy the client software.</span></span> <span data-ttu-id="65043-136">雖然您可以在每個電腦上手動部署用戶端，但大多陣列織想要透過自動化程式來部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="65043-136">Although it is possible to deploy the client manually on each computer, most organizations prefer to deploy the client through an automated process.</span></span> <span data-ttu-id="65043-137">較大型的組織可能有一個可操作的電子軟體發佈（ESD）系統，這是理想的用戶端部署系統。</span><span class="sxs-lookup"><span data-stu-id="65043-137">A larger organization might have an operational Electronic Software Distribution (ESD) system, which is an ideal client deployment system.</span></span> <span data-ttu-id="65043-138">如果不存在 ESD 系統，您可以使用貴組織的標準安裝軟體方法。</span><span class="sxs-lookup"><span data-stu-id="65043-138">If no ESD system exists, you can use your organization’s standard method of installing software.</span></span> <span data-ttu-id="65043-139">可能的方法包括群組原則或各種腳本技術。</span><span class="sxs-lookup"><span data-stu-id="65043-139">Possible methods include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="65043-140">根據用戶端電腦的數量和不同位置而定，此部署程式可能會很複雜。</span><span class="sxs-lookup"><span data-stu-id="65043-140">Depending on the quantity and disparate locations of your client computers, this deployment process can be complex.</span></span> <span data-ttu-id="65043-141">您必須使用結構化的方法，以確保所有電腦都能以正確的設定來取得已安裝的用戶端。</span><span class="sxs-lookup"><span data-stu-id="65043-141">You must use a structured approach to ensure that all computers get the client installed with the correct configuration.</span></span>

<span data-ttu-id="65043-142">如需用戶端最低需求的清單，請參閱[App-V 5.1 先決條件](app-v-51-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="65043-142">For a list of the client minimum requirements see [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

## <a href="" id="bkmk-client-coexist"></a><span data-ttu-id="65043-143">規劃 App-v 用戶端共存</span><span class="sxs-lookup"><span data-stu-id="65043-143">Planning for App-V client coexistence</span></span>


<span data-ttu-id="65043-144">您可以並排部署 app-v 5.1 用戶端與 App-v 4.6 用戶端。</span><span class="sxs-lookup"><span data-stu-id="65043-144">You can deploy the App-V 5.1 client side by side with the App-V 4.6 client.</span></span> <span data-ttu-id="65043-145">用戶端共存需要您使用部署設定檔或使用者設定檔來新增或發佈虛擬化的應用程式，因為這些設定檔案中必須設定 App-V 5.1 才能與 App-v 4.6 用戶端搭配使用的特定設定。</span><span class="sxs-lookup"><span data-stu-id="65043-145">Client coexistence requires that you add or publish virtualized applications by using either a deployment configuration file or a user configuration file, because there are certain settings in these configuration files that must be configured in order for App-V 5.1 to function with App-V4.6 clients.</span></span> <span data-ttu-id="65043-146">使用用戶端或伺服器升級套件時，套件必須重新提交設定檔。</span><span class="sxs-lookup"><span data-stu-id="65043-146">When a package is upgraded by using either the client or the server, the package must resubmit the configuration file.</span></span> <span data-ttu-id="65043-147">對於任何有對應設定檔的套件而言，這是正確的，因此它不是用戶端共存所特有的。</span><span class="sxs-lookup"><span data-stu-id="65043-147">This is true for any package that has a corresponding configuration file, so it is not specific to client coexistence.</span></span> <span data-ttu-id="65043-148">不過，如果您在套件升級期間沒有提交設定檔案，則在共存案例中，封裝狀態將無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="65043-148">However, if you do not submit the configuration file during the package upgrade, then the package state will not function as expected in coexistence scenarios.</span></span>

<span data-ttu-id="65043-149">App-v 5.1 動態配置檔案自訂特定使用者的套件。</span><span class="sxs-lookup"><span data-stu-id="65043-149">App-V 5.1 dynamic configuration files customize a package for a specific user.</span></span> <span data-ttu-id="65043-150">您必須先建立動態使用者配置（.xml）檔案或動態部署設定檔，才能使用它們。</span><span class="sxs-lookup"><span data-stu-id="65043-150">You must create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use them.</span></span> <span data-ttu-id="65043-151">若要建立檔案，需要執行高級手動操作。</span><span class="sxs-lookup"><span data-stu-id="65043-151">To create the file it requires an advanced manual operation.</span></span>

<span data-ttu-id="65043-152">使用動態使用者設定檔案時，不會使用資訊清單檔案中的任何應用程式-V 5.1 資訊。</span><span class="sxs-lookup"><span data-stu-id="65043-152">When a dynamic user configuration file is used, none of the App-V 5.1 information for the extension in the manifest file is used.</span></span> <span data-ttu-id="65043-153">這表示動態使用者設定檔案必須包含在資訊清單檔案中與 App-v 5.1 專用之延伸的所有內容，以及您想要進行的變更，例如刪除和更新。</span><span class="sxs-lookup"><span data-stu-id="65043-153">This means that the dynamic user configuration file must include everything for the extension that is specific to App-V 5.1 in the manifest file, as well as the changes that you want to make, such as, deletions and updates.</span></span> <span data-ttu-id="65043-154">如需如何建立自訂設定檔的詳細資訊，請參閱[如何使用 app-v 5.1 管理主控台來建立自訂的設定檔](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)。</span><span class="sxs-lookup"><span data-stu-id="65043-154">For more information about how to create a custom configuration file, see [How to Create a Custom Configuration File by Using the App-V 5.1 Management Console](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md).</span></span>

## <a href="" id="bkmk-plan-for-scs"></a><span data-ttu-id="65043-155">規劃 app-v 5.1 共用內容存放區（SCS）</span><span class="sxs-lookup"><span data-stu-id="65043-155">Planning for the App-V 5.1 Shared Content Store (SCS)</span></span>


<span data-ttu-id="65043-156">App-V 5.1 的 [共用內容存放區] 模式可讓執行 App-v 5.1 用戶端的電腦執行虛擬化的應用程式，而不會將任何套件內容儲存在執行 App-v 5.1 用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="65043-156">The App-V 5.1 shared content store mode allows the computer running the App-V 5.1 client to run virtualized applications and none of the package contents is saved on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="65043-157">只有在用戶端要求時，才會將虛擬應用程式流式處理至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="65043-157">Virtual applications are streamed to target computers only when requested by the client.</span></span>

<span data-ttu-id="65043-158">下列清單顯示使用 App-v 5.1 共用內容存放區的一些優點：</span><span class="sxs-lookup"><span data-stu-id="65043-158">The following list displays some of the benefits of using the App-V 5.1 shared content store:</span></span>

-   <span data-ttu-id="65043-159">減少 app 對應用程式和多使用者應用程式的衝突，因而減少迴歸測試的需求</span><span class="sxs-lookup"><span data-stu-id="65043-159">Reduced app-to-app and multi-user application conflicts and hence a reduced need for regression testing</span></span>

-   <span data-ttu-id="65043-160">減少部署風險，加速應用程式部署</span><span class="sxs-lookup"><span data-stu-id="65043-160">Accelerated application deployment by reduction of deployment risk</span></span>

-   <span data-ttu-id="65043-161">簡化的設定檔管理</span><span class="sxs-lookup"><span data-stu-id="65043-161">Simplified profile management</span></span>






## <a href="" id="other-resources-for-the-app-v-5-1-deployment-"></a><span data-ttu-id="65043-162">App-V 5.1 部署的其他資源</span><span class="sxs-lookup"><span data-stu-id="65043-162">Other resources for the App-V 5.1 deployment</span></span>


[<span data-ttu-id="65043-163">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="65043-163">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

## <span data-ttu-id="65043-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="65043-164">Related topics</span></span>


[<span data-ttu-id="65043-165">如何安裝 Sequencer</span><span class="sxs-lookup"><span data-stu-id="65043-165">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-51beta-gb18030.md)

[<span data-ttu-id="65043-166">如何部署 App-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="65043-166">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-51gb18030.md)

[<span data-ttu-id="65043-167">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="65043-167">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

[<span data-ttu-id="65043-168">如何安裝 App-V 5.1 用戶端以使用共用內容存放區模式</span><span class="sxs-lookup"><span data-stu-id="65043-168">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

 

 





