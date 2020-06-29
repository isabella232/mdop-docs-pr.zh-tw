---
title: 啟動和停止 AGPM 服務
description: 啟動和停止 AGPM 服務
author: dansimp
ms.assetid: 769aa0ce-224a-446f-9958-9518af4ad159
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 33e797182d49157da0fe8f36dce17b4b35cdd623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801770"
---
# <span data-ttu-id="9fc8b-103">啟動和停止 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9fc8b-103">Start and Stop the AGPM Service</span></span>


<span data-ttu-id="9fc8b-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span>

<span data-ttu-id="9fc8b-105">**重要** 停止或停用 AGPM 服務將會防止 AGPM 用戶端透過伺服器執行任何操作（例如列出或編輯 Gpo）。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-105">**Important** Stopping or disabling the AGPM Service will prevent AGPM clients from performing any operations (such as listing or editing GPOs) through the server.</span></span>

 

<span data-ttu-id="9fc8b-106">需要擁有 AGPM 服務器存取權的使用者帳戶（安裝了 AGPM 服務的電腦），才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-106">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="9fc8b-107">啟動或停止 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9fc8b-107">To start or stop the AGPM Service</span></span>**

1.  <span data-ttu-id="9fc8b-108">在已安裝 Microsoft 高級群組原則管理-伺服器（以及 AGPM 服務）的電腦上，按一下 [**開始**]，按一下 [**控制台**]，按一下 [**管理工具**]，然後按一下 [**服務**]。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-108">On the computer on which Microsoft Advanced Group Policy Management - Server (and therefore the AGPM Service) is installed, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **Services**.</span></span>

2.  <span data-ttu-id="9fc8b-109">在服務清單中，以滑鼠右鍵按一下 [ **AGPM 服務**]，然後選取 [**開始**]、[**重新開機**] 或 [**停止**]。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-109">In the list of services, right-click **AGPM Service** and select **Start**, **Restart**, or **Stop**.</span></span>

    <span data-ttu-id="9fc8b-110">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-110">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="9fc8b-111">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-111">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="9fc8b-112">若要修改服務的設定，請參閱[管理 AGPM 服務](managing-the-agpm-service.md)。</span><span class="sxs-lookup"><span data-stu-id="9fc8b-112">To modify settings for the service, see [Managing the AGPM Service](managing-the-agpm-service.md).</span></span>

     

### <span data-ttu-id="9fc8b-113">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="9fc8b-113">Additional references</span></span>

-   [<span data-ttu-id="9fc8b-114">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9fc8b-114">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





