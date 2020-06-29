---
title: 虛擬應用程式封裝其他元件
description: 虛擬應用程式封裝其他元件
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800747"
---
# <span data-ttu-id="f7a5e-103">虛擬應用程式封裝其他元件</span><span class="sxs-lookup"><span data-stu-id="f7a5e-103">Virtual Application Package Additional Components</span></span>


<span data-ttu-id="f7a5e-104">App-v 排序器檢測到一個目錄，其中包含64位和32位的可執行檔，以及/或動態連結程式庫（.dll）檔案，而這些檔案是由同一個並行元件所組成。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-104">The App-V Sequencer has detected a directory that contains 64-bit and 32-bit executables and/or dynamic-link library (.dll) files that depend on the same side-by-side assembly.</span></span> <span data-ttu-id="f7a5e-105">通常，Sequencer 會針對封裝所使用的所有公用元件建立私有並行元件;不過，無法在同一個目錄中建立32位與64位版本的私人程式集。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-105">Typically, the Sequencer creates private side-by-side assemblies for all public assemblies that are used by the package; however, it is not possible to create 32-bit and 64-bit versions of the private assemblies in the same directory.</span></span>

<span data-ttu-id="f7a5e-106">如果 Sequencer 檢測到單一衝突，則會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f7a5e-106">If the Sequencer detects a single conflict, it will perform the following actions:</span></span>

-   <span data-ttu-id="f7a5e-107">移除整個套件中所有現有的64位私用程式集（無論該目錄是否有衝突）。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-107">Remove all of the existing 64-bit private assemblies in the entire package, whether or not the directory has a conflict.</span></span>

-   <span data-ttu-id="f7a5e-108">只建立32位的私人並行元件版本。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-108">Create only 32-bit versions of the private side-by-side assemblies.</span></span>

<span data-ttu-id="f7a5e-109">您應該在執行排序器的電腦和所有 App-v 用戶端電腦上，本機安裝所有必要64位元件的公開版本。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-109">You should natively install public versions of all the required 64-bit assemblies on the computer running the Sequencer and on all App-V client computers.</span></span>

<span data-ttu-id="f7a5e-110">若要找出所需的現有公用元件，請開啟套件的儲存目錄，並在**VFS**資料夾中尋找。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-110">To locate the required existing public assemblies, open the directory where the package is saved and look in the **VFS** folder.</span></span> <span data-ttu-id="f7a5e-111">例如，如果套件根目錄是**Q:\\MyApp**，當您將應用程式排序時，請參閱**Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests** ，並找出所有現有的公用元件。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-111">For example, if the package root is **Q:\\MyApp**, when you sequence the application, look in **Q:\\MyApp\\VFS\\CSIDL\_Windows\\WinSxS\\Manifests** and locate all of the existing public assemblies.</span></span> <span data-ttu-id="f7a5e-112">這些檔案的64位版本永遠會以下列文字從資訊清單名稱開頭開始： **amd64 ...**</span><span class="sxs-lookup"><span data-stu-id="f7a5e-112">The 64-bit versions of these files will always start with the following text at the beginning of the manifest name: **amd64…**.</span></span> <span data-ttu-id="f7a5e-113">您可以在相關聯的資訊清單檔案中找到該元件的確切名稱和版本。</span><span class="sxs-lookup"><span data-stu-id="f7a5e-113">The exact name and version of the assembly can be found in the associated manifest file.</span></span>

<span data-ttu-id="f7a5e-114">使用下列任何一個連結，下載並安裝正確的必要必備元件版本：</span><span class="sxs-lookup"><span data-stu-id="f7a5e-114">Use any of the following links to download and install the correct version of the required prerequisites:</span></span>

-   [<span data-ttu-id="f7a5e-115">Microsoft Visual c + + 2005 可再發行套件（x64）</span><span class="sxs-lookup"><span data-stu-id="f7a5e-115">Microsoft Visual C++ 2005 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [<span data-ttu-id="f7a5e-116">Microsoft Visual c + + 2005 SP1 可再發行套件（x64）</span><span class="sxs-lookup"><span data-stu-id="f7a5e-116">Microsoft Visual C++ 2005 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [<span data-ttu-id="f7a5e-117">Microsoft Visual c + + 2008 可再發行套件（x64）</span><span class="sxs-lookup"><span data-stu-id="f7a5e-117">Microsoft Visual C++ 2008 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [<span data-ttu-id="f7a5e-118">Microsoft Visual c + + 2008 SP1 可再發行套件（x64）</span><span class="sxs-lookup"><span data-stu-id="f7a5e-118">Microsoft Visual C++ 2008 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





