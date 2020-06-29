---
title: 如何使用技術支援入口網站
description: 如何使用技術支援入口網站
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811690"
---
# <span data-ttu-id="57d50-103">如何使用技術支援入口網站</span><span class="sxs-lookup"><span data-stu-id="57d50-103">How to Use the Help Desk Portal</span></span>


<span data-ttu-id="57d50-104">MBAM 管理和監控網站（也稱為 [技術支援中心] 入口網站）是一種系統管理介面，可作為 Microsoft BitLocker 管理與監控（MBAM）伺服器基礎結構的一部分安裝的 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="57d50-104">The MBAM Administration and Monitoring website, also referred to as the Help Desk Portal, is an administrative interface to BitLocker drive encryption that is installed as part of the Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure.</span></span> <span data-ttu-id="57d50-105">下列各節說明您可以如何使用此網站來查看報告、復原使用者的磁片磁碟機，以及管理使用者的 TPMs。</span><span class="sxs-lookup"><span data-stu-id="57d50-105">The following sections describe how you can use this website to review reports, recover end users’ drives, and manage end users’ TPMs.</span></span>

## <a href="" id="bkmk-reports"></a><span data-ttu-id="57d50-106">報告</span><span class="sxs-lookup"><span data-stu-id="57d50-106">Reports</span></span>


<span data-ttu-id="57d50-107">MBAM 會從 Active Directory 和用戶端電腦收集資訊，這可讓您執行不同的報告，以監控 BitLocker 使用量與合規性。</span><span class="sxs-lookup"><span data-stu-id="57d50-107">MBAM collects information from Active Directory and client computers, which enables you to run different reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="57d50-108">您可以使用 [管理] 和 [監控] 網站的 [**報告**] 區段來產生有關企業合規性、個別電腦及金鑰復原活動的報告。</span><span class="sxs-lookup"><span data-stu-id="57d50-108">Using the **Reports** section of the Administration and Monitoring website, you can generate reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="57d50-109">如需每個報告的描述，請參閱[瞭解 MBAM 報告](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-109">For a description of each report, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

**<span data-ttu-id="57d50-110">存取報表</span><span class="sxs-lookup"><span data-stu-id="57d50-110">To access reports</span></span>**

1.  <span data-ttu-id="57d50-111">開啟網頁瀏覽器並流覽至 MBAM 管理和監控網站。</span><span class="sxs-lookup"><span data-stu-id="57d50-111">Open a web browser and navigate to the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="57d50-112">選取左窗格中的 [**報表**]。</span><span class="sxs-lookup"><span data-stu-id="57d50-112">Select **Reports** in the left pane.</span></span>

3.  <span data-ttu-id="57d50-113">從上方的功能表列中，選取您要產生的報表類型。</span><span class="sxs-lookup"><span data-stu-id="57d50-113">From the top menu bar, select the report type you want to generate.</span></span> <span data-ttu-id="57d50-114">若要儲存報表，請按一下 [報表] 功能表列上的 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="57d50-114">To save reports, click the **Export** button on the Reports menu bar.</span></span>

<span data-ttu-id="57d50-115">如需如何執行 MBAM 報告的其他資訊，請參閱[如何產生 MBAM 報告](how-to-generate-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-115">For additional information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

## <a href="" id="bkmk-drirec"></a><span data-ttu-id="57d50-116">磁片磁碟機恢復</span><span class="sxs-lookup"><span data-stu-id="57d50-116">Drive Recovery</span></span>


<span data-ttu-id="57d50-117">[管理與監視] 網站的 [**磁碟機**復原] 功能可讓擁有特定管理員角色（例如，技術支援人員使用者）存取已由 MBAM 用戶端收集的復原金鑰資料的使用者。</span><span class="sxs-lookup"><span data-stu-id="57d50-117">The **Drive Recovery** feature of the Administration and Monitoring website allows users with specific administrator roles (for example, Help Desk Users) to access recovery key data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="57d50-118">此資料可用於在 BitLocker 進入復原模式時存取受 BitLocker 保護的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="57d50-118">This data can be used to access a BitLocker-protected drive when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="57d50-119">如需如何復原復原模式中磁片磁碟機的指示，請參閱[如何在復原模式中復原磁片磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-119">For instructions on how to recover a drive that is in recovery mode, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-2.md).</span></span>

<span data-ttu-id="57d50-120">您也可以復原已移動或損毀的磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="57d50-120">You can also recover drives that have been moved or that are corrupted:</span></span>

-   [<span data-ttu-id="57d50-121">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="57d50-121">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="57d50-122">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="57d50-122">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

<span data-ttu-id="57d50-123">如需有關如何復原受 BitLocker 保護的磁碟機的其他資訊，請參閱[使用 MBAM 執行 BitLocker 管理](performing-bitlocker-management-with-mbam-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-123">For additional information about how to recover a BitLocker-protected drive, see [Performing BitLocker Management with MBAM](performing-bitlocker-management-with-mbam-mbam-2.md).</span></span>

## <a href="" id="bkmk-manatpm"></a><span data-ttu-id="57d50-124">管理 TPM</span><span class="sxs-lookup"><span data-stu-id="57d50-124">Manage TPM</span></span>


<span data-ttu-id="57d50-125">管理和監控網站的 [管理 TPM] 功能可為使用者提供特定的系統管理員角色（例如，「MBAM 技術支援人員」）存取已由 MBAM 用戶端收集的 TPM 資料。</span><span class="sxs-lookup"><span data-stu-id="57d50-125">The Manage TPM feature of the Administration and Monitoring website gives users with certain administrator roles (for example, “MBAM Helpdesk Users”) access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="57d50-126">在 TPM 封鎖中，系統管理員可以使用 [管理] 和 [監視] 網站來取得解除鎖定 TPM 所需的密碼檔。</span><span class="sxs-lookup"><span data-stu-id="57d50-126">In a TPM lockout, an administrator can use the Administration and Monitoring website to retrieve the necessary password file to unlock the TPM.</span></span> <span data-ttu-id="57d50-127">如需如何在 TPM 封鎖之後重設 TPM 的指示，請參閱[如何重設 Tpm 封鎖](how-to-reset-a-tpm-lockout-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-127">For instructions on how to reset a TPM after a TPM lockout, see [How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-2.md).</span></span>

## <a href="" id="bkmk-helpdesk"></a> <span data-ttu-id="57d50-128">MBAM 技術支援中心任務</span><span class="sxs-lookup"><span data-stu-id="57d50-128">MBAM Help Desk Tasks</span></span>


<span data-ttu-id="57d50-129">您可以使用管理和監控網站進行許多管理工作，例如管理受 BitLocker 保護的硬體、恢復磁片磁碟機，以及執行報告。</span><span class="sxs-lookup"><span data-stu-id="57d50-129">You can use the Administration and Monitoring website for many administrative tasks, such as managing BitLocker-protected hardware, recovering drives, and running reports.</span></span> <span data-ttu-id="57d50-130">根據預設，管理和監控網站的 URL 是 HTTP:// &lt; *MBAMAdministrationServername* &gt; ，不過您可以在安裝程式期間對它進行自訂。</span><span class="sxs-lookup"><span data-stu-id="57d50-130">By default, the URL for the Administration and Monitoring website is http://&lt;*MBAMAdministrationServername*&gt;, although you can customize it during the installation process.</span></span>

<span data-ttu-id="57d50-131">**記事** 若要存取 [管理] 和 [監視] 網站提供的各種功能，您必須擁有與您的使用者帳戶相關聯的適當角色。</span><span class="sxs-lookup"><span data-stu-id="57d50-131">**Note** To access the various features offered by the Administration and Monitoring website, you must have the appropriate roles associated with your user account.</span></span> <span data-ttu-id="57d50-132">如需瞭解使用者角色的詳細資訊，請參閱[如何管理 MBAM 系統管理員角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="57d50-132">For more information about understanding user roles, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md).</span></span>

 

<span data-ttu-id="57d50-133">使用下列連結，以尋找您可以使用 [管理和監控] 網站執行的工作相關資訊：</span><span class="sxs-lookup"><span data-stu-id="57d50-133">Use the following links to find information about the tasks that you can perform by using the Administration and Monitoring website:</span></span>

-   [<span data-ttu-id="57d50-134">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="57d50-134">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [<span data-ttu-id="57d50-135">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="57d50-135">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [<span data-ttu-id="57d50-136">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="57d50-136">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="57d50-137">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="57d50-137">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [<span data-ttu-id="57d50-138">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="57d50-138">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





