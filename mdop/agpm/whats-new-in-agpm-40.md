---
title: AGPM 4.0 的新功能
description: AGPM 4.0 的新功能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802482"
---
# <span data-ttu-id="6f86f-103">AGPM 4.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="6f86f-103">What's New in AGPM 4.0</span></span>


<span data-ttu-id="6f86f-104">Microsoft 高級群組原則管理（AGPM）4.0 包含新功能，可讓您搜尋群組原則物件（Gpo）、篩選所顯示的 Gpo 清單、匯出及匯入 GPO 至不同的林中，以及在執行 Windows7 和 Windows Server2008R2 的電腦上安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="6f86f-104">Microsoft Advanced Group Policy Management (AGPM)4.0 includes new features that let you search for Group Policy Objects (GPOs), filter the list of GPOs displayed, export and import a GPO to a different forest, and install AGPM on computers running Windows7 and Windows Server2008R2.</span></span>

## <span data-ttu-id="6f86f-105">搜尋和篩選 Gpo</span><span class="sxs-lookup"><span data-stu-id="6f86f-105">Search and filter GPOs</span></span>


<span data-ttu-id="6f86f-106">在 AGPM 4.0 中，您可以在 Gpo 清單中搜尋特定屬性，以篩選所顯示之 Gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="6f86f-106">In AGPM 4.0, you can search the list of GPOs for specific attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="6f86f-107">例如，您可以搜尋具有特定名稱、狀態或批註的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6f86f-107">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="6f86f-108">您也可以搜尋由特定群組原則系統管理員或特定日期所變更的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="6f86f-108">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

<span data-ttu-id="6f86f-109">您可以使用 [格式化*GPO 屬性1：搜尋文字 1 GPO 屬性2：搜尋文字 2 ...*]，其中 gpo 屬性是 AGPM 中 gpo 清單中的任何欄標題。</span><span class="sxs-lookup"><span data-stu-id="6f86f-109">You can create a complex search string by using the format *GPO attribute 1: search text 1 GPO attribute 2: search text 2…*, where a GPO attribute is any column heading in the list of GPOs in AGPM.</span></span> <span data-ttu-id="6f86f-110">例如，若要搜尋包含已取出且由使用者 Editor03 最後變更之文字「MyGPO」的所有 Gpo，您可以在 [搜尋] 方塊中輸入下列內容： **name： MyGPO state：** 已依下列方式**核**取 **： Editor03**。</span><span class="sxs-lookup"><span data-stu-id="6f86f-110">For example, to search for all GPOs with names including the text "MyGPO" that are checked in and were last changed by the user Editor03, you would type the following in the Search box: **name: MyGPO state:\*\*\*\*checked in\*\*\*\*changed by: Editor03**.</span></span> <span data-ttu-id="6f86f-111">搜尋會傳回部分相符的專案，讓您輸入部分的 GPO 名稱或使用者名稱，並查看其名稱中包含該文字的所有 Gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="6f86f-111">The search returns partial matches so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="6f86f-112">此外，您也可以使用在 Windows 中搜尋時所提供的相同特殊字詞，在特定日期或日期範圍內搜尋 Gpo 已變更。</span><span class="sxs-lookup"><span data-stu-id="6f86f-112">Additionally, you can use the same special terms available when you search in Windows to search for GPOs changed on a specific date or range of dates.</span></span> <span data-ttu-id="6f86f-113">例如，[**變更日期：\*\*\*\*lastmonth** ] 或 [**變更日期]：\*\*\*\*thisweek**。</span><span class="sxs-lookup"><span data-stu-id="6f86f-113">For example, **change date:\*\*\*\*lastmonth** or **change date:\*\*\*\*thisweek**.</span></span>

## <span data-ttu-id="6f86f-114">匯出及匯入 Gpo 至不同的林</span><span class="sxs-lookup"><span data-stu-id="6f86f-114">Export and import GPOs to different forests</span></span>


<span data-ttu-id="6f86f-115">您可以使用 AGPM 4.0，將受控的 GPO 從一個目錄林中的網域複製到第二個林中的網域。</span><span class="sxs-lookup"><span data-stu-id="6f86f-115">Using AGPM 4.0, you can copy a controlled GPO from a domain in one forest to a domain in a second forest.</span></span> <span data-ttu-id="6f86f-116">例如，您可以使用 AGPM 將 GPO 從某個林中的網域匯出到 CAB 檔案，然後將該 CAB 檔案複製到 USB 磁片磁碟機，將 USB 磁片磁碟機插入第二個目錄林中網域中的電腦，然後將該 GPO 匯入到第二個目錄林中網域的 AGPM 中。</span><span class="sxs-lookup"><span data-stu-id="6f86f-116">For example, you can export a GPO from a domain in one forest to a CAB file by using AGPM, copy that CAB file to a USB drive, plug the USB drive into a computer in a domain in a second forest, and import the GPO into AGPM in a domain in the second forest.</span></span> <span data-ttu-id="6f86f-117">您可以將 GPO 匯入為新的受控 GPO，或將它匯入以取代已取出之現有 GPO 的設定。</span><span class="sxs-lookup"><span data-stu-id="6f86f-117">You can either import the GPO as a new controlled GPO, or import it to replace the settings of an existing GPO that is checked out.</span></span>

## <span data-ttu-id="6f86f-118">Windows Server 2008 R2 和 Windows 7 的支援</span><span class="sxs-lookup"><span data-stu-id="6f86f-118">Support for Windows Server 2008 R2 and Windows 7</span></span>


<span data-ttu-id="6f86f-119">AGPM 4.0 支援 Windows Server2008R2 和 Windows7，但仍支援 Windows Server2008，且 WindowsVista Service Pack1 （SP1）®。</span><span class="sxs-lookup"><span data-stu-id="6f86f-119">AGPM 4.0 supports Windows Server2008R2 and Windows7, yet still supports Windows Server2008 and WindowsVista® with Service Pack1 (SP1).</span></span> <span data-ttu-id="6f86f-120">不過，混合環境會有一些限制，包括較新及較舊的作業系統，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6f86f-120">However, there are limitations in a mixed environment that includes both the newer and older operating systems, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6f86f-121">在其上執行 AGPM Server 4.0 的作業系統</span><span class="sxs-lookup"><span data-stu-id="6f86f-121">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="6f86f-122">在其上執行 AGPM 用戶端4.0 的作業系統</span><span class="sxs-lookup"><span data-stu-id="6f86f-122">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="6f86f-123">AGPM 4.0 支援的狀態</span><span class="sxs-lookup"><span data-stu-id="6f86f-123">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f86f-124">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="6f86f-124">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-125">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="6f86f-125">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-126">支援</span><span class="sxs-lookup"><span data-stu-id="6f86f-126">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f86f-127">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="6f86f-127">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-128">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="6f86f-128">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-129">支援，但無法編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="6f86f-129">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f86f-130">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="6f86f-130">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-131">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="6f86f-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-132">不支援</span><span class="sxs-lookup"><span data-stu-id="6f86f-132">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f86f-133">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="6f86f-133">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-134">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="6f86f-134">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f86f-135">支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="6f86f-135">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





