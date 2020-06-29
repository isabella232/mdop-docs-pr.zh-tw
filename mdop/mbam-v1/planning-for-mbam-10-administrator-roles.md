---
title: MBAM 1.0 系統管理員角色規劃
description: MBAM 1.0 系統管理員角色規劃
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811426"
---
# <span data-ttu-id="94dcf-103">MBAM 1.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="94dcf-103">Planning for MBAM 1.0 Administrator Roles</span></span>


<span data-ttu-id="94dcf-104">本主題包含並說明 Microsoft BitLocker 管理和監控（MBAM）中可用的系統管理員角色，以及建立本機群組的伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="94dcf-104">This topic includes and describes the administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM), as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="94dcf-105">MBAM 管理員角色</span><span class="sxs-lookup"><span data-stu-id="94dcf-105">MBAM Administrator roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="94dcf-106">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="94dcf-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="94dcf-107">這個角色的管理員可以存取所有的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="94dcf-107">Administrators in this role have access to all MBAM features.</span></span> <span data-ttu-id="94dcf-108">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="94dcf-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-hardware-users"></a> **<span data-ttu-id="94dcf-109">MBAM 硬體使用者</span><span class="sxs-lookup"><span data-stu-id="94dcf-109">MBAM Hardware Users</span></span>**  
<span data-ttu-id="94dcf-110">此角色的系統管理員可以存取 MBAM 中的硬體功能功能。</span><span class="sxs-lookup"><span data-stu-id="94dcf-110">Administrators in this role have access to the Hardware Capability features from MBAM.</span></span> <span data-ttu-id="94dcf-111">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="94dcf-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="94dcf-112">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="94dcf-112">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="94dcf-113">此角色的系統管理員可從 MBAM 存取技術支援人員的功能。</span><span class="sxs-lookup"><span data-stu-id="94dcf-113">Administrators in this role have access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="94dcf-114">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="94dcf-114">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam--report-users"></a> **<span data-ttu-id="94dcf-115">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="94dcf-115">MBAM Report Users</span></span>**  
<span data-ttu-id="94dcf-116">此角色的管理員可從 MBAM 存取合規性和審核報告功能。</span><span class="sxs-lookup"><span data-stu-id="94dcf-116">Administrators in this role have access to the Compliance and Audit Reports feature from MBAM.</span></span> <span data-ttu-id="94dcf-117">此角色的本機群組已安裝在管理和監控伺服器、合規性與審核資料庫，以及託管合規性與審核報告的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="94dcf-117">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **<span data-ttu-id="94dcf-118">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="94dcf-118">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="94dcf-119">此角色的系統管理員已提升從 MBAM 到技術支援人員功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="94dcf-119">Administrators in this role have increased access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="94dcf-120">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="94dcf-120">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="94dcf-121">如果使用者是 MBAM 技術支援人員的成員，且 MBAM 高級技術支援人員的使用者，則 MBAM [高級技術支援人員] 的許可權會覆寫 MBAM 的 [支援人員] 使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="94dcf-121">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will overwrite the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="94dcf-122">**重要** 若要查看報表，系統管理使用者必須是 [管理與監控伺服器]、[合規性] 和 [審核資料庫] 中的**MBAM 報表使用者**安全性群組成員，以及託管合規性與報告功能的伺服器。</span><span class="sxs-lookup"><span data-stu-id="94dcf-122">**Important** To view the reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Reports feature.</span></span> <span data-ttu-id="94dcf-123">最佳做法是在 Active Directory 中建立一個安全性群組，並在 [管理] 和 [監視] 伺服器以及託管合規性與報告的伺服器上，以許可權在 [管理員] 和 [監視] 伺服器上的 [**使用者**安全性群組] 中建立。</span><span class="sxs-lookup"><span data-stu-id="94dcf-123">As a best practice, create a security group in Active Directory with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and on the server that hosts the Compliance and Reports.</span></span>

 

## <span data-ttu-id="94dcf-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="94dcf-124">Related topics</span></span>


[<span data-ttu-id="94dcf-125">MBAM 1.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="94dcf-125">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)

 

 





