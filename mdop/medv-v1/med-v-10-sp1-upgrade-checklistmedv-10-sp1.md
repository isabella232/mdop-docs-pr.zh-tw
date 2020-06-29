---
title: MED-V 1.0 SP1 升級檢查清單
description: MED-V 1.0 SP1 升級檢查清單
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812254"
---
# <span data-ttu-id="2fed0-103">MED-V 1.0 SP1 升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="2fed0-103">MED-V 1.0 SP1 Upgrade Checklist</span></span>


<span data-ttu-id="2fed0-104">若要將 Microsoft 企業版桌面虛擬化（MED-V）1.0 升級至 MED-V 1.0 服務 Pack1 （SP1），必須升級用戶端。</span><span class="sxs-lookup"><span data-stu-id="2fed0-104">To upgrade Microsoft Enterprise Desktop Virtualization (MED-V)1.0 to MED-V1.0 Service Pack1 (SP1), the client must be upgraded.</span></span> <span data-ttu-id="2fed0-105">您也可以選擇升級伺服器。</span><span class="sxs-lookup"><span data-stu-id="2fed0-105">The server can optionally be upgraded.</span></span>

## <span data-ttu-id="2fed0-106">伺服器升級</span><span class="sxs-lookup"><span data-stu-id="2fed0-106">Server Upgrade</span></span>


**<span data-ttu-id="2fed0-107">若要將 MED-V 1.0 伺服器升級至 MED-V 1.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fed0-107">To upgrade the MED-V1.0 server to MED-V1.0 SP1</span></span>**

1.  <span data-ttu-id="2fed0-108">備份位於\* &lt; InstallDir &gt; /Servers/ConfigurationServer\*目錄中的下列檔案：</span><span class="sxs-lookup"><span data-stu-id="2fed0-108">Back up the following files that are located in the *&lt;InstallDir&gt; / Servers / ConfigurationServer* directory:</span></span>

    -   <span data-ttu-id="2fed0-109">OrganizationalPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="2fed0-109">OrganizationalPolicy.XML</span></span>

    -   <span data-ttu-id="2fed0-110">ClientPolicy.XML</span><span class="sxs-lookup"><span data-stu-id="2fed0-110">ClientPolicy.XML</span></span>

    -   <span data-ttu-id="2fed0-111">WorkspaceKeys.XML</span><span class="sxs-lookup"><span data-stu-id="2fed0-111">WorkspaceKeys.XML</span></span>

2.  <span data-ttu-id="2fed0-112">備份\* &lt; InstallDir &gt; /伺服器/ServerSettings.xml\*檔案。</span><span class="sxs-lookup"><span data-stu-id="2fed0-112">Back up the *&lt;InstallDir&gt; / Servers / ServerSettings.xml* file.</span></span>

3.  <span data-ttu-id="2fed0-113">卸載 MED-V 1.0 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2fed0-113">Uninstall the MED-V1.0 server.</span></span>

4.  <span data-ttu-id="2fed0-114">安裝 MED-V 1.0 SP1 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2fed0-114">Install the MED-V1.0 SP1 server.</span></span>

5.  <span data-ttu-id="2fed0-115">將備份檔案還原至適當的目錄。</span><span class="sxs-lookup"><span data-stu-id="2fed0-115">Restore the backup files to the appropriate directories.</span></span>

6.  <span data-ttu-id="2fed0-116">重新開機 MED-V 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="2fed0-116">Restart the MED-V server service.</span></span>

<span data-ttu-id="2fed0-117">**記事** 如果伺服器設定已從預設值變更，則檔案可能會儲存在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="2fed0-117">**Note** If the server configuration has been changed from the default, the files might be stored in a different location.</span></span>

 

## <span data-ttu-id="2fed0-118">用戶端升級</span><span class="sxs-lookup"><span data-stu-id="2fed0-118">Client Upgrade</span></span>


<span data-ttu-id="2fed0-119">若要將 MED-V 1.0 用戶端升級至 MED-V 1.0 SP1，請在 MED-V 1.0 用戶端上安裝 .msp 檔案。</span><span class="sxs-lookup"><span data-stu-id="2fed0-119">To upgrade the MED-V1.0 client to MED-V1.0 SP1, install the .msp file on a MED-V1.0 client.</span></span> <span data-ttu-id="2fed0-120">用戶端和 MED-V 會自動升級。</span><span class="sxs-lookup"><span data-stu-id="2fed0-120">The client and MED-V are automatically upgraded.</span></span>

 

 





