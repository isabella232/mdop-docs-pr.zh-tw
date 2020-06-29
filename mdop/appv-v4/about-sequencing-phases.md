---
title: 關於排序階段
description: 關於排序階段
author: dansimp
ms.assetid: c1cb7b6c-204c-48f2-848c-4bd5a3d5ecb6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e3d1504f0af82f3d21806b38bb4640b6f7ebc45
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802442"
---
# <span data-ttu-id="68fb0-103">關於排序階段</span><span class="sxs-lookup"><span data-stu-id="68fb0-103">About Sequencing Phases</span></span>


<span data-ttu-id="68fb0-104">[順序] 是您使用 Microsoft Application Virtualization （App-v） Sequencer 來建立順序式應用程式套件的處理方式。</span><span class="sxs-lookup"><span data-stu-id="68fb0-104">Sequencing is the process by which you create a sequenced application package by using the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="68fb0-105">在排序期間，Sequencer 會監視及記錄應用程式的所有安裝與設定進程，並建立下列檔案： .ICO、OSD、SFT 及 SPRJ。</span><span class="sxs-lookup"><span data-stu-id="68fb0-105">During sequencing, the Sequencer monitors and records all installation and setup processes for an application and creates the following files: ICO, OSD, SFT, and SPRJ.</span></span> <span data-ttu-id="68fb0-106">這些檔案包含有關應用程式的所有必要資訊，並可讓該應用程式在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="68fb0-106">These files contain all the necessary information about an application, and they allow that application to run in a virtual environment.</span></span>

<span data-ttu-id="68fb0-107">排序應用程式及建立虛擬應用程式套件的四個階段，包括安裝、啟動、自訂及儲存。</span><span class="sxs-lookup"><span data-stu-id="68fb0-107">The four phases to sequencing an application and creating a virtual application package are installation, launch, customization, and save.</span></span> <span data-ttu-id="68fb0-108">下列清單提供每個階段的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="68fb0-108">The following list provides information about each of the phases:</span></span>

1.  <span data-ttu-id="68fb0-109">**安裝階段**：您可以在安裝階段指定套件名稱，以及將與套件相關聯的選擇性相關批註。</span><span class="sxs-lookup"><span data-stu-id="68fb0-109">**Installation phase**—During the installation phase, you specify the package name and an optional associated comment that will be associated with the package.</span></span> <span data-ttu-id="68fb0-110">您也可以在此階段設定高級監視選項。</span><span class="sxs-lookup"><span data-stu-id="68fb0-110">You can also configure advanced monitoring options during this phase.</span></span> <span data-ttu-id="68fb0-111">[高級監視] 選項包括指定區塊大小，以及在監視期間是否會安裝自動更新。</span><span class="sxs-lookup"><span data-stu-id="68fb0-111">Advanced monitoring options include specifying the block size and whether you will install automatic updates during monitoring.</span></span> <span data-ttu-id="68fb0-112">Sequencer 會記錄建立虛擬應用程式套件所需的所有必要資訊和設定，以及相關聯的檔案和註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="68fb0-112">The sequencer records all necessary information and configurations required to create a virtual application package and the associated file and registry settings.</span></span>

    <span data-ttu-id="68fb0-113">**重要** 若要查看 [高級選項]，請選取 [**套件資訊**] 頁面上的 [**顯示高級監視選項**]。</span><span class="sxs-lookup"><span data-stu-id="68fb0-113">**Important** To view the advanced options select **Show Advanced Monitoring Options** on the **Package Information** page.</span></span>

     

2.  <span data-ttu-id="68fb0-114">**啟動階段**：啟動階段期間，您可以指定任何所需的檔案關聯和安全描述項，以在套件中進行設定。</span><span class="sxs-lookup"><span data-stu-id="68fb0-114">**Launch phase**—During the launch phase, you can specify any required file associations and security descriptors that should be configured with the package.</span></span> <span data-ttu-id="68fb0-115">您應該視需要多次開啟應用程式，以確保應用程式的功能和穩定性。</span><span class="sxs-lookup"><span data-stu-id="68fb0-115">You should open the application as many times as necessary to ensure application functionality and stability.</span></span>

3.  <span data-ttu-id="68fb0-116">**自訂階段**：在自訂階段期間，您可以使用相關聯的 .osd 檔案來設定您的套件。</span><span class="sxs-lookup"><span data-stu-id="68fb0-116">**Customization phase**—During the customization phase, you can configure your package by using the associated .osd files.</span></span> <span data-ttu-id="68fb0-117">您可以指定任何相關聯的腳本應該在虛擬環境內或外部執行、指定要執行的其他動作、指定關聯腳本執行的方式（同步或非同步），以及指定應該在使用者內容下執行的任何其他腳本。</span><span class="sxs-lookup"><span data-stu-id="68fb0-117">You can specify whether any associated scripts should run inside or outside of the virtual environment, specify additional actions that should be performed, specify how associated scripts run (synchronously or asynchronously), and specify any additional scripts that should be run under the user context.</span></span>

4.  <span data-ttu-id="68fb0-118">**儲存階段**：在儲存階段中，會建立虛擬應用程式套件所需的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="68fb0-118">**Save phase**—During the save phase, all required files for the virtual application package are created.</span></span> <span data-ttu-id="68fb0-119">建立的檔案為 sprj、sft、.osd、.ico、.xml 資訊清單，以及 Windows installer （.msi）檔案。</span><span class="sxs-lookup"><span data-stu-id="68fb0-119">The files created are .sprj, .sft, .osd, .ico, .xml manifest, and the Windows installer (.msi) file.</span></span>

## <span data-ttu-id="68fb0-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="68fb0-120">Related topics</span></span>


[<span data-ttu-id="68fb0-121">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="68fb0-121">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





