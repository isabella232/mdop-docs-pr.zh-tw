---
title: 關於 Application Virtualization Sequencer
description: 關於 Application Virtualization Sequencer
author: dansimp
ms.assetid: bee193ca-58bd-40c9-b41a-310435633895
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83709bcceabe3312fba34512b47d28a24b4dc52c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802441"
---
# <span data-ttu-id="20f3f-103">關於 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="20f3f-103">About the Application Virtualization Sequencer</span></span>


<span data-ttu-id="20f3f-104">Microsoft Application Virtualization （App-v） Sequencer 會監視及記錄應用程式的所有安裝與設定處理常式，並建立下列檔案： **.ico**、 **OSD**、 **SFT**及**SPRJ**。</span><span class="sxs-lookup"><span data-stu-id="20f3f-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records all installation and setup processes for an application and creates the following files: **ICO**, **OSD**, **SFT**, and **SPRJ**.</span></span> <span data-ttu-id="20f3f-105">這些檔案包含有關應用程式的所有必要資訊，讓應用程式可以在目的電腦上的虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="20f3f-105">These files contain all the necessary information about an application so the application can run in a virtual environment on target computers.</span></span> <span data-ttu-id="20f3f-106">您可以使用 Microsoft Application Virtualization （App-v） Sequencer 來建立虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-106">You can use the Microsoft Application Virtualization (App-V) Sequencer to create virtual applications.</span></span> <span data-ttu-id="20f3f-107">當您將應用程式排序之後，就可以將它流式處理至目的電腦，或讓目的電腦下載虛擬應用程式套件的內容，並在本機執行應用程式，以執行虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-107">After you sequence an application, it can be streamed to target computers, or target computers can run the virtual application by downloading the contents of the virtual application package and running the application locally.</span></span>

<span data-ttu-id="20f3f-108">**重要** 若要執行虛擬應用程式套件，目的電腦必須執行適當版本的 App-V 用戶端。</span><span class="sxs-lookup"><span data-stu-id="20f3f-108">**Important** To run a virtual application package the target computer must be running the appropriate version of the App-V client.</span></span>

 

<span data-ttu-id="20f3f-109">虛擬應用程式套件是在目的電腦上執行，而不與目的電腦上的基礎作業系統互動，因為每個應用程式都是在虛擬環境中執行，且獨立于在目的電腦上安裝或執行的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-109">Virtual application packages run on target computers without interacting with the underlying operating system on the target computer because each application runs in a virtual environment and is isolated from other applications that are installed or running on the target computer.</span></span> <span data-ttu-id="20f3f-110">這個隔離可以減少應用程式衝突，並有助於減少所需的應用程式預先部署測試數量。</span><span class="sxs-lookup"><span data-stu-id="20f3f-110">This isolation can reduce application conflicts and can help decrease the required amount of application pre-deployment testing.</span></span>

## <span data-ttu-id="20f3f-111">排序器術語</span><span class="sxs-lookup"><span data-stu-id="20f3f-111">Sequencer Terminology</span></span>


<a href="" id="application-virtualization-drive"></a><span data-ttu-id="20f3f-112">Application Virtualization 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="20f3f-112">Application Virtualization drive</span></span>  
<span data-ttu-id="20f3f-113">應用程式虛擬化磁片磁碟機是執行順序應用程式的目的電腦上的預設磁片磁碟機（Q:\）。</span><span class="sxs-lookup"><span data-stu-id="20f3f-113">The application virtualization drive is the default drive (Q:\) on the target computer from which sequenced applications are run.</span></span>

<a href="" id="ico-file"></a><span data-ttu-id="20f3f-114">.ICO 檔案</span><span class="sxs-lookup"><span data-stu-id="20f3f-114">ICO file</span></span>  
<span data-ttu-id="20f3f-115">用戶端桌面上的圖示檔案，用來啟動已排序的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-115">The icon file on the client desktop which is used to launch a sequenced application.</span></span>

<a href="" id="installation-directory"></a><span data-ttu-id="20f3f-116">安裝目錄</span><span class="sxs-lookup"><span data-stu-id="20f3f-116">Installation directory</span></span>  
<span data-ttu-id="20f3f-117">排序器在安裝期間用來放置安裝盤案的目錄。</span><span class="sxs-lookup"><span data-stu-id="20f3f-117">The directory used by the sequencer to place installation files during setup.</span></span>

<a href="" id="open-software-descriptor--osd--file"></a><span data-ttu-id="20f3f-118">開啟軟體描述項（OSD）檔案</span><span class="sxs-lookup"><span data-stu-id="20f3f-118">Open Software Descriptor (OSD) file</span></span>  
<span data-ttu-id="20f3f-119">程式化的 XML 檔案，會指示 App-v 用戶端如何從 App-v 流式處理伺服器中檢索已排序的應用程式，以及如何在虛擬環境中執行已排序的應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-119">An XML-based file that instructs the App-V client how to retrieve the sequenced application from the App-V streaming server and how to run the sequenced application in the virtual environment.</span></span>

<a href="" id="package-root-directory"></a><span data-ttu-id="20f3f-120">套件根目錄</span><span class="sxs-lookup"><span data-stu-id="20f3f-120">Package root directory</span></span>  
<span data-ttu-id="20f3f-121">排序電腦上已安裝排序後之應用程式套件之檔案的目錄。</span><span class="sxs-lookup"><span data-stu-id="20f3f-121">The directory on the sequencing computer on which files for the sequenced application package are installed.</span></span> <span data-ttu-id="20f3f-122">這個目錄也會在您的電腦上以資料流程的方式存在。</span><span class="sxs-lookup"><span data-stu-id="20f3f-122">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span>

<a href="" id="sequenced-application"></a><span data-ttu-id="20f3f-123">順序應用程式</span><span class="sxs-lookup"><span data-stu-id="20f3f-123">Sequenced application</span></span>  
<span data-ttu-id="20f3f-124">由 sequencer 監視的應用程式，分解成主要和次要功能區塊，資料流程傳送到執行 App-v 用戶端 t 的目的電腦，並執行虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="20f3f-124">An application that has been monitored by the sequencer, broken up into primary and secondary feature blocks, streamed to a target computer running the App-V client t, and runs a virtual environment.</span></span>

<a href="" id="sequenced-application-package"></a><span data-ttu-id="20f3f-125">已排序的應用程式套件</span><span class="sxs-lookup"><span data-stu-id="20f3f-125">Sequenced application package</span></span>  
<span data-ttu-id="20f3f-126">組成虛擬應用程式的檔案，並允許虛擬應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="20f3f-126">The files that comprise a virtual application and allow a virtual application to run.</span></span> <span data-ttu-id="20f3f-127">這些檔案是在進行排序之後建立，特別包含 **.osd**、 **sft**、 **sprj**及 **.ico**檔案。</span><span class="sxs-lookup"><span data-stu-id="20f3f-127">These files are created after sequencing and specifically include **.osd**, **.sft**, **.sprj**, and **.ico** files.</span></span>

<a href="" id="sequencing"></a><span data-ttu-id="20f3f-128">序列</span><span class="sxs-lookup"><span data-stu-id="20f3f-128">Sequencing</span></span>  
<span data-ttu-id="20f3f-129">使用 App-v 排序器建立應用程式套件的程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-129">The process of creating an application package using the App-V Sequencer.</span></span> <span data-ttu-id="20f3f-130">在這個程式中，系統會監視應用程式、設定其快速鍵，並建立順序化的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="20f3f-130">In this process, an application is monitored, its shortcuts are configured, and a sequenced application package is created.</span></span>

<a href="" id="sequencing-computer"></a><span data-ttu-id="20f3f-131">順序電腦</span><span class="sxs-lookup"><span data-stu-id="20f3f-131">Sequencing computer</span></span>  
<span data-ttu-id="20f3f-132">用來對應用程式進行排序的電腦。</span><span class="sxs-lookup"><span data-stu-id="20f3f-132">The computer used to sequence an application.</span></span>

<a href="" id="virtual-application"></a><span data-ttu-id="20f3f-133">虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="20f3f-133">Virtual application</span></span>  
<span data-ttu-id="20f3f-134">由排序器封裝的應用程式，以在自包含的虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="20f3f-134">An application packaged by the Sequencer to run in a self-contained, virtual environment.</span></span> <span data-ttu-id="20f3f-135">虛擬環境包含在用戶端上執行應用程式所需的資訊，而不需要在本機安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="20f3f-135">The virtual environment contains the information necessary to run the application on the client without installing the application locally.</span></span>

<a href="" id="primary-feature-block"></a><span data-ttu-id="20f3f-136">主要功能區塊</span><span class="sxs-lookup"><span data-stu-id="20f3f-136">Primary feature block</span></span>  
<span data-ttu-id="20f3f-137">應用程式在目的電腦上執行時所需的虛擬應用程式套件中的最小內容。</span><span class="sxs-lookup"><span data-stu-id="20f3f-137">The minimum content in a virtual application package that is necessary for an application to run on a target computer.</span></span> <span data-ttu-id="20f3f-138">主要功能區塊中的內容是在排序的應用程式階段中識別，通常是由最常用的應用程式功能的內容所組成。</span><span class="sxs-lookup"><span data-stu-id="20f3f-138">The content in the primary feature block is identified during the application phase of sequencing and typically consists of the content for the most used application features.</span></span>

## <a href="" id="sequencing-applications-"></a><span data-ttu-id="20f3f-139">排序應用程式</span><span class="sxs-lookup"><span data-stu-id="20f3f-139">Sequencing Applications</span></span>


<span data-ttu-id="20f3f-140">有兩種方法可以在您的環境中建立及修改虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="20f3f-140">There are two methods to create and modify virtual application packages in your environment.</span></span> <span data-ttu-id="20f3f-141">第一種方法是使用 [**順序**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="20f3f-141">The first method is by using the **Sequencing** wizard.</span></span> <span data-ttu-id="20f3f-142">[**順序**] 嚮導可讓您建立新的虛擬應用程式套件或修改現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="20f3f-142">The **Sequencing** wizard allows you to create new, or modify existing virtual application packages.</span></span> <span data-ttu-id="20f3f-143">如需使用 [**排序**嚮導] 的詳細資訊，請參閱[如何為新的應用程式排序](how-to-sequence-a-new-application.md)。</span><span class="sxs-lookup"><span data-stu-id="20f3f-143">For more information about using the **Sequencing** wizard see, [How to Sequence a New Application](how-to-sequence-a-new-application.md).</span></span> <span data-ttu-id="20f3f-144">第二種方法是使用命令列。</span><span class="sxs-lookup"><span data-stu-id="20f3f-144">The second method is by using the command-line.</span></span> <span data-ttu-id="20f3f-145">命令列可讓您使用命令提示字元建立新的或修改現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="20f3f-145">The command-line allows you to create new, or modify existing virtual application packages using the command prompt.</span></span> <span data-ttu-id="20f3f-146">如需有關使用命令列的詳細資訊，請參閱[如何使用命令列管理虛擬應用程式](how-to-manage-virtual-applications-using-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="20f3f-146">For more information about using the command line see, [How to Manage Virtual Applications Using the Command Line](how-to-manage-virtual-applications-using-the-command-line.md).</span></span>

<span data-ttu-id="20f3f-147">[**順序**] 嚮導會提供下列函數來建立虛擬應用程式套件：</span><span class="sxs-lookup"><span data-stu-id="20f3f-147">The **Sequencing** wizard provides the following functions for creating virtual application packages:</span></span>

1.  <span data-ttu-id="20f3f-148">**套件**設定： [**順序**] 嚮導會提示完成開啟軟體描述項（OSD）檔案所需的封裝設定資訊，這是啟動順序應用程式套件所需的檔案。</span><span class="sxs-lookup"><span data-stu-id="20f3f-148">**Package Configuration**: The **Sequencing** Wizard prompts for package configuration information necessary to complete the Open Software Descriptor (OSD) file, which is a required file for starting a sequenced application package.</span></span>

2.  <span data-ttu-id="20f3f-149">**應用程式安裝**： [**順序**] 嚮導會收集應用程式安裝與啟動設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="20f3f-149">**Application Installation**: The **Sequencing** Wizard gathers information about an application’s installation and startup configurations.</span></span> <span data-ttu-id="20f3f-150">它會監視及記錄與應用程式相關聯的安裝與啟動資訊，以建立虛擬應用程式套件所需的檔案。</span><span class="sxs-lookup"><span data-stu-id="20f3f-150">It monitors and records the installation and startup information associated with the application to create the files necessary for a virtual application package.</span></span>

3.  <span data-ttu-id="20f3f-151">**應用程式啟動**： [**排序**] 嚮導會收集編譯及排序所需程式碼區塊的資訊，以便在目的電腦上執行已排序之應用程式套件的初始啟動。</span><span class="sxs-lookup"><span data-stu-id="20f3f-151">**Application Startup**: The **Sequencing** Wizard gathers information for compiling and ordering the blocks of code necessary to perform the initial startup of the sequenced application package on the target computer.</span></span> <span data-ttu-id="20f3f-152">程式碼區塊的編譯稱為主要功能區塊。</span><span class="sxs-lookup"><span data-stu-id="20f3f-152">The compilation of the code block is referred to as the primary feature block.</span></span>

## <span data-ttu-id="20f3f-153">應用程式虛擬化 Sequencer 的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="20f3f-153">Application Virtualization Sequencer Security Considerations</span></span>


<span data-ttu-id="20f3f-154">App-v 排序器會執行使用本機系統帳戶在先後順序時間檢測到的所有服務，但不會在服務控制要求上強制執行安全性描述項。</span><span class="sxs-lookup"><span data-stu-id="20f3f-154">The App-V Sequencer runs all services detected at sequencing time using the Local System account and does not enforce security descriptors on service control requests.</span></span> <span data-ttu-id="20f3f-155">如果服務是使用不同的使用者帳戶安裝，或者如果安全描述項是要授與使用者群組特定的服務許可權，請仔細考慮是否應該將服務虛擬化。</span><span class="sxs-lookup"><span data-stu-id="20f3f-155">If the service was installed using a different user account or if the security descriptors are intended to grant different user groups specific service permissions, consider carefully whether the service should be virtualized.</span></span> <span data-ttu-id="20f3f-156">在某些情況下，您應該在本機安裝該服務，以確保所需的服務安全性得以保留。</span><span class="sxs-lookup"><span data-stu-id="20f3f-156">In some cases, you should install the service locally to ensure that the intended service security is preserved.</span></span>

<span data-ttu-id="20f3f-157">**重要** 您應該總是將虛擬應用程式套件儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="20f3f-157">**Important** You should always save virtual application packages in a secure location.</span></span>

 

## <span data-ttu-id="20f3f-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="20f3f-158">Related topics</span></span>


[<span data-ttu-id="20f3f-159">Application Virtualization Sequencer 概觀</span><span class="sxs-lookup"><span data-stu-id="20f3f-159">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





