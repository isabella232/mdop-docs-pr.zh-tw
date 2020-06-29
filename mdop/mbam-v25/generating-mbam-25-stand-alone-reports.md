---
title: 產生 MBAM 2.5 獨立報告
description: 產生 MBAM 2.5 獨立報告
author: dansimp
ms.assetid: 0ec623ff-5155-4906-aef2-20cdc0f84667
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: e1c6b33de26cce5d9ad8d20461dbe0ea0f138c78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809765"
---
# <span data-ttu-id="b5ad0-103">產生 MBAM 2.5 獨立報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-103">Generating MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="b5ad0-104">當您將 Microsoft BitLocker 管理和監視（MBAM）設定為獨立拓朴時，您可以產生報告來監視 BitLocker 磁片磁碟機加密的使用方式及合規性。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-104">When you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate reports to monitor BitLocker drive encryption usage and compliance.</span></span> <span data-ttu-id="b5ad0-105">本主題包含下列程式：</span><span class="sxs-lookup"><span data-stu-id="b5ad0-105">This topic contains the following procedures:</span></span>

-   [<span data-ttu-id="b5ad0-106">開啟 [管理及監視] 網站</span><span class="sxs-lookup"><span data-stu-id="b5ad0-106">To open the Administration and Monitoring Website</span></span>](#bkmk-openadmin)

-   [<span data-ttu-id="b5ad0-107">產生企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-107">To generate an Enterprise Compliance Report</span></span>](#bkmk-enterprise)

-   [<span data-ttu-id="b5ad0-108">產生電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-108">To generate a Computer Compliance Report</span></span>](#bkmk-computercomp)

-   [<span data-ttu-id="b5ad0-109">產生復原金鑰審核報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-109">To generate a Recovery Key Audit Report</span></span>](#bkmk-recoverykey)

<span data-ttu-id="b5ad0-110">如需獨立報表的說明，請參閱[瞭解 MBAM 2.5 獨立的報表](understanding-mbam-25-stand-alone-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-110">For descriptions of the Stand-alone reports, see [Understanding MBAM 2.5 Stand-alone Reports](understanding-mbam-25-stand-alone-reports.md).</span></span>

<span data-ttu-id="b5ad0-111">**記事** 若要執行報表，您必須是您在 Active Directory 網域服務中設定之**MBAM Report Users**群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-111">**Note** To run the reports, you must be a member of the **MBAM Report Users** group, which you configure in Active Directory Domain Services.</span></span> <span data-ttu-id="b5ad0-112">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-112">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

 

<a href="" id="bkmk-openadmin"></a>**<span data-ttu-id="b5ad0-113">開啟 [管理及監視] 網站</span><span class="sxs-lookup"><span data-stu-id="b5ad0-113">To open the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="b5ad0-114">開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-114">Open a web browser and navigate to the Administration and Monitoring Website.</span></span> <span data-ttu-id="b5ad0-115">[管理] 和 [監視] 網站的預設 URL 為：</span><span class="sxs-lookup"><span data-stu-id="b5ad0-115">The default URL for the Administration and Monitoring Website is:</span></span>

    *<span data-ttu-id="b5ad0-116">HTTP （s）// &lt; MBAMAdministrationServerName &gt; ： &lt; 埠 &gt; /Helpdesk</span><span class="sxs-lookup"><span data-stu-id="b5ad0-116">http(s)://&lt;MBAMAdministrationServerName&gt;:&lt;port&gt;/Helpdesk</span></span>*

2.  <span data-ttu-id="b5ad0-117">在左窗格中，按一下 [**報表**]。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-117">In the left pane, click **Reports**.</span></span> <span data-ttu-id="b5ad0-118">從上方的功能表列中，選取您要執行的報表。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-118">From the top menu bar, select the report you want to run.</span></span>

    <span data-ttu-id="b5ad0-119">MBAM 用戶端資料會保留在合規性和審核資料庫中，以便在電腦遺失或被盜時進行歷史參考。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-119">MBAM client data is retained in the Compliance and Audit Database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="b5ad0-120">在執行企業報告時，建議您使用適當的開始和結束日期，將報告的時間範圍從1到兩周，以提高報告資料的精確度。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-120">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="b5ad0-121">產生報告之後，您可以將結果儲存為不同的格式，例如 HTML、Microsoft Word 及 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-121">After you generate a report, you can save the results in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="b5ad0-122">**記事** 設定 SQL Server Reporting Services （SSRS），以使用安全通訊端層（SSL），然後再設定管理和監視網站。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-122">**Note** Configure SQL Server Reporting Services (SSRS) to use Secure Sockets Layer (SSL) before configuring the Administration and Monitoring Website.</span></span> <span data-ttu-id="b5ad0-123">如果由於任何原因而未將 SSRS 設定為使用 SSL，當您設定管理和監控網站時，報告的 URL 就會設定為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-123">If, for any reason, SSRS is not configured to use SSL, the URL for the Reports will be set to HTTP instead of to HTTPS when you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="b5ad0-124">如果您接著移至 [管理及監視] 網站並選取報表，則會顯示下列訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-124">If you then go to the Administration and Monitoring Website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="b5ad0-125">若要顯示報表，請按一下 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-125">To show the report, click **Show All Content**.</span></span>

     

<a href="" id="bkmk-enterprise"></a>**<span data-ttu-id="b5ad0-126">產生企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-126">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="b5ad0-127">從 [管理和監控] 網站，從左側流覽窗格中選取 [**報表**] 節點，選取 [**企業合規性報告**]，然後選取您要使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-127">From the Administration and Monitoring Website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="b5ad0-128">企業合規性報告可用的篩選器包括：</span><span class="sxs-lookup"><span data-stu-id="b5ad0-128">The available filters for the Enterprise Compliance Report are:</span></span>

    -   <span data-ttu-id="b5ad0-129">**合規性狀態**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-129">**Compliance Status**.</span></span> <span data-ttu-id="b5ad0-130">使用此篩選指定報表的合規性狀態類型（例如，合規或不相容）。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-130">Use this filter to specify the compliance status types of the report (for example, Compliant or Noncompliant).</span></span>

    -   <span data-ttu-id="b5ad0-131">**錯誤狀態**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-131">**Error State**.</span></span> <span data-ttu-id="b5ad0-132">使用這個篩選指定報告的錯誤狀態類型（例如，沒有錯誤或錯誤）。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-132">Use this filter to specify the error state types of the report (for example, No Error or Error).</span></span>

2.  <span data-ttu-id="b5ad0-133">按一下 [**查看報表**] 以顯示選取的報表。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-133">Click **View Report** to display the selected report.</span></span>

3.  <span data-ttu-id="b5ad0-134">選取電腦名稱稱，以在電腦合規性報告中查看電腦的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-134">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="b5ad0-135">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-135">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

<a href="" id="bkmk-computercomp"></a>**<span data-ttu-id="b5ad0-136">產生電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-136">To generate a Computer Compliance Report</span></span>**

1.  <span data-ttu-id="b5ad0-137">從 [管理和監控] 網站，從左側流覽窗格中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-137">From the Administration and Monitoring Website, select the **Report** node from the left navigation pane, and then select **Computer Compliance Report**.</span></span> <span data-ttu-id="b5ad0-138">使用電腦相容性報告來搜尋**使用者名稱**或**電腦名稱稱**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-138">Use the Computer Compliance Report to search for **User name** or **Computer name**.</span></span>

2.  <span data-ttu-id="b5ad0-139">按一下 [**查看報表**]，以查看電腦合規性報告。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-139">Click **View Report** to view the Computer Compliance Report.</span></span>

3.  <span data-ttu-id="b5ad0-140">選取電腦名稱稱，以在電腦合規性報告中顯示電腦的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-140">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="b5ad0-141">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-141">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="b5ad0-142">**記事** 如果電腦符合或超過 MBAM 群組原則設定的需求，則會認為 MBAM 用戶端電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-142">**Note** An MBAM client computer is considered compliant if the computer matches or exceeds the requirements of the MBAM Group Policy settings.</span></span>

<a href="" id="bkmk-recoverykey"></a>**<span data-ttu-id="b5ad0-143">產生復原金鑰審核報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-143">To generate a Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="b5ad0-144">從 [管理和監控] 網站，選取左側流覽窗格中的 [**報表**] 節點，然後選取 [復原**審核報告**]。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-144">From the Administration and Monitoring Website, select the **Report** node in the left navigation pane, and then select **Recovery Audit Report**.</span></span> <span data-ttu-id="b5ad0-145">選取您的 [復原金鑰] 審核報告篩選器。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-145">Select the filters for your Recovery Key Audit Report.</span></span> <span data-ttu-id="b5ad0-146">復原金鑰審核的可用篩選器如下所示：</span><span class="sxs-lookup"><span data-stu-id="b5ad0-146">The available filters for recovery key audits are as follows:</span></span>

    -   <span data-ttu-id="b5ad0-147">**支援人員的使用者**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-147">**Helpdesk User**.</span></span> <span data-ttu-id="b5ad0-148">此篩選可讓使用者指定申請者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-148">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="b5ad0-149">申請者是技術支援人員中代表使用者存取金鑰的人員。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-149">The requester is the person in the Help Desk who accessed the key on behalf of an end user.</span></span>

    -   <span data-ttu-id="b5ad0-150">**使用者**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-150">**End User**.</span></span> <span data-ttu-id="b5ad0-151">此篩選可讓使用者指定 requestee 的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-151">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="b5ad0-152">Requestee 是呼叫技術支援人員以取得復原金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-152">The requestee is the end user who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="b5ad0-153">**要求結果**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-153">**Request Result**.</span></span> <span data-ttu-id="b5ad0-154">此篩選可讓使用者指定要作為報表基礎的要求結果類型（例如，成功或失敗）。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-154">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="b5ad0-155">例如，使用者可能會想要查看失敗的按鍵存取嘗試。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-155">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="b5ad0-156">**金鑰類型**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-156">**Key Type**.</span></span> <span data-ttu-id="b5ad0-157">此篩選可讓使用者指定要作為報告基礎的金鑰類型（例如，復原金鑰密碼或 TPM 密碼雜湊）。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-157">This filter enables users to specify the key type (for example, Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="b5ad0-158">**開始日期**。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-158">**Start Date**.</span></span> <span data-ttu-id="b5ad0-159">這個篩選器可用來定義使用者想要報告的日期範圍的開始日期部分。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-159">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="b5ad0-160">[**結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-160">**End Date**.</span></span> <span data-ttu-id="b5ad0-161">這個篩選器可用來定義使用者要報告的日期範圍的結束日期部分。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-161">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="b5ad0-162">按一下 [**查看報表**]，即可查看報表。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-162">Click **View Report** to view the report.</span></span>



## <span data-ttu-id="b5ad0-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="b5ad0-163">Related topics</span></span>


[<span data-ttu-id="b5ad0-164">使用 MBAM 2.5 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="b5ad0-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="b5ad0-165">了解 MBAM 2.5 獨立報告</span><span class="sxs-lookup"><span data-stu-id="b5ad0-165">Understanding MBAM 2.5 Stand-alone Reports</span></span>](understanding-mbam-25-stand-alone-reports.md)

 

## <span data-ttu-id="b5ad0-166">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="b5ad0-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b5ad0-167">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b5ad0-168">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="b5ad0-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





