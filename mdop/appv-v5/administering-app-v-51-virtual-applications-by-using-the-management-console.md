---
title: 使用 Management Console 管理 App-V 5.1 虛擬應用程式
description: 使用 Management Console 管理 App-V 5.1 虛擬應用程式
author: dansimp
ms.assetid: a4d078aa-ec54-4fa4-9463-bfb3b971d724
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63ec965519bedef08b09c961dc5d1c90e1d8d694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800700"
---
# <span data-ttu-id="62394-103">使用 Management Console 管理 App-V 5.1 虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="62394-103">Administering App-V 5.1 Virtual Applications by Using the Management Console</span></span>


<span data-ttu-id="62394-104">在您的環境中使用 Microsoft Application Virtualization （App-v）5.1 管理伺服器來管理套件、連線群組和套件存取。</span><span class="sxs-lookup"><span data-stu-id="62394-104">Use the Microsoft Application Virtualization (App-V) 5.1 management server to manage packages, connection groups, and package access in your environment.</span></span> <span data-ttu-id="62394-105">伺服器會將應用程式圖示、快速鍵及檔案類型關聯發佈到執行 App-v 5.1 用戶端的已授權電腦。</span><span class="sxs-lookup"><span data-stu-id="62394-105">The server publishes application icons, shortcuts, and file type associations to authorized computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="62394-106">一或多個管理伺服器通常會共用通用資料存放區，以取得設定和封裝資訊。</span><span class="sxs-lookup"><span data-stu-id="62394-106">One or more management servers typically share a common data store for configuration and package information.</span></span>

<span data-ttu-id="62394-107">管理伺服器使用 Active Directory 網域服務（AD DS）群組來管理使用者授權，並安裝 SQL Server 來管理資料庫和資料存放區。</span><span class="sxs-lookup"><span data-stu-id="62394-107">The management server uses Active Directory Domain Services (AD DS) groups to manage user authorization and has SQL Server installed to manage the database and data store.</span></span>

<span data-ttu-id="62394-108">由於管理伺服器會根據需求將應用程式流式處理至使用者，因此這些伺服器非常適合擁有可靠、高頻寬局域網的系統組態。</span><span class="sxs-lookup"><span data-stu-id="62394-108">Because the management servers stream applications to end users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span> <span data-ttu-id="62394-109">管理伺服器包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="62394-109">The management server consists of the following components:</span></span>

-   <span data-ttu-id="62394-110">管理伺服器–使用管理伺服器來管理套件和連線群組。</span><span class="sxs-lookup"><span data-stu-id="62394-110">Management Server – Use the management server to manage packages and connection groups.</span></span>

-   <span data-ttu-id="62394-111">發佈伺服器–使用發佈伺服器將套件部署到執行 App-v 5.1 用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="62394-111">Publishing Server – Use the publishing server to deploy packages to computers that run the App-V 5.1 client.</span></span>

-   <span data-ttu-id="62394-112">管理資料庫-使用管理資料庫來管理套件存取，併發布伺服器與管理伺服器的同步處理。</span><span class="sxs-lookup"><span data-stu-id="62394-112">Management Database - Use the management database to manage the package access and to publish the server’s synchronization with the management server.</span></span>

## <span data-ttu-id="62394-113">管理主控台任務</span><span class="sxs-lookup"><span data-stu-id="62394-113">Management Console tasks</span></span>


<span data-ttu-id="62394-114">您可以使用 App-v 5.1 管理主控台執行的最常見工作包括：</span><span class="sxs-lookup"><span data-stu-id="62394-114">The most common tasks that you can perform with the App-V 5.1 Management console are:</span></span>

-   [<span data-ttu-id="62394-115">如何連線到 Management Console</span><span class="sxs-lookup"><span data-stu-id="62394-115">How to Connect to the Management Console</span></span>](how-to-connect-to-the-management-console-51.md)

-   [<span data-ttu-id="62394-116">如何使用 Management Console 新增或升級套件</span><span class="sxs-lookup"><span data-stu-id="62394-116">How to Add or Upgrade Packages by Using the Management Console</span></span>](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)

-   [<span data-ttu-id="62394-117">如何使用 Management Console 設定對套件的存取權</span><span class="sxs-lookup"><span data-stu-id="62394-117">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

-   [<span data-ttu-id="62394-118">如何使用 Management Console 發佈套件</span><span class="sxs-lookup"><span data-stu-id="62394-118">How to Publish a Package by Using the Management Console</span></span>](how-to-publish-a-package-by-using-the-management-console-51.md)

-   [<span data-ttu-id="62394-119">如何在 Management Console 中刪除套件</span><span class="sxs-lookup"><span data-stu-id="62394-119">How to Delete a Package in the Management Console</span></span>](how-to-delete-a-package-in-the-management-console-51.md)

-   [<span data-ttu-id="62394-120">如何使用 Management Console 新增或移除系統管理員</span><span class="sxs-lookup"><span data-stu-id="62394-120">How to Add or Remove an Administrator by Using the Management Console</span></span>](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)

-   [<span data-ttu-id="62394-121">如何使用 Management Console 註冊及取消註冊發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="62394-121">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console51.md)

-   [<span data-ttu-id="62394-122">如何使用 App-V 5.1 Management Console 建立自訂設定檔案</span><span class="sxs-lookup"><span data-stu-id="62394-122">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)

-   [<span data-ttu-id="62394-123">如何使用 Management Console 將存取權與設定傳輸到另一個套件版本</span><span class="sxs-lookup"><span data-stu-id="62394-123">How to Transfer Access and Configurations to Another Version of a Package by Using the Management Console</span></span>](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console51.md)

-   [<span data-ttu-id="62394-124">如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組</span><span class="sxs-lookup"><span data-stu-id="62394-124">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console51.md)

-   [<span data-ttu-id="62394-125">如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組</span><span class="sxs-lookup"><span data-stu-id="62394-125">How to View and Configure Applications and Default Virtual Application Extensions by Using the Management Console</span></span>](how-to-view-and-configure-applications-and-default-virtual-application-extensions-by-using-the-management-console-beta.md)

<span data-ttu-id="62394-126">App-v 5.1 管理主控台的主要元素包括：</span><span class="sxs-lookup"><span data-stu-id="62394-126">The main elements of the App-V 5.1 Management Console are:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="62394-127">管理 [主控台] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="62394-127">Management Console tab</span></span></th>
<th align="left"><span data-ttu-id="62394-128">描述</span><span class="sxs-lookup"><span data-stu-id="62394-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62394-129">[套件] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="62394-129">Packages tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="62394-130">使用 [ <strong> 套件] 索引標籤 </strong> 來新增或升級套件。</span><span class="sxs-lookup"><span data-stu-id="62394-130">Use the <strong>PACKAGES</strong> tab to add or upgrade packages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62394-131">[連線群組] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="62394-131">Connection Groups tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="62394-132">使用 [ <strong> 連接群組] 索引標籤 </strong> 來管理連線群組。</span><span class="sxs-lookup"><span data-stu-id="62394-132">Use the <strong>CONNECTION GROUPS</strong> tab to manage connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="62394-133">[伺服器] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="62394-133">Servers tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="62394-134">使用 [ <strong> 伺服器] 索引標籤 </strong> 來註冊新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="62394-134">Use the <strong>SERVERS</strong> tab to register a new server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="62394-135">[管理員] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="62394-135">Administrators tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="62394-136">使用 [ <strong> 管理員] 索引標籤 </strong> 來註冊、新增或移除 app-v 5.1 環境中的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="62394-136">Use the <strong>ADMINISTRATORS</strong> tab to register, add, or remove administrators in your App-V 5.1 environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="62394-137">**重要** 您必須在開啟 Web 管理主控台的瀏覽器上啟用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="62394-137">**Important** JavaScript must be enabled on the browser that opens the Web Management Console.</span></span>

 






## <a href="" id="other-resources-for-this-app-v-5-1-deployment-"></a><span data-ttu-id="62394-138">此 App-v 5.1 部署的其他資源</span><span class="sxs-lookup"><span data-stu-id="62394-138">Other resources for this App-V 5.1 deployment</span></span>


-   [<span data-ttu-id="62394-139">Microsoft Application Virtualization 5.1 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="62394-139">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="62394-140">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="62394-140">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





