---
title: 應用程式虛擬化屬性 [一般] 索引標籤
description: 應用程式虛擬化屬性 [一般] 索引標籤
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802317"
---
# <span data-ttu-id="85477-103">Application Virtualization 內容：一般索引標籤</span><span class="sxs-lookup"><span data-stu-id="85477-103">Application Virtualization Properties: General Tab</span></span>


<span data-ttu-id="85477-104">使用 [**應用程式虛擬化屬性**] 對話方塊的 **[一般**] 索引標籤來修改記錄設定和資料位置。</span><span class="sxs-lookup"><span data-stu-id="85477-104">Use the **General** tab of the **Application Virtualization Properties** dialog box to modify log settings and data locations.</span></span>

<span data-ttu-id="85477-105">此索引標籤包含下列元素。</span><span class="sxs-lookup"><span data-stu-id="85477-105">This tab contains the following elements.</span></span>

<a href="" id="log-level"></a>**<span data-ttu-id="85477-106">記錄層級</span><span class="sxs-lookup"><span data-stu-id="85477-106">Log Level</span></span>**  
<span data-ttu-id="85477-107">從下拉式清單中選取等級。</span><span class="sxs-lookup"><span data-stu-id="85477-107">Select the level from the drop-down list.</span></span> <span data-ttu-id="85477-108">預設等級為 [**資訊**]。</span><span class="sxs-lookup"><span data-stu-id="85477-108">The default level is **Information**.</span></span>

<a href="" id="reset-log"></a>**<span data-ttu-id="85477-109">重設記錄</span><span class="sxs-lookup"><span data-stu-id="85477-109">Reset Log</span></span>**  
<span data-ttu-id="85477-110">按一下此按鈕以備份目前的記錄檔，並立即開始新的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="85477-110">Click this button to back up the current log file and immediately start a new log file.</span></span>

<a href="" id="location"></a>**<span data-ttu-id="85477-111">位置</span><span class="sxs-lookup"><span data-stu-id="85477-111">Location</span></span>**  
<span data-ttu-id="85477-112">輸入或流覽至您要儲存記錄檔 sftlog.txt 的位置。</span><span class="sxs-lookup"><span data-stu-id="85477-112">Enter or browse to the location where you want to save the log file sftlog.txt.</span></span> <span data-ttu-id="85477-113">預設位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="85477-113">The default locations are as follows:</span></span>

-   <span data-ttu-id="85477-114">針對 WindowsXP、Windows Server2003-*C:\\Documents 與 Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization 用戶端*</span><span class="sxs-lookup"><span data-stu-id="85477-114">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="85477-115">Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application Virtualization 用戶端*</span><span class="sxs-lookup"><span data-stu-id="85477-115">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="system-log-level"></a>**<span data-ttu-id="85477-116">系統記錄層級</span><span class="sxs-lookup"><span data-stu-id="85477-116">System Log Level</span></span>**  
<span data-ttu-id="85477-117">從下拉式清單中選取等級。</span><span class="sxs-lookup"><span data-stu-id="85477-117">Select the level from the drop-down list.</span></span> <span data-ttu-id="85477-118">預設的層級為 [**警告**]。</span><span class="sxs-lookup"><span data-stu-id="85477-118">The default level is **Warning**.</span></span>

<span data-ttu-id="85477-119">**記事** **系統記錄層級**設定控制傳送至系統事件記錄條的訊息層級。</span><span class="sxs-lookup"><span data-stu-id="85477-119">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="85477-120">記錄的訊息與記錄在用戶端事件日誌中的訊息相同，但它們儲存在不同的位置，而不具備用戶端事件記錄的空間限制。</span><span class="sxs-lookup"><span data-stu-id="85477-120">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location that does not have the space limitations of the client event log.</span></span> <span data-ttu-id="85477-121">因為系統事件記錄檔沒有空間限制，所以特別適合在需要詳細記錄的情況下。</span><span class="sxs-lookup"><span data-stu-id="85477-121">Because the system event log does not have space limitations, it is ideally suited for situations where verbose logging is necessary.</span></span>

 

<a href="" id="global-data-directory"></a>**<span data-ttu-id="85477-122">全域資料目錄</span><span class="sxs-lookup"><span data-stu-id="85477-122">Global Data Directory</span></span>**  
<span data-ttu-id="85477-123">輸入或流覽至記錄檔目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="85477-123">Enter or browse to the location of the directory of the log file.</span></span> <span data-ttu-id="85477-124">預設位置如下所示：</span><span class="sxs-lookup"><span data-stu-id="85477-124">The default locations are as follows:</span></span>

-   <span data-ttu-id="85477-125">針對 WindowsXP、Windows Server2003-*C:\\Documents 與 Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization 用戶端*</span><span class="sxs-lookup"><span data-stu-id="85477-125">For WindowsXP, Windows Server2003—*C:\\Documents and Settings\\All Users\\Application Data\\Microsoft\\Application Virtualization Client*</span></span>

-   <span data-ttu-id="85477-126">Windows Vista、Windows 7、Windows Server2008-*C:\\ProgramData\\Microsoft\\Application Virtualization 用戶端*</span><span class="sxs-lookup"><span data-stu-id="85477-126">For Windows Vista, Windows 7, Windows Server2008—*C:\\ProgramData\\Microsoft\\Application Virtualization Client*</span></span>

<a href="" id="user-data-directory"></a>**<span data-ttu-id="85477-127">使用者資料目錄</span><span class="sxs-lookup"><span data-stu-id="85477-127">User Data Directory</span></span>**  
<span data-ttu-id="85477-128">輸入或流覽至儲存使用者特定資料之目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="85477-128">Enter or browse to the location of the directory where user-specific data is stored.</span></span> <span data-ttu-id="85477-129">預設值為% APPDATA%。</span><span class="sxs-lookup"><span data-stu-id="85477-129">The default is %APPDATA%.</span></span> <span data-ttu-id="85477-130">此路徑必須是用戶端電腦上的有效環境變數。</span><span class="sxs-lookup"><span data-stu-id="85477-130">This path must be a valid environment variable on the client computer.</span></span>

## <span data-ttu-id="85477-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="85477-131">Related topics</span></span>


[<span data-ttu-id="85477-132">用戶端管理主控台：Application Virtualization 內容</span><span class="sxs-lookup"><span data-stu-id="85477-132">Client Management Console: Application Virtualization Properties</span></span>](client-management-console-application-virtualization-properties.md)

 

 





