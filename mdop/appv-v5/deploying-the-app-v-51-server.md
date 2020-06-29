---
title: 部署 App-V 5.1 伺服器
description: 部署 App-V 5.1 伺服器
author: dansimp
ms.assetid: 987b61dc-00d6-49ba-8f1b-92d7b948e702
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bcff2a3211ea3e2f666aff1d6f2ad919509aa3a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800625"
---
# <span data-ttu-id="ed1fc-103">部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="ed1fc-103">Deploying the App-V 5.1 Server</span></span>

<span data-ttu-id="ed1fc-104">您可以使用本主題中所述的不同部署配置來安裝 Microsoft Application Virtualization （App-v）5.1 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-104">You can install the Microsoft Application Virtualization (App-V) 5.1 server features by using different deployment configurations, which described in this topic.</span></span> <span data-ttu-id="ed1fc-105">在您安裝伺服器功能前，請先參閱[app-v 5.1 安全性考慮](app-v-51-security-considerations.md)的伺服器區段。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-105">Before you install the server features, review the server section of [App-V 5.1 Security Considerations](app-v-51-security-considerations.md).</span></span>

<span data-ttu-id="ed1fc-106">如需有關部署 App-v Server 的資訊，請參閱[關於 app-v 5.1](about-app-v-51.md#bkmk-migrate-to-51)。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-106">For information about deploying the App-V Server, see [About App-V 5.1](about-app-v-51.md#bkmk-migrate-to-51).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed1fc-107">在您安裝並設定 App-v 5.1 伺服器之前，您必須指定將託管每個元件的埠。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-107">Before you install and configure the App-V 5.1 servers, you must specify a port where each component will be hosted.</span></span> <span data-ttu-id="ed1fc-108">您也必須新增相關聯的防火牆規則，以允許傳入要求存取指定的埠。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-108">You must also add the associated firewall rules to allow incoming requests to access the specified ports.</span></span> <span data-ttu-id="ed1fc-109">安裝程式不會修改防火牆設定。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-109">The installer does not modify firewall settings.</span></span>

## <a href="" id="---------app-v-5-1-server-overview"></a> <span data-ttu-id="ed1fc-110">App-V 5.1 伺服器概述</span><span class="sxs-lookup"><span data-stu-id="ed1fc-110">App-V 5.1 Server overview</span></span>

<span data-ttu-id="ed1fc-111">App-v 5.1 Server 是由五個元件所組成。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-111">The App-V 5.1 Server is made up of five components.</span></span> <span data-ttu-id="ed1fc-112">每個元件在 App-v 5.1 環境中都有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-112">Each component serves a different purpose within the App-V 5.1 environment.</span></span> <span data-ttu-id="ed1fc-113">這裡簡要說明五個元件中的每一個：</span><span class="sxs-lookup"><span data-stu-id="ed1fc-113">Each of the five components is briefly described here:</span></span>

- <span data-ttu-id="ed1fc-114">管理伺服器-提供 App-V 5.1 基礎結構的整體管理功能。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-114">Management Server – provides overall management functionality for the App-V 5.1 infrastructure.</span></span>
- <span data-ttu-id="ed1fc-115">管理資料庫–可協助 App-v 5.1 管理的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-115">Management Database – facilitates database predeployments for App-V 5.1 management.</span></span>
- <span data-ttu-id="ed1fc-116">發佈伺服器-提供虛擬應用程式的託管與流式處理功能。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-116">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>
- <span data-ttu-id="ed1fc-117">報表伺服器–提供 App-v 5.1 reporting services。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-117">Reporting Server – provides App-V 5.1 reporting services.</span></span>
- <span data-ttu-id="ed1fc-118">報告資料庫–協助 App-v 5.1 報告的資料庫 predeployments。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-118">Reporting Database – facilitates database predeployments for App-V 5.1 reporting.</span></span>

## <a href="" id="---------app-v-5-1-stand-alone-deployment"></a> <span data-ttu-id="ed1fc-119">App-v 5.1 獨立部署</span><span class="sxs-lookup"><span data-stu-id="ed1fc-119">App-V 5.1 stand-alone deployment</span></span>

<span data-ttu-id="ed1fc-120">App-v 5.1 獨立部署可為小型部署或測試環境提供良好的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-120">The App-V 5.1 standalone deployment provides a good topology for a small deployment or a test environment.</span></span> <span data-ttu-id="ed1fc-121">當您使用這種類型的實現時，所有伺服器元件都會部署到單台電腦上。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-121">When you use this type of implementation, all server components are deployed to a single computer.</span></span> <span data-ttu-id="ed1fc-122">服務與相關聯的資料庫會爭用執行 App-v 5.1 元件之電腦上的資源。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-122">The services and associated databases will compete for the resources on the computer that runs the App-V 5.1 components.</span></span> <span data-ttu-id="ed1fc-123">因此，您不應該將這個拓朴用於較大型的部署。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-123">Therefore, you should not use this topology for larger deployments.</span></span>

[<span data-ttu-id="ed1fc-124">如何部署 App-V 5.1 Server</span><span class="sxs-lookup"><span data-stu-id="ed1fc-124">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)

[<span data-ttu-id="ed1fc-125">如何使用指令碼來部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="ed1fc-125">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

## <a href="" id="---------app-v-5-1-server-distributed-deployment"></a> <span data-ttu-id="ed1fc-126">App-V 5.1 伺服器分散式部署</span><span class="sxs-lookup"><span data-stu-id="ed1fc-126">App-V 5.1 Server distributed deployment</span></span>

<span data-ttu-id="ed1fc-127">分散式部署拓撲可支援大型 App-v 5.1 用戶端基礎，並可讓您更輕鬆地管理和縮放您的環境。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-127">The distributed deployment topology can support a large App-V 5.1 client base and it allows you to more easily manage and scale your environment.</span></span> <span data-ttu-id="ed1fc-128">當您使用這種類型的部署時，App-V 5.1 伺服器元件會根據組織的結構與需求，在多部電腦上部署。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-128">When you use this type of deployment, the App-V 5.1 Server components are deployed across multiple computers, based on the structure and requirements of the organization.</span></span>

[<span data-ttu-id="ed1fc-129">如何在與管理和報告服務不同的電腦上安裝管理和報告資料庫</span><span class="sxs-lookup"><span data-stu-id="ed1fc-129">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[<span data-ttu-id="ed1fc-130">如何在獨立電腦上安裝 Management Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="ed1fc-130">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

[<span data-ttu-id="ed1fc-131">如何使用指令碼來部署 App-V 5.1 伺服器</span><span class="sxs-lookup"><span data-stu-id="ed1fc-131">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

[<span data-ttu-id="ed1fc-132">如何在遠端電腦上安裝發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="ed1fc-132">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[<span data-ttu-id="ed1fc-133">如何在獨立電腦上安裝 Management Server 並將它連線到資料庫</span><span class="sxs-lookup"><span data-stu-id="ed1fc-133">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

## <span data-ttu-id="ed1fc-134">使用企業軟體發佈（ESD）解決方案和 App-v 5。1</span><span class="sxs-lookup"><span data-stu-id="ed1fc-134">Using an Enterprise Software Distribution (ESD) solution and App-V 5.1</span></span>

<span data-ttu-id="ed1fc-135">您也可以使用 ESD 來部署 app-v 5.1 用戶端和套件，而不需部署 App-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-135">You can also deploy the App-V 5.1 clients and packages by using an ESD without having to deploy App-V 5.1.</span></span> <span data-ttu-id="ed1fc-136">整合的完整功能會視您所使用的 ESD 而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-136">The full capabilities for integration will vary depending on the ESD that you use.</span></span>

> [!NOTE]
> <span data-ttu-id="ed1fc-137">App-V 5.1 報表服務器與報告資料庫仍可在 ESD 中部署，以從 App-v 5.1 用戶端收集報告資料。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-137">The App-V 5.1 reporting server and reporting database can still be deployed alongside the ESD to collect the reporting data from the App-V 5.1 clients.</span></span> <span data-ttu-id="ed1fc-138">不過，不應該部署其他三個伺服器元件，因為它們會與 ESD 功能發生衝突。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-138">However, the other three server components should not be deployed, because they will conflict with the ESD functionality.</span></span>

[<span data-ttu-id="ed1fc-139">使用電子軟體發佈 (ESD) 來部署 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="ed1fc-139">Deploying App-V 5.1 Packages by Using Electronic Software Distribution (ESD)</span></span>](deploying-app-v-51-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-1-server-logs"></a> <span data-ttu-id="ed1fc-140">App-v 5.1 Server 記錄</span><span class="sxs-lookup"><span data-stu-id="ed1fc-140">App-V 5.1 Server logs</span></span>

<span data-ttu-id="ed1fc-141">您可以使用 app-v 5.1 server 記錄資訊，協助您在使用 App-v 5.1 時，對伺服器安裝與操作事件進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-141">You can use App-V 5.1 server log information to help troubleshoot the server installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="ed1fc-142">伺服器相關記錄資訊可以使用**事件檢視器**進行檢查。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-142">The server-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="ed1fc-143">下一行顯示與伺服器相關事件的特定路徑：</span><span class="sxs-lookup"><span data-stu-id="ed1fc-143">The following line displays the specific path for Server-related events:</span></span>

**<span data-ttu-id="ed1fc-144">事件檢視器 \\ 應用程式和服務記錄 \\ Microsoft \\ App V</span><span class="sxs-lookup"><span data-stu-id="ed1fc-144">Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V</span></span>**

<span data-ttu-id="ed1fc-145">關聯的安裝記錄會儲存在下列目錄中：</span><span class="sxs-lookup"><span data-stu-id="ed1fc-145">Associated setup logs are saved in the following directory:</span></span>

**<span data-ttu-id="ed1fc-146">temp</span><span class="sxs-lookup"><span data-stu-id="ed1fc-146">%temp%</span></span>**

<span data-ttu-id="ed1fc-147">在 App-v 5.0 SP3 中，已整合並移動一些記錄。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-147">In App-V 5.0 SP3, some logs were consolidated and moved.</span></span> <span data-ttu-id="ed1fc-148">請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-148">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

## <a href="" id="---------app-v-5-1-reporting"></a> <span data-ttu-id="ed1fc-149">App-V 5.1 報告</span><span class="sxs-lookup"><span data-stu-id="ed1fc-149">App-V 5.1 reporting</span></span>

<span data-ttu-id="ed1fc-150">App-v 5.1 報告可讓 App-v 5.1 用戶端收集資料，然後再將資料傳送回儲存在中央儲存庫中。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-150">App-V 5.1 reporting allows App-V 5.1 clients to collect data and then send it back to be stored in a central repository.</span></span> <span data-ttu-id="ed1fc-151">您可以使用這項資訊，更清楚地瞭解貴組織內的虛擬應用程式使用量。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-151">You can use this information to get a better view of the virtual application usage within your organization.</span></span> <span data-ttu-id="ed1fc-152">下列清單顯示 App-v 5.1 用戶端所收集的一些資訊類型：</span><span class="sxs-lookup"><span data-stu-id="ed1fc-152">The following list displays some of the types of information the App-V 5.1 client collects:</span></span>

- <span data-ttu-id="ed1fc-153">有關執行 App-v 5.1 用戶端的電腦資訊。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-153">Information about the computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="ed1fc-154">在執行 App-v 5.1 用戶端之特定電腦上的虛擬化套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-154">Information about virtualized packages on a specific computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="ed1fc-155">針對特定使用者開啟和關閉套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-155">Information about package open and shutdown for a specific user.</span></span>

<span data-ttu-id="ed1fc-156">報告資訊將會保留，直到成功傳送到報表伺服器資料庫為止。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-156">The reporting information will be maintained until it is successfully sent to the reporting server database.</span></span> <span data-ttu-id="ed1fc-157">在資料庫中資料之後，您就可以使用 Microsoft SQL Server Reporting Services 來產生任何必要的報告。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-157">After the data is in the database, you can use Microsoft SQL Server Reporting Services to generate any necessary reports.</span></span>

<span data-ttu-id="ed1fc-158">如果您想要檢索報表資訊，您必須使用 Microsoft sql Server Reporting Services （SSRS），這可與 Microsoft SQL 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-158">If you want to retrieve report information, you must use Microsoft SQL Server Reporting Services (SSRS) which is available with Microsoft SQL.</span></span> <span data-ttu-id="ed1fc-159">當您安裝應用程式 V 5.1 報表伺服器且必須單獨部署它才能產生相關聯的報表時，就不會安裝 SSRS。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-159">SSRS is not installed when you install the App-V 5.1 reporting server and it must be deployed separately to generate the associated reports.</span></span>

<span data-ttu-id="ed1fc-160">如需[app-v 5.1 報告](about-app-v-51-reporting.md)的詳細資訊，請使用下列連結。</span><span class="sxs-lookup"><span data-stu-id="ed1fc-160">Use the following link for more information [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

[<span data-ttu-id="ed1fc-161">如何使用 PowerShell 在 App-V 5.1 用戶端上啟用報表</span><span class="sxs-lookup"><span data-stu-id="ed1fc-161">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)

## <span data-ttu-id="ed1fc-162">App-V 伺服器的其他資源</span><span class="sxs-lookup"><span data-stu-id="ed1fc-162">Other resources for the App-V server</span></span>

[<span data-ttu-id="ed1fc-163">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="ed1fc-163">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
