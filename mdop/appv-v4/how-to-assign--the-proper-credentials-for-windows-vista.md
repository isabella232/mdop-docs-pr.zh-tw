---
title: 如何為 Windows Vista 指派適當的認證
description: 如何為 Windows Vista 指派適當的認證
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808714"
---
# <span data-ttu-id="95cc8-103">如何為 Windows Vista 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="95cc8-103">How to Assign the Proper Credentials for Windows Vista</span></span>


<span data-ttu-id="95cc8-104">使用下列程式設定 App-V 桌面用戶端以取得適當的 WindowsVista 認證。</span><span class="sxs-lookup"><span data-stu-id="95cc8-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsVista credentials.</span></span>

<span data-ttu-id="95cc8-105">**記事** 此程式必須在每個未加入網域的電腦上完成。</span><span class="sxs-lookup"><span data-stu-id="95cc8-105">**Note** This procedure must be completed on each non-domain joined computer.</span></span> <span data-ttu-id="95cc8-106">根據您的環境中未加入網域的電腦數目而定，這可能是相當乏味的操作。</span><span class="sxs-lookup"><span data-stu-id="95cc8-106">Depending on the number of non-domain joined computers in your environment, this could be a very tedious operation.</span></span> <span data-ttu-id="95cc8-107">您可以將腳本與命令列介面用於認證管理員，以協助管理員自動執行此程式。</span><span class="sxs-lookup"><span data-stu-id="95cc8-107">You can use scripts and the command-line interface for Credential Manager to help administrators automate this process.</span></span>

 

**<span data-ttu-id="95cc8-108">若要為執行 Windows Vista 的 App-v 用戶端指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="95cc8-108">To assign the proper credentials for App-V clients running Windows Vista</span></span>**

1.  <span data-ttu-id="95cc8-109">在執行 Windows Vista 的 App-v Desktop 用戶端上使用系統管理員許可權，開啟 [**使用者帳戶**] 控制台（傳統的 [控制台]）。</span><span class="sxs-lookup"><span data-stu-id="95cc8-109">With administrator privileges on the App-V Desktop Client running Windows Vista, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="95cc8-110">從 [左側工作] 窗格中的 [**使用者帳戶**] 選取 [**管理您的網路密碼**]。</span><span class="sxs-lookup"><span data-stu-id="95cc8-110">Select **Manage your network passwords** from **User Accounts** in the left tasks pane.</span></span>

3.  <span data-ttu-id="95cc8-111">選取 [儲存的**使用者名稱和密碼**] 畫面上的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="95cc8-111">Select **Add** on the **Stored User Names and Passwords** screen.</span></span>

4.  <span data-ttu-id="95cc8-112">在 [**儲存的認證屬性**] 畫面上，提供 app-v 基礎結構的資訊：</span><span class="sxs-lookup"><span data-stu-id="95cc8-112">On the **Stored Credential Properties** screen, provide the information for the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="95cc8-113">**登入：** 發佈伺服器的外部名稱。</span><span class="sxs-lookup"><span data-stu-id="95cc8-113">**Log on to:** External name of the publishing server.</span></span>

    2.  <span data-ttu-id="95cc8-114">**使用者名稱：**[表單 Domain\\Username.] 中的外部使用者使用者名稱</span><span class="sxs-lookup"><span data-stu-id="95cc8-114">**User name:** User name for the external user in the form Domain\\Username.</span></span>

    3.  <span data-ttu-id="95cc8-115">**密碼：** 在 [**使用者名稱**] 欄位中輸入之使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="95cc8-115">**Password:** Password for the user account entered in the **User name** field.</span></span>

    4.  <span data-ttu-id="95cc8-116">保留已選取的**認證類型**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="95cc8-116">Leave **Credential Type** selected, and click **OK**.</span></span>

5.  <span data-ttu-id="95cc8-117">按一下 **\[關閉\]**。</span><span class="sxs-lookup"><span data-stu-id="95cc8-117">Click **Close**.</span></span> <span data-ttu-id="95cc8-118">認證儲存在認證存放區中，以適當驗證 App V 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="95cc8-118">The credentials are stored in the credential store for proper authentication to the App-V infrastructure.</span></span>

## <span data-ttu-id="95cc8-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="95cc8-119">Related topics</span></span>


[<span data-ttu-id="95cc8-120">加入網域及未加入網域的用戶端</span><span class="sxs-lookup"><span data-stu-id="95cc8-120">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="95cc8-121">如何為 Windows XP 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="95cc8-121">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





