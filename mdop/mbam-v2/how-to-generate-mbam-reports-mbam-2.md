---
title: 如何產生 MBAM 報告
description: 如何產生 MBAM 報告
author: dansimp
ms.assetid: 083550cb-8c3f-49b3-a30e-97d85374d2f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ccdc1a2cd69d8cc2e2c2823827f5ea43ad867a78
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810347"
---
# <span data-ttu-id="64473-103">如何產生 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="64473-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="64473-104">當您使用獨立拓朴安裝 Microsoft BitLocker 管理和監控（MBAM）時，您可以產生不同的報告，以監控 BitLocker 加密的使用方式與合規性。</span><span class="sxs-lookup"><span data-stu-id="64473-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM) with the Stand-alone topology, you can generate different reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="64473-105">本主題中的程式說明如何開啟管理和監控網站，以及在企業合規性、個別電腦及金鑰復原活動中產生 Microsoft BitLocker 管理和監控報告所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="64473-105">The procedures in this topic describe how to open the Administration and Monitoring website and the steps that are needed to generate Microsoft BitLocker Administration and Monitoring reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="64473-106">如需協助瞭解 MBAM 報告的詳細資訊，請參閱[瞭解 MBAM 報告](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="64473-106">For detailed information to help understand MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

<span data-ttu-id="64473-107">**記事** 若要執行報表，您必須是電腦上的**報表使用者角色**的成員，包括系統管理和監控伺服器功能、合規性和審核資料庫，以及合規性和審核報告的安裝。</span><span class="sxs-lookup"><span data-stu-id="64473-107">**Note** To run the reports, you must be a member of the **Report Users Role** on the computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

 

**<span data-ttu-id="64473-108">開啟 [管理及監視] 網站</span><span class="sxs-lookup"><span data-stu-id="64473-108">To open the Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="64473-109">開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="64473-109">Open a web browser and navigate to the Administration and Monitoring website.</span></span> <span data-ttu-id="64473-110">[管理] 和 [監視] 網站的預設 URL 是\*HTTP:// &lt; computername &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="64473-110">The default URL for the Administration and Monitoring website is *http://&lt;computername&gt;*.</span></span>

    <span data-ttu-id="64473-111">**記事** 如果 theAdministration 和監控網站是在80以外的埠上安裝，您必須在 URL 中指定埠（例如， \*HTTP:// &lt; computername &gt; ： &lt; port &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="64473-111">**Note** If theAdministration and Monitoring website was installed on a port other than 80, you have to specify the port in the URL (for example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="64473-112">如果您在安裝期間為 theAdministration 和監控網站指定了主機名稱，URL 就是*HTTP:// &lt; 主機 &gt; 名*。</span><span class="sxs-lookup"><span data-stu-id="64473-112">If you specified a host name for theAdministration and Monitoring website during the installation, the URL is *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="64473-113">在左窗格中，按一下 [**報表**]，然後從頂端功能表列選取您要執行的報表。</span><span class="sxs-lookup"><span data-stu-id="64473-113">In the left pane, click **Reports** and then select the report you want to run from the top menu bar.</span></span>

    <span data-ttu-id="64473-114">當電腦遺失或被盜時，會在合規性資料庫中保留歷史 MBAM 用戶端資料，以進行歷史參考。</span><span class="sxs-lookup"><span data-stu-id="64473-114">Historical MBAM client data is retained in the compliance database for historical reference in case a computer is lost or stolen.</span></span> <span data-ttu-id="64473-115">在執行企業報告時，建議您使用適當的開始和結束日期，將報告的時間範圍從1到兩周，以提高報告資料的精確度。</span><span class="sxs-lookup"><span data-stu-id="64473-115">When running enterprise reports, we recommend that you use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase reporting data accuracy.</span></span>

    <span data-ttu-id="64473-116">**記事** 如果未將 SSRS 設定為使用安全通訊端層，當您安裝 MBAM 伺服器時，報告的 URL 會設定為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="64473-116">**Note** If SSRS was not configured to use Secure Socket Layer, the URL for the reports will be set to HTTP instead of to HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="64473-117">如果您接著移至 [技術支援中心] 入口網站，並選取報表，則會顯示下列訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="64473-117">If you then go to the Help Desk portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span> <span data-ttu-id="64473-118">若要顯示報表，請按一下 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="64473-118">To show the report, click **Show All Content**.</span></span>

     

**<span data-ttu-id="64473-119">產生企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="64473-119">To generate an Enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="64473-120">從 [管理和監控] 網站，從左側流覽窗格中選取 [**報表**] 節點，選取 [**企業合規性報告**]，然後選取您要使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="64473-120">From the Administration and Monitoring website, select the **Reports** node from the left navigation pane, select **Enterprise Compliance Report**, and select the filters that you want to use.</span></span> <span data-ttu-id="64473-121">企業合規性報告的可用篩選器如下所示：</span><span class="sxs-lookup"><span data-stu-id="64473-121">The available filters for the Enterprise Compliance Report are the following:</span></span>

    -   <span data-ttu-id="64473-122">**合規性狀態**。</span><span class="sxs-lookup"><span data-stu-id="64473-122">**Compliance Status**.</span></span> <span data-ttu-id="64473-123">使用此篩選指定報表的合規性狀態類型（例如，合規性或不相容）。</span><span class="sxs-lookup"><span data-stu-id="64473-123">Use this filter to specify the compliance status types (for example, Compliant, or Noncompliant) of the report.</span></span>

    -   <span data-ttu-id="64473-124">**錯誤狀態**。</span><span class="sxs-lookup"><span data-stu-id="64473-124">**Error State**.</span></span> <span data-ttu-id="64473-125">使用此篩選指定報表的錯誤狀態類型（例如，沒有錯誤或錯誤）。</span><span class="sxs-lookup"><span data-stu-id="64473-125">Use this filter to specify the error state types (for example, No Error, or Error) of the report.</span></span>

2.  <span data-ttu-id="64473-126">按一下 [**查看報表**] 以顯示選取的報表。</span><span class="sxs-lookup"><span data-stu-id="64473-126">Click **View Report** to display the selected report.</span></span>

    <span data-ttu-id="64473-127">您可以使用不同的格式（例如 HTML、Microsoft Word 及 Microsoft Excel）來儲存結果。</span><span class="sxs-lookup"><span data-stu-id="64473-127">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="64473-128">**記事** 企業合規性報告是由 SQL 作業產生，每6小時執行一次。</span><span class="sxs-lookup"><span data-stu-id="64473-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="64473-129">因此，當您第一次查看報表時，您可能會發現某些資料遺失了。</span><span class="sxs-lookup"><span data-stu-id="64473-129">Therefore, the first time you view the report, you may find that some data is missing.</span></span> <span data-ttu-id="64473-130">您可以使用 SQL Management Studio 手動產生更新的報表資料。</span><span class="sxs-lookup"><span data-stu-id="64473-130">You can generate updated report data manually by using SQL Management Studio.</span></span> <span data-ttu-id="64473-131">在 [**物件資源管理器**] 視窗中，展開 **[SQL Server 代理程式**]，然後展開 [**作業**]，以滑鼠右鍵按一下**CreateCache**工作，然後選取 [**在步驟中開始工作 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="64473-131">From the **Object Explorer** window, expand **SQL Server Agent**, expand **Jobs**, right-click the **CreateCache** job, and select **Start Job at Step….**</span></span>

     

3.  <span data-ttu-id="64473-132">選取電腦名稱稱，以在電腦合規性報告中查看電腦的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="64473-132">Select a computer name to view information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="64473-133">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="64473-133">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="64473-134">產生電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="64473-134">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="64473-135">在 [管理及監視] 網站中，從左側流覽窗格中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。</span><span class="sxs-lookup"><span data-stu-id="64473-135">In the Administration and Monitoring website, select the **Report** node from the left navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="64473-136">使用電腦相容性報告來搜尋**使用者名稱**或**電腦名稱稱**。</span><span class="sxs-lookup"><span data-stu-id="64473-136">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="64473-137">按一下 [**查看報表**] 來查看電腦報告。</span><span class="sxs-lookup"><span data-stu-id="64473-137">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="64473-138">您可以使用不同的格式（例如 HTML、Microsoft Word 及 Microsoft Excel）來儲存結果。</span><span class="sxs-lookup"><span data-stu-id="64473-138">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="64473-139">選取電腦名稱稱，以在電腦合規性報告中顯示電腦的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="64473-139">Select a computer name to display more information about the computer in the Computer Compliance Report.</span></span>

4.  <span data-ttu-id="64473-140">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="64473-140">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="64473-141">**記事** 如果電腦符合 MBAM 原則設定的需求，則會認為 MBAM 用戶端電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="64473-141">**Note** An MBAM client computer is considered compliant if the computer matches the requirements of the MBAM policy settings.</span></span>

     

**<span data-ttu-id="64473-142">產生修復金鑰審核報告</span><span class="sxs-lookup"><span data-stu-id="64473-142">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="64473-143">從 [管理和監控] 網站，選取左側流覽窗格中的 [**報表**] 節點，然後選取 [復原**審核報告**]。</span><span class="sxs-lookup"><span data-stu-id="64473-143">From the Administration and Monitoring website, select the **Report** node in the left navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="64473-144">選取您的 [復原金鑰] 審核報告篩選器。</span><span class="sxs-lookup"><span data-stu-id="64473-144">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="64473-145">復原金鑰審核的可用篩選器如下所示：</span><span class="sxs-lookup"><span data-stu-id="64473-145">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="64473-146">**請求**程式。</span><span class="sxs-lookup"><span data-stu-id="64473-146">**Requestor**.</span></span> <span data-ttu-id="64473-147">此篩選可讓使用者指定申請者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="64473-147">This filter enables users to specify the user name of the requester.</span></span> <span data-ttu-id="64473-148">申請者是技術支援人員中代表使用者存取金鑰的人員。</span><span class="sxs-lookup"><span data-stu-id="64473-148">The requester is the person in the Help Desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="64473-149">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="64473-149">**Requestee**.</span></span> <span data-ttu-id="64473-150">此篩選可讓使用者指定 requestee 的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="64473-150">This filter enables users to specify the user name of the requestee.</span></span> <span data-ttu-id="64473-151">Requestee 是呼叫問訊台以取得復原金鑰的人員。</span><span class="sxs-lookup"><span data-stu-id="64473-151">The requestee is the person who called the Help Desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="64473-152">**要求結果**。</span><span class="sxs-lookup"><span data-stu-id="64473-152">**Request Result**.</span></span> <span data-ttu-id="64473-153">此篩選可讓使用者指定要作為報表基礎的要求結果類型（例如，成功或失敗）。</span><span class="sxs-lookup"><span data-stu-id="64473-153">This filter enables users to specify the request result types (for example, Success or Failed) that they want to base the report on.</span></span> <span data-ttu-id="64473-154">例如，使用者可能會想要查看失敗的按鍵存取嘗試。</span><span class="sxs-lookup"><span data-stu-id="64473-154">For example, users may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="64473-155">**金鑰類型**。</span><span class="sxs-lookup"><span data-stu-id="64473-155">**Key Type**.</span></span> <span data-ttu-id="64473-156">此篩選可讓使用者指定要作為報告基礎的金鑰類型（例如，復原金鑰密碼或 TPM 密碼雜湊）。</span><span class="sxs-lookup"><span data-stu-id="64473-156">This filter enables users to specify the Key Type (for example: Recovery Key Password or TPM Password Hash) that they want to base the report on.</span></span>

    -   <span data-ttu-id="64473-157">**開始日期**。</span><span class="sxs-lookup"><span data-stu-id="64473-157">**Start Date**.</span></span> <span data-ttu-id="64473-158">這個篩選器可用來定義使用者想要報告的日期範圍的開始日期部分。</span><span class="sxs-lookup"><span data-stu-id="64473-158">This filter is used to define the Start Date part of the date range that the user wants to report on.</span></span>

    -   <span data-ttu-id="64473-159">[**結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="64473-159">**End Date**.</span></span> <span data-ttu-id="64473-160">這個篩選器可用來定義使用者要報告的日期範圍的結束日期部分。</span><span class="sxs-lookup"><span data-stu-id="64473-160">This filter is used to define the End Date part of the date range that the users want to report on.</span></span>

2.  <span data-ttu-id="64473-161">按一下 [**查看報表**]，即可查看報表。</span><span class="sxs-lookup"><span data-stu-id="64473-161">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="64473-162">您可以使用不同的格式（例如 HTML、Microsoft Word 及 Microsoft Excel）來儲存結果。</span><span class="sxs-lookup"><span data-stu-id="64473-162">Results can be saved in different formats, such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="64473-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="64473-163">Related topics</span></span>


[<span data-ttu-id="64473-164">使用 MBAM 2.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="64473-164">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





