---
title: 如何重設 TPM 鎖定
description: 如何重設 TPM 鎖定
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810923"
---
# <span data-ttu-id="5e0fc-103">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="5e0fc-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="5e0fc-104">Microsoft BitLocker 管理與監視（MBAM）的加密磁片磁碟機復原功能包含了資料的捕獲與儲存，以及管理受信任的平臺模組（TPM）所需的工具可用性。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are needed to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="5e0fc-105">本主題說明如何在 [管理與監控] 網站中存取集中式金鑰復原資料系統，這可以在提供電腦識別碼及相關聯的使用者識別碼時提供 TPM 擁有者密碼檔案。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-105">This topic covers how to access the centralized Key Recovery data system in the Administration and Monitoring website, which can provide a TPM owner password file when a computer ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="5e0fc-106">如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-106">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="5e0fc-107">在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-107">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="5e0fc-108">您只能在 MBAM 擁有 TPM 時重設 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-108">You can reset a TPM lockout only if MBAM owns the TPM.</span></span>

**<span data-ttu-id="5e0fc-109">重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="5e0fc-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="5e0fc-110">開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-110">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="5e0fc-111">在左側功能窗格中，選取 [**管理 tpm** ] 以開啟 [**管理 tpm** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-111">In the left navigation pane, select **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="5e0fc-112">輸入電腦和電腦名稱稱的完整功能變數名稱，然後輸入使用者的 Windows 登入網域和使用者的使用者名稱，以取得 TPM 擁有者密碼檔案。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-112">Enter the fully qualified domain name for the computer and the computer name, and enter the user’s Windows logon domain and the user’s user name to retrieve the TPM owner password file.</span></span>

4.  <span data-ttu-id="5e0fc-113">從 [**要求 TPM 擁有者密碼**檔案的原因] 清單中，選取要求的原因，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-113">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="5e0fc-114">MBAM 會傳回下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5e0fc-114">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="5e0fc-115">找不到符合的 TPM 擁有者密碼檔的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="5e0fc-115">An error message, if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="5e0fc-116">已提交電腦的 TPM 擁有者密碼檔</span><span class="sxs-lookup"><span data-stu-id="5e0fc-116">The TPM owner password file for the submitted computer</span></span>

    **<span data-ttu-id="5e0fc-117">注意</span><span class="sxs-lookup"><span data-stu-id="5e0fc-117">Note</span></span>**  
    <span data-ttu-id="5e0fc-118">如果您是「高級服務台」使用者，則不需要 [使用者網域] 和 [使用者識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-118">If you are an Advanced Helpdesk user, the user domain and user ID fields are not required.</span></span>



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. <span data-ttu-id="5e0fc-119">若要將密碼儲存至 tpm 檔案，請按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-119">To save the password to a .tpm file, click the **Save** button.</span></span>

   <span data-ttu-id="5e0fc-120">使用者會執行 TPM 管理主控台，選取 [**重設 tpm 封鎖**] 選項，並提供 tpm 擁有者密碼檔來重設 tpm 封鎖。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-120">The user will run the TPM management console, select the **Reset TPM lockout** option, and provide the TPM owner password file to reset the TPM lockout.</span></span>

   **<span data-ttu-id="5e0fc-121">重要</span><span class="sxs-lookup"><span data-stu-id="5e0fc-121">Important</span></span>**  
   <span data-ttu-id="5e0fc-122">技術支援中心系統管理員不應將 TPM 雜湊值或 TPM 擁有者密碼檔提供給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-122">Help Desk administrators should not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="5e0fc-123">TPM 資訊不會變更，因此如果將檔案提供給使用者，就可能會造成安全風險。</span><span class="sxs-lookup"><span data-stu-id="5e0fc-123">The TPM information does not change, so it could pose a security risk if the file is given to end users.</span></span>



## <span data-ttu-id="5e0fc-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="5e0fc-124">Related topics</span></span>


[<span data-ttu-id="5e0fc-125">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="5e0fc-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









