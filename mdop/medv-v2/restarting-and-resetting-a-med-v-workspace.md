---
title: 重新啟動和重設 MED-V 工作區
description: 重新啟動和重設 MED-V 工作區
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811145"
---
# <span data-ttu-id="56a3f-103">重新啟動和重設 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="56a3f-103">Restarting and Resetting a MED-V Workspace</span></span>


<span data-ttu-id="56a3f-104">在疑難排解期間，有時您可能會發現需要重新開機或重設 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="56a3f-104">During troubleshooting, you may sometimes find it necessary to restart or reset the MED-V workspace.</span></span> <span data-ttu-id="56a3f-105">重新開機 MED-V 工作區與重新開機物理電腦基本相同。</span><span class="sxs-lookup"><span data-stu-id="56a3f-105">Restarting the MED-V workspace is basically the same as restarting a physical computer.</span></span> <span data-ttu-id="56a3f-106">重設 MED-V 工作區第一次重新安裝，並刪除儲存在虛擬機器中的所有資料。</span><span class="sxs-lookup"><span data-stu-id="56a3f-106">Resetting the MED-V workspace reruns first time setup and deletes all data that is stored in the virtual machine.</span></span> <span data-ttu-id="56a3f-107">由於已刪除所有已儲存的資料，因此您通常應該只重設 MED-V 工作區，以解決最嚴重的疑難排解問題，或將先前工作的 MED-V 工作區還原到工作狀態。</span><span class="sxs-lookup"><span data-stu-id="56a3f-107">Because all stored data is deleted, you typically should only reset the MED-V workspace to resolve the most serious troubleshooting issues, or to restore a previously working MED-V workspace back to a working state.</span></span>

<span data-ttu-id="56a3f-108">如需如何開啟 MED-V 管理工具組的相關資訊，請參閱[使用管理工具組在 med-v 中進行疑難排解](troubleshooting-med-v-by-using-the-administration-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="56a3f-108">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

**<span data-ttu-id="56a3f-109">重新開機 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="56a3f-109">Restarting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="56a3f-110">在 [ **med-v-v 管理工具**] 視窗中，按一下 [**重新開機 Med-v-V 工作區**]。</span><span class="sxs-lookup"><span data-stu-id="56a3f-110">On the **MED-V Administration Toolkit** window, click **Restart MED-V Workspace**.</span></span> <span data-ttu-id="56a3f-111">對話方塊視窗隨即開啟，您必須在其中確認您要重新開機 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="56a3f-111">A dialog window opens in which you must confirm that you want to restart the MED-V workspace.</span></span>

2.  <span data-ttu-id="56a3f-112">按一下 [**重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="56a3f-112">Click **Restart**.</span></span>

    <span data-ttu-id="56a3f-113">當 MED-V 工作區重新開機時，任何執行中的已發佈應用程式或開啟的網站，都將會關閉。</span><span class="sxs-lookup"><span data-stu-id="56a3f-113">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace restarts.</span></span>

**<span data-ttu-id="56a3f-114">重設 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="56a3f-114">Resetting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="56a3f-115">在 [ **Med-v 管理工具**組] 視窗中，按一下 [**重設 Med-v-V 工作區**]。</span><span class="sxs-lookup"><span data-stu-id="56a3f-115">On the **MED-V Administration Toolkit** window, click **Reset MED-V Workspace**.</span></span> <span data-ttu-id="56a3f-116">對話方塊視窗隨即開啟，您必須在其中確認您要重設 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="56a3f-116">A dialog window opens in which you must confirm that you want to reset the MED-V workspace.</span></span>

    <span data-ttu-id="56a3f-117">**警告** 重設 MED-V 工作區會導致第一次設定再次執行，進而重新載入原始的虛擬硬碟。</span><span class="sxs-lookup"><span data-stu-id="56a3f-117">**Warning** Resetting the MED-V workspace causes first time setup to run again, and thus reloads the original virtual hard disk.</span></span> <span data-ttu-id="56a3f-118">在第一次執行設定之後，所有儲存在 MED-V 工作區的資料，都將會被刪除。</span><span class="sxs-lookup"><span data-stu-id="56a3f-118">All data that is stored in the MED-V workspace since first time setup was originally run will be deleted.</span></span>

     

2.  <span data-ttu-id="56a3f-119">按一下 \[**重設**\]。</span><span class="sxs-lookup"><span data-stu-id="56a3f-119">Click **Reset**.</span></span>

    <span data-ttu-id="56a3f-120">當 MED-V 工作區重設時，任何執行中的已發佈應用程式或開啟的網站，都將會關閉。</span><span class="sxs-lookup"><span data-stu-id="56a3f-120">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace resets.</span></span>

## <span data-ttu-id="56a3f-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="56a3f-121">Related topics</span></span>


[<span data-ttu-id="56a3f-122">檢視及設定 MED-V 記錄</span><span class="sxs-lookup"><span data-stu-id="56a3f-122">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)

[<span data-ttu-id="56a3f-123">檢視 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="56a3f-123">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





