---
title: 如何使用差異 SFT 檔案
description: 如何使用差異 SFT 檔案
author: dansimp
ms.assetid: 607e30fd-2f0e-4e2f-b669-0b3f010aebb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 85cc45f9665569d77fcf275db6dbc080eb919229
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801009"
---
# <span data-ttu-id="ec4cc-103">如何使用差異 SFT 檔案</span><span class="sxs-lookup"><span data-stu-id="ec4cc-103">How to Use the Differential SFT File</span></span>


<span data-ttu-id="ec4cc-104">當您將應用程式排序時，Microsoft Application Virtualization （App-v） Sequencer 會建立 SFT 檔案（SFT），以儲存虛擬應用程式的所有檔案內容和配置資訊。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-104">When sequencing an application, the Microsoft Application Virtualization (App-V) Sequencer creates SFT files (.sft) to store all of the virtual application’s files content and configuration information.</span></span> <span data-ttu-id="ec4cc-105">在 App-v 的4.5 版本中，引入了差異 SFT （dsft）檔案。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-105">In version4.5 of App-V, the Differential SFT (.dsft) file has been introduced.</span></span> <span data-ttu-id="ec4cc-106">使用 Sequencer 建立現有套件的升級之後，您可以選擇產生此檔案，只儲存原始已排序的應用程式套件與新版本之間的差異。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-106">After using the Sequencer to create an upgrade for an existing package, you can choose to generate this file to store only the differences between the original sequenced application package and the new version.</span></span> <span data-ttu-id="ec4cc-107">因此，它比完整的 SFT 檔案要小得多，就是針對新版本的應用程式，並減少在低頻寬網路連線中傳送套件更新的影響。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-107">It is therefore much smaller than the full SFT file would be for the new version of the application and reduces the impact of sending package updates over low-bandwidth network connections.</span></span> <span data-ttu-id="ec4cc-108">不過，只有在某些受限制的情況下，才支援使用。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-108">However, its use is supported only in certain restricted situations.</span></span> <span data-ttu-id="ec4cc-109">此功能是專門用來在您使用電子軟體發佈（ESD）系統管理一組使用者，並在低頻寬連線中使用本機檔案伺服器來管理使用者，而不是使用 App-v 流式處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-109">This feature was intended to be used specifically where you are using an electronic software distribution (ESD) system to manage a group of users with a local file server over a low-bandwidth connection and you are not using App-V streaming servers.</span></span>

<span data-ttu-id="ec4cc-110">如果您使用的是 [配置 Manager2007] 來管理使用者，則不需要使用差異 SFT 檔案，因為 Configuration Manager 支援已內建的低頻寬部署。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-110">You do not need to use the Differential SFT file if you are using Configuration Manager2007 to manage the users, because Configuration Manager has support for low-bandwidth deployments already built in.</span></span> <span data-ttu-id="ec4cc-111">如果您使用的是應用程式虛擬化（App-v）管理或流式伺服器（含作用中升級），則也不需要它，因為用戶端只會檢索舊版本與新套件版本之間的差異。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-111">It is also not required if you are using Application Virtualization (App-V) Management or Streaming Servers with Active Upgrade because the client will retrieve only the differences between the old and new package versions.</span></span>

<span data-ttu-id="ec4cc-112">下列程式說明如何使用 Sequencer 安裝中包含的 mkdiffpkg.exe 來建立差異 SFT 檔案、完成虛擬應用程式套件升級之後，以及部署差異 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-112">The following procedure shows how to use the mkdiffpkg.exe that is included in the Sequencer installation to create the Differential SFT file, after completing the upgrade of the virtual application package, and to deploy the Differential SFT file.</span></span> <span data-ttu-id="ec4cc-113">完成這個程式有助於確保如果套件是以某種方式從用戶端電腦上卸載，則在使用者下次嘗試執行該應用程式時，用戶端會回到覆寫 URL，該 URL 已設定為從本機檔案共用中傳送完整套件 V2。 sft。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-113">Completing this procedure helps ensure that if the package is somehow unloaded from the client computer, the next time the user tries to run the application, the client will fall back to the override URL, which is set to stream the full package V2.sft from the local file share.</span></span> <span data-ttu-id="ec4cc-114">這將避免啟動應用程式時的使用者任何失敗。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-114">This will avoid any failure for the user when starting the application.</span></span> <span data-ttu-id="ec4cc-115">如果整個用戶端遭到損毀或卸載，建議將 ESD 系統設定為將升級套件的完整版本（V2）部署到用戶端。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-115">If the entire client becomes corrupted or is uninstalled, it is recommended that the ESD system be configured to deploy the full version of the upgraded package, V2.sft, to the client.</span></span>

<span data-ttu-id="ec4cc-116">如需升級套件的詳細資訊，請參閱 App-V 4.5 操作指南中的「如何升級現有的虛擬應用程式」</span><span class="sxs-lookup"><span data-stu-id="ec4cc-116">For more information about upgrading a package, see “How to Upgrade an Existing Virtual Application” in the App-V4.5 Operations Guide at</span></span> <https://go.microsoft.com/fwlink/?LinkId=133129>

<span data-ttu-id="ec4cc-117">**記事** 作為先決條件，ESD 所針對的所有使用者電腦都必須將 V1 檔案完全載入到其本機快取中，而且必須在所有電腦上啟用檔案資料流程。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-117">**Note** As a prerequisite, all user computers being targeted by the ESD must have the V1.sft file fully loaded into their local cache, and file streaming must be enabled on all computers.</span></span>

 

**<span data-ttu-id="ec4cc-118">使用差異 SFT 檔案</span><span class="sxs-lookup"><span data-stu-id="ec4cc-118">To use the Differential SFT file</span></span>**

1.  <span data-ttu-id="ec4cc-119">使用具有系統管理員許可權的帳戶登入 Sequencer 電腦。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-119">Log on to the Sequencer computer by using an account with administrator rights.</span></span> <span data-ttu-id="ec4cc-120">在 Sequencer 中開啟原始套件（V1）以進行升級，然後將套件升級為新的版本（V2），並將其儲存為新的 V2. sft。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-120">Open the original package (V1) for upgrade in the Sequencer, and then upgrade the package to the new version (V2) and save it as a new V2.sft.</span></span>

2.  <span data-ttu-id="ec4cc-121">在 App-V 4.5 排序器安裝資料夾中開啟命令視窗，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ec4cc-121">Open a command window in the App-V4.5 Sequencer installation folder, and run the following command:</span></span>

    `“mkdiffpkg.exe V2.sft V2.dsft”`

3.  <span data-ttu-id="ec4cc-122">使用 ESD 系統或其他檔案複製程式，將完整的 V2 套件內容檔案（V2）複製到本機檔案共用，以供使用者電腦在連線良好的網路連線時存取。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-122">Using the ESD system or other file copy process, copy the full V2 package content file, V2.sft, to a local file share that is accessible to the user computers on a well-connected network connection.</span></span>

4.  <span data-ttu-id="ec4cc-123">使用 ESD 系統，將差異 SFT 檔案（dsft）的複本放在每個使用者電腦上。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-123">Using the ESD system, place a copy of the Differential SFT file, V2.dsft, on each user computer.</span></span>

5.  <span data-ttu-id="ec4cc-124">若要匯入 dsft 檔案，請在每個使用者電腦上執行下列 SFTMIME 命令：</span><span class="sxs-lookup"><span data-stu-id="ec4cc-124">To import the V2.dsft file, run the following SFTMIME command on each user computer:</span></span>

    `“SFTMIME load package:<package name> /SFTPATH <path to V2.dsft>”`

6.  <span data-ttu-id="ec4cc-125">在每個使用者電腦上執行下列 SFTMIME 命令，以將覆寫 URL 設定為指向 V2 盤案：</span><span class="sxs-lookup"><span data-stu-id="ec4cc-125">Run the following SFTMIME command on each user computer to set the override URL to point to the V2.sft file:</span></span>

    `“SFTMIME configure package:<package name> /OverrideURL FILE://<network path to V2.sft>”`

**<span data-ttu-id="ec4cc-126">注意</span><span class="sxs-lookup"><span data-stu-id="ec4cc-126">Note</span></span>**  
-   <span data-ttu-id="ec4cc-127">差異 SFT 檔案必須按照正確的順序套用到用戶端。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-127">Differential SFT files must be applied to clients in the correct order.</span></span> <span data-ttu-id="ec4cc-128">例如，dsft 必須套用至 V1 應用程式後，才會套用 V3. dsft。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-128">For example, V2.dsft must be applied to a V1 application before V3.dsft is applied.</span></span>

-   <span data-ttu-id="ec4cc-129">Sequencer 中的 [**產生 Microsoft Windows Installer （MSI）] 套件**功能無法與差異 SFT 檔案搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-129">The **Generate Microsoft Windows Installer (MSI) Package** capability in the Sequencer cannot be used with the Differential SFT file.</span></span>

 

## <span data-ttu-id="ec4cc-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec4cc-130">Related topics</span></span>


[<span data-ttu-id="ec4cc-131">如何使用 App-v 排序器建立或升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="ec4cc-131">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





