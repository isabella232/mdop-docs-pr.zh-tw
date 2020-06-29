---
title: 關於 Microsoft Application Virtualization 4.5
description: 關於 Microsoft Application Virtualization 4.5
author: dansimp
ms.assetid: 39f45a6f-ac55-4fd7-8a83-865e1a7034f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 30f285680ab24e9c638ff8a200946925074bddf1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802453"
---
# <span data-ttu-id="c05f4-103">關於 Microsoft Application Virtualization 4.5</span><span class="sxs-lookup"><span data-stu-id="c05f4-103">About Microsoft Application Virtualization 4.5</span></span>


<span data-ttu-id="c05f4-104">Microsoft Application Virtualization （App-v）4.5 是本產品的第一次 Microsoft 署名版本，在先前稱為 SoftGrid 應用程式虛擬化。</span><span class="sxs-lookup"><span data-stu-id="c05f4-104">Formerly known as SoftGrid Application Virtualization, Microsoft Application Virtualization (App-V) 4.5 is the first Microsoft-branded release of the product.</span></span> <span data-ttu-id="c05f4-105">它包含的新功能可讓企業 IT 組織輕鬆支援大型、全域應用程式虛擬化實現。</span><span class="sxs-lookup"><span data-stu-id="c05f4-105">It includes new capabilities that make it easy for enterprise IT organizations to support large-scale, global application virtualization implementations.</span></span>

-   <span data-ttu-id="c05f4-106">動態虛擬化： App-v 4.5 可讓您靈活地控制虛擬應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="c05f4-106">Dynamic Virtualization: App-V 4.5 provides the flexibility to control virtual application interaction.</span></span> <span data-ttu-id="c05f4-107">如果系統管理員想要整合虛擬環境，並更快速、更輕鬆地管理，可以使用產品的動態套件組合，這會將中介軟體應用程式的序列化與管理的中介軟體應用程式組成套件。</span><span class="sxs-lookup"><span data-stu-id="c05f4-107">Administrators who want to consolidate virtual environments and enable faster, easier administration, can use the product’s Dynamic Suite Composition, which sequences and manages packages for middleware applications separately from the main application.</span></span> <span data-ttu-id="c05f4-108">它會透過消除中介軟體的多餘封裝來縮小可能的套件大小。</span><span class="sxs-lookup"><span data-stu-id="c05f4-108">It shrinks potential package size by eliminating redundant packaging of middleware.</span></span> <span data-ttu-id="c05f4-109">這可讓多個 Web 應用程式與同一個虛擬化應用程式的單一實例（例如 Microsoft .NET Framework 或 Sun JAVA 執行時間環境（JRE））進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c05f4-109">This lets multiple Web applications communicate with the same single instance of a virtualized application of, for example, Microsoft .NET Framework or Sun Java Runtime Environment (JRE).</span></span> <span data-ttu-id="c05f4-110">通用虛擬中介軟體的更新會簡化，且會更新一個虛擬應用程式（而不是數個）。</span><span class="sxs-lookup"><span data-stu-id="c05f4-110">Updates for the common virtual middleware are simplified and one virtual application is updated instead of several.</span></span> <span data-ttu-id="c05f4-111">這種 "多對一" 功能可大大減少更新成本。</span><span class="sxs-lookup"><span data-stu-id="c05f4-111">This “many-to-one” capability greatly reduces the cost of updates.</span></span> <span data-ttu-id="c05f4-112">它也可讓您更輕鬆地部署和管理使用多個外掛程式和增益集的應用程式，並將外掛程式發佈的管理功能提升至不同的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="c05f4-112">It also makes it easier to deploy and manage applications that use multiple plug-ins and add-ins, and improves management of plug-in distribution to different user groups.</span></span>

-   <span data-ttu-id="c05f4-113">延伸擴充能力：在三個靈活的部署模式之間選擇：</span><span class="sxs-lookup"><span data-stu-id="c05f4-113">Extended Scalability: Choose among three flexible deployment modes:</span></span>

    1.  <span data-ttu-id="c05f4-114">應用程式虛擬化管理伺服器隨附于 Microsoft 桌上出版的優化套件，以及適用于遠端桌面服務套件的 Microsoft Application Virtualization，可啟用動態資料流，包括套件和活動升級，以及需要 Microsoft Active Directory 網域服務與 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c05f4-114">Application Virtualization Management Server, which ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, enables dynamic streaming including package and active upgrades, and requires Microsoft Active Directory Domain Services and Microsoft SQL Server.</span></span>

    2.  <span data-ttu-id="c05f4-115">應用程式虛擬化流式處理伺服器（一種精簡版本），也會隨 Microsoft 桌面服務套件的 microsoft 桌面優化套件和 Microsoft Application Virtualization 提供，提供應用程式資料流程，包括不含 Active Directory 網域服務與資料庫開銷的封裝及作用中升級，並可讓系統管理員部署至現有的伺服器，或新增資料流程至電子軟體傳送（ESD）系統。</span><span class="sxs-lookup"><span data-stu-id="c05f4-115">Application Virtualization Streaming Server, a lightweight version which also ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, offers application streaming including package and active upgrades without the Active Directory Domain Services and database overheads, and enables administrators to deploy to existing servers or add streaming to Electronic Software Delivery (ESD) systems.</span></span>

    3.  <span data-ttu-id="c05f4-116">獨立模式可讓虛擬應用程式在沒有資料流程的情況下執行，且可與 Microsoft 端點設定管理員和協力廠商 ESD 系統交互操作。</span><span class="sxs-lookup"><span data-stu-id="c05f4-116">Standalone mode enables virtual applications to run without streaming and is interoperable with Microsoft Endpoint Configuration Manager and third-party ESD systems.</span></span>

-   <span data-ttu-id="c05f4-117">全球化：此產品是透過11種語言當地語系化，包括支援使用特殊字元的外語語言應用程式，以及支援外語語言 Active Directory 和伺服器以及執行時間地區偵測。</span><span class="sxs-lookup"><span data-stu-id="c05f4-117">Globalization: The product is localized across 11 languages, includes support for foreign language applications that use special characters, and supports foreign language Active Directory and servers and runtime locale detection.</span></span>

-   <span data-ttu-id="c05f4-118">Microsoft Security 標準： Microsoft Application Virtualization （App-v）4.5 遵循 Microsoft 安全標準（包括可信賴的計算、安全的 Windows 方案與安全性開發週期）。</span><span class="sxs-lookup"><span data-stu-id="c05f4-118">Microsoft Security Standards: Microsoft Application Virtualization (App-V) 4.5 complies with Microsoft security standards including Trustworthy Computing, Secure Windows Initiative and Security Development Lifecycle.</span></span> <span data-ttu-id="c05f4-119">它包含支援網際網路案例，並根據預設設定提供安全。</span><span class="sxs-lookup"><span data-stu-id="c05f4-119">It includes support for Internet-facing scenarios and provides Secure by Default configuration out of the box.</span></span>

## <span data-ttu-id="c05f4-120">本節內容</span><span class="sxs-lookup"><span data-stu-id="c05f4-120">In This Section</span></span>


<a href="" id="microsoft-application-virtualization-management-system-release-notes"></a>[<span data-ttu-id="c05f4-121">Microsoft Application Virtualization 管理系統版本資訊</span><span class="sxs-lookup"><span data-stu-id="c05f4-121">Microsoft Application Virtualization Management System Release Notes</span></span>](microsoft-application-virtualization-management-system-release-notes.md)  
<span data-ttu-id="c05f4-122">提供 Microsoft Application Virtualization （App-v）4.5 已知問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="c05f4-122">Provides the most up-to-date information about known issues with Microsoft Application Virtualization (App-V) 4.5.</span></span>

 

 





