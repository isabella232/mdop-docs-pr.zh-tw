---
title: 評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單
description: 評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811768"
---
# <span data-ttu-id="3c159-103">評估適用於 UE-V 1.0 之企業營運應用程式的檢查清單</span><span class="sxs-lookup"><span data-stu-id="3c159-103">Checklist for Evaluating Line-of-Business Applications for UE-V 1.0</span></span>


<span data-ttu-id="3c159-104">若要評估您在 UE-V 部署中應包含哪一項行業應用程式，請考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="3c159-104">To evaluate which line-of-business applications should be included in your UE-V deployment, consider the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="3c159-105">描述</span><span class="sxs-lookup"><span data-stu-id="3c159-105">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-106">此應用程式是否包含使用者可自訂的設定？</span><span class="sxs-lookup"><span data-stu-id="3c159-106">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-107">這些設定漫遊的使用者是否很重要？</span><span class="sxs-lookup"><span data-stu-id="3c159-107">Is it important for the user that these settings roam?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-108">這些使用者設定已經由應用程式管理或設定原則方案所管理嗎？</span><span class="sxs-lookup"><span data-stu-id="3c159-108">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="3c159-109">UE-V 在 [登入]、[解除鎖定] 或 [遠端連線] 事件中，在應用程式啟動和 Windows 設定中套用應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="3c159-109">UE-V applies application settings at application launch and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="3c159-110">如果您將 UE-V 與其他設定原則方案搭配使用，使用者可能會遇到漫遊設定不一致的問題。</span><span class="sxs-lookup"><span data-stu-id="3c159-110">If you use UE-V with other settings policy solutions, users might experience inconsistency across roamed settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-111">電腦是否有特定的應用程式設定？</span><span class="sxs-lookup"><span data-stu-id="3c159-111">Are the application settings specific to the computer?</span></span> <span data-ttu-id="3c159-112">與硬體或特定電腦配置相關聯的應用程式喜好設定和自訂，不會在多個會話中持續漫遊，而且可能會造成應用程式不佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="3c159-112">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently roam across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-113">[應用程式檔案] 目錄或 [使用者 <strong> </strong> 名稱] \ <strong> AppData </strong>  \  <strong> LocalLow </strong> 目錄中的檔案目錄中的 [應用程式儲存] 設定</span><span class="sxs-lookup"><span data-stu-id="3c159-113">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong> \ [User name] \ <strong>AppData</strong> \ <strong>LocalLow</strong> directory?</span></span> <span data-ttu-id="3c159-114">儲存在上述任一位置的應用程式資料通常不應與使用者漫遊，因為這項資料是針對電腦所專用，或因為資料太大而無法漫遊。</span><span class="sxs-lookup"><span data-stu-id="3c159-114">Application data that is stored in either of these locations usually should not roam with the user, because this data is specific to the computer or because the data is too large to roam.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-115">應用程式會將任何設定儲存在檔案中，包含不應漫遊的其他應用程式資料？</span><span class="sxs-lookup"><span data-stu-id="3c159-115">Does the application store any settings in a file that contains other application data that should not roam?</span></span> <span data-ttu-id="3c159-116">UE-V 會將檔案同步處理為單一單元。</span><span class="sxs-lookup"><span data-stu-id="3c159-116">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="3c159-117">如果設定儲存在包括 [設定] 以外的應用程式資料的檔案中，則同步處理這項額外的資料可能會造成不佳的應用程式體驗。</span><span class="sxs-lookup"><span data-stu-id="3c159-117">If settings are stored in files that include application data other than settings, then synchronizing this additional data may cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="3c159-118">包含這些設定的檔案有多大？</span><span class="sxs-lookup"><span data-stu-id="3c159-118">How large are the files that contain the settings?</span></span> <span data-ttu-id="3c159-119">較大的檔案可能會影響設定同步處理的效能。</span><span class="sxs-lookup"><span data-stu-id="3c159-119">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="3c159-120">包括大型檔案會影響設定同步處理的效能。</span><span class="sxs-lookup"><span data-stu-id="3c159-120">Including large files can impact the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3c159-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="3c159-121">Related topics</span></span>


[<span data-ttu-id="3c159-122">為 UE-V 組態方法進行規劃</span><span class="sxs-lookup"><span data-stu-id="3c159-122">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

[<span data-ttu-id="3c159-123">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="3c159-123">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

 

 





