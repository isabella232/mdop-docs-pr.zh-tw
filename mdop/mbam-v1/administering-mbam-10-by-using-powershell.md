---
title: 使用 PowerShell 管理 MBAM 1.0
description: 使用 PowerShell 管理 MBAM 1.0
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810976"
---
# <span data-ttu-id="667bf-103">使用 PowerShell 管理 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="667bf-103">Administering MBAM 1.0 by Using PowerShell</span></span>


<span data-ttu-id="667bf-104">Microsoft BitLocker 管理與監控（MBAM）提供下列所列的 Windows PowerShell Cmdlet 集合。</span><span class="sxs-lookup"><span data-stu-id="667bf-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="667bf-105">系統管理員可以使用這些 PowerShell Cmdlet，從命令提示字元執行各種 MBAM 伺服器工作，而不是從 MBAM 管理網站執行。</span><span class="sxs-lookup"><span data-stu-id="667bf-105">Administrators can use these PowerShell cmdlets to perform various MBAM server tasks from the command prompt rather than from the MBAM administration website.</span></span>

## <span data-ttu-id="667bf-106">如何使用 PowerShell 管理 MBAM</span><span class="sxs-lookup"><span data-stu-id="667bf-106">How to administer MBAM by using PowerShell</span></span>


<span data-ttu-id="667bf-107">使用這裡所述的 PowerShell Cmdlet 來管理 MBAM。</span><span class="sxs-lookup"><span data-stu-id="667bf-107">Use the PowerShell cmdlets described here to administer MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="667bf-108">名稱</span><span class="sxs-lookup"><span data-stu-id="667bf-108">Name</span></span></th>
<th align="left"><span data-ttu-id="667bf-109">描述</span><span class="sxs-lookup"><span data-stu-id="667bf-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="667bf-110">附加 MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="667bf-110">Add-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-111">將新的硬體模型新增至 MBAM 硬體清單。</span><span class="sxs-lookup"><span data-stu-id="667bf-111">Adds a new hardware model to the MBAM hardware inventory.</span></span> <span data-ttu-id="667bf-112">這個 Cmdlet 也可以指定是否支援或不支援 BitLocker 磁片磁碟機加密的硬體。</span><span class="sxs-lookup"><span data-stu-id="667bf-112">This cmdlet can also specify whether the hardware is supported or unsupported for BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="667bf-113">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="667bf-113">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-114">要求可讓使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="667bf-114">Requests an MBAM recovery key that will enable a user to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="667bf-115">MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="667bf-115">Get-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-116">取得含有資料的主硬體清單，指出硬體模型相容性或與 BitLocker 磁片磁碟機加密不相容。</span><span class="sxs-lookup"><span data-stu-id="667bf-116">Gets a master hardware inventory that contains data that indicates whether hardware models are compatible or incompatible with BitLocker drive encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="667bf-117">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="667bf-117">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-118">為使用者提供 TPM 擁有者密碼來管理其 TPM （受信任的平臺模組）存取權。</span><span class="sxs-lookup"><span data-stu-id="667bf-118">Provides a TPM owner password for a user to manage their TPM (Trusted Platform Module) access.</span></span> <span data-ttu-id="667bf-119">可在 TPM 已鎖定並將不再接受其 PIN 時，協助使用者。</span><span class="sxs-lookup"><span data-stu-id="667bf-119">Helps users when TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="667bf-120">安裝-Mbam</span><span class="sxs-lookup"><span data-stu-id="667bf-120">Install-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-121">安裝可提供高級群組原則、加密、金鑰復原及合規性報告工具的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="667bf-121">Installs MBAM features that provide advanced group policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="667bf-122">移除-MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="667bf-122">Remove-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-123">從硬體清點移除硬體模型。</span><span class="sxs-lookup"><span data-stu-id="667bf-123">Removes the hardware models from the hardware inventory.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="667bf-124">Set-MbamHardwareType</span><span class="sxs-lookup"><span data-stu-id="667bf-124">Set-MbamHardwareType</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-125">允許管理主要硬體清查，以指定硬體模型是否可以執行 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="667bf-125">Allows management of a master hardware inventory to designate whether or not hardware models are capable or incapable to perform BitLocker encryption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="667bf-126">卸載-Mbam</span><span class="sxs-lookup"><span data-stu-id="667bf-126">Uninstall-Mbam</span></span></p></td>
<td align="left"><p><span data-ttu-id="667bf-127">移除先前安裝的 MBAM 功能，提供高級原則、加密、金鑰復原及合規性報告工具。</span><span class="sxs-lookup"><span data-stu-id="667bf-127">Removes previously installed MBAM features that provide advanced policy, encryption, key recovery, and compliance reporting tools.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="667bf-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="667bf-128">Related topics</span></span>


[<span data-ttu-id="667bf-129">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="667bf-129">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





