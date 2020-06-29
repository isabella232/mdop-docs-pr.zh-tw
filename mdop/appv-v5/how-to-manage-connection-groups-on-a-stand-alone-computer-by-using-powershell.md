---
title: 如何使用 PowerShell 來管理獨立電腦上的連線群組
description: 如何使用 PowerShell 來管理獨立電腦上的連線群組
author: dansimp
ms.assetid: b73ae74d-8a6f-4bb3-b1f2-0067c7bd5212
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 32dd4f9c5ad1ba4ae9e25246d5ec52a6363ef303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800465"
---
# <span data-ttu-id="fd8f2-103">如何使用 PowerShell 來管理獨立電腦上的連線群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-103">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span>


<span data-ttu-id="fd8f2-104">App-v 連線群組可讓您在單一虛擬環境中，以一組已定義套件的形式來執行所有虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-104">An App-V connection group allows you to run all the virtual applications as a defined set of packages in a single virtual environment.</span></span> <span data-ttu-id="fd8f2-105">例如，您可以使用個別的套件，將應用程式及其外掛程式虛擬化，但在單一連線群組中一起執行。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-105">For example, you can virtualize an application and its plug-ins by using separate packages, but run them together in a single connection group.</span></span>

<span data-ttu-id="fd8f2-106">連線群組 XML 檔案會定義在您已安裝 App-v 用戶端的電腦上執行的連線群組。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-106">A connection group XML file defines the connection group that runs on the computer where you’ve installed the App-V client.</span></span> <span data-ttu-id="fd8f2-107">如需連線群組 XML 檔案及其設定方式的相關資訊，請參閱[關於連線群組](about-the-connection-group-file.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-107">For information about the connection group XML file and how to configure it, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

<span data-ttu-id="fd8f2-108">本主題說明下列程式：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-108">This topic explains the following procedures:</span></span>

-   [<span data-ttu-id="fd8f2-109">在連線群組中新增併發布 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="fd8f2-109">To add and publish the App-V packages in the connection group</span></span>](#bkmk-add-pub-pkgs-in-cg)

-   [<span data-ttu-id="fd8f2-110">在 App-V 用戶端上新增並啟用 [連線] 群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-110">To add and enable the connection group on the App-V client</span></span>](#bkmk-add-enable-cg-on-clt)

-   [<span data-ttu-id="fd8f2-111">啟用或停用特定使用者的連線群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-111">To enable or disable a connection group for a specific user</span></span>](#bkmk-enable-cg-for-user-poshtopic)

-   [<span data-ttu-id="fd8f2-112">僅允許系統管理員啟用連線群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-112">To allow only administrators to enable connection groups</span></span>](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a>**<span data-ttu-id="fd8f2-113">在連線群組中新增併發布 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="fd8f2-113">To add and publish the App-V packages in the connection group</span></span>**

1.  <span data-ttu-id="fd8f2-114">若要在執行 App-v 用戶端的電腦上新增併發布 App-v 5.0 套件，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-114">To add and publish the App-V 5.0 packages to the computer running the App-V client, type the following command:</span></span>

    <span data-ttu-id="fd8f2-115">AppvClientPackage – path c:\\tmpstore\\quartfin.appv |發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="fd8f2-115">Add-AppvClientPackage –path c:\\tmpstore\\quartfin.appv | Publish-AppvClientPackage</span></span>

2.  <span data-ttu-id="fd8f2-116">針對連接群組中的每個套件，重複執行此程式的**步驟 1** 。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-116">Repeat **step 1** of this procedure for each package in the connection group.</span></span>

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**<span data-ttu-id="fd8f2-117">在 App-V 用戶端上新增並啟用 [連線] 群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-117">To add and enable the connection group on the App-V client</span></span>**

1.  <span data-ttu-id="fd8f2-118">輸入下列命令以新增 [連線] 群組：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-118">Add the connection group by typing the following command:</span></span>

    <span data-ttu-id="fd8f2-119">AppvClientConnectionGroup – path c:\\tmpstore\\financ.xml</span><span class="sxs-lookup"><span data-stu-id="fd8f2-119">Add-AppvClientConnectionGroup –path c:\\tmpstore\\financ.xml</span></span>

2.  <span data-ttu-id="fd8f2-120">輸入下列命令以啟用 [連接] 群組：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-120">Enable the connection group by typing the following command:</span></span>

    <span data-ttu-id="fd8f2-121">Enable-AppvClientConnectionGroup – name "財務應用程式"</span><span class="sxs-lookup"><span data-stu-id="fd8f2-121">Enable-AppvClientConnectionGroup –name “Financial Applications”</span></span>

    <span data-ttu-id="fd8f2-122">當成員套件中的任何虛擬應用程式都在目的電腦上執行時，它們會在連線到連線群組的虛擬環境中執行，並將提供給連線群組中其他套件中的所有虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-122">When any virtual applications that are in the member packages are run on the target computer, they will run inside the connection group’s virtual environment and will be available to all the virtual applications in the other packages in the connection group.</span></span>

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**<span data-ttu-id="fd8f2-123">啟用或停用特定使用者的連線群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-123">To enable or disable a connection group for a specific user</span></span>**

1.  <span data-ttu-id="fd8f2-124">查看參數描述與需求：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-124">Review the parameter description and requirements:</span></span>

    -   <span data-ttu-id="fd8f2-125">此參數可讓系統管理員啟用或停用特定使用者的連線群組。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-125">The parameter enables an administrator to enable or disable a connection group for a specific user.</span></span>

    -   <span data-ttu-id="fd8f2-126">您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-126">You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

    -   <span data-ttu-id="fd8f2-127">您可以從使用者或系統管理員會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-127">You can run this cmdlet from the user or administrator session.</span></span>

    -   <span data-ttu-id="fd8f2-128">您必須以管理認證登入，才能使用此參數。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-128">You must be logged in with administrative credentials to use the parameter.</span></span>

    -   <span data-ttu-id="fd8f2-129">最終使用者必須登入。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-129">The end user must be logged in.</span></span>

    -   <span data-ttu-id="fd8f2-130">您必須提供最終使用者的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-130">You must provide the end user’s security identifier (SID).</span></span>

2.  <span data-ttu-id="fd8f2-131">使用下列 Cmdlet，並新增選擇性 **– UserSID**參數，其中 **-UserSID**代表最終使用者的安全性識別碼（SID）：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-131">Use the following cmdlets, and add the optional **–UserSID** parameter, where **-UserSID** represents the end user’s security identifier (SID):</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="fd8f2-132">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fd8f2-132">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="fd8f2-133">範例</span><span class="sxs-lookup"><span data-stu-id="fd8f2-133">Examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="fd8f2-134">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="fd8f2-134">Enable-AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fd8f2-135">Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="fd8f2-135">Enable-AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="fd8f2-136">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="fd8f2-136">Disable -AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fd8f2-137">Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="fd8f2-137">Disable -AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**<span data-ttu-id="fd8f2-138">僅允許系統管理員啟用連線群組</span><span class="sxs-lookup"><span data-stu-id="fd8f2-138">To allow only administrators to enable connection groups</span></span>**

1.  <span data-ttu-id="fd8f2-139">請參閱使用此 Cmdlet 的描述與需求：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-139">Review the description and requirement for using this cmdlet:</span></span>

    -   <span data-ttu-id="fd8f2-140">使用這個 Cmdlet 和參數設定 App-v 用戶端，只允許系統管理員（而非最終使用者）啟用或停用連線群組。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-140">Use this cmdlet and parameter to configure the App-V client to allow only administrators (not end users) to enable or disable connection groups.</span></span>

    -   <span data-ttu-id="fd8f2-141">您必須至少使用 App-v 5.0 SP3，才能使用此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-141">You must be using at least App-V 5.0 SP3 to use this cmdlet.</span></span>

2.  <span data-ttu-id="fd8f2-142">執行下列 Cmdlet 和參數：</span><span class="sxs-lookup"><span data-stu-id="fd8f2-142">Run the following cmdlet and parameter:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="fd8f2-143">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fd8f2-143">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="fd8f2-144">參數和值</span><span class="sxs-lookup"><span data-stu-id="fd8f2-144">Parameter and values</span></span></th>
    <th align="left"><span data-ttu-id="fd8f2-145">範例</span><span class="sxs-lookup"><span data-stu-id="fd8f2-145">Example</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="fd8f2-146">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd8f2-146">Set-AppvClientConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="fd8f2-147">–RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="fd8f2-147">–RequirePublishAsAdmin</span></span></p>
    <ul>
    <li><p><span data-ttu-id="fd8f2-148">0-False</span><span class="sxs-lookup"><span data-stu-id="fd8f2-148">0 - False</span></span></p></li>
    <li><p><span data-ttu-id="fd8f2-149">1-True</span><span class="sxs-lookup"><span data-stu-id="fd8f2-149">1 - True</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="fd8f2-150">Set-AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="fd8f2-150">Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="fd8f2-151">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="fd8f2-151">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="fd8f2-152">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-152">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="fd8f2-153">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="fd8f2-153">Got an App-V issue?</span></span>** <span data-ttu-id="fd8f2-154">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="fd8f2-154">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="fd8f2-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="fd8f2-155">Related topics</span></span>


[<span data-ttu-id="fd8f2-156">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="fd8f2-156">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="fd8f2-157">使用 PowerShell 管理 App-V</span><span class="sxs-lookup"><span data-stu-id="fd8f2-157">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





