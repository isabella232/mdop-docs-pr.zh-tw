---
title: 如何解除安裝 App-V Client
description: 如何解除安裝 App-V Client
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801050"
---
# <span data-ttu-id="c09aa-103">如何解除安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="c09aa-103">How to Uninstall the App-V Client</span></span>


<span data-ttu-id="c09aa-104">使用下列程式從電腦卸載應用程式虛擬化用戶端。</span><span class="sxs-lookup"><span data-stu-id="c09aa-104">Use the following procedure to uninstall the Application Virtualization Client from the computer.</span></span>

**<span data-ttu-id="c09aa-105">卸載應用程式虛擬化桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="c09aa-105">To uninstall the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="c09aa-106">在 [控制台] 中，按兩下 [**新增或移除程式**] （或在 Windows Vista 中，按一下 [**程式和功能**]），然後按兩下 [ **Microsoft Application Virtualization 桌面用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="c09aa-106">In Control Panel, double-click **Add or Remove Programs** (or in Windows Vista, **Programs and Features**), and then double-click **Microsoft Application Virtualization Desktop Client**.</span></span>

2.  <span data-ttu-id="c09aa-107">在出現的對話方塊中，按一下 [**是**] 以繼續卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-107">In the dialog box that appears, click **Yes** to continue with the uninstall process.</span></span>

    <span data-ttu-id="c09aa-108">**重要** 無法取消或中斷卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-108">**Important** The uninstall process cannot be canceled or interrupted.</span></span>

     

3.  <span data-ttu-id="c09aa-109">如果出現指出 Microsoft Application Virtualization 用戶端工作列應用程式的訊息必須在 [繼續] 出現前關閉，請以滑鼠右鍵按一下通知區域中的 app-v 圖示，**然後選取 [** 結束] 來關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-109">When a message stating that the Microsoft Application Virtualization Client Tray application must be closed before continuing appears, right-click the App-V icon in the notification area and select **Exit** to close the application.</span></span> <span data-ttu-id="c09aa-110">然後按一下 [**重試**] 繼續卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-110">Then click **Retry** to continue with the uninstall process.</span></span>

    <span data-ttu-id="c09aa-111">**重要** 您可能會看到一則訊息，指出正在使用一或多個虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-111">**Important** You might see a message stating that one or more virtual applications are in use.</span></span> <span data-ttu-id="c09aa-112">在繼續之前，請先關閉任何開啟的應用程式並儲存您的資料。</span><span class="sxs-lookup"><span data-stu-id="c09aa-112">Close any open applications and save your data before you continue.</span></span> <span data-ttu-id="c09aa-113">然後按一下 **[確定]** ，繼續進行卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-113">Then click **OK** to continue with the uninstall process.</span></span>

     

4.  <span data-ttu-id="c09aa-114">進度列會顯示剩餘的時間。</span><span class="sxs-lookup"><span data-stu-id="c09aa-114">A progress bar shows the time remaining.</span></span> <span data-ttu-id="c09aa-115">完成這個步驟後，您必須重新開機電腦，才能停止所有相關聯的驅動程式來完成卸載程式。</span><span class="sxs-lookup"><span data-stu-id="c09aa-115">When this step finishes, you must restart the computer so that all associated drivers can be stopped to complete the uninstall process.</span></span>

    <span data-ttu-id="c09aa-116">**記事** 卸載程式完成之後，下列登錄機碼仍會保留：</span><span class="sxs-lookup"><span data-stu-id="c09aa-116">**Note** The following registry keys remain after the uninstall process is complete:</span></span>

    -   <span data-ttu-id="c09aa-117">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid</span><span class="sxs-lookup"><span data-stu-id="c09aa-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid</span></span>

    -   <span data-ttu-id="c09aa-118">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4。5</span><span class="sxs-lookup"><span data-stu-id="c09aa-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5</span></span>

    -   <span data-ttu-id="c09aa-119">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard "用戶端" = dword：00000000</span><span class="sxs-lookup"><span data-stu-id="c09aa-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard"Client"=dword:00000000</span></span>

    -   <span data-ttu-id="c09aa-120">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey</span><span class="sxs-lookup"><span data-stu-id="c09aa-120">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey</span></span>

     

## <span data-ttu-id="c09aa-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="c09aa-121">Related topics</span></span>


[<span data-ttu-id="c09aa-122">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="c09aa-122">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="c09aa-123">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="c09aa-123">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="c09aa-124">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="c09aa-124">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





