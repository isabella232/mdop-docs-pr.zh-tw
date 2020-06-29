---
title: App-V 後續安裝檢查清單
description: App-V 後續安裝檢查清單
author: dansimp
ms.assetid: 74db297e-a744-4287-bcc6-0e096ca8b57a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79728bd2043076b20eb37ba0b1fa6f834a0d94bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802362"
---
# <span data-ttu-id="b30d4-103">App-V 後續安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="b30d4-103">App-V Postinstallation Checklist</span></span>


<span data-ttu-id="b30d4-104">下列檢查清單提供在您完成 Microsoft Application Virtualization （App-v）管理伺服器、App-v 流式處理伺服器和 App-v Desktop 用戶端的安裝後，要考慮的事項，以及概述您應該採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="b30d4-104">The following checklist provides a high-level list of items to consider and outlines the steps you should take after you have completed the installation of the Microsoft Application Virtualization (App-V) Management Server, App-V Streaming Server, and the App-V Desktop Client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b30d4-105">步驟</span><span class="sxs-lookup"><span data-stu-id="b30d4-105">Step</span></span></th>
<th align="left"><span data-ttu-id="b30d4-106">參考</span><span class="sxs-lookup"><span data-stu-id="b30d4-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b30d4-107">建立 App-v Management Server 或流式處理伺服器服務的防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="b30d4-107">Create firewall exceptions for the App-V Management Server or Streaming Server services.</span></span></p></td>
<td align="left"><p><a href="configuring-the-firewall-for-the-app-v-servers.md" data-raw-source="[Configuring the Firewall for the App-V Servers](configuring-the-firewall-for-the-app-v-servers.md)"><span data-ttu-id="b30d4-108">設定 App-V 伺服器所需的防火牆</span><span class="sxs-lookup"><span data-stu-id="b30d4-108">Configuring the Firewall for the App-V Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b30d4-109">透過發佈、流式處理及測試預設的應用程式，驗證 App-v 系統是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="b30d4-109">Verify that the App-V system is functioning correctly by publishing, streaming, and testing the default application.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-the-default-application.md" data-raw-source="[How to Install and Configure the Default Application](how-to-install-and-configure-the-default-application.md)"><span data-ttu-id="b30d4-110">如何安裝和設定 Default Application</span><span class="sxs-lookup"><span data-stu-id="b30d4-110">How to Install and Configure the Default Application</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b30d4-111">針對 <strong> ApplicationSourceRoot </strong> 、 <strong> IconSourceRoot </strong> 和 <strong> OSDSourceRoot </strong> 設定，將 app v 用戶端設定為使用 app-v 流式處理伺服器或其他可進行流式處理的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b30d4-111">Configure the App-V Client to use the App-V Streaming Server or other server for streaming by means of the <strong>ApplicationSourceRoot</strong>, <strong>IconSourceRoot</strong>, and <strong>OSDSourceRoot</strong> settings.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-client-for-application-package-retrieval.md" data-raw-source="[How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md)"><span data-ttu-id="b30d4-112">如何設定應用程式封裝擷取的用戶端</span><span class="sxs-lookup"><span data-stu-id="b30d4-112">How to Configure the Client for Application Package Retrieval</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b30d4-113">瞭解如何使用已排序之應用程式套件的 .msi 檔案版本來進行離線部署。</span><span class="sxs-lookup"><span data-stu-id="b30d4-113">Understand how to use the .msi file version of sequenced application packages for offline deployment.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-virtual-application-on-the-client.md" data-raw-source="[How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md)"><span data-ttu-id="b30d4-114">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="b30d4-114">How to Publish a Virtual Application on the Client</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b30d4-115">可選針對應用程式 V 資料庫設定 SQL Server 資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="b30d4-115">(Optional) Configure SQL Server database mirroring for the App-V database.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md" data-raw-source="[How to Configure Microsoft SQL Server Mirroring Support for App-V](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)"><span data-ttu-id="b30d4-116">如何為 App-V 設定 Microsoft SQL Server 鏡像支援</span><span class="sxs-lookup"><span data-stu-id="b30d4-116">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b30d4-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="b30d4-117">Related topics</span></span>


[<span data-ttu-id="b30d4-118">Application Virtualization 部署與升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="b30d4-118">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





