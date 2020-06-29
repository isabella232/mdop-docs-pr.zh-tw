---
title: MED-V 安裝必要條件
description: MED-V 安裝必要條件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810874"
---
# <span data-ttu-id="ab3fe-103">MED-V 安裝必要條件</span><span class="sxs-lookup"><span data-stu-id="ab3fe-103">MED-V Installation Prerequisites</span></span>


<span data-ttu-id="ab3fe-104">以下是安裝 MED-V 的先決條件：</span><span class="sxs-lookup"><span data-stu-id="ab3fe-104">The following are prerequisites for installing MED-V:</span></span>

[<span data-ttu-id="ab3fe-105">Active Directory 需求</span><span class="sxs-lookup"><span data-stu-id="ab3fe-105">Active Directory Requirements</span></span>](#bkmk-activedirectoryrequirements)

[<span data-ttu-id="ab3fe-106">報表資料庫</span><span class="sxs-lookup"><span data-stu-id="ab3fe-106">Report Database</span></span>](#bkmk-howtoinstallthereportdatabase)

[<span data-ttu-id="ab3fe-107">防病毒/備份軟體設定</span><span class="sxs-lookup"><span data-stu-id="ab3fe-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

[<span data-ttu-id="ab3fe-108">Microsoft Virtual PC 2007 SP1</span><span class="sxs-lookup"><span data-stu-id="ab3fe-108">Microsoft Virtual PC 2007 SP1</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a><span data-ttu-id="ab3fe-109">Active Directory 需求</span><span class="sxs-lookup"><span data-stu-id="ab3fe-109">Active Directory Requirements</span></span>


<span data-ttu-id="ab3fe-110">在配置 MED-V 伺服器時，如果使用者不屬於伺服器所屬的網域，則必須在網域之間設定信任。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-110">When configuring the MED-V server, if users are not part of the same domain the server belongs to, a trust must be set between the domains.</span></span>

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a><span data-ttu-id="ab3fe-111">如何安裝報表資料庫</span><span class="sxs-lookup"><span data-stu-id="ab3fe-111">How to Install the Report Database</span></span>


<span data-ttu-id="ab3fe-112">儲存所有 MED-V 工作區記錄需要報表資料庫。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-112">The report database is required for storing all MED-V workspace logs.</span></span> <span data-ttu-id="ab3fe-113">然後，就會使用記錄資料庫來產生 MED-V 報告。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-113">The log database is then used for generating MED-V reports.</span></span> <span data-ttu-id="ab3fe-114">如需報告的相關資訊，請參閱[Med-v 報告](med-v-reporting.md)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-114">For information about reports, see [MED-V Reporting](med-v-reporting.md).</span></span>

<span data-ttu-id="ab3fe-115">SQL Server 可以安裝在與 MED-V 伺服器相同的伺服器上，或安裝在遠端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-115">SQL Server can be installed on the same server as the MED-V server or on a remote server.</span></span> <span data-ttu-id="ab3fe-116">如果是在遠端伺服器上安裝，請參閱[在遠端伺服器上安裝 SQL server](#bkmk-installingsqlserveronaremoteserver)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-116">If installing on a remote server, see [Installing SQL Server on a Remote Server](#bkmk-installingsqlserveronaremoteserver).</span></span>

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a><span data-ttu-id="ab3fe-117">在遠端伺服器上安裝 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab3fe-117">Installing SQL Server on a Remote Server</span></span>

**<span data-ttu-id="ab3fe-118">在遠端伺服器上安裝 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab3fe-118">To install SQL Server on a remote server</span></span>**

1.  <span data-ttu-id="ab3fe-119">在遠端伺服器上設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="ab3fe-119">Configure the following on the remote server:</span></span>

    -   <span data-ttu-id="ab3fe-120">實例名稱-預設實例</span><span class="sxs-lookup"><span data-stu-id="ab3fe-120">Instance name—Default instance</span></span>

    -   <span data-ttu-id="ab3fe-121">驗證模式-混合模式</span><span class="sxs-lookup"><span data-stu-id="ab3fe-121">Authentication mode—Mixed mode</span></span>

    -   <span data-ttu-id="ab3fe-122">使用者：建立的預設使用者為「sa」</span><span class="sxs-lookup"><span data-stu-id="ab3fe-122">User—The default user created is “sa”</span></span>

    -   <span data-ttu-id="ab3fe-123">密碼-所需的密碼</span><span class="sxs-lookup"><span data-stu-id="ab3fe-123">Password—Desired password</span></span>

    -   <span data-ttu-id="ab3fe-124">排序規則設定-預設</span><span class="sxs-lookup"><span data-stu-id="ab3fe-124">Collation Settings—Default</span></span>

    -   <span data-ttu-id="ab3fe-125">使用方式報告設定中的錯誤-預設值</span><span class="sxs-lookup"><span data-stu-id="ab3fe-125">Error in usage report settings—Default</span></span>

2.  <span data-ttu-id="ab3fe-126">在 MED-V 伺服器上安裝下列檔案：</span><span class="sxs-lookup"><span data-stu-id="ab3fe-126">Install the following files on the MED-V server:</span></span>

    -   <span data-ttu-id="ab3fe-127">若要針對 Microsoft SQL Server2008 的管理套件物件集合安裝必備元件，請從 Microsoft 下載中心下載[MICROSOFT Sql Server2008 原生用戶端](https://go.microsoft.com/fwlink/?LinkId=164039)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-127">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2008, download [Microsoft SQL Server2008 Native Client](https://go.microsoft.com/fwlink/?LinkId=164039) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="ab3fe-128">若要針對 Microsoft SQL Server2005 的管理套件物件集合安裝必備元件，請從 Microsoft 下載中心下載[MICROSOFT Sql Server2005 原生用戶端](https://go.microsoft.com/fwlink/?LinkId=164038)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-128">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Native Client](https://go.microsoft.com/fwlink/?LinkId=164038) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="ab3fe-129">若要為 Microsoft SQL Server2008 安裝必要的 dll 檔案，請從 Microsoft 下載中心下載[MICROSOFT Sql Server 2008 管理物件集合](https://go.microsoft.com/fwlink/?LinkId=164041)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-129">To install the required dll files for Microsoft SQL Server2008, download [Microsoft SQL Server 2008 Management Objects Collection](https://go.microsoft.com/fwlink/?LinkId=164041) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="ab3fe-130">若要為 Microsoft SQL Server2005 安裝必要的 dll 檔案，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2005 管理物件](https://go.microsoft.com/fwlink/?LinkId=164040)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-130">To install the required dll files for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Management Objects](https://go.microsoft.com/fwlink/?LinkId=164040) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="ab3fe-131">若要安裝可提供其他 SQL Server2008 值的獨立安裝套件，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=163960)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-131">To install the stand-alone install packages that provide additional value for SQL Server2008, download the [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="ab3fe-132">若要安裝可提供其他 SQL Server2005 值的獨立安裝套件，請從 Microsoft 下載中心下載[MICROSOFT SQL Server2005 的功能套件]( https://go.microsoft.com/fwlink/?LinkId=163961)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-132">To install the stand-alone install packages that provide additional value for SQL Server2005, download the [Feature Pack for Microsoft SQL Server2005]( https://go.microsoft.com/fwlink/?LinkId=163961) from the Microsoft Download Center.</span></span>

    <span data-ttu-id="ab3fe-133">如需這些檔案的詳細資訊，請參閱 microsoft 下載中心（或 microsoft 下載中心的功能套件）上的[MICROSOFT Sql Server2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=163960)（ https://go.microsoft.com/fwlink/?LinkId=163960) 或 microsoft 下載中心的 [ [microsoft sql Server2005](https://go.microsoft.com/fwlink/?LinkId=163961) ] https://go.microsoft.com/fwlink/?LinkId=163961) 。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-133">For more information about these files, see [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163960) or [Feature Pack for Microsoft SQL Server2005](https://go.microsoft.com/fwlink/?LinkId=163961) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163961).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="ab3fe-134">防病毒/備份軟體設定</span><span class="sxs-lookup"><span data-stu-id="ab3fe-134">Antivirus/Backup Software Configuration</span></span>


<span data-ttu-id="ab3fe-135">若要防止防病毒活動影響虛擬桌面的效能，建議您盡可能從主機上執行的任何防毒軟體或備份處理常式中排除下列虛擬機器檔案類型：</span><span class="sxs-lookup"><span data-stu-id="ab3fe-135">To prevent antivirus activity from affecting the performance of the virtual desktop, it is recommended where possible to exclude the following virtual machine file types from any antivirus or backup processing running on the host:</span></span>

-   <span data-ttu-id="ab3fe-136">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="ab3fe-136">\*.VMC</span></span>

-   <span data-ttu-id="ab3fe-137">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="ab3fe-137">\*.VUD</span></span>

-   <span data-ttu-id="ab3fe-138">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="ab3fe-138">\*.VSV</span></span>

-   <span data-ttu-id="ab3fe-139">\*.CKM</span><span class="sxs-lookup"><span data-stu-id="ab3fe-139">\*.CKM</span></span>

-   <span data-ttu-id="ab3fe-140">\*.EVHD</span><span class="sxs-lookup"><span data-stu-id="ab3fe-140">\*.EVHD</span></span>

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a><span data-ttu-id="ab3fe-141">如何安裝和設定 Microsoft Virtual PC2007 SP1</span><span class="sxs-lookup"><span data-stu-id="ab3fe-141">How to Install and Configure Microsoft Virtual PC2007 SP1</span></span>


<span data-ttu-id="ab3fe-142">**重要** 如果主機電腦上存在 Windows 版虛擬電腦，請在安裝 Virtual PC2007 SP1 之前先將它卸載。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-142">**Important** If Virtual PC for Windows exists on the host computer, uninstall it before installing Virtual PC2007 SP1.</span></span>

 

**<span data-ttu-id="ab3fe-143">若要安裝 Microsoft Virtual PC2007 SP1</span><span class="sxs-lookup"><span data-stu-id="ab3fe-143">To install Microsoft Virtual PC2007 SP1</span></span>**

1.  <span data-ttu-id="ab3fe-144">從 Microsoft 下載中心[VIRTUAL PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=142994)下載 VIRTUAL PC2007 SP1。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-144">Download Virtual PC2007 SP1 from the Microsoft Download Center [Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=142994).</span></span>

2.  <span data-ttu-id="ab3fe-145">在主機電腦上執行安裝檔，然後依照嚮導進行。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-145">Run the installation file on the host computer, and follow the wizard.</span></span>

3.  <span data-ttu-id="ab3fe-146">在主機電腦上以提升模式安裝 Virtual PC2007 SP1 更新。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-146">Install Virtual PC2007 SP1 update on the host computer in elevated mode.</span></span>

    <span data-ttu-id="ab3fe-147">如需詳細資訊，請參閱適用于[VIRTUAL PC 2007 SP1 之修補程式套件的說明](https://go.microsoft.com/fwlink/?LinkId=150575)。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-147">For more information, see [the description of the hotfix package for Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=150575).</span></span>

    <span data-ttu-id="ab3fe-148">**記事** 執行 Virtual PC2007 SP1 需要 Virtual PC2007 SP1 更新。</span><span class="sxs-lookup"><span data-stu-id="ab3fe-148">**Note** The Virtual PC2007 SP1 update is required for running Virtual PC2007 SP1.</span></span>

     

## <span data-ttu-id="ab3fe-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab3fe-149">Related topics</span></span>


[<span data-ttu-id="ab3fe-150">支援的設定</span><span class="sxs-lookup"><span data-stu-id="ab3fe-150">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

 

 





