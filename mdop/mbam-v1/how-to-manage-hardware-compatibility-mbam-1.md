---
title: 如何管理硬體相容性
description: 如何管理硬體相容性
author: dansimp
ms.assetid: c74b96b9-8161-49bc-b5bb-4838734e7df5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf9e2c5b2b33ea93d9834a81700bd2be8a9b9757
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800230"
---
# <span data-ttu-id="8879c-103">如何管理硬體相容性</span><span class="sxs-lookup"><span data-stu-id="8879c-103">How to Manage Hardware Compatibility</span></span>


<span data-ttu-id="8879c-104">在您部署 [允許硬體相容性檢查] 群組原則後，Microsoft BitLocker 管理和監控（MBAM）就可以收集用戶端電腦製造商與模型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8879c-104">Microsoft BitLocker Administration and Monitoring (MBAM) can collect information about the manufacturer and model of client computers after you deploy the Allow Hardware Compatibility Checking Group Policy.</span></span> <span data-ttu-id="8879c-105">如果您設定此原則，當您在用戶端電腦上部署 MBAM 用戶端時，MBAM 代理會向 MBAM 伺服器報告電腦品牌和模型資訊。</span><span class="sxs-lookup"><span data-stu-id="8879c-105">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

<span data-ttu-id="8879c-106">如果貴組織的電腦硬體或電腦不支援信任的平臺模組（TPM）晶片，硬體相容性功能就很有説明。</span><span class="sxs-lookup"><span data-stu-id="8879c-106">The Hardware Compatibility feature is helpful when your organization has older computer hardware or computers that do not support Trusted Platform Module (TPM) chips.</span></span> <span data-ttu-id="8879c-107">在這些情況下，您可以使用硬體相容性功能，以確保 BitLocker 加密僅適用于支援它的電腦模型。</span><span class="sxs-lookup"><span data-stu-id="8879c-107">In these cases, you can use the Hardware Compatibility feature to ensure that BitLocker encryption is applied only to computer models that support it.</span></span> <span data-ttu-id="8879c-108">如果貴組織中的所有電腦都支援 BitLocker，您就不需要使用硬體相容性功能。</span><span class="sxs-lookup"><span data-stu-id="8879c-108">If all computers in your organization will support BitLocker, you do not have to use the Hardware Compatibility feature.</span></span>

<span data-ttu-id="8879c-109">**記事** 根據預設，不會啟用 MBAM 硬體相容性功能。</span><span class="sxs-lookup"><span data-stu-id="8879c-109">**Note** By default, MBAM Hardware Compatibility feature is not enabled.</span></span> <span data-ttu-id="8879c-110">若要啟用，請在安裝期間選取 [**管理與監視伺服器**] 功能底下的 [**硬體相容性**] 功能。</span><span class="sxs-lookup"><span data-stu-id="8879c-110">To enable it, select the **Hardware Compatibility** feature under the **Administration and Monitoring Server** feature during setup.</span></span> <span data-ttu-id="8879c-111">如需如何設定和設定硬體相容性的詳細資訊，請參閱[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="8879c-111">For more information about how to set up and configure Hardware Compatibility, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

<span data-ttu-id="8879c-112">硬體相容性功能會以下列方式運作。</span><span class="sxs-lookup"><span data-stu-id="8879c-112">The Hardware Compatibility feature works in the following way.</span></span>

****

1.  <span data-ttu-id="8879c-113">MBAM 用戶端代理程式會探索基本電腦資訊，例如製造商、型號、BIOS 製造商、BIOS 版本、TPM 製造商及 TPM 版本，然後將此資訊傳遞到 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8879c-113">The MBAM client agent discovers basic computer information such as manufacturer, model, BIOS maker, BIOS version, TPM maker, and TPM version, and then passes this information to the MBAM server.</span></span>

2.  <span data-ttu-id="8879c-114">MBAM 伺服器會產生用戶端電腦與模型的清單，讓您能夠區分那些可以或不支援 BitLocker 的那些人</span><span class="sxs-lookup"><span data-stu-id="8879c-114">The MBAM server generates a list of client computer makes and models to enable you to differentiate between those that can or cannot support BitLocker</span></span>

3.  <span data-ttu-id="8879c-115">在企業中部署的 MBAM 用戶端代理程式會自動更新此清單，並將所有新電腦群組成，且已發現狀態為 [**未知**] 的模型。</span><span class="sxs-lookup"><span data-stu-id="8879c-115">The MBAM client agents that are deployed in the enterprise automatically update this list with all new computer makes and models that are discovered with a state of **Unknown**.</span></span> <span data-ttu-id="8879c-116">然後，系統管理員可以使用 MBAM 管理網站來變更清單專案，將特定的電腦專案與模型指定為**相容**或**不相容**。</span><span class="sxs-lookup"><span data-stu-id="8879c-116">An administrator can then use the MBAM administration website to change list entries to specify a particular computer make and model as **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="8879c-117">在 MBAM 用戶端代理開始加密磁片磁碟機之前，代理程式首先驗證正在執行的硬體的 BitLocker 加密相容性。</span><span class="sxs-lookup"><span data-stu-id="8879c-117">Before the MBAM client agent begins encrypting a drive, the agent first verifies the BitLocker encryption compatibility of the hardware it is running on.</span></span>

    -   <span data-ttu-id="8879c-118">如果硬體標示為相容，就會啟動 BitLocker 加密處理常式。</span><span class="sxs-lookup"><span data-stu-id="8879c-118">If the hardware is marked as compatible, the BitLocker encryption process starts.</span></span> <span data-ttu-id="8879c-119">MBAM 也會再次檢查電腦的硬體相容性狀態，每一天一次。</span><span class="sxs-lookup"><span data-stu-id="8879c-119">MBAM will also recheck the hardware compatibility status of the computer one time per day.</span></span>

    -   <span data-ttu-id="8879c-120">如果硬體標示為不相容，則 agent 會記錄事件，並傳遞「硬體已免除」狀態，做為合規性報告的一部分。</span><span class="sxs-lookup"><span data-stu-id="8879c-120">If the hardware is marked as incompatible, the agent logs an event and passes a “hardware exempted” state as part of compliance reporting.</span></span> <span data-ttu-id="8879c-121">Agent 會每隔7天檢查一次，以查看狀態是否已變更為「相容」。</span><span class="sxs-lookup"><span data-stu-id="8879c-121">The agent checks every seven days to see whether the state has changed to “compatible.”</span></span>

    -   <span data-ttu-id="8879c-122">如果硬體標示為 [未知]，則不會開始 BitLocker 加密程式。</span><span class="sxs-lookup"><span data-stu-id="8879c-122">If the hardware is marked as unknown, the BitLocker encryption process will not begin.</span></span> <span data-ttu-id="8879c-123">MBAM 用戶端代理程式將逐一重新檢查電腦的硬體相容性狀態。</span><span class="sxs-lookup"><span data-stu-id="8879c-123">The MBAM client agent will recheck the hardware compatibility status of the computer one time per day.</span></span>

<span data-ttu-id="8879c-124">**警告** 如果 MBAM 用戶端代理程式嘗試加密不支援 BitLocker 磁片磁碟機加密的電腦，電腦可能會損毀。</span><span class="sxs-lookup"><span data-stu-id="8879c-124">**Warning** If the MBAM client agent tries to encrypt a computer that does not support BitLocker drive encryption, there is a possibility that the computer will become corrupted.</span></span> <span data-ttu-id="8879c-125">當貴組織擁有不支援 BitLocker 的舊版硬體時，請確定硬體相容性功能已正確設定。</span><span class="sxs-lookup"><span data-stu-id="8879c-125">Ensure that the hardware compatibility feature is correctly configured when your organization has older hardware that does not support BitLocker.</span></span>

 

**<span data-ttu-id="8879c-126">管理硬體相容性</span><span class="sxs-lookup"><span data-stu-id="8879c-126">To manage hardware compatibility</span></span>**

1.  <span data-ttu-id="8879c-127">開啟網頁瀏覽器，然後流覽至 Microsoft BitLocker 管理及監視網站。</span><span class="sxs-lookup"><span data-stu-id="8879c-127">Open a web browser and navigate to the Microsoft BitLocker Administration and Monitoring website.</span></span> <span data-ttu-id="8879c-128">選取左側功能表列中的 [**硬體**]。</span><span class="sxs-lookup"><span data-stu-id="8879c-128">Select **Hardware** in the left menu bar.</span></span>

2.  <span data-ttu-id="8879c-129">在右窗格中，按一下 [**高級搜尋**]，然後篩選，以顯示**功能**狀態為 [**未知**] 的所有電腦模型的清單。</span><span class="sxs-lookup"><span data-stu-id="8879c-129">On the right pane, click **Advanced Search**, and then filter to display a list of all computer models that have a **Capability** status of **Unknown**.</span></span> <span data-ttu-id="8879c-130">隨即會顯示符合搜尋準則的電腦模型清單。</span><span class="sxs-lookup"><span data-stu-id="8879c-130">A list of computer models matching the search criteria is displayed.</span></span> <span data-ttu-id="8879c-131">系統管理員可以在此頁面上新增、編輯或移除新的電腦類型。</span><span class="sxs-lookup"><span data-stu-id="8879c-131">Administrators can add, edit, or remove new computer types from this page.</span></span>

3.  <span data-ttu-id="8879c-132">查看每個未知的硬體設定，以判斷是否應該將設定設為**相容**或**不相容**。</span><span class="sxs-lookup"><span data-stu-id="8879c-132">Review each unknown hardware configuration to determine whether the configuration should be set to **Compatible** or **Incompatible**.</span></span>

4.  <span data-ttu-id="8879c-133">選取一或多個列，然後按一下 [**設定相容**] 或 [**設定不相容**]，針對所選的電腦模型設定 BitLocker 相容性（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="8879c-133">Select one or more rows, and then click either **Set Compatible** or **Set Incompatible** to set the BitLocker compatibility, as appropriate, for the selected computer models.</span></span> <span data-ttu-id="8879c-134">如果設定為 [**相容**]，BitLocker 會嘗試在符合支援的模型的電腦上強制執行磁片磁碟機加密原則。</span><span class="sxs-lookup"><span data-stu-id="8879c-134">If set to **Compatible**, BitLocker tries to enforce drive encryption policy on computers that match the supported model.</span></span> <span data-ttu-id="8879c-135">如果設定為**不相容**，BitLocker 將不會在那些電腦上強制執行磁片磁碟機加密原則。</span><span class="sxs-lookup"><span data-stu-id="8879c-135">If set to **Incompatible**, BitLocker will not enforce drive encryption policy on those computers.</span></span>

    <span data-ttu-id="8879c-136">**記事** 將電腦模型設定為相容後，MBAM 用戶端可能需要24小時以上的時間，才能在符合該硬體模型的電腦上開始 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="8879c-136">**Note** After you set a computer model as compatible, it can take more than twenty-four hours for the MBAM Client to begin BitLocker encryption on the computers matching that hardware model.</span></span>

     

5.  <span data-ttu-id="8879c-137">系統管理員應該定期監視硬體相容性清單，以查看由 MBAM 代理程式探索的新模型，然後將其相容性設定更新為**相容**或**不相容**（視情況而定）。</span><span class="sxs-lookup"><span data-stu-id="8879c-137">Administrators should regularly monitor the hardware compatibility list to review new models that are discovered by the MBAM agent, and then update their compatibility setting to **Compatible** or **Incompatible** as appropriate.</span></span>

## <span data-ttu-id="8879c-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="8879c-138">Related topics</span></span>


[<span data-ttu-id="8879c-139">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="8879c-139">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





