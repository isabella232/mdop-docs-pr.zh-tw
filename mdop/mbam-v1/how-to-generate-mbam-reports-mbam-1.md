---
title: 如何產生 MBAM 報告
description: 如何產生 MBAM 報告
author: dansimp
ms.assetid: cdf4ae76-040c-447c-8736-c9e57068d221
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f0b5a4e984d7a609eab7204e67f46042992f586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810610"
---
# <span data-ttu-id="7cc29-103">如何產生 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="7cc29-103">How to Generate MBAM Reports</span></span>


<span data-ttu-id="7cc29-104">Microsoft BitLocker 管理和監控（MBAM）會產生各種報告，以監控 BitLocker 加密的使用及合規性。</span><span class="sxs-lookup"><span data-stu-id="7cc29-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker encryption usage and compliance.</span></span> <span data-ttu-id="7cc29-105">本主題說明如何開啟 MBAM 管理網站，以及如何在企業合規性、個別電腦、硬體相容性及金鑰復原活動中產生 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="7cc29-105">This topic describes how to open the MBAM administration website and how to generate MBAM reports on enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span> <span data-ttu-id="7cc29-106">如需有關 MBAM 報告的詳細資訊，請參閱[瞭解 MBAM 報告](understanding-mbam-reports-mbam-1.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc29-106">For more information about MBAM reports, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-1.md).</span></span>

<span data-ttu-id="7cc29-107">**記事** 若要執行報表，您必須是已安裝管理和監控伺服器功能、合規性和審核資料庫，以及合規性和審核報告的電腦上的**報表使用者**角色的成員。</span><span class="sxs-lookup"><span data-stu-id="7cc29-107">**Note** To run the reports, you must be a member of the **Report Users** role on the computers where you have installed the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports.</span></span>

 

**<span data-ttu-id="7cc29-108">開啟 MBAM 管理網站</span><span class="sxs-lookup"><span data-stu-id="7cc29-108">To open the MBAM Administration website</span></span>**

1.  <span data-ttu-id="7cc29-109">開啟網頁瀏覽器並流覽至 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="7cc29-109">Open a web browser and navigate to the MBAM website.</span></span> <span data-ttu-id="7cc29-110">網站的預設 URL 是 HTTP://Microsoft BitLocker 管理和監視伺服器的\* &lt; 電腦名稱稱 &gt; \* 。</span><span class="sxs-lookup"><span data-stu-id="7cc29-110">The default URL for the website is *http://&lt;computername&gt;* of the Microsoft BitLocker Administration and Monitoring server.</span></span>

    <span data-ttu-id="7cc29-111">**記事** 如果 MBAMadministration 網站是安裝在埠80以外的埠，您必須在 URL 中指定該埠號碼。</span><span class="sxs-lookup"><span data-stu-id="7cc29-111">**Note** If the MBAMadministration website was installed on a port other than port 80, you must specify that port number in the URL.</span></span> <span data-ttu-id="7cc29-112">例如， \*HTTP:// &lt; computername &gt; ： &lt; port &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="7cc29-112">For example, *http://&lt;computername&gt;:&lt;port&gt;*.</span></span> <span data-ttu-id="7cc29-113">如果您在安裝期間為 MBAMadministration 網站指定了主機名稱，URL 就會是\*HTTP:// &lt; 主機名稱 &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="7cc29-113">If you specified a Host Name for the MBAMadministration website during the installation, the URL would be *http://&lt;hostname&gt;*.</span></span>

     

2.  <span data-ttu-id="7cc29-114">在 [功能窗格] 中，按一下 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-114">In the navigation pane, click **Reports**.</span></span> <span data-ttu-id="7cc29-115">在主要窗格中，按一下您報表類型的索引標籤：**企業規範報告**、**電腦合規性報告**、**硬體審核報告**，或復原**審核報告**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-115">In the main pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

    <span data-ttu-id="7cc29-116">**記事** [歷史 MBAM] 用戶端資料會保留在合規性資料庫中。</span><span class="sxs-lookup"><span data-stu-id="7cc29-116">**Note** Historical MBAM Client data is retained in the compliance database.</span></span> <span data-ttu-id="7cc29-117">如果電腦遺失或被盜，可能需要此保留的資料。</span><span class="sxs-lookup"><span data-stu-id="7cc29-117">This retained data may be needed in case a computer is lost or stolen.</span></span> <span data-ttu-id="7cc29-118">執行企業報告時，您應該使用適當的開始和結束日期，將報告的時間範圍從一到兩周的範圍內，以增加報告資料的準確性。</span><span class="sxs-lookup"><span data-stu-id="7cc29-118">When running enterprise reports, you should use appropriate start and end dates to scope the time frames for the reports from one to two weeks to increase the reporting data accuracy.</span></span>

     

**<span data-ttu-id="7cc29-119">產生企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="7cc29-119">To generate an enterprise Compliance Report</span></span>**

1.  <span data-ttu-id="7cc29-120">在 MBAMadministration 網站上，按一下 [功能窗格] 中的 [**報表**]，然後按一下 [**企業合規性報告**] 索引標籤，並為您的報表選取適當的篩選器。</span><span class="sxs-lookup"><span data-stu-id="7cc29-120">On the MBAMadministration website, click **Reports** in the navigation pane, then click the **Enterprise Compliance Report** tab and select the appropriate filters for your report.</span></span> <span data-ttu-id="7cc29-121">針對企業合規性報告，您可以設定下列篩選器。</span><span class="sxs-lookup"><span data-stu-id="7cc29-121">For the Enterprise Compliance Report, you can set the following filters.</span></span>

    -   <span data-ttu-id="7cc29-122">**合規性狀態**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-122">**Compliance Status**.</span></span> <span data-ttu-id="7cc29-123">使用此篩選指定要包含在報表中的合規性狀態類型（例如，合規性或不相容）。</span><span class="sxs-lookup"><span data-stu-id="7cc29-123">Use this filter to specify the compliance status types (for example, Compliant or Noncompliant) to include in the report.</span></span>

    -   <span data-ttu-id="7cc29-124">**錯誤狀態**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-124">**Error State**.</span></span> <span data-ttu-id="7cc29-125">使用此篩選指定要包含在報表中的錯誤狀態類型，例如 [沒有錯誤] 或 [錯誤]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-125">Use this filter to specify the Error State types, such as No Error or Error, to include in the report.</span></span>

2.  <span data-ttu-id="7cc29-126">按一下 [**查看報表**] 以顯示指定的報表。</span><span class="sxs-lookup"><span data-stu-id="7cc29-126">Click **View Report** to display the specified report.</span></span>

    <span data-ttu-id="7cc29-127">報告結果可以儲存為多種可用檔案格式（例如 HTML、Microsoft Word 及 Microsoft Excel）中的任何一種。</span><span class="sxs-lookup"><span data-stu-id="7cc29-127">The report results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

    <span data-ttu-id="7cc29-128">**記事** 企業合規性報告是由 SQL 作業產生，每6小時執行一次。</span><span class="sxs-lookup"><span data-stu-id="7cc29-128">**Note** The Enterprise Compliance report is generated by a SQL job that runs every six hours.</span></span> <span data-ttu-id="7cc29-129">因此，當您第一次嘗試查看報表時，您可能會發現某些資料遺失了。</span><span class="sxs-lookup"><span data-stu-id="7cc29-129">Therefore, the first time you try to view the report you may find that some data is missing.</span></span>

     

3.  <span data-ttu-id="7cc29-130">若要在電腦合規性報告中查看電腦的相關資訊，請選取該電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cc29-130">To view information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="7cc29-131">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7cc29-131">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

**<span data-ttu-id="7cc29-132">產生電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="7cc29-132">To generate the Computer Compliance Report</span></span>**

1.  <span data-ttu-id="7cc29-133">在 MBAMadministration 網站中，選取 [功能窗格] 中的 [**報表**] 節點，然後選取 [**電腦合規性報告**]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-133">In the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Computer Compliance Report**.</span></span> <span data-ttu-id="7cc29-134">使用電腦相容性報告來搜尋**使用者名稱**或**電腦名稱稱**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-134">Use the Computer Compliance report to search for **user name** or **computer name**.</span></span>

2.  <span data-ttu-id="7cc29-135">按一下 [**查看報表**] 來查看電腦報告。</span><span class="sxs-lookup"><span data-stu-id="7cc29-135">Click **View Report** to view the computer report.</span></span>

    <span data-ttu-id="7cc29-136">結果可以儲存為幾種可用檔案格式（例如 HTML、Microsoft Word 及 Microsoft Excel）中的任何一種。</span><span class="sxs-lookup"><span data-stu-id="7cc29-136">Results can be saved in any of several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

3.  <span data-ttu-id="7cc29-137">若要在電腦合規性報告中顯示電腦的詳細資訊，請選取該電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="7cc29-137">To display more information about a computer in the Computer Compliance Report, select the computer name.</span></span>

4.  <span data-ttu-id="7cc29-138">選取電腦名稱稱旁的加號（+），以查看電腦上的磁片卷的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7cc29-138">Select the plus sign (+) next to the computer name to view information about the volumes on the computer.</span></span>

    <span data-ttu-id="7cc29-139">**記事** 如果電腦符合 MBAM 原則設定的需求，或電腦的硬體模型設定為不相容，則會認為 MBAM 用戶端電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="7cc29-139">**Note** An MBAM Client computer is considered compliant if the computer matches the requirements of the MBAM policy settings or the computer’s hardware model is set to incompatible.</span></span> <span data-ttu-id="7cc29-140">因此，當您要查看與電腦相關聯之磁片卷的詳細資訊時，由於硬體相容性而不符合 BitLocker 加密的電腦，即使其磁碟機容量已加密，也會顯示為不符合的狀態。</span><span class="sxs-lookup"><span data-stu-id="7cc29-140">Therefore, when you are viewing detailed information about the disk volumes associated with the computer, computers that are exempt from BitLocker encryption due to hardware compatibility can be displayed as compliant even though their drive volume encryption status is displayed as noncompliant.</span></span>

     

**<span data-ttu-id="7cc29-141">產生硬體相容性審核報告</span><span class="sxs-lookup"><span data-stu-id="7cc29-141">To generate the Hardware Compatibility Audit Report</span></span>**

1.  <span data-ttu-id="7cc29-142">從 MBAMadministration 網站選取 [功能窗格] 中的 [**報表**] 節點，然後選取 [**硬體] 審核報告**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-142">From the MBAMadministration website, select the **Report** node from the navigation pane, and then select the **Hardware Audit Report**.</span></span> <span data-ttu-id="7cc29-143">針對您的硬體審查報告選取適當的篩選器。</span><span class="sxs-lookup"><span data-stu-id="7cc29-143">Select the appropriate filters for your Hardware Audit report.</span></span> <span data-ttu-id="7cc29-144">硬體審查報告提供下列可用的篩選：</span><span class="sxs-lookup"><span data-stu-id="7cc29-144">The Hardware Audit report offers the following available filters:</span></span>

    -   <span data-ttu-id="7cc29-145">**User （Domain\\User）**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-145">**User (Domain\\User)**.</span></span> <span data-ttu-id="7cc29-146">指定進行變更的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="7cc29-146">Specifies the name of the user who made a change.</span></span>

    -   <span data-ttu-id="7cc29-147">**變更類型**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-147">**Change Type**.</span></span> <span data-ttu-id="7cc29-148">指定您要尋找的變更類型。</span><span class="sxs-lookup"><span data-stu-id="7cc29-148">Specifies the type of changes you are looking for.</span></span>

    -   <span data-ttu-id="7cc29-149">**開始日期**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-149">**Start Date**.</span></span> <span data-ttu-id="7cc29-150">指定您想要報告的日期範圍的開始日期部分。</span><span class="sxs-lookup"><span data-stu-id="7cc29-150">Specifies the Start Date part of the date range that you want to report on.</span></span>

    -   <span data-ttu-id="7cc29-151">[**結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-151">**End Date**.</span></span> <span data-ttu-id="7cc29-152">指定您想要報告的日期範圍的結束日期部分。</span><span class="sxs-lookup"><span data-stu-id="7cc29-152">Specifies the End Date part of the date range that you want to report on.</span></span>

2.  <span data-ttu-id="7cc29-153">按一下 [**查看報表**]，即可查看報表。</span><span class="sxs-lookup"><span data-stu-id="7cc29-153">Click **View Report** to view the report.</span></span>

    <span data-ttu-id="7cc29-154">結果可以儲存為幾種可用的檔案格式，例如 HTML、Microsoft Word 及 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="7cc29-154">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

**<span data-ttu-id="7cc29-155">產生修復金鑰審核報告</span><span class="sxs-lookup"><span data-stu-id="7cc29-155">To generate the Recovery Key Audit Report</span></span>**

1.  <span data-ttu-id="7cc29-156">從 MBAMadministration 網站，選取 [功能窗格] 中的 [**報表**] 節點，然後選取 [復原**審核報告**]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-156">From the MBAMadministration website, select the **Report** node in the navigation pane, and then select the **Recovery Audit Report**.</span></span> <span data-ttu-id="7cc29-157">選取您的 [復原金鑰] 審核報告篩選器。</span><span class="sxs-lookup"><span data-stu-id="7cc29-157">Select the filters for your Recovery Key Audit report.</span></span> <span data-ttu-id="7cc29-158">復原金鑰審核的可用篩選器如下所示：</span><span class="sxs-lookup"><span data-stu-id="7cc29-158">The available filters for Recovery Key audits are as follows:</span></span>

    -   <span data-ttu-id="7cc29-159">**請求**程式。</span><span class="sxs-lookup"><span data-stu-id="7cc29-159">**Requestor**.</span></span> <span data-ttu-id="7cc29-160">指定申請者的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="7cc29-160">Specifies the user name of the requestor.</span></span> <span data-ttu-id="7cc29-161">申請人是協助服務台中代表使用者存取金鑰的人員。</span><span class="sxs-lookup"><span data-stu-id="7cc29-161">The requestor is the person in the help desk who accessed the key on behalf of a user.</span></span>

    -   <span data-ttu-id="7cc29-162">**Requestee**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-162">**Requestee**.</span></span> <span data-ttu-id="7cc29-163">指定 requestee 的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="7cc29-163">Specifies the user name of the requestee.</span></span> <span data-ttu-id="7cc29-164">Requestee 是呼叫問訊台以取得復原金鑰的人員。</span><span class="sxs-lookup"><span data-stu-id="7cc29-164">The requestee is the person who called the help desk to obtain a recovery key.</span></span>

    -   <span data-ttu-id="7cc29-165">**要求結果**指定要求結果類型，例如：成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="7cc29-165">**Request Result** Specifies the request result types, such as: Success or Failed.</span></span> <span data-ttu-id="7cc29-166">例如，您可能會想要查看失敗的按鍵存取嘗試。</span><span class="sxs-lookup"><span data-stu-id="7cc29-166">For example, you may want to view failed key access attempts.</span></span>

    -   <span data-ttu-id="7cc29-167">**金鑰類型**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-167">**Key Type**.</span></span> <span data-ttu-id="7cc29-168">指定金鑰類型，例如：復原金鑰密碼或 TPM 密碼雜湊。</span><span class="sxs-lookup"><span data-stu-id="7cc29-168">Specifies the Key Type, such as: Recovery Key Password or TPM Password Hash.</span></span>

    -   <span data-ttu-id="7cc29-169">**開始日期**。</span><span class="sxs-lookup"><span data-stu-id="7cc29-169">**Start Date**.</span></span> <span data-ttu-id="7cc29-170">指定日期範圍的開始日期部分。</span><span class="sxs-lookup"><span data-stu-id="7cc29-170">Specifies the Start Date part of the date range.</span></span>

    -   <span data-ttu-id="7cc29-171">[**結束日期**]。</span><span class="sxs-lookup"><span data-stu-id="7cc29-171">**End Date**.</span></span> <span data-ttu-id="7cc29-172">指定日期範圍的結束日期部分。</span><span class="sxs-lookup"><span data-stu-id="7cc29-172">Specifies the End Date part of the date range.</span></span>

2.  <span data-ttu-id="7cc29-173">按一下 [**查看報表**] 以顯示報表。</span><span class="sxs-lookup"><span data-stu-id="7cc29-173">Click **View Report** to display the report.</span></span>

    <span data-ttu-id="7cc29-174">結果可以儲存為幾種可用的檔案格式，例如 HTML、Microsoft Word 及 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="7cc29-174">Results can be saved in several available file formats such as HTML, Microsoft Word, and Microsoft Excel.</span></span>

## <span data-ttu-id="7cc29-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="7cc29-175">Related topics</span></span>


[<span data-ttu-id="7cc29-176">使用 MBAM 1.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="7cc29-176">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





