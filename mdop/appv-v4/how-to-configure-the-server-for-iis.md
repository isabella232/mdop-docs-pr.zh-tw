---
title: 如何設定伺服器使用 IIS
description: 如何設定伺服器使用 IIS
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801538"
---
# <span data-ttu-id="c7777-103">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="c7777-103">How to Configure the Server for IIS</span></span>


<span data-ttu-id="c7777-104">在虛擬應用程式可以傳送到應用程式虛擬化桌面用戶端和遠端桌面服務的用戶端（以前稱為終端服務）之前，必須先設定 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c7777-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services), the IIS servers must be configured.</span></span> <span data-ttu-id="c7777-105">當您設定伺服器時，您就是在儲存 SFT 檔案的位置設定 [內容目錄]。</span><span class="sxs-lookup"><span data-stu-id="c7777-105">When you configure the servers, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="c7777-106">SFT 檔案包含虛擬應用程式（或應用程式）。</span><span class="sxs-lookup"><span data-stu-id="c7777-106">The SFT files contain the virtual application (or applications).</span></span>

**<span data-ttu-id="c7777-107">若要在 IIS 伺服器上設定內容目錄</span><span class="sxs-lookup"><span data-stu-id="c7777-107">To configure the content directory on the IIS server</span></span>**

1.  <span data-ttu-id="c7777-108">在執行 IIS 的伺服器上，找出您要用來做為內容目錄的目錄，或建立不存在的目錄。</span><span class="sxs-lookup"><span data-stu-id="c7777-108">On the server that is running IIS, locate the directory that you want to use as the content directory, or create the directory if it does not exist.</span></span> <span data-ttu-id="c7777-109">將此目錄設定為標準檔案共用。</span><span class="sxs-lookup"><span data-stu-id="c7777-109">Configure this directory as a standard file share.</span></span>

2.  <span data-ttu-id="c7777-110">在執行 IIS 的伺服器上，開啟 [ **Iis 管理員**]，然後在 [預設網站] 底下，建立一個與您在伺服器上建立之內容目錄相對應的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="c7777-110">On the server that is running IIS, open **IIS Manager**, and under the default website, create a virtual directory that corresponds to the content directory that you created on the server.</span></span> <span data-ttu-id="c7777-111">請確定已核取 [**讀取**]。</span><span class="sxs-lookup"><span data-stu-id="c7777-111">Make sure that **Read** is checked.</span></span>

3.  <span data-ttu-id="c7777-112">為新建立的虛擬目錄提供別名**內容**。</span><span class="sxs-lookup"><span data-stu-id="c7777-112">Give the newly created virtual directory the alias **Content**.</span></span>

4.  <span data-ttu-id="c7777-113">接受此虛擬目錄的所有其他預設設定。</span><span class="sxs-lookup"><span data-stu-id="c7777-113">Accept all other default settings for this virtual directory.</span></span>

5.  <span data-ttu-id="c7777-114">使用您先前定義的 Active Directory 網域服務中的安全性群組，將 NTFS 檔案系統許可權設定為內容目錄及 [內容目錄] 底下的 [套件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="c7777-114">Configure the NTFS file system permissions to the content directory and the package folders under the content directory by using the Security Groups in Active Directory Domain Services that you defined earlier.</span></span>

<span data-ttu-id="c7777-115">**記事** 如果您使用 IIS 發佈 .ICO 和 OSD 檔案，您必須設定 OSD = TXT 的 MIME 類型;否則，IIS 將不會將 .ICO 和 OSD 檔案提供給用戶端。</span><span class="sxs-lookup"><span data-stu-id="c7777-115">**Note** If you are using IIS to publish the ICO and OSD files, you must configure a MIME type for OSD=TXT; otherwise, IIS will not serve the ICO and OSD files to clients.</span></span> <span data-ttu-id="c7777-116">如果您使用 IIS 發佈套件（SFT 檔案），則必須針對 SFT = Binary 設定 MIME 類型;否則，IIS 將不會將 SFT 檔案提供給用戶端。</span><span class="sxs-lookup"><span data-stu-id="c7777-116">If you are using IIS to publish packages (SFT files), you must configure a MIME type for SFT=Binary; otherwise, IIS will not serve the SFT files to clients.</span></span>

 

## <span data-ttu-id="c7777-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="c7777-117">Related topics</span></span>


[<span data-ttu-id="c7777-118">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="c7777-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="c7777-119">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="c7777-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="c7777-120">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="c7777-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="c7777-121">如何設定 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="c7777-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="c7777-122">如何設定檔案伺服器</span><span class="sxs-lookup"><span data-stu-id="c7777-122">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

 

 





