---
title: 判斷裝置為何收到不合規的訊息
description: 判斷裝置為何收到不合規的訊息
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810635"
---
# <span data-ttu-id="3d74a-103">判斷裝置為何收到不合規的訊息</span><span class="sxs-lookup"><span data-stu-id="3d74a-103">Determining why a Device Receives a Noncompliance Message</span></span>


<span data-ttu-id="3d74a-104">WMI 提供下列不相容程式碼，並說明 MBAM 為不符合的特定裝置所報告的原因。</span><span class="sxs-lookup"><span data-stu-id="3d74a-104">The following noncompliance codes are provided by WMI and describe the reasons why a particular device is reported by MBAM as noncompliant.</span></span>

<span data-ttu-id="3d74a-105">您可以使用您慣用的方法來查看 WMI。</span><span class="sxs-lookup"><span data-stu-id="3d74a-105">You can use your preferred method to view WMI.</span></span> <span data-ttu-id="3d74a-106">如果您使用的是 PowerShell，請 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` 從 PowerShell 提示執行，然後搜尋 ReasonsForNoncompliance。</span><span class="sxs-lookup"><span data-stu-id="3d74a-106">If you use PowerShell, run `gwmi -class mbam_volume -Namespace root\microsoft\mbam` from a PowerShell prompt and search for ReasonsForNoncompliance.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3d74a-107">不合規性程式碼</span><span class="sxs-lookup"><span data-stu-id="3d74a-107">Non-Compliance Code</span></span></th>
<th align="left"><span data-ttu-id="3d74a-108">違反規範的原因</span><span class="sxs-lookup"><span data-stu-id="3d74a-108">Reason for Non-Compliance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-109">0</span><span class="sxs-lookup"><span data-stu-id="3d74a-109">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-110">密碼強度不是 AES 256。</span><span class="sxs-lookup"><span data-stu-id="3d74a-110">Cipher strength not AES 256.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-111">sr-1</span><span class="sxs-lookup"><span data-stu-id="3d74a-111">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-112">MBAM 原則需要加密這個卷，但不需要加密。</span><span class="sxs-lookup"><span data-stu-id="3d74a-112">MBAM Policy requires this volume to be encrypted but it is not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-113">pplx-2</span><span class="sxs-lookup"><span data-stu-id="3d74a-113">2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-114">MBAM 原則需要此卷沒有加密，但它是。</span><span class="sxs-lookup"><span data-stu-id="3d74a-114">MBAM Policy requires this volume to NOT be encrypted, but it is.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-115">3</span><span class="sxs-lookup"><span data-stu-id="3d74a-115">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-116">MBAM 原則需要這個大量的磁片才能使用 TPM 保護器，但不需要。</span><span class="sxs-lookup"><span data-stu-id="3d74a-116">MBAM Policy requires this volume use a TPM protector, but it does not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-117">4</span><span class="sxs-lookup"><span data-stu-id="3d74a-117">4</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-118">MBAM 原則需要此大量的磁片才能使用 TPM + PIN 保護器，但不需要。</span><span class="sxs-lookup"><span data-stu-id="3d74a-118">MBAM Policy requires this volume use a TPM+PIN protector, but it does not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-119">500</span><span class="sxs-lookup"><span data-stu-id="3d74a-119">5</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-120">MBAM 原則不允許非 TPM 電腦報告為合規性。</span><span class="sxs-lookup"><span data-stu-id="3d74a-120">MBAM Policy does not allow non TPM machines to report as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-121">6</span><span class="sxs-lookup"><span data-stu-id="3d74a-121">6</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-122">Volume 有 TPM 保護器，但看不到 TPM （在 BIOS 中停用 TPM 之後，以復原金鑰啟動）。</span><span class="sxs-lookup"><span data-stu-id="3d74a-122">Volume has a TPM protector but the TPM is not visible (booted with recover key after disabling TPM in BIOS?).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-123">utf-7</span><span class="sxs-lookup"><span data-stu-id="3d74a-123">7</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-124">MBAM 原則需要使用密碼保護器，但沒有密碼保護器。</span><span class="sxs-lookup"><span data-stu-id="3d74a-124">MBAM Policy requires this volume use a password protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-125">型</span><span class="sxs-lookup"><span data-stu-id="3d74a-125">8</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-126">MBAM 原則需要此磁片卷不使用密碼保護器，但有一個密碼保護器。</span><span class="sxs-lookup"><span data-stu-id="3d74a-126">MBAM Policy requires this volume NOT use a password protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-127">9</span><span class="sxs-lookup"><span data-stu-id="3d74a-127">9</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-128">MBAM 原則需要使用自動解除鎖定的保護器，但沒有任何一個。</span><span class="sxs-lookup"><span data-stu-id="3d74a-128">MBAM Policy requires this volume use an auto-unlock protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-129">第</span><span class="sxs-lookup"><span data-stu-id="3d74a-129">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-130">MBAM 原則需要此磁片卷不使用自動解除鎖定保護器，但有一個。</span><span class="sxs-lookup"><span data-stu-id="3d74a-130">MBAM Policy requires this volume NOT use an auto-unlock protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-131">11</span><span class="sxs-lookup"><span data-stu-id="3d74a-131">11</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-132">偵測到原則衝突，防止 MBAM 將此卷報告為合規性。</span><span class="sxs-lookup"><span data-stu-id="3d74a-132">Policy conflict detected preventing MBAM from reporting this volume as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-133">之間</span><span class="sxs-lookup"><span data-stu-id="3d74a-133">12</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-134">需要系統磁碟區來加密作業系統，但不存在。</span><span class="sxs-lookup"><span data-stu-id="3d74a-134">A system volume is needed to encrypt the OS volume but it is not present.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-135">合</span><span class="sxs-lookup"><span data-stu-id="3d74a-135">13</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-136">已針對該卷暫停保護。</span><span class="sxs-lookup"><span data-stu-id="3d74a-136">Protection is suspended for the volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-137">4</span><span class="sxs-lookup"><span data-stu-id="3d74a-137">14</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-138">除非 OS 卷已加密，否則 AutoUnlock 不安全。</span><span class="sxs-lookup"><span data-stu-id="3d74a-138">AutoUnlock unsafe unless the OS volume is encrypted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3d74a-139">工資</span><span class="sxs-lookup"><span data-stu-id="3d74a-139">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-140">原則需要最小 cypher 強度為 XTS-AES-128 位，實際 cypher 強度弱。</span><span class="sxs-lookup"><span data-stu-id="3d74a-140">Policy requires minimum cypher strength is XTS-AES-128 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3d74a-141">位</span><span class="sxs-lookup"><span data-stu-id="3d74a-141">16</span></span></p></td>
<td align="left"><p><span data-ttu-id="3d74a-142">原則需要最小 cypher 強度為 XTS-AES-256 位，實際 cypher 強度弱。</span><span class="sxs-lookup"><span data-stu-id="3d74a-142">Policy requires minimum cypher strength is XTS-AES-256 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3d74a-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="3d74a-143">Related topics</span></span>


[<span data-ttu-id="3d74a-144">MBAM 2.5 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="3d74a-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="3d74a-145">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="3d74a-145">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## <span data-ttu-id="3d74a-146">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3d74a-146">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3d74a-147">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3d74a-147">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3d74a-148">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3d74a-148">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





