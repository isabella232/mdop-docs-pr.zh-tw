---
title: 從 MBAM 2.5 升級至 MBAM 2.5 SP1
description: 從 MBAM 2.5 升級至 MBAM 2.5 SP1
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 330ded822dd9da96a1c33eabcb31d744044dc28e
ms.sourcegitcommit: ae34c5cb5e7979b472b257a4691142e493d5d6fe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091618"
---
# <span data-ttu-id="ff50b-103">從 MBAM 2.5 升級至 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff50b-103">Upgrading to MBAM 2.5 SP1 from MBAM 2.5</span></span>
<span data-ttu-id="ff50b-104">本主題描述升級 Microsoft BitLocker 管理和監視 (MBAM) Server 2.5 和 MBAM 用戶端（從2.5 到 MBAM 2.5 SP1）的程式。</span><span class="sxs-lookup"><span data-stu-id="ff50b-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 and the MBAM Client from 2.5 to MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="ff50b-105">開始之前</span><span class="sxs-lookup"><span data-stu-id="ff50b-105">Before you begin</span></span>
#### <span data-ttu-id="ff50b-106">下載2019年5月的服務發行</span><span class="sxs-lookup"><span data-stu-id="ff50b-106">Download the May 2019 servicing release</span></span>
[<span data-ttu-id="ff50b-107">桌面優化套件</span><span class="sxs-lookup"><span data-stu-id="ff50b-107">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=58345)

#### <span data-ttu-id="ff50b-108">下載2018年7月的服務發行</span><span class="sxs-lookup"><span data-stu-id="ff50b-108">Download the July 2018 servicing release</span></span>
[<span data-ttu-id="ff50b-109">桌面優化套件</span><span class="sxs-lookup"><span data-stu-id="ff50b-109">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)


#### <span data-ttu-id="ff50b-110">確認安裝 documentaion</span><span class="sxs-lookup"><span data-stu-id="ff50b-110">Verify the installation documentaion</span></span>
<span data-ttu-id="ff50b-111">確認您有 MBAM 環境的目前檔，包括所有伺服器名稱、資料庫名稱、服務帳戶及其密碼。</span><span class="sxs-lookup"><span data-stu-id="ff50b-111">Verify you have a current documentation of your MBAM environment, including all server names, database names, service accounts and their passwords.</span></span>

### <span data-ttu-id="ff50b-112">升級步驟</span><span class="sxs-lookup"><span data-stu-id="ff50b-112">Upgrade steps</span></span>
#### <span data-ttu-id="ff50b-113"> (SQL Server) 升級 MBAM 資料庫的步驟</span><span class="sxs-lookup"><span data-stu-id="ff50b-113">Steps to upgrade the MBAM Database (SQL Server)</span></span>
1. <span data-ttu-id="ff50b-114">使用 MBAM 配置器;從 SQL server 移除 [報表] 角色，或從任何託管 SSRS 資料庫的位置移除。</span><span class="sxs-lookup"><span data-stu-id="ff50b-114">Using the MBAM Configurator; remove the Reports role from the SQL server, or wherever the SSRS database is hosted.</span></span> <span data-ttu-id="ff50b-115">視您的環境而定，這可以是同一個伺服器或不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ff50b-115">Depending on your environment, this can be the same server or a separate one.</span></span>
  > [!NOTE]
  > <span data-ttu-id="ff50b-116">您將不會看到移除資料庫的選項;此為預期。</span><span class="sxs-lookup"><span data-stu-id="ff50b-116">You will not see an option to remove the Databases; this is expected.</span></span>  
2. <span data-ttu-id="ff50b-117">從大量授權服務中心網站使用 MDOP-Microsoft 桌上型電腦優化套件2015安裝 2.5 SP1 (：</span><span class="sxs-lookup"><span data-stu-id="ff50b-117">Install 2.5 SP1(Located with MDOP - Microsoft Desktop Optimization Pack 2015 from the Volume Licensing Service Center site:</span></span>  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. <span data-ttu-id="ff50b-118">目前不要設定</span><span class="sxs-lookup"><span data-stu-id="ff50b-118">Do not configure it at this time</span></span> 
4. <span data-ttu-id="ff50b-119">使用 MBAM 配置器;重新新增報表角色</span><span class="sxs-lookup"><span data-stu-id="ff50b-119">Using the MBAM Configurator; re-add the Reports role</span></span>
5. <span data-ttu-id="ff50b-120">使用 MBAM 配置器;在 SQL Server 上重新新增 SQL 資料庫角色</span><span class="sxs-lookup"><span data-stu-id="ff50b-120">Using the MBAM Configurator; re-add the SQL Database role on the SQL Server</span></span>
6. <span data-ttu-id="ff50b-121">在結束時，系統會警告您已經存在並無法建立該系統，但預期</span><span class="sxs-lookup"><span data-stu-id="ff50b-121">At the end, you will be warned that the DBs already exist and  weren’t created, but this is expected</span></span>
7. <span data-ttu-id="ff50b-122">這個程式會將現有的資料庫更新為目前安裝的版本。</span><span class="sxs-lookup"><span data-stu-id="ff50b-122">This process updates the existing databases to the current version being installed.</span></span>              

#### <span data-ttu-id="ff50b-123">升級 MBAM 伺服器 (執行 MBAM 和 IIS 的步驟) </span><span class="sxs-lookup"><span data-stu-id="ff50b-123">Steps to upgrade the MBAM Server (Running MBAM and IIS)</span></span>
1. <span data-ttu-id="ff50b-124">使用 MBAM 配置器;從 IIS 伺服器移除系統管理和自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="ff50b-124">Using the MBAM Configurator; remove the Admin and Self Service Portals from  the IIS server</span></span>
2. <span data-ttu-id="ff50b-125">安裝 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff50b-125">Install MBAM 2.5 SP1</span></span>
3. <span data-ttu-id="ff50b-126">目前不要設定</span><span class="sxs-lookup"><span data-stu-id="ff50b-126">Do not configure it at this time</span></span>  
4. <span data-ttu-id="ff50b-127">使用 MBAM 配置器;將系統管理和自助服務入口網站重新新增至 IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="ff50b-127">Using the MBAM Configurator; re-add the Admin and Self Service Portals to the IIS server</span></span> 
5. <span data-ttu-id="ff50b-128">開啟提升許可權的命令提示字元，輸入 [ **IISRESET**]，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="ff50b-128">Open an elevated command prompt, type **IISRESET**, and hit Enter.</span></span>
 
#### <span data-ttu-id="ff50b-129">升級 MBAM 用戶端/端點的步驟</span><span class="sxs-lookup"><span data-stu-id="ff50b-129">Steps to upgrade the MBAM Clients/Endpoints</span></span>
1. <span data-ttu-id="ff50b-130">從用戶端端點卸載2.5 代理程式</span><span class="sxs-lookup"><span data-stu-id="ff50b-130">Uninstall the 2.5 Agent from client endpoints</span></span>
2. <span data-ttu-id="ff50b-131">在用戶端端點上安裝 2.5 SP1 代理程式</span><span class="sxs-lookup"><span data-stu-id="ff50b-131">Install the 2.5 SP1 Agent on the client endpoints</span></span>
3. <span data-ttu-id="ff50b-132">將5月的2019匯總用戶端更新推送到執行 2.5 SP1 代理程式的用戶端</span><span class="sxs-lookup"><span data-stu-id="ff50b-132">Push out the May 2019 Rollup Client update to clients running the 2.5 SP1 Agent</span></span> 
4. <span data-ttu-id="ff50b-133">安裝2019匯總前，不需要先卸載現有的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ff50b-133">There is no need to uninstall the existing client prior to installing the May 2019 Rollup.</span></span>  
