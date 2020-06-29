---
title: 如何新增伺服器
description: 如何新增伺服器
author: dansimp
ms.assetid: 1f31678a-8edf-4d35-a812-e4a2abfd979b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d08b79bcbf34910ce357f39635431d11e3e99bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808726"
---
# <span data-ttu-id="a36c5-103">如何新增伺服器</span><span class="sxs-lookup"><span data-stu-id="a36c5-103">How to Add a Server</span></span>


<span data-ttu-id="a36c5-104">為了協助您更有效率地管理應用程式虛擬化管理伺服器，請將它們組織成伺服器群組。</span><span class="sxs-lookup"><span data-stu-id="a36c5-104">To help you manage your Application Virtualization Management Servers more efficiently, organize them into server groups.</span></span> <span data-ttu-id="a36c5-105">在應用程式虛擬化伺服器管理主控台中建立伺服器群組之後，您可以使用下列程式將伺服器新增到群組中。</span><span class="sxs-lookup"><span data-stu-id="a36c5-105">After you create a server group in the Application Virtualization Server Management Console, you can use the following procedure to add a server to the group.</span></span>

<span data-ttu-id="a36c5-106">**記事** 伺服器群組中的所有伺服器都必須連線到相同的資料存放區。</span><span class="sxs-lookup"><span data-stu-id="a36c5-106">**Note** All servers in a server group must be connected to the same data store.</span></span>

 

**<span data-ttu-id="a36c5-107">在群組中新增伺服器</span><span class="sxs-lookup"><span data-stu-id="a36c5-107">To add a server to a group</span></span>**

1.  <span data-ttu-id="a36c5-108">按一下左窗格中的 [**伺服器群組**] 節點，展開伺服器群組清單。</span><span class="sxs-lookup"><span data-stu-id="a36c5-108">Click the **Server Groups** node in the left pane to expand the list of server groups.</span></span>

2.  <span data-ttu-id="a36c5-109">以滑鼠右鍵按一下所需的 [伺服器] 群組，然後選取 [**新的應用程式虛擬化管理伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="a36c5-109">Right-click the desired server group, and select **New Application Virtualization Management Server**.</span></span>

3.  <span data-ttu-id="a36c5-110">在 [**新增伺服器群組] 嚮導**中，輸入**顯示名稱**和**DNS 主機名稱**。</span><span class="sxs-lookup"><span data-stu-id="a36c5-110">In the **New Server Group Wizard**, enter the **Display Name** and the **DNS Host Name**.</span></span>

4.  <span data-ttu-id="a36c5-111">保留伺服器快取的 [**最大記憶體配置**] 欄位中的預設值，以及 [**警告記憶體分配**] 欄位，以指定閾值警告層級。</span><span class="sxs-lookup"><span data-stu-id="a36c5-111">Leave the default values in the **Maximum Memory Allocation** field for the server cache and the **Warn Memory Allocation** field to specify the threshold warning level.</span></span>

5.  <span data-ttu-id="a36c5-112">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a36c5-112">Click **Next**.</span></span>

6.  <span data-ttu-id="a36c5-113">在 [連線**安全模式**] 對話方塊中，核取 [**使用增強型安全性**] 方塊以選取 [加強安全模式] （如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="a36c5-113">In the **Connection Security Mode** dialog, check the **Use enhanced security** box to select enhanced security mode, if desired.</span></span> <span data-ttu-id="a36c5-114">如有需要，請完成 [**憑證] 嚮導**或 [查看現有的憑證]。</span><span class="sxs-lookup"><span data-stu-id="a36c5-114">If necessary, complete the **Certificate Wizard** or view existing certificates.</span></span>

7.  <span data-ttu-id="a36c5-115">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a36c5-115">Click **Next**.</span></span>

8.  <span data-ttu-id="a36c5-116">在 [**應用程式 Virt 埠設定**] 對話方塊中，選取 [**使用預設埠**] 或 [**使用者自訂埠**] 選項按鈕，然後輸入自訂埠號碼。</span><span class="sxs-lookup"><span data-stu-id="a36c5-116">In the **App Virt Port Setting** dialog, select the **Use Default Port** or the **User Custom Port** radio button and enter the custom port number.</span></span>

9.  <span data-ttu-id="a36c5-117">按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="a36c5-117">Click **Finish**.</span></span>

## <span data-ttu-id="a36c5-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="a36c5-118">Related topics</span></span>


[<span data-ttu-id="a36c5-119">如何建立伺服器群組</span><span class="sxs-lookup"><span data-stu-id="a36c5-119">How to Create a Server Group</span></span>](how-to-create-a-server-group.md)

[<span data-ttu-id="a36c5-120">如何移除伺服器</span><span class="sxs-lookup"><span data-stu-id="a36c5-120">How to Remove a Server</span></span>](how-to-remove-a-server.md)

 

 





