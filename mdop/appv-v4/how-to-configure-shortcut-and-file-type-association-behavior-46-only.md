---
title: 如何設定捷徑和檔案類型關聯行為
description: 如何設定捷徑和檔案類型關聯行為
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801606"
---
# <span data-ttu-id="7f4db-103">如何設定捷徑和檔案類型關聯行為</span><span class="sxs-lookup"><span data-stu-id="7f4db-103">How to Configure Shortcut and File Type Association Behavior</span></span>


<span data-ttu-id="7f4db-104">快捷方式和檔案類型關聯（FTA）發佈原則是由發佈 XML 檔案定義並加以控制，在發佈重新整理作業期間，由發佈伺服器傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="7f4db-104">Shortcut and File Type Association (FTA) publishing policy is defined and controlled by the publishing XML file, which is sent to clients by a publishing server during a publishing refresh operation.</span></span> <span data-ttu-id="7f4db-105">當用戶端收到此資訊時，會新增有關應用程式（例如圖示與 FTAs）的任何新近發佈資料。</span><span class="sxs-lookup"><span data-stu-id="7f4db-105">When the client receives this information, it adds any newly published data about applications such as the icons and FTAs.</span></span> <span data-ttu-id="7f4db-106">接著，它會移除任何過時的發佈資料。</span><span class="sxs-lookup"><span data-stu-id="7f4db-106">Then, it removes any outdated publishing data.</span></span>

<span data-ttu-id="7f4db-107">在 App-V 版本4.6 中，已定義兩個登錄機碼值，讓系統管理員可以控制此行為。</span><span class="sxs-lookup"><span data-stu-id="7f4db-107">In App-V version 4.6, two registry key values have been defined to enable administrators to control this behavior.</span></span> <span data-ttu-id="7f4db-108">根據預設，使用用戶端主控台在本機建立的快速鍵現在會保留下來。</span><span class="sxs-lookup"><span data-stu-id="7f4db-108">By default, shortcuts that are created locally by using the client console are now retained.</span></span>

## <span data-ttu-id="7f4db-109">如何變更快速鍵與 FTA 行為</span><span class="sxs-lookup"><span data-stu-id="7f4db-109">How to Change Shortcut and FTA Behavior</span></span>


<span data-ttu-id="7f4db-110">已針對用戶端配置登錄機碼（"FileTypePolicy" 和 "ShortcutPolicy"）定義兩個新的 DWORD 值登錄值。</span><span class="sxs-lookup"><span data-stu-id="7f4db-110">Two new DWORD registry values have been defined for the client Configuration registry key, “FileTypePolicy” and “ShortcutPolicy”.</span></span> <span data-ttu-id="7f4db-111">預設不會顯示這些 DWORD 登錄值，但可以手動新增它們。</span><span class="sxs-lookup"><span data-stu-id="7f4db-111">These DWORD registry values are not present by default, but they can be added manually.</span></span> <span data-ttu-id="7f4db-112">配置登錄機碼位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\Configuration。</span><span class="sxs-lookup"><span data-stu-id="7f4db-112">The Configuration registry key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\Configuration.</span></span>

<span data-ttu-id="7f4db-113">下表中定義了四個原則值，它們都適用于兩個登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="7f4db-113">There are four policy values defined in the following table and these apply to both registry key values.</span></span> <span data-ttu-id="7f4db-114">下列清單顯示註冊表設定的數值，以及在發佈重新整理作業上套用至檔案類型或快速鍵的行為。</span><span class="sxs-lookup"><span data-stu-id="7f4db-114">The following list shows the numeric values for the registry settings, and the behavior applied to file types or shortcuts on a publishing refresh operation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f4db-115">名稱</span><span class="sxs-lookup"><span data-stu-id="7f4db-115">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-116">類型</span><span class="sxs-lookup"><span data-stu-id="7f4db-116">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-117">資料（範例）</span><span class="sxs-lookup"><span data-stu-id="7f4db-117">Data (Examples)</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-118">描述</span><span class="sxs-lookup"><span data-stu-id="7f4db-118">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7f4db-119">FileTypePolicy</span><span class="sxs-lookup"><span data-stu-id="7f4db-119">FileTypePolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-120">DWORD</span><span class="sxs-lookup"><span data-stu-id="7f4db-120">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-121">預設值 = 0x2 （App-v 4.6）</span><span class="sxs-lookup"><span data-stu-id="7f4db-121">Default=0x2 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-122">（0x0）-"ClientOnly"-從相同的發佈資訊來源移除任何現有的專案，並只保留在本機新增的專案</span><span class="sxs-lookup"><span data-stu-id="7f4db-122">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items that are added locally</span></span></p>
<p><span data-ttu-id="7f4db-123">（0x1）-"ServerOnly"-從相同的發佈資訊來源以及任何在本機加入的專案，移除任何過期的專案，並新增專案</span><span class="sxs-lookup"><span data-stu-id="7f4db-123">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items that are added locally, and add the new items</span></span></p>
<p><span data-ttu-id="7f4db-124">（0x2）-"ClientAndServer"-從相同的發佈資訊來源中移除任何過時的專案、將專案新增到本機，以及新增專案（如果 App-v 4.6 不存在，則為預設值）</span><span class="sxs-lookup"><span data-stu-id="7f4db-124">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present for App-V 4.6)</span></span></p>
<p><span data-ttu-id="7f4db-125">（0x3）– "NoChange"-不對檔案類型或快速鍵進行任何變更</span><span class="sxs-lookup"><span data-stu-id="7f4db-125">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f4db-126">ShortcutPolicy</span><span class="sxs-lookup"><span data-stu-id="7f4db-126">ShortcutPolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-127">DWORD</span><span class="sxs-lookup"><span data-stu-id="7f4db-127">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-128">預設 = 0x2</span><span class="sxs-lookup"><span data-stu-id="7f4db-128">Default=0x2</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f4db-129">（0x0）-"ClientOnly"-從相同的發佈資訊來源移除任何現有的專案，並只保留在本機新增的專案</span><span class="sxs-lookup"><span data-stu-id="7f4db-129">(0x0) – “ClientOnly”- remove any existing items from the same publishing information source, and keep only items added locally</span></span></p>
<p><span data-ttu-id="7f4db-130">（0x1）-"ServerOnly"-從相同的發佈資訊來源以及任何在本機加入的專案，移除任何過期的專案，並新增專案</span><span class="sxs-lookup"><span data-stu-id="7f4db-130">(0x1) – “ServerOnly” - remove any outdated items from the same publishing information source and any items added locally, and add the new items</span></span></p>
<p><span data-ttu-id="7f4db-131">（0x2）-"ClientAndServer"-從相同的發佈資訊來源中移除任何過時的專案，將專案保留在本機，並新增專案（如果沒有的話則為預設值）</span><span class="sxs-lookup"><span data-stu-id="7f4db-131">(0x2) – “ClientAndServer”- remove any outdated items from the same publishing information source, keep items added locally, and add the new items (default if not present)</span></span></p>
<p><span data-ttu-id="7f4db-132">（0x3）– "NoChange"-不對檔案類型或快速鍵進行任何變更</span><span class="sxs-lookup"><span data-stu-id="7f4db-132">(0x3) – “NoChange” - make no changes to file types or shortcuts</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7f4db-133">**記事** 文字值會參照發佈 XML 檔案中 XML 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="7f4db-133">**Note** The text values refer to the values for the XML attributes in the publishing XML file.</span></span><span data-ttu-id="7f4db-134">如果您已執行自訂 HTTP 發佈解決方案，您可以手動設定這些值。</span><span class="sxs-lookup"><span data-stu-id="7f4db-134"> You can set these values manually if you have implemented a custom HTTP publishing solution.</span></span>

 

 

 





