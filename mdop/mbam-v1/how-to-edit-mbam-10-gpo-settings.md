---
title: 如何編輯 MBAM 1.0 GPO 設定
description: 如何編輯 MBAM 1.0 GPO 設定
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810461"
---
# <span data-ttu-id="8f07a-103">如何編輯 MBAM 1.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="8f07a-103">How to Edit MBAM 1.0 GPO Settings</span></span>


<span data-ttu-id="8f07a-104">若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定您要在實施 Microsoft BitLocker 管理和監控時使用的群組原則。</span><span class="sxs-lookup"><span data-stu-id="8f07a-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="8f07a-105">如需各種可用原則的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f07a-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="8f07a-106">在您決定要使用的原則之後，您必須修改包含 MBAM 原則設定的一個或多個群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="8f07a-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the MBAM policy settings.</span></span>

<span data-ttu-id="8f07a-107">下列步驟說明如何設定基本的建議群組原則物件（GPO）設定，以讓 MBAM 管理貴組織用戶端電腦的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="8f07a-107">The following steps describe how to configure the basic, recommended Group Policy object (GPO) settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="8f07a-108">編輯 MBAM 用戶端 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="8f07a-108">To edit the MBAM Client GPO settings</span></span>**

1.  <span data-ttu-id="8f07a-109">在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。</span><span class="sxs-lookup"><span data-stu-id="8f07a-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="8f07a-110">使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 產品進行下列動作：選取 [電腦設定]，選擇 [**原則**]，按一下 [**系統\*\*\*\*管理範本**]，選取 [ **Windows 元件**]，然後按一下 **[MDOP MBAM （BitLocker Management）**]。</span><span class="sxs-lookup"><span data-stu-id="8f07a-110">Use the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product for these actions: Select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="8f07a-111">編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則物件設定。</span><span class="sxs-lookup"><span data-stu-id="8f07a-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="8f07a-112">針對後面的資料表中的每個原則，選取 [**原則群組**]，按一下**原則**，然後設定**設定**。</span><span class="sxs-lookup"><span data-stu-id="8f07a-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**.</span></span>

    <span data-ttu-id="8f07a-113">原則群組</span><span class="sxs-lookup"><span data-stu-id="8f07a-113">Policy Group</span></span>

    <span data-ttu-id="8f07a-114">原則</span><span class="sxs-lookup"><span data-stu-id="8f07a-114">Policy</span></span>

    <span data-ttu-id="8f07a-115">設定</span><span class="sxs-lookup"><span data-stu-id="8f07a-115">Setting</span></span>

    <span data-ttu-id="8f07a-116">用戶端管理</span><span class="sxs-lookup"><span data-stu-id="8f07a-116">Client Management</span></span>

    <span data-ttu-id="8f07a-117">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="8f07a-117">Configure MBAM Services</span></span>

    <span data-ttu-id="8f07a-118">啟用。</span><span class="sxs-lookup"><span data-stu-id="8f07a-118">Enabled.</span></span> <span data-ttu-id="8f07a-119">設定**MBAM 復原與硬體服務端點**，然後**選取要儲存的 BitLocker 復原資訊**。</span><span class="sxs-lookup"><span data-stu-id="8f07a-119">Set **MBAM Recovery and Hardware service endpoint** and **Select BitLocker recovery information to store**.</span></span>

    <span data-ttu-id="8f07a-120">設定**MBAM 合規性服務端點**，並**在（分鐘）中輸入狀態報表頻率**。</span><span class="sxs-lookup"><span data-stu-id="8f07a-120">Set **MBAM compliance service endpoint** and **Enter status report frequency in (minutes)**.</span></span>

    <span data-ttu-id="8f07a-121">允許硬體相容性檢查</span><span class="sxs-lookup"><span data-stu-id="8f07a-121">Allow hardware compatibility checking</span></span>

    <span data-ttu-id="8f07a-122">已停用。</span><span class="sxs-lookup"><span data-stu-id="8f07a-122">Disabled.</span></span> <span data-ttu-id="8f07a-123">預設會啟用此原則，但基本 MBAM 實現不需要此原則。</span><span class="sxs-lookup"><span data-stu-id="8f07a-123">This policy is enabled by default, but is not needed for a basic MBAM implementation.</span></span>

    <span data-ttu-id="8f07a-124">作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="8f07a-124">Operating System Drive</span></span>

    <span data-ttu-id="8f07a-125">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="8f07a-125">Operating system drive encryption settings</span></span>

    <span data-ttu-id="8f07a-126">啟用。</span><span class="sxs-lookup"><span data-stu-id="8f07a-126">Enabled.</span></span> <span data-ttu-id="8f07a-127">**針對作業系統磁片磁碟機設定 [選取保護**器]。</span><span class="sxs-lookup"><span data-stu-id="8f07a-127">Set **Select protector for operating system drive**.</span></span> <span data-ttu-id="8f07a-128">若要將作業系統磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，必須這麼做。</span><span class="sxs-lookup"><span data-stu-id="8f07a-128">This is required to save operating system drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="8f07a-129">抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="8f07a-129">Removable Drive</span></span>

    <span data-ttu-id="8f07a-130">在抽取式磁碟磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="8f07a-130">Control Use of BitLocker on removable drives</span></span>

    <span data-ttu-id="8f07a-131">啟用。</span><span class="sxs-lookup"><span data-stu-id="8f07a-131">Enabled.</span></span> <span data-ttu-id="8f07a-132">如果 MBAM 會將抽取式磁碟磁碟機資料儲存到 MBAM 金鑰復原伺服器，就是必要的。</span><span class="sxs-lookup"><span data-stu-id="8f07a-132">This is required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="8f07a-133">固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="8f07a-133">Fixed Drive</span></span>

    <span data-ttu-id="8f07a-134">在固定磁片磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="8f07a-134">Control Use of BitLocker on fixed drives</span></span>

    <span data-ttu-id="8f07a-135">啟用。</span><span class="sxs-lookup"><span data-stu-id="8f07a-135">Enabled.</span></span> <span data-ttu-id="8f07a-136">如果 MBAM 會將固定磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，則需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="8f07a-136">This is required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="8f07a-137">您**可以選擇如何復原受 BitLocker 保護的磁碟機**，以及**允許資料修復代理程式**。</span><span class="sxs-lookup"><span data-stu-id="8f07a-137">Set **Choose how BitLocker-protected drives can be recovered** and **Allow data recovery agent**.</span></span>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="8f07a-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f07a-138">Related topics</span></span>


[<span data-ttu-id="8f07a-139">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="8f07a-139">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)









