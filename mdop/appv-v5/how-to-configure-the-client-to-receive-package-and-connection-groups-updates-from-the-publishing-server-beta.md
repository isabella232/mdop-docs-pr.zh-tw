---
title: 如何設定用戶端以從發佈伺服器接收套件與連線群組更新
description: 如何設定用戶端以從發佈伺服器接收套件與連線群組更新
author: dansimp
ms.assetid: f5dfd96d-4b63-468c-8d93-9dfdf47c28fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e9df1f8b324430449d8d1dd3624d9f1157968a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800581"
---
# <span data-ttu-id="b42e1-103">如何設定用戶端以從發佈伺服器接收套件與連線群組更新</span><span class="sxs-lookup"><span data-stu-id="b42e1-103">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>


<span data-ttu-id="b42e1-104">使用 App-v 5.0 發佈伺服器部署套件和連線群組非常有用，因為它提供單一點管理和高伸縮性。</span><span class="sxs-lookup"><span data-stu-id="b42e1-104">Deploying packages and connection groups using the App-V 5.0 publishing server is helpful because it offers single-point management and high scalability.</span></span>

<span data-ttu-id="b42e1-105">使用下列步驟，將 App-v 5.0 用戶端設定為從發佈伺服器接收更新。</span><span class="sxs-lookup"><span data-stu-id="b42e1-105">Use the following steps to configure the App-V 5.0 client to receive updates from the publishing server.</span></span>

<span data-ttu-id="b42e1-106">**記事** 針對下列程式，管理伺服器已安裝在名為**MyMgmtSrv**的電腦上，且發佈伺服器已安裝在名為**MyPubSrv**的電腦上。</span><span class="sxs-lookup"><span data-stu-id="b42e1-106">**Note** For the following procedures the management server was installed on a computer named **MyMgmtSrv**, and the publishing server was installed on a computer named **MyPubSrv**.</span></span>

 

**<span data-ttu-id="b42e1-107">若要將 App-v 5.0 用戶端設定為從發佈伺服器接收更新</span><span class="sxs-lookup"><span data-stu-id="b42e1-107">To configure the App-V 5.0 client to receive updates from the publishing server</span></span>**

1.  <span data-ttu-id="b42e1-108">部署 app-v 5.0 管理與發佈伺服器，並新增必要的套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="b42e1-108">Deploy the App-V 5.0 management and publishing servers, and add the required packages and connection groups.</span></span> <span data-ttu-id="b42e1-109">如需新增套件和連線群組的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)，以及[如何建立連線群組](how-to-create-a-connection-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b42e1-109">For more information about adding packages and connection groups, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md) and [How to Create a Connection Group](how-to-create-a-connection-group.md).</span></span>

2.  <span data-ttu-id="b42e1-110">若要開啟管理主控台，請按一下下列連結，開啟瀏覽器，並輸入以下內容： http://MyMgmtSrv/AppvManagement/Console.html 在網頁瀏覽器中，然後匯入、發佈及 entitle 特定使用者組所需的所有套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="b42e1-110">To open the management console click the following link, open a browser and type the following: http://MyMgmtSrv/AppvManagement/Console.html in a web browser, and import, publish, and entitle all the packages and connection groups which will be necessary for a particular set of users.</span></span>

3.  <span data-ttu-id="b42e1-111">在執行 App-v 5.0 用戶端的電腦上，開啟提升許可權的 PowerShell 命令提示字元，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b42e1-111">On the computer running the App-V 5.0 client, open an elevated PowerShell command prompt, run the following command:</span></span>

    **<span data-ttu-id="b42e1-112">AppvPublishingServer-Name ABC-URL HTTP://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="b42e1-112">Add-AppvPublishingServer -Name ABC -URL http:// MyPubSrv/AppvPublishing</span></span>**

    <span data-ttu-id="b42e1-113">這個命令會設定指定的發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="b42e1-113">This command will configure the specified publishing server.</span></span> <span data-ttu-id="b42e1-114">您應該會看到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="b42e1-114">You should see output similar to the following:</span></span>

    <span data-ttu-id="b42e1-115">Id：1</span><span class="sxs-lookup"><span data-stu-id="b42e1-115">Id : 1</span></span>

    <span data-ttu-id="b42e1-116">SetByGroupPolicy： False</span><span class="sxs-lookup"><span data-stu-id="b42e1-116">SetByGroupPolicy : False</span></span>

    <span data-ttu-id="b42e1-117">名稱： ABC</span><span class="sxs-lookup"><span data-stu-id="b42e1-117">Name : ABC</span></span>

    <span data-ttu-id="b42e1-118">URL： HTTP://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="b42e1-118">URL : http:// MyPubSrv/AppvPublishing</span></span>

    <span data-ttu-id="b42e1-119">GlobalRefreshEnabled： False</span><span class="sxs-lookup"><span data-stu-id="b42e1-119">GlobalRefreshEnabled : False</span></span>

    <span data-ttu-id="b42e1-120">GlobalRefreshOnLogon： False</span><span class="sxs-lookup"><span data-stu-id="b42e1-120">GlobalRefreshOnLogon : False</span></span>

    <span data-ttu-id="b42e1-121">GlobalRefreshInterval：0</span><span class="sxs-lookup"><span data-stu-id="b42e1-121">GlobalRefreshInterval : 0</span></span>

    <span data-ttu-id="b42e1-122">GlobalRefreshIntervalUnit： Day</span><span class="sxs-lookup"><span data-stu-id="b42e1-122">GlobalRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="b42e1-123">UserRefreshEnabled： True</span><span class="sxs-lookup"><span data-stu-id="b42e1-123">UserRefreshEnabled : True</span></span>

    <span data-ttu-id="b42e1-124">UserRefreshOnLogon： True</span><span class="sxs-lookup"><span data-stu-id="b42e1-124">UserRefreshOnLogon : True</span></span>

    <span data-ttu-id="b42e1-125">UserRefreshInterval：0</span><span class="sxs-lookup"><span data-stu-id="b42e1-125">UserRefreshInterval : 0</span></span>

    <span data-ttu-id="b42e1-126">UserRefreshIntervalUnit： Day</span><span class="sxs-lookup"><span data-stu-id="b42e1-126">UserRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="b42e1-127">傳回的識別碼（在此例中為1）</span><span class="sxs-lookup"><span data-stu-id="b42e1-127">The returned Id – in this case 1</span></span>

4.  <span data-ttu-id="b42e1-128">在執行 App-V 5.0 用戶端的電腦上，開啟 PowerShell 命令提示字元，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b42e1-128">On the computer running the App-V 5.0 client, open a PowerShell command prompt, and type the following command:</span></span>

    **<span data-ttu-id="b42e1-129">同步處理-AppvPublishingServer-ServerId 1</span><span class="sxs-lookup"><span data-stu-id="b42e1-129">Sync-AppvPublishingServer -ServerId 1</span></span>**

    <span data-ttu-id="b42e1-130">根據管理伺服器上設定的套件和連線群組的權利，該命令會針對您需要針對此特定用戶端新增或移除之套件與連接群組的發佈伺服器進行查詢。</span><span class="sxs-lookup"><span data-stu-id="b42e1-130">The command will query the publishing server for the packages and connection groups that need to be added or removed for this particular client based on the entitlements for the packages and connection groups as configured on the management server.</span></span>

    <span data-ttu-id="b42e1-131">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="b42e1-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b42e1-132">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b42e1-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b42e1-133">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="b42e1-133">Got an App-V issue?</span></span>** <span data-ttu-id="b42e1-134">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="b42e1-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b42e1-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="b42e1-135">Related topics</span></span>


[<span data-ttu-id="b42e1-136">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="b42e1-136">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





