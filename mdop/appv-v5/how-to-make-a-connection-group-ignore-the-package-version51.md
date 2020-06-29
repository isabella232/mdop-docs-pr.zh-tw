---
title: 如何讓連線群組略過套件版本
description: 如何讓連線群組略過套件版本
author: dansimp
ms.assetid: db16b095-dbe2-42c7-863d-b0d5d91b2f4c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 026ef1b3a2aa073a684b1fe5da4f79aa1067072d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800467"
---
# <span data-ttu-id="e487b-103">如何讓連線群組略過套件版本</span><span class="sxs-lookup"><span data-stu-id="e487b-103">How to Make a Connection Group Ignore the Package Version</span></span>


<span data-ttu-id="e487b-104">Microsoft Application Virtualization （App-v）5.1 可讓您將連接群組設定為使用任何版本的套件，這可簡化套件升級並減少您需要建立的連線群組數量。</span><span class="sxs-lookup"><span data-stu-id="e487b-104">Microsoft Application Virtualization (App-V) 5.1 lets you configure a connection group to use any version of a package, which simplifies package upgrades and reduces the number of connection groups you need to create.</span></span>

<span data-ttu-id="e487b-105">若要在一些舊版 App-v 中升級套件，您必須執行數個步驟，包括停用連線群組及修改連線群組的 XML 定義檔案。</span><span class="sxs-lookup"><span data-stu-id="e487b-105">To upgrade a package in some earlier versions of App-V, you had to perform several steps, including disabling the connection group and modifying the connection group’s XML definition file.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e487b-106">App-V 5.1 的任務描述</span><span class="sxs-lookup"><span data-stu-id="e487b-106">Task description with App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="e487b-107">如何使用 App-v 5.1 執行任務</span><span class="sxs-lookup"><span data-stu-id="e487b-107">How to perform the task with App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e487b-108">您可以將連線群組設定為接受任何版本的套件，這可讓您在不需停用連線群組的情況下升級套件。</span><span class="sxs-lookup"><span data-stu-id="e487b-108">You can configure a connection group to accept any version of a package, which enables you to upgrade the package without having to disable the connection group.</span></span></p>
<p><strong><span data-ttu-id="e487b-109">此功能的運作方式：</span><span class="sxs-lookup"><span data-stu-id="e487b-109">How the feature works:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="e487b-110">如果連線群組有權存取多個版本的套件，則會使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="e487b-110">If the connection group has access to multiple versions of a package, the latest version is used.</span></span></p></li>
<li><p><span data-ttu-id="e487b-111">如果連線群組包含不正確版本的選用套件，則會忽略套件，而且不會封鎖連接群組的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="e487b-111">If the connection group contains an optional package that has an incorrect version, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></li>
<li><p><span data-ttu-id="e487b-112">如果連接群組包含不正確版本的非選用套件，則無法建立連線群組的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="e487b-112">If the connection group contains a non-optional package that has an incorrect version, the connection group’s virtual environment cannot be created.</span></span></p></li>
</ul></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e487b-113">方法</span><span class="sxs-lookup"><span data-stu-id="e487b-113">Method</span></span></th>
<th align="left"><span data-ttu-id="e487b-114">步驟</span><span class="sxs-lookup"><span data-stu-id="e487b-114">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e487b-115">App-v Server –管理主控台</span><span class="sxs-lookup"><span data-stu-id="e487b-115">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="e487b-116">在管理主控台中，選取 [連線 <strong> 群組] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e487b-116">In the Management Console, select <strong>CONNECTION GROUPS</strong>.</span></span></p></li>
<li><p><span data-ttu-id="e487b-117">從連線群組程式庫中選取正確的連線群組。</span><span class="sxs-lookup"><span data-stu-id="e487b-117">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="e487b-118">按一下 <strong> </strong> [連線的套件] 窗格中的 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="e487b-118">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="e487b-119">選取 <strong> </strong> 套件名稱旁邊的 [使用任何版本] 核取方塊，然後按一下 [套用] <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e487b-119">Select <strong>Use Any Version</strong> check box next to the package name, and click <strong>Apply</strong>.</span></span></p></li>
</ol>
<p><span data-ttu-id="e487b-120">如需新增或升級套件的詳細資訊，請參閱 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)"> 如何使用管理主控台新增或升級套件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="e487b-120">For more about adding or upgrading packages, see <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)">How to Add or Upgrade Packages by Using the Management Console</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e487b-121">在獨立電腦上使用 app-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="e487b-121">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="e487b-122">建立連線群組 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="e487b-122">Create the connection group XML document.</span></span></p></li>
<li><p><span data-ttu-id="e487b-123">若要升級套件，請將 [套件標籤 <strong> </strong> 屬性 VersionID] 設定 <strong> </strong> 為星號（ <strong>\*</strong> ）。</span><span class="sxs-lookup"><span data-stu-id="e487b-123">For the package to be upgraded, set the <strong>Package</strong> tag attribute <strong>VersionID</strong> to an asterisk (<strong>\*</strong>).</span></span></p></li>
<li><p><span data-ttu-id="e487b-124">使用下列 Cmdlet 來新增連線群組，並包含連線群組 XML 檔的路徑：</span><span class="sxs-lookup"><span data-stu-id="e487b-124">Use the following cmdlet to add the connection group, and include the path to the connection group XML document:</span></span></p>
<p><strong><span data-ttu-id="e487b-125">附加 AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="e487b-125">Add-AppvClientConnectionGroup</span></span></strong></p></li>
<li><p><span data-ttu-id="e487b-126">當您升級套件時，請使用下列 Cmdlet 來移除舊的套件、新增已升級的套件，併發布升級後的套件：</span><span class="sxs-lookup"><span data-stu-id="e487b-126">When you upgrade a package, use the following cmdlets to remove the old package, add the upgraded package, and publish the upgraded package:</span></span></p>
<ul>
<li><p><span data-ttu-id="e487b-127">RemoveAppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="e487b-127">RemoveAppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="e487b-128">附加 AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="e487b-128">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="e487b-129">發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="e487b-129">Publish-AppvClientPackage</span></span></p></li>
</ul></li>
</ol>
<p><span data-ttu-id="e487b-130">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e487b-130">For more information, see:</span></span></p>
<ul>
<li><p><span data-ttu-id="e487b-131">此區段中的範例 XML 檔案（ <strong> 含選用套件的連線群組 XML 檔案 </strong> ）：如何在連線 <a href="how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional)"> 群組中使用選用套件</span><span class="sxs-lookup"><span data-stu-id="e487b-131">The example XML file, <strong>Connection group XML file with optional packages</strong>, in this section: <a href="how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional)">How to Use Optional Packages in Connection Groups</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="e487b-132">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="e487b-132">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="e487b-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="e487b-133">Related topics</span></span>


[<span data-ttu-id="e487b-134">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="e487b-134">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





