---
title: 僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
description: 僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800125"
---
# <span data-ttu-id="dbe41-103">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</span><span class="sxs-lookup"><span data-stu-id="dbe41-103">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="dbe41-104">如果您是使用 System Center Configuration Manager 整合功能安裝 Microsoft BitLocker 管理和監控（MBAM）2.5，您必須完成本主題所述的先決條件，以及[適用于獨立與 Configuration Manager 整合拓朴的 MBAM 2.5 伺服器先決條件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="dbe41-104">If you are installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 by using the System Center Configuration Manager Integration feature, you must complete the prerequisites described in this topic, in addition to those in [MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md).</span></span> <span data-ttu-id="dbe41-105">您也必須建立或修改 Configuration Manager 整合拓朴所需的 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="dbe41-105">You must also create or modify .mof files that are needed for the Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="dbe41-106">Configuration Manager 整合功能的必要條件</span><span class="sxs-lookup"><span data-stu-id="dbe41-106">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="dbe41-107">如果您是使用 System Center Configuration Manager 整合拓朴來設定 MBAM，則必須完成 Configuration Manager 所需的其他先決條件。</span><span class="sxs-lookup"><span data-stu-id="dbe41-107">If you are configuring MBAM with the System Center Configuration Manager Integration topology, you must complete additional prerequisites that are required for Configuration Manager.</span></span>

[<span data-ttu-id="dbe41-108">Configuration Manager 整合功能的必要條件</span><span class="sxs-lookup"><span data-stu-id="dbe41-108">Prerequisites for the Configuration Manager Integration Feature</span></span>](prerequisites-for-the-configuration-manager-integration-feature.md)

## <span data-ttu-id="dbe41-109">編輯 Configuration （mof）檔案</span><span class="sxs-lookup"><span data-stu-id="dbe41-109">Edit the Configuration.mof file</span></span>


<span data-ttu-id="dbe41-110">若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 Configuration. SystemCenter2012 ConfigurationManager 和 Microsoft System Center Configuration Manager 2007 的 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="dbe41-110">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager Reports, you have to edit the Configuration.mof file for SystemCenter2012 ConfigurationManager and Microsoft System Center Configuration Manager 2007.</span></span>

[<span data-ttu-id="dbe41-111">編輯 Configuration.mof 檔案</span><span class="sxs-lookup"><span data-stu-id="dbe41-111">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a><span data-ttu-id="dbe41-112">建立或編輯 Sms \ _def 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="dbe41-112">Create or edit the Sms\_def.mof file</span></span>


<span data-ttu-id="dbe41-113">若要讓用戶端電腦在 MBAM Configuration Manager 報告中報告 BitLocker 相容性詳細資料，您必須建立或編輯 Sms \ _def. mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="dbe41-113">To enable the client computers to report BitLocker compliance details in the MBAM Configuration Manager Reports, you have to create or edit the Sms\_def.mof file.</span></span> <span data-ttu-id="dbe41-114">如果您使用的是 SystemCenter2012 ConfigurationManager，則必須建立檔案。</span><span class="sxs-lookup"><span data-stu-id="dbe41-114">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span> <span data-ttu-id="dbe41-115">在 Configuration Manager 2007 中，檔案已經存在，因此您必須編輯現有的檔案，但不需要覆寫該檔案。</span><span class="sxs-lookup"><span data-stu-id="dbe41-115">In Configuration Manager 2007, the file already exists, so you need to edit, but not overwrite, the existing file.</span></span>

[<span data-ttu-id="dbe41-116">建立或編輯 Sms \ _def 的 mof 檔案</span><span class="sxs-lookup"><span data-stu-id="dbe41-116">Create or Edit the Sms\_def.mof File</span></span>](create-or-edit-the-sms-defmof-file-mbam-25.md)


## <span data-ttu-id="dbe41-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="dbe41-117">Related topics</span></span>


[<span data-ttu-id="dbe41-118">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="dbe41-118">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="dbe41-119">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="dbe41-119">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="dbe41-120">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="dbe41-120">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="dbe41-121">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="dbe41-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="dbe41-122">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="dbe41-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="dbe41-123">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="dbe41-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




