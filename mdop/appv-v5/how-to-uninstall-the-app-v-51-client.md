---
title: 如何解除安裝 App-V 5.1 Client
description: 如何解除安裝 App-V 5.1 Client
author: dansimp
ms.assetid: 21f2d946-fc9f-4cd3-899b-ac52b3fbc306
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9338bef6b8a3123f9b8f49036427121987e7aa9f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800398"
---
# <span data-ttu-id="61149-103">如何解除安裝 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="61149-103">How to Uninstall the App-V 5.1 Client</span></span>


<span data-ttu-id="61149-104">使用下列程式從電腦卸載 Microsoft Application Virtualization （App-v）5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="61149-104">Use the following procedure to uninstall the Microsoft Application Virtualization (App-V) 5.1 client from a computer.</span></span> <span data-ttu-id="61149-105">當您卸載 App-v 5.1 用戶端時，所有發佈到執行用戶端之電腦的套件也都會被移除。</span><span class="sxs-lookup"><span data-stu-id="61149-105">When you uninstall the App-V 5.1 client all packages published to the computer running the client are also removed.</span></span> <span data-ttu-id="61149-106">如果卸載操作沒有完成，則需要將套件重新發佈到執行 App-v 5.1 用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="61149-106">If the uninstall operation does not complete the packages will need to be re-published to the computer running the App-V 5.1 client.</span></span>

**<span data-ttu-id="61149-107">重要</span><span class="sxs-lookup"><span data-stu-id="61149-107">Important</span></span>**  
<span data-ttu-id="61149-108">在執行卸載程式之前，您應該先確定 App-V 5.1 用戶端服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="61149-108">You should ensure that the App-V 5.1 client service is running prior to performing the uninstall procedure.</span></span>



**<span data-ttu-id="61149-109">若要卸載應用程式-V 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="61149-109">To uninstall the App-V 5.1 Client</span></span>**

1.  <span data-ttu-id="61149-110">在 [控制台] 中，按兩下 [**程式**  /  **卸載程式**]，然後按兩下 [ **Microsoft Application Virtualization 用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="61149-110">In Control Panel, double-click **Programs** / **Uninstall a Program**, and then double-click **Microsoft Application Virtualization Client**.</span></span>

2.  <span data-ttu-id="61149-111">在出現的對話方塊中，按一下 [**是**] 以繼續卸載程式。</span><span class="sxs-lookup"><span data-stu-id="61149-111">In the dialog box that appears, click **Yes** to continue with the uninstall process.</span></span>

    **<span data-ttu-id="61149-112">重要</span><span class="sxs-lookup"><span data-stu-id="61149-112">Important</span></span>**  
    <span data-ttu-id="61149-113">無法取消或中斷卸載程式。</span><span class="sxs-lookup"><span data-stu-id="61149-113">The uninstall process cannot be canceled or interrupted.</span></span>



3.  <span data-ttu-id="61149-114">進度列會顯示剩餘的時間。</span><span class="sxs-lookup"><span data-stu-id="61149-114">A progress bar shows the time remaining.</span></span> <span data-ttu-id="61149-115">完成這個步驟後，您必須重新開機電腦，才能停止所有相關聯的驅動程式來完成卸載程式。</span><span class="sxs-lookup"><span data-stu-id="61149-115">When this step finishes, you must restart the computer so that all associated drivers can be stopped to complete the uninstall process.</span></span>

    **<span data-ttu-id="61149-116">注意</span><span class="sxs-lookup"><span data-stu-id="61149-116">Note</span></span>**  
    <span data-ttu-id="61149-117">您也可以使用命令列，以下列開關： **/uninstall**卸載 app-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="61149-117">You can also use the command line to uninstall the App-V 5.1 client with the following switch: **/UNINSTALL**.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="61149-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="61149-118">Related topics</span></span>


[<span data-ttu-id="61149-119">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="61149-119">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









