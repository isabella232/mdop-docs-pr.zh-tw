---
title: 如何安裝管理主控台
description: 如何安裝管理主控台
author: dansimp
ms.assetid: 586d99c8-bca6-42e2-a39c-a696053142f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48f4f69753794cf8099df36828e0502e98414b31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801362"
---
# <span data-ttu-id="ccaa6-103">如何安裝管理主控台</span><span class="sxs-lookup"><span data-stu-id="ccaa6-103">How to Install the Management Console</span></span>


<span data-ttu-id="ccaa6-104">您可以使用下列程式，在網路上的目的電腦上安裝應用程式虛擬化管理主控台。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-104">You can use the following procedure to install the Application Virtualization Management Console on a target computer on the network.</span></span> <span data-ttu-id="ccaa6-105">您必須使用在目的電腦上具有系統管理員許可權的網路帳戶。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-105">You must use a network account that has administrator privileges on the target computer.</span></span> <span data-ttu-id="ccaa6-106">您可以使用主控台來設定和管理應用程式虛擬化系統平臺。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-106">You can use the console to configure and manage the Application Virtualization System Platform.</span></span>

<span data-ttu-id="ccaa6-107">您必須先在這或不同的電腦上安裝應用程式虛擬化管理 Web 服務，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-107">Before you can complete this procedure, you must install the Application Virtualization Management Web Service on this or a different computer.</span></span> <span data-ttu-id="ccaa6-108">管理 Web 服務可讓您存取資料儲存區和網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-108">The Management Web Service allows you to access the data store and the domain controller.</span></span> <span data-ttu-id="ccaa6-109">如需安裝 Web 服務的詳細資訊，請參閱[如何安裝管理 Web 服務](how-to-install-the-management-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-109">For more information about installing the Web service, see [How to Install the Management Web Service](how-to-install-the-management-web-service.md).</span></span>

**<span data-ttu-id="ccaa6-110">若要安裝管理主控台</span><span class="sxs-lookup"><span data-stu-id="ccaa6-110">To install the Management Console</span></span>**

1.  <span data-ttu-id="ccaa6-111">確認沒有在目的電腦上安裝任何舊版的管理主控台。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-111">Verify that no previous versions of the Management Console are installed on the target computer.</span></span>

2.  <span data-ttu-id="ccaa6-112">流覽至 [應用程式虛擬化系統] 設定程式在網路上的位置，請從網路執行此程式，或將其目錄複寫到目的電腦，然後按兩下 [ **Setup.exe**]。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-112">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="ccaa6-113">在 [**歡迎] 頁面**上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-113">On the **Welcome Page**, click **Next**.</span></span>

4.  <span data-ttu-id="ccaa6-114">若要接受授權協定，請在 [**授權協定**] 頁面上，選取 [**我接受授權條款及條件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-114">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="ccaa6-115">在 [**註冊資訊**] 頁面上，指定**使用者名稱**和**組織**資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-115">On the **Registration Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

6.  <span data-ttu-id="ccaa6-116">按一下 [**安裝類型**] 頁面上的 [**自訂**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-116">On the **Setup Type** page, click **Custom** and then click **Next**.</span></span>

7.  <span data-ttu-id="ccaa6-117">在 [**自訂安裝**] 頁面上，取消選取 [**管理主控台**以外的所有應用程式虛擬化系統元件]，然後按 **[下一步**</span><span class="sxs-lookup"><span data-stu-id="ccaa6-117">On the **Custom Setup** page, deselect all Application Virtualization System components except **Management Console**, and then click **Next**.</span></span>

    <span data-ttu-id="ccaa6-118">**記事** 如果電腦上已安裝元件，請在 [自訂安裝程式] 畫面上取消選擇該元件，系統會自動將它卸載。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-118">**Note** If a component is already installed on the computer, by deselecting it on the Custom Setup screen, it will automatically be uninstalled.</span></span>

     

8.  <span data-ttu-id="ccaa6-119">在 [**準備修改程式**] 畫面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-119">On the **Ready to Modify the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="ccaa6-120">**記事** 如果這是您安裝的第一個元件，就會顯示 [已**準備好安裝程式**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-120">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="ccaa6-121">若要開始安裝，請按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-121">To start the installation, click **Install**.</span></span>

     

9.  <span data-ttu-id="ccaa6-122">在 [**安裝精靈完成]** 畫面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-122">On the **Installation Wizard Completed** screen, click **Finish**.</span></span> <span data-ttu-id="ccaa6-123">按一下 **[** 確定] 以重新開機電腦並完成安裝。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-123">Click **Okay** to restart the computer and complete the installation.</span></span>

10. <span data-ttu-id="ccaa6-124">在 Windows [控制台] 中，按兩下 [系統**管理工具**]，然後按一下 [**應用程式虛擬化管理主控台**] 以顯示管理主控台。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-124">In the Windows Control Panel, double-click **Administrative Tools** and then click **Application Virtualization Management Console** to display the Management Console.</span></span>

11. <span data-ttu-id="ccaa6-125">按一下 [**連接]** 圖示，或以滑鼠右鍵按一下 [**應用程式虛擬機器系統**] 容器，然後按一下 **[連線至應用程式虛擬化系統]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-125">Click the **Connect** icon, or right-click the **Application Virtualization Systems** container, and then click **Connect to Application Virtualization System**.</span></span>

12. <span data-ttu-id="ccaa6-126">在 [連線**至應用程式虛擬化系統]** 畫面上，輸入管理 Web 服務電腦的主機名稱和埠，視需要變更安全性資訊和登入認證，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-126">On the **Connect to Application Virtualization System** screen, enter the host name and port of the Management Web Service computer, change the security information and login credentials if necessary, and then click **OK**.</span></span>

13. <span data-ttu-id="ccaa6-127">連線至管理 Web 服務電腦後 **，按一下 [\*\*\*\*主控台**] 功能表上的 [檔案]，**然後按一下 [** 結束]。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-127">After connecting to the Management Web Service computer, click **File** on the **Console** menu, and then click **Exit**.</span></span> <span data-ttu-id="ccaa6-128">按一下 **[是]** 以儲存主控台設定。</span><span class="sxs-lookup"><span data-stu-id="ccaa6-128">Click **Yes** to save console settings.</span></span>

## <span data-ttu-id="ccaa6-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="ccaa6-129">Related topics</span></span>


[<span data-ttu-id="ccaa6-130">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="ccaa6-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





