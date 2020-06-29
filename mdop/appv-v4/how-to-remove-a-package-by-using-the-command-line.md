---
title: 如何使用命令列來移除封裝
description: 如何使用命令列來移除封裝
author: dansimp
ms.assetid: 47697ec7-20e5-4258-8865-a0a710d41d5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b282830802f34bfb0670ddfdb8e2852d3559e3f7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801170"
---
# <span data-ttu-id="379fd-103">如何使用命令列來移除封裝</span><span class="sxs-lookup"><span data-stu-id="379fd-103">How to Remove a Package by Using the Command Line</span></span>


<span data-ttu-id="379fd-104">您可以使用下列命令列程式，從特定電腦上的應用程式虛擬化（App-v）用戶端刪除虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="379fd-104">You can use the following command-line procedures to delete a virtual application package from the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="379fd-105">刪除所有使用者的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="379fd-105">To delete a virtual application package for all users</span></span>**

-   <span data-ttu-id="379fd-106">如果先前是使用/GLOBAL 開關為所有使用者新增套件，請使用下列命令刪除套件和通用檔案類型及快速鍵。</span><span class="sxs-lookup"><span data-stu-id="379fd-106">If the package was previously added for all users by using the /GLOBAL switch, use the following command to delete the package and the global file types and shortcuts.</span></span> <span data-ttu-id="379fd-107">需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="379fd-107">Administrator rights are required.</span></span> <span data-ttu-id="379fd-108">在這種情況下，不需要/GLOBAL 切換，因為命令會永遠執行套件的全域刪除。</span><span class="sxs-lookup"><span data-stu-id="379fd-108">The /GLOBAL switch is not needed in this case because the command always performs a global deletion of the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

**<span data-ttu-id="379fd-109">刪除先前針對個別使用者新增的套件</span><span class="sxs-lookup"><span data-stu-id="379fd-109">To delete a package previously added for individual users</span></span>**

1.  <span data-ttu-id="379fd-110">如果先前已為個別使用者新增套件，您有幾個選項。</span><span class="sxs-lookup"><span data-stu-id="379fd-110">If the package was previously added for individual users, you have several options.</span></span>

    <span data-ttu-id="379fd-111">在發行套件的每位使用者帳戶下，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="379fd-111">Run the following command once under the user account of each person the package was published to.</span></span> <span data-ttu-id="379fd-112">這會在應用程式漫遊至另一部電腦時，拒絕使用者存取。</span><span class="sxs-lookup"><span data-stu-id="379fd-112">This denies the user access to the applications if they roam to another computer.</span></span> <span data-ttu-id="379fd-113">它會從設定檔中刪除特定使用者的設定、快速鍵和檔案類型，並停止在使用者的內容下進行背景載入。</span><span class="sxs-lookup"><span data-stu-id="379fd-113">It deletes the specific user’s settings, shortcuts, and file types from the profile, and it stops background loads under the user’s context.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

2.  <span data-ttu-id="379fd-114">或者，您也可以在發行套件的每位使用者帳戶下執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="379fd-114">Alternatively, run the following command under the user account of each person the package was published to.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

    <span data-ttu-id="379fd-115">然後對套件執行此命令。</span><span class="sxs-lookup"><span data-stu-id="379fd-115">Then run this command for the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

    <span data-ttu-id="379fd-116">這會完全移除套件，並刪除其設定檔中的所有使用者設定、快速鍵和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="379fd-116">This completely removes the package, and it deletes all user settings, shortcuts, and file types from their profiles.</span></span> <span data-ttu-id="379fd-117">如果隨後重新新增套件，則使用者將必須再次指定其設定。</span><span class="sxs-lookup"><span data-stu-id="379fd-117">If the package is subsequently re-added, the users will have to specify their settings again.</span></span> <span data-ttu-id="379fd-118">只有「刪除應用程式」（**DeleteApp**）許可權才需要執行這個命令。</span><span class="sxs-lookup"><span data-stu-id="379fd-118">Only “Delete applications” (**DeleteApp**) permission is needed to run this command.</span></span>

3.  <span data-ttu-id="379fd-119">第三個替代方案是，您可以直接執行 [**刪除套件**] 命令，而不使用 [**取消發佈套件**] 命令。</span><span class="sxs-lookup"><span data-stu-id="379fd-119">As a third alternative, you can simply run the **DELETE PACKAGE** command without using the **UNPUBLISH PACKAGE** command.</span></span> <span data-ttu-id="379fd-120">在這種情況下，每個使用者的檔案類型和快速鍵都會隱藏而不是刪除，而且使用者設定會保留下來。</span><span class="sxs-lookup"><span data-stu-id="379fd-120">In this case, file types and shortcuts for each user are hidden rather than deleted, and the user settings are retained.</span></span> <span data-ttu-id="379fd-121">這表示如果隨後針對使用者重新新增套件，則會還原檔案類型和快速鍵，並重新應用使用者設定。</span><span class="sxs-lookup"><span data-stu-id="379fd-121">This means that if the package is subsequently re-added for the user, the file types and shortcuts are restored, and the user settings are reapplied.</span></span>

## <span data-ttu-id="379fd-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="379fd-122">Related topics</span></span>


[<span data-ttu-id="379fd-123">如何使用命令列新增封裝</span><span class="sxs-lookup"><span data-stu-id="379fd-123">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="379fd-124">如何使用命令列刪除所有虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="379fd-124">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

 

 





