---
title: Application Virtualization Client 中的使用者存取權限
description: Application Virtualization Client 中的使用者存取權限
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800755"
---
# <span data-ttu-id="18c84-103">Application Virtualization Client 中的使用者存取權限</span><span class="sxs-lookup"><span data-stu-id="18c84-103">User Access Permissions in Application Virtualization Client</span></span>


<span data-ttu-id="18c84-104">在 [**屬性**] 對話方塊的 [**許可權**] 索引標籤上，以滑鼠右鍵按一下應用程式虛擬化用戶端管理主控台中的 [**應用程式虛擬化**] 節點，管理員可以授與使用者使用各種用戶端函數的許可權。</span><span class="sxs-lookup"><span data-stu-id="18c84-104">On the **Permissions** tab on the **Properties** dialog box, accessible by right-clicking the **Application Virtualization** node in the Application Virtualization Client Management Console, administrators can grant users permissions to use the various client functions.</span></span>

<span data-ttu-id="18c84-105">**記事** 在變更使用者許可權前，請確定任何許可權變更與組織提供使用者許可權的指導方針一致。</span><span class="sxs-lookup"><span data-stu-id="18c84-105">**Note** Before changing users permissions, ensure that any permissions changes are consistent with the organization's guidelines for granting user permissions.</span></span>

 

<span data-ttu-id="18c84-106">下表列出並說明可授與使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="18c84-106">The following table lists and describes the permissions that can be granted to users.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="18c84-107">許可權名稱</span><span class="sxs-lookup"><span data-stu-id="18c84-107">Permission Name</span></span></th>
<th align="left"><span data-ttu-id="18c84-108">描述</span><span class="sxs-lookup"><span data-stu-id="18c84-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-109">新增應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-109">Add applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-110">使用 sfttray.exe、sftmime.exe 或 MMC，將新的應用程式傳到用戶端。</span><span class="sxs-lookup"><span data-stu-id="18c84-110">Register new applications by passing a new OSD file to the client by using sfttray.exe, sftmime.exe or the MMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-111">變更檔案系統快取大小</span><span class="sxs-lookup"><span data-stu-id="18c84-111">Change file system cache size</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-112">增加檔案系統快取的大小。</span><span class="sxs-lookup"><span data-stu-id="18c84-112">Increase the size of the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-113">變更檔系統磁碟機</span><span class="sxs-lookup"><span data-stu-id="18c84-113">Change file system drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-114">針對檔案系統選取不同的喜好磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="18c84-114">Select a different preferred drive letter for the file system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-115">變更記錄設定</span><span class="sxs-lookup"><span data-stu-id="18c84-115">Change log settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-116">變更用戶端記錄檔的記錄層級或記錄路徑。</span><span class="sxs-lookup"><span data-stu-id="18c84-116">Change the log level or the log path for the client log file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-117">變更 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="18c84-117">Change OSD files</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-118">修改已註冊之應用程式的 OSD 檔案，並將它們傳到用戶端。</span><span class="sxs-lookup"><span data-stu-id="18c84-118">Modify OSD files for registered applications and pass them into the client.</span></span> <span data-ttu-id="18c84-119">這不會影響發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="18c84-119">This does not affect publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-120">清除應用程式設定</span><span class="sxs-lookup"><span data-stu-id="18c84-120">Clear application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-121">刪除目前使用者的檔案類型、快速鍵及任何設定。</span><span class="sxs-lookup"><span data-stu-id="18c84-121">Delete file types, shortcuts and any configurations for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-122">刪除應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-122">Delete applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-123">針對電腦上的所有使用者，從 [檔案系統] 和 [OSD 快取] 移除應用程式的所有參照。</span><span class="sxs-lookup"><span data-stu-id="18c84-123">Remove all references to an application from the file system and OSD cache for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-124">將應用程式匯入快取</span><span class="sxs-lookup"><span data-stu-id="18c84-124">Import applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-125">將應用程式資料直接從指定的 SFT 檔案載入至檔案系統快取。</span><span class="sxs-lookup"><span data-stu-id="18c84-125">Load application data directly from a specified SFT file into the file system cache.</span></span> <span data-ttu-id="18c84-126">這會影響所有使用者。</span><span class="sxs-lookup"><span data-stu-id="18c84-126">This affects all users.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-127">將應用程式載入到快取</span><span class="sxs-lookup"><span data-stu-id="18c84-127">Load applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-128">從已設定的來源開始為應用程式載入 SFT 檔案，例如 App-v 串流伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c84-128">Start a load of the SFT file for an application from the configured source, such as an App-V Streaming Server.</span></span> <span data-ttu-id="18c84-129">這會針對電腦上的所有使用者載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="18c84-129">This loads the application for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-130">在快取中鎖定和解除鎖定應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-130">Lock and unlock applications in the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-131">防止或允許從檔案系統快取中卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="18c84-131">Prevent or allow applications from being unloaded from the file system cache.</span></span> <span data-ttu-id="18c84-132">這會影響電腦上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="18c84-132">This affects all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-133">管理檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="18c84-133">Manage file type associations</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-134">新增、修改或刪除目前使用者的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="18c84-134">Add, modify, or delete file type associations for the current user only.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-135">管理發佈更新設定</span><span class="sxs-lookup"><span data-stu-id="18c84-135">Manage publishing refresh settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-136">變更設定，以控制電腦上所有使用者的發佈更新時間。</span><span class="sxs-lookup"><span data-stu-id="18c84-136">Change settings that control the timing of publishing refreshes for all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-137">管理發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="18c84-137">Manage publishing servers</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-138">新增、修改或刪除電腦上所有使用者的發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="18c84-138">Add, modify, or delete publishing servers for all users on the computer.</span></span> <span data-ttu-id="18c84-139">此許可權會隱式包含管理發佈更新設定的許可權。</span><span class="sxs-lookup"><span data-stu-id="18c84-139">This permission implicitly includes permission to manage publishing refresh settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-140">發佈快速鍵</span><span class="sxs-lookup"><span data-stu-id="18c84-140">Publish shortcuts</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-141">建立已註冊應用程式的新快速鍵。</span><span class="sxs-lookup"><span data-stu-id="18c84-141">Create new shortcuts to registered applications.</span></span> <span data-ttu-id="18c84-142">使用者也必須具有在本機檔案系統中建立檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="18c84-142">The user must also have permission to create files in the local file system.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-143">修復應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-143">Repair applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-144">移除目前使用者的應用程式特定設定，但不移除快速鍵或檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="18c84-144">Remove application specific configurations for the current user without removing shortcuts or file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-145">啟動發佈更新</span><span class="sxs-lookup"><span data-stu-id="18c84-145">Start a publishing refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-146">針對目前的使用者，啟動未排程的發佈更新。</span><span class="sxs-lookup"><span data-stu-id="18c84-146">Start an unscheduled publishing refresh for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-147">切換離線模式</span><span class="sxs-lookup"><span data-stu-id="18c84-147">Toggle offline mode</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-148">針對所有使用者將整個用戶端從線上改為離線模式。</span><span class="sxs-lookup"><span data-stu-id="18c84-148">Change the entire client from online to offline mode for all users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18c84-149">從快取中卸載應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-149">Unload applications from the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-150">清除檔案系統快取中所有使用者的應用程式資料，而不需移除使用者專用的設定、快速鍵或檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="18c84-150">Clear application data from the file system cache for all users without removing user-specific settings, shortcuts, or file type associations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18c84-151">查看所有應用程式</span><span class="sxs-lookup"><span data-stu-id="18c84-151">View all applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="18c84-152">允許使用者查看在電腦上註冊之所有使用者的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="18c84-152">Allow the user to see the virtual applications for all users registered on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="18c84-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="18c84-153">Related topics</span></span>


[<span data-ttu-id="18c84-154">如何變更使用者存取權限</span><span class="sxs-lookup"><span data-stu-id="18c84-154">How to Change User Access Permissions</span></span>](how-to-change-user-access-permissions.md)

 

 





