---
title: 如何使用命令列部署 MBAM 用戶端
description: 如何使用命令列部署 MBAM 用戶端
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810586"
---
# <span data-ttu-id="f2e2a-103">如何使用命令列部署 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="f2e2a-103">How to Deploy the MBAM Client by Using a Command Line</span></span>


<span data-ttu-id="f2e2a-104">您可以使用命令列來部署 Microsoft BitLocker 管理和監控（MBAM）用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-104">You can use a command line to deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software.</span></span>

## <span data-ttu-id="f2e2a-105">部署 MBAM 用戶端軟體的命令列</span><span class="sxs-lookup"><span data-stu-id="f2e2a-105">Command Line to deploy the MBAM Client software</span></span>


<span data-ttu-id="f2e2a-106">在命令提示字元中輸入下列命令，以在部署 MBAM 用戶端軟體時自動接受使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-106">Type the following command at the command prompt to automatically accept the end user license agreement when deploying the MBAM Client software.</span></span>

**<span data-ttu-id="f2e2a-107">MBAMClientSetup.exe/acceptEula = 是</span><span class="sxs-lookup"><span data-stu-id="f2e2a-107">MBAMClientSetup.exe /acceptEula=Yes</span></span>**

<span data-ttu-id="f2e2a-108">**記事** **/Ju**和 **/jm**命令列選項不受支援，且無法用來安裝 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-108">**Note** The **/ju** and **/jm** command-line options are not supported and cannot be used to install the MBAM Client software.</span></span>

 

<span data-ttu-id="f2e2a-109">在命令提示字元中輸入下列命令，以解壓並安裝 MSP：</span><span class="sxs-lookup"><span data-stu-id="f2e2a-109">Type the following command at the command prompt to extract and install the MSP:</span></span>

**<span data-ttu-id="f2e2a-110">MBAMClientSetup.exe/extract &lt; 路徑來解壓縮 MSI &gt; /AcceptEula = 是</span><span class="sxs-lookup"><span data-stu-id="f2e2a-110">MBAMClientSetup.exe /extract &lt;path to extract MSI&gt; /acceptEula=Yes</span></span>**

<span data-ttu-id="f2e2a-111">然後，執行下列命令，以無訊息方式安裝 MSI：</span><span class="sxs-lookup"><span data-stu-id="f2e2a-111">Then, install the MSI silently by running the following command:</span></span>

**<span data-ttu-id="f2e2a-112">msiexec/i &lt; 路徑解壓至已解壓縮的 MSI &gt; /qb ALLUSERS = 1 重新開機 = ReallySuppress</span><span class="sxs-lookup"><span data-stu-id="f2e2a-112">msiexec /i &lt;path to extracted MSI&gt; /qb ALLUSERS=1 REBOOT=ReallySuppress</span></span>**

<span data-ttu-id="f2e2a-113">**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-113">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="f2e2a-114">不過，您可以在接受 EULA 之後，從產品隨附的可執行檔（.exe）中解壓縮 MSI。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-114">However, you can extract the MSI from the executable file (.exe) that is included with the product, after accepting the EULA.</span></span>

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a><span data-ttu-id="f2e2a-115">OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 命令列選項</span><span class="sxs-lookup"><span data-stu-id="f2e2a-115">OPTIN\_FOR\_MICROSOFT\_UPDATES=1 command-line option</span></span>


<span data-ttu-id="f2e2a-116">您也可以選擇在 `OPTIN_FOR_MICROSOFT_UPDATES=1` 用戶端軟體安裝期間指定命令列選項，在用戶端電腦上自動安裝 Microsoft 更新。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-116">You can optionally specify the command-line option `OPTIN_FOR_MICROSOFT_UPDATES=1` during the Client software installation to automatically install Microsoft Updates on client computers.</span></span> <span data-ttu-id="f2e2a-117">指定此選項會讓 Microsoft Update 在用戶端軟體安裝完成後，自動啟動並搜尋可用的更新以進行安裝。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-117">Specifying this option makes Microsoft Update automatically start and search for available updates to install after the Client software installation finishes.</span></span>

<span data-ttu-id="f2e2a-118">您可以將這個命令列選項與下列其中一個安裝方法搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-118">You can use this command-line option with either of the following installation methods.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f2e2a-119">使用 MBAM 用戶端軟體安裝</span><span class="sxs-lookup"><span data-stu-id="f2e2a-119">Install the MBAM Client software by using</span></span></th>
<th align="left"><span data-ttu-id="f2e2a-120">範例</span><span class="sxs-lookup"><span data-stu-id="f2e2a-120">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f2e2a-121">MBAMClientSetup.exe</span><span class="sxs-lookup"><span data-stu-id="f2e2a-121">MBAMClientSetup.exe</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="f2e2a-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="f2e2a-122">MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="f2e2a-123">msiexec/i MBAMClient.msi</span><span class="sxs-lookup"><span data-stu-id="f2e2a-123">msiexec /i MBAMClient.msi</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="f2e2a-124">msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</span><span class="sxs-lookup"><span data-stu-id="f2e2a-124">msiexec /i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES=1</span></span></strong></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="f2e2a-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="f2e2a-125">Related topics</span></span>


[<span data-ttu-id="f2e2a-126">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="f2e2a-126">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="f2e2a-127">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="f2e2a-127">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="f2e2a-128">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-128">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="f2e2a-129">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="f2e2a-129">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




