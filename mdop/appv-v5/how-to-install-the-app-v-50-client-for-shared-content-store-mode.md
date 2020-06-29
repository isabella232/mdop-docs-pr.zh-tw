---
title: 如何安裝 App-V 5.0 用戶端以使用共用內容存放區模式
description: 如何安裝 App-V 5.0 用戶端以使用共用內容存放區模式
author: dansimp
ms.assetid: 88f09e6f-19e7-48ea-965a-907052d1a02f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 704ea6c1e4b1ba4670a4e52d754b8e6e5a9fb8f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800498"
---
# <span data-ttu-id="cb834-103">如何安裝 App-V 5.0 用戶端以使用共用內容存放區模式</span><span class="sxs-lookup"><span data-stu-id="cb834-103">How to Install the App-V 5.0 Client for Shared Content Store Mode</span></span>


<span data-ttu-id="cb834-104">使用下列程式來安裝 Microsoft Application Virtualization （App-v）5.0 用戶端，讓它使用 App-v 5.0 的共用內容儲存區（SCS）模式。</span><span class="sxs-lookup"><span data-stu-id="cb834-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.0 client so that it uses the App-V 5.0 Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="cb834-105">您應該確保您打算安裝的電腦上已安裝所有必要的先決條件。</span><span class="sxs-lookup"><span data-stu-id="cb834-105">You should ensure that all required prerequisites are installed on the computer you plan to install to.</span></span> <span data-ttu-id="cb834-106">針對[app-v 5.0 先決條件](app-v-50-prerequisites.md)使用下列連結。</span><span class="sxs-lookup"><span data-stu-id="cb834-106">Use the following link for a [App-V 5.0 Prerequisites](app-v-50-prerequisites.md).</span></span>

<span data-ttu-id="cb834-107">**記事** 在執行此程式之前，請先卸載任何現有的 App-v 5.0 用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="cb834-107">**Note** Before performing this procedure if necessary uninstall any existing version of the App-V 5.0 client.</span></span>

 

<span data-ttu-id="cb834-108">如需 SCS 模式的詳細資訊，請參閱[Microsoft app-v 5.0 中的共用內容存放區](https://go.microsoft.com/fwlink/?LinkId=316879)（位於幕後） https://go.microsoft.com/fwlink/?LinkId=316879) 。</span><span class="sxs-lookup"><span data-stu-id="cb834-108">For more information about SCS mode, see [Shared Content Store in Microsoft App-V 5.0 – Behind the Scenes](https://go.microsoft.com/fwlink/?LinkId=316879) (https://go.microsoft.com/fwlink/?LinkId=316879).</span></span>

**<span data-ttu-id="cb834-109">安裝並設定適用于 SCS 模式的 App-v 5.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="cb834-109">Install and configure the App-V 5.0 client for SCS mode</span></span>**

1.  <span data-ttu-id="cb834-110">將 App-v 5.0 用戶端安裝檔案複製到安裝該檔案的電腦上。</span><span class="sxs-lookup"><span data-stu-id="cb834-110">Copy the App-V 5.0 client installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="cb834-111">開啟命令列，並從儲存安裝盤案的目錄中，輸入下列其中一個選項（視您要安裝的用戶端版本而定）：</span><span class="sxs-lookup"><span data-stu-id="cb834-111">Open a command line and from the directory where the installation files are saved type one of the following options depending on the version of the client you are installing:</span></span>

    -   <span data-ttu-id="cb834-112">若要安裝 RDS 版的 App-v 5.0 用戶端類型： **appv\_client\_setup\_rds.exe/SHAREDCONTENTSTOREMODE = 1/q**</span><span class="sxs-lookup"><span data-stu-id="cb834-112">To install the RDS version of the App-V 5.0 client type: **appv\_client\_setup\_rds.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

    -   <span data-ttu-id="cb834-113">若要安裝標準版的 App-v 5.0 用戶端類型： **appv\_client\_setup.exe/SHAREDCONTENTSTOREMODE = 1/q**</span><span class="sxs-lookup"><span data-stu-id="cb834-113">To install the standard version of the App-V 5.0 client type: **appv\_client\_setup.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

        <span data-ttu-id="cb834-114">**重要** 您必須執行緘默安裝，否則安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="cb834-114">**Important** You must perform a silent installation or the installation will fail.</span></span>

         

2.  <span data-ttu-id="cb834-115">完成安裝之後，您可以將套件部署到執行用戶端的電腦，所有套件內容都會在整個網路中流動。</span><span class="sxs-lookup"><span data-stu-id="cb834-115">After you have completed the installation you can deploy packages to the computer running the client and all package contents will be streamed across the network.</span></span>

    <span data-ttu-id="cb834-116">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="cb834-116">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="cb834-117">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="cb834-117">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="cb834-118">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="cb834-118">Got an App-V issue?</span></span>** <span data-ttu-id="cb834-119">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="cb834-119">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="cb834-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="cb834-120">Related topics</span></span>


[<span data-ttu-id="cb834-121">部署 App-V 5.0 排序器和用戶端</span><span class="sxs-lookup"><span data-stu-id="cb834-121">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

 

 





