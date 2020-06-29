---
title: Defender 正在執行對話方塊 (App-V 4.6 SP1)
description: Defender 正在執行對話方塊 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 716ec7f9-ddad-45dd-a3c7-4a9d81cfcfd0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e33d48c089d7bf903c65da804e6cf5aa1bd2065
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808955"
---
# <span data-ttu-id="3e4a0-103">Defender 正在執行對話方塊 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="3e4a0-103">Defender Running Dialog Box (App-V 4.6 SP1)</span></span>


<span data-ttu-id="3e4a0-104">Microsoft Windows Defender 正在執行。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-104">Microsoft Windows Defender is running.</span></span> <span data-ttu-id="3e4a0-105">您應該先停止 Windows Defender，然後再繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-105">You should stop Windows Defender before continuing with the installation.</span></span> <span data-ttu-id="3e4a0-106">Windows Defender 會存取必須新增至虛擬應用程式套件的檔案，或是在虛擬應用程式套件中新增無關資料，來干擾建立套件。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-106">Windows Defender can interfere with creation of a package by accessing files that must be added to the virtual application package or by adding extraneous data to the virtual application package.</span></span>

<span data-ttu-id="3e4a0-107">使用下列程式來避免 Microsoft Windows Defender 在排序期間執行。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-107">Use the following procedure to stop Microsoft Windows Defender from running during sequencing.</span></span>

1.  <span data-ttu-id="3e4a0-108">在執行 App-v 排序器的電腦上，按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-108">On the computer running the App-V Sequencer, click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="3e4a0-109">在 [**電腦管理**] 主控台中，按兩下 [**服務與應用程式**]，然後按兩下 [**服務**] 以展開 [**服務**]。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-109">In the **Computer Management** console, double click **Services and Applications**, and then double-click **Services** to expand **Services**.</span></span>

3.  <span data-ttu-id="3e4a0-110">在清單中找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-110">Locate it in the list.</span></span> <span data-ttu-id="3e4a0-111">以滑鼠右鍵按一下 [Windows Defender]，按一下 [**停止**] 停止 Microsoft Windows defender，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3e4a0-111">Right-click Windows Defender, click **Stop** to stop Microsoft Windows Defender, and then click **Ok**.</span></span>

## <span data-ttu-id="3e4a0-112">相關主題</span><span class="sxs-lookup"><span data-stu-id="3e4a0-112">Related topics</span></span>


[<span data-ttu-id="3e4a0-113">對話方塊 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="3e4a0-113">Dialog Boxes (AppV 4.6 SP1)</span></span>](dialog-boxes--appv-46-sp1-.md)

 

 





