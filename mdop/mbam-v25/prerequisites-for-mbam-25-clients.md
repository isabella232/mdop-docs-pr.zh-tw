---
title: MBAM 2.5 用戶端的必要條件
description: MBAM 2.5 用戶端的必要條件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812074"
---
# <span data-ttu-id="e7751-103">MBAM 2.5 用戶端的必要條件</span><span class="sxs-lookup"><span data-stu-id="e7751-103">Prerequisites for MBAM 2.5 Clients</span></span>


<span data-ttu-id="e7751-104">在最終使用者的電腦上安裝 MBAM 用戶端軟體之前，請確定您的環境和用戶端電腦符合下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="e7751-104">Before you install the MBAM Client software on end users' computers, ensure that your environment and the client computers meet the following prerequisites.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e7751-105">必備</span><span class="sxs-lookup"><span data-stu-id="e7751-105">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e7751-106">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e7751-106">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7751-107">企業網域必須包含至少一個 Windows Server 2008 （或更新版本）網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="e7751-107">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7751-108">用戶端電腦必須登入企業內部網路。</span><span class="sxs-lookup"><span data-stu-id="e7751-108">The client computer must be logged on to the enterprise intranet.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7751-109">僅適用于 Windows 7 用戶端電腦：每個用戶端都必須具有信任的平臺模組（TPM）功能（TPM 1.2 或更新版本）。</span><span class="sxs-lookup"><span data-stu-id="e7751-109">For Windows 7 client computers only: Each client must have Trusted Platform Module (TPM) capability (TPM 1.2 or later).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7751-110">針對 Windows 8.1、Windows 10 RTM 或 Windows 10 版本1511用戶端電腦：如果您希望 MBAM 能夠儲存及管理 TPM 復原金鑰，必須先關閉 TPM 自動供給，然後再將 MBAM 設定為 TPM 擁有者，才能部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="e7751-110">For Windows 8.1, Windows 10 RTM or Windows 10 version 1511 client computers only: If you want MBAM to be able to store and manage the TPM recovery keys, TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p>
<p><span data-ttu-id="e7751-111">在 MBAM 2.5 SP1 中，您不再需要關閉 TPM 自動供給，但您必須確認已將 TPM 群組原則物件設定為無法將 TPM OwnerAuth 到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e7751-111">In MBAM 2.5 SP1 only, you no longer need to turn off TPM auto-provisioning, but you must make sure that the TPM Group Policy Objects are set to not escrow TPM OwnerAuth to Active Directory.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)"><span data-ttu-id="e7751-112">MBAM 2.5 安全性考量</span><span class="sxs-lookup"><span data-stu-id="e7751-112">MBAM 2.5 Security Considerations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7751-113">如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="e7751-113">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="e7751-114">在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="e7751-114">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span></p>
<p><span data-ttu-id="e7751-115">在 MBAM 2.5 SP1 中，您必須開啟自動供給。</span><span class="sxs-lookup"><span data-stu-id="e7751-115">In MBAM 2.5 SP1, you must turn on auto-provisioning.</span></span></p>
</p></td>
<td align="left"><p><span data-ttu-id="e7751-116"><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 如需詳細資訊，請參閱 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="e7751-116">See <a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)">TPM owner password</a> for further details.</span></span>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7751-117">您必須在 BIOS 中開啟 TPM 晶片，然後從作業系統 resettable。</span><span class="sxs-lookup"><span data-stu-id="e7751-117">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7751-118">如需詳細資訊，請參閱 BIOS 檔。</span><span class="sxs-lookup"><span data-stu-id="e7751-118">See the BIOS documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7751-119">電腦的硬碟必須至少有兩個磁碟分割，且必須使用 NTFS 檔案系統來格式化。</span><span class="sxs-lookup"><span data-stu-id="e7751-119">The computer’s hard disk must have at least two partitions and must be formatted with the NTFS file system.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7751-120">電腦的硬碟必須有與 TPM 相容且在電腦啟動期間支援 USB 裝置的 BIOS。</span><span class="sxs-lookup"><span data-stu-id="e7751-120">The computer’s hard disk must have a BIOS that is compatible with TPM and that supports USB devices during computer startup.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="e7751-121">注意</span><span class="sxs-lookup"><span data-stu-id="e7751-121">Note</span></span></strong><br/><p><span data-ttu-id="e7751-122">確定鍵盤、影片或滑鼠已直接連接，且未透過鍵盤、影片或滑鼠（KVM）開關進行管理。</span><span class="sxs-lookup"><span data-stu-id="e7751-122">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="e7751-123">KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。</span><span class="sxs-lookup"><span data-stu-id="e7751-123">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7751-124">如果您使用 proxy，必須在系統內容中顯示它。</span><span class="sxs-lookup"><span data-stu-id="e7751-124">If you use a proxy, it must be visible in the system context.</span></span> <span data-ttu-id="e7751-125">MBAM 會在系統內容（而非使用者內容）底下執行。</span><span class="sxs-lookup"><span data-stu-id="e7751-125">MBAM runs under the system context, not the user context.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e7751-126">重要</span><span class="sxs-lookup"><span data-stu-id="e7751-126">Important</span></span>**  
<span data-ttu-id="e7751-127">如果在沒有 MBAM 的情況下使用 BitLocker，可以安裝 MBAM 並利用現有的 TPM 資訊。</span><span class="sxs-lookup"><span data-stu-id="e7751-127">If BitLocker was used without MBAM, MBAM can be installed and utilize the existing TPM information.</span></span>




## <span data-ttu-id="e7751-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7751-128">Related topics</span></span>


[<span data-ttu-id="e7751-129">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="e7751-129">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="e7751-130">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="e7751-130">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)


## <span data-ttu-id="e7751-131">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="e7751-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e7751-132">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e7751-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="e7751-133">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e7751-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






