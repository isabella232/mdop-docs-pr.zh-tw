---
title: 如何編輯 MBAM 2.0 GPO 設定
description: 如何編輯 MBAM 2.0 GPO 設定
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810346"
---
# <span data-ttu-id="df09b-103">如何編輯 MBAM 2.0 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="df09b-103">How to Edit MBAM 2.0 GPO Settings</span></span>


<span data-ttu-id="df09b-104">若要成功部署 Microsoft BitLocker 管理和監控（MBAM），您必須先決定您要在實施 Microsoft BitLocker 管理和監控時使用的群組原則。</span><span class="sxs-lookup"><span data-stu-id="df09b-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you first have to determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="df09b-105">如需其他可用原則的詳細資訊，請參閱[規劃 MBAM 2.0 群組原則需求](planning-for-mbam-20-group-policy-requirements-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="df09b-105">See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for more information on the different policies that are available.</span></span> <span data-ttu-id="df09b-106">在您決定要使用的原則之後，您必須修改一或多個包括 MBAM 原則設定的群組原則物件（GPO）。</span><span class="sxs-lookup"><span data-stu-id="df09b-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the policy settings for MBAM.</span></span>

<span data-ttu-id="df09b-107">您可以使用下列步驟來設定基本的建議 GPO 設定，以讓 MBAM 管理貴組織用戶端電腦的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="df09b-107">You can use the following steps to configure the basic, recommended GPO settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="df09b-108">編輯 MBAM 用戶端 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="df09b-108">To Edit MBAM Client GPO Settings</span></span>**

1.  <span data-ttu-id="df09b-109">在已安裝 MBAM 群組原則範本的電腦上，請確定已啟用 MBAM 服務。</span><span class="sxs-lookup"><span data-stu-id="df09b-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="df09b-110">在已安裝 MBAM 群組原則範本的電腦上使用群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 產品，選取 [電腦設定]，選擇 [**原則**]，按一下 [**系統\*\*\*\*管理範本**]，選取 [ **Windows 元件**]，然後按一下 **[MDOP MBAM （BitLocker Management）**]。</span><span class="sxs-lookup"><span data-stu-id="df09b-110">Using the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product on a computer with the MBAM Group Policy template installed, select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="df09b-111">編輯在用戶端電腦上啟用 MBAM 用戶端服務所需的群組原則物件設定。</span><span class="sxs-lookup"><span data-stu-id="df09b-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="df09b-112">針對後面的資料表中的每個原則，選取 [**原則群組**]，按一下**原則**，然後設定**設定**：</span><span class="sxs-lookup"><span data-stu-id="df09b-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="df09b-113">原則群組</span><span class="sxs-lookup"><span data-stu-id="df09b-113">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="df09b-114">原則</span><span class="sxs-lookup"><span data-stu-id="df09b-114">Policy</span></span></th>
    <th align="left"><span data-ttu-id="df09b-115">設定</span><span class="sxs-lookup"><span data-stu-id="df09b-115">Setting</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="df09b-116">用戶端管理</span><span class="sxs-lookup"><span data-stu-id="df09b-116">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-117">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="df09b-117">Configure MBAM Services</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-118">啟用。</span><span class="sxs-lookup"><span data-stu-id="df09b-118">Enabled.</span></span> <span data-ttu-id="df09b-119">設定 <strong> MBAM 復原與硬體服務端點 </strong> ，然後 <strong> 選取要儲存的 BitLocker 復原資訊 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="df09b-119">Set <strong>MBAM Recovery and Hardware service endpoint</strong> and <strong>Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="df09b-120">設定 <strong> MBAM 合規性服務端點 </strong> ，並在（分鐘）中輸入狀態報表頻率。</span><span class="sxs-lookup"><span data-stu-id="df09b-120">Set <strong>MBAM compliance service endpoint</strong> and Enter status report frequency in (minutes).</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="df09b-121">作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="df09b-121">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-122">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="df09b-122">Operating system drive encryption settings</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-123">啟用。</span><span class="sxs-lookup"><span data-stu-id="df09b-123">Enabled.</span></span> <span data-ttu-id="df09b-124"><strong>針對作業系統磁片磁碟機設定 [選取保護器] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="df09b-124">Set <strong>Select protector for operating system drive</strong>.</span></span> <span data-ttu-id="df09b-125">需要將作業系統磁片磁碟機資料儲存至 MBAMKey 恢復伺服器。</span><span class="sxs-lookup"><span data-stu-id="df09b-125">Required to save operating system drive data to the MBAMKey Recovery server.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="df09b-126">抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="df09b-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-127">在抽取式磁碟磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="df09b-127">Control Use of BitLocker on removable drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-128">啟用。</span><span class="sxs-lookup"><span data-stu-id="df09b-128">Enabled.</span></span> <span data-ttu-id="df09b-129">如果 MBAM 會將抽取式磁碟磁碟機資料儲存至 MBAM 金鑰復原伺服器，則為必要。</span><span class="sxs-lookup"><span data-stu-id="df09b-129">Required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="df09b-130">固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="df09b-130">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-131">在固定磁片磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="df09b-131">Control Use of BitLocker on fixed drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="df09b-132">啟用。</span><span class="sxs-lookup"><span data-stu-id="df09b-132">Enabled.</span></span> <span data-ttu-id="df09b-133">如果 MBAM 會將固定磁片磁碟機資料儲存至 MBAM 金鑰復原伺服器，則為必要。</span><span class="sxs-lookup"><span data-stu-id="df09b-133">Required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span></p>
    <p><span data-ttu-id="df09b-134">您 <strong> 可以選擇如何復原受 BitLocker 保護的磁碟機 </strong> ，以及 <strong> 允許資料修復代理程式 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="df09b-134">Set <strong>Choose how BitLocker-protected drives can be recovered</strong> and <strong>Allow data recovery agent</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="df09b-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="df09b-135">Related topics</span></span>


[<span data-ttu-id="df09b-136">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="df09b-136">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)









