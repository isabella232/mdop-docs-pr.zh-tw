---
title: 如何使用命令列刪除所有虛擬應用程式
description: 如何使用命令列刪除所有虛擬應用程式
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801457"
---
# <span data-ttu-id="1d292-103">如何使用命令列刪除所有虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="1d292-103">How to Delete All Virtual Applications by Using the Command Line</span></span>


<span data-ttu-id="1d292-104">您可以使用下列程式來刪除特定電腦中的所有虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d292-104">You can use the following procedure to delete all virtual applications from a specific computer.</span></span>

<span data-ttu-id="1d292-105">**記事** 從套件中刪除所有應用程式時，應用程式虛擬化（App-v）用戶端也會刪除套件。</span><span class="sxs-lookup"><span data-stu-id="1d292-105">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

 

**<span data-ttu-id="1d292-106">刪除所有應用程式</span><span class="sxs-lookup"><span data-stu-id="1d292-106">To delete all applications</span></span>**

-   <span data-ttu-id="1d292-107">執行下列命令，以刪除執行命令之使用者帳戶的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d292-107">Run the following command to delete all applications for the user account under which the command is run.</span></span> <span data-ttu-id="1d292-108">如果您使用具有管理許可權的帳戶來執行命令與選用的/GLOBAL 開關，所有的使用者都會刪除所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1d292-108">If you run the command with the optional /GLOBAL switch, using an account with administrative rights, all applications are deleted for all users.</span></span>

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    <span data-ttu-id="1d292-109">**記事** 從套件中刪除所有應用程式時，應用程式虛擬化（App-v）用戶端也會刪除套件。</span><span class="sxs-lookup"><span data-stu-id="1d292-109">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

     

## <span data-ttu-id="1d292-110">相關主題</span><span class="sxs-lookup"><span data-stu-id="1d292-110">Related topics</span></span>


[<span data-ttu-id="1d292-111">如何使用命令列新增封裝</span><span class="sxs-lookup"><span data-stu-id="1d292-111">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="1d292-112">如何使用命令列來移除封裝</span><span class="sxs-lookup"><span data-stu-id="1d292-112">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





