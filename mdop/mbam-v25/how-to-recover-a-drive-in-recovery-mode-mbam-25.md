---
title: 如何修復處於修復模式的磁碟機
description: 如何修復處於修復模式的磁碟機
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809914"
---
# <span data-ttu-id="33085-103">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="33085-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="33085-104">本主題說明如何使用管理和監控網站（也稱為說明服務台）來取得恢復密碼，以便在其受 BitLocker 保護的磁碟機進入復原模式時提供給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="33085-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to get a recovery password to give to end users if their BitLocker-protected drive goes into recovery mode.</span></span> <span data-ttu-id="33085-105">如果使用者遺失或忘記其 PIN 或密碼，或受信任的模組平臺（TPM）晶片偵測到電腦的 BIOS 或啟動檔案變更，磁碟機就會進入 [復原模式]。</span><span class="sxs-lookup"><span data-stu-id="33085-105">Drives go into recovery mode if users lose or forget their PIN or password or if the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="33085-106">若要取得復原密碼，請使用 [管理] 和 [監視] 網站的 [**磁碟機恢復**] 區域。</span><span class="sxs-lookup"><span data-stu-id="33085-106">To get a recovery password, use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="33085-107">您必須獲指派 MBAM 技術支援人員的使用者角色，或 MBAM [高級支援人員] 使用者角色，才能存取網站的此區域。</span><span class="sxs-lookup"><span data-stu-id="33085-107">You must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role to access this area of the website.</span></span>

**<span data-ttu-id="33085-108">注意</span><span class="sxs-lookup"><span data-stu-id="33085-108">Note</span></span>**  
<span data-ttu-id="33085-109">您可能會在建立這些角色時，為它們指定不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="33085-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="33085-110">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="33085-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>



**<span data-ttu-id="33085-111">重要</span><span class="sxs-lookup"><span data-stu-id="33085-111">Important</span></span>**  
<span data-ttu-id="33085-112">在單一使用之後，復原密碼就會過期。</span><span class="sxs-lookup"><span data-stu-id="33085-112">Recovery passwords expire after a single use.</span></span> <span data-ttu-id="33085-113">在操作系統磁碟機和固定資料磁碟機上，會自動套用單一用途規則。</span><span class="sxs-lookup"><span data-stu-id="33085-113">On operating system drives and fixed data drives, the single-use rule is applied automatically.</span></span> <span data-ttu-id="33085-114">在抽取式磁碟磁碟機上，在已啟用群組原則設定以管理抽取式磁碟磁碟機的電腦上，移除該磁碟機，然後將它重新插入並解除鎖定時，就會套用它。</span><span class="sxs-lookup"><span data-stu-id="33085-114">On removable drives, it is applied when the drive is removed and then reinserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="33085-115">在復原模式中復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="33085-115">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="33085-116">開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。</span><span class="sxs-lookup"><span data-stu-id="33085-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="33085-117">在左窗格中，選取 [**磁片磁碟機**復原] 以開啟 [**復原存取加密的磁碟機**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="33085-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="33085-118">輸入使用者的 Windows 登入網域和使用者名稱，以查看恢復資訊。</span><span class="sxs-lookup"><span data-stu-id="33085-118">Enter the end user’s Windows log-on domain and user name to view recovery information.</span></span>

    **<span data-ttu-id="33085-119">注意</span><span class="sxs-lookup"><span data-stu-id="33085-119">Note</span></span>**  
    <span data-ttu-id="33085-120">如果您在 [MBAM 高級服務台使用者] 群組中，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="33085-120">If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>



4.  <span data-ttu-id="33085-121">輸入復原金鑰識別碼的前八位數，以查看可能符合的復原金鑰清單，或輸入整個復原金鑰識別碼來取得確切的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="33085-121">Enter the first eight digits of the recovery key ID to see a list of possible matching recovery keys, or enter the entire recovery key ID to get the exact recovery key.</span></span>

5.  <span data-ttu-id="33085-122">從 [**磁片磁碟機解除鎖定的原因**] 清單中，選取其中一個預先定義的選項，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="33085-122">From the **Reason for Drive Unlock** list, select one of the predefined options, and then click **Submit**.</span></span>

    <span data-ttu-id="33085-123">MBAM 會傳回下列內容：</span><span class="sxs-lookup"><span data-stu-id="33085-123">MBAM returns the following:</span></span>

    -   <span data-ttu-id="33085-124">找不到符合的復原密碼時的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="33085-124">An error message if no matching recovery password is found</span></span>

    -   <span data-ttu-id="33085-125">如果使用者有多個相符的恢復密碼，可能會有多個可能的相符專案</span><span class="sxs-lookup"><span data-stu-id="33085-125">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    -   <span data-ttu-id="33085-126">已提交使用者的復原密碼及復原套件</span><span class="sxs-lookup"><span data-stu-id="33085-126">The recovery password and recovery package for the submitted user</span></span>

        **<span data-ttu-id="33085-127">注意</span><span class="sxs-lookup"><span data-stu-id="33085-127">Note</span></span>**  
        <span data-ttu-id="33085-128">如果您要復原已損壞的磁片磁碟機，recover 套裝程式選項會提供 BitLocker，其中包含復原磁片磁碟機所需的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="33085-128">If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.</span></span>



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. <span data-ttu-id="33085-129">若要複製密碼，請按一下 [**複製金鑰**]，然後將恢復密碼貼到電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="33085-129">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="33085-130">或者，按一下 [**儲存**] 以將復原密碼儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="33085-130">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="33085-131">當使用者在系統中輸入復原密碼或使用復原套件時，磁片磁碟機就會解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="33085-131">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>



## <span data-ttu-id="33085-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="33085-132">Related topics</span></span>


[<span data-ttu-id="33085-133">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="33085-133">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)



## <span data-ttu-id="33085-134">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="33085-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="33085-135">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="33085-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="33085-136">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="33085-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





