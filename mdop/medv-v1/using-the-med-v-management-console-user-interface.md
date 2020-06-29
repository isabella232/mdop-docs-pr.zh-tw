---
title: 使用 MED-V 管理主控台使用者介面
description: 使用 MED-V 管理主控台使用者介面
author: dansimp
ms.assetid: f42714d7-6f0c-4995-ab31-d4ef0845a22c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22fc98c3edbea48847e1a00369bea21a470e66b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811402"
---
# <span data-ttu-id="ed9f2-103">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="ed9f2-103">Using the MED-V Management Console User Interface</span></span>


<span data-ttu-id="ed9f2-104">主控台使用者介面分為下列幾個區段：</span><span class="sxs-lookup"><span data-stu-id="ed9f2-104">The console user interface is divided into the following sections:</span></span>

-   <span data-ttu-id="ed9f2-105">下列**med-v 管理按鈕**會對應到三個模組：</span><span class="sxs-lookup"><span data-stu-id="ed9f2-105">The following **MED-V management buttons**, which correspond to the three modules:</span></span>

    -   <span data-ttu-id="ed9f2-106">**原則**：**原則**模組是用來定義 med-v 工作區及其相關的設定和許可權。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-106">**Policy**—The **Policy** module is used to define the MED-V workspaces and their related settings and permissions.</span></span>

    -   <span data-ttu-id="ed9f2-107">**影像**：**影像**模組可用來管理 med-v 工作區影像。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-107">**Images**—The **Images** module is used to manage MED-V workspace images.</span></span>

    -   <span data-ttu-id="ed9f2-108">**報告**：**報表**模組可用來產生並查看 med-v 工作區報告。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-108">**Reports**—The **Reports** module is used for generating and viewing MED-V workspace reports.</span></span>

-   <span data-ttu-id="ed9f2-109">**工具列**會顯示與所選按鈕相關的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-109">The **toolbar** displays shortcuts relevant to the button selected.</span></span>

-   <span data-ttu-id="ed9f2-110">[**顯示] 窗格**會顯示與所選按鈕相對應的模組。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-110">The **display pane** displays a module corresponding to the button that is selected.</span></span>

![](images/medv-ui-console-general.gif)

## <span data-ttu-id="ed9f2-111">如何登入 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="ed9f2-111">How to Log In to the MED-V Management Console</span></span>


**<span data-ttu-id="ed9f2-112">若要開啟 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="ed9f2-112">To open the MED-V management console</span></span>**

-   <span data-ttu-id="ed9f2-113">在 Windows [**開始**] 功能表上，選取 [**所有程式] &gt; med-v &gt; med-v 管理**，或在桌面上按兩下 [med-v 管理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-113">On the Windows **Start** menu, select **All Programs &gt; MED-V &gt; MED-V Management**, or on the desktop, double-click the MED-V Management icon.</span></span>

    <span data-ttu-id="ed9f2-114">[ **Med-v 管理登入**] 視窗隨即出現。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-114">The **MED-V Management Login** window appears.</span></span>

<span data-ttu-id="ed9f2-115">**記事** 基於安全性的考慮，第一個登入 MED-V 管理主控台的使用者將成為該電腦上唯一允許存取管理主控台的使用者。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-115">**Note** For security reasons, the first user to log in to the MED-V management console will become the only user on that computer allowed to access the management console.</span></span>

 

**<span data-ttu-id="ed9f2-116">登入</span><span class="sxs-lookup"><span data-stu-id="ed9f2-116">To log in</span></span>**

1.  <span data-ttu-id="ed9f2-117">以下列格式輸入您的網域使用者認證：</span><span class="sxs-lookup"><span data-stu-id="ed9f2-117">Type in your domain user credentials in the following format:</span></span>

    <span data-ttu-id="ed9f2-118">「網域 \ _name \\user\ _name "，" 密碼 "</span><span class="sxs-lookup"><span data-stu-id="ed9f2-118">"domain\_name\\user\_name", "password"</span></span>

    <span data-ttu-id="ed9f2-119">**記事** 設定伺服器時，系統會定義具有完整存取權的使用者，以及具有唯讀存取權的使用者。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-119">**Note** When configuring the server, users with full access as well as users with read-only access are defined.</span></span> <span data-ttu-id="ed9f2-120">所有使用者都必須是網域使用者。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-120">All users must be domain users.</span></span> <span data-ttu-id="ed9f2-121">網域使用者名稱和密碼用於 MED-V 管理登入。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-121">The domain user name and password is used for MED-V management login.</span></span>

     

2.  <span data-ttu-id="ed9f2-122">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-122">Click **OK**.</span></span>

    <span data-ttu-id="ed9f2-123">**Med-v 管理**主控台隨即出現。</span><span class="sxs-lookup"><span data-stu-id="ed9f2-123">The **MED-V Management** console appears.</span></span>

## <span data-ttu-id="ed9f2-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="ed9f2-124">Related topics</span></span>


[<span data-ttu-id="ed9f2-125">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="ed9f2-125">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

 

 





