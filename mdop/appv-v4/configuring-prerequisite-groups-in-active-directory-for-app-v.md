---
title: 在 Active Directory 中設定 App-V 的必要群組
description: 在 Active Directory 中設定 App-V 的必要群組
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809009"
---
# <span data-ttu-id="5d6b5-103">在 Active Directory 中設定 App-V 的必要群組</span><span class="sxs-lookup"><span data-stu-id="5d6b5-103">Configuring Prerequisite Groups in Active Directory for App-V</span></span>


<span data-ttu-id="5d6b5-104">在您安裝 Microsoft Application Virtualization （App-v）管理伺服器之前，您必須在 Active Directory 中建立下列物件。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-104">Before you install the Microsoft Application Virtualization (App-V) Management Server, you must create the following objects in Active Directory.</span></span> <span data-ttu-id="5d6b5-105">App-v 使用 Active Directory 群組來控制對應用程式和管理功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-105">App-V uses Active Directory groups to control access to applications and administrative functions.</span></span> <span data-ttu-id="5d6b5-106">您將會在伺服器安裝程式中及發佈應用程式時使用這些群組。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-106">You will use these groups during the server installation process and when publishing applications.</span></span>

## <span data-ttu-id="5d6b5-107">在 Active Directory 中針對應用程式虛擬化設定必備群組</span><span class="sxs-lookup"><span data-stu-id="5d6b5-107">Configuring Prerequisite Groups in Active Directory for Application Virtualization</span></span>


<span data-ttu-id="5d6b5-108">下表列出安裝 App-v 所需的 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-108">This table lists the Active Directory groups that are required for installing App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5d6b5-109">物件</span><span class="sxs-lookup"><span data-stu-id="5d6b5-109">Object</span></span></th>
<th align="left"><span data-ttu-id="5d6b5-110">描述</span><span class="sxs-lookup"><span data-stu-id="5d6b5-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d6b5-111">組織單位（OU）</span><span class="sxs-lookup"><span data-stu-id="5d6b5-111">Organizational Unit (OU)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d6b5-112">針對應用程式 V 所需的特定群組，在 Active Directory 中建立一個 OU。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-112">Create an OU in Active Directory for the specific groups required for App-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d6b5-113">App-v 系統管理群組</span><span class="sxs-lookup"><span data-stu-id="5d6b5-113">App-V Administrative Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d6b5-114">在安裝 App-v Management Server 期間，您必須選取 Active Directory 群組，以將管理存取權控制到管理主控台。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-114">During installation of the App-V Management Server, you must select an Active Directory group to use as the App-V Administrators group to control administrative access to the Management Console.</span></span> <span data-ttu-id="5d6b5-115">針對應用程式 V 管理員建立安全性群組，並將需要使用管理主控台的每位使用者新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-115">Create a security group for App-V administrators, and add to this group every user who needs to use the Management Console.</span></span> <span data-ttu-id="5d6b5-116">您無法直接從 App-v Management Server 安裝程式建立此群組。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-116">You cannot create this group directly from the App-V Management Server installer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d6b5-117">App-v Users 群組</span><span class="sxs-lookup"><span data-stu-id="5d6b5-117">App-V Users Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d6b5-118">App-v 要求存取 App-v 函數的每個使用者帳戶，都是與單一群組相關聯的提供者原則的成員，用於一般平臺存取。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-118">App-V requires that every User account that accesses App-V functions be a member of a provider policy associated with a single group for general platform access.</span></span> <span data-ttu-id="5d6b5-119">使用現有的群組;例如，如果所有使用者都能存取 app-v，或建立新的群組，則是網域使用者。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-119">Use an existing group; for example, Domain Users, if all users are to have access to App-V, or create a new group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d6b5-120">應用程式群組</span><span class="sxs-lookup"><span data-stu-id="5d6b5-120">Application Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d6b5-121">App-v 會將適當的應用程式關聯至使用 Active Directory 群組的個別應用程式。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-121">App-V associates the right to use an individual application with an Active Directory group.</span></span> <span data-ttu-id="5d6b5-122">針對每個應用程式建立 Active Directory 群組，並視需要將使用者指派給這些群組，以控制使用者對應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="5d6b5-122">Create an Active Directory group for each application, and assign users to these groups as needed to control user access to the applications.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5d6b5-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="5d6b5-123">Related topics</span></span>


[<span data-ttu-id="5d6b5-124">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="5d6b5-124">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="5d6b5-125">如何針對 App-V Management Server 設定 Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="5d6b5-125">How to Configure Windows Server 2008 for App-V Management Servers</span></span>](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





