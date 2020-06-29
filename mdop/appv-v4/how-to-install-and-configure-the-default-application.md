---
title: 如何安裝和設定 Default Application
description: 如何安裝和設定 Default Application
author: dansimp
ms.assetid: 5c5d5ad1-af40-4f83-8234-39e972f2c29a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083de7a8ebf94bce0b41c0d3c3edf350a9aff38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801389"
---
# <span data-ttu-id="dc40f-103">如何安裝和設定 Default Application</span><span class="sxs-lookup"><span data-stu-id="dc40f-103">How to Install and Configure the Default Application</span></span>


<span data-ttu-id="dc40f-104">預設的應用程式是在安裝過程中提供，而且會在安裝期間自動複製到 Microsoft Application Virtualization （App-v）管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc40f-104">The default application is provided as part of the installation and is automatically copied to the Microsoft Application Virtualization (App-V) Management Server during installation.</span></span> <span data-ttu-id="dc40f-105">它是用來確認管理伺服器已正確安裝及設定，但必須發佈至 Microsoft Application Virtualization （App-v）用戶端，才能讓使用者存取。</span><span class="sxs-lookup"><span data-stu-id="dc40f-105">It is used to verify that the Management Server was installed and configured correctly, but it has to be published to the Microsoft Application Virtualization (App-V) Client so that the user can access it.</span></span>

<span data-ttu-id="dc40f-106">使用下列程式發佈預設的應用程式，並將它資料流。</span><span class="sxs-lookup"><span data-stu-id="dc40f-106">Use the following procedures to publish the default application and to stream it.</span></span>

**<span data-ttu-id="dc40f-107">發佈預設應用程式</span><span class="sxs-lookup"><span data-stu-id="dc40f-107">To publish the default application</span></span>**

1.  <span data-ttu-id="dc40f-108">使用安裝期間指定的 App-v 系統管理員群組成員的帳戶登入 App-v Management 伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc40f-108">Log on to the App-V Management Server by using an account that is a member of the App-V Administrators group specified during installation.</span></span>

2.  <span data-ttu-id="dc40f-109">在 App-v Management Server 上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [**應用程式虛擬化管理主控台**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-109">On the App-V Management Server, click **Start**, click **Administrative Tools**, and then click **Application Virtualization Management Console**.</span></span>

3.  <span data-ttu-id="dc40f-110">在應用程式 V 管理主控台中，按一下 [**動作**]，然後按一下 **[連線至應用程式虛擬化系統]**。</span><span class="sxs-lookup"><span data-stu-id="dc40f-110">In the App-V Management Console, click **Actions**, and then click **Connect to Application Virtualization System**.</span></span>

4.  <span data-ttu-id="dc40f-111">在 [**設定**連線] 頁面上，清除 [**使用安全**連線] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dc40f-111">On the **Configure Connection** page, clear the **Use Secure Connection** check box.</span></span>

5.  <span data-ttu-id="dc40f-112">在 [ **Web 服務主機名稱**] 方塊中，輸入 App V 管理伺服器的完整功能變數名稱（FQDN），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dc40f-112">In the **Web Service Host Name** box, type the fully qualified domain name (FQDN) of the App-V Management Server, and then click **OK**.</span></span>

    <span data-ttu-id="dc40f-113">**記事** 如果您的 Web 服務主機名稱已安裝在管理伺服器上，您也可以使用**localhost**作為它。</span><span class="sxs-lookup"><span data-stu-id="dc40f-113">**Note** You can also use **localhost** for the Web Service Host name if it is installed on the Management Server.</span></span>

     

6.  <span data-ttu-id="dc40f-114">在 App-v 管理主控台中，以滑鼠右鍵按一下 [**伺服器**] 節點，然後按一下 [**系統選項**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-114">In the App-V Management Console, right-click the **Server** node, and click **System Options**.</span></span>

7.  <span data-ttu-id="dc40f-115">在 [**一般**] 索引標籤的 [**預設內容路徑**] 方塊中，輸入您在安裝期間在伺服器上建立之內容資料夾的通用命名慣例（UNC）路徑;例如，\\ &lt; 伺服器名稱 &gt; \\Content，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dc40f-115">On the **General** tab, in the **Default Content Path** box, enter the Universal Naming Convention (UNC) path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and then click **OK**.</span></span>

    <span data-ttu-id="dc40f-116">**重要** 使用伺服器名稱的 FQDN，即可讓用戶端正確解析名稱。</span><span class="sxs-lookup"><span data-stu-id="dc40f-116">**Important** Use the FQDN for the server name so that the client can resolve the name correctly.</span></span>

     

8.  <span data-ttu-id="dc40f-117">在 App-V 管理主控台的 [功能窗格] 中，展開 [**伺服器**] 節點，然後按一下 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-117">In the App-V Management Console, in the navigation pane, expand the **Server** node, and then click **Applications**.</span></span>

9.  <span data-ttu-id="dc40f-118">在主題窗格中，按一下 [**預設應用程式**]，然後在 [**動作**] 窗格中按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-118">In the topic pane, click **Default Application**, and then, in the **Actions** pane, click **Properties**.</span></span>

10. <span data-ttu-id="dc40f-119">在 [**屬性**] 對話方塊中，按一下 [ **OSD 路徑**] 方塊旁的 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="dc40f-119">In the **Properties** dialog box, next to the **OSD Path** box, click **Browse**.</span></span>

11. <span data-ttu-id="dc40f-120">在 [**開啟**舊檔] 對話方塊中，輸入您在安裝期間在伺服器上建立之內容資料夾的 UNC 路徑;例如，\\ &lt; Server Name &gt; \\Content，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="dc40f-120">In the **Open** dialog box, enter the UNC path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and press ENTER.</span></span> <span data-ttu-id="dc40f-121">您必須使用實際的伺服器名稱，且無法在這裡使用**localhost** 。</span><span class="sxs-lookup"><span data-stu-id="dc40f-121">You must use the actual server name and cannot use the **localhost** here.</span></span>

    <span data-ttu-id="dc40f-122">**重要** 確認**OSD 路徑**和**圖示路徑**方塊中的值都是 UNC 格式（例如，\\ &lt; Server Name &gt; \\Content\\DefaultApp.ico），並指向您在安裝伺服器時所建立的內容資料夾。</span><span class="sxs-lookup"><span data-stu-id="dc40f-122">**Important** Ensure that the values in both the **OSD Path** and **Icon Path** boxes are in UNC format (for example, \\\\&lt;Server Name&gt;\\Content\\DefaultApp.ico), and point to the Content folder you created when installing the server.</span></span> <span data-ttu-id="dc40f-123">請勿使用**localhost**或包含磁片磁碟機盤符的檔案路徑（例如 c:\\program files Files\\..）\\..內容.</span><span class="sxs-lookup"><span data-stu-id="dc40f-123">Do not use **localhost** or a file path containing a drive letter such as C:\\Program Files\\..\\..\\Content.</span></span>

     

12. <span data-ttu-id="dc40f-124">選取 [DefaultApp] 檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-124">Select the DefaultApp.osd file, and click **Open**.</span></span>

13. <span data-ttu-id="dc40f-125">重複上述步驟來設定圖示路徑。</span><span class="sxs-lookup"><span data-stu-id="dc40f-125">Repeat the previous steps to configure the icon path.</span></span>

14. <span data-ttu-id="dc40f-126">按一下 [**存取許可權**] 索引標籤，確認 app-v 使用者群組擁有應用程式的存取許可權。</span><span class="sxs-lookup"><span data-stu-id="dc40f-126">Click the **Access Permissions** tab, and confirm that the App-V Users group has access permissions to the application.</span></span>

15. <span data-ttu-id="dc40f-127">按一下 [**快速鍵**] 索引標籤，然後按一下 [**發佈至使用者的桌面**]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-127">Click the **Shortcuts** tab, and then click **Publish to User’s Desktop**.</span></span> <span data-ttu-id="dc40f-128">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc40f-128">Click **OK**.</span></span>

16. <span data-ttu-id="dc40f-129">開啟 [Windows 資源管理器]，然後找到 [內容目錄]。</span><span class="sxs-lookup"><span data-stu-id="dc40f-129">Open Windows Explorer, and locate the Content directory.</span></span>

17. <span data-ttu-id="dc40f-130">按兩下 DefaultApp 的 .osd 檔案，然後使用記事本開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="dc40f-130">Double-click the DefaultApp.osd file, and open it with Notepad.</span></span>

18. <span data-ttu-id="dc40f-131">找出包含**HREF**標記的那一行，然後將它變更為下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="dc40f-131">Locate the line that contains the **HREF** tag, and change it to the following code:</span></span>

         `CODEBASEHREF=”RTSP://<FQDN of your server>:554/DefaultApp.sft”`

    <span data-ttu-id="dc40f-132">或者，如果您使用的是 RTSPS：</span><span class="sxs-lookup"><span data-stu-id="dc40f-132">Or, if you are using RTSPS:</span></span>

         `CODEBASEHREF=”RTSPS://<FQDN of your server>:322/DefaultApp.sft”`

19. <span data-ttu-id="dc40f-133">關閉 DefaultApp 檔案，然後儲存變更。</span><span class="sxs-lookup"><span data-stu-id="dc40f-133">Close the DefaultApp.osd file, and save the changes.</span></span>

**<span data-ttu-id="dc40f-134">若要將預設的應用程式串流</span><span class="sxs-lookup"><span data-stu-id="dc40f-134">To stream the default application</span></span>**

1.  <span data-ttu-id="dc40f-135">在已安裝應用程式 V 用戶端的電腦上，請以在安裝伺服器期間指定的應用程式虛擬使用者群組成員的使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="dc40f-135">On the computer that has the App-V Client installed, log on as a user who is a member of the Application Virtualization Users group specified during server installation.</span></span>

2.  <span data-ttu-id="dc40f-136">在桌上型電腦上，會出現**預設的應用程式虛擬化應用程式**快捷方式。</span><span class="sxs-lookup"><span data-stu-id="dc40f-136">On the desktop, the **Default Application Virtualization Application** shortcut appears.</span></span> <span data-ttu-id="dc40f-137">按兩下快捷方式以啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc40f-137">Double-click the shortcut to start the application.</span></span>

3.  <span data-ttu-id="dc40f-138">在 Windows 通知區域上方顯示的狀態列，會報告應用程式正在啟動。</span><span class="sxs-lookup"><span data-stu-id="dc40f-138">A status bar, displayed above the Windows notification area, reports that the application is starting.</span></span> <span data-ttu-id="dc40f-139">如果應用程式啟動成功，則會顯示預設應用程式的標題畫面。</span><span class="sxs-lookup"><span data-stu-id="dc40f-139">If the application startup is successful, the title screen for the default application is displayed.</span></span> <span data-ttu-id="dc40f-140">按一下 **[確定**] 以關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="dc40f-140">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="dc40f-141">您現在已確認 App-V 系統正在正常運作。</span><span class="sxs-lookup"><span data-stu-id="dc40f-141">You have now confirmed that the App-V system is running correctly.</span></span>

## <span data-ttu-id="dc40f-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="dc40f-142">Related topics</span></span>


[<span data-ttu-id="dc40f-143">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="dc40f-143">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





