---
title: 使用 Windows PowerShell 管理 MBAM 2.5
description: 使用 Windows PowerShell 管理 MBAM 2.5
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800168"
---
# <span data-ttu-id="890d2-103">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="890d2-103">Using Windows PowerShell to Administer MBAM 2.5</span></span>


<span data-ttu-id="890d2-104">本主題描述 Microsoft BitLocker 管理與監控（MBAM）的 Windows PowerShell Cmdlet，這些 Cmdlet 會在使用者鎖定時，與復原電腦或磁片磁碟機有關。</span><span class="sxs-lookup"><span data-stu-id="890d2-104">This topic describes Windows PowerShell cmdlets for Microsoft BitLocker Administration and Monitoring (MBAM) that relate to recovering computers or drives when users get locked out.</span></span>

<span data-ttu-id="890d2-105">針對您用來設定 MBAM 伺服器功能的 Cmdlet，請參閱[使用 Windows PowerShell 配置 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="890d2-105">For cmdlets that you use to configure MBAM Server features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a><span data-ttu-id="890d2-106">用來復原由 MBAM 管理的電腦或磁片磁碟機的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="890d2-106">Cmdlets for recovering computers or drives that are managed by MBAM</span></span>


<span data-ttu-id="890d2-107">使用下列 Windows PowerShell Cmdlet 來復原由 MBAM 管理的電腦或磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="890d2-107">Use the following Windows PowerShell cmdlets to recover computers or drives that are managed by MBAM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="890d2-108">名稱</span><span class="sxs-lookup"><span data-stu-id="890d2-108">Name</span></span></th>
<th align="left"><span data-ttu-id="890d2-109">描述</span><span class="sxs-lookup"><span data-stu-id="890d2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="890d2-110">MbamBitLockerRecoveryKey</span><span class="sxs-lookup"><span data-stu-id="890d2-110">Get-MbamBitLockerRecoveryKey</span></span></p></td>
<td align="left"><p><span data-ttu-id="890d2-111">要求使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="890d2-111">Requests an MBAM recovery key that enables users to unlock a computer or encrypted drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="890d2-112">MbamTPMOwnerPassword</span><span class="sxs-lookup"><span data-stu-id="890d2-112">Get-MbamTPMOwnerPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="890d2-113">提供擁有 TPM 擁有者密碼的使用者，這些密碼可用來解除鎖定受信任的平臺模組（TPM），而 TPM 已將它們鎖定並將不再接受其 PIN。</span><span class="sxs-lookup"><span data-stu-id="890d2-113">Provides users with a TPM owner password that they can use to unlock a Trusted Platform Module (TPM) when the TPM has locked them out and will no longer accept their PIN.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> <span data-ttu-id="890d2-114">MBAM Cmdlet 說明</span><span class="sxs-lookup"><span data-stu-id="890d2-114">MBAM cmdlet Help</span></span>


<span data-ttu-id="890d2-115">MBAM Cmdlet 的 Windows PowerShell 說明提供下列格式：</span><span class="sxs-lookup"><span data-stu-id="890d2-115">Windows PowerShell Help for MBAM cmdlets is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="890d2-116">Windows PowerShell 說明格式</span><span class="sxs-lookup"><span data-stu-id="890d2-116">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="890d2-117">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="890d2-117">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="890d2-118">在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="890d2-118">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="890d2-119">若要上傳最新的 Windows PowerShell Cmdlet，請依照 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> 使用 Windows powershell 設定 MBAM 2.5 伺服器功能中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="890d2-119">To upload the latest Windows PowerShell cmdlets, follow the instructions in <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="890d2-120">在 TechNet 上做為網頁</span><span class="sxs-lookup"><span data-stu-id="890d2-120">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="890d2-121">以單字 .docx 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="890d2-121">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="890d2-122">以 .pdf 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="890d2-122">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="890d2-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="890d2-123">Related topics</span></span>


[<span data-ttu-id="890d2-124">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="890d2-124">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="890d2-125">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="890d2-125">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## <span data-ttu-id="890d2-126">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="890d2-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="890d2-127">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="890d2-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="890d2-128">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="890d2-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





