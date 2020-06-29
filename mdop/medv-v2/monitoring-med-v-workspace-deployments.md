---
title: 監控 MED-V 工作區部署
description: 監控 MED-V 工作區部署
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812219"
---
# <span data-ttu-id="100ca-103">監控 MED-V 工作區部署</span><span class="sxs-lookup"><span data-stu-id="100ca-103">Monitoring MED-V Workspace Deployments</span></span>


<span data-ttu-id="100ca-104">Microsoft 企業桌面虛擬化（MED-V）2.0 中的 [監視] 功能可讓您在個別的 MED-V 工作區上執行查詢，以判斷在部署 MED-V 工作區之後，是否要讓整個企業中的第一次都成功完成設定。</span><span class="sxs-lookup"><span data-stu-id="100ca-104">The monitoring feature in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 lets you run queries on individual MED-V workspaces to determine whether first time setup succeeded throughout your enterprise after the MED-V workspaces are deployed.</span></span> <span data-ttu-id="100ca-105">監控第一次設定的成功與否，是因為 MED-V 在第一次成功完成之前並不是使用中的狀態。</span><span class="sxs-lookup"><span data-stu-id="100ca-105">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has been completed successfully.</span></span>

<span data-ttu-id="100ca-106">本節提供資訊與指示，協助您監控第一次設定的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="100ca-106">This section provides information and instruction to assist you in monitoring the success or failure of first time setup.</span></span>

## <span data-ttu-id="100ca-107">監視 MED-V 工作區部署</span><span class="sxs-lookup"><span data-stu-id="100ca-107">To monitor MED-V workspace deployments</span></span>


<span data-ttu-id="100ca-108">[監視] 功能是由結合的進程內 Windows 管理規範（WMI）提供者所組成，您可以使用 WMI 查詢語言來查詢，以探索 MED-V 工作區中所有最終使用者的第一次設定狀態。</span><span class="sxs-lookup"><span data-stu-id="100ca-108">The monitoring feature consists of a coupled in-process Windows Management Instrumentation (WMI) provider that you can query using WMI Query Language to discover the status of first time setup for all end users on a MED-V workspace.</span></span>

<span data-ttu-id="100ca-109">WMI 提供者是使用來自 Microsoft .Net Framework 3.5 的 WMI 提供程式擴充架構來實現。</span><span class="sxs-lookup"><span data-stu-id="100ca-109">The WMI provider is implemented by using the WMI Provider Extension framework from the Microsoft .Net Framework 3.5.</span></span> <span data-ttu-id="100ca-110">WMI 提供者會在 LocalService 的內容中執行，並在 \\ProgramData. 下安全地儲存第一次設定狀態。</span><span class="sxs-lookup"><span data-stu-id="100ca-110">The WMI provider executes in the context of LocalService and stores the first time setup state securely under \\ProgramData.</span></span>

<span data-ttu-id="100ca-111">WMI 提供者是在**root\\microsoft\\medv**命名空間中實現，並實現 class **FTS \ _Status**，這會公開方法**SetFtsState**。</span><span class="sxs-lookup"><span data-stu-id="100ca-111">The WMI provider is implemented in the **root\\microsoft\\medv** namespace and implements the class **FTS\_Status**, which exposes the method **SetFtsState**.</span></span> <span data-ttu-id="100ca-112">MED-V 會使用**SetFtsState**來設定第一次設定狀態。</span><span class="sxs-lookup"><span data-stu-id="100ca-112">MED-V uses **SetFtsState** to set the first time setup state.</span></span>

<span data-ttu-id="100ca-113">此類別包含下列屬性。</span><span class="sxs-lookup"><span data-stu-id="100ca-113">The class contains the following properties.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="100ca-114">屬性</span><span class="sxs-lookup"><span data-stu-id="100ca-114">Property</span></span></th>
<th align="left"><span data-ttu-id="100ca-115">描述</span><span class="sxs-lookup"><span data-stu-id="100ca-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="100ca-116">電腦</span><span class="sxs-lookup"><span data-stu-id="100ca-116">Machine</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="100ca-117">[唯讀] </strong> 屬性，包含由第一次設定所配的來賓虛擬機器名稱。</span><span class="sxs-lookup"><span data-stu-id="100ca-117">Read Only</strong> property that contains the name of the guest virtual machine provisioned by first time setup.</span></span> <span data-ttu-id="100ca-118">此金鑰包含來賓在第一次設定失敗時所擁有的名稱。</span><span class="sxs-lookup"><span data-stu-id="100ca-118">This key contains the name that the guest would have had on first time setup failure.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="100ca-119">StatusCode</span><span class="sxs-lookup"><span data-stu-id="100ca-119">StatusCode</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="100ca-120"></strong>第一次設定成功時，包含零的唯讀屬性。</span><span class="sxs-lookup"><span data-stu-id="100ca-120">Read Only</strong> property that contains zero if first time setup succeeded.</span></span> <span data-ttu-id="100ca-121">傳回的任何其他值都等於記錄之錯誤的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="100ca-121">Any other value returned equals the event ID for the error that is logged.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="100ca-122">時間</span><span class="sxs-lookup"><span data-stu-id="100ca-122">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="100ca-123">第一次設定完成時的 UTC 時間。</span><span class="sxs-lookup"><span data-stu-id="100ca-123">The UTC time that first time setup completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="100ca-124">使用者</span><span class="sxs-lookup"><span data-stu-id="100ca-124">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="100ca-125">第一次執行設定的使用者。</span><span class="sxs-lookup"><span data-stu-id="100ca-125">The user for which first time setup was run.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="100ca-126">下列程式碼會顯示定義**FTS \ _Status**類別的 Managed 物件格式（MOF）檔案。</span><span class="sxs-lookup"><span data-stu-id="100ca-126">The following code shows the Managed Object Format (MOF) file that defines the **FTS\_Status** class.</span></span>

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

<span data-ttu-id="100ca-127">因為您主要關心的是那些第一次未成功完成設定的 MED-V 工作區，所以您可以撰寫您的查詢，只返回那些第一次設定失敗的專案，例如：</span><span class="sxs-lookup"><span data-stu-id="100ca-127">Because your main concern is most likely those MED-V workspaces for which first time setup was not completed successfully, you can write your query to only return those that failed first time setup, for example:</span></span>

``` syntax
Select * from FTS_Status where StatusCode != 0
```

<span data-ttu-id="100ca-128">在這種情況下，[監視] 功能會傳回那些第一次設定失敗的那些 MED-V 工作區清單，您可以用來採取適當的動作來解決失敗。</span><span class="sxs-lookup"><span data-stu-id="100ca-128">In this case, the monitoring feature returns a list of those MED-V workspaces that failed first time setup, which you can use to take the appropriate actions to resolve the failure.</span></span>

## <span data-ttu-id="100ca-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="100ca-129">Related topics</span></span>


[<span data-ttu-id="100ca-130">監控 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="100ca-130">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="100ca-131">如何驗證第一次安裝設定</span><span class="sxs-lookup"><span data-stu-id="100ca-131">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

 

 





