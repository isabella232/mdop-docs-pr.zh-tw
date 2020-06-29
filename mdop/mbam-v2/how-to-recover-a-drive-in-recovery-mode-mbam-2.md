---
title: 如何修復處於修復模式的磁碟機
description: 如何修復處於修復模式的磁碟機
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810928"
---
# <span data-ttu-id="3ed6a-103">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="3ed6a-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="3ed6a-104">Microsoft BitLocker 管理與監控（MBAM）的加密磁片磁碟機復原功能可確保在 BitLocker 進入復原模式時，捕獲和儲存存取受 BitLocker 保護的磁片所需的工具資料和可用性。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-104">The encrypted drive recovery features of Microsoft BitLocker Administration and Monitoring (MBAM) ensure the capture and storage of data and availability of tools required to access a BitLocker-protected volume when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="3ed6a-105">當 PIN 或密碼遺失或忘記，或當受信任的模組平臺（TPM）晶片偵測到電腦的 BIOS 或啟動檔案變更時，BitLocker 受保護的卷就會進入 [復原模式]。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-105">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="3ed6a-106">使用此程式來存取集中式金鑰復原資料系統，如果提供了復原密碼識別碼及相關聯的使用者識別碼，就可以提供復原密碼。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-106">Use this procedure to access the centralized key recovery data system, which can provide a recovery password if a recovery password ID and associated user identifier are supplied.</span></span>

**<span data-ttu-id="3ed6a-107">重要</span><span class="sxs-lookup"><span data-stu-id="3ed6a-107">Important</span></span>**  
<span data-ttu-id="3ed6a-108">Microsoft BitLocker 管理和監控使用的單一用途修復金鑰會在使用時過期。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-108">Microsoft BitLocker Administration and Monitoring uses single-use recovery keys that expire upon use.</span></span> <span data-ttu-id="3ed6a-109">復原密碼的單一用途會自動套用至作業系統磁片磁碟機和固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-109">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="3ed6a-110">在抽取式磁碟磁碟機上，當您移除該磁碟機，然後在已啟用群組原則設定的電腦上重新插入並解除鎖定時，就會套用它，以管理抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-110">On removable drives, it is applied when the drive is removed and then re-inserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="3ed6a-111">在復原模式中復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="3ed6a-111">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="3ed6a-112">開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-112">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="3ed6a-113">在 [功能窗格] 中，按一下 [**磁片磁碟機**復原]。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-113">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="3ed6a-114">隨即會開啟「復原加密的磁片磁碟機存取」網頁。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-114">The “Recover access to an encrypted drive” webpage opens.</span></span>

3.  <span data-ttu-id="3ed6a-115">輸入使用者的 Windows 登入網域和使用者名稱，以查看復原資訊，以及復原金鑰識別碼的前八位數，以接收符合實際復原金鑰的可能相符的復原金鑰清單或整個復原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-115">Enter the Windows Logon domain and user name of the user to view recovery information and the first eight digits of the recovery key ID to receive a list of possible matching recovery keys or the entire recovery key ID to receive the exact recovery key.</span></span>

4.  <span data-ttu-id="3ed6a-116">從 [**硬碟解除鎖定的原因**] 清單中選取其中一個預先定義的選項，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-116">Select one of the predefined options from the **Reason for Drive Unlock** list, and then click **Submit**.</span></span>

    **<span data-ttu-id="3ed6a-117">注意</span><span class="sxs-lookup"><span data-stu-id="3ed6a-117">Note</span></span>**  
    <span data-ttu-id="3ed6a-118">如果您是 MBAM 高級支援人員的使用者，則不需要使用者網域和使用者識別碼專案。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-118">If you are an MBAM Advanced Helpdesk user, the user domain and user ID entries are not required.</span></span>



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. <span data-ttu-id="3ed6a-119">若要複製密碼，請按一下 [**複製金鑰**]，然後將恢復密碼貼到電子郵件訊息中。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-119">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="3ed6a-120">或者，按一下 [**儲存**] 以將復原密碼儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-120">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="3ed6a-121">當使用者在系統中輸入復原密碼或使用復原套件時，磁片磁碟機就會解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="3ed6a-121">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="3ed6a-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="3ed6a-122">Related topics</span></span>


[<span data-ttu-id="3ed6a-123">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="3ed6a-123">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









