---
title: 選取主要項目頁面 (深入瞭解)
description: 選取主要項目頁面 (深入瞭解)
author: dansimp
ms.assetid: 17c779da-f683-4967-b136-94fe65373c1b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca1cba253cfc2ddb7ccc5768d9a32982b178287
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800845"
---
# <span data-ttu-id="9e805-103">選取主要項目頁面 (深入瞭解)</span><span class="sxs-lookup"><span data-stu-id="9e805-103">Select Primary Page (Learn More)</span></span>


<span data-ttu-id="9e805-104">使用 [**選取主要**頁面] 來指定附加元件或外掛程式將與之關聯之程式的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="9e805-104">Use the **Select Primary** page to specify the installation file of the program that the add-on or plug-in will be associated with.</span></span> <span data-ttu-id="9e805-105">如果未在執行 App-v 排序器的電腦上安裝上層應用程式，您必須先停止此程式，然後立即安裝。</span><span class="sxs-lookup"><span data-stu-id="9e805-105">If the parent application is not already installed on the computer running the App-V Sequencer, you must stop this procedure and install it now.</span></span>

<span data-ttu-id="9e805-106">例如，如果您要安裝的外掛程式是與 MicrosoftExcel 操作，您必須指定**Excel.exe**。</span><span class="sxs-lookup"><span data-stu-id="9e805-106">For example, if you are installing a plug-in that is designed to operate with MicrosoftExcel, you must specify **Excel.exe**.</span></span>

<span data-ttu-id="9e805-107">您也可以使用現有的虛擬應用程式套件做為父應用程式。</span><span class="sxs-lookup"><span data-stu-id="9e805-107">You can also use an existing virtual application package as the parent application.</span></span> <span data-ttu-id="9e805-108">若要使用現有的虛擬應用程式套件，請在為新的附加元件或外掛程式排序前，先使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="9e805-108">To use an existing virtual application package, use the following procedure before sequencing the new add-on or plug-in.</span></span>

1.  <span data-ttu-id="9e805-109">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="9e805-109">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="9e805-110">若要將現有的套件展開至執行排序器的電腦，請按一下 [**工具**]，將 [  /  **套件] 展開至 [本機系統**</span><span class="sxs-lookup"><span data-stu-id="9e805-110">To expand an existing package to the computer running the Sequencer, click **Tools** / **Expand Package to Local System**.</span></span>

3.  <span data-ttu-id="9e805-111">流覽至，然後選取您要展開的套件（**sprj**檔案），然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="9e805-111">Browse to, and select the package (**.sprj** file) that you want to expand, and then click **Open**.</span></span>

<span data-ttu-id="9e805-112">此頁面包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="9e805-112">This page contains the following elements:</span></span>

<a href="" id="browse"></a>**<span data-ttu-id="9e805-113">瀏覽</span><span class="sxs-lookup"><span data-stu-id="9e805-113">Browse</span></span>**  
<span data-ttu-id="9e805-114">按一下 **[流覽]** ，指定您要將其排序的增益集或外掛程式與之關聯的程式。</span><span class="sxs-lookup"><span data-stu-id="9e805-114">Click **Browse** to specify the program that the add-in or plug-in you are sequencing will be associated with.</span></span>

## <span data-ttu-id="9e805-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="9e805-115">Related topics</span></span>


[<span data-ttu-id="9e805-116">[建立新套件] 嚮導（AppV 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="9e805-116">Create New Package Wizard (AppV 4.6 SP1)</span></span>](create-new-package-wizard---appv-46-sp1-.md)

 

 





