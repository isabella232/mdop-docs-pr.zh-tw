---
title: 如何在分散式伺服器上安裝 MBAM 語言更新
description: 如何在分散式伺服器上安裝 MBAM 語言更新
author: dansimp
ms.assetid: 5ddc64c6-0417-4a04-843e-b5e18d9f1a52
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6758463c6fc038c4d6ea86c0d49804f29bb543d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811312"
---
# <span data-ttu-id="49ca3-103">如何在分散式伺服器上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="49ca3-103">How to Install the MBAM Language Update on Distributed Servers</span></span>


<span data-ttu-id="49ca3-104">Microsoft BitLocker 管理與監控（MBAM）包括可在一或多部電腦上執行的四個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="49ca3-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="49ca3-105">不過，只有兩個 MBAM 伺服器功能需要更新，才能支援 MBAM 1.0 語言發行和 MBAM 原則範本的安裝。</span><span class="sxs-lookup"><span data-stu-id="49ca3-105">However, only two MBAM Server features require the update to support the installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="49ca3-106">在配置中，將 MBAM 伺服器功能安裝在多部電腦上，只需要更新下列伺服器功能：</span><span class="sxs-lookup"><span data-stu-id="49ca3-106">In configurations with the MBAM Server features installed on multiple computers, only the following server features need to be updated:</span></span>

-   <span data-ttu-id="49ca3-107">MBAM 合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="49ca3-107">The MBAM Compliance and Audit Reports</span></span>

-   <span data-ttu-id="49ca3-108">MBAM 管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="49ca3-108">The MBAM Administration and Monitoring Server</span></span>

<span data-ttu-id="49ca3-109">**重要** MBAM 伺服器功能必須以下列順序進行更新：首先是合規性和審核報告，然後是系統管理和監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="49ca3-109">**Important** The MBAM server features must be updated in this order: Compliance and Audit Reports first, and then the Administration and Monitoring Server.</span></span> <span data-ttu-id="49ca3-110">您可以隨時更新 MBAM 群組原則範本，而不需考慮順序。</span><span class="sxs-lookup"><span data-stu-id="49ca3-110">The MBAM Group Policy templates can be updated at any time without concern for sequence.</span></span>

 

**<span data-ttu-id="49ca3-111">在 MBAM 合規性和審核報表伺服器功能上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="49ca3-111">To install the MBAM Language Update on the MBAM Compliance and Audit Report Server feature</span></span>**

1.  <span data-ttu-id="49ca3-112">在執行 MBAM 合規性和審核報告功能的電腦上，找出並執行 [MBAM 語言更新設定] 嚮導（MBAMsetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="49ca3-112">On the computer running the MBAM Compliance and Audit Report feature, locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span>

2.  <span data-ttu-id="49ca3-113">針對合規性和審核報告完成嚮導，然後關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="49ca3-113">Complete the wizard for the Compliance and Audit Reports and then close the wizard.</span></span>

**<span data-ttu-id="49ca3-114">若要在 [MBAM 管理及監視伺服器] 功能上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="49ca3-114">To install the MBAM Language Update on the MBAM Administration and Monitoring Server feature</span></span>**

1.  <span data-ttu-id="49ca3-115">在執行 MBAM 管理和監視功能的電腦上，開啟 [網際網路資訊服務（IIS）管理主控台]，移至 [**網站**]，然後關閉 Microsoft BitLocker 管理和監視網站。</span><span class="sxs-lookup"><span data-stu-id="49ca3-115">On the computer that is running the MBAM Administration and Monitoring feature, open the Internet Information Services (IIS) management console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="49ca3-116">選擇編輯 MBAM 網站的系結，然後修改該網站的系結。</span><span class="sxs-lookup"><span data-stu-id="49ca3-116">Choose to edit the bindings for the MBAM website, and then modify the bindings of the site.</span></span> <span data-ttu-id="49ca3-117">例如，將埠從443變更為9443。</span><span class="sxs-lookup"><span data-stu-id="49ca3-117">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="49ca3-118">找出並執行 MBAM 語言更新設定向導（MBAMsetup.exe）。</span><span class="sxs-lookup"><span data-stu-id="49ca3-118">Locate and run the MBAM Language Update setup wizard (MBAMsetup.exe).</span></span> <span data-ttu-id="49ca3-119">完成 [管理及監視伺服器] 功能的嚮導，然後關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="49ca3-119">Complete the wizard for the Administration and Monitoring Server feature and then close the wizard.</span></span>

4.  <span data-ttu-id="49ca3-120">在您升級伺服器資料庫之後，請開啟 IIS 管理主控台並查看 Microsoft BitLocker 管理及監視網站的系結。</span><span class="sxs-lookup"><span data-stu-id="49ca3-120">After you upgrade the server database, open IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="49ca3-121">刪除舊的系結，並確認其餘的系結有正確的主機名稱、憑證和埠號碼供 MBAM 企業設定。</span><span class="sxs-lookup"><span data-stu-id="49ca3-121">Delete the old binding and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="49ca3-122">重新開機 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="49ca3-122">Restart the MBAM web site.</span></span>

7.  <span data-ttu-id="49ca3-123">測試 MBAM 網站的功能：</span><span class="sxs-lookup"><span data-stu-id="49ca3-123">Test the MBAM web site functionality:</span></span>

    -   <span data-ttu-id="49ca3-124">開啟 MBAM 網頁介面，並確認您可以取得用戶端的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="49ca3-124">Open the MBAM web interface and ensure that you can obtain a recovery key for a client.</span></span>

    -   <span data-ttu-id="49ca3-125">強制加密新的或手動解密的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="49ca3-125">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="49ca3-126">**記事** MBAM 用戶端只會在能與恢復與硬體資料庫通訊時開啟。</span><span class="sxs-lookup"><span data-stu-id="49ca3-126">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="49ca3-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="49ca3-127">Related topics</span></span>


[<span data-ttu-id="49ca3-128">部署 MBAM 1.0 語言版本更新</span><span class="sxs-lookup"><span data-stu-id="49ca3-128">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





