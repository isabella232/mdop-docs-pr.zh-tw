---
title: 管理 AGPM 服務
description: 管理 AGPM 服務
author: dansimp
ms.assetid: a522b1f1-c57b-43aa-9d75-acc6f9bedbf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08749b1b698ff2ec560a5922c5e71138ad31068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802674"
---
# <span data-ttu-id="76315-103">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="76315-103">Managing the AGPM Service</span></span>


<span data-ttu-id="76315-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="76315-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="76315-105">它會強制執行高級的群組原則管理（AGPM）委派，並提供增強的安全性等級。</span><span class="sxs-lookup"><span data-stu-id="76315-105">It enforces Advanced Group Policy Management (AGPM) delegation and provides an enhanced level of security.</span></span> <span data-ttu-id="76315-106">AGPM 服務是位於已安裝 Microsoft 高級群組原則管理-伺服器的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="76315-106">The AGPM Service is hosted on the server on which the Microsoft Advanced Group Policy Management - Server is installed.</span></span>

<span data-ttu-id="76315-107">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="76315-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="76315-108">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="76315-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

-   [<span data-ttu-id="76315-109">啟動和停止 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="76315-109">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service-agpm30ops.md)

-   [<span data-ttu-id="76315-110">修改 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="76315-110">Modify the AGPM Service</span></span>](modify-the-agpm-service-agpm30ops.md)

### <span data-ttu-id="76315-111">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="76315-111">Additional references</span></span>

-   [<span data-ttu-id="76315-112">移動 AGPM 伺服器和封存</span><span class="sxs-lookup"><span data-stu-id="76315-112">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive.md)

-   [<span data-ttu-id="76315-113">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="76315-113">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





