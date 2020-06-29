---
title: 一般索引標籤
description: 一般索引標籤
author: dansimp
ms.assetid: aeefae39-60cd-4ad4-9575-c07d7e2b1e59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 327635422030b713aeadbc5de0007685b69e1c2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808775"
---
# <span data-ttu-id="6fa07-103">一般索引標籤</span><span class="sxs-lookup"><span data-stu-id="6fa07-103">General Tab</span></span>


<span data-ttu-id="6fa07-104">使用 **[一般**] 索引標籤來設定適用于 Microsoft Application Virtualization （App-v） Sequencer 的選項。</span><span class="sxs-lookup"><span data-stu-id="6fa07-104">Use the **General** tab to configure options for Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<a href="" id="scratch-directory"></a>**<span data-ttu-id="6fa07-105">臨時目錄</span><span class="sxs-lookup"><span data-stu-id="6fa07-105">Scratch Directory</span></span>**  
<span data-ttu-id="6fa07-106">指定排序器在排序期間將會暫時儲存所產生檔案之位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="6fa07-106">Specifies the path to the location where the Sequencer will temporarily save files generated during sequencing.</span></span> <span data-ttu-id="6fa07-107">預設路徑是 C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch。</span><span class="sxs-lookup"><span data-stu-id="6fa07-107">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch.</span></span> <span data-ttu-id="6fa07-108">若要指定新路徑，請按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="6fa07-108">To specify a new path, click **Browse**.</span></span>

<a href="" id="log-directory"></a>**<span data-ttu-id="6fa07-109">記錄目錄</span><span class="sxs-lookup"><span data-stu-id="6fa07-109">Log Directory</span></span>**  
<span data-ttu-id="6fa07-110">指定排序器將儲存記錄檔的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="6fa07-110">Specifies the path to the directory where the Sequencer will save log files.</span></span> <span data-ttu-id="6fa07-111">預設路徑是 C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs。</span><span class="sxs-lookup"><span data-stu-id="6fa07-111">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs.</span></span> <span data-ttu-id="6fa07-112">若要指定新路徑，請按一下 **[流覽]**</span><span class="sxs-lookup"><span data-stu-id="6fa07-112">To specify a new path, click **Browse**</span></span>

<a href="" id="allow-use-of-msi-installer"></a>**<span data-ttu-id="6fa07-113">允許使用 MSI 安裝程式</span><span class="sxs-lookup"><span data-stu-id="6fa07-113">Allow Use of MSI Installer</span></span>**  
<span data-ttu-id="6fa07-114">選取此選項可允許在排序器和應用程式安裝程式之間互動。</span><span class="sxs-lookup"><span data-stu-id="6fa07-114">Select this option to allow interaction between the Sequencer and the application installer.</span></span> <span data-ttu-id="6fa07-115">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="6fa07-115">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-events"></a>**<span data-ttu-id="6fa07-116">允許虛擬化事件</span><span class="sxs-lookup"><span data-stu-id="6fa07-116">Allow Virtualization of Events</span></span>**  
<span data-ttu-id="6fa07-117">選取此選項可讓應用程式的低層作業系統活動在 App-v 桌面用戶端上執行順序式應用程式套件時得以虛擬化。</span><span class="sxs-lookup"><span data-stu-id="6fa07-117">Select this option to allow low-level operating system activities of the application to be virtualized when a sequenced application package is run on App-V Desktop Clients.</span></span> <span data-ttu-id="6fa07-118">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="6fa07-118">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-services"></a>**<span data-ttu-id="6fa07-119">允許虛擬化服務</span><span class="sxs-lookup"><span data-stu-id="6fa07-119">Allow Virtualization of Services</span></span>**  
<span data-ttu-id="6fa07-120">選取這個選項，可在應用程式在 App-v Desktop 用戶端上執行應用程式時，允許應用程式所需的服務得以虛擬化。</span><span class="sxs-lookup"><span data-stu-id="6fa07-120">Select this option to allow services required by the application to be virtualized when the application is run on App-V Desktop Clients.</span></span> <span data-ttu-id="6fa07-121">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="6fa07-121">This option is selected by default.</span></span>

<a href="" id="append-package-version-to-filename"></a>**<span data-ttu-id="6fa07-122">將套件版本附加至檔案名</span><span class="sxs-lookup"><span data-stu-id="6fa07-122">Append Package Version to Filename</span></span>**  
<span data-ttu-id="6fa07-123">選取這個選項，即可將排序後的應用程式套件版本號碼自動附加到檔案名中。</span><span class="sxs-lookup"><span data-stu-id="6fa07-123">Select this option to automatically append the sequenced application package version number to the file name.</span></span> <span data-ttu-id="6fa07-124">預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="6fa07-124">This option is selected by default.</span></span>

<a href="" id="ok"></a>**<span data-ttu-id="6fa07-125">確定</span><span class="sxs-lookup"><span data-stu-id="6fa07-125">OK</span></span>**  
<span data-ttu-id="6fa07-126">儲存變更並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6fa07-126">Saves changes and closes the dialog box.</span></span>

<a href="" id="cancel"></a>**<span data-ttu-id="6fa07-127">取消</span><span class="sxs-lookup"><span data-stu-id="6fa07-127">Cancel</span></span>**  
<span data-ttu-id="6fa07-128">退出對話方塊，但不儲存任何變更。</span><span class="sxs-lookup"><span data-stu-id="6fa07-128">Exits the dialog box without saving any changes.</span></span>

<a href="" id="apply"></a>**<span data-ttu-id="6fa07-129">[套用]</span><span class="sxs-lookup"><span data-stu-id="6fa07-129">Apply</span></span>**  
<span data-ttu-id="6fa07-130">儲存變更並保留在對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="6fa07-130">Saves the changes and remains in the dialog box.</span></span>

## <span data-ttu-id="6fa07-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="6fa07-131">Related topics</span></span>


[<span data-ttu-id="6fa07-132">Application Virtualization Sequencer 選項對話方塊</span><span class="sxs-lookup"><span data-stu-id="6fa07-132">Application Virtualization Sequencer Options Dialog Box</span></span>](application-virtualization-sequencer-options-dialog-box.md)

 

 





