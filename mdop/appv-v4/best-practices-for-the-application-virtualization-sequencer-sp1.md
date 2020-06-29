---
title: Application Virtualization Sequencer 的最佳作法
description: Application Virtualization Sequencer 的最佳作法
author: dansimp
ms.assetid: 95e5e216-864f-41a1-90d4-b8d7e1eb42a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859514fb34185a339c7f2c2734f331e5a99d050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809092"
---
# <span data-ttu-id="8018f-103">Application Virtualization Sequencer 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="8018f-103">Best Practices for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="8018f-104">本主題提供執行 Microsoft 應用程式虛擬化（App-v）排序器的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8018f-104">This topic provides best practices for running the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="8018f-105">在您的環境中規劃和使用排序器時，請複習並考慮下列建議。</span><span class="sxs-lookup"><span data-stu-id="8018f-105">Review and consider the following recommendations when planning and using the Sequencer in your environment.</span></span>

## <span data-ttu-id="8018f-106">順序電腦配置最佳做法</span><span class="sxs-lookup"><span data-stu-id="8018f-106">Sequencing Computer Configuration Best Practices</span></span>


<span data-ttu-id="8018f-107">在設定執行 App-v 排序器的電腦時，請考慮下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="8018f-107">The following best practices should be considered when configuring the computer running the App-V Sequencer:</span></span>

-   **<span data-ttu-id="8018f-108">在具有類似設定且執行與目的電腦舊版作業系統的電腦上的順序。</span><span class="sxs-lookup"><span data-stu-id="8018f-108">Sequence on a computer that has a similar configuration and that is running an earlier version of the operating system than the target computers.</span></span>**

    <span data-ttu-id="8018f-109">確定執行排序器的電腦執行的是舊版作業系統，而不是目的電腦。</span><span class="sxs-lookup"><span data-stu-id="8018f-109">Ensure that the computer that is running the Sequencer is running an earlier version of the operating system than the target computers.</span></span> <span data-ttu-id="8018f-110">這包括 service pack 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="8018f-110">This includes the service pack and update versions.</span></span> <span data-ttu-id="8018f-111">例如，如果目的電腦正在執行 WindowsVista 和 WindowsXP，您應該在執行 WindowsXP 的電腦上排列應用程式。</span><span class="sxs-lookup"><span data-stu-id="8018f-111">For example, if the target computers are running WindowsVista and WindowsXP, you should sequence applications on a computer that is running WindowsXP.</span></span> <span data-ttu-id="8018f-112">在一個作業系統上進行排序的功能，並不保證在不同作業系統上執行虛擬化應用程式，而是視特定的應用程式和作業系統而定。</span><span class="sxs-lookup"><span data-stu-id="8018f-112">The ability to sequence on one operating system and run the virtualized application on a different operating system is not guaranteed, and depends on the particular application and operating system.</span></span> <span data-ttu-id="8018f-113">如果您遇到問題，可能會要求您在與 App V 用戶端執行的作業系統環境上進行順序。</span><span class="sxs-lookup"><span data-stu-id="8018f-113">If you encounter issues, you may be required to sequence on the same operating system environment as the one on which the App-V client is running.</span></span>

-   **<span data-ttu-id="8018f-114">將執行排序器的電腦設定為多個分區。</span><span class="sxs-lookup"><span data-stu-id="8018f-114">Configure the computer running the Sequencer with multiple partitions.</span></span>**

    <span data-ttu-id="8018f-115">您應該將執行排序器的電腦設定為至少有兩個主要分區。</span><span class="sxs-lookup"><span data-stu-id="8018f-115">You should configure the computer running the Sequencer with at least two primary partitions.</span></span> <span data-ttu-id="8018f-116">第一個分區（**C：**）應該包含作業系統，而且應該使用 NTFS 檔案系統來設定格式。</span><span class="sxs-lookup"><span data-stu-id="8018f-116">The first partition (**C:**) should contain the operating system, and it should be formatted using the NTFS file system.</span></span> <span data-ttu-id="8018f-117">第二個 partition （**Q：**）是用來做為虛擬應用程式安裝的目的地路徑，也應該使用 NTFS 檔案系統來設定格式。</span><span class="sxs-lookup"><span data-stu-id="8018f-117">The second partition (**Q:**) is used as the destination path for the virtual application installation and should also be formatted using the NTFS file system.</span></span>

-   **<span data-ttu-id="8018f-118">使用足夠的可用磁碟空間來設定 temp 目錄。</span><span class="sxs-lookup"><span data-stu-id="8018f-118">Configure the temp directory with enough free disk space.</span></span>**

    <span data-ttu-id="8018f-119">排序器使用 **% TMP%** 或 **% TEMP%** 目錄和**暫存**目錄，在排序期間儲存臨時檔案。</span><span class="sxs-lookup"><span data-stu-id="8018f-119">The Sequencer uses the **%TMP%** or **%TEMP%** directory and the **Scratch** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="8018f-120">您應該在執行排序器的電腦上設定這些目錄，並提供與估計應用程式安裝需求相當的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8018f-120">You should configure these directories on the computer running the Sequencer with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="8018f-121">您可以開啟排序器主控台，然後選取 [**工具**]、[**選項**]，然後選取 [**路徑**] 索引標籤，以驗證**暫存**目錄的位置。在不同的硬碟分區上設定臨時目錄和**暫存**目錄，可以在排序期間提升效能。</span><span class="sxs-lookup"><span data-stu-id="8018f-121">You can verify the location of the **Scratch** directory by opening the Sequencer console and selecting **Tools**, **Options**, and then selecting the **Paths** tab. Configuring the temp directories and the **Scratch** directory on different hard drive partitions can improve performance during sequencing.</span></span>

-   **<span data-ttu-id="8018f-122">使用 Microsoft VirtualPC 來排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="8018f-122">Sequence applications by using Microsoft VirtualPC.</span></span>**

    <span data-ttu-id="8018f-123">您會將大部分的應用程式順序數超過一次。</span><span class="sxs-lookup"><span data-stu-id="8018f-123">You will sequence most applications more than once.</span></span> <span data-ttu-id="8018f-124">為了協助協助您，您應該考慮在虛擬環境中執行的電腦上的順序。</span><span class="sxs-lookup"><span data-stu-id="8018f-124">To help facilitate this, you should consider sequencing on a computer running in a virtual environment.</span></span> <span data-ttu-id="8018f-125">這可讓您在執行排序器的電腦上，排序應用程式，並還原到乾淨狀態（最小的重新配置）。</span><span class="sxs-lookup"><span data-stu-id="8018f-125">This will allow you to sequence an application and revert to a clean state, with minimal reconfiguration, on the computer that is running the Sequencer.</span></span>

    <span data-ttu-id="8018f-126">如果您是在您的環境中執行 Microsoft Hyper-v，那麼當執行的 Hyper-v 虛擬電腦是下列情況時，就會執行 App-v 排序器：</span><span class="sxs-lookup"><span data-stu-id="8018f-126">If you are running Microsoft Hyper-V in your environment the App-V sequencer will run when the Hyper-V virtual computer it is running on is:</span></span>

    -   <span data-ttu-id="8018f-127">暫停並繼續。</span><span class="sxs-lookup"><span data-stu-id="8018f-127">paused and resumed.</span></span>

    -   <span data-ttu-id="8018f-128">其狀態已儲存並還原。</span><span class="sxs-lookup"><span data-stu-id="8018f-128">has its state saved and restored.</span></span>

    -   <span data-ttu-id="8018f-129">儲存為快照且已還原。</span><span class="sxs-lookup"><span data-stu-id="8018f-129">saved as a snapshot and is restored.</span></span>

    -   <span data-ttu-id="8018f-130">遷移至不同的硬體，做為即時移轉的一部分。</span><span class="sxs-lookup"><span data-stu-id="8018f-130">migrated to different hardware as part of a live migration.</span></span>

-   **<span data-ttu-id="8018f-131">在您順序新的應用程式之前，請先關閉其他執行中的程式。</span><span class="sxs-lookup"><span data-stu-id="8018f-131">Before you sequence a new application, shut down other running programs.</span></span>**

    <span data-ttu-id="8018f-132">在順序電腦上正常執行的程式及排程任務，可能會減緩順序程式，並導致在排序期間收集不相關的資料。</span><span class="sxs-lookup"><span data-stu-id="8018f-132">Processes and scheduled tasks that normally run on the sequencing computer can slow down the sequencing process and cause irrelevant data to be gathered during sequencing.</span></span> <span data-ttu-id="8018f-133">您必須先關閉所有不需要的應用程式和程式，才能開始進行排序。</span><span class="sxs-lookup"><span data-stu-id="8018f-133">All unnecessary applications and programs should be shut down before you begin sequencing.</span></span>

-   **<span data-ttu-id="8018f-134">在執行終端服務的電腦上的順序</span><span class="sxs-lookup"><span data-stu-id="8018f-134">Sequence on a computer that is running Terminal Services</span></span>**

    <span data-ttu-id="8018f-135">在安裝排序器之前，您不應該在執行終端服務的電腦上設定安裝模式。</span><span class="sxs-lookup"><span data-stu-id="8018f-135">You should not configure the install mode on a computer that is running Terminal Services before you install the sequencer.</span></span>

## <span data-ttu-id="8018f-136">排序最佳做法</span><span class="sxs-lookup"><span data-stu-id="8018f-136">Sequencing Best Practices</span></span>


<span data-ttu-id="8018f-137">排序新的應用程式時，請考慮下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="8018f-137">The following best practices should be considered when sequencing a new application:</span></span>

-   

    <span data-ttu-id="8018f-138">**記事** 如果您執行的是 App-V 4.6 SP1，您不需要按照8.3 命名慣例的目錄順序。</span><span class="sxs-lookup"><span data-stu-id="8018f-138">**Note** If you are running App-V 4.6 SP1 you do not need to sequence to a directory that follows the 8.3 naming convention.</span></span>

     

-   **<span data-ttu-id="8018f-139">順序移至遵循8.3 命名慣例的唯一目錄。</span><span class="sxs-lookup"><span data-stu-id="8018f-139">Sequence to a unique directory that follows the 8.3 naming convention.</span></span>**

    <span data-ttu-id="8018f-140">您應該將所有的應用程式排序為遵循8.3 命名慣例的目錄。</span><span class="sxs-lookup"><span data-stu-id="8018f-140">You should sequence all applications to a directory that follows the 8.3 naming convention.</span></span> <span data-ttu-id="8018f-141">指定的目錄名不能包含超過八個字元，後面再加上三個字元的副檔名，例如**Q:\\MYAPP。ABC**。</span><span class="sxs-lookup"><span data-stu-id="8018f-141">The specified directory name cannot contain more than eight characters, followed by a three-character file name extension—for example, **Q:\\MYAPP.ABC**.</span></span>

-   **<span data-ttu-id="8018f-142">順序，移至磁碟機根目錄的目的地資料夾，而不是子目錄。</span><span class="sxs-lookup"><span data-stu-id="8018f-142">Sequence to a destination folder on the root of the drive, not to a subdirectory.</span></span>**

    <span data-ttu-id="8018f-143">如果應用程式套件有多個元件，請將每個應用程式安裝到主要目錄的子目錄中。</span><span class="sxs-lookup"><span data-stu-id="8018f-143">If the application suite has multiple parts, install each application to a subdirectory of the main directory.</span></span> <span data-ttu-id="8018f-144">例如，如果套件包含與用戶端相同的應用程式，請使用**Q:\\AppSuite**作為主要目錄，並將主要的應用程式排序至**Q:\\AppSuite\\Main**，並將用戶端排序至**Q:\\AppSuite\\Client**。</span><span class="sxs-lookup"><span data-stu-id="8018f-144">For example, if a package contains an application along with a client, use **Q:\\AppSuite** as the main directory and sequence the main application to **Q:\\AppSuite\\Main**, and sequence the client to **Q:\\AppSuite\\Client**.</span></span>

-   **<span data-ttu-id="8018f-145">在安裝階段中設定並測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="8018f-145">Configure and test the application during the installation phase.</span></span>**

    <span data-ttu-id="8018f-146">完成應用程式的安裝通常需要執行幾個手動步驟，這些步驟不是應用程式安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="8018f-146">Completing the installation of an application often requires performing several manual steps that are not part of the application installation process.</span></span> <span data-ttu-id="8018f-147">這些步驟可涉及設定資料庫連線，或複製更新的檔案。</span><span class="sxs-lookup"><span data-stu-id="8018f-147">These steps can involve configuring a connection to a database or copying updated files.</span></span> <span data-ttu-id="8018f-148">您應該在安裝階段執行這些設定，然後執行應用程式，以確定它能正常運作。</span><span class="sxs-lookup"><span data-stu-id="8018f-148">You should perform these configurations during the installation phase and then run the application to make sure it works.</span></span>

-   **<span data-ttu-id="8018f-149">如有需要，請多次執行應用程式，直到程式穩定為止。</span><span class="sxs-lookup"><span data-stu-id="8018f-149">Run the application, multiple times if necessary, until the program is stable.</span></span>**

    <span data-ttu-id="8018f-150">在安裝期間，您應該多次執行應用程式，以確保所有相關聯的註冊與對話方塊設定都已完成。</span><span class="sxs-lookup"><span data-stu-id="8018f-150">You should run the application multiple times during the installation to ensure all associated registration and dialog box configurations have been completed.</span></span> <span data-ttu-id="8018f-151">在安裝期間多次開啟應用程式將會確保只會在**主要功能區塊**中載入相關的應用程式功能。</span><span class="sxs-lookup"><span data-stu-id="8018f-151">Opening the application multiple times during installation will ensure that only the relevant application features are loaded into the **primary feature block**.</span></span>

-   **<span data-ttu-id="8018f-152">停用與應用程式相關聯的所有自動更新功能。</span><span class="sxs-lookup"><span data-stu-id="8018f-152">Disable all automatic update features associated with the application.</span></span>**

    <span data-ttu-id="8018f-153">某些應用程式能夠在安裝期間自動檢查最新的更新。</span><span class="sxs-lookup"><span data-stu-id="8018f-153">Some applications have the ability to check for the latest updates automatically during installation.</span></span> <span data-ttu-id="8018f-154">若要協助虛擬化應用程式套件的版本設定，您應該在進行排序期間停用此功能。</span><span class="sxs-lookup"><span data-stu-id="8018f-154">To assist with versioning of virtual application packages, you should disable this feature during sequencing.</span></span> <span data-ttu-id="8018f-155">如果有必要的更新，您應該為新的虛擬應用程式套件排序，並安裝相關的更新。</span><span class="sxs-lookup"><span data-stu-id="8018f-155">If there are required updates, you should sequence a new virtual application package with the associated updates installed.</span></span>

## <span data-ttu-id="8018f-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="8018f-156">Related topics</span></span>


[<span data-ttu-id="8018f-157">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="8018f-157">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





