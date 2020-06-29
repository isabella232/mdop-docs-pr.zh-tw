---
title: 如何移動 MBAM 2.5 網站
description: 如何移動 MBAM 2.5 網站
author: dansimp
ms.assetid: 71af9a54-c27b-408f-9d75-37c0d02e730e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa5bd8156810b3dccc1588b4dfd4cadd96fd22fb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811342"
---
# <span data-ttu-id="6d9d5-103">如何移動 MBAM 2.5 網站</span><span class="sxs-lookup"><span data-stu-id="6d9d5-103">How to Move the MBAM 2.5 Websites</span></span>


<span data-ttu-id="6d9d5-104">您可以使用這些程式將下列 MBAM 網站從一部電腦移到另一部，也就是將下列功能從伺服器 A 移到伺服器 B：</span><span class="sxs-lookup"><span data-stu-id="6d9d5-104">Use these procedures to move the following MBAM websites from one computer to another, that is, to move the following features from Server A to Server B:</span></span>

-   <span data-ttu-id="6d9d5-105">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="6d9d5-105">Administration and Monitoring Website</span></span>

-   <span data-ttu-id="6d9d5-106">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="6d9d5-106">Self-Service Portal</span></span>

<span data-ttu-id="6d9d5-107">**重要** 在這兩個網站的設定期間，您必須提供相同的連線字串、報表 URL、群群組帳戶，以及 web 服務應用程式池網域帳戶作為您目前正在使用的專案。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-107">**Important** During the configuration of both websites, you must provide the same connection string, Reports URL, group accounts, and web service application pool domain account as the ones that you are currently using.</span></span> <span data-ttu-id="6d9d5-108">如果您沒有使用相同的值，就無法存取某些伺服器。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-108">If you don’t use the same values, you cannot access some of the servers.</span></span> <span data-ttu-id="6d9d5-109">若要取得目前的值，請使用**MbamWebApplication** Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-109">To get the current values, use the **Get-MbamWebApplication** Windows PowerShell cmdlet.</span></span>

 

**<span data-ttu-id="6d9d5-110">將管理和監控網站移至另一個伺服器</span><span class="sxs-lookup"><span data-stu-id="6d9d5-110">To move the Administration and Monitoring Website to another server</span></span>**

1.  <span data-ttu-id="6d9d5-111">在伺服器 B 上，安裝 MBAM 2.5 Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-111">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="6d9d5-112">如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-112">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="6d9d5-113">在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**管理及監視網站**] 功能。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-113">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Administration and Monitoring Website** feature.</span></span>

    <span data-ttu-id="6d9d5-114">或者，您也可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 來設定管理和監控網站。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-114">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Administration and Monitoring Website.</span></span>

    <span data-ttu-id="6d9d5-115">如需如何設定管理和監控網站的相關指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-115">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

**<span data-ttu-id="6d9d5-116">將自助式入口網站移至另一個伺服器</span><span class="sxs-lookup"><span data-stu-id="6d9d5-116">To move the Self-Service Portal to another server</span></span>**

1.  <span data-ttu-id="6d9d5-117">在伺服器 B 上，安裝 MBAM 2.5 Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-117">On Server B, install the MBAM 2.5 Server software.</span></span> <span data-ttu-id="6d9d5-118">如需相關指示，請參閱[安裝 MBAM 2.5 Server 軟體](installing-the-mbam-25-server-software.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-118">For instructions, see [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span>

2.  <span data-ttu-id="6d9d5-119">在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**自助入口網站**] 功能。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-119">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Self-Service Portal** feature.</span></span>

    <span data-ttu-id="6d9d5-120">或者，您也可以使用**Enable-MbamWebApplication** Windows PowerShell Cmdlet 來設定自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-120">Alternatively, you can use the **Enable-MbamWebApplication** Windows PowerShell cmdlet to configure the Self-Service Portal.</span></span>

    <span data-ttu-id="6d9d5-121">如需如何設定管理和監控網站的相關指示，請參閱[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-121">For instructions on how to configure the Administration and Monitoring Website, see [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

3.  <span data-ttu-id="6d9d5-122">如果貴組織中的用戶端電腦沒有 Microsoft 內容傳遞網路的存取權，您也必須移動 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-122">If the client computers in your organization do not have access to the Microsoft Content Delivery Network, you also have to move the JavaScript files.</span></span> <span data-ttu-id="6d9d5-123">如需詳細資訊，請參閱[如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時，設定自助服務入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-123">See [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md) for more information.</span></span>

4.  <span data-ttu-id="6d9d5-124">自訂貴組織的自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-124">Customize the Self-Service Portal for your organization.</span></span> <span data-ttu-id="6d9d5-125">使用[自訂貴組織的自助入口網站](customizing-the-self-service-portal-for-your-organization.md)中的指示來查看您目前的自訂專案，以及在伺服器 B 的自助伺服器入口網站上設定自訂設定。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-125">Use the instructions in [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md) to review your current customizations and to configure custom settings on the Self-Server Portal on Server B.</span></span>



## <span data-ttu-id="6d9d5-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d9d5-126">Related topics</span></span>


[<span data-ttu-id="6d9d5-127">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="6d9d5-127">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="6d9d5-128">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="6d9d5-128">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

[<span data-ttu-id="6d9d5-129">將 MBAM 2.5 功能移到其他伺服器</span><span class="sxs-lookup"><span data-stu-id="6d9d5-129">Moving MBAM 2.5 Features to Another Server</span></span>](moving-mbam-25-features-to-another-server.md)

 

## <span data-ttu-id="6d9d5-130">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="6d9d5-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6d9d5-131">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6d9d5-132">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="6d9d5-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





