---
title: UE-V 1.0 的高階架構
description: UE-V 1.0 的高階架構
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812152"
---
# <span data-ttu-id="7f329-103">UE-V 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="7f329-103">High-Level Architecture for UE-V 1.0</span></span>


<span data-ttu-id="7f329-104">本主題描述 Microsoft 使用者體驗虛擬化（UE-V）設定漫遊解決方案的高層次結構元素。</span><span class="sxs-lookup"><span data-stu-id="7f329-104">This topic describes high-level architectural elements of the Microsoft User Experience Virtualization (UE-V) settings roaming solution.</span></span> <span data-ttu-id="7f329-105">下列元素是標準 UE-V 部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f329-105">The following elements are part of a standard UE-V deployment.</span></span>

![ue-v agent 結構圖表](images/ue-vagentarchitecturaldiagram.gif)

<span data-ttu-id="7f329-107">UE-V Agent 會監視應用程式及作業系統進程，因為它們是在 UE-V 設定位置範本中識別。</span><span class="sxs-lookup"><span data-stu-id="7f329-107">The UE-V Agent monitors the applications and the operating system processes as they are identified in the UE-V settings location templates.</span></span> <span data-ttu-id="7f329-108">當應用程式或作業系統啟動時，會從 [設定] 套件讀取設定，並將其套用到電腦。</span><span class="sxs-lookup"><span data-stu-id="7f329-108">When the application or operating system starts, the settings are read from the settings package and applied to the computer.</span></span> <span data-ttu-id="7f329-109">當應用程式關閉或作業系統鎖定或關閉時，設定就會儲存在 [設定] 儲存位置中的 UE-V 設定套件中。</span><span class="sxs-lookup"><span data-stu-id="7f329-109">When the application closes or when the operating system is locked or shut down, settings are saved in a UE-V settings package in the settings storage location.</span></span>

## <span data-ttu-id="7f329-110">設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="7f329-110">Settings storage location</span></span>


<span data-ttu-id="7f329-111">[設定儲存位置] 是使用者體驗虛擬化代理程式存取來讀取和寫入設定的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="7f329-111">The settings storage location is a file share that the User Experience Virtualization agent accesses to read and write settings.</span></span> <span data-ttu-id="7f329-112">這個位置是 Active Directory 主目錄，或在 UE-V 安裝期間定義。</span><span class="sxs-lookup"><span data-stu-id="7f329-112">This location is either the Active Directory home directory or defined during the UE-V installation.</span></span> <span data-ttu-id="7f329-113">您可以在安裝 UE-V agent 期間設定位置，或者您可以在稍後使用 [群組原則]、[WMI] 或 [PowerShell] 進行設定。</span><span class="sxs-lookup"><span data-stu-id="7f329-113">You can set the location during the installation of the UE-V agent, or you can set it later with Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="7f329-114">位置可以是使用者可以存取的任何常見檔案共用。</span><span class="sxs-lookup"><span data-stu-id="7f329-114">The location can be on any common file share that users can access.</span></span> <span data-ttu-id="7f329-115">如果在安裝期間未設定儲存位置，則 UE-V 會使用 Active Directory 中的主目錄。</span><span class="sxs-lookup"><span data-stu-id="7f329-115">If no setting storage location is set during installation then UE-V will use the home directory in Active Directory.</span></span> <span data-ttu-id="7f329-116">UE-V agent 會驗證位置，並建立要儲存及存取使用者設定的使用者所隱藏的系統資料夾。</span><span class="sxs-lookup"><span data-stu-id="7f329-116">The UE-V agent verifies the location and creates a system folder that is hidden from the user in which to store and access the user settings.</span></span> <span data-ttu-id="7f329-117">如需設定儲存空間的詳細資訊，請參閱為[Ue-v 準備您的環境](preparing-your-environment-for-ue-v.md)。</span><span class="sxs-lookup"><span data-stu-id="7f329-117">For more information about settings storage, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <span data-ttu-id="7f329-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="7f329-118">UE-V Agent</span></span>


<span data-ttu-id="7f329-119">UE-V agent 是在每一台電腦上安裝，其設定是由使用者體驗虛擬化所同步處理。</span><span class="sxs-lookup"><span data-stu-id="7f329-119">The UE-V agent is installed on each computer with settings that are synchronized by User Experience Virtualization.</span></span> <span data-ttu-id="7f329-120">Agent 會監視已註冊的應用程式與作業系統，以瞭解對設定所做的任何變更，並在電腦之間同步處理這些設定。</span><span class="sxs-lookup"><span data-stu-id="7f329-120">The agent monitors the registered applications and the operating system for any changes to that are made to settings, and it synchronizes those settings between computers.</span></span> <span data-ttu-id="7f329-121">當應用程式啟動時，設定會從 [設定] 儲存位置套用到應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f329-121">Settings are applied from the settings storage location to the application when the application is started.</span></span> <span data-ttu-id="7f329-122">然後，在應用程式關閉時，這些設定會儲存回 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-122">The settings are then saved back to the settings storage location when the application closes.</span></span> <span data-ttu-id="7f329-123">當使用者登入時、電腦已解除鎖定，或當使用者使用遠端桌面通訊協定（RDP）連線到電腦時，就會套用作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="7f329-123">The operating system settings are applied when the user logs on, when the computer is unlocked, or when the user connects remotely to the computer by using remote desktop protocol (RDP).</span></span> <span data-ttu-id="7f329-124">當使用者登出、電腦被鎖定時，或當遠端連線中斷時，agent 會儲存設定。</span><span class="sxs-lookup"><span data-stu-id="7f329-124">The agent saves settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="7f329-125">如需 UE-V Agent 的詳細資訊，請參閱為[Ue-v 準備您的環境](preparing-your-environment-for-ue-v.md)。</span><span class="sxs-lookup"><span data-stu-id="7f329-125">For more information about the UE-V Agent, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <a href="" id="bkmk-settingslocationtemplate"></a><span data-ttu-id="7f329-126">設定位置範本</span><span class="sxs-lookup"><span data-stu-id="7f329-126">Settings location templates</span></span>


<span data-ttu-id="7f329-127">[設定位置] 範本是一個 XML 檔案，可定義使用者體驗虛擬化所監視的設定位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-127">The settings location template is an XML file that defines the settings locations to be monitored by User Experience Virtualization.</span></span> <span data-ttu-id="7f329-128">只有在這些設定範本中定義的設定位置，才會在執行 UE-V Agent 的電腦上捕獲或套用。</span><span class="sxs-lookup"><span data-stu-id="7f329-128">Only the settings locations defined in these settings templates are captured or applied on computers running the UE-V Agent.</span></span> <span data-ttu-id="7f329-129">[設定位置] 範本不包含設定值，只能包含值儲存在電腦上的位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-129">The settings location template does not contain settings values, only the locations where values are stored on the computer.</span></span>

<span data-ttu-id="7f329-130">UE-V 包含一組設定位置範本，這些範本指定一些 Microsoft 應用程式和 Windows 設定的設定位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-130">UE-V includes a set of settings location templates that specify settings locations for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="7f329-131">系統管理員可以使用 UE-V 發生器來建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="7f329-131">An administrator can create custom settings location templates by using the UE-V Generator.</span></span>

[<span data-ttu-id="7f329-132">規劃要與 UE-V 1.0 同步處理的應用程式</span><span class="sxs-lookup"><span data-stu-id="7f329-132">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="7f329-133">規劃 UE-V 1.0 的自訂範本部署</span><span class="sxs-lookup"><span data-stu-id="7f329-133">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="7f329-134">使用自訂 UE-V 範本與 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="7f329-134">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <span data-ttu-id="7f329-135">設定套件</span><span class="sxs-lookup"><span data-stu-id="7f329-135">Settings packages</span></span>


<span data-ttu-id="7f329-136">[應用程式設定] 和 [Windows 設定] 儲存在由 UE-V Agent 建立的 [設定套件] 中。</span><span class="sxs-lookup"><span data-stu-id="7f329-136">Application settings and Windows settings are stored in settings packages, which are created by the UE-V Agent.</span></span> <span data-ttu-id="7f329-137">[設定套件] 是 [設定位置] 範本中所代表的設定集合。</span><span class="sxs-lookup"><span data-stu-id="7f329-137">A settings package is a collection of the settings that are represented in the settings location templates.</span></span> <span data-ttu-id="7f329-138">這些設定套件會建立並儲存在本機，然後複製到 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-138">These settings packages are built, locally stored, and then copied to the settings storage location.</span></span> <span data-ttu-id="7f329-139">「上次寫入 wins」決定當單一使用者將多台電腦同步處理到儲存位置時，會保留哪些設定。</span><span class="sxs-lookup"><span data-stu-id="7f329-139">“Last write wins” determines which settings are preserved when a single user synchronizes the more than one computer to a storage location.</span></span> <span data-ttu-id="7f329-140">在一部電腦上執行的代理程式會讀取並寫入到 [設定] 位置，而不受在其他電腦上執行的代理程式。</span><span class="sxs-lookup"><span data-stu-id="7f329-140">The agent that runs on one computer reads and writes to the settings location independent of agents that run on other computers.</span></span> <span data-ttu-id="7f329-141">下次代理從設定儲存位置讀取時，就會套用最近寫入的設定和值。</span><span class="sxs-lookup"><span data-stu-id="7f329-141">The most recently written settings and values are applied when the next agent reads from the settings storage location.</span></span>

![ue-v 發生器程式](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="7f329-143">設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="7f329-143">Settings template catalog</span></span>


<span data-ttu-id="7f329-144">[設定範本目錄] 是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="7f329-144">The settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="7f329-145">UE-V agent 會從這個位置中檢索新的或更新的範本。</span><span class="sxs-lookup"><span data-stu-id="7f329-145">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="7f329-146">UE-V agent 每天都會檢查這個位置，然後根據此資料夾中的範本，更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="7f329-146">The UE-V agent checks this location once each day and it updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="7f329-147">在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。</span><span class="sxs-lookup"><span data-stu-id="7f329-147">The templates that were added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="7f329-148">UE-V agent 會 deregisters 從這個資料夾移除的範本。</span><span class="sxs-lookup"><span data-stu-id="7f329-148">The UE-V agent deregisters the templates that were removed from this folder.</span></span> <span data-ttu-id="7f329-149">範本是由任務排程器每日登錄並取消註冊一次。</span><span class="sxs-lookup"><span data-stu-id="7f329-149">Templates are registered and unregistered one time per day by the task scheduler.</span></span> <span data-ttu-id="7f329-150">如果您只會使用 UE-V 隨附的預設設定位置範本，則不需要設定範本目錄。</span><span class="sxs-lookup"><span data-stu-id="7f329-150">If you will use only the default settings location templates that are included with UE-V, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="7f329-151">如需設定部署目錄的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="7f329-151">For more information about settings deployment catalogs, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

## <span data-ttu-id="7f329-152">使用者體驗虛擬化發生器</span><span class="sxs-lookup"><span data-stu-id="7f329-152">User Experience Virtualization Generator</span></span>


<span data-ttu-id="7f329-153">使用者體驗虛擬化發生器可讓您建立自訂設定位置範本，這些範本會儲存在企業中使用且您想要包含在漫遊設定方案中之應用程式的設定位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-153">The User Experience Virtualization Generator enables you to create custom settings location templates which will store the settings locations of the applications that are used in the enterprise and that you want to include in the roaming settings solution.</span></span> <span data-ttu-id="7f329-154">UE-V 發生器將搜尋以探索登錄的位置和應用程式的設定檔案，然後將這些位置記錄在設定位置範本 XML 檔案中。</span><span class="sxs-lookup"><span data-stu-id="7f329-154">The UE-V Generator will seek to discover the locations of registry values and the settings files for applications and then it will record those locations in a settings location template XML file.</span></span> <span data-ttu-id="7f329-155">然後，您可以將這些設定位置範本發佈到使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="7f329-155">You can then distribute these settings location templates to the user computers.</span></span> <span data-ttu-id="7f329-156">UE-V 發生器也可讓系統管理員編輯現有的範本，或驗證與其他 XML 編輯器建立的範本。</span><span class="sxs-lookup"><span data-stu-id="7f329-156">The UE-V Generator also allows an administrator to edit an existing template or validate a template that was created with another XML editor.</span></span>

<span data-ttu-id="7f329-157">UE-V 發生器會監視應用程式，以探索並記錄儲存其設定的位置。</span><span class="sxs-lookup"><span data-stu-id="7f329-157">The UE-V Generator monitors an application to discover and record where it stores its settings.</span></span> <span data-ttu-id="7f329-158">若要這麼做，它會監視應用程式在 HKEY \ _CURRENT \ _USER 登錄或在 [**使用者**\\] 下的檔案資料夾中讀取或寫入的位置 \ \ [使用者 \] [使用者名稱 \] \] **AppData**  \\  **漫遊，以及使用者**\\ [user name \\] **AppData**  \\  **Local**。</span><span class="sxs-lookup"><span data-stu-id="7f329-158">To do this, it monitors where the application reads or writes in the HKEY\_CURRENT\_USER registry or in the file folders under **Users** \\ \[User name\] \\ **AppData** \\ **Roaming and Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span>

<span data-ttu-id="7f329-159">探索程式會排除登入使用者無法寫入值的登錄機碼和檔案。</span><span class="sxs-lookup"><span data-stu-id="7f329-159">The discovery process excludes registry keys and files to which the logged-in user cannot write values.</span></span> <span data-ttu-id="7f329-160">這些內容不會包含在 XML 檔案中。</span><span class="sxs-lookup"><span data-stu-id="7f329-160">None of these will be included in the XML file.</span></span> <span data-ttu-id="7f329-161">探索程式也會排除與 Windows 作業系統核心功能相關聯的登錄機碼和檔案。</span><span class="sxs-lookup"><span data-stu-id="7f329-161">The discovery process also excludes registry keys and files that are associated with the core functionality of the Windows operating system.</span></span>

<span data-ttu-id="7f329-162">如需 UE-V 發生器的詳細資訊，請參閱[安裝 Ue-v 發生器](installing-the-ue-v-generator.md)。</span><span class="sxs-lookup"><span data-stu-id="7f329-162">For more information about the UE-V Generator, see [Installing the UE-V Generator](installing-the-ue-v-generator.md).</span></span>

## <span data-ttu-id="7f329-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f329-163">Related topics</span></span>


[<span data-ttu-id="7f329-164">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="7f329-164">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="7f329-165">開始使用 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="7f329-165">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="7f329-166">關於 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="7f329-166">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

[<span data-ttu-id="7f329-167">使用自訂 UE-V 範本與 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="7f329-167">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





