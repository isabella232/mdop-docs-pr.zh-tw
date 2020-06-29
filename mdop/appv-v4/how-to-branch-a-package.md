---
title: 如何將封裝分支
description: 如何將封裝分支
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801693"
---
# <span data-ttu-id="49624-103">如何將封裝分支</span><span class="sxs-lookup"><span data-stu-id="49624-103">How to Branch a Package</span></span>


<span data-ttu-id="49624-104">使用此程式來修改現有的已排序應用程式套件，讓您可以與原始的已排序應用程式套件並存執行。</span><span class="sxs-lookup"><span data-stu-id="49624-104">Use this procedure to modify an existing sequenced application package so you can run it side-by-side with the original sequenced application package.</span></span> <span data-ttu-id="49624-105">這個處理常式稱為 [分支]。</span><span class="sxs-lookup"><span data-stu-id="49624-105">This process is called branching.</span></span> <span data-ttu-id="49624-106">當您分支虛擬應用程式套件時，您可以執行同一個套件的兩個版本。</span><span class="sxs-lookup"><span data-stu-id="49624-106">When you branch a virtual application package you are able to run two versions of the same package.</span></span> <span data-ttu-id="49624-107">例如，您可以將 service pack 套用至現有的套件，並與原始已排序的虛擬應用程式套件並存執行。</span><span class="sxs-lookup"><span data-stu-id="49624-107">For example, you can apply a service pack to an existing package, and run it side-by-side with the original sequenced virtual application package.</span></span>

<span data-ttu-id="49624-108">使用下列程式來分支已排序的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="49624-108">Use the following procedure to branch a sequenced virtual application package.</span></span>

**<span data-ttu-id="49624-109">分支已排序的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="49624-109">To branch a sequenced virtual application package</span></span>**

1.  <span data-ttu-id="49624-110">開啟 Microsoft Application Virtualization （App-v）排序器。</span><span class="sxs-lookup"><span data-stu-id="49624-110">Open the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="49624-111">若要指定包含您想要分支的套件（sprj）的目的地目錄，請**選取 [** 檔案]，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="49624-111">To specify the destination directory that contains the package (.sprj) you want to branch select **File**, **Open**.</span></span>

2.  <span data-ttu-id="49624-112">流覽至包含您要分支之已排序之應用程式的目錄，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="49624-112">Navigate to the directory that contains the sequenced application you plan to branch and click **Open**.</span></span>

3.  <span data-ttu-id="49624-113">若要儲存套件複本 **，請在**應用程式 V 排序器中選取 [檔案]、[**另存**新檔]。</span><span class="sxs-lookup"><span data-stu-id="49624-113">To save a copy of the package, in the App-V Sequencer, select **File**, **Save As**.</span></span> <span data-ttu-id="49624-114">指定新的唯一名稱，並為套件複本指定新的唯一套件根目錄。</span><span class="sxs-lookup"><span data-stu-id="49624-114">Specify a new, unique name, and specify a new unique package root directory for the copy of the package.</span></span> <span data-ttu-id="49624-115">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="49624-115">Click **Save**.</span></span>

    **<span data-ttu-id="49624-116">重要</span><span class="sxs-lookup"><span data-stu-id="49624-116">Important</span></span>**  
    <span data-ttu-id="49624-117">您必須指定新的套件名稱，否則您會覆寫現有的套件版本。</span><span class="sxs-lookup"><span data-stu-id="49624-117">You must specify a new package name or you will overwrite the existing version of the package.</span></span>



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. <span data-ttu-id="49624-118">在您儲存新版本之後，您可以套用所需的設定變更，並將相關聯的 .ICO、OSD、SFT 及 SPRJ 檔案儲存在應用程式虛擬化（App-v）伺服器上的正確位置。</span><span class="sxs-lookup"><span data-stu-id="49624-118">After you save the new version you can apply the required configuration changes and save the associated ICO, OSD, SFT, and SPRJ files to correct location on the Application Virtualization (App-V) server.</span></span>

## <span data-ttu-id="49624-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="49624-119">Related topics</span></span>


[<span data-ttu-id="49624-120">Application Virtualization Sequencer 的工作</span><span class="sxs-lookup"><span data-stu-id="49624-120">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









