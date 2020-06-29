---
title: 安裝檔案頁面
description: 安裝檔案頁面
author: dansimp
ms.assetid: b0aad26f-b143-4f09-87a1-9f016a23cb62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08a2e7318271503f072298ca137a1e65e16c0178
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801000"
---
# <span data-ttu-id="a5bb1-103">安裝檔案頁面</span><span class="sxs-lookup"><span data-stu-id="a5bb1-103">Installation Files Page</span></span>


<span data-ttu-id="a5bb1-104">使用 [**安裝**檔案] 頁面來指定所用的安裝檔案，這些檔案是用來建立此嚮導 [**選取套件**] 頁面上指定的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-104">Use the **Installation Files** page to specify the installation files that were used to create the virtual application package specified on the **Select Package** page of this wizard.</span></span> <span data-ttu-id="a5bb1-105">如果您建立的虛擬應用程式套件包含多個應用程式，您應該將所有必要的安裝檔案複製到執行 Microsoft Application Virtualization 排序器的電腦上的單一資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-105">If you created a virtual application package that contains multiple applications, you should copy all required installation files to a single folder on the computer running the Microsoft Application Virtualization Sequencer.</span></span>

<span data-ttu-id="a5bb1-106">此頁面包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="a5bb1-106">This page contains the following elements:</span></span>

<a href="" id="original-installation-files"></a>**<span data-ttu-id="a5bb1-107">原始安裝檔</span><span class="sxs-lookup"><span data-stu-id="a5bb1-107">Original Installation Files</span></span>**  
<span data-ttu-id="a5bb1-108">按一下 **[流覽]** ，指定原先用來建立虛擬應用程式套件的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-108">Click **Browse** to specify the installation files that were originally used to create the virtual application package.</span></span> <span data-ttu-id="a5bb1-109">您指定的父目錄應該儲存在本機的電腦上，且必須包含所有必要的安裝檔案或包含安裝檔案的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-109">The parent directory you specify should be saved locally to the computer running the Sequencer and must contain all required installation files or subfolders that contain the installation files.</span></span> <span data-ttu-id="a5bb1-110">安裝檔案可以包含在上層資料夾或指定的父資料夾的任何子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-110">The installation files can be contained in the parent folder or in any of the subfolders of the specified parent folder.</span></span>

<a href="" id="files-installed-on-local-system"></a>**<span data-ttu-id="a5bb1-111">安裝在本機系統上的檔案</span><span class="sxs-lookup"><span data-stu-id="a5bb1-111">Files installed on local system</span></span>**  
<span data-ttu-id="a5bb1-112">按一下 **[流覽]** ，指定在執行排序器的電腦上本機安裝的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-112">Click **Browse** to specify the installation files that have been installed locally on the computer running the Sequencer.</span></span> <span data-ttu-id="a5bb1-113">如果應用程式安裝檔案已安裝到應用程式的預設位置，您就只能選取此選項。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-113">You can only select this option if the application installation files have been installed to the application’s default location.</span></span>

<span data-ttu-id="a5bb1-114">**記事** 您所提供的預設安裝位置視下列情況而定：</span><span class="sxs-lookup"><span data-stu-id="a5bb1-114">**Note** The default installation location you provide depends on the following conditions:</span></span>

 

-   <span data-ttu-id="a5bb1-115">最初建立套件時指定的套件根目錄。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-115">The package root specified when the package was originally created.</span></span>

-   <span data-ttu-id="a5bb1-116">最初建立套件時，在 Windows 安裝程式中指定的安裝位置。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-116">The installation location specified in the Windows Installer when the package was originally created.</span></span>

-   <span data-ttu-id="a5bb1-117">預設的應用程式安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-117">The default application installation path.</span></span>

<span data-ttu-id="a5bb1-118">例如，如果指定的套件根目錄是**Q:\\Office12** ，且在安裝期間，預設的安裝位置會從**c:\\program files Files\\Office12**變更為**Q:\\Office12**，所以凍結期間指定的路徑必須是**c:\\program files Files\\Office 12**。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-118">For example, if the package root specified is **Q:\\Office12** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Office12**, then the path specified during dehydration must be **C:\\Program Files\\Office 12**.</span></span>

<span data-ttu-id="a5bb1-119">如果指定的套件根目錄是**Q:\\Microsoft** ，且安裝期間預設的安裝位置是從**c:\\program files Files\\Office12**改為**Q:\\Microsoft\\Office12**，則在凍結期間指定的路徑必須是**c:\\program files**檔案。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-119">If the package root specified is **Q:\\Microsoft** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Microsoft\\Office12**, then the path specified during dehydration must be **C:\\Program Files**.</span></span>

<span data-ttu-id="a5bb1-120">當您使用套件加速器建立套件時，封裝中的每個檔案（例如**Q:\\Office12\\file.txt** ）都是在本機電腦上使用建立套件加速器時所指定的預設位置（例如， **c:\\program files Files\\Office12**）來取代套件根**Q:\\Office12** 。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-120">When you create a package using a package accelerator, each file in the package, for example **Q:\\Office12\\file.txt** is found on the local computer by replacing the package root **Q:\\Office12** with the default location specified when the Package Accelerator was created, for example, **C:\\Program Files\\Office12**.</span></span> <span data-ttu-id="a5bb1-121">在上一個範例中，檔案應該位於**c:\\program files Files\\Office12\\file.txt**中。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-121">In the previous example, the file should be located in **C:\\Program Files\\Office12\\file.txt**.</span></span>

## <span data-ttu-id="a5bb1-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="a5bb1-122">Related topics</span></span>


[<span data-ttu-id="a5bb1-123">建立封裝加速器精靈 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="a5bb1-123">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

 

 





