---
title: 如何以使用者發佈的套件與全域發佈的套件建立連線群組
description: 如何以使用者發佈的套件與全域發佈的套件建立連線群組
author: dansimp
ms.assetid: 82f7ea7f-7b14-4506-8940-fdcd6c3e117f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: c98981180133881909db17d19cb42771f94bd66a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800572"
---
# <span data-ttu-id="a3b21-103">如何以使用者發佈的套件與全域發佈的套件建立連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-103">How to Create a Connection Group with User-Published and Globally Published Packages</span></span>
<span data-ttu-id="a3b21-104">您可以使用下列其中一種方法，建立包含使用者發佈與全域發佈套件的使用者擁有資格的連接群組：</span><span class="sxs-lookup"><span data-stu-id="a3b21-104">You can create user-entitled connection groups that contain both user-published and globally published packages, using either of the following methods:</span></span>

-   [<span data-ttu-id="a3b21-105">如何使用 PowerShell Cmdlet 來建立使用者擁有資格的連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-105">How to use PowerShell cmdlets to create the user-entitled connection groups</span></span>](#bkmk-posh-userentitled-cg)

-   [<span data-ttu-id="a3b21-106">如何使用 App-v Server 來建立使用者擁有資格的連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-106">How to use the App-V Server to create the user-entitled connection groups</span></span>](#bkmk-appvserver-userentitled-cg)

**<span data-ttu-id="a3b21-107">開始之前的須知：</span><span class="sxs-lookup"><span data-stu-id="a3b21-107">What to know before you start:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3b21-108">不支援的案例和可能的問題</span><span class="sxs-lookup"><span data-stu-id="a3b21-108">Unsupported scenarios and potential issues</span></span></th>
<th align="left"><span data-ttu-id="a3b21-109">結果</span><span class="sxs-lookup"><span data-stu-id="a3b21-109">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3b21-110">您不能在全域名為 [連線群組] 中包含使用者發佈的套件。</span><span class="sxs-lookup"><span data-stu-id="a3b21-110">You cannot include user-published packages in globally entitled connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3b21-111">[連接] 群組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a3b21-111">The connection group will fail.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3b21-112">如果您要全域發佈套件，然後建立使用者發佈的連線群組（您已將該套件設為非選用），您仍然可以執行 <strong> 取消發佈-AppvClientPackage &lt; 套件 &gt; -global </strong> 以取消發佈套件，即使該套件是在另一個連線群組中使用時也一樣。</span><span class="sxs-lookup"><span data-stu-id="a3b21-112">If you publish a package globally and then create a user-published connection group in which you’ve made that package non-optional, you can still run <strong>Unpublish-AppvClientPackage &lt;package&gt; -global</strong> to unpublish the package, even when that package is being used in another connection group.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3b21-113">如果有任何其他的連線群組正在使用該套件，則這些連線群組中的套件將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a3b21-113">If any other connection groups are using that package, the package will fail in those connection groups.</span></span></p>
<p><span data-ttu-id="a3b21-114">為了避免無意間取消發佈其他連線群組中使用的非選用套件，我們建議您追蹤已使用非選用套件的連線群組。</span><span class="sxs-lookup"><span data-stu-id="a3b21-114">To avoid inadvertently unpublishing a non-optional package that is being used in another connection group, we recommend that you track the connection groups in which you’ve used a non-optional package.</span></span></p></td>
</tr>
</tbody>
</table>

 
<a href="" id="bkmk-posh-userentitled-cg"></a>**<span data-ttu-id="a3b21-115">如何使用 PowerShell Cmdlet 來建立使用者擁有資格的連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-115">How to use PowerShell cmdlets to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="a3b21-116">使用下列命令新增及發佈套件：</span><span class="sxs-lookup"><span data-stu-id="a3b21-116">Add and publish packages by using the following commands:</span></span>

    **<span data-ttu-id="a3b21-117">AppvClientPackage Package1 \ _AppV _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="a3b21-117">Add-AppvClientPackage Package1\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="a3b21-118">AppvClientPackage Package2 \ _AppV _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="a3b21-118">Add-AppvClientPackage Package2\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="a3b21-119">Publish-AppvClientPackage-PackageId Package1 \ _ID VersionId Package1 \ _Version 識別碼-全域</span><span class="sxs-lookup"><span data-stu-id="a3b21-119">Publish-AppvClientPackage -PackageId Package1\_ID-VersionId Package1\_Version ID -Global</span></span>**

    **<span data-ttu-id="a3b21-120">Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID</span><span class="sxs-lookup"><span data-stu-id="a3b21-120">Publish-AppvClientPackage -PackageId Package2\_ID -VersionIdPackage2\_ID</span></span>**

2.  <span data-ttu-id="a3b21-121">建立連線群組 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="a3b21-121">Create the connection group XML file.</span></span> <span data-ttu-id="a3b21-122">如需詳細資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="a3b21-122">For more information, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

3.  <span data-ttu-id="a3b21-123">使用下列命令新增及發佈 [連線] 群組：</span><span class="sxs-lookup"><span data-stu-id="a3b21-123">Add and publish the connection group by using the following commands:</span></span>

    **<span data-ttu-id="a3b21-124">載入 AppvClientConnectionGroup 連線 _Group \ _XML \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="a3b21-124">Add-AppvClientConnectionGroup Connection\_Group\_XML\_file\_Path</span></span>**

    **<span data-ttu-id="a3b21-125">Enable-AppvClientConnectionGroup-GroupId CG \ _Group \ _ID VersionId CG \ _Version \ _ID</span><span class="sxs-lookup"><span data-stu-id="a3b21-125">Enable-AppvClientConnectionGroup -GroupId CG\_Group\_ID-VersionId CG\_Version\_ID</span></span>**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**<span data-ttu-id="a3b21-126">如何使用 App-v Server 來建立使用者擁有資格的連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-126">How to use the App-V Server to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="a3b21-127">開啟 App-V 5.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="a3b21-127">Open the App-V 5.0 Management Console.</span></span>

2.  <span data-ttu-id="a3b21-128">請依照[如何使用管理主控台](how-to-publish-a-package-by-using-the-management-console-50.md)來將套件發佈至全域及使用者的方式，按照如何發佈套件的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a3b21-128">Follow the instructions in [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md) to publish packages globally and to the user.</span></span>

3.  <span data-ttu-id="a3b21-129">依照[如何建立連線群組](how-to-create-a-connection-group.md)以建立連線群組，以及新增使用者發佈及全域發佈的套件中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="a3b21-129">Follow the instructions in [How to Create a Connection Group](how-to-create-a-connection-group.md) to create the connection group, and add the user-published and globally published packages.</span></span>

    <span data-ttu-id="a3b21-130">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a3b21-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a3b21-131">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a3b21-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a3b21-132">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a3b21-132">Got an App-V issue?</span></span>** <span data-ttu-id="a3b21-133">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a3b21-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a3b21-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3b21-134">Related topics</span></span>


[<span data-ttu-id="a3b21-135">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="a3b21-135">Managing Connection Groups</span></span>](managing-connection-groups.md)

[<span data-ttu-id="a3b21-136">如何在連線群組中使用選用套件</span><span class="sxs-lookup"><span data-stu-id="a3b21-136">How to Use Optional Packages in Connection Groups</span></span>](how-to-use-optional-packages-in-connection-groups.md)

 

 





