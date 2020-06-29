---
title: 修改 AGPM 服務帳戶
description: 修改 AGPM 服務帳戶
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802650"
---
# <span data-ttu-id="26c7e-103">修改 AGPM 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="26c7e-103">Modify the AGPM Service Account</span></span>


<span data-ttu-id="26c7e-104">AGPM 服務是一個充當安全性 proxy 的 Windows 服務，管理用戶端對封存和生產環境中的群組原則物件（Gpo）的存取權。</span><span class="sxs-lookup"><span data-stu-id="26c7e-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="26c7e-105">如果此服務已停止或停用，則 AGPM 用戶端無法透過伺服器執行作業。</span><span class="sxs-lookup"><span data-stu-id="26c7e-105">If this service is stopped or disabled, AGPM clients cannot perform operations through the server.</span></span>

<span data-ttu-id="26c7e-106">封存路徑和 AGPM 服務帳戶是在安裝 AGPM 服務器期間進行設定，您可以在此後透過 [**新增或移除程式**] 在 AGPM 服務器上變更。</span><span class="sxs-lookup"><span data-stu-id="26c7e-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="26c7e-107">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來修改 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="26c7e-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="26c7e-108">如此一來，就能防止 AGPM 服務啟動。</span><span class="sxs-lookup"><span data-stu-id="26c7e-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="26c7e-109">使用者帳戶是 Domain Admins 群組的成員，且有權存取 AGPM 服務器（安裝 Microsoft 高級群組原則管理-伺服器的電腦）需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="26c7e-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

<span data-ttu-id="26c7e-110">**重要** AGPM 服務帳戶必須擁有對其所管理之 Gpo 的完整存取權，並將其授**與服務許可權登**入。</span><span class="sxs-lookup"><span data-stu-id="26c7e-110">**Important** The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="26c7e-111">如果您要在單一網域上管理 Gpo，您可以將 [本機系統] 帳戶設為主要網網域控制站（AGPM 服務帳戶）。</span><span class="sxs-lookup"><span data-stu-id="26c7e-111">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

<span data-ttu-id="26c7e-112">如果您要管理多個網域上的 Gpo，或如果成員伺服器將是 AGPM 服務器，您應該將另一個帳戶設定為 AGPM 服務帳戶，因為一個網網域控制站的本機系統帳戶無法存取其他網域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="26c7e-112">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

 

**<span data-ttu-id="26c7e-113">修改 AGPM 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="26c7e-113">To modify the AGPM Service Account</span></span>**

1.  <span data-ttu-id="26c7e-114">在已安裝 Microsoft 高級群組原則管理-伺服器的電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**新增或移除程式**]。</span><span class="sxs-lookup"><span data-stu-id="26c7e-114">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="26c7e-115">按一下 [ **Microsoft 高級群組原則管理-伺服器**]，然後按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="26c7e-115">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="26c7e-116">按一下 **[下一步]**，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="26c7e-116">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="26c7e-117">依照螢幕上的指示來設定 AGPM 服務的設定：</span><span class="sxs-lookup"><span data-stu-id="26c7e-117">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="26c7e-118">針對封存路徑，確認或變更封存相對於 AGPM 服務器的位置。</span><span class="sxs-lookup"><span data-stu-id="26c7e-118">For the archive path, confirm or change the location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="26c7e-119">封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但該位置應該有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="26c7e-119">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="26c7e-120">輸入 AGPM 服務帳戶的新認證。</span><span class="sxs-lookup"><span data-stu-id="26c7e-120">Enter new credentials for the AGPM Service Account.</span></span>

    3.  <span data-ttu-id="26c7e-121">針對封存擁有者，輸入 AGPM 系統管理員的認證（[完全控制]）。</span><span class="sxs-lookup"><span data-stu-id="26c7e-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="26c7e-122">按一下 [**變更**]，完成安裝後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="26c7e-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="26c7e-123">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="26c7e-123">Additional references</span></span>

-   [<span data-ttu-id="26c7e-124">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="26c7e-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





