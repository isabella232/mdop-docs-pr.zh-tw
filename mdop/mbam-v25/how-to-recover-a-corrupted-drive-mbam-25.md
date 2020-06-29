---
title: 如何修復損毀的磁碟機
description: 如何修復損毀的磁碟機
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809423"
---
# <span data-ttu-id="84e05-103">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="84e05-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="84e05-104">您可以將此程式與 [管理及監視] 網站（也稱為 [技術支援中心]）網站搭配使用，以復原受 BitLocker 保護的損壞的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="84e05-104">You can use this procedure with the Administration and Monitoring Website (also referred to as the Help Desk) Website to recover a corrupted drive that is protected by BitLocker.</span></span> <span data-ttu-id="84e05-105">若要這樣做，您將完成下表所述的工作。</span><span class="sxs-lookup"><span data-stu-id="84e05-105">To do this, you will complete the tasks outlined in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84e05-106">工作</span><span class="sxs-lookup"><span data-stu-id="84e05-106">Task</span></span></th>
<th align="left"><span data-ttu-id="84e05-107">詳細資料及詳細資訊</span><span class="sxs-lookup"><span data-stu-id="84e05-107">Details and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84e05-108">透過存取 [管理] 和 [監視] 網站的 [磁碟機] 恢復區域，建立復原金鑰套件檔案 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="84e05-108">Create a recovery key package file by accessing the <strong>Drive Recovery</strong> area of the Administration and Monitoring Website.</span></span></p></td>
<td align="left"><p><span data-ttu-id="84e05-109">若要存取 <strong> 磁片磁碟機復原 </strong> 區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。</span><span class="sxs-lookup"><span data-stu-id="84e05-109">To access the <strong>Drive Recovery</strong> area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="84e05-110">您可能會在建立這些角色時，為它們指定不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="84e05-110">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="84e05-111">如需詳細資訊，請參閱 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> 規劃 MBAM 2.5 群組和帳戶 </a> 。</span><span class="sxs-lookup"><span data-stu-id="84e05-111">For more information, see <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)">Planning for MBAM 2.5 Groups and Accounts</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84e05-112">將套件檔案複製到內含損壞之磁片磁碟機的電腦上。</span><span class="sxs-lookup"><span data-stu-id="84e05-112">Copy the package file to the computer that contains the corrupted drive.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84e05-113">使用 <code>repair-bde</code> 命令完成恢復程式。</span><span class="sxs-lookup"><span data-stu-id="84e05-113">Use the <code>repair-bde</code> command to complete the recovery process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="84e05-114">為了避免潛在的資料遺失，強烈建議您 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 先查看 manage-bde </a> 命令，然後再使用它。</span><span class="sxs-lookup"><span data-stu-id="84e05-114">To avoid a potential loss of data, it is strongly recommended that you review the <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)">Manage-bde</a> command before using it.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="84e05-115">復原損壞的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="84e05-115">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="84e05-116">開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。</span><span class="sxs-lookup"><span data-stu-id="84e05-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="84e05-117">在左窗格中，選取 [**磁片磁碟機**復原] 以開啟 [**復原存取加密的磁碟機**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="84e05-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="84e05-118">輸入使用者的 Windows 登入網域和使用者名稱、解除磁片磁碟機鎖定的原因，以及使用者的復原密碼識別碼。</span><span class="sxs-lookup"><span data-stu-id="84e05-118">Enter the end user’s Windows log-on domain and user name, the reason for unlocking the drive, and the end user’s recovery password ID.</span></span>

    <span data-ttu-id="84e05-119">**記事** 如果您是 [高級支援人員] 使用者訪問群組的成員，則不需要輸入使用者的功能變數名稱或使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="84e05-119">**Note** If you are a member of the Advanced Helpdesk Users access group, you do not have to enter the user’s domain name or user name.</span></span>

     

4.  <span data-ttu-id="84e05-120">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="84e05-120">Click **Submit**.</span></span> <span data-ttu-id="84e05-121">隨即會顯示覆原金鑰。</span><span class="sxs-lookup"><span data-stu-id="84e05-121">The recovery key will be displayed.</span></span>

5.  <span data-ttu-id="84e05-122">按一下 [**儲存**]，然後選取 [復原**金鑰套件**]。</span><span class="sxs-lookup"><span data-stu-id="84e05-122">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="84e05-123">系統會在您的電腦上建立復原金鑰套件。</span><span class="sxs-lookup"><span data-stu-id="84e05-123">The recovery key package will be created on your computer.</span></span>

6.  <span data-ttu-id="84e05-124">將復原金鑰套件複製到有損毀磁片磁碟機的電腦。</span><span class="sxs-lookup"><span data-stu-id="84e05-124">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

7.  <span data-ttu-id="84e05-125">開啟提升權限的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="84e05-125">Open an elevated command prompt.</span></span> <span data-ttu-id="84e05-126">若要這樣做，請按一下 [**開始**]，然後 `cmd` 在 [**搜尋程式和**檔案] 文字方塊中輸入。</span><span class="sxs-lookup"><span data-stu-id="84e05-126">To do this, click **Start** and type `cmd` in the **Search programs and files** text box.</span></span> <span data-ttu-id="84e05-127">以滑鼠右鍵按一下 [ **cmd.exe**]，然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="84e05-127">Right-click **cmd.exe**, and select **Run as Administrator**.</span></span>

8.  <span data-ttu-id="84e05-128">在命令提示字元中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="84e05-128">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="84e05-129">**記事** 將 &lt; *固定磁碟機*更換 &gt; 為可用的硬碟磁片磁碟機，其可用空間等於或大於損壞的磁片磁碟機上的資料。</span><span class="sxs-lookup"><span data-stu-id="84e05-129">**Note** Replace &lt;*fixed drive*&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="84e05-130">已損壞的磁片磁碟機上的資料會復原並移至指定的硬碟。</span><span class="sxs-lookup"><span data-stu-id="84e05-130">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     


## <span data-ttu-id="84e05-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="84e05-131">Related topics</span></span>


[<span data-ttu-id="84e05-132">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="84e05-132">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="84e05-133">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="84e05-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="84e05-134">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="84e05-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="84e05-135">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="84e05-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





