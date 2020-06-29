---
title: App-V 4.6 SP1 版本資訊
description: App-V 4.6 SP1 版本資訊
author: dansimp
ms.assetid: aeb6784a-864a-4f4e-976b-40c34dcfd8d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7081aaf4a04d52bf288d7a76b4a488e2b200c3d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802377"
---
# <span data-ttu-id="a3015-103">App-V 4.6 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="a3015-103">App-V 4.6 SP1 Release Notes</span></span>


<span data-ttu-id="a3015-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="a3015-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="a3015-105">**重要** 安裝 Microsoft Application Virtualization （App-v）管理系統之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="a3015-105">**Important** Read these Release Notes thoroughly before you install the Microsoft Application Virtualization (App-V) Management System.</span></span> <span data-ttu-id="a3015-106">這些版本資訊包含的資訊可協助您成功安裝應用程式虛擬化（App-v） 4.6 SP1。</span><span class="sxs-lookup"><span data-stu-id="a3015-106">These Release Notes contain information that helps you successfully install Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="a3015-107">此檔包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a3015-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="a3015-108">如果這些版本資訊與其他 App-v 檔之間有差異，最新變更應視為權威性。</span><span class="sxs-lookup"><span data-stu-id="a3015-108">If there is a difference between these Release Notes and other App-V documentation, the latest change should be considered authoritative.</span></span>

 

## <span data-ttu-id="a3015-109">防範安全性漏洞與病毒</span><span class="sxs-lookup"><span data-stu-id="a3015-109">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="a3015-110">若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="a3015-110">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="a3015-111">如需詳細資訊，請參閱[Microsoft 安全性網站](https://go.microsoft.com/fwlink/?LinkId=3482)（ https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="a3015-111">For more information, see the [Microsoft Security website](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="a3015-112">應用程式虛擬化 4.6 SP1 的已知問題</span><span class="sxs-lookup"><span data-stu-id="a3015-112">Known Issues with Application Virtualization4.6 SP1</span></span>


<span data-ttu-id="a3015-113">本節提供關於 Microsoft 應用程式虛擬化（App-v） 4.6 SP1 問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="a3015-113">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.6 SP1.</span></span> <span data-ttu-id="a3015-114">這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。</span><span class="sxs-lookup"><span data-stu-id="a3015-114">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="a3015-115">如果可能的話，這些問題將會在稍後的版本中解決。</span><span class="sxs-lookup"><span data-stu-id="a3015-115">When it is possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="a3015-116">如果 SPRT 的路徑不是以正斜線（/）結尾，就會遺失</span><span class="sxs-lookup"><span data-stu-id="a3015-116">Path from SPRT is lost if it does not end in forward slash ( / )</span></span>

<span data-ttu-id="a3015-117">當專案範本中 HREF 中的路徑不是以正斜杠（）結尾時 **/** ，產生的 HREF 不包含路徑。</span><span class="sxs-lookup"><span data-stu-id="a3015-117">When the path in an HREF in a project template does not end with a forward slash (**/**), the generated HREF does not include the path.</span></span> <span data-ttu-id="a3015-118">當使用者手動處理**sprt**檔案時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="a3015-118">This occurs when the user manually manipulates the **.sprt** file.</span></span> <span data-ttu-id="a3015-119">如果您使用 sequencer，它會永遠在路徑後面加上斜線（ **/** ）。</span><span class="sxs-lookup"><span data-stu-id="a3015-119">If you use the sequencer it always adds the forward slash (**/**) after the path.</span></span>

<span data-ttu-id="a3015-120">因應措施請確認 HREF 有結尾的正斜杠（ **/** ）。</span><span class="sxs-lookup"><span data-stu-id="a3015-120">WORKAROUND Make sure that the HREF has a trailing forward slash (**/**).</span></span>

### <span data-ttu-id="a3015-121">使用者資料夾名稱不會對應到套件名稱</span><span class="sxs-lookup"><span data-stu-id="a3015-121">User folder name do not correspond to the package name</span></span>

<span data-ttu-id="a3015-122">包含 user 和 global installer.pkg 檔案的資料夾不會再包含套件名稱。</span><span class="sxs-lookup"><span data-stu-id="a3015-122">Folders that contain user and global .pkg files no longer include the package name.</span></span> <span data-ttu-id="a3015-123">之前，App-v 用戶端會使用 [套件根資料夾8.3 簡稱] 作為資料夾名稱的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3015-123">Previously, the App-V client used to use the package root folder 8.3 short name as part of the folder name.</span></span> <span data-ttu-id="a3015-124">這可讓您輕鬆識別它。</span><span class="sxs-lookup"><span data-stu-id="a3015-124">This lets you easily identify it.</span></span> <span data-ttu-id="a3015-125">當您使用 App-v 4.6 SP1 排序器時，套件根資料夾8.3 的短名稱現在就是隨機字串。</span><span class="sxs-lookup"><span data-stu-id="a3015-125">When you use the App-V 4.6 SP1 sequencer, the package root folder 8.3 short names are now random strings.</span></span> <span data-ttu-id="a3015-126">這會讓您難以在執行 App-v 用戶端的電腦上，找出包含套件**installer.pkg**檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3015-126">This makes it difficult to identify the folders that contain the package’s **.pkg** files on the computer that is running the App-V client.</span></span>

<span data-ttu-id="a3015-127">因應措施請使用下列其中一種方法，更輕鬆地辨識這些套件資料夾：</span><span class="sxs-lookup"><span data-stu-id="a3015-127">WORKAROUND Use one of the following methods to more easily identify these package folders:</span></span>

1.  <span data-ttu-id="a3015-128">當您使用排序器建立套件時，請為主要應用程式資料夾指定遵循8.3 命名慣例的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="a3015-128">When you create the package by using the Sequencer, specify a folder name that follows the 8.3 naming convention for the primary application folder.</span></span> <span data-ttu-id="a3015-129">然後，此名稱就會用來做為使用者資料夾名稱的一部分，就像在 App-v 4.6 中的情況。</span><span class="sxs-lookup"><span data-stu-id="a3015-129">This name will then be used as part of the user folder name as was the case in App-V 4.6.</span></span>

2.  <span data-ttu-id="a3015-130">Sprj 檔案現在包含一個標記，以顯示用作使用者資料夾名稱開頭的字串。</span><span class="sxs-lookup"><span data-stu-id="a3015-130">The .sprj file now contains a tag that displays the string that is used as the beginning of the user folder name.</span></span> <span data-ttu-id="a3015-131">您可以使用**PACKAGEROOTFOLDER**元素的**SHORTNAME**元素來判斷名稱。</span><span class="sxs-lookup"><span data-stu-id="a3015-131">You can use the **SHORTNAME** element of the **PACKAGEROOTFOLDER** element to determine the name.</span></span>

### <span data-ttu-id="a3015-132">在超過64個處理器的電腦上執行 App-v 4.6 SP1</span><span class="sxs-lookup"><span data-stu-id="a3015-132">Running App-V 4.6 SP1 on computers that have more than 64 processors</span></span>

<span data-ttu-id="a3015-133">當您在已安裝超過64個處理器的電腦上執行 App-v 4.6 SP1 時，App-v 用戶端會失敗。</span><span class="sxs-lookup"><span data-stu-id="a3015-133">When you run App-V 4.6 SP1 on computers that have more than 64 processors installed, the App-V client fails.</span></span>

<span data-ttu-id="a3015-134">因應措施無。</span><span class="sxs-lookup"><span data-stu-id="a3015-134">WORKAROUND None.</span></span> <span data-ttu-id="a3015-135">不支援此設定。</span><span class="sxs-lookup"><span data-stu-id="a3015-135">This configuration is not supported.</span></span> <span data-ttu-id="a3015-136">您必須執行 App-v 4.6 SP1on 少於64個處理器的電腦。</span><span class="sxs-lookup"><span data-stu-id="a3015-136">You must run App-V 4.6 SP1on computers that have fewer than 64 processors.</span></span>

### <span data-ttu-id="a3015-137">未在使用 Microsoft Update 的所有地區設定中提供 Application Virtualization 4.6 SP1 更新</span><span class="sxs-lookup"><span data-stu-id="a3015-137">Application Virtualization 4.6 SP1 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="a3015-138">當您使用 Microsoft Update 時，App-v 4.6 SP1 的更新不適用於下列語言地區設定：</span><span class="sxs-lookup"><span data-stu-id="a3015-138">When you use Microsoft Update, the update for App-V 4.6 SP1 is not available for the following language locales:</span></span>

-   <span data-ttu-id="a3015-139">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="a3015-139">Kazakh</span></span>

-   <span data-ttu-id="a3015-140">印度文</span><span class="sxs-lookup"><span data-stu-id="a3015-140">Hindi</span></span>

-   <span data-ttu-id="a3015-141">塞爾維亞文-西瑞爾文</span><span class="sxs-lookup"><span data-stu-id="a3015-141">Serbian-Cyrillic</span></span>

<span data-ttu-id="a3015-142">因應措施如果您使用的是 Microsoft Windows Server Update Services （WSUS），請使用英文版的更新，或從 Microsoft 更新目錄下載更新。</span><span class="sxs-lookup"><span data-stu-id="a3015-142">WORKAROUND If you are using Microsoft Windows Server Update Services (WSUS) use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

### <span data-ttu-id="a3015-143">展開父套件後，您無法使用並列元件順序排列外掛程式</span><span class="sxs-lookup"><span data-stu-id="a3015-143">After expanding the parent package, you cannot sequence a plug-in with side by side components</span></span>

<span data-ttu-id="a3015-144">當您使用 [**工具**] 展開父項套件時，會將 [  /  **封裝到本機系統**] 的 [應用程式-V] 排序器視窗中的 [封裝到本機系統]，而且您會傳回安裝錯誤。</span><span class="sxs-lookup"><span data-stu-id="a3015-144">When you expand a parent package by using **Tools** / **Expand Package to Local System** in the App-V Sequencer console and you sequence a plug-in with side by side components, an installation error is returned.</span></span> <span data-ttu-id="a3015-145">例如：</span><span class="sxs-lookup"><span data-stu-id="a3015-145">For example:</span></span>

-   **<span data-ttu-id="a3015-146">HRESULT 0x80073712</span><span class="sxs-lookup"><span data-stu-id="a3015-146">HRESULT 0x80073712</span></span>**

<span data-ttu-id="a3015-147">當 sequencer 將並列元件寫入到註冊表，但不清除下列登錄機碼的值時，就會造成這種情況：</span><span class="sxs-lookup"><span data-stu-id="a3015-147">This is caused when the sequencer writes the side-by-side component to the registry but does not clear the value for the following registry key:</span></span>

<span data-ttu-id="a3015-148">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="a3015-148">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="a3015-149">解決方法在執行排序器的電腦上展開上層套件後，您必須刪除下列登錄機碼的值：</span><span class="sxs-lookup"><span data-stu-id="a3015-149">WORKAROUND After expanding the parent package on the computer that is running the sequencer, you have to delete the value for the following registry key:</span></span>

<span data-ttu-id="a3015-150">HKEY \ _LOCAL \ _MACHINE \\COMPONENTS\\StoreDirty</span><span class="sxs-lookup"><span data-stu-id="a3015-150">HKEY\_LOCAL\_MACHINE\\COMPONENTS\\StoreDirty</span></span>

<span data-ttu-id="a3015-151">刪除值後，請依序排列外掛程式。</span><span class="sxs-lookup"><span data-stu-id="a3015-151">After you have deleted the value, sequence the plug-in.</span></span>

### <span data-ttu-id="a3015-152">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="a3015-152">Release Notes Copyright Information</span></span>

<span data-ttu-id="a3015-153">本檔是以「原樣」提供。</span><span class="sxs-lookup"><span data-stu-id="a3015-153">This document is provided “as-is”.</span></span> <span data-ttu-id="a3015-154">此檔中所表示的資訊和視圖（例如 URL 和其他網際網路網站參考）可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="a3015-154">Information and views expressed in this document, such as URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="a3015-155">您會承擔使用它的風險。</span><span class="sxs-lookup"><span data-stu-id="a3015-155">You bear the risk of using it.</span></span>

<span data-ttu-id="a3015-156">本文中描述的一些範例只提供給說明，且是虛構的。</span><span class="sxs-lookup"><span data-stu-id="a3015-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="a3015-157">沒有任何實際的關聯或連線是有意或無意的。</span><span class="sxs-lookup"><span data-stu-id="a3015-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="a3015-158">本文件不為您提供對任何 Microsoft 產品中的任何智慧財產的法定權利。</span><span class="sxs-lookup"><span data-stu-id="a3015-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="a3015-159">您可以複製本文件供內部參照之用。</span><span class="sxs-lookup"><span data-stu-id="a3015-159">You may copy and use this document for your internal, reference purposes.</span></span> <span data-ttu-id="a3015-160">您可以針對內部、參考目的來修改這份檔。</span><span class="sxs-lookup"><span data-stu-id="a3015-160">You may modify this document for your internal, reference purposes.</span></span>



<span data-ttu-id="a3015-161">Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、Windows、Windows PowerShell、Windows Server 和 Windows Vista 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="a3015-161">Microsoft, Active Directory, ActiveSync, ActiveX, Excel, SQL Server, Windows, Windows PowerShell, Windows Server, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="a3015-162">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="a3015-162">All other trademarks are property of their respective owners.</span></span>

 

 





