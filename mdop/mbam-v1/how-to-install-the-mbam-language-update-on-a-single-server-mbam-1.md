---
title: 如何在單一伺服器上安裝 MBAM 語言更新
description: 如何在單一伺服器上安裝 MBAM 語言更新
author: dansimp
ms.assetid: e6fe59a3-a3e1-455c-a059-1f23ee083cf6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94814158335430aba433c180cdba83d0cf15b760
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810743"
---
# <span data-ttu-id="1e49f-103">如何在單一伺服器上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="1e49f-103">How to Install the MBAM Language Update on a Single Server</span></span>


<span data-ttu-id="1e49f-104">Microsoft BitLocker 管理與監控（MBAM）包括可在一或多部電腦上執行的四個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="1e49f-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes four server roles that can be run on one or more computers.</span></span> <span data-ttu-id="1e49f-105">不過，只有兩個 MBAM 伺服器功能需要更新，才能支援安裝 MBAM 1.0 語言發行和 MBAM 原則範本。</span><span class="sxs-lookup"><span data-stu-id="1e49f-105">However, only two MBAM Server features require the update to support installation of the MBAM 1.0 language release and the MBAM Policy Template.</span></span> <span data-ttu-id="1e49f-106">若要更新所有三個必要的 MBAM 功能，以在一部電腦上安裝，請執行本主題中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="1e49f-106">To update all three of the required MBAM features to be installed on one computer, perform the steps described in this topic.</span></span>

**<span data-ttu-id="1e49f-107">在單一伺服器上安裝 MBAM 語言更新</span><span class="sxs-lookup"><span data-stu-id="1e49f-107">To install the MBAM language update on a single server</span></span>**

1.  <span data-ttu-id="1e49f-108">開啟 [網際網路資訊服務（IIS）管理主控台]，移至 [**網站**]，然後關閉 Microsoft BitLocker 管理及監視網站。</span><span class="sxs-lookup"><span data-stu-id="1e49f-108">Open the Internet Information Services (IIS) Management Console, go to **Sites**, and then shut down the Microsoft BitLocker Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="1e49f-109">編輯 MBAM 網站的系結，然後暫時修改網站的系結。</span><span class="sxs-lookup"><span data-stu-id="1e49f-109">Edit the bindings for the MBAM website, and then temporarily modify the bindings of the site.</span></span> <span data-ttu-id="1e49f-110">例如，將埠從443變更為9443。</span><span class="sxs-lookup"><span data-stu-id="1e49f-110">For example, change the port from 443 to 9443.</span></span>

3.  <span data-ttu-id="1e49f-111">找出並執行 [MBAM 設定] 嚮導（MBAMsetup.exe），然後選取下列三個功能：</span><span class="sxs-lookup"><span data-stu-id="1e49f-111">Locate and run the MBAM setup wizard (MBAMsetup.exe) and select the following three features:</span></span>

    1.  <span data-ttu-id="1e49f-112">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="1e49f-112">Compliance and Audit Reports</span></span>

    2.  <span data-ttu-id="1e49f-113">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="1e49f-113">Administration and Monitoring Server</span></span>

    3.  <span data-ttu-id="1e49f-114">群組原則範本</span><span class="sxs-lookup"><span data-stu-id="1e49f-114">Group Policy Templates</span></span>

    <span data-ttu-id="1e49f-115">**重要** MBAM 伺服器的功能必須以下列順序進行更新：合規性和審核報告，然後是系統管理與監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e49f-115">**Important** The MBAM server features must be updated in the following order: Compliance and Audit Reports first, then Administration and Monitoring Server.</span></span> <span data-ttu-id="1e49f-116">您可以隨時更新群組原則範本，而不需考慮順序。</span><span class="sxs-lookup"><span data-stu-id="1e49f-116">The Group Policy templates can be updated at any time without concern for sequence.</span></span>

     

4.  <span data-ttu-id="1e49f-117">在您升級伺服器資料庫之後，請開啟 IIS 管理主控台並查看 Microsoft BitLocker 管理及監視網站的系結。</span><span class="sxs-lookup"><span data-stu-id="1e49f-117">After you upgrade the server database, open the IIS Management Console and review the bindings of the Microsoft BitLocker Administration and Monitoring website.</span></span>

5.  <span data-ttu-id="1e49f-118">刪除其中一個系結，並確認其餘的系結有正確的主機名稱、憑證和埠號碼供 MBAM 企業設定。</span><span class="sxs-lookup"><span data-stu-id="1e49f-118">Delete one of the bindings and ensure that the remaining binding has the correct host name, certificate, and port number for the MBAM enterprise configuration.</span></span>

6.  <span data-ttu-id="1e49f-119">重新開機 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="1e49f-119">Restart the MBAM website.</span></span>

7.  <span data-ttu-id="1e49f-120">測試 MBAM 網站的功能：</span><span class="sxs-lookup"><span data-stu-id="1e49f-120">Test the MBAM website functionality:</span></span>

    -   <span data-ttu-id="1e49f-121">開啟 MBAM 網頁介面，並確保您可以取得用戶端的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="1e49f-121">Open the MBAM web interface and ensure you can fetch a recovery key for a client.</span></span>

    -   <span data-ttu-id="1e49f-122">強制加密新的或手動解密的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="1e49f-122">Enforce encryption of a new or manually decrypted client computer.</span></span>

        <span data-ttu-id="1e49f-123">**記事** MBAM 用戶端只會在能與恢復與硬體資料庫通訊時開啟。</span><span class="sxs-lookup"><span data-stu-id="1e49f-123">**Note** The MBAM client opens only if it can communicate with the Recovery and Hardware database.</span></span>

         

## <span data-ttu-id="1e49f-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="1e49f-124">Related topics</span></span>


[<span data-ttu-id="1e49f-125">部署 MBAM 1.0 語言版本更新</span><span class="sxs-lookup"><span data-stu-id="1e49f-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





