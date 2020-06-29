---
title: 規劃要與 UE-V 1.0 同步處理的應用程式
description: 規劃要與 UE-V 1.0 同步處理的應用程式
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800088"
---
# <span data-ttu-id="3f8e3-103">規劃要與 UE-V 1.0 同步處理的應用程式</span><span class="sxs-lookup"><span data-stu-id="3f8e3-103">Planning Which Applications to Synchronize with UE-V 1.0</span></span>


<span data-ttu-id="3f8e3-104">Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案）來定義由 UE-V 捕獲並套用的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="3f8e3-105">UE-V 包含一組預先定義的設定位置範本，也可讓系統管理員為在企業中使用的協力廠商或商務用端應用程式建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-105">UE-V includes a set of predefined settings location templates and also allows administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="3f8e3-106">如果您是系統管理員，當您認為要在 UE-V 方案中包含哪些應用程式時，請考慮使用者可以自訂哪些設定，以及應用程式儲存其設定的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-106">As an administrator, when you consider which applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="3f8e3-107">並非所有應用程式都有可自訂或經常由使用者自訂的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-107">Not all applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="3f8e3-108">此外，並非所有應用程式設定都能安全地跨多部電腦或環境進行漫遊。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-108">In addition, not all applications settings can safely roam across multiple computers or environments.</span></span> <span data-ttu-id="3f8e3-109">同步處理符合下列準則的設定：</span><span class="sxs-lookup"><span data-stu-id="3f8e3-109">Synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="3f8e3-110">儲存在使用者可存取位置的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-110">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="3f8e3-111">例如，請勿同步處理在 system32 或在 registry 的 [在 HKCU 中] 區段中儲存的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-111">For example, do not synchronize settings that are stored in system32 or outside HKCU section of the registry.</span></span>

-   <span data-ttu-id="3f8e3-112">特定電腦不專用的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-112">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="3f8e3-113">例如，排除網路或硬體設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-113">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="3f8e3-114">可以在電腦之間同步處理的設定，不會造成資料損毀的風險。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-114">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="3f8e3-115">例如，請勿使用儲存在資料庫檔案中的設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-115">For example, do not use settings that are stored in a database file.</span></span>

## <span data-ttu-id="3f8e3-116">UE-V 提供的設定位置範本</span><span class="sxs-lookup"><span data-stu-id="3f8e3-116">Settings location templates that are included in UE-V</span></span>


**<span data-ttu-id="3f8e3-117">UE-V 應用程式設定位置範本</span><span class="sxs-lookup"><span data-stu-id="3f8e3-117">UE-V application settings location templates</span></span>**

<span data-ttu-id="3f8e3-118">UE-V agent 安裝軟體會安裝代理程式，並為常見的 Microsoft 應用程式登錄預設的設定位置範本組。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-118">The UE-V agent installation software installs the agent and registers a default group of settings location templates for common Microsoft applications.</span></span> <span data-ttu-id="3f8e3-119">這些設定位置範本會捕獲下列應用程式的設定值：</span><span class="sxs-lookup"><span data-stu-id="3f8e3-119">These settings location templates capture settings values for the following applications:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="3f8e3-120">應用程式類別</span><span class="sxs-lookup"><span data-stu-id="3f8e3-120">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="3f8e3-121">描述</span><span class="sxs-lookup"><span data-stu-id="3f8e3-121">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f8e3-122">Microsoft Office 2010 應用程式</span><span class="sxs-lookup"><span data-stu-id="3f8e3-122">Microsoft Office 2010 applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-123">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-123">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="3f8e3-124">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-124">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="3f8e3-125">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-125">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="3f8e3-126">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-126">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="3f8e3-127">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-127">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="3f8e3-128">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-128">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="3f8e3-129">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-129">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="3f8e3-130">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-130">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="3f8e3-131">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-131">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="3f8e3-132">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-132">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="3f8e3-133">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-133">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="3f8e3-134">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="3f8e3-134">Microsoft OneNote 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f8e3-135">瀏覽器選項（Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10）</span><span class="sxs-lookup"><span data-stu-id="3f8e3-135">Browser options (Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-136">[我的最愛]、[首頁]、[定位點] 和工具列</span><span class="sxs-lookup"><span data-stu-id="3f8e3-136">Favorites, home page, tabs, and toolbars.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f8e3-137">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="3f8e3-137">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-138">[計算機]、[記事本]、[寫字板]。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-138">Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3f8e3-139">當應用程式啟動時，應用程式設定會套用到應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-139">Application settings are applied to the application when the application is started.</span></span> <span data-ttu-id="3f8e3-140">當應用程式關閉時，就會儲存這些專案。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-140">They are saved when the application closes.</span></span>

**<span data-ttu-id="3f8e3-141">UE-V Windows 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="3f8e3-141">UE-V Windows settings location templates</span></span>**

<span data-ttu-id="3f8e3-142">使用者體驗虛擬化包括設定位置範本，可捕獲下列 Windows 設定的設定值：</span><span class="sxs-lookup"><span data-stu-id="3f8e3-142">User Experience Virtualization includes settings location templates that capture settings values for the following Windows settings:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f8e3-143">Windows 設定</span><span class="sxs-lookup"><span data-stu-id="3f8e3-143">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="3f8e3-144">描述</span><span class="sxs-lookup"><span data-stu-id="3f8e3-144">Description</span></span></th>
<th align="left"><span data-ttu-id="3f8e3-145">適用</span><span class="sxs-lookup"><span data-stu-id="3f8e3-145">Apply on</span></span></th>
<th align="left"><span data-ttu-id="3f8e3-146">預設狀態</span><span class="sxs-lookup"><span data-stu-id="3f8e3-146">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f8e3-147">桌面背景</span><span class="sxs-lookup"><span data-stu-id="3f8e3-147">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-148">目前處於作用中桌面的背景。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-148">Currently active desktop background.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-149">登入、解除鎖定、遠端連線。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-149">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-150">啟用</span><span class="sxs-lookup"><span data-stu-id="3f8e3-150">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f8e3-151">輕鬆存取</span><span class="sxs-lookup"><span data-stu-id="3f8e3-151">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-152">[協助工具] 和 [輸入設定]、[放大鏡]、[朗讀程式] 和螢幕小鍵盤。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-152">Accessibility and input settings, magnifier, Narrator, and on-Screen keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-153">登入、解除鎖定、遠端連線。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-153">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-154">停用</span><span class="sxs-lookup"><span data-stu-id="3f8e3-154">Disabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f8e3-155">桌面設定</span><span class="sxs-lookup"><span data-stu-id="3f8e3-155">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-156">[開始] 功能表和工作列設定、[資料夾選項]、[預設桌面圖示]、[其他時鐘] 和 [地區及語言設定]。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-156">Start menu and Taskbar settings, Folder options, default desktop icons, additional clocks, and region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-157">僅限登入。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-157">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f8e3-158">停用</span><span class="sxs-lookup"><span data-stu-id="3f8e3-158">Disabled</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3f8e3-159">當使用者登入時、電腦已解除鎖定，或遠端連線至其他電腦時，就會套用 Windows 桌面背景和 [輕鬆存取] 設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-159">The Windows desktop background and Ease of Access settings are applied when the user logs on, when the computer is unlocked, or upon remote connection to another computer.</span></span> <span data-ttu-id="3f8e3-160">當使用者登出、電腦鎖定時，或當遠端連線中斷時，agent 會儲存這些設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-160">The agent saves these settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="3f8e3-161">根據預設，Windows 桌面背景設定是在相同作業系統版本的電腦之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-161">By default, Windows desktop background settings are roamed between computers of the same operating system version.</span></span>

<span data-ttu-id="3f8e3-162">Windows 桌面和 [輕鬆存取] 設定會在登入桌面之後套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-162">Windows desktop and Ease of Access settings are applied at logon before the desktop is presented to the user.</span></span> <span data-ttu-id="3f8e3-163">若要優化登入體驗，預設不會漫遊這些設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-163">To optimize the logon experience, these settings are not roamed by default.</span></span> <span data-ttu-id="3f8e3-164">您可以使用群組原則、PowerShell 及 WMI 來啟用 [桌面] 和 [輕鬆存取] 設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-164">Desktop and Ease of Access settings can be enabled by using Group Policy, PowerShell, and WMI.</span></span>

<span data-ttu-id="3f8e3-165">UE-V 不支援在不同語言的作業系統之間漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-165">UE-V does not support the roaming of settings between operating systems with different languages.</span></span> <span data-ttu-id="3f8e3-166">例如，不支援英文與德文之間的同步處理。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-166">For example, synchronization between English and German is not supported.</span></span> <span data-ttu-id="3f8e3-167">UE-V 漫遊使用者設定必須符合的所有電腦的語言。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-167">The language of all computers to which UE-V roams the user settings must match.</span></span>

<span data-ttu-id="3f8e3-168">**記事** 如果您變更 Microsoft 所提供的設定位置範本，使用者體驗虛擬化可能無法針對指定的應用程式或 Windows 設定群組正常運作。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-168">**Note** If you change the settings location templates that are provided by Microsoft, User Experience Virtualization might not work properly for the designated application or Windows settings group.</span></span>

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a><span data-ttu-id="3f8e3-169">防止無意間的使用者設定設定</span><span class="sxs-lookup"><span data-stu-id="3f8e3-169">Prevent unintentional user Settings configuration</span></span>


<span data-ttu-id="3f8e3-170">使用者體驗虛擬化會檢查新的使用者設定資訊，並從設定儲存位置下載該資訊。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-170">User Experience Virtualization checks for new user settings information, and downloads that information accordingly from a settings storage location.</span></span> <span data-ttu-id="3f8e3-171">然後，在下列情況下，它會將設定套用到本機電腦：</span><span class="sxs-lookup"><span data-stu-id="3f8e3-171">Then, it applies the settings to the local computer in the following cases:</span></span>

-   <span data-ttu-id="3f8e3-172">每次啟動應用程式時，都會有已註冊的 UE-V 範本。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-172">Every time an application is launched that has a registered UE-V template.</span></span>

-   <span data-ttu-id="3f8e3-173">當使用者登入電腦時。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-173">When a user logs on to their computer.</span></span>

-   <span data-ttu-id="3f8e3-174">當使用者解除鎖定電腦時。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-174">When a user unlocks their computer.</span></span>

-   <span data-ttu-id="3f8e3-175">在已安裝 UE-V 的遠端桌面電腦建立連線時。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-175">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

<span data-ttu-id="3f8e3-176">如果 UE-V 是安裝在電腦 A 和電腦 B 上，且應用程式所需的設定是在電腦 A 上，那麼電腦 A 必須先開啟並關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-176">If UE-V is installed on computer A and computer B, and the desired settings for the application are on computer A, then computer A must open and close the application first.</span></span> <span data-ttu-id="3f8e3-177">如果應用程式先于電腦 B 開啟和關閉，則電腦 A 上的應用程式設定將會設定為與電腦 B 上的應用程式設定相同。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-177">If an application is opened and closed on computer B first, then the application settings on computer A will be configured to be the same as the application settings on computer B.</span></span>

<span data-ttu-id="3f8e3-178">此案例也適用于 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-178">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="3f8e3-179">如果電腦 B 上的 Windows 設定應該與電腦 A 上的 Windows 設定相同，則使用者必須先登入和登出電腦 A。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-179">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should logon and logoff computer A first.</span></span>

<span data-ttu-id="3f8e3-180">如果以錯誤的順序套用所需的使用者設定，就可以在重寫設定的電腦上，針對特定的應用程式或 Windows 設定執行還原作業來復原這些設定。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-180">If the desired user settings are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="3f8e3-181">如需詳細資訊，請參閱[還原與 ue-v 1.0 同步處理的應用程式和 Windows 設定](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-181">For more information, see [Restoring Application and Windows Settings Synchronized with UE-V 1.0](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md).</span></span>

## <span data-ttu-id="3f8e3-182">自訂 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="3f8e3-182">Custom UE-V settings location templates</span></span>


<span data-ttu-id="3f8e3-183">您可以使用 UE-V 發生器來建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-183">You can create custom settings location templates by using the UE-V Generator.</span></span> <span data-ttu-id="3f8e3-184">在測試環境中建立並測試自訂設定位置範本之後，您可以將設定位置範本部署到企業中的電腦。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-184">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span> <span data-ttu-id="3f8e3-185">自訂設定位置範本必須使用現有的部署基礎結構（例如企業軟體發佈（ESD）方法）及喜好設定，或設定 UE-V 設定範本目錄來部署。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-185">Custom settings location templates must be deployed with an existing deployment infrastructure, such as enterprise software distribution (ESD) method, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="3f8e3-186">使用 [ESD] 或 [群組原則] 部署的範本，必須使用 UE-V WMI 或 PowerShell 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-186">Templates that are deployed with ESD or Group Policy must be registered by using UE-V WMI or PowerShell.</span></span> <span data-ttu-id="3f8e3-187">如需自訂設定位置範本的詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-187">For more information about custom settings location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

<span data-ttu-id="3f8e3-188">如需有關企業相關應用程式是否應進行同步處理的指導方針，請參閱[評估 ue-v 1.0 的商務用行應用程式的檢查清單](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8e3-188">For guidance on whether a line-of-business application should be synchronized, see [Checklist for Evaluating Line-of-Business Applications for UE-V 1.0](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md).</span></span>

## <span data-ttu-id="3f8e3-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="3f8e3-189">Related topics</span></span>


[<span data-ttu-id="3f8e3-190">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="3f8e3-190">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="3f8e3-191">規劃 UE-V 1.0 的自訂範本部署</span><span class="sxs-lookup"><span data-stu-id="3f8e3-191">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="3f8e3-192">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="3f8e3-192">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

 

 





