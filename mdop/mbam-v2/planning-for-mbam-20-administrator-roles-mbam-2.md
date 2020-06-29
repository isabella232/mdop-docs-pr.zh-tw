---
title: MBAM 2.0 系統管理員角色規劃
description: MBAM 2.0 系統管理員角色規劃
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810827"
---
# <span data-ttu-id="a442b-103">MBAM 2.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="a442b-103">Planning for MBAM 2.0 Administrator Roles</span></span>


<span data-ttu-id="a442b-104">本主題列出並說明 Microsoft BitLocker 管理和監控（MBAM）中可用的系統管理員角色，以及建立本機群組的伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="a442b-104">This topic lists and describes the available administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM) as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="a442b-105">MBAM 管理員角色</span><span class="sxs-lookup"><span data-stu-id="a442b-105">MBAM Administrator Roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="a442b-106">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="a442b-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="a442b-107">此角色的管理員可以存取所有 Microsoft BitLocker 管理和監控功能。</span><span class="sxs-lookup"><span data-stu-id="a442b-107">Administrators in this role have access to all Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="a442b-108">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a442b-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="a442b-109">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="a442b-109">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="a442b-110">此角色的管理員可從 MBAM 存取技術支援人員的功能。</span><span class="sxs-lookup"><span data-stu-id="a442b-110">Administrators in this role have access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="a442b-111">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a442b-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-report-users"></a> **<span data-ttu-id="a442b-112">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="a442b-112">MBAM Report Users</span></span>**  
<span data-ttu-id="a442b-113">此角色的管理員可以存取 MBAM 的合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="a442b-113">Administrators in this role have access to the Compliance and Audit Reports from MBAM.</span></span> <span data-ttu-id="a442b-114">此角色的本機群組已安裝在管理和監控伺服器、合規性與審核資料庫，以及託管合規性與審核報告的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a442b-114">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **<span data-ttu-id="a442b-115">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="a442b-115">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="a442b-116">此角色的系統管理員已增加從 MBAM 存取服務台功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="a442b-116">Administrators in this role have increased access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="a442b-117">此角色的本機群組已安裝在管理和監視伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a442b-117">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="a442b-118">如果使用者是 MBAM 技術支援人員的成員，且 MBAM 高級技術支援人員的使用者，則 MBAM [高級技術支援人員] 的許可權會覆寫 MBAM 的 [支援人員] 使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="a442b-118">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will override the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="a442b-119">**重要** 若要查看報表，系統管理使用者必須是管理和監控伺服器、合規性和審核資料庫，以及託管合規性和審核報告功能之伺服器上的**MBAM Report 使用者**安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a442b-119">**Important** To view reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports feature.</span></span> <span data-ttu-id="a442b-120">最佳做法是在 Active Directory 網域服務中使用本機**MBAM 報表**上的許可權，在管理與監視伺服器以及託管合規性和審核報告的伺服器上，建立具有許可權的使用者安全性群組。</span><span class="sxs-lookup"><span data-stu-id="a442b-120">As a best practice, create a security group in Active Directory Domain Services with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and the server that hosts the Compliance and Audit Reports.</span></span>

 

## <span data-ttu-id="a442b-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="a442b-121">Related topics</span></span>


[<span data-ttu-id="a442b-122">MBAM 2.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="a442b-122">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





