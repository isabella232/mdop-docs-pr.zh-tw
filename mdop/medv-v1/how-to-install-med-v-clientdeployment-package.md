---
title: 如何安裝 MED-V 用戶端
description: 如何安裝 MED-V 用戶端
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812207"
---
# <span data-ttu-id="c8c06-103">如何安裝 MED-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="c8c06-103">How to Install MED-V Client</span></span>


<span data-ttu-id="c8c06-104">在部署套件的案例中，MED-V 用戶端安裝包含在部署套件中，並直接從套件安裝。</span><span class="sxs-lookup"><span data-stu-id="c8c06-104">In a deployment package-based scenario, the MED-V client installation is included in the deployment package and installed directly from the package.</span></span>

**<span data-ttu-id="c8c06-105">重要</span><span class="sxs-lookup"><span data-stu-id="c8c06-105">Important</span></span>**  
<span data-ttu-id="c8c06-106">使用不含影像的部署套件時，請務必先將影像上傳至網路，或是將它推到前階段資料夾，然後再安裝部署套件。</span><span class="sxs-lookup"><span data-stu-id="c8c06-106">When using a deployment package that does not include an image, ensure that the image is uploaded to the Web or pushed to the pre-stage folder prior to installing the deployment package.</span></span>



**<span data-ttu-id="c8c06-107">若要安裝部署套件</span><span class="sxs-lookup"><span data-stu-id="c8c06-107">To install a deployment package</span></span>**

1.  <span data-ttu-id="c8c06-108">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c8c06-108">Do one of the following:</span></span>

    -   <span data-ttu-id="c8c06-109">從網路下載 MED-V 套件。</span><span class="sxs-lookup"><span data-stu-id="c8c06-109">Download the MED-V package from the Web.</span></span>

    -   <span data-ttu-id="c8c06-110">將部署 USB 或 DVD 插入主機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="c8c06-110">Insert the deployment USB or DVD into the host drive.</span></span>

2.  <span data-ttu-id="c8c06-111">如果 MED-V 沒有自動啟動，請按兩下 [MED-VAutoInstaller.exe]。</span><span class="sxs-lookup"><span data-stu-id="c8c06-111">If MED-V does not launch automatically, double-click MED-VAutoInstaller.exe.</span></span>

    <span data-ttu-id="c8c06-112">隨即會出現一個對話方塊，其中列出已安裝的元件，以及目前正在安裝的元件。</span><span class="sxs-lookup"><span data-stu-id="c8c06-112">A dialog box appears listing the components that are already installed and those that are currently being installed.</span></span>

    **<span data-ttu-id="c8c06-113">注意</span><span class="sxs-lookup"><span data-stu-id="c8c06-113">Note</span></span>**  
    <span data-ttu-id="c8c06-114">如果主機電腦上存在不支援的 Microsoft 虛擬電腦版本，則會顯示一則訊息，告訴您要卸載現有版本並再次執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="c8c06-114">If a version of the Microsoft Virtual PC that is not supported exists on the host computer, a message will appear telling you to uninstall the existing version and run the installer again.</span></span>



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. <span data-ttu-id="c8c06-115">如有需要，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="c8c06-115">If necessary, reboot the computer.</span></span>

   <span data-ttu-id="c8c06-116">安裝完成後，MED-V 隨即啟動，並出現一則訊息，通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="c8c06-116">When the installation is complete, MED-V starts and a message appears notifying you that the installation is complete.</span></span>

4. <span data-ttu-id="c8c06-117">使用下列使用者名稱和密碼登入 MED-V：</span><span class="sxs-lookup"><span data-stu-id="c8c06-117">Log in to MED-V using the following user name and password:</span></span>

   -   <span data-ttu-id="c8c06-118">輸入網功能變數名稱稱和使用者名稱，後面接著允許在 MED-V 中使用之網域使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="c8c06-118">Type in the domain name and user name followed by the password of the domain user who is permitted to work with MED-V.</span></span>

       <span data-ttu-id="c8c06-119">範例：「網域 \ _name \\user\ _name "，" password "</span><span class="sxs-lookup"><span data-stu-id="c8c06-119">Example: "domain\_name\\user\_name", "password"</span></span>

## <span data-ttu-id="c8c06-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="c8c06-120">Related topics</span></span>


[<span data-ttu-id="c8c06-121">如何設定部署套件</span><span class="sxs-lookup"><span data-stu-id="c8c06-121">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

[<span data-ttu-id="c8c06-122">如何上傳 MED-V 映像至伺服器</span><span class="sxs-lookup"><span data-stu-id="c8c06-122">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="c8c06-123">用戶端安裝命令列參考資料</span><span class="sxs-lookup"><span data-stu-id="c8c06-123">Client Installation Command Line Reference</span></span>](client-installation-command-line-reference.md)









