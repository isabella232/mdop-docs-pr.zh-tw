---
title: 如何在用戶端上發佈虛擬應用程式
description: 如何在用戶端上發佈虛擬應用程式
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801190"
---
# <span data-ttu-id="8514b-103">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="8514b-103">How to Publish a Virtual Application on the Client</span></span>


<span data-ttu-id="8514b-104">當您使用電子軟體發佈系統部署應用程式虛擬化時，您可以使用下列其中一個程式，將應用程式套件發佈給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="8514b-104">When you deploy Application Virtualization by using an electronic software distribution system, you can use one of the following procedures to publish an application package to your users.</span></span>

**<span data-ttu-id="8514b-105">使用獨立的 Windows 安裝程式檔案發佈套件</span><span class="sxs-lookup"><span data-stu-id="8514b-105">To publish a package using a stand-alone Windows Installer file</span></span>**

1.  <span data-ttu-id="8514b-106">用戶端應該安裝，並將*REQUIREAUTHORIZATIONIFCACHED*參數設定為0（零）。</span><span class="sxs-lookup"><span data-stu-id="8514b-106">The client should be installed with the *REQUIREAUTHORIZATIONIFCACHED* parameter set to 0 (zero).</span></span> <span data-ttu-id="8514b-107">如需設定此參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="8514b-107">For more information about setting this parameter, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md)</span></span>

2.  <span data-ttu-id="8514b-108">將 Windows 安裝程式檔案和 SFT 檔案複製到目的電腦上的同一個資料夾。</span><span class="sxs-lookup"><span data-stu-id="8514b-108">Copy the Windows Installer file and the SFT file to same folder on the target computer.</span></span>

3.  <span data-ttu-id="8514b-109">在電腦上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8514b-109">Run the following command on the computer:</span></span>

    `Msiexec.exe /I "packagename.msi" /q`

**<span data-ttu-id="8514b-110">使用 Windows 安裝程式和套件資訊清單發佈套件</span><span class="sxs-lookup"><span data-stu-id="8514b-110">To publish a package using Windows Installer and the package manifest</span></span>**

1.  <span data-ttu-id="8514b-111">將 Windows 安裝程式檔案複製到目的電腦和 SFT 檔案，移至流式處理伺服器上的內容共用。</span><span class="sxs-lookup"><span data-stu-id="8514b-111">Copy the Windows Installer file to the target computer and the SFT file to the CONTENT share on the streaming server.</span></span>

2.  <span data-ttu-id="8514b-112">在每個使用者的電腦上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8514b-112">Run the following command on each user’s computer:</span></span>

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    <span data-ttu-id="8514b-113">**重要** 針對 OVERRIDEURL，所有反斜線字元都必須使用前面的反斜線來轉義，否則不會正確分析 OVERRIDEURL 路徑。</span><span class="sxs-lookup"><span data-stu-id="8514b-113">**Important** For OVERRIDEURL all backslash characters must be escaped using a preceding backslash, or the OVERRIDEURL path will not be parsed correctly.</span></span> <span data-ttu-id="8514b-114">此外，屬性和值必須以大寫輸入，但值是檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="8514b-114">Also, properties and values must be entered as uppercase except where the value is a path to a file.</span></span>

     

**<span data-ttu-id="8514b-115">使用 SFTMIME 發佈套件</span><span class="sxs-lookup"><span data-stu-id="8514b-115">To publish a package using SFTMIME</span></span>**

-   <span data-ttu-id="8514b-116">如需如何為電腦上的所有使用者發佈應用程式的範例，請在使用者的電腦上執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8514b-116">For an example of how to publish an application for all users on a computer, run the following command on the user’s computer:</span></span>

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    <span data-ttu-id="8514b-117">如需這些及其他 SFTMIME 命令的其他詳細資訊，請參閱[SFTMIME 命令參考](sftmime--command-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="8514b-117">For additional details about these and other SFTMIME commands, see [SFTMIME Command Reference](sftmime--command-reference.md).</span></span>

## <span data-ttu-id="8514b-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="8514b-118">Related topics</span></span>


[<span data-ttu-id="8514b-119">決定您的發佈方法</span><span class="sxs-lookup"><span data-stu-id="8514b-119">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="8514b-120">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="8514b-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="8514b-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="8514b-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

[<span data-ttu-id="8514b-122">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="8514b-122">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





