---
title: App-V 5.1 入門
description: App-V 5.1 入門
author: dansimp
ms.assetid: 49a20e1f-0566-4e53-a417-1521393fc974
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff10f12bc672a24f2837f50bfb1f0033ede3e46f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800621"
---
# <span data-ttu-id="bd4b7-103">App-V 5.1 入門</span><span class="sxs-lookup"><span data-stu-id="bd4b7-103">Getting Started with App-V 5.1</span></span>


<span data-ttu-id="bd4b7-104">Microsoft 應用程式虛擬化（App-v）5.1 可讓系統管理員根據需要在即時部署、更新及支援應用程式。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-104">Microsoft Application Virtualization (App-V) 5.1 enables administrators to deploy, update, and support applications as services in real time, on an as-needed basis.</span></span> <span data-ttu-id="bd4b7-105">個別的應用程式是從本機安裝的產品轉換成集中管理的服務，且無論您在哪裡，都能隨時隨地存取，而不需要預先設定電腦或變更作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-105">Individual applications are transformed from locally installed products into centrally managed services and are available wherever you need, without the need to preconfigure computers or to change operating system settings.</span></span>

<span data-ttu-id="bd4b7-106">App-v 包含下列元素：</span><span class="sxs-lookup"><span data-stu-id="bd4b7-106">App-V consists of the following elements:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bd4b7-107">元素</span><span class="sxs-lookup"><span data-stu-id="bd4b7-107">Element</span></span></th>
<th align="left"><span data-ttu-id="bd4b7-108">描述</span><span class="sxs-lookup"><span data-stu-id="bd4b7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bd4b7-109">App-v 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="bd4b7-109">App-V Management Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bd4b7-110">提供管理 App-v 基礎結構的中央位置，這會將虛擬應用程式提供給 App-v Desktop 用戶端和遠端桌面服務（舊稱終端服務）用戶端。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-110">Provides a central location for managing the App-V infrastructure, which delivers virtual applications to both the App-V Desktop Client and the Remote Desktop Services (formerly Terminal Services) Client.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-111">針對其資料存放區使用 Microsoft SQL Server®，其中一個或多個 App-v 管理伺服器可以共用單一的 SQL Server 資料存放區。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-111">Uses Microsoft SQL Server® for its data store, where one or more App-V Management servers can share a single SQL Server data store.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-112">驗證要求並提供安全性、測定、監視及資料收集。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-112">Authenticates requests and provides security, metering, monitoring, and data gathering.</span></span> <span data-ttu-id="bd4b7-113">伺服器使用 Active Directory 和支援工具來管理使用者和應用程式。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-113">The server uses Active Directory and supporting tools to manage users and applications.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-114">擁有管理網站，可讓您從任何電腦設定 App-v 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-114">Has a management site that lets you configure the App-V infrastructure from any computer.</span></span> <span data-ttu-id="bd4b7-115">您可以新增及移除應用程式、操縱快速鍵、指派存取權限給使用者和群組，以及建立連線群組。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-115">You can add and remove applications, manipulate shortcuts, assign access permissions to users and groups, and create connection groups.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-116">啟用 App-v Web 管理主控台與 SQL Server 資料存放區之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-116">Enables communication between the App-V Web Management Console and the SQL Server data store.</span></span> <span data-ttu-id="bd4b7-117">這些元件都可以安裝在單一伺服器電腦或一或多個不同的電腦上，視所需的系統架構而定。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-117">These components can all be installed on a single server computer, or on one or more separate computers, depending on the required system architecture.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bd4b7-118">App-v 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="bd4b7-118">App-V Publishing Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bd4b7-119">為特定使用者提供具有資格的應用程式的 App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="bd4b7-119">Provides App-V Clients with entitled applications for the specific user</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-120">承載用於流式處理的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-120">Hosts the virtual application package for streaming.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bd4b7-121">App-v Desktop 用戶端</span><span class="sxs-lookup"><span data-stu-id="bd4b7-121">App-V Desktop Client</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bd4b7-122">檢索虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="bd4b7-122">Retrieves virtual applications</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-123">在用戶端發佈應用程式</span><span class="sxs-lookup"><span data-stu-id="bd4b7-123">Publishes the applications on the clients</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-124">在 Windows 端點上的執行時間自動設定及管理虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-124">Automatically sets up and manages virtual environments at runtime on Windows endpoints.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-125">在每個使用者&#39;s 設定檔中儲存使用者特定的虛擬應用程式設定，例如登錄和檔案變更。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-125">Stores user-specific virtual application settings, such as registry and file changes, in each user&#39;s profile.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bd4b7-126">App-v 遠端桌面服務（RDS）用戶端</span><span class="sxs-lookup"><span data-stu-id="bd4b7-126">App-V Remote Desktop Services (RDS) Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="bd4b7-127">啟用遠端桌面工作階段主機伺服器，以使用 App-v Desktop 用戶端的共用桌面會話功能。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-127">Enables Remote Desktop Session Host servers to use the capabilities of the App-V Desktop Client for shared desktop sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bd4b7-128">App-v 排序器</span><span class="sxs-lookup"><span data-stu-id="bd4b7-128">App-V Sequencer</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="bd4b7-129">是您用來將傳統應用程式轉換成虛擬應用程式的嚮導工具。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-129">Is a wizard-based tool that you use to transform traditional applications into virtual applications.</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-130">產生應用程式 "套件"，其中包含：</span><span class="sxs-lookup"><span data-stu-id="bd4b7-130">Produces the application “package,” which consists of:</span></span></p>
<ol>
<li><p><span data-ttu-id="bd4b7-131">已排序的應用程式（APPV）檔案</span><span class="sxs-lookup"><span data-stu-id="bd4b7-131">a sequenced application (APPV) file</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-132">可部署至針對獨立作業設定之用戶端的 Windows Installer 檔案（MSI）</span><span class="sxs-lookup"><span data-stu-id="bd4b7-132">a Windows Installer file (MSI) that can be deployed to clients configured for stand-alone operation</span></span></p></li>
<li><p><span data-ttu-id="bd4b7-133">幾個 XML 檔案，包括 Report.XML、PackageName_DeploymentConfig.XML 及 PackageName_UserConfig.XML。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-133">Several XML files including Report.XML, PackageName_DeploymentConfig.XML, and PackageName_UserConfig.XML.</span></span> <span data-ttu-id="bd4b7-134">UserConfig 和 DeploymentConfig XML 檔案是用來將自訂變更設定為套件的預設行為。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-134">The UserConfig and DeploymentConfig XML files are used to configure custom changes to the default behavior of the package.</span></span></p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="bd4b7-135">如需這些元素的詳細資訊，請參閱[app-v 5.1 的高層次架構](high-level-architecture-for-app-v-51.md)。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-135">For more information about these elements, see [High Level Architecture for App-V 5.1](high-level-architecture-for-app-v-51.md).</span></span>

<span data-ttu-id="bd4b7-136">如果您是本產品的新使用者，建議您仔細閱讀檔。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-136">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="bd4b7-137">在您將它部署到生產環境之前，我們也建議您在測試網路環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-137">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="bd4b7-138">您也可以考慮參與相關技術的課程。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-138">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="bd4b7-139">如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-139">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="bd4b7-140">**記事** 此系統管理員指南的可下載版本無法使用。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-140">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="bd4b7-141">不過，您可以瞭解 TechNet 文件庫的特殊模式，讓您選取文章、將其群組在集合中，或在 <https://go.microsoft.com/fwlink/?LinkId=272491> （ https://go.microsoft.com/fwlink/?LinkId=272491) 。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-141">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272491> (https://go.microsoft.com/fwlink/?LinkId=272491).</span></span>

 

<span data-ttu-id="bd4b7-142">App-V 5.1 系統管理員指南的本節包含 App-V 5.1 的高層資訊，讓您在開始進行部署規劃之前先對產品有基本的瞭解。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-142">This section of the App-V 5.1 Administrator’s Guide includes high-level information about App-V 5.1 to provide you with a basic understanding of the product before you begin the deployment planning.</span></span>

## <span data-ttu-id="bd4b7-143">App 快速入門-V 5。1</span><span class="sxs-lookup"><span data-stu-id="bd4b7-143">Getting started with App-V 5.1</span></span>


-   [<span data-ttu-id="bd4b7-144">關於 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bd4b7-144">About App-V 5.1</span></span>](about-app-v-51.md)

    <span data-ttu-id="bd4b7-145">提供 App-V 5.1 的高層概覽，以及如何在您的組織中使用它。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-145">Provides a high-level overview of App-V 5.1 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="bd4b7-146">評估 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bd4b7-146">Evaluating App-V 5.1</span></span>](evaluating-app-v-51.md)

    <span data-ttu-id="bd4b7-147">提供關於您在組織中使用 App-v 5.1 的最佳評估方式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-147">Provides information about how you can best evaluate App-V 5.1 for use in your organization.</span></span>

-   [<span data-ttu-id="bd4b7-148">App-V 5.1 的高階架構</span><span class="sxs-lookup"><span data-stu-id="bd4b7-148">High Level Architecture for App-V 5.1</span></span>](high-level-architecture-for-app-v-51.md)

    <span data-ttu-id="bd4b7-149">提供應用程式 V 5.1 功能的說明，以及它們如何共同運作。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-149">Provides a description of the App-V 5.1 features and how they work together.</span></span>

-   [<span data-ttu-id="bd4b7-150">App-V 5.1 的協助工具</span><span class="sxs-lookup"><span data-stu-id="bd4b7-150">Accessibility for App-V 5.1</span></span>](accessibility-for-app-v-51.md)

    <span data-ttu-id="bd4b7-151">提供有關讓殘障人士更容易存取本產品及其對應檔的功能與服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd4b7-151">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="bd4b7-152">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="bd4b7-152">Other resources for this product</span></span>


-   [<span data-ttu-id="bd4b7-153">Microsoft Application Virtualization 5.1 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="bd4b7-153">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="bd4b7-154">為 App-V 5.1 進行規劃</span><span class="sxs-lookup"><span data-stu-id="bd4b7-154">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)

-   [<span data-ttu-id="bd4b7-155">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bd4b7-155">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

-   [<span data-ttu-id="bd4b7-156">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="bd4b7-156">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

-   [<span data-ttu-id="bd4b7-157">疑難排解 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="bd4b7-157">Troubleshooting App-V 5.1</span></span>](troubleshooting-app-v-51.md)

-   [<span data-ttu-id="bd4b7-158">App-V 5.1 技術參考資訊</span><span class="sxs-lookup"><span data-stu-id="bd4b7-158">Technical Reference for App-V 5.1</span></span>](technical-reference-for-app-v-51.md)






 

 





