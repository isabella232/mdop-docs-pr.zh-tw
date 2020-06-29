---
title: App-V 5.0 SP1 的新功能
description: App-V 5.0 SP1 的新功能
author: dansimp
ms.assetid: e97c2dbb-7b40-46a0-8137-9ee4fc2bd071
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2542d0cc5a544d26b3279b24063cf3ef428b9f39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800288"
---
# <span data-ttu-id="5339d-103">App-V 5.0 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="5339d-103">What's new in App-V 5.0 SP1</span></span>


<span data-ttu-id="5339d-104">本節適用于已熟悉 App V 的使用者，並且想要知道 App-v 5.0 SP1 中有哪些變更。</span><span class="sxs-lookup"><span data-stu-id="5339d-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 SP1.</span></span> <span data-ttu-id="5339d-105">如果您還不熟悉 App V，您應該首先閱讀[app-v 5.0 的規劃](planning-for-app-v-50-rc.md)。</span><span class="sxs-lookup"><span data-stu-id="5339d-105">If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="5339d-106">標準功能的變更</span><span class="sxs-lookup"><span data-stu-id="5339d-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="5339d-107">下列各節包含 App-v 5.0 SP1 之標準功能變更的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5339d-107">The following sections contain information about the changes in standard functionality for App-V 5.0 SP1.</span></span>

### <span data-ttu-id="5339d-108">支援的語言變更</span><span class="sxs-lookup"><span data-stu-id="5339d-108">Changes to Supported Languages</span></span>

<span data-ttu-id="5339d-109">如需詳細資訊，請參閱[關於 App-V 5.0 SP1](about-app-v-50-sp1.md)。</span><span class="sxs-lookup"><span data-stu-id="5339d-109">For more information, see [About App-V 5.0 SP1](about-app-v-50-sp1.md).</span></span>

<span data-ttu-id="5339d-110">下列清單包含新語言套件的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="5339d-110">The following list contains more information about the new Language Packs:</span></span>

-   <span data-ttu-id="5339d-111">App-v 5.0 SP1 語言套件會捆綁到適用于所有 App-v 5.0 元件的**appv\_xxx\_setup.exe**安裝程式中。</span><span class="sxs-lookup"><span data-stu-id="5339d-111">The App-V 5.0SP1 language packs are bundled into the **appv\_xxx\_setup.exe** installer for all the App-V 5.0 Components.</span></span>

-   <span data-ttu-id="5339d-112">當您執行安裝程式時，系統會根據在目的電腦上執行的相關作業系統的地區設定，自動安裝最適合的語言套件。</span><span class="sxs-lookup"><span data-stu-id="5339d-112">When you run the installer it will automatically install the most appropriate language pack based on the locale of the associated operating system running on the target computer.</span></span>

-   <span data-ttu-id="5339d-113">如果需要其他語言套件，您必須執行下列命令，以從安裝程式解壓縮這些語言套件： `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”` 。</span><span class="sxs-lookup"><span data-stu-id="5339d-113">If additional language packs are required, you must extract these language packs from the installer by running the following command: `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”`.</span></span> <span data-ttu-id="5339d-114">在執行這項工作之後，安裝程式的內容會解壓縮到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="5339d-114">After this has been run, the contents of the installer are extracted to the specified location.</span></span>

-   <span data-ttu-id="5339d-115">您必須套用適當的語言套件 Windows 安裝檔案，才能安裝所需的語言套件。</span><span class="sxs-lookup"><span data-stu-id="5339d-115">You must install the desired language pack by applying the appropriate Language pack Windows Installation file.</span></span> <span data-ttu-id="5339d-116">例如， **appv\_hib\_LP\_jmmb\_x86.msi**或**appv\_hib\_LP\_jmmb\_x64.msi**，其中**hib**會參照元件，而**jmmb**參照區域設定。</span><span class="sxs-lookup"><span data-stu-id="5339d-116">For example, **appv\_hib\_LP\_jmmb\_x86.msi** or **appv\_hib\_LP\_jmmb\_x64.msi**, where **hib** refers to the component and **jmmb** refers to the locale.</span></span>

## <span data-ttu-id="5339d-117">Microsoft Office2010 的增強支援</span><span class="sxs-lookup"><span data-stu-id="5339d-117">Enhanced Support for Microsoft Office2010</span></span>


<span data-ttu-id="5339d-118">**應用程式虛擬化5.0 的 Microsoft Office 2010 排序套件**-可協助讓使用者使用虛擬化版本的 Microsoft Office2010 提供一致的體驗。</span><span class="sxs-lookup"><span data-stu-id="5339d-118">**Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** – helps provide users with a consistent experience using a virtualized version of Microsoft Office2010.</span></span> <span data-ttu-id="5339d-119">**應用程式虛擬化5.0 的 Microsoft office 2010 排序套件**是與適用于**App-v 的 Microsoft Office 2010 部署套件**搭配使用，同時也提供必要的 Microsoft Office2010 授權服務。</span><span class="sxs-lookup"><span data-stu-id="5339d-119">The **Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** is used in conjunction with the **Microsoft Office 2010 Deployment Kit for App-V** and also provides the required Microsoft Office2010 licensing service.</span></span>






## <span data-ttu-id="5339d-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="5339d-120">Related topics</span></span>


[<span data-ttu-id="5339d-121">關於 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="5339d-121">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





