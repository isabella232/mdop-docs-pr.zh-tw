---
title: Application Virtualization Sequencer 主控台概觀
description: Application Virtualization Sequencer 主控台概觀
author: dansimp
ms.assetid: 681bb40d-2937-4645-82aa-4a44775232d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2f977fccaaded0309181a1d74c16b749498abb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809207"
---
# <span data-ttu-id="2fcf3-103">Application Virtualization Sequencer 主控台概觀</span><span class="sxs-lookup"><span data-stu-id="2fcf3-103">Application Virtualization Sequencer Console Overview</span></span>


<span data-ttu-id="2fcf3-104">應用程式虛擬化（App-v） Sequencer 會建立應用程式，讓它們可以在虛擬環境中執行，就像虛擬應用程式一樣。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-104">The Application Virtualization (App-V) Sequencer creates applications so that they can be run in a virtual environment, as virtual applications.</span></span> <span data-ttu-id="2fcf3-105">當應用程式已排序之後，就可以從應用程式 V 伺服器執行，以使用稱為「流式處理」的程式，從 App V 伺服器執行，以進行遠端桌面服務（先前稱為「終端服務）」的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-105">After an application has been sequenced, it can run from an App-V Server to target computers that are running the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using a process called streaming.</span></span> <span data-ttu-id="2fcf3-106">App-v 排序器會監視應用程式的安裝與設定程式，並記錄應用程式在虛擬環境中執行的所有必要資訊。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-106">The App-V Sequencer monitors the installation and setup process for applications, and it records all the information necessary for the application to run in the virtual environment.</span></span> <span data-ttu-id="2fcf3-107">這個程式也會判斷哪些檔案和設定適用于所有使用者，以及使用者可以自訂哪些設定。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-107">This process also determines which files and configurations are applicable to all users and which configurations users can customize.</span></span> <span data-ttu-id="2fcf3-108">虛擬應用程式是在目的電腦上執行，在目的電腦上執行的作業系統或目的電腦上安裝的任何應用程式上，都不會產生任何作用。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-108">Virtual applications run on target computers and have no effect on the operating system running on the target computer or on any applications that are installed on the target computer.</span></span>

## <span data-ttu-id="2fcf3-109">應用程式虛擬化 Sequencer 的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="2fcf3-109">Application Virtualization Sequencer Security Considerations</span></span>


<span data-ttu-id="2fcf3-110">App-v 排序器會執行使用本機系統帳戶在先後順序時間檢測到的所有服務，但不會在服務控制要求上強制執行安全性描述項。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-110">The App-V Sequencer runs all services detected at sequencing time using the Local System account and does not enforce security descriptors on service control requests.</span></span> <span data-ttu-id="2fcf3-111">如果服務是使用不同的使用者帳戶安裝，或者如果安全描述項是要授與使用者群組特定的服務許可權，請仔細考慮是否應該將服務虛擬化。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-111">If the service was installed using a different user account or if the security descriptors are intended to grant different user groups specific service permissions, consider carefully whether the service should be virtualized.</span></span> <span data-ttu-id="2fcf3-112">在某些情況下，您應該在本機安裝該服務，以確保所需的服務安全性得以保留。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-112">In some cases, you should install the service locally to ensure that the intended service security is preserved.</span></span>

## <span data-ttu-id="2fcf3-113">應用程式虛擬化排序器主控台功能表選項</span><span class="sxs-lookup"><span data-stu-id="2fcf3-113">Application Virtualization Sequencer Console Menu Options</span></span>


<span data-ttu-id="2fcf3-114">App-v 排序器主控台提供下列功能表項目：</span><span class="sxs-lookup"><span data-stu-id="2fcf3-114">The following menu items are available in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="2fcf3-115">[檔案 **]：包含各種命令，可**協助您建立、開啟、修改及儲存已排序的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-115">**File**—Contains various commands to help create, open, modify, and save sequenced applications.</span></span>

-   <span data-ttu-id="2fcf3-116">[**編輯**]：包含各種編輯現有虛擬應用程式的命令。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-116">**Edit**—Contains various commands for editing existing virtual applications.</span></span>

-   <span data-ttu-id="2fcf3-117">[**視圖**]：包含各種命令，可用於查看虛擬應用程式的屬性。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-117">**View**—Contains various commands for viewing properties of a virtual application.</span></span>

-   <span data-ttu-id="2fcf3-118">**工具**-包含各種工具和診斷功能，可用於設定虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-118">**Tools**—Contains various tools and diagnostics for configuring virtual applications.</span></span>

## <span data-ttu-id="2fcf3-119">應用程式虛擬化排序器主控台工具列選項</span><span class="sxs-lookup"><span data-stu-id="2fcf3-119">Application Virtualization Sequencer Console Toolbar Options</span></span>


<span data-ttu-id="2fcf3-120">App-v 排序器主控台提供下列工具列按鈕：</span><span class="sxs-lookup"><span data-stu-id="2fcf3-120">The following toolbar buttons are available in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="2fcf3-121">**新套件**-按一下以建立新的已排序的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-121">**New Package**—Click to create a new sequenced application.</span></span>

-   <span data-ttu-id="2fcf3-122">**開啟**—按一下以開啟 app-v 排序器主機中的順序式應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-122">**Open**—Click to open a sequenced application package in the App-V Sequencer Console.</span></span>

-   <span data-ttu-id="2fcf3-123">**開啟以供升級**：按一下以開啟已排序的應用程式以進行升級或套用更新。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-123">**Open for Upgrade**—Click to open a sequenced application to upgrade or apply an update.</span></span>

-   <span data-ttu-id="2fcf3-124">**儲存**：按一下以儲存已排序的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-124">**Save**—Click to save a sequenced virtual application.</span></span>

-   <span data-ttu-id="2fcf3-125">**順序嚮導**-按一下以開啟 [順序] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-125">**Sequencing Wizard**—Click to open the Sequencing Wizard.</span></span> <span data-ttu-id="2fcf3-126">如果您在 [**工具**選項] 底下的 **[一般**] 索引標籤上進行任何變更，就應該使用這個按鈕來啟動 [順序] 嚮導  /  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-126">You should use this button to start the Sequencing Wizard if you make any changes on the **General** tab under **Tools** / **Options**.</span></span>

## <span data-ttu-id="2fcf3-127">虛擬應用程式索引標籤</span><span class="sxs-lookup"><span data-stu-id="2fcf3-127">Virtual Application Tabs</span></span>


<span data-ttu-id="2fcf3-128">當您在 App-v 排序器主控台中查看虛擬應用程式時，會顯示下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="2fcf3-128">The following tabs are displayed when you view a virtual application in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="2fcf3-129">[**屬性**]-顯示所選虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-129">**Properties**—Displays information about the selected virtual application.</span></span> <span data-ttu-id="2fcf3-130">您可以更新與虛擬應用程式相關聯的**套件名稱**和**批註**。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-130">You can update the **Package Name** and **Comments** associated with the virtual application.</span></span>

-   <span data-ttu-id="2fcf3-131">**部署**-顯示目的電腦將如何存取虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-131">**Deployment**—Displays information about how the virtual application will be accessed by target computers.</span></span> <span data-ttu-id="2fcf3-132">您可以設定虛擬應用程式傳遞方法，而且您可以設定哪些作業系統必須在目的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-132">You can configure the virtual application delivery method, and you can configure which operating systems must be running on the target computer.</span></span> <span data-ttu-id="2fcf3-133">您也可以設定相關聯的輸出選項。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-133">You can also configure the associated output options.</span></span> <span data-ttu-id="2fcf3-134">如果您打算讓用戶端從檔案存取虛擬應用程式，請在指定 path： **File://server/share/path/.sft**時使用下列格式。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-134">If you plan to have clients access a virtual application from a file, use the following format when specifying the path: **File://server/share/path/.sft**.</span></span> <span data-ttu-id="2fcf3-135">選取 [**強制安全性描述項**]，以保留升級期間與套件相關聯的安全性，或在升級期間重設許可權。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-135">Select **Enforce Security Descriptors** to preserve security associated with the package during an upgrade, or the permissions will be reset during the upgrade.</span></span>

-   <span data-ttu-id="2fcf3-136">**變更記錄**-顯示已對虛擬應用程式所做的更新資訊。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-136">**Change History**—Displays information about updates that have been made to the virtual application.</span></span>

-   <span data-ttu-id="2fcf3-137">[檔案 **] —顯示**與所選虛擬應用程式相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-137">**Files**—Displays the files associated with the selected virtual application.</span></span> <span data-ttu-id="2fcf3-138">您可以使用適當的欄位，對相關聯的檔案屬性進行微小的修訂。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-138">You can make minor revisions to the associated file properties by using the appropriate fields.</span></span>

-   <span data-ttu-id="2fcf3-139">[**虛擬**機]：顯示與所選虛擬應用程式相關聯的虛擬機器碼。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-139">**Virtual Registry**—Displays the virtual registry associated with the selected virtual application.</span></span> <span data-ttu-id="2fcf3-140">您可以在適當的專案上按一下滑鼠右鍵，以新增或刪除登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-140">You can add or delete registry keys by right-clicking the appropriate entry.</span></span>

-   <span data-ttu-id="2fcf3-141">**虛擬檔案系統**-顯示與所選虛擬應用程式相關聯的虛擬檔案系統。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-141">**Virtual File System**—Displays the virtual file systems associated with the selected virtual application.</span></span> <span data-ttu-id="2fcf3-142">您可以在此索引標籤上，以滑鼠右鍵按一下適當的專案，然後選取該選項，即可新增、刪除或編輯檔案系統專案。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-142">You can add, delete, or edit file system entries on this tab by right-clicking the appropriate entry and selecting the option.</span></span>

-   <span data-ttu-id="2fcf3-143">[**虛擬服務**]-顯示與所選虛擬應用程式相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-143">**Virtual Services**—Displays the services associated with the selected virtual application.</span></span>

-   <span data-ttu-id="2fcf3-144">**OSD**-顯示與虛擬應用程式相關聯之開放式軟體描述項（OSD）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-144">**OSD**—Displays information about the Open Software Descriptor (OSD) associated with the virtual application.</span></span> <span data-ttu-id="2fcf3-145">您可以在適當的專案上按一下滑鼠右鍵，然後選取您想要的動作，來更新與 OSD 檔案相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="2fcf3-145">You can update the files associated with the OSD file by right-clicking the appropriate entry and selecting the action that you want.</span></span>

## <span data-ttu-id="2fcf3-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="2fcf3-146">Related topics</span></span>


[<span data-ttu-id="2fcf3-147">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2fcf3-147">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





