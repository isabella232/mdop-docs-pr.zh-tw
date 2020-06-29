---
title: 使用管理工具組來疑難排解 MED-V
description: 使用管理工具組來疑難排解 MED-V
author: dansimp
ms.assetid: 6c096a1c-b9ce-4ec7-8dfd-5286e3b9a617
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1eaa493e5603e8a1275a6ff5f189739b168f319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811115"
---
# <span data-ttu-id="9a8b1-103">使用管理工具組來疑難排解 MED-V</span><span class="sxs-lookup"><span data-stu-id="9a8b1-103">Troubleshooting MED-V by Using the Administration Toolkit</span></span>


<span data-ttu-id="9a8b1-104">使用 MED-V 管理工具組來針對 MED-V 工作區中的特定問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-104">Use the MED-V Administration Toolkit to troubleshoot certain problems in a MED-V workspace.</span></span> <span data-ttu-id="9a8b1-105">MED-V 管理工具組可讓您存取及設定事件記錄、重新開機或重設 MED-V 工作區，以及在 MED-V 工作區中查看已發佈的應用程式和重定向的網址。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-105">The MED-V Administration Toolkit lets you access and configure event logs, restart or reset the MED-V workspace, and view the published applications and redirected web addresses in the MED-V workspace.</span></span> <span data-ttu-id="9a8b1-106">您也可以使用 MED-V 管理工具組，以全螢幕模式開啟 MED-V 工作區虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-106">You can also use the MED-V Administration Toolkit to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="9a8b1-107">若要開啟 MED-V 管理工具組</span><span class="sxs-lookup"><span data-stu-id="9a8b1-107">To Open the MED-V Administration Toolkit</span></span>


<span data-ttu-id="9a8b1-108">請執行下列步驟以開啟 MED-V 管理工具組：</span><span class="sxs-lookup"><span data-stu-id="9a8b1-108">Perform the following steps to open the MED-V Administration Toolkit:</span></span>

1.  <span data-ttu-id="9a8b1-109">在包含您要疑難排解之 MED-V 工作區的主機電腦上，開啟 [命令提示字元] 視窗。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-109">On the host computer that contains the MED-V workspace you are troubleshooting, open a Command Prompt window.</span></span>

2.  <span data-ttu-id="9a8b1-110">流覽至%systemdrive%\\Program Files\\Microsoft 企業版桌面虛擬化。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-110">Browse to %systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization.</span></span>

3.  <span data-ttu-id="9a8b1-111">在命令提示字元中，輸入**MedvHost/toolkit**。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-111">At the command prompt, type **MedvHost /toolkit**.</span></span>

<span data-ttu-id="9a8b1-112">在 MED-V 管理工具組開啟之後，您可以使用該工具來協助解決在疑難排解期間的 MED-V 工作區中的問題。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-112">After the MED-V Administration Toolkit opens, you can use the toolkit to help resolve issues in the MED-V workspace found during troubleshooting.</span></span>

## <span data-ttu-id="9a8b1-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="9a8b1-113">In this Section</span></span>


<a href="" id="viewing-and-configuring-med-v-logs"></a>[<span data-ttu-id="9a8b1-114">檢視及設定 MED-V 記錄</span><span class="sxs-lookup"><span data-stu-id="9a8b1-114">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)  
<span data-ttu-id="9a8b1-115">說明如何使用 MED-V 管理工具組，在主機電腦和來賓虛擬機器中收集及管理 MED-V 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-115">Describes how to use the MED-V Administration Toolkit to collect and manage MED-V event logs in the host computer and the guest virtual machine.</span></span>

<a href="" id="restarting-and-resetting-a-med-v-workspace"></a>[<span data-ttu-id="9a8b1-116">重新啟動和重設 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="9a8b1-116">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)  
<span data-ttu-id="9a8b1-117">說明如何使用 MED-V 管理工具組重新開機及重設 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-117">Describes how to restart and reset MED-V workspaces by using the MED-V Administration Toolkit.</span></span>

<a href="" id="viewing-med-v-workspace-configurations"></a>[<span data-ttu-id="9a8b1-118">檢視 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="9a8b1-118">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)  
<span data-ttu-id="9a8b1-119">說明如何使用 MED-V 管理工具組，在 MED-V 工作區中查看已發佈的應用程式和重新導向的網址，以及如何在全螢幕模式中開啟 MED-V 工作區虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="9a8b1-119">Describes how to use the MED-V Administration Toolkit to view the published applications and redirected web addresses in a MED-V workspace and how to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="9a8b1-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="9a8b1-120">Related topics</span></span>


[<span data-ttu-id="9a8b1-121">MED-V 事件記錄檔訊息</span><span class="sxs-lookup"><span data-stu-id="9a8b1-121">MED-V Event Log Messages</span></span>](med-v-event-log-messages.md)

[<span data-ttu-id="9a8b1-122">疑難排解 MED-V</span><span class="sxs-lookup"><span data-stu-id="9a8b1-122">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





