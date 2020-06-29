---
title: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
description: 如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810580"
---
# <span data-ttu-id="b27d1-103">如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b27d1-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="b27d1-104">本主題說明如何將 MBAM 用戶端部署到終端使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="b27d1-104">This topic explains how to deploy the MBAM Client to end users’ computers.</span></span> <span data-ttu-id="b27d1-105">您可以透過電子軟體發佈系統（例如 Active Directory 網域服務或 MicrosoftSystemCenterConfiguration 管理員）部署 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b27d1-105">You can deploy the MBAM Client through an electronic software distribution system, such as Active Directory Domain Services or MicrosoftSystemCenterConfiguration Manager.</span></span>

<span data-ttu-id="b27d1-106">若要將 MBAM 用戶端部署為 Windows 部署的一部分，請參閱[如何使用 MBAM 來啟用 BitLocker，做為 Windows 部署的一部分](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="b27d1-106">To deploy the MBAM Client as part of a Windows deployment, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md).</span></span>

<span data-ttu-id="b27d1-107">在您開始 MBAM 用戶端部署之前，請先查看[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="b27d1-107">Before you start the MBAM Client deployment, review the [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="b27d1-108">若要將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="b27d1-108">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="b27d1-109">找出 MBAM 軟體隨附的 MBAM 用戶端安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="b27d1-109">Locate the MBAM Client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="b27d1-110">使用 Active Directory 網域服務，或 MicrosoftSystemCenterConfiguration Manager 等企業軟體部署工具，將 Windows 安裝程式套件部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="b27d1-110">Use Active Directory Domain Services or an enterprise software deployment tool like MicrosoftSystemCenterConfiguration Manager to deploy the Windows Installer package to target computers.</span></span>

3.  <span data-ttu-id="b27d1-111">設定 [分發設定] 或 [群組原則] 設定，以執行 MBAM 用戶端安裝檔。</span><span class="sxs-lookup"><span data-stu-id="b27d1-111">Configure the distribution settings or Group Policy settings to run the MBAM Client installation file.</span></span>

    <span data-ttu-id="b27d1-112">成功安裝之後，MBAM 用戶端會套用從網網域控制站接收的群組原則設定，以開始 BitLocker 磁片磁碟機加密和管理功能。</span><span class="sxs-lookup"><span data-stu-id="b27d1-112">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker Drive Encryption and management functions.</span></span>

    <span data-ttu-id="b27d1-113">**重要** 如果遠端桌面通訊協定連線處於作用中狀態，則 MBAM 用戶端不會啟動 BitLocker 磁片磁碟機加密動作。</span><span class="sxs-lookup"><span data-stu-id="b27d1-113">**Important** The MBAM Client does not start BitLocker Drive Encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="b27d1-114">必須關閉所有遠端主控台連線，且必須先登入物理主機，然後才能開始 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="b27d1-114">All remote console connections must be closed and a user must be logged on to a physical console session before BitLocker Drive Encryption begins.</span></span>

     


## <span data-ttu-id="b27d1-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="b27d1-115">Related topics</span></span>
[<span data-ttu-id="b27d1-116">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="b27d1-116">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="b27d1-117">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="b27d1-117">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

 

## <span data-ttu-id="b27d1-118">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="b27d1-118">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b27d1-119">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b27d1-119">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b27d1-120">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="b27d1-120">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





