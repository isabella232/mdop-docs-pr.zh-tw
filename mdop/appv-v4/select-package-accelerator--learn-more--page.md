---
title: 選取封裝加速器 (深入瞭解) 頁面
description: 選取封裝加速器 (深入瞭解) 頁面
author: dansimp
ms.assetid: 2db51514-8695-4b5e-b3e5-1e96e3ee4cc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51df0f8eb16816bacf681b1acaf4c911ee9da55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800851"
---
# <span data-ttu-id="fa040-103">選取封裝加速器 (深入瞭解) 頁面</span><span class="sxs-lookup"><span data-stu-id="fa040-103">Select Package Accelerator (Learn More) Page</span></span>


<span data-ttu-id="fa040-104">只能從您信任的發行者執行套件加速器。</span><span class="sxs-lookup"><span data-stu-id="fa040-104">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="fa040-105">套件加速器通常包含數位簽章。</span><span class="sxs-lookup"><span data-stu-id="fa040-105">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="fa040-106">數位簽章是一種電子安全標記，可協助您指示軟體的發行者，且套件在最初簽署轉換後沒有被篡改。</span><span class="sxs-lookup"><span data-stu-id="fa040-106">A digital signature is an electronic security mark that can help indicate the publisher of the software, and that the package has not been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="fa040-107">如果您使用的轉換是由發行商數位簽署的，且發行商已透過憑證授權單位驗證其身分識別，您就可以更有把握該轉換來自該特定的發行者，而且尚未變更。</span><span class="sxs-lookup"><span data-stu-id="fa040-107">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="fa040-108">如果下列任一條件成立，sequencer 會通知您：</span><span class="sxs-lookup"><span data-stu-id="fa040-108">The sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="fa040-109">選取的轉換尚未經過數位簽署。</span><span class="sxs-lookup"><span data-stu-id="fa040-109">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="fa040-110">所選的轉換是由尚未使用憑證授權單位驗證其身分識別的發行者所簽署。</span><span class="sxs-lookup"><span data-stu-id="fa040-110">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="fa040-111">所選取的轉換在經過數位簽署及放開後已變更。</span><span class="sxs-lookup"><span data-stu-id="fa040-111">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="fa040-112">如果使用套件加速器時會顯示這些訊息中的任何一種，請造訪封裝加速器發行者的網站，以取得經過數位簽署的轉換版本。</span><span class="sxs-lookup"><span data-stu-id="fa040-112">If any of these messages are displayed when using a Package Accelerator, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

## <span data-ttu-id="fa040-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa040-113">Related topics</span></span>


[<span data-ttu-id="fa040-114">Sequencer 精靈 - 封裝加速器 (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="fa040-114">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





