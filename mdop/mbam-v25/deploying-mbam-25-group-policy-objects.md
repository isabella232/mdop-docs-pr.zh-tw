---
title: 部署 MBAM 2.5 群組原則物件
description: 部署 MBAM 2.5 群組原則物件
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810526"
---
# <span data-ttu-id="ce014-103">部署 MBAM 2.5 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="ce014-103">Deploying MBAM 2.5 Group Policy Objects</span></span>


<span data-ttu-id="ce014-104">若要部署 MBAM，您必須設定定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的 [組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="ce014-104">To deploy MBAM, you have to set Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="ce014-105">若要完成這項工作，您必須將 MBAM 群組原則範本複製到能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的伺服器或工作站，然後編輯設定。</span><span class="sxs-lookup"><span data-stu-id="ce014-105">To complete this task, you must copy the MBAM Group Policy Templates to a server or workstation that are capable of running Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM), and then edit the settings.</span></span>

<span data-ttu-id="ce014-106">**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="ce014-106">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="ce014-107">當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。</span><span class="sxs-lookup"><span data-stu-id="ce014-107">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

## <span data-ttu-id="ce014-108">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="ce014-108">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="ce014-109">在您安裝 MBAM 用戶端之前，您必須將 MBAM 專用的群組原則物件（Gpo）複製到管理工作站。</span><span class="sxs-lookup"><span data-stu-id="ce014-109">Before you install the MBAM Client, you must copy MBAM-specific Group Policy Objects (GPOs) to the Management Workstation.</span></span> <span data-ttu-id="ce014-110">這些 Gpo 定義 BitLocker 磁片磁碟機加密的 MBAM 實現設定。</span><span class="sxs-lookup"><span data-stu-id="ce014-110">These GPOs define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="ce014-111">您可以將群組原則範本複製到任何支援 Windows server 或用戶端電腦的伺服器或工作站，且能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="ce014-111">You can copy the Group Policy templates to any server or workstation that is a supported Windows server or client computer and that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="ce014-112">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="ce014-112">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

## <span data-ttu-id="ce014-113">編輯 MBAM 2.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="ce014-113">Editing MBAM 2.0 GPO settings</span></span>


<span data-ttu-id="ce014-114">在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="ce014-114">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span> <span data-ttu-id="ce014-115">若要查看和建立 Gpo，您必須已安裝群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="ce014-115">To view and create GPOs, you must have Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) installed.</span></span>

[<span data-ttu-id="ce014-116">編輯 MBAM 2.5 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="ce014-116">Editing the MBAM 2.5 Group Policy Settings</span></span>](editing-the-mbam-25-group-policy-settings.md)

## <span data-ttu-id="ce014-117">顯示或隱藏 Windows [控制台] 中的 [MBAM] 控制台</span><span class="sxs-lookup"><span data-stu-id="ce014-117">Showing or hiding the MBAM Control Panel in Windows Control Panel</span></span>


<span data-ttu-id="ce014-118">因為 MBAM 提供自訂的 MBAM 控制台，可以取代預設的 Windows BitLocker [控制台]，您也可以選擇使用 [群組原則] 設定來顯示或隱藏最終使用者的預設 BitLocker 控制台。</span><span class="sxs-lookup"><span data-stu-id="ce014-118">Since MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to show or hide the default BitLocker Control Panel from end users by using Group Policy settings.</span></span>

[<span data-ttu-id="ce014-119">隱藏控制台中預設的 BitLocker 磁碟機加密項目</span><span class="sxs-lookup"><span data-stu-id="ce014-119">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## <span data-ttu-id="ce014-120">部署 MBAM 2.0 群組原則物件的其他資源</span><span class="sxs-lookup"><span data-stu-id="ce014-120">Other Resources for deploying MBAM 2.0 Group Policy Objects</span></span>


[<span data-ttu-id="ce014-121">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="ce014-121">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

## <span data-ttu-id="ce014-122">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="ce014-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ce014-123">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ce014-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ce014-124">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="ce014-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





