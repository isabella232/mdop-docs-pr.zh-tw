---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800216"
---
# <span data-ttu-id="9da3c-103">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9da3c-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="9da3c-104">當您移動先前已使用 Microsoft BitLocker 管理和監控（MBAM）加密的作業系統磁片磁碟機時，您必須解決特定問題。</span><span class="sxs-lookup"><span data-stu-id="9da3c-104">When you move an operating system drive that has been previously encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), you must resolve certain issues.</span></span> <span data-ttu-id="9da3c-105">將 PIN 附加到新電腦之後，此磁碟機將不會接受在先前電腦中使用的啟動 PIN。</span><span class="sxs-lookup"><span data-stu-id="9da3c-105">After a PIN is attached to the new computer, the drive will not accept the start-up PIN that was used in previous computer.</span></span> <span data-ttu-id="9da3c-106">因為信任的平臺模組（TPM）晶片變更，所以系統會認為 PIN 無效。</span><span class="sxs-lookup"><span data-stu-id="9da3c-106">The system considers the PIN to be invalid because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="9da3c-107">您必須取得復原金鑰識別碼，才能取得恢復密碼，以便使用移動的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="9da3c-107">You must obtain a recovery key ID to retrieve the recovery password in order to use the moved drive.</span></span> <span data-ttu-id="9da3c-108">若要這樣做，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="9da3c-108">To do this, use the following procedure.</span></span>

**<span data-ttu-id="9da3c-109">若要復原移動的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="9da3c-109">To recover a moved drive</span></span>**

1.  <span data-ttu-id="9da3c-110">在包含已移動的磁片磁碟機的電腦上，從 Windows 復原環境（WinRE）模式開始，或使用 Microsoft Diagnostics 和復原工具組（DaRT）來啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="9da3c-110">On the computer that contains the moved drive, start in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="9da3c-111">電腦開始使用 WinRE 或 DaRT 之後，MBAM 會將移動的作業系統磁片磁碟機視為資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="9da3c-111">Once the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="9da3c-112">MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。</span><span class="sxs-lookup"><span data-stu-id="9da3c-112">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="9da3c-113">**記事** 在某些情況下，您可能可以在啟動程式中，按一下 [**我不在 PIN** ]，進入復原模式。</span><span class="sxs-lookup"><span data-stu-id="9da3c-113">**Note** In some cases, you might be able to click **I forget the PIN** during the startup process to enter the recovery mode.</span></span> <span data-ttu-id="9da3c-114">這也會顯示 [復原金鑰識別碼]。</span><span class="sxs-lookup"><span data-stu-id="9da3c-114">This also displays the recovery key ID.</span></span>

     

3.  <span data-ttu-id="9da3c-115">在 MBAM 管理網站上，使用復原金鑰識別碼來取得恢復密碼並解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="9da3c-115">On the MBAM administration website, use the recovery key ID to retrieve the recovery password and unlock the drive.</span></span>

4.  <span data-ttu-id="9da3c-116">如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，您必須在解除硬碟鎖定並完成開始程式後採取其他步驟。</span><span class="sxs-lookup"><span data-stu-id="9da3c-116">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after you unlock the drive and complete the start process.</span></span> <span data-ttu-id="9da3c-117">在 WinRE 模式中，開啟命令提示字元，然後使用 [ **manage-bde** ] 工具來解密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="9da3c-117">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="9da3c-118">此工具的使用方式是在沒有原始 TPM 晶片的情況下，移除 TPM 外加 PIN 保護的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="9da3c-118">The use of this tool is the only way to remove the TPM-plus-PIN protection without the original TPM chip.</span></span>

5.  <span data-ttu-id="9da3c-119">完成移除之後，請正常啟動系統。</span><span class="sxs-lookup"><span data-stu-id="9da3c-119">After the removal is complete, start the system normally.</span></span> <span data-ttu-id="9da3c-120">MBAM 代理程式將繼續執行原則，以使用新電腦的 TPM plus PIN 來加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="9da3c-120">The MBAM agent will proceed to enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="9da3c-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="9da3c-121">Related topics</span></span>


[<span data-ttu-id="9da3c-122">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9da3c-122">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





