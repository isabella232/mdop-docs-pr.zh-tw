---
title: 使用 PowerShell 管理 MBAM 2.0
description: 使用 PowerShell 管理 MBAM 2.0
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809993"
---
# <span data-ttu-id="4ccd6-103">使用 PowerShell 管理 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="4ccd6-103">Administering MBAM 2.0 Using PowerShell</span></span>


<span data-ttu-id="4ccd6-104">Microsoft BitLocker 管理與監控（MBAM）提供下列所列的 Windows PowerShell Cmdlet 集合。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4ccd6-105">系統管理員可以使用這些 PowerShell Cmdlet，從命令列執行各種 Microsoft BitLocker 管理及監視伺服器工作，而不是從 MBAM 管理網站執行。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-105">Administrators can use these PowerShell cmdlets to perform various Microsoft BitLocker Administration and Monitoring server tasks from the command line rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="4ccd6-106">如何使用 PowerShell 管理 MBAM</span><span class="sxs-lookup"><span data-stu-id="4ccd6-106">How to Administer MBAM Using PowerShell</span></span>


<span data-ttu-id="4ccd6-107">使用這裡所述的 PowerShell Cmdlet 來管理 MBAM。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ccd6-108">名稱</span><span class="sxs-lookup"><span data-stu-id="4ccd6-108">Name</span></span></th>
<th align="left"><span data-ttu-id="4ccd6-109">描述</span><span class="sxs-lookup"><span data-stu-id="4ccd6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ccd6-110">安裝-Mbam</span><span class="sxs-lookup"><span data-stu-id="4ccd6-110">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ccd6-111">安裝提供高級原則、加密、金鑰復原及合規性報告的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-111">Installs the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ccd6-112">卸載-Mbam</span><span class="sxs-lookup"><span data-stu-id="4ccd6-112">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ccd6-113">移除提供高級原則、加密、金鑰復原及合規性報告工具的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-113">Removes the MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ccd6-114">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="4ccd6-114">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ccd6-115">要求能讓使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-115">Requests an MBAM recovery key that will enable users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ccd6-116">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="4ccd6-116">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ccd6-117">提供擁有 TPM 擁有者密碼的使用者，這些密碼可用來解除鎖定受信任的平臺模組（TPM），而 TPM 已將它們鎖定並將不再接受其 PIN。</span><span class="sxs-lookup"><span data-stu-id="4ccd6-117">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4ccd6-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="4ccd6-118">Related topics</span></span>


[<span data-ttu-id="4ccd6-119">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="4ccd6-119">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





