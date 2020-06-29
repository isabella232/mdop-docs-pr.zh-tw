---
title: 如何安裝 MED-V 用戶端及 MED-V 管理主控台
description: 如何安裝 MED-V 用戶端及 MED-V 管理主控台
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812081"
---
# <span data-ttu-id="8ea21-103">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="8ea21-103">How to Install MED-V Client and MED-V Management Console</span></span>


<span data-ttu-id="8ea21-104">用戶端 .msi 套件包含下列 MED-V 元件：</span><span class="sxs-lookup"><span data-stu-id="8ea21-104">The following MED-V components are included in the client .msi package:</span></span>

-   <span data-ttu-id="8ea21-105">MED-V 用戶端：必須在用戶端電腦上安裝 MED-V-V 工作區的 MED-V 軟體。</span><span class="sxs-lookup"><span data-stu-id="8ea21-105">MED-V client—The MED-V software that must be installed on client computers for running MED-V workspaces.</span></span>

-   <span data-ttu-id="8ea21-106">MED-V 管理主控台-系統管理員可用來建立及維護影像、MED-V 工作區及原則的管理工具。</span><span class="sxs-lookup"><span data-stu-id="8ea21-106">MED-V management console—The administrative tool that administrators can use to create and maintain images, MED-V workspaces, and policies.</span></span>

<span data-ttu-id="8ea21-107">MED-V 管理主控台和 MED-V 用戶端都是從 MED-V 用戶端的 .msi 套件進行安裝。</span><span class="sxs-lookup"><span data-stu-id="8ea21-107">The MED-V management console and the MED-V client are both installed from the MED-V client .msi package.</span></span> <span data-ttu-id="8ea21-108">不過，您可以在安裝期間清除 [**安裝 Med-v 管理應用程式**] 核取方塊，以在沒有 med-v 管理主控台的情況下獨立安裝 med-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8ea21-108">The MED-V client, however, can be installed independently without the MED-V management console by clearing the **Install the MED-V Management application** check box during installation.</span></span>

**<span data-ttu-id="8ea21-109">注意</span><span class="sxs-lookup"><span data-stu-id="8ea21-109">Note</span></span>**  
<span data-ttu-id="8ea21-110">MED-V 用戶端和 MED-V 管理主控台只能安裝在 Windows 7、Windows Vista 和 Windows XP 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="8ea21-110">The MED-V client and MED-V management console can only be installed on Windows 7-, Windows Vista-, and Windows XP-based computers.</span></span> <span data-ttu-id="8ea21-111">無法在伺服器產品上安裝它們。</span><span class="sxs-lookup"><span data-stu-id="8ea21-111">They cannot be installed on server products.</span></span>



**<span data-ttu-id="8ea21-112">注意</span><span class="sxs-lookup"><span data-stu-id="8ea21-112">Note</span></span>**  
<span data-ttu-id="8ea21-113">請勿使用 Windows **runas**命令安裝 med-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8ea21-113">Do not install the MED-V client using the Windows **runas** command.</span></span>



**<span data-ttu-id="8ea21-114">安裝 MED-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="8ea21-114">To install the MED-V client</span></span>**

1.  <span data-ttu-id="8ea21-115">以擁有本機系統管理員許可權的使用者身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="8ea21-115">Log in as a user with local administrator rights on the local computer.</span></span>

2.  <span data-ttu-id="8ea21-116">執行 MED-V 封裝。</span><span class="sxs-lookup"><span data-stu-id="8ea21-116">Run the MED-V .msi package.</span></span>

    <span data-ttu-id="8ea21-117">會呼叫 MED-V 封裝*MED-V\_x.msi*，其中*x*是版本號碼。</span><span class="sxs-lookup"><span data-stu-id="8ea21-117">The MED-V .msi package is called *MED-V\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="8ea21-118">例如， *MED-V\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="8ea21-118">For example, *MED-V\_1.0.65.msi*.</span></span>

3.  <span data-ttu-id="8ea21-119">出現**InstallShield 嚮導歡迎**畫面時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8ea21-119">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

4.  <span data-ttu-id="8ea21-120">在 [**授權合約**] 畫面上，閱讀 [授權合約]，按一下 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8ea21-120">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and click **Next**.</span></span>

    <span data-ttu-id="8ea21-121">[**目的地資料夾**] 畫面隨即出現，並顯示預設安裝資料夾。</span><span class="sxs-lookup"><span data-stu-id="8ea21-121">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="8ea21-122">預設的 [安裝] 資料夾是安裝作業系統的目錄。</span><span class="sxs-lookup"><span data-stu-id="8ea21-122">The default installation folder is the directory where the operating system is installed.</span></span>

    -   <span data-ttu-id="8ea21-123">若要變更要安裝 MED-V 的資料夾，請按一下 [**變更**]，然後流覽至現有的資料夾。</span><span class="sxs-lookup"><span data-stu-id="8ea21-123">To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.</span></span>

5.  <span data-ttu-id="8ea21-124">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="8ea21-124">Click **Next**.</span></span>

6.  <span data-ttu-id="8ea21-125">在**med-v [設定**] 畫面上，設定 med-v 安裝，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8ea21-125">On the **MED-V Settings** screen, configure the MED-V installation as follows:</span></span>

    -   <span data-ttu-id="8ea21-126">選取 [**安裝 med-v 管理應用程式**] 核取方塊，以在安裝中包含管理元件。</span><span class="sxs-lookup"><span data-stu-id="8ea21-126">Select the **Install the MED-V management application** check box to include the management component in the installation.</span></span>

        **<span data-ttu-id="8ea21-127">注意</span><span class="sxs-lookup"><span data-stu-id="8ea21-127">Note</span></span>**  
        <span data-ttu-id="8ea21-128">企業桌面虛擬化管理員應該安裝 MED-V 管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ea21-128">Enterprise Desktop Virtualization administrators should install the MED-V management application.</span></span> <span data-ttu-id="8ea21-129">這個應用程式是設定桌面影像和 MED-V 工作區所必需的。</span><span class="sxs-lookup"><span data-stu-id="8ea21-129">This application is required for configuring desktop images and MED-V workspaces.</span></span>



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. <span data-ttu-id="8ea21-130">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="8ea21-130">Click **Next**.</span></span>

8. <span data-ttu-id="8ea21-131">在 [**準備好安裝程式**] 畫面中，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="8ea21-131">On the **Ready to Install the Program** screen, click **Install**.</span></span>

   <span data-ttu-id="8ea21-132">MED-V 用戶端安裝隨即啟動。</span><span class="sxs-lookup"><span data-stu-id="8ea21-132">The MED-V client installation starts.</span></span> <span data-ttu-id="8ea21-133">這可能需要幾分鐘的時間，而且螢幕可能不會顯示文字。</span><span class="sxs-lookup"><span data-stu-id="8ea21-133">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="8ea21-134">在安裝期間，會出現幾個進度畫面。</span><span class="sxs-lookup"><span data-stu-id="8ea21-134">During installation, several progress screens appear.</span></span> <span data-ttu-id="8ea21-135">如果出現訊息，請依照提供的指示進行。</span><span class="sxs-lookup"><span data-stu-id="8ea21-135">If a message appears, follow the instructions provided.</span></span>

   <span data-ttu-id="8ea21-136">成功安裝後，就會出現 [ **InstallShield 嚮導完成]** 畫面。</span><span class="sxs-lookup"><span data-stu-id="8ea21-136">Upon successful installation, the **InstallShield Wizard Completed** screen appears.</span></span>

9. <span data-ttu-id="8ea21-137">按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="8ea21-137">Click **Finish** to close the wizard.</span></span>

## <span data-ttu-id="8ea21-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="8ea21-138">Related topics</span></span>


[<span data-ttu-id="8ea21-139">支援的設定</span><span class="sxs-lookup"><span data-stu-id="8ea21-139">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="8ea21-140">安裝和升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="8ea21-140">Installation and Upgrade Checklists</span></span>](installation-and-upgrade-checklists.md)









