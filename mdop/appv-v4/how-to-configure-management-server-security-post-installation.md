---
title: 如何設定安裝後續管理伺服器安全性
description: 如何設定安裝後續管理伺服器安全性
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801617"
---
# <span data-ttu-id="362a0-103">如何設定安裝後續管理伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="362a0-103">How to Configure Management Server Security Post-Installation</span></span>


<span data-ttu-id="362a0-104">使用 App-v 管理主控台來新增憑證，並設定 App-v Management Server 以增強安全性。</span><span class="sxs-lookup"><span data-stu-id="362a0-104">Use the App-V Management Console to add the certificate and configure the App-V Management Server for enhanced security.</span></span> <span data-ttu-id="362a0-105">您可以使用下列程式來設定安裝後的安全性。</span><span class="sxs-lookup"><span data-stu-id="362a0-105">You can use the following procedure to configure security post-installation.</span></span>

**<span data-ttu-id="362a0-106">設定管理伺服器安全性安裝後</span><span class="sxs-lookup"><span data-stu-id="362a0-106">To configure Management Server security post-installation</span></span>**

1.  <span data-ttu-id="362a0-107">開啟 App-v 管理主控台，然後使用 App-v 管理員許可權連線到**管理服務**。</span><span class="sxs-lookup"><span data-stu-id="362a0-107">Open the App-V Management Console, and connect to the **Management Service** with App-V administrator privileges.</span></span>

2.  <span data-ttu-id="362a0-108">展開 [伺服器]，展開 [**伺服器群組**]，然後選取要用來註冊管理伺服器的適當伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="362a0-108">Expand the server, expand **Server Groups**, and then select the appropriate server group with which the Management Server was registered.</span></span>

3.  <span data-ttu-id="362a0-109">以滑鼠右鍵按一下管理伺服器物件，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="362a0-109">Right-click the Management Server object, and select **Properties**.</span></span>

4.  <span data-ttu-id="362a0-110">在 [**埠**] 索引標籤上，按一下 [**伺服器憑證**] 並完成嚮導，以選取正確提供的憑證。</span><span class="sxs-lookup"><span data-stu-id="362a0-110">On the **Ports** tab, click **Server Certificate** and complete the wizard to select the properly provisioned certificate.</span></span>

    <span data-ttu-id="362a0-111">**記事** 如果嚮導中沒有顯示任何憑證，則憑證尚未提供，或憑證符合 App-v 的需求。</span><span class="sxs-lookup"><span data-stu-id="362a0-111">**Note** If no certificates are displayed in the wizard, a certificate has not been provisioned or the certificate does meet the requirements of App-V.</span></span>

     

5.  <span data-ttu-id="362a0-112">按一下 **[下一步**]，繼續至 [**歡迎使用憑證] 嚮導**頁面。</span><span class="sxs-lookup"><span data-stu-id="362a0-112">Click **Next** to continue on to the **Welcome To Certificate Wizard** page.</span></span>

6.  <span data-ttu-id="362a0-113">在 [**可用的憑證**] 畫面中選取正確的憑證。</span><span class="sxs-lookup"><span data-stu-id="362a0-113">Select the correct certificate in the **Available Certificates** screen.</span></span>

7.  <span data-ttu-id="362a0-114">按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="362a0-114">Click **Finish**.</span></span>

8.  <span data-ttu-id="362a0-115">完成嚮導之後，清除 [ **RTSP** ] 做為可用的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="362a0-115">After completing the wizard, clear **RTSP** as an available listening port.</span></span> <span data-ttu-id="362a0-116">這可防止透過不安全的通訊通道進行連線。</span><span class="sxs-lookup"><span data-stu-id="362a0-116">This prevents connections from being made over a non-secure communication channel.</span></span>

9.  <span data-ttu-id="362a0-117">按一下 **[** 套用]，然後重新開機**Microsoft 虛擬應用程式伺服器**服務。</span><span class="sxs-lookup"><span data-stu-id="362a0-117">Click **Apply**, and restart the **Microsoft Virtual Application Server** service.</span></span> <span data-ttu-id="362a0-118">使用服務的 MMC 管理單元來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="362a0-118">Use the service’s MMC snap-in to accomplish this task.</span></span>

## <span data-ttu-id="362a0-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="362a0-119">Related topics</span></span>


[<span data-ttu-id="362a0-120">如何設定安裝後續串流伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="362a0-120">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)

[<span data-ttu-id="362a0-121">疑難排解憑證權限問題</span><span class="sxs-lookup"><span data-stu-id="362a0-121">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)

 

 





