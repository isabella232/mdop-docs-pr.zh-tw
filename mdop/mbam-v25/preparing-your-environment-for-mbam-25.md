---
title: MBAM 2.5 的環境準備
description: MBAM 2.5 的環境準備
author: dansimp
ms.assetid: 7552ba08-9dbf-40cd-8920-203d733fd242
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b18c9853035018c2e36dd447fbf0effbf49c45cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811187"
---
# <span data-ttu-id="2ee3a-103">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="2ee3a-103">Preparing your Environment for MBAM 2.5</span></span>


<span data-ttu-id="2ee3a-104">開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您應該確定您已滿足安裝產品的先決條件。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-104">Before beginning Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should make sure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="2ee3a-105">當您知道必備的先決條件之後，您就可以高效地部署產品並啟用其功能，讓它能更有效率地支援貴組織的業務目標。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-105">When you know what the prerequisites are ahead of time, you can efficiently deploy the product and enable its features so that it most effectively supports your organization’s business objectives.</span></span>

<span data-ttu-id="2ee3a-106">如果您是使用 Configuration Manager 部署 Microsoft BitLocker 管理和監視，請確定您符合本主題稍後所列的 Configuration Manager 其他需求。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-106">If you are deploying Microsoft BitLocker Administration and Monitoring with Configuration Manager, ensure that you meet the additional requirements for Configuration Manager, which are listed later in this topic.</span></span>

## <span data-ttu-id="2ee3a-107">評審 MBAM 2.5 部署先決條件</span><span class="sxs-lookup"><span data-stu-id="2ee3a-107">Review MBAM 2.5 deployment prerequisites</span></span>


<span data-ttu-id="2ee3a-108">若要確保您的 MBAM 部署成功，請務必在安裝 MBAM 用戶端並設定 MBAM 伺服器功能之前，先查看並完成必要的軟體先決條件。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-108">To ensure that your MBAM deployment is successful, make sure that you review and complete the required software prerequisites before you install the MBAM Client and configure the MBAM Server features.</span></span>

[<span data-ttu-id="2ee3a-109">MBAM 2.5 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="2ee3a-109">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)

## <span data-ttu-id="2ee3a-110">規劃 MBAM 2.5 群組原則需求</span><span class="sxs-lookup"><span data-stu-id="2ee3a-110">Plan for MBAM 2.5 Group Policy requirements</span></span>


<span data-ttu-id="2ee3a-111">在 MBAM 可以管理企業中的用戶端之前，您必須下載並設定 MBAM 專用的群組原則範本，然後設定您想要的環境的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-111">Before MBAM can manage clients in the enterprise, you must download and configure Group Policy templates that are specific to MBAM, and then configure the Group Policy settings that you want for your environment.</span></span>

[<span data-ttu-id="2ee3a-112">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="2ee3a-112">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

## <span data-ttu-id="2ee3a-113">規劃 MBAM 2.5 角色與帳戶</span><span class="sxs-lookup"><span data-stu-id="2ee3a-113">Plan for MBAM 2.5 roles and accounts</span></span>


<span data-ttu-id="2ee3a-114">作為先決條件的一部分，您必須定義特定的角色和帳戶，這些角色和帳戶會在 MBAM 中使用，以提供對特定伺服器與功能的安全性與存取權，例如在 SQL Server 上執行的資料庫，以及在管理和監視伺服器上執行的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-114">As part of the prerequisites, you must define certain roles and accounts, which are used in MBAM to provide security and access rights to specific servers and features, such as the databases running on SQL Server and the web applications running on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="2ee3a-115">MBAM 2.5 群組與帳戶規劃</span><span class="sxs-lookup"><span data-stu-id="2ee3a-115">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)

## <span data-ttu-id="2ee3a-116">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="2ee3a-116">Other resources for MBAM planning</span></span>


[<span data-ttu-id="2ee3a-117">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="2ee3a-117">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="2ee3a-118">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="2ee3a-118">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="2ee3a-119">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="2ee3a-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2ee3a-120">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2ee3a-121">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="2ee3a-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





