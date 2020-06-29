---
title: 如何修復處於修復模式的磁碟機
description: 如何修復處於修復模式的磁碟機
author: dansimp
ms.assetid: 09d27e4b-57fa-47c7-a004-8b876a49f27e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1151ffe7453eb8d07d2aa6dcb4c41f6b3efe6de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800222"
---
# <span data-ttu-id="6dc30-103">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="6dc30-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="6dc30-104">Microsoft BitLocker 管理和監控（MBAM）包括加密的磁片磁碟機復原功能。</span><span class="sxs-lookup"><span data-stu-id="6dc30-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes Encrypted Drive Recovery features.</span></span> <span data-ttu-id="6dc30-105">這些功能可確保在 BitLocker 將該磁片移至 [恢復] 模式時，捕獲和儲存存取受 BitLocker 保護的磁片時所需的工具資料和可用性。</span><span class="sxs-lookup"><span data-stu-id="6dc30-105">These features ensure the capture and storage of data and availability of tools that are required to access a BitLocker-protected volume when BitLocker puts that volume into recovery mode.</span></span> <span data-ttu-id="6dc30-106">當 PIN 或密碼遺失或忘記，或當受信任的模組平臺（TPM）晶片偵測到電腦的 BIOS 或啟動檔案變更時，BitLocker 受保護的卷就會進入 [復原模式]。</span><span class="sxs-lookup"><span data-stu-id="6dc30-106">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects a change to the computer's BIOS or startup files.</span></span>

<span data-ttu-id="6dc30-107">您可以使用此程式來存取集中式金鑰復原資料系統，這些系統可在提供復原密碼識別碼及相關聯的使用者識別碼時提供恢復密碼。</span><span class="sxs-lookup"><span data-stu-id="6dc30-107">Use this procedure to access the centralized Key Recovery data system that can provide a recovery password when a recovery password ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="6dc30-108">**重要** MBAM 會產生單一使用修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="6dc30-108">**Important** MBAM generates single-use recovery keys.</span></span> <span data-ttu-id="6dc30-109">在這個限制下，復原金鑰只能使用一次，然後才會失效。</span><span class="sxs-lookup"><span data-stu-id="6dc30-109">Under this limitation, a recovery key can be used only once and then it is no longer valid.</span></span> <span data-ttu-id="6dc30-110">復原密碼的單一用途會自動套用至作業系統磁片磁碟機和固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="6dc30-110">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="6dc30-111">在抽取式磁碟磁碟機上，當您移除該磁碟機，然後在已啟用群組原則設定的電腦上重新插入並解除鎖定時，就會套用單一用途，以管理抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="6dc30-111">On removable drives, the single use is applied when the drive is removed and then re-inserted and unlocked on a computer that has the group policy settings activated to manage removable drives.</span></span>

 

**<span data-ttu-id="6dc30-112">在復原模式中復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="6dc30-112">To recover a drive in Recovery Mode</span></span>**

1.  <span data-ttu-id="6dc30-113">開啟 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="6dc30-113">Open the MBAM website.</span></span>

2.  <span data-ttu-id="6dc30-114">在 [功能窗格] 中，按一下 [**磁片磁碟機**復原]。</span><span class="sxs-lookup"><span data-stu-id="6dc30-114">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="6dc30-115">隨即會開啟 [**復原對加密磁片磁碟機的存取**] 網頁。</span><span class="sxs-lookup"><span data-stu-id="6dc30-115">The **Recover access to an encrypted drive** webpage opens.</span></span>

3.  <span data-ttu-id="6dc30-116">輸入使用者的 Windows 登入網域和使用者名稱，以及復原金鑰識別碼的前八位數，即可接收可能相符的復原金鑰清單。</span><span class="sxs-lookup"><span data-stu-id="6dc30-116">Enter the user's Windows Logon domain and user name and the first eight digits of the recovery key ID, to receive a list of possible matching recovery keys.</span></span> <span data-ttu-id="6dc30-117">或者，輸入完整的復原金鑰識別碼來接收確切的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="6dc30-117">Alternatively, enter the entire recovery key ID to receive the exact recovery key.</span></span> <span data-ttu-id="6dc30-118">在 [**磁碟機解除鎖定的原因**] 下拉式清單中，選取其中一個預先定義的選項，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="6dc30-118">Select one of the predefined options in the **Reason for Drive Unlock** drop-down list, and then click **Submit**.</span></span>

    <span data-ttu-id="6dc30-119">**記事** 如果您是 MBAM 高級支援人員的使用者，則不需要使用者網域和使用者識別碼專案。</span><span class="sxs-lookup"><span data-stu-id="6dc30-119">**Note** If you are an MBAM Advanced Helpdesk User, the user domain and user ID entries are not required.</span></span>

     

4.  <span data-ttu-id="6dc30-120">MBAM 會傳回下列內容：</span><span class="sxs-lookup"><span data-stu-id="6dc30-120">MBAM returns the following:</span></span>

    1.  <span data-ttu-id="6dc30-121">找不到符合的復原密碼時的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="6dc30-121">An error message if no matching recovery password is found</span></span>

    2.  <span data-ttu-id="6dc30-122">如果使用者有多個相符的恢復密碼，可能會有多個可能的相符專案</span><span class="sxs-lookup"><span data-stu-id="6dc30-122">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    3.  <span data-ttu-id="6dc30-123">已提交使用者的復原密碼及復原套件</span><span class="sxs-lookup"><span data-stu-id="6dc30-123">The recovery password and recovery package for the submitted user</span></span>

        <span data-ttu-id="6dc30-124">**記事** 如果您要復原的是已損壞的磁片磁碟機，[復原套件] 選項會提供 BitLocker，以及嘗試復原所需的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="6dc30-124">**Note** If you are recovering a damaged drive, the recovery package option provides BitLocker with the critical information necessary to attempt the recovery.</span></span>

         

5.  <span data-ttu-id="6dc30-125">在取回復原密碼及復原套件之後，就會顯示 [恢復密碼]。</span><span class="sxs-lookup"><span data-stu-id="6dc30-125">After the recovery password and recovery package are retrieved, the recovery password is displayed.</span></span> <span data-ttu-id="6dc30-126">若要複製密碼，請按一下 [**複製金鑰**]，然後將恢復密碼貼到電子郵件或其他文字檔中，以進行暫時儲存。</span><span class="sxs-lookup"><span data-stu-id="6dc30-126">To copy the password, click **Copy Key**, and then paste the recovery password into an email or other text file for temporary storage.</span></span> <span data-ttu-id="6dc30-127">或者，若要將恢復密碼儲存至檔案，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6dc30-127">Or, to save the recovery password to a file, click **Save**.</span></span>

6.  <span data-ttu-id="6dc30-128">當使用者在系統中輸入復原密碼或使用復原套件時，磁片磁碟機就會解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="6dc30-128">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="6dc30-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="6dc30-129">Related topics</span></span>


[<span data-ttu-id="6dc30-130">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="6dc30-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





