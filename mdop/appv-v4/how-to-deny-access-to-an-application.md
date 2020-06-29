---
title: 如何拒絕應用程式的存取權
description: 如何拒絕應用程式的存取權
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801449"
---
# <span data-ttu-id="fbd43-103">如何拒絕應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="fbd43-103">How to Deny Access to an Application</span></span>


<span data-ttu-id="fbd43-104">使用者必須在應用程式的**存取許可權**清單中，才能載入和使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="fbd43-104">Users must be in an application's **Access Permissions** list to load and use the application.</span></span> <span data-ttu-id="fbd43-105">雖然應用程式虛擬化伺服器管理主控台不支援明確拒絕使用者群組對應用程式的存取權，但您可以從應用程式的屬性中移除使用者群組，以達到此目的。</span><span class="sxs-lookup"><span data-stu-id="fbd43-105">Although the Application Virtualization Server Management Console does not support explicitly denying a user group access to an application, you can remove the user groups from an application’s properties to achieve this.</span></span>

**<span data-ttu-id="fbd43-106">拒絕存取應用程式</span><span class="sxs-lookup"><span data-stu-id="fbd43-106">To deny access to an application</span></span>**

1.  <span data-ttu-id="fbd43-107">針對現有的應用程式，請按一下左窗格中的 [**應用程式**] 節點。</span><span class="sxs-lookup"><span data-stu-id="fbd43-107">For an existing application, click the **Applications** node in the left pane.</span></span>

2.  <span data-ttu-id="fbd43-108">在右窗格中，以滑鼠右鍵按一下應用程式，然後選擇 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fbd43-108">Right-click an application in the right pane, and choose **Properties**.</span></span> <span data-ttu-id="fbd43-109">然後選取 [**存取許可權**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fbd43-109">Then select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="fbd43-110">若要移除使用者群組的存取權，請醒目提示 [使用者] 群組，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="fbd43-110">To remove access for a user group, highlight the user group and click **Remove**.</span></span>

4.  <span data-ttu-id="fbd43-111">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbd43-111">Click **OK**.</span></span>

    <span data-ttu-id="fbd43-112">**記事** 若要控制對應用程式的存取，您也可以限制應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="fbd43-112">**Note** To control access to applications, you can also limit the application licenses.</span></span> <span data-ttu-id="fbd43-113">在 Active Directory 網域服務中設定適當的使用者群組，提供最簡單的方式來授與拒絕特定使用者組的存取權。</span><span class="sxs-lookup"><span data-stu-id="fbd43-113">Setting up the proper user groups in Active Directory Domain Services provides the easiest way to grant and deny access to specific sets of users.</span></span>

     

## <span data-ttu-id="fbd43-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="fbd43-114">Related topics</span></span>


[<span data-ttu-id="fbd43-115">如何授與應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="fbd43-115">How to Grant Access to an Application</span></span>](how-to-grant-access-to-an-application.md)

[<span data-ttu-id="fbd43-116">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="fbd43-116">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="fbd43-117">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="fbd43-117">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





