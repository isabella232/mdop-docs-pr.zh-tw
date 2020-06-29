---
title: 如何針對 App-V Management Server 設定 Windows Server 2008
description: 如何針對 App-V Management Server 設定 Windows Server 2008
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801530"
---
# <span data-ttu-id="aa99c-103">如何針對 App-V Management Server 設定 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="aa99c-103">How to Configure Windows Server 2008 for App-V Management Servers</span></span>


<span data-ttu-id="aa99c-104">安裝 Microsoft Application Virtualization （App-v）管理 Web 服務的 Windows Server 2008 server 上，需要將 Internet Information Services （IIS）安裝為伺服器上的角色。</span><span class="sxs-lookup"><span data-stu-id="aa99c-104">The Windows Server 2008 server on which you install the Microsoft Application Virtualization (App-V) Management Web Service requires Internet Information Services (IIS) to be installed as a role on the server.</span></span> <span data-ttu-id="aa99c-105">使用下列程式來設定 Windows Server 2008，以支援應用程式 Vserver 安裝。</span><span class="sxs-lookup"><span data-stu-id="aa99c-105">Use the following procedure to configure Windows Server 2008 to support App-Vserver installation.</span></span>

**<span data-ttu-id="aa99c-106">在 Windows Server2008 電腦上安裝 IIS</span><span class="sxs-lookup"><span data-stu-id="aa99c-106">To install IIS on a Windows Server2008 computer</span></span>**

1.  <span data-ttu-id="aa99c-107">在 Windows Server2008 電腦上，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，然後按一下 [**伺服器管理員**] 來啟動伺服器管理員。</span><span class="sxs-lookup"><span data-stu-id="aa99c-107">On the Windows Server2008 computer, click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Server Manager** to start Server Manager.</span></span> <span data-ttu-id="aa99c-108">在伺服器管理員中，以滑鼠右鍵按一下 [**角色**] 節點，然後按一下 [**新增角色**]，啟動 [**新增角色] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="aa99c-108">In Server Manager, right-click the **Roles** node, and click **Add Roles** to start the **Add Roles Wizard**.</span></span>

2.  <span data-ttu-id="aa99c-109">在 [**新增角色] 嚮導**的 [**選取伺服器角色**] 頁面上，選取 [ **Web 服務器（IIS）**]。</span><span class="sxs-lookup"><span data-stu-id="aa99c-109">In the **Add Roles Wizard**, on the **Select Server Roles** page, select **Web Server (IIS)**.</span></span> <span data-ttu-id="aa99c-110">出現提示時，請按一下 [**新增必要的功能**] 來新增相依功能。</span><span class="sxs-lookup"><span data-stu-id="aa99c-110">When prompted, click **Add Required Features** to add the dependent features.</span></span>

3.  <span data-ttu-id="aa99c-111">在 [**選取伺服器角色**] 頁面上，按一下 **[下一步**]，然後再按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="aa99c-111">On the **Select Server Roles** page, Click **Next**, and then click **Next** again.</span></span>

4.  <span data-ttu-id="aa99c-112">在 [**新增角色] 嚮導**中的 [**選取角色服務**] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="aa99c-112">In the **Add Roles Wizard**, on the **Select Role Services** page:</span></span>

    1.  <span data-ttu-id="aa99c-113">在 [**應用程式開發**] 底下，選取 [ **ASP.NET** ]，然後在出現提示時，按一下 [**新增必要的角色服務**] 來新增相依角色服務和功能。</span><span class="sxs-lookup"><span data-stu-id="aa99c-113">Under **Application Development**, select **ASP.NET** and, when prompted, click **Add Required Role Services** to add the dependent roles services and features.</span></span>

    2.  <span data-ttu-id="aa99c-114">在 [**安全性**] 底下，選取 [ **Windows 驗證**]。</span><span class="sxs-lookup"><span data-stu-id="aa99c-114">Under **Security**, select **Windows Authentication**.</span></span>

    3.  <span data-ttu-id="aa99c-115">在 [**管理工具**] 節點中，選取 [ **IIS 管理腳本與工具**]。</span><span class="sxs-lookup"><span data-stu-id="aa99c-115">In the **Management Tools** node, select **IIS Management Scripts and Tools**.</span></span> <span data-ttu-id="aa99c-116">在 [ **IIS6 管理相容性**] 底下，請確定已選取**IIS6 元資料庫相容性**和**IIS6 WMI 相容性**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="aa99c-116">Under **IIS6 Management Compatibility**, ensure that both **IIS6 Metabase Compatibility** and **IIS6 WMI Compatibility** are selected, and then click **Next**.</span></span>

5.  <span data-ttu-id="aa99c-117">在 [**確認安裝選項**] 頁面上，按一下 [**安裝**]，然後完成嚮導的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="aa99c-117">On the **Confirm Installation Selections** page, click **Install**, and then complete the rest of the wizard.</span></span>

6.  <span data-ttu-id="aa99c-118">按一下 [**關閉**] 以結束 [**新增角色] 嚮導**，然後關閉 [伺服器管理員]。</span><span class="sxs-lookup"><span data-stu-id="aa99c-118">Click **Close** to exit the **Add Roles Wizard**, and then close Server Manager.</span></span>

## <span data-ttu-id="aa99c-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa99c-119">Related topics</span></span>


[<span data-ttu-id="aa99c-120">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="aa99c-120">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="aa99c-121">Application Virtualization 部署與升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="aa99c-121">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





