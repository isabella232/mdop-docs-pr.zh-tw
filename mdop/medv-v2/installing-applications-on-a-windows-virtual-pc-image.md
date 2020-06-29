---
title: 在 Windows 虛擬電腦映像上安裝應用程式
description: 在 Windows 虛擬電腦映像上安裝應用程式
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811991"
---
# <span data-ttu-id="f4b44-103">在 Windows 虛擬電腦映像上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="f4b44-103">Installing Applications on a Windows Virtual PC Image</span></span>


<span data-ttu-id="f4b44-104">在您建立 Windows 虛擬電腦映射以搭配 Microsoft 企業桌面虛擬化（MED-V）2.0 之後，您可以在執行 MED-V （例如電子軟體發佈（ESD）系統和防毒軟體）時，安裝其他有用的元件。</span><span class="sxs-lookup"><span data-stu-id="f4b44-104">After you have created a Windows Virtual PC image for use with Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you can install other components that are helpful when running MED-V, such as an electronic software distribution (ESD) system and antivirus software.</span></span>

<span data-ttu-id="f4b44-105">下列各節提供的資訊可協助您在 MED-V 影像上安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="f4b44-105">The following section provides information to help you install software on the MED-V image.</span></span>

<span data-ttu-id="f4b44-106">**小心** 若要在部署之後輕鬆使用 MED-V 工作區管理，我們建議您將在 MED-V 影像上安裝的元件數量限制為所需的元件，或使用 MED-V 的實用程式。</span><span class="sxs-lookup"><span data-stu-id="f4b44-106">**Caution** For ease of MED-V workspace management after deployment, we recommend that you limit the number of components that you install on the MED-V image to those components that are required or that are helpful when using MED-V.</span></span> <span data-ttu-id="f4b44-107">例如，雖然不需要執行 MED-V，但您可以安裝 ESD 系統來供日後安裝應用程式到 MED-V 工作區，以及在影像上進行安全性的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="f4b44-107">For example, although they are not required to run MED-V, you can install an ESD system to use later for installing applications to a MED-V workspace and antivirus software for security on the image.</span></span>

 

**<span data-ttu-id="f4b44-108">在 MED-V 影像上安裝軟體</span><span class="sxs-lookup"><span data-stu-id="f4b44-108">Installing Software on a MED-V Image</span></span>**

1.  <span data-ttu-id="f4b44-109">如果目前沒有執行，請開啟您的 MED-V 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="f4b44-109">If it is not currently running, open your MED-V virtual machine.</span></span>

    1.  <span data-ttu-id="f4b44-110">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。</span><span class="sxs-lookup"><span data-stu-id="f4b44-110">Click **Start**, click **All Programs**, click **Windows Virtual PC** and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="f4b44-111">按兩下您的 MED-V 虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="f4b44-111">Double-click your MED-V virtual machine.</span></span>

2.  <span data-ttu-id="f4b44-112">從虛擬機器作業系統內，找出您要安裝之軟體的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="f4b44-112">From inside the virtual machine operating system, locate the installation files for the software that you want to install.</span></span>

3.  <span data-ttu-id="f4b44-113">依照軟體廠商提供的安裝指示進行。</span><span class="sxs-lookup"><span data-stu-id="f4b44-113">Follow the installation instructions that are provided by the software vendor.</span></span>

    <span data-ttu-id="f4b44-114">**記事** 安裝完成後，您可能必須關閉虛擬機器，然後再重新開機。</span><span class="sxs-lookup"><span data-stu-id="f4b44-114">**Note** After installation is complete, you might have to close and then restart the virtual machine.</span></span>

     

<span data-ttu-id="f4b44-115">針對您想要在 MED-V 影像上安裝的任何軟體或應用程式，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="f4b44-115">Repeat these steps for any software or application that you want to install on the MED-V image.</span></span> <span data-ttu-id="f4b44-116">我們建議您限制您在影像上預先安裝的應用程式數量。</span><span class="sxs-lookup"><span data-stu-id="f4b44-116">We recommend that you limit the number of applications that you preinstall on the image.</span></span> <span data-ttu-id="f4b44-117">在影像上安裝應用程式和其他軟體的建議程式是立即預先安裝 ESD 系統，稍後再使用它來將軟體部署至影像。</span><span class="sxs-lookup"><span data-stu-id="f4b44-117">The recommended process for installing applications and other software on the image is to preinstall an ESD system now and to use it later to deploy software to the image.</span></span> <span data-ttu-id="f4b44-118">或者，您也可以使用群組原則或 App-v 在 MED-V 工作區上新增或移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4b44-118">Alternately, you can also use Group Policy or App-V to add or remove applications on a MED-V workspace.</span></span> <span data-ttu-id="f4b44-119">如需詳細資訊，請參閱[管理部署至 Med-v 工作區的應用程式](managing-applications-deployed-to-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b44-119">For more information, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

<span data-ttu-id="f4b44-120">如需如何在虛擬影像上安裝軟體的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="f4b44-120">For more information about how to install software on a virtual image, see the following articles:</span></span>

-   <span data-ttu-id="f4b44-121">[發佈並使用虛擬應用程式](https://go.microsoft.com/fwlink/?LinkId=195926)（ https://go.microsoft.com/fwlink/?LinkId=195926) 。</span><span class="sxs-lookup"><span data-stu-id="f4b44-121">[Publish and Use Virtual Applications](https://go.microsoft.com/fwlink/?LinkId=195926) (https://go.microsoft.com/fwlink/?LinkId=195926).</span></span>

-   <span data-ttu-id="f4b44-122">[Windows 虛擬電腦](https://go.microsoft.com/fwlink/?LinkId=182378)說明（ https://go.microsoft.com/fwlink/?LinkId=182378) 。</span><span class="sxs-lookup"><span data-stu-id="f4b44-122">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="f4b44-123">在 MED-V 影像上安裝完所有您想要的軟體之後，您的影像就可以打包了。</span><span class="sxs-lookup"><span data-stu-id="f4b44-123">After you have installed all of the software that you want on the MED-V image, your image is ready to be packaged.</span></span>

## <span data-ttu-id="f4b44-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="f4b44-124">Related topics</span></span>


[<span data-ttu-id="f4b44-125">設定 MED-V 的 Windows 虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="f4b44-125">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="f4b44-126">準備 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="f4b44-126">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)

 

 





