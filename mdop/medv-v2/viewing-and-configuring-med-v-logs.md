---
title: 檢視及設定 MED-V 記錄
description: 檢視及設定 MED-V 記錄
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810130"
---
# <span data-ttu-id="34163-103">檢視及設定 MED-V 記錄</span><span class="sxs-lookup"><span data-stu-id="34163-103">Viewing and Configuring MED-V Logs</span></span>


<span data-ttu-id="34163-104">當您排查 MED-V 問題和問題時，您可能會發現存取 MED-V 事件記錄很有説明。</span><span class="sxs-lookup"><span data-stu-id="34163-104">When you are troubleshooting MED-V issues and problems, you may find it helpful or necessary to access the MED-V event logs.</span></span> <span data-ttu-id="34163-105">您可以使用 MED-V 管理工具組開啟主機電腦和來賓虛擬機器的事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="34163-105">You can open Event Viewer for the host computer and the guest virtual machine by using the MED-V Administration Toolkit.</span></span> <span data-ttu-id="34163-106">您也可以使用 MED-V 管理工具組來設定 MED-V 事件記錄的記錄層級（MED-V 事件）。</span><span class="sxs-lookup"><span data-stu-id="34163-106">You can also use the MED-V Administration Toolkit to set the logging level at which the MED-V event logs report MED-V events.</span></span>

<span data-ttu-id="34163-107">如需如何開啟 MED-V 管理工具組的相關資訊，請參閱[使用管理工具組在 med-v 中進行疑難排解](troubleshooting-med-v-by-using-the-administration-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="34163-107">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

## <span data-ttu-id="34163-108">查看 MED-V 事件記錄</span><span class="sxs-lookup"><span data-stu-id="34163-108">Viewing MED-V Event Logs</span></span>


<span data-ttu-id="34163-109">在 [ **Med-v 管理工具**組] 視窗中，按一下 [**主機事件**] 來開啟主機電腦的事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="34163-109">On the **MED-V Administration Toolkit** window, click **Host Events** to open the event viewer for the host computer.</span></span> <span data-ttu-id="34163-110">或者，按一下 [**來賓事件**] 來開啟來賓虛擬機器的事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="34163-110">Or, click **Guest Events** to open Event Viewer for the guest virtual machine.</span></span>

<span data-ttu-id="34163-111">[事件檢視器] 會開啟並顯示對應的事件記錄，您可以用來針對您在部署或管理 MED-V 時可能遇到的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="34163-111">Event Viewer opens and displays the corresponding event logs that you can use to troubleshoot the issues that you might encounter when you deploy or manage MED-V.</span></span> <span data-ttu-id="34163-112">根據預設，只會顯示錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="34163-112">By default, only errors and warnings are displayed.</span></span> <span data-ttu-id="34163-113">如需特定事件識別碼和訊息的詳細資訊，請參閱[Med-v 事件記錄訊息](med-v-event-log-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="34163-113">For more information about specific event IDs and messages, see [MED-V Event Log Messages](med-v-event-log-messages.md).</span></span>

<span data-ttu-id="34163-114">**記事** 如果使用者擁有系統管理許可權，就只能將事件記錄檔儲存在來賓中。</span><span class="sxs-lookup"><span data-stu-id="34163-114">**Note** End users can only save event log files in the guest if they have administrative permissions.</span></span>

 

### <span data-ttu-id="34163-115">手動開啟主機電腦中的 [事件檢視器]</span><span class="sxs-lookup"><span data-stu-id="34163-115">To manually open the Event Viewer in the host computer</span></span>

1.  <span data-ttu-id="34163-116">按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**管理工具**]。</span><span class="sxs-lookup"><span data-stu-id="34163-116">Click **Start**, click **Control Panel**, and then click **Administrative Tools**.</span></span>

2.  <span data-ttu-id="34163-117">按兩下 [**事件檢視器**]，然後按一下 [**應用程式和服務記錄**]。</span><span class="sxs-lookup"><span data-stu-id="34163-117">Double-click **Event Viewer**, and then click **Applications and Services Logs**.</span></span>

3.  <span data-ttu-id="34163-118">按兩下 [ **MEDV**]。</span><span class="sxs-lookup"><span data-stu-id="34163-118">Double-click **MEDV**.</span></span>

## <span data-ttu-id="34163-119">設定 MED-V 事件記錄</span><span class="sxs-lookup"><span data-stu-id="34163-119">Configuring MED-V Event Logs</span></span>


<span data-ttu-id="34163-120">您可以選取 MED-V 管理工具組上的對應選項按鈕，以指定 MED-V 事件記錄層級。</span><span class="sxs-lookup"><span data-stu-id="34163-120">You can specify the MED-V event logging level by selecting the corresponding option button on the MED-V Administration Toolkit.</span></span> <span data-ttu-id="34163-121">您可以決定事件記錄是否只包含錯誤、錯誤和警告，或錯誤、警告及資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="34163-121">You can decide whether event logging includes errors only, errors and warnings, or errors, warnings and informational messages.</span></span> <span data-ttu-id="34163-122">針對主機電腦和來賓虛擬機器，會同時設定指定的事件記錄層級。</span><span class="sxs-lookup"><span data-stu-id="34163-122">The event logging level specified is set for both the host computer and the guest virtual machine.</span></span>

<span data-ttu-id="34163-123">您也可以透過編輯 EventLogLevel 註冊表值來指定事件記錄層級。</span><span class="sxs-lookup"><span data-stu-id="34163-123">You can also specify the event logging level by editing the EventLogLevel registry value.</span></span> <span data-ttu-id="34163-124">如需詳細資訊，請參閱[管理 Med-v 工作區配置設定](managing-med-v-workspace-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="34163-124">For more information, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="34163-125">**記事** 您在**Med-v 管理工具**組中指定的層級會套用至未來的 med-v 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="34163-125">**Note** The level you specify on the **MED-V Administration Toolkit** window applies to future MED-V event logging.</span></span> <span data-ttu-id="34163-126">如果您將階層設定為捕獲所有錯誤、警告及資訊性訊息，則會移除事件記錄更快速且較舊的事件。</span><span class="sxs-lookup"><span data-stu-id="34163-126">If you set the level to capture all errors, warnings, and informational messages, then the event logs fill more quickly and older events are removed.</span></span>

 

## <span data-ttu-id="34163-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="34163-127">Related topics</span></span>


[<span data-ttu-id="34163-128">重新啟動和重設 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="34163-128">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)

[<span data-ttu-id="34163-129">檢視 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="34163-129">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





