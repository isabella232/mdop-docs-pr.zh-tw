---
title: 管理 AGPM 服務
description: 管理 AGPM 服務
author: dansimp
ms.assetid: 331f64d2-1236-4711-81b4-1b92f019bfa5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3247be846487ba6d80f30a55654b20b3db96e219
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802670"
---
# <span data-ttu-id="9584d-103">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9584d-103">Managing the AGPM Service</span></span>


<span data-ttu-id="9584d-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="9584d-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="9584d-105">它會強制執行高級的群組原則管理（AGPM）委派，並提供增強的安全性等級。</span><span class="sxs-lookup"><span data-stu-id="9584d-105">It enforces Advanced Group Policy Management (AGPM) delegation and provides an enhanced level of security.</span></span> <span data-ttu-id="9584d-106">AGPM 服務是位於已安裝 Microsoft 高級群組原則管理-伺服器的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9584d-106">The AGPM Service is hosted on the server on which the Microsoft Advanced Group Policy Management - Server is installed.</span></span>

<span data-ttu-id="9584d-107">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="9584d-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="9584d-108">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="9584d-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

-   [<span data-ttu-id="9584d-109">啟動和停止 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="9584d-109">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service.md)

-   [<span data-ttu-id="9584d-110">修改封存路徑</span><span class="sxs-lookup"><span data-stu-id="9584d-110">Modify the Archive Path</span></span>](modify-the-archive-path.md)

-   [<span data-ttu-id="9584d-111">修改 AGPM 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="9584d-111">Modify the AGPM Service Account</span></span>](modify-the-agpm-service-account.md)

-   [<span data-ttu-id="9584d-112">修改 AGPM 服務接聽的連接埠</span><span class="sxs-lookup"><span data-stu-id="9584d-112">Modify the Port on Which the AGPM Service Listens</span></span>](modify-the-port-on-which-the-agpm-service-listens.md)

 

 





