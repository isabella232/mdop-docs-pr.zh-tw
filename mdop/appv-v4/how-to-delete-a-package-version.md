---
title: 如何刪除封裝版本
description: 如何刪除封裝版本
author: dansimp
ms.assetid: a55adb9d-ffa6-4df3-a2d1-5e0c73c35e1b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc77e60ac9745033ae8f074ae71db0cb8517a202
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801466"
---
# <span data-ttu-id="e7dcd-103">如何刪除封裝版本</span><span class="sxs-lookup"><span data-stu-id="e7dcd-103">How to Delete a Package Version</span></span>


<span data-ttu-id="e7dcd-104">從應用程式虛擬化伺服器管理主控台，針對有多個版本的套件，您可以使用下列程式來刪除一或多個版本，仍會對流進行其他版本的套件。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-104">From the Application Virtualization Server Management Console, for a package that has multiple versions, you can use the following procedure to delete one or more versions and still stream the remaining versions of the package.</span></span> <span data-ttu-id="e7dcd-105">您可以這樣做，以更有效率的方式管理伺服器上的檔案，或移除過時的版本。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-105">You might do this to more effectively manage files on the server or to remove an obsolete version.</span></span>

<span data-ttu-id="e7dcd-106">**記事** 當您選擇刪除版本時，確認方塊會提醒您用戶端電腦可能仍在使用它。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-106">**Note** When you choose to delete a version, a confirmation box reminds you that client computers might still be using it.</span></span> <span data-ttu-id="e7dcd-107">在移除已使用的版本之前，您應該建議使用者結束並卸載任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-107">You should advise users to exit and unload any applications before you remove a version that is in use.</span></span>

 

**<span data-ttu-id="e7dcd-108">刪除套件版本</span><span class="sxs-lookup"><span data-stu-id="e7dcd-108">To delete a package version</span></span>**

1.  <span data-ttu-id="e7dcd-109">在應用程式虛擬化伺服器管理主控台的左面板中，展開 [**套件**]。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-109">In the left panel of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

2.  <span data-ttu-id="e7dcd-110">按一下包含您要刪除之版本的套件。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-110">Click the package that contains the version you want to delete.</span></span>

3.  <span data-ttu-id="e7dcd-111">在中央窗格中，以滑鼠右鍵按一下您要刪除的套件版本，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-111">In the center pane, right-click the version of the package you want to delete and choose **Delete**.</span></span>

4.  <span data-ttu-id="e7dcd-112">閱讀確認視窗，然後按一下 **[是]** 以完成動作。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-112">Read the confirmation window, and click **Yes** to complete the action.</span></span>

    <span data-ttu-id="e7dcd-113">**記事** 如果您的使用者已中斷連線作業，下次連線到伺服器時，其應用程式將會以新的版本取代。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-113">**Note** If you have users in disconnected operation, their applications will be replaced with the new versions the next time they connect to the servers.</span></span> <span data-ttu-id="e7dcd-114">確定所有使用者都已更新應用程式之後，您就可以刪除舊版本。</span><span class="sxs-lookup"><span data-stu-id="e7dcd-114">After you are sure all users have updated applications, you can delete old versions.</span></span>

     

## <span data-ttu-id="e7dcd-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7dcd-115">Related topics</span></span>


[<span data-ttu-id="e7dcd-116">如何刪除封裝</span><span class="sxs-lookup"><span data-stu-id="e7dcd-116">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="e7dcd-117">如何在伺服器管理主控台中管理封裝</span><span class="sxs-lookup"><span data-stu-id="e7dcd-117">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





