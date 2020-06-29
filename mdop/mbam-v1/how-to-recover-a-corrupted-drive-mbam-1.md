---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800220"
---
# <span data-ttu-id="ef3e1-103">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="ef3e1-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="ef3e1-104">若要復原受 BitLocker 保護的已損壞的磁片磁碟機，Microsoft BitLocker 管理與監視（MBAM）技術支援服務使用者必須建立復原金鑰套件檔案。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-104">To recover a corrupted drive that has been protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) help desk user must create a recovery key package file.</span></span> <span data-ttu-id="ef3e1-105">這個套件檔案可以複製到包含損壞之磁片磁碟機的電腦，然後用來復原磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-105">This package file can be copied to the computer that contains the corrupted drive and then used to recover the drive.</span></span> <span data-ttu-id="ef3e1-106">若要完成這項作業，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-106">To accomplish this, use the following procedure.</span></span>

**<span data-ttu-id="ef3e1-107">復原損壞的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="ef3e1-107">To Recover a Corrupted Drive</span></span>**

1.  <span data-ttu-id="ef3e1-108">開啟 [MBAM 管理] 網站。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-108">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="ef3e1-109">從 [功能窗格] 中選取 [**磁片磁碟機**復原]。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-109">Select **Drive Recovery** from the navigation pane.</span></span> <span data-ttu-id="ef3e1-110">輸入使用者的網功能變數名稱稱和使用者名稱、解除磁片磁碟機鎖定的原因，以及使用者的復原密碼識別碼。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-110">Enter the user’s domain name and user name, the reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="ef3e1-111">**記事** 如果您是技術支援中心系統管理員角色的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-111">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="ef3e1-112">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-112">Click **Submit**.</span></span> <span data-ttu-id="ef3e1-113">隨即會顯示覆原金鑰。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-113">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="ef3e1-114">按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-114">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="ef3e1-115">系統會在您的電腦上建立復原金鑰套件。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-115">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="ef3e1-116">將復原金鑰套件複製到有損毀磁片磁碟機的電腦。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-116">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="ef3e1-117">開啟提升權限的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-117">Open an elevated command prompt.</span></span> <span data-ttu-id="ef3e1-118">若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式及**檔案] 方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-118">To do this, click **Start** and type `cmd` in the **Search programs and files** box.</span></span> <span data-ttu-id="ef3e1-119">在搜尋結果清單中，以滑鼠右鍵按一下**cmd.exe**然後選取 [以**系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-119">In the search results list, right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="ef3e1-120">在命令提示字元中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="ef3e1-120">At the command prompt, type the following:</span></span>

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="ef3e1-121">**記事** 針對 &lt; 命令中的固定磁片磁碟機 &gt; ，指定可用的儲存空間，該裝置的可用空間等於或大於損壞的磁片磁碟機上的資料。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-121">**Note** For the &lt;fixed drive&gt; in the command, specify an available storage device that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="ef3e1-122">已損壞的磁片磁碟機上的資料會復原並移至指定的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-122">Data on the corrupted drive is recovered and moved to the specified fixed drive.</span></span>

     

## <span data-ttu-id="ef3e1-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="ef3e1-123">Related topics</span></span>


[<span data-ttu-id="ef3e1-124">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="ef3e1-124">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





