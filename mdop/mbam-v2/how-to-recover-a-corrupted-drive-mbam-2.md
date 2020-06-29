---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809615"
---
# <span data-ttu-id="5faaa-103">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="5faaa-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="5faaa-104">若要復原受 BitLocker 保護的損毀磁片磁碟機，Microsoft BitLocker 管理與監控（MBAM）技術支援服務使用者將需要建立復原金鑰套件檔案。</span><span class="sxs-lookup"><span data-stu-id="5faaa-104">To recover a corrupted drive protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) Help Desk user will need to create a recovery key package file.</span></span> <span data-ttu-id="5faaa-105">這個套件檔案可以複製到包含損毀磁片磁碟機的電腦，然後用來復原磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5faaa-105">This package file can then be copied to the computer that contains the corrupted drive, and then used to recover the drive.</span></span> <span data-ttu-id="5faaa-106">使用下列程式執行此動作所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="5faaa-106">Use the following procedure for the steps needed to do this.</span></span>

<span data-ttu-id="5faaa-107">**重要** 為了避免潛在的資料遺失，強烈建議您閱讀「repair-manage-bde」說明，並清楚瞭解如何使用命令，然後再完成下列指示。</span><span class="sxs-lookup"><span data-stu-id="5faaa-107">**Important** To avoid a potential loss of data, it is strongly recommended that you read the “repair-bde” help and clearly understand how to use the command before completing the following instructions.</span></span>

 

**<span data-ttu-id="5faaa-108">復原損壞的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5faaa-108">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="5faaa-109">若要建立復原損壞的磁片磁碟機所需的復原金鑰套件，請啟動網頁瀏覽器，然後開啟 MBAM 管理和監控網站。</span><span class="sxs-lookup"><span data-stu-id="5faaa-109">To create the recovery key package necessary to recover a corrupted drive, start a web browser and open the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="5faaa-110">從左側流覽窗格中選取 [**磁片磁碟機**復原]。</span><span class="sxs-lookup"><span data-stu-id="5faaa-110">Select **Drive Recovery** from the left navigation pane.</span></span> <span data-ttu-id="5faaa-111">輸入使用者的功能變數名稱、使用者名稱、解除磁片鎖定的原因，以及使用者的復原密碼識別碼。</span><span class="sxs-lookup"><span data-stu-id="5faaa-111">Enter the user’s domain name, user name, reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="5faaa-112">**記事** 如果您是技術支援中心系統管理員角色的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="5faaa-112">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="5faaa-113">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="5faaa-113">Click **Submit**.</span></span> <span data-ttu-id="5faaa-114">隨即會顯示覆原金鑰。</span><span class="sxs-lookup"><span data-stu-id="5faaa-114">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="5faaa-115">按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。</span><span class="sxs-lookup"><span data-stu-id="5faaa-115">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="5faaa-116">系統會在您的電腦上建立復原金鑰套件。</span><span class="sxs-lookup"><span data-stu-id="5faaa-116">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="5faaa-117">將復原金鑰套件複製到有損毀磁片磁碟機的電腦。</span><span class="sxs-lookup"><span data-stu-id="5faaa-117">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="5faaa-118">開啟提升權限的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="5faaa-118">Open an elevated command prompt.</span></span> <span data-ttu-id="5faaa-119">若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式及**檔案] 方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="5faaa-119">To do this, click **Start** and type `cmd` in the **Search programs and files box**.</span></span> <span data-ttu-id="5faaa-120">以滑鼠右鍵按一下**cmd.exe** ，然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="5faaa-120">Right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="5faaa-121">在命令提示字元中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="5faaa-121">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="5faaa-122">**記事** &lt;將固定磁碟機更換 &gt; 為可用的硬碟磁片磁碟機，其可用空間等於或大於損壞的磁片磁碟機上的資料。</span><span class="sxs-lookup"><span data-stu-id="5faaa-122">**Note** Replace &lt;fixed drive&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="5faaa-123">已損壞的磁片磁碟機上的資料會復原並移至指定的硬碟。</span><span class="sxs-lookup"><span data-stu-id="5faaa-123">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     

## <span data-ttu-id="5faaa-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="5faaa-124">Related topics</span></span>


[<span data-ttu-id="5faaa-125">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="5faaa-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





