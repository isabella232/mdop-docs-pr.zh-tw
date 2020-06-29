---
title: 設定叢集模式的 MED-V 伺服器
description: 設定叢集模式的 MED-V 伺服器
author: dansimp
ms.assetid: 41f0b2a3-4ce9-48e1-a6fb-4c13c4228515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddb7dd5af65d8a465c5c1884bb27a3027621bac1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811924"
---
# <span data-ttu-id="04b64-103">設定叢集模式的 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="04b64-103">Configuring MED-V Server for Cluster Mode</span></span>


<span data-ttu-id="04b64-104">您可以在 [群集模式] 中設定 MED-V 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04b64-104">You can configure the MED-V server in cluster mode.</span></span> <span data-ttu-id="04b64-105">在群集模式中，會使用兩個伺服器，並將兩個伺服器標示為共有的所有檔案都放在檔案系統上。</span><span class="sxs-lookup"><span data-stu-id="04b64-105">In cluster mode, two servers are used and all files identified as mutual to both servers are placed on a file system.</span></span> <span data-ttu-id="04b64-106">伺服器會從檔案系統存取檔案，而不是將檔案儲存在本機。</span><span class="sxs-lookup"><span data-stu-id="04b64-106">The server accesses the files from the file system rather than storing the files locally.</span></span>

## <a href="" id="bkmk-howtoconfigurethemedvserverinclustermode"></a>


**<span data-ttu-id="04b64-107">若要在群集模式中設定 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="04b64-107">To configure the MED-V server in cluster mode</span></span>**

1.  <span data-ttu-id="04b64-108">在其中一個伺服器上安裝並設定 MED-V。</span><span class="sxs-lookup"><span data-stu-id="04b64-108">Install and configure MED-V on one of the servers.</span></span>

2.  <span data-ttu-id="04b64-109">在所有伺服器都可以存取的中央位置建立共用網路。</span><span class="sxs-lookup"><span data-stu-id="04b64-109">Create a shared network in a central location where all of the servers can access it.</span></span>

3.  <span data-ttu-id="04b64-110">將 [ \* &lt; InstallDir &gt; /Servers/ConfigurationServer\* ] 資料夾的內容複寫到共用的網路上。</span><span class="sxs-lookup"><span data-stu-id="04b64-110">Copy the contents of the *&lt;InstallDir&gt;/Servers/ConfigurationServer* folder to the shared network.</span></span>

4.  <span data-ttu-id="04b64-111">在所有指定的伺服器上安裝 MED-V 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04b64-111">Install MED-V server on all designated servers.</span></span>

5.  <span data-ttu-id="04b64-112">在共用的網路上，指派所有 MED-V 伺服器系統帳戶的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="04b64-112">On the shared network, assign full access to all MED-V server system accounts.</span></span>

6.  <span data-ttu-id="04b64-113">在每個伺服器上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="04b64-113">On each server, do the following:</span></span>

    1.  <span data-ttu-id="04b64-114">在\* &lt; InstallDir &gt; /Servers/ServerConfiguration.xml*檔案中，將* &lt; StorePath &gt; \*的值設為共用的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="04b64-114">In the *&lt;InstallDir&gt;/Servers/ServerConfiguration.xml* file, set the value of *&lt;StorePath&gt;* to the shared network path.</span></span>

    2.  <span data-ttu-id="04b64-115">從原始伺服器將\* &lt; InstsallDir &gt; /Servers/KeyPair.xml\*檔案複製到所有的 med-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="04b64-115">Copy the *&lt;InstsallDir&gt;/Servers/KeyPair.xml* file from the original server to all MED-V servers.</span></span>

    3.  <span data-ttu-id="04b64-116">重新開機 MED-V 服務。</span><span class="sxs-lookup"><span data-stu-id="04b64-116">Restart the MED-V service.</span></span>

<span data-ttu-id="04b64-117">**記事** 如果所有伺服器都有相同的本機設定（例如，偵聽埠、IIS server、管理許可權、報表資料庫等），則所有伺服器也都可以共用\* &lt; InstallDir &gt; /Servers/ServerSettings.xml\* 。</span><span class="sxs-lookup"><span data-stu-id="04b64-117">**Note** If all servers have the same local settings (such as listening ports, IIS server, management permissions, report database, and so on), the *&lt;InstallDir&gt;/Servers/ServerSettings.xml* can be shared by all servers as well.</span></span>

 

## <span data-ttu-id="04b64-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="04b64-118">Related topics</span></span>


[<span data-ttu-id="04b64-119">MED-V 基礎結構規劃和設計</span><span class="sxs-lookup"><span data-stu-id="04b64-119">MED-V Infrastructure Planning and Design</span></span>](med-v-infrastructure-planning-and-design.md)

 

 





