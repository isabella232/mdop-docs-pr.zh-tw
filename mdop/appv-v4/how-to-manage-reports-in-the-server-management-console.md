---
title: 如何在伺服器管理主控台中管理報告
description: 如何在伺服器管理主控台中管理報告
author: dansimp
ms.assetid: 28d99620-6339-43f6-9288-4aa958607c59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3d70734be04df380e6ce3f4ee8de126503e482e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801298"
---
# <span data-ttu-id="77c43-103">如何在伺服器管理主控台中管理報告</span><span class="sxs-lookup"><span data-stu-id="77c43-103">How to Manage Reports in the Server Management Console</span></span>


<span data-ttu-id="77c43-104">若要有效管理應用程式虛擬化系統，您可以使用應用程式虛擬化伺服器管理主控台來產生各種可提供系統資訊的報表。</span><span class="sxs-lookup"><span data-stu-id="77c43-104">To effectively manage the Application Virtualization System, you can use the Application Virtualization Server Management Console to generate a variety of reports that provide information about the system.</span></span> <span data-ttu-id="77c43-105">此資訊包含特定應用程式或所有應用程式的每日使用方式資訊，以及系統錯誤追蹤。</span><span class="sxs-lookup"><span data-stu-id="77c43-105">This information includes daily usage information for a specific application or all applications, and system error tracking.</span></span>

**<span data-ttu-id="77c43-106">注意</span><span class="sxs-lookup"><span data-stu-id="77c43-106">Note</span></span>**  
-   <span data-ttu-id="77c43-107">在安裝期間，安裝腳本只會安裝英文版報表檢視器的語言。</span><span class="sxs-lookup"><span data-stu-id="77c43-107">During installation, the installation script installs only the English language version of report viewer.</span></span> <span data-ttu-id="77c43-108">若要讓報表檢視器以其他語言顯示正確的資訊，必須從以下位置安裝語言套件： <https://go.microsoft.com/fwlink/?LinkId=131645> 。</span><span class="sxs-lookup"><span data-stu-id="77c43-108">For the report viewer to display the correct information in other languages, it is necessary to install a language pack from the following location: <https://go.microsoft.com/fwlink/?LinkId=131645>.</span></span>

-   <span data-ttu-id="77c43-109">當您在伺服器管理主控台中新增或編輯應用程式時，您必須確認應用程式名稱與版本完全符合 OSD 檔案中的專案。</span><span class="sxs-lookup"><span data-stu-id="77c43-109">When you add or edit an application in the Server Management Console, you must make sure that the application names and versions exactly match those in the OSD files.</span></span> <span data-ttu-id="77c43-110">[報告] 功能會在識別要報告其上的應用程式使用資料時，使用 [應用程式名稱] 和 [版本資料] 欄位。</span><span class="sxs-lookup"><span data-stu-id="77c43-110">The reporting feature uses the application names and versions data fields when it identifies application usage data on which to report.</span></span> <span data-ttu-id="77c43-111">如果資料欄位不相符，則會略過使用記錄。</span><span class="sxs-lookup"><span data-stu-id="77c43-111">If the data fields do not match, the usage records will be skipped.</span></span>

 

## <span data-ttu-id="77c43-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="77c43-112">In This Section</span></span>


<a href="" id="application-virtualization-report-types"></a>[<span data-ttu-id="77c43-113">Application Virtualization 報告類型</span><span class="sxs-lookup"><span data-stu-id="77c43-113">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)  
<span data-ttu-id="77c43-114">包含可用報告類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="77c43-114">Contains information about the available report types.</span></span>

<a href="" id="how-to-create-a-report"></a>[<span data-ttu-id="77c43-115">如何建立報告</span><span class="sxs-lookup"><span data-stu-id="77c43-115">How to Create a Report</span></span>](how-to-create-a-reportserver.md)  
<span data-ttu-id="77c43-116">提供建立報表的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="77c43-116">Provides a step-by-step process for creating a report.</span></span>

<a href="" id="how-to-run-a-report"></a>[<span data-ttu-id="77c43-117">如何執行報告</span><span class="sxs-lookup"><span data-stu-id="77c43-117">How to Run a Report</span></span>](how-to-run-a-reportserver.md)  
<span data-ttu-id="77c43-118">提供執行報表的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="77c43-118">Provides a step-by-step process for running a report.</span></span>

<a href="" id="how-to-print-a-report"></a>[<span data-ttu-id="77c43-119">如何列印報告</span><span class="sxs-lookup"><span data-stu-id="77c43-119">How to Print a Report</span></span>](how-to-print-a-reportserver.md)  
<span data-ttu-id="77c43-120">提供列印報表的逐步處理常式。</span><span class="sxs-lookup"><span data-stu-id="77c43-120">Provides a step-by-step process for printing a report.</span></span>

<a href="" id="how-to-export-a-report"></a>[<span data-ttu-id="77c43-121">如何匯出報告</span><span class="sxs-lookup"><span data-stu-id="77c43-121">How to Export a Report</span></span>](how-to-export-a-reportserver.md)  
<span data-ttu-id="77c43-122">提供匯出報表的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="77c43-122">Provides a step-by-step process for exporting a report.</span></span>

<a href="" id="how-to-delete-a-report"></a>[<span data-ttu-id="77c43-123">如何刪除報告</span><span class="sxs-lookup"><span data-stu-id="77c43-123">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)  
<span data-ttu-id="77c43-124">提供刪除報表的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="77c43-124">Provides a step-by-step process for deleting a report.</span></span>

## <span data-ttu-id="77c43-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="77c43-125">Related topics</span></span>


[<span data-ttu-id="77c43-126">應用程式使用報告</span><span class="sxs-lookup"><span data-stu-id="77c43-126">Application Utilization Report</span></span>](application-utilization-reportserver.md)

[<span data-ttu-id="77c43-127">如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作</span><span class="sxs-lookup"><span data-stu-id="77c43-127">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="77c43-128">軟體稽核報告</span><span class="sxs-lookup"><span data-stu-id="77c43-128">Software Audit Report</span></span>](software-audit-reportserver.md)

[<span data-ttu-id="77c43-129">系統錯誤報告</span><span class="sxs-lookup"><span data-stu-id="77c43-129">System Error Report</span></span>](system-error-reportserver.md)

[<span data-ttu-id="77c43-130">系統使用報告</span><span class="sxs-lookup"><span data-stu-id="77c43-130">System Utilization Report</span></span>](system-utilization-reportserver.md)

 

 





