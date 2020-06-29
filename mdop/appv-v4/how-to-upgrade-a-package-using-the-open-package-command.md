---
title: 如何使用 [開啟封裝] 命令來升級封裝
description: 如何使用 [開啟封裝] 命令來升級封裝
author: dansimp
ms.assetid: 67c10440-de8a-4547-a34b-f83206d0cc3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca438fe90373e8f934d1d790246544cdf46fa18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801049"
---
# <span data-ttu-id="db9a2-103">如何使用 [開啟封裝] 命令來升級封裝</span><span class="sxs-lookup"><span data-stu-id="db9a2-103">How to Upgrade a Package Using the Open Package Command</span></span>


<span data-ttu-id="db9a2-104">使用 [開啟套件] 命令來升級或將更新套用至已排序的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="db9a2-104">Use the Open Package command to upgrade or apply an update to a sequenced application package.</span></span> <span data-ttu-id="db9a2-105">當您使用命令列升級現有的虛擬應用程式套件時，會刪除該版本的 sft 檔案的原始版本。</span><span class="sxs-lookup"><span data-stu-id="db9a2-105">When you upgrade an existing virtual application package using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="db9a2-106">您應該先備份關聯的 sft 檔案，然後再使用命令列升級套件。</span><span class="sxs-lookup"><span data-stu-id="db9a2-106">You should backup the associated .sft file before upgrading the package using the command line.</span></span>

**<span data-ttu-id="db9a2-107">使用 [開啟套件] 命令升級套件</span><span class="sxs-lookup"><span data-stu-id="db9a2-107">To upgrade a package using the Open Package command</span></span>**

1.  <span data-ttu-id="db9a2-108">若要開啟將升級的套件，請在應用程式虛擬化（App-v）中 **，選取 [** 檔案]、[**開啟套件以供升級**]。</span><span class="sxs-lookup"><span data-stu-id="db9a2-108">To open the package that will be upgraded, in the Application Virtualization (App-V) console select **File**, **Open Package for Upgrade**.</span></span> <span data-ttu-id="db9a2-109">在 [**開啟**舊檔] 對話方塊中，選取要升級的套件。</span><span class="sxs-lookup"><span data-stu-id="db9a2-109">In the **Open** dialog box, select the package that will be upgraded.</span></span>

2.  <span data-ttu-id="db9a2-110">若要啟動 [**先後順序**] 嚮導，請選取 [**工具**]、[**順序] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="db9a2-110">To start the **Sequencing** wizard, select **Tools**, **Sequencing Wizard**.</span></span> <span data-ttu-id="db9a2-111">完成嚮導套用設定變更，若要儲存新的已排序應用**程式，請選取 [** 檔案]、[**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="db9a2-111">Complete the wizard applying the configuration changes, to save the new sequenced application, select **File**, **Save**.</span></span>

3.  <span data-ttu-id="db9a2-112">若要將版本號碼附加到套件名稱，請在 Sequencer 主控台中，選取 [**工具**]、[**選項**]。</span><span class="sxs-lookup"><span data-stu-id="db9a2-112">To append the version number to the package name, in the Sequencer console, select **Tools**, **Options**.</span></span> <span data-ttu-id="db9a2-113">選取 [**將套件版本附加至檔案名**]。</span><span class="sxs-lookup"><span data-stu-id="db9a2-113">Select **Append Package Version to Filename**.</span></span> <span data-ttu-id="db9a2-114">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="db9a2-114">Click **OK**.</span></span>

    <span data-ttu-id="db9a2-115">**重要** 更新套件版本的檔案名對於成功完成升級而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="db9a2-115">**Important** Updating the file name with the package version is essential to successfully completing the upgrade.</span></span>

     

## <span data-ttu-id="db9a2-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="db9a2-116">Related topics</span></span>


[<span data-ttu-id="db9a2-117">如何使用命令列管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="db9a2-117">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





