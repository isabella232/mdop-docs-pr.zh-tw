---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810929"
---
# <span data-ttu-id="4b0d2-103">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="4b0d2-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="4b0d2-104">當您移動使用 Microsoft BitLocker 管理和監視（MBAM）加密的作業系統磁片磁碟機時，由於受信任的平臺模組（TPM）晶片的變更，磁片磁碟機不會接受先前電腦上所使用的 PIN。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-104">When you move an operating system drive that is encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), the drive will not accept the PIN that was used in a previous computer because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="4b0d2-105">若要使用移動的磁片磁碟機，您需要取得修復金鑰識別碼以取得復原密碼的方式。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-105">To use the moved drive, you will need a way to obtain the recovery key ID to retrieve the recovery password.</span></span> <span data-ttu-id="4b0d2-106">使用下列程式來復原已移動的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-106">Use the following procedure to recover a drive that has moved.</span></span>

**<span data-ttu-id="4b0d2-107">若要復原移動的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4b0d2-107">To recover a moved drive</span></span>**

1.  <span data-ttu-id="4b0d2-108">在包含已移動的磁片磁碟機的電腦上，在 Windows 復原環境（WinRE）模式中啟動電腦，或使用 Microsoft 診斷與修復工具組（DaRT）啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-108">On the computer that contains the moved drive, start the computer in Windows recovery environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="4b0d2-109">電腦開始使用 WinRE 或 DaRT 之後，Microsoft BitLocker 管理和監控就會將移動的作業系統磁片磁碟機視為資料硬碟。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-109">Once the computer has been started with WinRE or DaRT, Microsoft BitLocker Administration and Monitoring will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="4b0d2-110">MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-110">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="4b0d2-111">**記事** 在某些情況下，您可能可以在啟動期間按一下 [**我忘記 PIN** ]，然後輸入 [恢復] 模式來顯示覆原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-111">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="4b0d2-112">使用復原金鑰識別碼來檢索復原密碼，然後從管理和監控網站解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-112">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="4b0d2-113">如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，您必須在解除硬碟鎖定並完成開始程式後採取其他步驟。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-113">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after unlocking the drive and completing the start process.</span></span> <span data-ttu-id="4b0d2-114">在 WinRE 模式中，開啟命令提示字元，然後使用 [ **manage-bde** ] 工具來解密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-114">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="4b0d2-115">使用這個工具是移除 TPM 加上不含原始 TPM 晶片的 PIN 保護器的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-115">Using this tool is the only way to remove the TPM plus PIN protector without the original TPM chip.</span></span>

5.  <span data-ttu-id="4b0d2-116">完成移除後，請正常啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-116">Once the removal is completed, start the computer normally.</span></span> <span data-ttu-id="4b0d2-117">MBAM 代理程式現在將強制執行原則，以新電腦的 TPM 加上 PIN 來加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b0d2-117">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="4b0d2-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="4b0d2-118">Related topics</span></span>


[<span data-ttu-id="4b0d2-119">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="4b0d2-119">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





