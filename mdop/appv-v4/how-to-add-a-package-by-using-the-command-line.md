---
title: 如何使用命令列新增封裝
description: 如何使用命令列新增封裝
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808738"
---
# <span data-ttu-id="2d10a-103">如何使用命令列新增封裝</span><span class="sxs-lookup"><span data-stu-id="2d10a-103">How to Add a Package by Using the Command Line</span></span>


<span data-ttu-id="2d10a-104">下列程式會列出將虛擬應用程式套件新增到特定電腦上的應用程式虛擬化（app-v）用戶端所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="2d10a-104">The following procedures list the steps that are necessary to add a virtual application package to the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="2d10a-105">為特定使用者新增虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="2d10a-105">To add a virtual application package for a specific user</span></span>**

-   <span data-ttu-id="2d10a-106">在要取得套件的人員的使用者帳戶下，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="2d10a-106">Run the following command under the user account of the person who is to get the package.</span></span> <span data-ttu-id="2d10a-107">該命令會為該使用者新增併發布套件。</span><span class="sxs-lookup"><span data-stu-id="2d10a-107">The command adds and publishes the package for that user.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**<span data-ttu-id="2d10a-108">為所有使用者新增虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="2d10a-108">To add a virtual application package for all users</span></span>**

-   <span data-ttu-id="2d10a-109">在具有系統管理員許可權的帳戶下，執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="2d10a-109">Run the following command under an account that has administrator rights.</span></span> <span data-ttu-id="2d10a-110">此套件是針對電腦上的所有使用者新增併發布。</span><span class="sxs-lookup"><span data-stu-id="2d10a-110">The package is added and published for all users on the computer.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**<span data-ttu-id="2d10a-111">使用電子軟體發佈系統新增套件</span><span class="sxs-lookup"><span data-stu-id="2d10a-111">To add a package using an electronic software distribution system</span></span>**

1.  <span data-ttu-id="2d10a-112">如果您使用的是電子軟體發佈系統，它會在電腦的**系統**帳戶下執行命令，除非您使用/GLOBAL 開關，否則只會針對該帳戶發佈套件。</span><span class="sxs-lookup"><span data-stu-id="2d10a-112">If you are using an electronic software distribution system that runs the commands under the computer’s **SYSTEM** account, the package is published for that account only, unless you use the /GLOBAL switch.</span></span> <span data-ttu-id="2d10a-113">執行下列命令，為電腦上的所有使用者新增及發佈套件：</span><span class="sxs-lookup"><span data-stu-id="2d10a-113">Run the following command to add and publish the package for all users on the computer:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    <span data-ttu-id="2d10a-114">如果您只想要為特定使用者新增套件，請執行 [**新增套件**] 命令，然後在每個人員的使用者帳戶下執行下列 [**發佈套件**] 命令，為每位使用者明確發佈套件：</span><span class="sxs-lookup"><span data-stu-id="2d10a-114">If you want to add the package for specific users only, run the **ADD PACKAGE** command, and then explicitly publish the package for each user by running the following **PUBLISH PACKAGE** command under each person’s user account:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    <span data-ttu-id="2d10a-115">發佈不含全域參數的套件時，系統會授與使用者對套件中應用程式的存取權，並將資訊清單中所列的檔案類型和快速鍵發佈至使用者的設定檔。</span><span class="sxs-lookup"><span data-stu-id="2d10a-115">Publishing the package without the GLOBAL parameter grants the user access to the applications in the package and publishes the file types and shortcuts that are listed in the manifest to the user’s profile.</span></span> <span data-ttu-id="2d10a-116">所需的許可權為「管理檔案類型關聯」（**ManageTypes**）和「發佈快捷方式」（**PublishShortcut**）。</span><span class="sxs-lookup"><span data-stu-id="2d10a-116">Permissions required are “Manage file type associations” (**ManageTypes**) and “Publish shortcuts” (**PublishShortcut**).</span></span>

## <span data-ttu-id="2d10a-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="2d10a-117">Related topics</span></span>


[<span data-ttu-id="2d10a-118">如何使用命令列刪除所有虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="2d10a-118">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[<span data-ttu-id="2d10a-119">如何使用命令列來移除封裝</span><span class="sxs-lookup"><span data-stu-id="2d10a-119">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





