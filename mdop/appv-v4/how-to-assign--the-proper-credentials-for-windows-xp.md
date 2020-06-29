---
title: 如何為 Windows XP 指派適當的認證
description: 如何為 Windows XP 指派適當的認證
author: dansimp
ms.assetid: cddbd556-d8f9-4981-a947-6e8e3f552b70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81581b75a9b7d5ce35e1c50fd01e0b7bbd3f7ef5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802170"
---
# <span data-ttu-id="764bf-103">如何為 Windows XP 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="764bf-103">How to Assign the Proper Credentials for Windows XP</span></span>


<span data-ttu-id="764bf-104">使用下列程式設定 App-V 桌面用戶端以取得適當的 WindowsXP 認證。</span><span class="sxs-lookup"><span data-stu-id="764bf-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsXP credentials.</span></span>

<span data-ttu-id="764bf-105">**記事** 完成這個程式後，非網域加入的用戶端可以在不加入網域的情況下執行發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="764bf-105">**Note** After finishing this procedure, the non-domain joined client can perform a publishing refresh without being joined to a domain.</span></span>

 

**<span data-ttu-id="764bf-106">為執行 WindowsXP 的 App-v 用戶端指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="764bf-106">To assign the proper credentials for App-V clients running WindowsXP</span></span>**

1.  <span data-ttu-id="764bf-107">在執行 WindowsXP 的 App-V 用戶端上使用系統管理員許可權，開啟 [**使用者帳戶**] 控制台（傳統的 [控制台]）。</span><span class="sxs-lookup"><span data-stu-id="764bf-107">With administrator privileges on the App-V Client running WindowsXP, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="764bf-108">按一下 [**高級]** 索引標籤，然後選取 [**管理密碼**]。</span><span class="sxs-lookup"><span data-stu-id="764bf-108">Click the **Advanced Tab**, and select **Manage Passwords**.</span></span>

3.  <span data-ttu-id="764bf-109">在 [已**儲存的使用者名稱和密碼**] 畫面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="764bf-109">On the **Stored User Names and Passwords** screen, click **Add**.</span></span>

4.  <span data-ttu-id="764bf-110">在 [**登入資訊屬性**] 畫面上，使用 app-v 基礎結構中的資訊填寫下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="764bf-110">On the **Logon Information Properties** screen, fill out the following fields with information from the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="764bf-111">**伺服器：** 發佈伺服器外部名稱的名稱。</span><span class="sxs-lookup"><span data-stu-id="764bf-111">**Server:** Name of publishing server external name.</span></span>

    2.  <span data-ttu-id="764bf-112">**使用者名稱：**[表單 Domain\\username.] 中的外部使用者使用者名稱</span><span class="sxs-lookup"><span data-stu-id="764bf-112">**User name:** User name for external user in the form Domain\\username.</span></span>

    3.  <span data-ttu-id="764bf-113">**密碼：** 在 [**使用者名稱**] 欄位中輸入之使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="764bf-113">**Password:** Password for the user account entered in the **User name** field.</span></span>

5.  <span data-ttu-id="764bf-114">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="764bf-114">Click **OK**.</span></span> <span data-ttu-id="764bf-115">認證將會儲存在用戶端上。</span><span class="sxs-lookup"><span data-stu-id="764bf-115">The credentials will be stored on the client.</span></span>

## <span data-ttu-id="764bf-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="764bf-116">Related topics</span></span>


[<span data-ttu-id="764bf-117">加入網域及未加入網域的用戶端</span><span class="sxs-lookup"><span data-stu-id="764bf-117">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="764bf-118">如何為 Windows Vista 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="764bf-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

 

 





