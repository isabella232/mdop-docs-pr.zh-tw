---
title: 磁碟重組正在執行對話方塊 (App-V 4.6 SP1)
description: 磁碟重組正在執行對話方塊 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 0ceb0897-377e-4754-a7ab-3bc2b5af1452
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ca56723dedb46ba87890ae62d476ca365b201c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808930"
---
# <span data-ttu-id="b18b4-103">磁碟重組正在執行對話方塊 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="b18b4-103">Defrag Running Dialog Box (App-V 4.6 SP1)</span></span>


<span data-ttu-id="b18b4-104">磁片磁碟重組程式服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="b18b4-104">The Disk Defragmenter service is running.</span></span> <span data-ttu-id="b18b4-105">磁片磁碟重組程式服務會使用系統資源，並可能導致效能降低或增加建立虛擬應用程式套件所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b18b4-105">The Disk Defragmenter service uses system resources and can cause degradation in performance or increase the time it takes to create virtual application package.</span></span>

<span data-ttu-id="b18b4-106">使用下列程式來停止磁片磁碟重組程式服務在順序期間執行。</span><span class="sxs-lookup"><span data-stu-id="b18b4-106">Use the following procedure to stop the Disk Defragmenter service from running during sequencing.</span></span>

1.  <span data-ttu-id="b18b4-107">在執行 App-v 排序器的電腦上，按一下 [**開始**]，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**管理**]。</span><span class="sxs-lookup"><span data-stu-id="b18b4-107">On the computer running the App-V Sequencer, click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="b18b4-108">在 [**電腦管理**] 主控台中，按兩下 [**服務與應用程式**]，然後按兩下 [**服務**]，展開 [**服務**]。</span><span class="sxs-lookup"><span data-stu-id="b18b4-108">In the **Computer Management** console, double-click **Services and Applications**, and then double-click **Services** to expand **Services**,.</span></span>

3.  <span data-ttu-id="b18b4-109">在清單中找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="b18b4-109">Locate it in the list.</span></span> <span data-ttu-id="b18b4-110">以滑鼠右鍵按一下 [**磁片磁碟重組程式**]，按一下 [**其他動作**]，按一下 [**停止**] 停止磁片磁碟重組程式，然後按一下 **[確定]**</span><span class="sxs-lookup"><span data-stu-id="b18b4-110">Right-click **Disk Defragmenter**, click **More Actions**, click **Stop** to stop Disk Defragmenter, and then click **OK**.</span></span>

## <span data-ttu-id="b18b4-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="b18b4-111">Related topics</span></span>


[<span data-ttu-id="b18b4-112">對話方塊 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="b18b4-112">Dialog Boxes (AppV 4.6 SP1)</span></span>](dialog-boxes--appv-46-sp1-.md)

 

 





