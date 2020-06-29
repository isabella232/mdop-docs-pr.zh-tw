---
title: 如何使用 MED-V 工作區封裝工具來管理 URL 重新導向
description: 如何使用 MED-V 工作區封裝工具來管理 URL 重新導向
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810784"
---
# <span data-ttu-id="e5432-103">如何使用 MED-V 工作區封裝工具來管理 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="e5432-103">How to Manage URL Redirection by Using the MED-V Workspace Packager</span></span>


<span data-ttu-id="e5432-104">您可以在 MED-V 工作區中使用 MED-V 工作區包裝程式來管理 URL 重新導向。</span><span class="sxs-lookup"><span data-stu-id="e5432-104">You can use the MED-V Workspace Packager to manage URL redirection in the MED-V workspace.</span></span>

**<span data-ttu-id="e5432-105">在 MED-V 工作區中管理 web 位址重新導向</span><span class="sxs-lookup"><span data-stu-id="e5432-105">To manage web address redirection in a MED-V workspace</span></span>**

1.  <span data-ttu-id="e5432-106">若要開啟**Med-v 工作區包裝**程式，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 工作區包裝程式**]。</span><span class="sxs-lookup"><span data-stu-id="e5432-106">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2.  <span data-ttu-id="e5432-107">在**Med-v 工作區包裝**程式主版面板上，按一下 [**管理 Web**重新導向]。</span><span class="sxs-lookup"><span data-stu-id="e5432-107">On the **MED-V Workspace Packager** main panel, click **Manage Web Redirection**.</span></span>

3.  <span data-ttu-id="e5432-108">在 [**管理 Web**重新導向] 視窗中，您可以輸入、貼上或匯入在 med-v 工作區中重新導向至 Internet Explorer 的 url 清單。</span><span class="sxs-lookup"><span data-stu-id="e5432-108">In the **Manage Web Redirection** window, you can type, paste, or import a list of the URLs that are redirected to Internet Explorer in the MED-V workspace.</span></span>

    **<span data-ttu-id="e5432-109">注意</span><span class="sxs-lookup"><span data-stu-id="e5432-109">Note</span></span>**  
    <span data-ttu-id="e5432-110">MED-V 中的 URL 重新導向只支援 HTTP 和 HTTPS 協定。</span><span class="sxs-lookup"><span data-stu-id="e5432-110">URL redirection in MED-V only supports the protocols HTTP and HTTPS.</span></span> <span data-ttu-id="e5432-111">MED-V 不提供 FTP 或任何其他協定的支援。</span><span class="sxs-lookup"><span data-stu-id="e5432-111">MED-V does not provide support for FTP or any other protocols.</span></span>



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



4. <span data-ttu-id="e5432-112">按一下 [**另存**新格式]。</span><span class="sxs-lookup"><span data-stu-id="e5432-112">Click **Save as…**</span></span> <span data-ttu-id="e5432-113">將更新的 URL 重新導向檔案儲存在指定的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="e5432-113">to save the updated URL redirection files in the specified folder.</span></span> <span data-ttu-id="e5432-114">MED-V 會建立包含更新之 URL 重新導向資訊的登錄檔案。</span><span class="sxs-lookup"><span data-stu-id="e5432-114">MED-V creates a registry file that contains the updated URL redirection information.</span></span> <span data-ttu-id="e5432-115">使用 [群組原則] 部署更新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="e5432-115">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="e5432-116">如需如何使用群組原則的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="e5432-116">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

   <span data-ttu-id="e5432-117">MED-V 也會在指定的資料夾中建立 Windows PowerShell 腳本，您可以用來重新建立更新的 MED-V 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="e5432-117">MED-V also creates a Windows PowerShell script in the specified folder that you can use to re-create the updated MED-V workspace package.</span></span>

## <span data-ttu-id="e5432-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5432-118">Related topics</span></span>


[<span data-ttu-id="e5432-119">如何新增或移除已部署 MED-V 工作區中的 URL 重新導向資訊</span><span class="sxs-lookup"><span data-stu-id="e5432-119">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[<span data-ttu-id="e5432-120">管理 MED-V URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="e5432-120">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)









