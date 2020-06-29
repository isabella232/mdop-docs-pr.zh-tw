---
title: App-V 前置安裝檢查清單
description: App-V 前置安裝檢查清單
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802357"
---
# <span data-ttu-id="fa94b-103">App-V 前置安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="fa94b-103">App-V Pre-Installation Checklist</span></span>


<span data-ttu-id="fa94b-104">下列檢查清單是用來提供一個要考慮的高層次專案清單，並簡要說明您在安裝 Microsoft Application Virtualization （App-v）伺服器之前應該採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="fa94b-104">The following checklist is intended to provide a high-level list of items to consider and outlines the steps you should take before you install the Microsoft Application Virtualization (App-V) servers.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fa94b-105">步驟</span><span class="sxs-lookup"><span data-stu-id="fa94b-105">Step</span></span></th>
<th align="left"><span data-ttu-id="fa94b-106">參考</span><span class="sxs-lookup"><span data-stu-id="fa94b-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa94b-107">確保您的計算環境符合 App-v 所需的支援設定。</span><span class="sxs-lookup"><span data-stu-id="fa94b-107">Ensure your computing environment meets the supported configurations required for App-V.</span></span></p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)"><span data-ttu-id="fa94b-108">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="fa94b-108">Application Virtualization Deployment Requirements</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa94b-109">設定必要的 Active Directory 群組和帳戶。</span><span class="sxs-lookup"><span data-stu-id="fa94b-109">Configure the necessary Active Directory groups and accounts.</span></span></p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)"><span data-ttu-id="fa94b-110">在 Active Directory 中設定 App-V 的必要群組</span><span class="sxs-lookup"><span data-stu-id="fa94b-110">Configuring Prerequisite Groups in Active Directory for App-V</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa94b-111">在執行 IIS 的伺服器上設定 [網際網路資訊服務（IIS）] 設定。</span><span class="sxs-lookup"><span data-stu-id="fa94b-111">Configure the Internet Information Services (IIS) settings on the server that is running IIS.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)"><span data-ttu-id="fa94b-112">如何針對 App-V Management Server 設定 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="fa94b-112">How to Configure Windows Server 2008 for App-V Management Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa94b-113">將執行 IIS 的伺服器設定為信任委派。</span><span class="sxs-lookup"><span data-stu-id="fa94b-113">Configure the server that is running IIS to be trusted for delegation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="fa94b-114">注意</span><span class="sxs-lookup"><span data-stu-id="fa94b-114">Note</span></span></strong><br/><p><span data-ttu-id="fa94b-115">只有在您使用分散式系統結構（即，如果您在不同的電腦上安裝 App V 管理主控台、管理 Web 服務和資料庫）安裝 App V 管理伺服器時，才需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="fa94b-115">This is required only if you are installing the App-V Management Server by using a distributed system architecture, that is, if you install the App-V Management Console, the Management Web Service, and the database on different computers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)"><span data-ttu-id="fa94b-116">如何將伺服器設定成受信任可以委派</span><span class="sxs-lookup"><span data-stu-id="fa94b-116">How to Configure the Server to be Trusted for Delegation</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa94b-117">安裝 Microsoft SQL Server 2008。</span><span class="sxs-lookup"><span data-stu-id="fa94b-117">Install Microsoft SQL Server 2008.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)"><span data-ttu-id="fa94b-118">安裝 SQL Server 2008 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="fa94b-118">Install SQL Server 2008</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924">https://go.microsoft.com/fwlink/?LinkId=181924</a>).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="fa94b-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa94b-119">Related topics</span></span>


[<span data-ttu-id="fa94b-120">Application Virtualization 部署與升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="fa94b-120">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

[<span data-ttu-id="fa94b-121">App-V 安裝檢查清單</span><span class="sxs-lookup"><span data-stu-id="fa94b-121">App-V Installation Checklist</span></span>](app-v-installation-checklist.md)









