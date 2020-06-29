---
title: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
description: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
author: dansimp
ms.assetid: f32927a2-4c05-4da8-acca-1108d1dfdb7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4f8597cc182c037983a89efd60c5ef935712ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811217"
---
# <span data-ttu-id="c68ba-103">如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="c68ba-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="c68ba-104">Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="c68ba-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="c68ba-105">您可以透過工具（例如 Active Directory 網域服務或企業軟體部署工具（例如 MicrosoftSystemCenter2012 ConfigurationManager）部署用戶端，將 MBAM 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="c68ba-105">The MBAM Client can be integrated into an organization by deploying the client through tools, such as Active Directory Domain Services or an enterprise software deployment tool such as MicrosoftSystemCenter2012 ConfigurationManager.</span></span>

<span data-ttu-id="c68ba-106">**記事** 若要查看 MBAM 用戶端系統需求，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="c68ba-106">**Note** To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

**<span data-ttu-id="c68ba-107">若要將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="c68ba-107">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="c68ba-108">找出 MBAM 軟體隨附的 MBAM 用戶端安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="c68ba-108">Locate the MBAM Client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="c68ba-109">使用 Active Directory 網域服務或企業軟體部署工具（例如 MicrosoftSystemCenter2012 ConfigurationManager），將 Windows Installer 套件部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="c68ba-109">Deploy the Windows Installer package to target computers by using Active Directory Domain Services or an enterprise software deployment tool, such as MicrosoftSystemCenter2012 ConfigurationManager.</span></span>

    <span data-ttu-id="c68ba-110">**記事** 您不應該使用 [群組原則] 來部署 Windows 安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="c68ba-110">**Note** You should not use Group Policy to deploy the Windows Installer package.</span></span>

     

3.  <span data-ttu-id="c68ba-111">設定 [發佈設定] 或 [群組原則]，以執行 MBAM 用戶端安裝檔。</span><span class="sxs-lookup"><span data-stu-id="c68ba-111">Configure the distribution settings or Group Policy to run the MBAM Client installation file.</span></span> <span data-ttu-id="c68ba-112">成功安裝之後，MBAM 用戶端會套用從網網域控制站接收的群組原則設定，以開始 BitLocker 加密和管理功能。</span><span class="sxs-lookup"><span data-stu-id="c68ba-112">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker encryption and management functions.</span></span> <span data-ttu-id="c68ba-113">如需 MBAM 群組原則設定的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c68ba-113">For more information about MBAM Group Policy settings, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span>

    <span data-ttu-id="c68ba-114">**重要** 如果遠端桌面通訊協定連線處於作用中狀態，則 MBAM 用戶端將無法啟動 BitLocker 加密動作。</span><span class="sxs-lookup"><span data-stu-id="c68ba-114">**Important** The MBAM Client will not start BitLocker encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="c68ba-115">必須先關閉所有遠端主控台連線，才能開始 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="c68ba-115">All remote console connections must be closed before BitLocker encryption will begin.</span></span>

     

## <span data-ttu-id="c68ba-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="c68ba-116">Related topics</span></span>


[<span data-ttu-id="c68ba-117">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="c68ba-117">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)

 

 





