---
title: 如何授與應用程式的存取權
description: 如何授與應用程式的存取權
author: dansimp
ms.assetid: e54d9e84-21f5-488f-b040-25f374d9289f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9cd3dfe4661f09bb7e7d3514a397955cb892be81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801414"
---
# <span data-ttu-id="4f328-103">如何授與應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="4f328-103">How to Grant Access to an Application</span></span>


<span data-ttu-id="4f328-104">就像管理員一樣，您可以使用應用程式虛擬化伺服器管理主控台來判斷哪些使用者可以存取哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="4f328-104">As the administrator, you can use the Application Virtualization Server Management Console to determine which users can access which applications.</span></span> <span data-ttu-id="4f328-105">您可以在匯入 Sequencer 專案（SPRJ）或開啟軟體描述項（OSD）檔案時，或使用應用**程式的 [內容] 對話方塊**隨時進行此動作。</span><span class="sxs-lookup"><span data-stu-id="4f328-105">You can do this when you import the Sequencer Project (SPRJ) or Open Software Descriptor (OSD) file or at anytime using the application's **Properties** dialog box.</span></span> <span data-ttu-id="4f328-106">在這兩種方法的情況下，請使用 [**存取許可權**] 選項來新增使用者。</span><span class="sxs-lookup"><span data-stu-id="4f328-106">With both methods, use the **Access Permissions** options to add users.</span></span>

**<span data-ttu-id="4f328-107">若要授與應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="4f328-107">To grant access to an application</span></span>**

1.  <span data-ttu-id="4f328-108">針對現有的應用程式，請按一下左窗格中的 [**應用程式**] 節點。</span><span class="sxs-lookup"><span data-stu-id="4f328-108">For an existing application, click the **Applications** node in the left pane.</span></span> <span data-ttu-id="4f328-109">在右窗格中，以滑鼠右鍵按一下應用程式，然後選擇 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="4f328-109">Right-click an application in the right pane, and choose **Properties**.</span></span>

2.  <span data-ttu-id="4f328-110">選取 [**存取許可權**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4f328-110">Select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="4f328-111">若要新增使用者群組，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4f328-111">To add user groups, click **Add**.</span></span>

4.  <span data-ttu-id="4f328-112">在 [**新增/編輯使用者群組**] 對話方塊中，流覽至 [使用者] 群組。</span><span class="sxs-lookup"><span data-stu-id="4f328-112">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="4f328-113">您也可以在個別欄位中輸入資訊，以輸入網域和群組。</span><span class="sxs-lookup"><span data-stu-id="4f328-113">You can also enter the domain and group by typing the information in the respective fields.</span></span>

5.  <span data-ttu-id="4f328-114">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f328-114">Click **OK**.</span></span> <span data-ttu-id="4f328-115">您可以使用相同的頁面新增其他群組。</span><span class="sxs-lookup"><span data-stu-id="4f328-115">You can add other groups with the same pages.</span></span>

6.  <span data-ttu-id="4f328-116">當嚮導再次出現時，請按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="4f328-116">When the wizard reappears, click **OK**.</span></span>

    <span data-ttu-id="4f328-117">**記事** 您必須先在 Active Directory 網域服務中設定您的群組，才能嘗試授與應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="4f328-117">**Note** You must set up your groups in Active Directory Domain Services before you attempt to grant access to applications.</span></span>

     

## <span data-ttu-id="4f328-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="4f328-118">Related topics</span></span>


[<span data-ttu-id="4f328-119">如何拒絕應用程式的存取權</span><span class="sxs-lookup"><span data-stu-id="4f328-119">How to Deny Access to an Application</span></span>](how-to-deny-access-to-an-application.md)

[<span data-ttu-id="4f328-120">如何在伺服器管理主控台中管理應用程式群組</span><span class="sxs-lookup"><span data-stu-id="4f328-120">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="4f328-121">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="4f328-121">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="4f328-122">如何手動新增應用程式</span><span class="sxs-lookup"><span data-stu-id="4f328-122">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





