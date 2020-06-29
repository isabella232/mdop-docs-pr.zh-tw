---
title: 如何使用命令列來開啟循序應用程式
description: 如何使用命令列來開啟循序應用程式
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801209"
---
# <span data-ttu-id="0006a-103">如何使用命令列來開啟循序應用程式</span><span class="sxs-lookup"><span data-stu-id="0006a-103">How to Open a Sequenced Application Using the Command Line</span></span>


<span data-ttu-id="0006a-104">您可以使用命令列開啟虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="0006a-104">You can open virtual application packages using the command line.</span></span> <span data-ttu-id="0006a-105">您必須以系統管理員身分執行**cmd**提示。</span><span class="sxs-lookup"><span data-stu-id="0006a-105">You must run the **cmd** prompt as an administrator.</span></span>

<span data-ttu-id="0006a-106">使用下列程式，使用命令列開啟順序化的應用程式套件</span><span class="sxs-lookup"><span data-stu-id="0006a-106">Use the following procedure to open sequenced application packages using the command line</span></span>

**<span data-ttu-id="0006a-107">使用命令列開啟順序化的應用程式</span><span class="sxs-lookup"><span data-stu-id="0006a-107">To open a sequenced application using the command line</span></span>**

1.  <span data-ttu-id="0006a-108">若要開啟命令提示字元，請按一下 [**開始**]，然後選取 [**執行**]，輸入**Cmd**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0006a-108">To open the command prompt, click **Start**, and select **Run**, type **cmd**, and click **OK**.</span></span>

2.  <span data-ttu-id="0006a-109">在命令提示字元中，輸入**cd\\**並指定安裝排序器的目錄路徑，然後按**enter。**</span><span class="sxs-lookup"><span data-stu-id="0006a-109">At a command prompt, type **cd\\** and specify the path to the directory where the Sequencer is installed and then press **Enter.**</span></span>

3.  <span data-ttu-id="0006a-110">在命令提示字元中，輸入下列命令，並以您的值取代斜體文字：</span><span class="sxs-lookup"><span data-stu-id="0006a-110">At the command prompt, type the following command, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="0006a-111">SFTSequencer/OPEN：「*指定要開啟的 sprj*檔案」</span><span class="sxs-lookup"><span data-stu-id="0006a-111">SFTSequencer /OPEN:*”specifies the .sprj file to open"*</span></span>

    <span data-ttu-id="0006a-112">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="0006a-112">Press **Enter**.</span></span>

4.  <span data-ttu-id="0006a-113">您也可以指定下列選用參數。</span><span class="sxs-lookup"><span data-stu-id="0006a-113">You can also specify the following optional parameters.</span></span> <span data-ttu-id="0006a-114">在命令提示字元中，輸入下列命令，並以您的值取代斜體文字：</span><span class="sxs-lookup"><span data-stu-id="0006a-114">At the command prompt, type the following commands, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="0006a-115">/PACKAGENAME： "*指定套件名稱"*</span><span class="sxs-lookup"><span data-stu-id="0006a-115">/PACKAGENAME:"*specifies the package name"*</span></span>

    <span data-ttu-id="0006a-116">/MSI-指定產生關聯的 Microsoft Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="0006a-116">/MSI - specifies generating an associated Microsoft Windows Installer.</span></span>

    <span data-ttu-id="0006a-117">/COMPRESS –指定套件是否會進行壓縮。</span><span class="sxs-lookup"><span data-stu-id="0006a-117">/COMPRESS – specifies if the package will be compressed.</span></span> <span data-ttu-id="0006a-118">根據預設，套件不會壓縮。</span><span class="sxs-lookup"><span data-stu-id="0006a-118">By default, packages are not compressed.</span></span>

    <span data-ttu-id="0006a-119">按**enter**。</span><span class="sxs-lookup"><span data-stu-id="0006a-119">Press **Enter**.</span></span>

    <span data-ttu-id="0006a-120">**記事** 如果安裝程式或 Windows 安裝程式套件有圖形使用者介面，則會在您指定命令列參數之後顯示。</span><span class="sxs-lookup"><span data-stu-id="0006a-120">**Note** If the installer or Windows Installer package has a graphical user interface, it will be displayed after you specify the command-line parameters.</span></span>

     

## <span data-ttu-id="0006a-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="0006a-121">Related topics</span></span>


[<span data-ttu-id="0006a-122">如何使用命令列管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="0006a-122">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





