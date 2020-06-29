---
title: MED-V 作業的安全性最佳做法
description: MED-V 作業的安全性最佳做法
author: dansimp
ms.assetid: 231e2b9a-8b49-42fe-93b5-2ef12fe17bac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4353a15c756dba8cf44f530c2077546e3f9288cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811132"
---
# <span data-ttu-id="6ab26-103">MED-V 作業的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="6ab26-103">Security Best Practices for MED-V Operations</span></span>


<span data-ttu-id="6ab26-104">身為授權的管理員，您有責任在部署 MED-V 工作區期間和之後，保護使用者的資訊並維持組織的安全性。</span><span class="sxs-lookup"><span data-stu-id="6ab26-104">As an authorized administrator, you are responsible to protect the information of the users and maintain security of your organization during and after the deployment of MED-V workspaces.</span></span> <span data-ttu-id="6ab26-105">具體說來，請考慮下列問題。</span><span class="sxs-lookup"><span data-stu-id="6ab26-105">In particular, consider the following issues.</span></span>

<span data-ttu-id="6ab26-106">**在 med-v 工作區中自訂 Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="6ab26-106">**Customizing Internet Explorer in the MED-V workspace**.</span></span> <span data-ttu-id="6ab26-107">較舊版本的 Windows 作業系統和 Internet Explorer 與目前版本不一樣安全。</span><span class="sxs-lookup"><span data-stu-id="6ab26-107">Earlier versions of the Windows operating system and of Internet Explorer are not as secure as current versions.</span></span> <span data-ttu-id="6ab26-108">因此，MED-V 工作區中的 Internet Explorer 會設定為防止流覽及其他可能帶來安全性風險的活動。</span><span class="sxs-lookup"><span data-stu-id="6ab26-108">Therefore, Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span> <span data-ttu-id="6ab26-109">此外，MED-V 工作區中 Internet Explorer 的 [網際網路安全性區域] 設定會設定為最高等級。</span><span class="sxs-lookup"><span data-stu-id="6ab26-109">In addition, the Internet security zone setting for Internet Explorer in the MED-V workspace is set to the highest level.</span></span> <span data-ttu-id="6ab26-110">根據預設，當您建立 MED-V 工作區套件時，會在 MED-V 工作區包裝程式中設定這兩個設定。</span><span class="sxs-lookup"><span data-stu-id="6ab26-110">By default, both of these configurations are set in the MED-V Workspace Packager when you create your MED-V workspace package.</span></span>

<span data-ttu-id="6ab26-111">透過使用 Internet Explorer 管理工具組（IEAK）或變更 MED-V 工作區包裝程式中的預設值，您可以在 MED-V 工作區中自訂 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="6ab26-111">By using Internet Explorer Administration Kit (IEAK) or by changing the defaults in the MED-V Workspace Packager, you can customize Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="6ab26-112">不過，請注意，如果您在 MED-V 工作區中自訂 Internet Explorer 的方式是不安全，您可以將貴組織暴露給舊版 Internet Explorer 中存在的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="6ab26-112">However, realize that if you customize Internet Explorer in the MED-V workspace in such a way as to make it less secure, you can expose your organization to those security risks that are present in older versions of Internet Explorer.</span></span>

<span data-ttu-id="6ab26-113">從安全性的觀點來看，在 MED-V 工作區中管理 Internet Explorer 的最佳做法如下：</span><span class="sxs-lookup"><span data-stu-id="6ab26-113">From a security perspective, best practices for managing Internet Explorer in the MED-V workspace are as follows:</span></span>

-   <span data-ttu-id="6ab26-114">建立 MED-V 工作區套件時，請保留預設設定，以便將 MED-V 工作區中的 Internet Explorer 設定為可避免流覽及其他可能帶來安全性風險的活動。</span><span class="sxs-lookup"><span data-stu-id="6ab26-114">When creating your MED-V workspace package, leave the defaults set so that Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span>

-   <span data-ttu-id="6ab26-115">建立 MED-V 工作區套件時，請保留預設設定，讓網際網路安全區域的安全性設定保持在最高等級。</span><span class="sxs-lookup"><span data-stu-id="6ab26-115">When creating your MED-V workspace package, leave the defaults set so that the security setting for the Internet security zone remains at the highest level.</span></span>

-   <span data-ttu-id="6ab26-116">設定您的企業 proxy 或 Internet Explorer 內容審查程式，以封鎖您公司內部網路以外的網域。</span><span class="sxs-lookup"><span data-stu-id="6ab26-116">Configure your enterprise proxy or Internet Explorer Content Advisor to block domains that are outside your company’s intranet.</span></span>

**<span data-ttu-id="6ab26-117">針對共用電腦上的所有使用者設定 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="6ab26-117">Configuring a MED-V workspace for all users on a shared computer.</span></span>** <span data-ttu-id="6ab26-118">在將 MED-V 工作區設定為可供共用電腦上的所有使用者存取時，請注意，系統會將來賓虛擬機器（VHD）放在一個位置，以提供對該系統上所有使用者的讀取和寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="6ab26-118">When configuring a MED-V workspace so that it can be accessed by all users on a shared computer, realize that the guest virtual machine (VHD) is put in a location that gives Read and Write access to all users on that system.</span></span>

**<span data-ttu-id="6ab26-119">針對加入網域的伺服器設定 proxy 帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ab26-119">Configuring a proxy account for domain joining.</span></span>** <span data-ttu-id="6ab26-120">當您設定將虛擬機器加入網域的 proxy 帳戶時，您必須知道最終使用者可以取得 proxy 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="6ab26-120">When configuring a proxy account for joining virtual machines to the domain, you must know that it is possible for an end user to obtain the proxy account credentials.</span></span> <span data-ttu-id="6ab26-121">因此，必須採取必要的預防措施（例如限制帳戶的使用者權利），避免使用者使用認證來造成損害。</span><span class="sxs-lookup"><span data-stu-id="6ab26-121">Thus, necessary precautions must be taken, such as limiting account user rights, to prevent an end user from using the credentials for causing harm.</span></span>

**<span data-ttu-id="6ab26-122">Sysprep 設定。</span><span class="sxs-lookup"><span data-stu-id="6ab26-122">Sysprep Configuration.</span></span>** <span data-ttu-id="6ab26-123">雖然 Sysprep .inf 檔案預設是經過加密，但其內容可以由任何已確定的最終使用者解密並讀取，任何人都可以成功登入虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="6ab26-123">Although the Sysprep.inf file is encrypted by default, its contents can be decrypted and read by any determined end user who can successfully log on to the virtual machine.</span></span> <span data-ttu-id="6ab26-124">這會引發安全性問題，因為除了 Windows 產品金鑰之外，Sysprep.inf 檔案也可以包含認證。</span><span class="sxs-lookup"><span data-stu-id="6ab26-124">This raises security concerns because the Sysprep.inf file can contain credentials in addition to a Windows product key.</span></span>

<span data-ttu-id="6ab26-125">您可以設定一個受限制的帳戶來將虛擬電腦加入網域，並在設定 Sysprep 時指定該帳戶的認證，以減輕此風險。</span><span class="sxs-lookup"><span data-stu-id="6ab26-125">You can lessen this risk by setting up a limited account for joining virtual machines to the domain and specifying the credentials for that account when configuring Sysprep.</span></span> <span data-ttu-id="6ab26-126">或者，您也可以設定 Sysprep 和第一次設定在**有人參與**模式下執行，並要求使用者提供其認證，才能將虛擬機器加入到網域。</span><span class="sxs-lookup"><span data-stu-id="6ab26-126">Alternately, you can also configure Sysprep and first time setup to run in **Attended** mode and require end users to provide their credentials for joining the virtual machine to the domain.</span></span>

<span data-ttu-id="6ab26-127">MED-V 最佳做法是將 FtsCompletion.exe 指定為在可讓使用者透過遠端桌面連線（RDC）用戶端連線至來賓的帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="6ab26-127">A MED-V best practice is to specify that FtsCompletion.exe is run under an account that gives the end user rights to connect to the guest through the Remote Desktop Connection (RDC) Client.</span></span>

**<span data-ttu-id="6ab26-128">最終使用者驗證。</span><span class="sxs-lookup"><span data-stu-id="6ab26-128">End-user authentication.</span></span>** <span data-ttu-id="6ab26-129">啟用終端使用者認證的快取可為 MED-V 提供最佳的使用者體驗，但卻帶來了某人可以取得使用者認證存取權的可能性。</span><span class="sxs-lookup"><span data-stu-id="6ab26-129">Enabling the caching of end-user credentials provides the best user experience of MED-V, but creates the potential that someone could gain access to the end user’s credentials.</span></span> <span data-ttu-id="6ab26-130">減少此風險的唯一方式，就是在**Med-v 工作區包裝**程式上指定不會儲存終端使用者認證。</span><span class="sxs-lookup"><span data-stu-id="6ab26-130">The only way to lessen this risk is by specifying on the **MED-V Workspace Packager** that end-user credentials are not stored.</span></span> <span data-ttu-id="6ab26-131">如需使用者驗證的詳細資訊，請參閱[Med-v 端使用者驗證](authentication-of-med-v-end-users.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab26-131">For more information about authentication of end users, see [Authentication of MED-V End Users](authentication-of-med-v-end-users.md).</span></span>

## <span data-ttu-id="6ab26-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="6ab26-132">Related topics</span></span>


[<span data-ttu-id="6ab26-133">作業疑難排解</span><span class="sxs-lookup"><span data-stu-id="6ab26-133">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

[<span data-ttu-id="6ab26-134">Microsoft 企業版桌面虛擬化2。0</span><span class="sxs-lookup"><span data-stu-id="6ab26-134">Microsoft Enterprise Desktop Virtualization 2.0</span></span>](index.md)

 

 





