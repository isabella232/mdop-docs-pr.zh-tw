---
title: 修改 AGPM 服務接聽的連接埠
description: 修改 AGPM 服務接聽的連接埠
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802637"
---
# <span data-ttu-id="14ddf-103">修改 AGPM 服務接聽的連接埠</span><span class="sxs-lookup"><span data-stu-id="14ddf-103">Modify the Port on Which the AGPM Service Listens</span></span>


<span data-ttu-id="14ddf-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="14ddf-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="14ddf-105">根據預設，AGPM 服務會偵聽埠4600。</span><span class="sxs-lookup"><span data-stu-id="14ddf-105">By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="14ddf-106">您可以針對每個封存修改高級群組原則管理（AGPM）封存索引檔案，以變更這個埠。</span><span class="sxs-lookup"><span data-stu-id="14ddf-106">You can change this port by modifying the Advanced Group Policy Management (AGPM) archive index file for each archive.</span></span>

<span data-ttu-id="14ddf-107">**記事** 在修改 AGPM 服務所偵聽的埠之前，建議您備份 AGPM 封存索引檔案（gpostate.xml）。</span><span class="sxs-lookup"><span data-stu-id="14ddf-107">**Note** Before modifying the port on which the AGPM Service listens, it is recommended that you back up the AGPM archive index file (gpostate.xml).</span></span> <span data-ttu-id="14ddf-108">這個檔案位於您在安裝高級群組原則管理-伺服器期間，在輸入為封存路徑的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="14ddf-108">This file is located in the folder entered as the archive path during the installation of Advanced Group Policy Management - Server.</span></span> <span data-ttu-id="14ddf-109">根據預設，此檔案的這個位置是在 AGPM 服務器上，% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml%。</span><span class="sxs-lookup"><span data-stu-id="14ddf-109">By default, this location of this file is %CommonAppData%\\Microsoft\\AGPM\\gpostate.xml on the AGPM Server.</span></span> <span data-ttu-id="14ddf-110">如果您不知道哪台電腦主持封存，您可以依照修改封存路徑的程式來顯示目前的封存路徑。</span><span class="sxs-lookup"><span data-stu-id="14ddf-110">If you do not know which computer hosts the archive, you can follow the procedure for modifying the archive path to display the current archive path.</span></span> <span data-ttu-id="14ddf-111">如需詳細資訊，請參閱[修改封存路徑](modify-the-archive-path.md)。</span><span class="sxs-lookup"><span data-stu-id="14ddf-111">For more information, see [Modify the Archive Path](modify-the-archive-path.md).</span></span>

 

<span data-ttu-id="14ddf-112">擁有 AGPM 服務器存取權的使用者帳戶（安裝 AGPM 服務的電腦），而封存索引檔案則需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="14ddf-112">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) and the archive index file is required to complete this procedure.</span></span>

**<span data-ttu-id="14ddf-113">修改 AGPM 服務偵聽的埠</span><span class="sxs-lookup"><span data-stu-id="14ddf-113">To modify the port on which the AGPM Service listens</span></span>**

1.  <span data-ttu-id="14ddf-114">在主持封存的電腦上，在文字編輯器中開啟封存索引檔（gpostate.xml）。</span><span class="sxs-lookup"><span data-stu-id="14ddf-114">On the computer hosting the archive, open the archive index file (gpostate.xml) in a text editor.</span></span>

2.  <span data-ttu-id="14ddf-115">在檔案中，搜尋**agpm： port = "4600"**。</span><span class="sxs-lookup"><span data-stu-id="14ddf-115">In the file, search for **agpm:port="4600"**.</span></span>

3.  <span data-ttu-id="14ddf-116">將**4600**取代為 AGPM 服務應聆聽的埠;然後，儲存並關閉檔案。</span><span class="sxs-lookup"><span data-stu-id="14ddf-116">Replace **4600** with the port on which the AGPM Service should listen; then, save and close the file.</span></span>

4.  <span data-ttu-id="14ddf-117">在 AGPM 服務器上，重新開機 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="14ddf-117">On the AGPM Server, restart the AGPM Service.</span></span> <span data-ttu-id="14ddf-118">（如需詳細資訊，請參閱[啟動和停止 AGPM 服務](start-and-stop-the-agpm-service.md)。）</span><span class="sxs-lookup"><span data-stu-id="14ddf-118">(For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).)</span></span>

5.  <span data-ttu-id="14ddf-119">針對每個群組原則管理員，在 AGPM 服務器連線中修改埠。</span><span class="sxs-lookup"><span data-stu-id="14ddf-119">Modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="14ddf-120">（如需詳細資訊，請參閱[設定 AGPM 服務器](configure-the-agpm-server-connection.md)連線）。</span><span class="sxs-lookup"><span data-stu-id="14ddf-120">(For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).)</span></span>

6.  <span data-ttu-id="14ddf-121">針對每個封存和 AGPM 服務器重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="14ddf-121">Repeat for each archive and AGPM Server.</span></span>

### <span data-ttu-id="14ddf-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="14ddf-122">Additional references</span></span>

-   [<span data-ttu-id="14ddf-123">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="14ddf-123">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





