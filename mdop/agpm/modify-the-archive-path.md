---
title: 修改封存路徑
description: 修改封存路徑
author: dansimp
ms.assetid: 6d90daf9-58db-4166-b5b3-e84bb261164a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1fc6ba2bf415d3d1bc67144d0dec1030c6173026
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802638"
---
# <span data-ttu-id="f7113-103">修改封存路徑</span><span class="sxs-lookup"><span data-stu-id="f7113-103">Modify the Archive Path</span></span>


<span data-ttu-id="f7113-104">封存路徑是相對於 AGPM 服務器的封存位置。</span><span class="sxs-lookup"><span data-stu-id="f7113-104">The archive path is the location of the archive relative to the AGPM Server.</span></span> <span data-ttu-id="f7113-105">封存路徑可以指向您在 AGPM 服務器上的資料夾，或是在同一林中的另一台伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f7113-105">The archive path can point to a folder on the AGPM Server or on another server in the same forest.</span></span>

<span data-ttu-id="f7113-106">封存路徑和 AGPM 服務帳戶是在安裝 AGPM 服務器期間進行設定，您可以在此後透過 [**新增或移除程式**] 在 AGPM 服務器上變更。</span><span class="sxs-lookup"><span data-stu-id="f7113-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="f7113-107">使用者帳戶是 Domain Admins 群組的成員，且有權存取 AGPM 服務器（安裝 Microsoft 高級群組原則管理-伺服器的電腦）需要完成此程式。</span><span class="sxs-lookup"><span data-stu-id="f7113-107">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="f7113-108">修改封存路徑</span><span class="sxs-lookup"><span data-stu-id="f7113-108">To modify the archive path</span></span>**

1.  <span data-ttu-id="f7113-109">在已安裝 Microsoft 高級群組原則管理-伺服器的電腦上，按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**新增或移除程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7113-109">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="f7113-110">按一下 [ **Microsoft 高級群組原則管理-伺服器**]，然後按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="f7113-110">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="f7113-111">按一下 **[下一步]**，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="f7113-111">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="f7113-112">依照螢幕上的指示來設定 AGPM 服務的設定：</span><span class="sxs-lookup"><span data-stu-id="f7113-112">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="f7113-113">針對封存路徑，針對 AGPM 服務器輸入封存的新位置。</span><span class="sxs-lookup"><span data-stu-id="f7113-113">For the archive path, enter a new location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="f7113-114">封存路徑可以指向 AGPM 服務器或其他位置的資料夾，但該位置應該有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="f7113-114">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="f7113-115">輸入 AGPM 服務帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="f7113-115">Enter credentials for the AGPM Service Account.</span></span>

        <span data-ttu-id="f7113-116">**重要** 修改安裝會清除 AGPM 服務帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="f7113-116">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="f7113-117">您必須重新輸入認證，但不需要符合在原始安裝期間所使用的認證。</span><span class="sxs-lookup"><span data-stu-id="f7113-117">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="f7113-118">AGPM 服務帳戶必須擁有它將管理之 Gpo 的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="f7113-118">The AGPM Service Account must have full access to the GPOs that it will manage.</span></span> <span data-ttu-id="f7113-119">如果您要在單一網域上管理 Gpo，您可以將 [本機系統] 帳戶設為主要網網域控制站（AGPM 服務帳戶）。</span><span class="sxs-lookup"><span data-stu-id="f7113-119">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="f7113-120">如果您要管理多個網域上的 Gpo，或如果成員伺服器將是 AGPM 服務器，您應該將另一個帳戶設定為 AGPM 服務帳戶，因為一個網網域控制站的本機系統帳戶無法存取其他網域上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="f7113-120">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="f7113-121">針對封存擁有者，輸入 AGPM 系統管理員的認證（[完全控制]）。</span><span class="sxs-lookup"><span data-stu-id="f7113-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="f7113-122">按一下 [**變更**]，完成安裝後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f7113-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="f7113-123">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="f7113-123">Additional references</span></span>

-   [<span data-ttu-id="f7113-124">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="f7113-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





