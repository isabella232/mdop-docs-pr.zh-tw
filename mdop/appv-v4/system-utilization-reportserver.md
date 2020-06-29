---
title: 系統使用報告
description: 系統使用報告
author: dansimp
ms.assetid: 4d490d15-2d1f-4f2c-99bb-0685447c0672
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe7ff547d969c63ace234104c3e6b7146da2c113
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800782"
---
# <span data-ttu-id="425a9-103">系統使用報告</span><span class="sxs-lookup"><span data-stu-id="425a9-103">System Utilization Report</span></span>


<span data-ttu-id="425a9-104">使用 [系統利用率] 報告來繪製每日系統使用方式的圖表。</span><span class="sxs-lookup"><span data-stu-id="425a9-104">Use the System Utilization Report to graph the total daily system usage.</span></span> <span data-ttu-id="425a9-105">您可以使用這個報告來判斷您的應用程式虛擬化系統上的負載。</span><span class="sxs-lookup"><span data-stu-id="425a9-105">You can use this report to determine the load on your Application Virtualization System.</span></span>

<span data-ttu-id="425a9-106">此報告在報告期間內追蹤指定伺服器或伺服器群組的使用方式。</span><span class="sxs-lookup"><span data-stu-id="425a9-106">This report tracks the usage over time during the reporting period for the specified server or for the server group.</span></span>

<span data-ttu-id="425a9-107">[系統使用量] 報告也會在下列系統使用量圖中圖形：</span><span class="sxs-lookup"><span data-stu-id="425a9-107">The System Utilization Report also graphs the following system usage:</span></span>

-   <span data-ttu-id="425a9-108">依周天數的使用方式</span><span class="sxs-lookup"><span data-stu-id="425a9-108">Usage by day of the week</span></span>

-   <span data-ttu-id="425a9-109">依日小時的使用量</span><span class="sxs-lookup"><span data-stu-id="425a9-109">Usage by hour of the day</span></span>

<span data-ttu-id="425a9-110">[系統利用率] 報告也包含特定使用者的總系統使用量及總會話計數的摘要。</span><span class="sxs-lookup"><span data-stu-id="425a9-110">The System Utilization Report also includes a summary of the total system usage for specific users and total session counts.</span></span>

<span data-ttu-id="425a9-111">當您建立報表時，您可以指定在執行報表時用於收集資料的參數。</span><span class="sxs-lookup"><span data-stu-id="425a9-111">When you create a report, you specify the parameters that are used for collecting the data when the report is run.</span></span>

<span data-ttu-id="425a9-112">報表不會自動執行;您必須明確執行這些規則，才能產生輸出資料。</span><span class="sxs-lookup"><span data-stu-id="425a9-112">Reports are not run automatically; you must run them explicitly to generate output data.</span></span> <span data-ttu-id="425a9-113">執行此報告所需的時間長度取決於資料存放區中收集的資料量。</span><span class="sxs-lookup"><span data-stu-id="425a9-113">The length of time it takes to run this report is determined by the amount of data collected in the data store.</span></span>

<span data-ttu-id="425a9-114">在您執行報表並顯示 [應用程式虛擬化伺服器管理] 主控台中的輸出之後，您可以將報表匯出成下列格式：</span><span class="sxs-lookup"><span data-stu-id="425a9-114">After you run a report and the output is displayed in the Application Virtualization Server Management Console, you can export the report into the following formats:</span></span>

-   <span data-ttu-id="425a9-115">Adobe Acrobat （PDF）</span><span class="sxs-lookup"><span data-stu-id="425a9-115">Adobe Acrobat (PDF)</span></span>

-   <span data-ttu-id="425a9-116">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="425a9-116">Microsoft Office Excel</span></span>

<span data-ttu-id="425a9-117">**記事** 用戶端所報告的 app-v 伺服器名稱必須是預設伺服器群組的一部分，才能讓系統利用率報告顯示資料。</span><span class="sxs-lookup"><span data-stu-id="425a9-117">**Note** The App-V server name reported from the clients must be part of the Default Server Group in order for the System Utilization report to show data.</span></span> <span data-ttu-id="425a9-118">例如，如果您將多個伺服器與網路負載平衡器（NLB）結合使用，您必須將 NLB 群集名稱新增到預設的伺服器群組中。</span><span class="sxs-lookup"><span data-stu-id="425a9-118">For example, if you are using multiple servers with a Network Load Balancer (NLB), you must add the NLB cluster name to the Default Server Group.</span></span>

 

## <span data-ttu-id="425a9-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="425a9-119">Related topics</span></span>


[<span data-ttu-id="425a9-120">如何建立報告</span><span class="sxs-lookup"><span data-stu-id="425a9-120">How to Create a Report</span></span>](how-to-create-a-reportserver.md)

[<span data-ttu-id="425a9-121">如何刪除報告</span><span class="sxs-lookup"><span data-stu-id="425a9-121">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)

[<span data-ttu-id="425a9-122">如何匯出報告</span><span class="sxs-lookup"><span data-stu-id="425a9-122">How to Export a Report</span></span>](how-to-export-a-reportserver.md)

[<span data-ttu-id="425a9-123">如何列印報告</span><span class="sxs-lookup"><span data-stu-id="425a9-123">How to Print a Report</span></span>](how-to-print-a-reportserver.md)

[<span data-ttu-id="425a9-124">如何執行報告</span><span class="sxs-lookup"><span data-stu-id="425a9-124">How to Run a Report</span></span>](how-to-run-a-reportserver.md)

 

 





