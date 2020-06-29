---
title: MED-V 安裝檔案的命令列選項
description: MED-V 安裝檔案的命令列選項
author: dansimp
ms.assetid: 7b8cd3e4-1d09-44a0-b690-f85b0d0a6b02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39582a592a59a4d0e81ef406edc6a984497275c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811774"
---
# <span data-ttu-id="543a5-103">MED-V 安裝檔案的命令列選項</span><span class="sxs-lookup"><span data-stu-id="543a5-103">Command-Line Options for MED-V Installation Files</span></span>


<span data-ttu-id="543a5-104">當您安裝或卸載 Microsoft 企業桌面虛擬化（MED-V）2.0 時，您可以選擇在命令提示字元執行安裝檔。</span><span class="sxs-lookup"><span data-stu-id="543a5-104">When you install or uninstall Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you have the option of running the installation files at the command prompt.</span></span> <span data-ttu-id="543a5-105">本節說明您可以在命令提示字元上安裝或卸載 MED-V 時指定的不同選項。</span><span class="sxs-lookup"><span data-stu-id="543a5-105">This section describes different options that you can specify when you install or uninstall MED-V at the command prompt.</span></span>

### <span data-ttu-id="543a5-106">命令列引數</span><span class="sxs-lookup"><span data-stu-id="543a5-106">Command-Line Arguments</span></span>

<span data-ttu-id="543a5-107">您可以將下列命令列引數與它們各自的 MED-V 安裝檔案搭配使用。</span><span class="sxs-lookup"><span data-stu-id="543a5-107">You can use the following command-line arguments together with their respective MED-V installation files.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="543a5-108">安裝檔</span><span class="sxs-lookup"><span data-stu-id="543a5-108">Installation File</span></span></th>
<th align="left"><span data-ttu-id="543a5-109">引數</span><span class="sxs-lookup"><span data-stu-id="543a5-109">Argument</span></span></th>
<th align="left"><span data-ttu-id="543a5-110">已接受的值</span><span class="sxs-lookup"><span data-stu-id="543a5-110">Accepted Values</span></span></th>
<th align="left"><span data-ttu-id="543a5-111">類型</span><span class="sxs-lookup"><span data-stu-id="543a5-111">Type</span></span></th>
<th align="left"><span data-ttu-id="543a5-112">描述</span><span class="sxs-lookup"><span data-stu-id="543a5-112">Description</span></span></th>
<th align="left"><span data-ttu-id="543a5-113">預設值</span><span class="sxs-lookup"><span data-stu-id="543a5-113">Default</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="543a5-114">主機代理程式</span><span class="sxs-lookup"><span data-stu-id="543a5-114">Host Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-115">MEDVDIR</span><span class="sxs-lookup"><span data-stu-id="543a5-115">MEDVDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-116">&lt;安裝路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="543a5-116">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-117">安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-117">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-118">變更已安裝的目錄</span><span class="sxs-lookup"><span data-stu-id="543a5-118">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-119">安裝程式會移至 Program Files\Microsoft 企業版桌面虛擬化。</span><span class="sxs-lookup"><span data-stu-id="543a5-119">Installation goes to Program Files\Microsoft Enterprise Desktop Virtualization.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="543a5-120">MED-V-V 工作區包裝程式</span><span class="sxs-lookup"><span data-stu-id="543a5-120">MED-V Workspace Packager</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-121">MEDVDIR</span><span class="sxs-lookup"><span data-stu-id="543a5-121">MEDVDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-122">&lt;安裝路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="543a5-122">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-123">安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-123">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-124">變更已安裝的目錄</span><span class="sxs-lookup"><span data-stu-id="543a5-124">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-125">安裝程式會移至 Program Files\Microsoft 企業版桌面虛擬化。</span><span class="sxs-lookup"><span data-stu-id="543a5-125">Installation goes to Program Files\Microsoft Enterprise Desktop Virtualization.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="543a5-126">MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="543a5-126">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-127">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="543a5-127">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-128">&lt;安裝路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="543a5-128">&lt;install path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-129">安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-129">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-130">變更已安裝的目錄</span><span class="sxs-lookup"><span data-stu-id="543a5-130">Change installed directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-131">安裝移至 ProgramData\Microsoft\Medv\Workspace。</span><span class="sxs-lookup"><span data-stu-id="543a5-131">Installation goes to ProgramData\Microsoft\Medv\Workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="543a5-132">MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="543a5-132">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-133">覆寫 VHD</span><span class="sxs-lookup"><span data-stu-id="543a5-133">OVERWRITE VHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-134">0 或 1</span><span class="sxs-lookup"><span data-stu-id="543a5-134">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-135">安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-135">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-136">如果 VHD 存在（0）或覆寫現有的 VHD （1），則無法安裝。</span><span class="sxs-lookup"><span data-stu-id="543a5-136">Fail installation if VHD exists(0) or overwrite existing VHD(1).</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-137">如果虛擬硬碟（VHD）已經存在，則不會發生覆寫，且安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="543a5-137">Overwrite does not occur and installation fails if a virtual hard disk (VHD) already exists.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="543a5-138">MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="543a5-138">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-139">SUPPRESSMEDVLAUNCH</span><span class="sxs-lookup"><span data-stu-id="543a5-139">SUPPRESSMEDVLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-140">0 或 1</span><span class="sxs-lookup"><span data-stu-id="543a5-140">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-141">安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-141">Installation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-142">啟動（0）或 [不啟動] （1）安裝 MED-V 工作區後的 MED-V。</span><span class="sxs-lookup"><span data-stu-id="543a5-142">Start(0) or do not start(1) MED-V after MED-V workspace is installed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-143">如果 MED-V 工作區是與使用者介面（UI）一起安裝，則 [完成] 頁面上的核取方塊會 <strong> </strong> 控制是否要啟動 med-v。</span><span class="sxs-lookup"><span data-stu-id="543a5-143">If the MED-V workspace was installed with the user interface (UI), a check box on the <strong>Finish</strong> page controls whether to start MED-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="543a5-144">MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="543a5-144">MED-V workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-145">DELETEDIFFDISKS</span><span class="sxs-lookup"><span data-stu-id="543a5-145">DELETEDIFFDISKS</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-146">0 或 1</span><span class="sxs-lookup"><span data-stu-id="543a5-146">0 or 1</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-147">解除安裝</span><span class="sxs-lookup"><span data-stu-id="543a5-147">Uninstallation</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-148">保留（0）或刪除（1）由 MED-V 建立的 Vhd-V</span><span class="sxs-lookup"><span data-stu-id="543a5-148">Keep(0) or delete(1) VHDs created by MED-V</span></span></p></td>
<td align="left"><p><span data-ttu-id="543a5-149">不會刪除任何 Vhd。</span><span class="sxs-lookup"><span data-stu-id="543a5-149">No VHDs are deleted.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="543a5-150">命令列引數的範例</span><span class="sxs-lookup"><span data-stu-id="543a5-150">Examples of Command-Line Arguments</span></span>

<span data-ttu-id="543a5-151">下列範例會安裝由 MED-V 工作區包裝程式所建立的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="543a5-151">The following example installs the MED-V workspace created by the MED-V workspace Packager.</span></span> <span data-ttu-id="543a5-152">安裝檔案會在 Temp 目錄中建立一個記錄檔案，並以安靜模式執行安裝檔案，但在完成時不會啟動 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="543a5-152">The installation file creates a log file in the Temp directory and runs the installation file in quiet mode, but does not start the MED-V Host Agent on completion.</span></span> <span data-ttu-id="543a5-153">安裝檔案會覆寫您先前安裝的相同名稱留下的任何 VHD。</span><span class="sxs-lookup"><span data-stu-id="543a5-153">The installation file overwrites any VHD left behind by a previous installation that has the same name.</span></span>

``` syntax
setup.exe /l* %temp%\medv-workspace-install.log /qn SUPPRESSMEDVLAUNCH=1 OVERWRITEVHD=1
```

<span data-ttu-id="543a5-154">下列範例會卸載先前安裝的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="543a5-154">The following example uninstalls the MED-V workspace that was previously installed.</span></span> <span data-ttu-id="543a5-155">安裝檔案會在 Temp 目錄中建立一個記錄檔案，並以安靜模式執行安裝檔。</span><span class="sxs-lookup"><span data-stu-id="543a5-155">The installation file creates a log file in the Temp directory and runs the installation file in quiet mode.</span></span> <span data-ttu-id="543a5-156">安裝檔案會從檔案系統中刪除所有剩餘的虛擬硬碟檔案。</span><span class="sxs-lookup"><span data-stu-id="543a5-156">The installation file deletes any remaining virtual hard disk files from the file system.</span></span>

``` syntax
%ProgramData%\Microsoft\Medv\Workspace\uninstall.exe /l* %temp%\medv-workspace-uninstall.log /qn DELETEDIFFDISKS=1
```

## <span data-ttu-id="543a5-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="543a5-157">Related topics</span></span>


[<span data-ttu-id="543a5-158">部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="543a5-158">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)

[<span data-ttu-id="543a5-159">MED-V 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="543a5-159">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





