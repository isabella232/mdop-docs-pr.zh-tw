---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809885"
---
# <span data-ttu-id="9b432-103">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="9b432-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="9b432-104">本主題說明如何使用管理和監控網站（也稱為說明服務台）來重設 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="9b432-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to reset a TPM lockout.</span></span> <span data-ttu-id="9b432-105">如果使用者輸入錯誤的 PIN 太多次，就會發生 TPM 鎖定。</span><span class="sxs-lookup"><span data-stu-id="9b432-105">TPM lockouts can occur if an end user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="9b432-106">在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。</span><span class="sxs-lookup"><span data-stu-id="9b432-106">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="9b432-107">從管理和監控網站的 [**管理 TPM** ] 區域，您可以存取集中式金鑰復原資料系統，當您提供電腦識別碼及相關聯的使用者識別碼時，就會提供 TPM 擁有者密碼檔案。</span><span class="sxs-lookup"><span data-stu-id="9b432-107">From the **Manage TPM** area of the Administration and Monitoring Website, you can access the centralized Key Recovery data system, which provides a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

<span data-ttu-id="9b432-108">若要存取 [管理] 和 [監視] 網站的 [管理 TPM] 區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。</span><span class="sxs-lookup"><span data-stu-id="9b432-108">To access the Manage TPM area of the Administration and Monitoring Website, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="9b432-109">這些角色是管理員在 Active Directory 中建立的群組。</span><span class="sxs-lookup"><span data-stu-id="9b432-109">These roles are groups that administrators create in Active Directory.</span></span> <span data-ttu-id="9b432-110">您可以為這些群組使用任何名稱。</span><span class="sxs-lookup"><span data-stu-id="9b432-110">You can use any name for these groups.</span></span> <span data-ttu-id="9b432-111">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="9b432-111">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="9b432-112">如需 MBAM 及 TPM 擁有權的相關資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md#bkmk-tpm)。</span><span class="sxs-lookup"><span data-stu-id="9b432-112">For information about MBAM and TPM ownership, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

**<span data-ttu-id="9b432-113">重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="9b432-113">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="9b432-114">開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。</span><span class="sxs-lookup"><span data-stu-id="9b432-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="9b432-115">在左窗格中，按一下 [**管理 tpm** ] 以開啟 [**管理 tpm** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9b432-115">In the left pane, click **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="9b432-116">輸入電腦和電腦名稱稱的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="9b432-116">Enter the fully qualified domain name for the computer and the computer name.</span></span>

4.  <span data-ttu-id="9b432-117">輸入使用者的 Windows 登入網域和使用者名稱，以取得 TPM 擁有者密碼檔。</span><span class="sxs-lookup"><span data-stu-id="9b432-117">Enter the end user’s Windows log-on domain and user name to retrieve the TPM owner password file.</span></span>

    <span data-ttu-id="9b432-118">**記事** 如果您在 [MBAM 高級服務台使用者] 群組中，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="9b432-118">**Note** If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="9b432-119">從 [**要求 TPM 擁有者密碼**檔案的原因] 清單中，選取要求的原因，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="9b432-119">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="9b432-120">MBAM 會傳回下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9b432-120">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="9b432-121">找不到符合的 TPM 擁有者密碼檔案時的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="9b432-121">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="9b432-122">已提交電腦的 TPM 擁有者密碼檔</span><span class="sxs-lookup"><span data-stu-id="9b432-122">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="9b432-123">在您檢索 TPM 擁有者密碼之後，就會顯示擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="9b432-123">After the TPM owner password is retrieved, the owner password is displayed.</span></span>

6.  <span data-ttu-id="9b432-124">若要將密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9b432-124">To save the password to a .tpm file, click the **Save** button.</span></span>

7.  <span data-ttu-id="9b432-125">在 [管理]**和 [監視] 網站**的 [**管理 tpm** ] 區域中，選取 [**重設 tpm 封鎖**] 選項，並提供 TPM 擁有者密碼檔。</span><span class="sxs-lookup"><span data-stu-id="9b432-125">In the **Manage TPM** area of the **Administration and Monitoring Website**, select the **Reset TPM lockout** option and provide the TPM owner password file.</span></span>

    <span data-ttu-id="9b432-126">TPM 封鎖會重定，而且最終使用者的存取權會還原。</span><span class="sxs-lookup"><span data-stu-id="9b432-126">The TPM lockout is reset and the end user’s access is restored.</span></span>

    <span data-ttu-id="9b432-127">**重要** 請勿將 TPM 雜湊值或 TPM 擁有者密碼檔提供給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="9b432-127">**Important** Do not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="9b432-128">因為 TPM 資訊不會變更，所以提供給使用者的檔案會造成安全風險。</span><span class="sxs-lookup"><span data-stu-id="9b432-128">Because the TPM information does not change, giving the file to end users creates a security risk.</span></span>

     



## <span data-ttu-id="9b432-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="9b432-129">Related topics</span></span>


[<span data-ttu-id="9b432-130">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9b432-130">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="9b432-131">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="9b432-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9b432-132">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="9b432-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9b432-133">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="9b432-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





