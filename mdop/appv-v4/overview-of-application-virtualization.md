---
title: Application Virtualization 概觀
description: Application Virtualization 概觀
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800944"
---
# <span data-ttu-id="a2707-103">Application Virtualization 概觀</span><span class="sxs-lookup"><span data-stu-id="a2707-103">Overview of Application Virtualization</span></span>


<span data-ttu-id="a2707-104">Microsoft Application Virtualization （App-v）可以讓最終使用者電腦能使用應用程式，而不必直接在那些電腦上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="a2707-104">Microsoft Application Virtualization (App-V) can make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="a2707-105">您可以透過稱為*應用程式順序的程式*來進行這項工作，這可讓每個應用程式在自己的用戶端電腦上獨立的虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="a2707-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="a2707-106">順序化的應用程式彼此隔離。</span><span class="sxs-lookup"><span data-stu-id="a2707-106">The sequenced applications are isolated from each other.</span></span> <span data-ttu-id="a2707-107">這會消除應用程式衝突，但應用程式仍可與用戶端電腦互動。</span><span class="sxs-lookup"><span data-stu-id="a2707-107">This eliminates application conflicts, but the applications can still interact with the client computer.</span></span>

<span data-ttu-id="a2707-108">App-v 用戶端是一個功能，可讓使用者在將應用程式發佈到電腦之後與它們互動。</span><span class="sxs-lookup"><span data-stu-id="a2707-108">The App-V client is the feature that lets the end user interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="a2707-109">用戶端管理虛擬化應用程式在每個電腦上執行的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="a2707-109">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="a2707-110">在電腦上安裝用戶端之後，您必須透過稱為*發佈*的程式，將應用程式提供給電腦，讓使用者能夠執行虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="a2707-110">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="a2707-111">發佈程式會將虛擬應用程式圖示和快速鍵複製到電腦（通常是在 Windows 桌面或 [**開始**] 功能表上），同時也會將套件定義和檔案類型關聯資訊複製到電腦。</span><span class="sxs-lookup"><span data-stu-id="a2707-111">The publishing process copies the virtual application icons and shortcuts to the computer—typically on the Windows desktop or on the **Start** menu—and also copies the package definition and file type association information to the computer.</span></span> <span data-ttu-id="a2707-112">發佈也會將應用程式套件內容提供給最終使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="a2707-112">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="a2707-113">您可以將虛擬應用程式套件內容複寫到一或多個應用程式虛擬化伺服器上，讓它可以根據需求傳送到用戶端，並在本機上緩存。</span><span class="sxs-lookup"><span data-stu-id="a2707-113">The virtual application package content can be copied onto one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="a2707-114">檔案伺服器和 Web 服務器也可以用來做為流式處理伺服器，或可以直接將內容複寫到最終使用者的電腦上，例如，如果您使用的是電子軟體發佈系統（例如 Microsoft 端點設定管理員）。</span><span class="sxs-lookup"><span data-stu-id="a2707-114">File servers and Web servers can also be used as streaming servers, or the content can be copied directly to the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a2707-115">在多重伺服器的實現中，維護封裝內容並在所有流式處理伺服器上保持在最新狀態，都需要綜合的套件管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="a2707-115">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="a2707-116">視貴組織的規模而定，您可能需要有許多虛擬應用程式可供世界各地的最終使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a2707-116">Depending on the size of your organization, you might need to have many virtual applications available to end users located all over the world.</span></span> <span data-ttu-id="a2707-117">管理套件，以確保所有使用者都能存取適當的應用程式，而他們需要存取這些專案的時間，就是一項重要的需求。</span><span class="sxs-lookup"><span data-stu-id="a2707-117">Managing the packages to ensure that the appropriate applications are available to all users where and when they need access to them is therefore an important requirement.</span></span>

## <span data-ttu-id="a2707-118">Microsoft Application Virtualization 系統功能</span><span class="sxs-lookup"><span data-stu-id="a2707-118">Microsoft Application Virtualization System Features</span></span>


<span data-ttu-id="a2707-119">下表說明 Microsoft Application Virtualization 管理系統的主要功能。</span><span class="sxs-lookup"><span data-stu-id="a2707-119">The following table describes the primary features of the Microsoft Application Virtualization Management System.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2707-120">功能</span><span class="sxs-lookup"><span data-stu-id="a2707-120">Feature</span></span></th>
<th align="left"><span data-ttu-id="a2707-121">函式</span><span class="sxs-lookup"><span data-stu-id="a2707-121">Function</span></span></th>
<th align="left"><span data-ttu-id="a2707-122">其他資訊</span><span class="sxs-lookup"><span data-stu-id="a2707-122">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2707-123">Microsoft Application Virtualization 管理伺服器</span><span class="sxs-lookup"><span data-stu-id="a2707-123">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-124">負責流式處理封裝內容，並將快捷方式和檔案類型關聯發佈到應用程式虛擬化用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2707-124">Responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-125">應用程式虛擬化管理伺服器支援作用中升級、授權管理，以及可用於報告的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a2707-125">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a2707-126">內容 </strong> 資料夾</span><span class="sxs-lookup"><span data-stu-id="a2707-126">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-127">表示應用程式虛擬化套件的下載位置。</span><span class="sxs-lookup"><span data-stu-id="a2707-127">Indicates the location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-128">這個資料夾可以位於應用程式虛擬化管理伺服器上的共用位置。</span><span class="sxs-lookup"><span data-stu-id="a2707-128">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2707-129">Microsoft Application Virtualization 管理主控台</span><span class="sxs-lookup"><span data-stu-id="a2707-129">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-130">這個主控台是用來進行 Microsoft Application Virtualization Server 管理的 MMC 3.0 管理單元管理工具。</span><span class="sxs-lookup"><span data-stu-id="a2707-130">This console is an MMC 3.0 snap-in management tool used for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-131">此工具可以安裝在 Microsoft Application Virtualization 伺服器上，或位於擁有 Microsoft 管理主控台（MMC）3.0 和 Microsoft 的個別工作站上。已安裝 NETFramework 2.0。</span><span class="sxs-lookup"><span data-stu-id="a2707-131">This tool can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has Microsoft Management Console (MMC)3.0 and Microsoft .NETFramework 2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2707-132">Microsoft Application Virtualization 管理 Web 服務</span><span class="sxs-lookup"><span data-stu-id="a2707-132">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-133">負責將任何讀取和寫入要求傳達給應用程式虛擬化資料存放區。</span><span class="sxs-lookup"><span data-stu-id="a2707-133">Responsible for communicating any read and write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-134">管理 Web 服務可以安裝在 Microsoft Application Virtualization 管理伺服器或已安裝 Microsoft 網際網路資訊服務（IIS）的另一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="a2707-134">The Management Web Service can be installed on the Microsoft Application Virtualization Management server or on a separate computer that has Microsoft Internet Information Services (IIS) installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2707-135">Microsoft Application Virtualization 資料存放區</span><span class="sxs-lookup"><span data-stu-id="a2707-135">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-136">App-v SQL Server 資料庫，負責儲存與應用程式虛擬化基礎結構相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="a2707-136">The App-V SQL Server database responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-137">此資訊包含所有應用程式記錄、應用程式指派，以及哪些群組負責管理應用程式虛擬化環境。</span><span class="sxs-lookup"><span data-stu-id="a2707-137">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2707-138">Microsoft Application Virtualization 串流伺服器</span><span class="sxs-lookup"><span data-stu-id="a2707-138">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-139">負責託管傳送給分支辦公室中用戶端的應用程式虛擬化套件，而該連結回到應用程式虛擬化管理伺服器，則會被視為廣域網路絡（WAN）連線。</span><span class="sxs-lookup"><span data-stu-id="a2707-139">Responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a wide area networks (WAN) connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-140">此伺服器只包含流式處理功能，且既不提供應用程式虛擬化管理主控台，也不提供應用程式虛擬化管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a2707-140">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2707-141">Microsoft Application Virtualization 排序器</span><span class="sxs-lookup"><span data-stu-id="a2707-141">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-142">Sequencer 是用來監視及捕獲應用程式的安裝，以建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="a2707-142">The sequencer is used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-143">輸出包含應用程式的圖示、內含套件定義資訊的 .osd 檔案、封裝資訊清單檔案，以及包含應用程式內容檔案的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2707-143">The output consists of the application’s icons, an .osd file that contains package definition information, a package manifest file, and the .sft file that contains the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2707-144">Microsoft Application Virtualization 用戶端</span><span class="sxs-lookup"><span data-stu-id="a2707-144">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-145">應用程式虛擬化桌面用戶端和適用于遠端桌面服務的應用程式虛擬化用戶端提供及管理虛擬化應用程式的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="a2707-145">The Application Virtualization Desktop Client and the Application Virtualization Client for Remote Desktop Services provide and manage the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2707-146">Microsoft Application Virtualization 用戶端會將套件資料流程管理到快取、發佈重新整理、傳輸，以及與應用程式虛擬化伺服器的所有互動。</span><span class="sxs-lookup"><span data-stu-id="a2707-146">The Microsoft Application Virtualization client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





