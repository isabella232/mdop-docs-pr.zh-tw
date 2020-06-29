---
title: 如何使用 App-V 5.1 Management Console 建立自訂設定檔案
description: 如何使用 App-V 5.1 Management Console 建立自訂設定檔案
author: dansimp
ms.assetid: f5ab426a-f49a-47b3-93f3-b9d60aada8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 282207b5424442950e88c40a372194e9def768cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800565"
---
# <span data-ttu-id="a19de-103">如何使用 App-V 5.1 Management Console 建立自訂設定檔案</span><span class="sxs-lookup"><span data-stu-id="a19de-103">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>


<span data-ttu-id="a19de-104">您可以使用動態設定來自訂特定使用者的 app-v 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="a19de-104">You can use a dynamic configuration to customize an App-V 5.1 package for a specific user.</span></span> <span data-ttu-id="a19de-105">不過，您必須先建立動態使用者配置（.xml）檔案或動態部署設定檔，才能使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a19de-105">However, you must first create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use the files.</span></span> <span data-ttu-id="a19de-106">建立檔案是一個高級的手動操作。</span><span class="sxs-lookup"><span data-stu-id="a19de-106">Creation of the file is an advanced manual operation.</span></span> <span data-ttu-id="a19de-107">如需有關動態使用者設定檔的一般資訊，請參閱[關於 app-v 5.1 動態](about-app-v-51-dynamic-configuration.md)設定。</span><span class="sxs-lookup"><span data-stu-id="a19de-107">For general information about dynamic user configuration files, see, [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md).</span></span>

<span data-ttu-id="a19de-108">使用下列程式來建立使用 App-v 5.1 管理主控台的動態使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="a19de-108">Use the following procedure to create a Dynamic User Configuration file by using the App-V 5.1 Management console.</span></span>

**<span data-ttu-id="a19de-109">建立動態使用者設定檔</span><span class="sxs-lookup"><span data-stu-id="a19de-109">To create a Dynamic User Configuration file</span></span>**

1.  <span data-ttu-id="a19de-110">以滑鼠右鍵按一下您想要查看之套件的名稱，然後選取 [**編輯 active directory 存取**]，以查看指派給特定使用者群組的配置。</span><span class="sxs-lookup"><span data-stu-id="a19de-110">Right-click the name of the package that you want to view and select **Edit active directory access** to view the configuration that is assigned to a given user group.</span></span> <span data-ttu-id="a19de-111">或者，選取套件，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a19de-111">Alternatively, select the package, and click **Edit**.</span></span>

2.  <span data-ttu-id="a19de-112">在**Ad 實體**清單中使用 Access，選取您要自訂的廣告群組。</span><span class="sxs-lookup"><span data-stu-id="a19de-112">Using the list of **AD Entities with Access**, select the AD group that you want to customize.</span></span> <span data-ttu-id="a19de-113">從下拉式清單中選取 [**自訂**] （如果尚未選取）。</span><span class="sxs-lookup"><span data-stu-id="a19de-113">Select **Custom** from the drop-down list, if it is not already selected.</span></span> <span data-ttu-id="a19de-114">隨即會顯示名為 [**編輯**] 的連結。</span><span class="sxs-lookup"><span data-stu-id="a19de-114">A link named **Edit** will be displayed.</span></span>

3.  <span data-ttu-id="a19de-115">按一下**編輯**。</span><span class="sxs-lookup"><span data-stu-id="a19de-115">Click **Edit**.</span></span> <span data-ttu-id="a19de-116">隨即會顯示已指派給 AD 群組的動態使用者設定。</span><span class="sxs-lookup"><span data-stu-id="a19de-116">The Dynamic User Configuration that is assigned to the AD Group will be displayed.</span></span>

4.  <span data-ttu-id="a19de-117">按一下 [**高級**]，然後按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="a19de-117">Click **Advanced**, and then click **Export Configuration**.</span></span> <span data-ttu-id="a19de-118">輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a19de-118">Type in a filename and click **Save**.</span></span> <span data-ttu-id="a19de-119">現在，您可以編輯檔案，為使用者設定套件。</span><span class="sxs-lookup"><span data-stu-id="a19de-119">Now you can edit the file to configure a package for a user.</span></span>

    **<span data-ttu-id="a19de-120">注意</span><span class="sxs-lookup"><span data-stu-id="a19de-120">Note</span></span>**  
    <span data-ttu-id="a19de-121">若要在 Windows Server 上執行時匯出配置，您必須停用「IE 增強的安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="a19de-121">To export a configuration while running on Windows Server, you must disable "IE Enhanced Security Configuration".</span></span> <span data-ttu-id="a19de-122">如果啟用此選項並將其設為 [封鎖下載]，您就無法從 App-v Server 下載任何內容。</span><span class="sxs-lookup"><span data-stu-id="a19de-122">If this is enabled and set to block downloads, you cannot download anything from the App-V Server.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="a19de-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="a19de-123">Related topics</span></span>


[<span data-ttu-id="a19de-124">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="a19de-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









