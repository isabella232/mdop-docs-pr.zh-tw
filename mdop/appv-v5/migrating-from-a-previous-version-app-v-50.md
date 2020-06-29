---
title: 從舊版移轉
description: 從舊版移轉
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800373"
---
# <span data-ttu-id="2021b-103">從舊版移轉</span><span class="sxs-lookup"><span data-stu-id="2021b-103">Migrating from a Previous Version</span></span>


<span data-ttu-id="2021b-104">借助 App-V 5.0，您可以將現有的 App-v 4.6 基礎結構遷移至更具彈性、整合且更輕鬆管理的 App-v 5.0 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="2021b-104">With App-V 5.0 you can migrate your existing App-V 4.6 infrastructure to the more flexible, integrated, and easier to manage App-V 5.0 infrastructure.</span></span>

<span data-ttu-id="2021b-105">規劃您的遷移策略時，請考慮下列各節：</span><span class="sxs-lookup"><span data-stu-id="2021b-105">Consider the following sections when you plan your migration strategy:</span></span>

<span data-ttu-id="2021b-106">**記事** 如需 App-v 4.6 與 App-v 5.0 之間差異的詳細資訊，請參閱[關於 app-v 5.0](about-app-v-50.md)的**app-v 4.6 與 app-v 5.0 區段之間的差異**。</span><span class="sxs-lookup"><span data-stu-id="2021b-106">**Note** For more information about the differences between App-V 4.6 and App-V 5.0, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <span data-ttu-id="2021b-107">轉換使用舊版 App-v （V）建立的套件</span><span class="sxs-lookup"><span data-stu-id="2021b-107">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="2021b-108">使用套件轉換器實用程式來升級使用舊版 App-V 所建立的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-108">Use the package converter utility to upgrade virtual application packages created using previous versions of App-V.</span></span> <span data-ttu-id="2021b-109">套件轉換器使用 PowerShell 來轉換套件，如果您有多個需要轉換的套件，就能協助自動處理常式。</span><span class="sxs-lookup"><span data-stu-id="2021b-109">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="2021b-110">**重要** 在您轉換現有的套件之後，您應該先測試套件，然後再部署套件，以確保轉換程式已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2021b-110">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="2021b-111">轉換現有套件前的須知事項</span><span class="sxs-lookup"><span data-stu-id="2021b-111">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2021b-112">問題</span><span class="sxs-lookup"><span data-stu-id="2021b-112">Issue</span></span></th>
<th align="left"><span data-ttu-id="2021b-113">因應措施</span><span class="sxs-lookup"><span data-stu-id="2021b-113">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-114">不會轉換套件腳本。</span><span class="sxs-lookup"><span data-stu-id="2021b-114">Package scripts are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-115">測試已轉換的套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-115">Test the converted package.</span></span> <span data-ttu-id="2021b-116">如有需要，請轉換腳本。</span><span class="sxs-lookup"><span data-stu-id="2021b-116">If necessary convert the script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2021b-117">不會轉換套件註冊設定覆寫。</span><span class="sxs-lookup"><span data-stu-id="2021b-117">Package registry setting overrides are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-118">測試已轉換的套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-118">Test the converted package.</span></span> <span data-ttu-id="2021b-119">如有需要，請重新新增登錄覆寫。</span><span class="sxs-lookup"><span data-stu-id="2021b-119">If necessary, re-add registry overrides.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-120">在轉換之後，使用 DSC 的虛擬套件不會連結。</span><span class="sxs-lookup"><span data-stu-id="2021b-120">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-121">使用連線群組連結封裝。</span><span class="sxs-lookup"><span data-stu-id="2021b-121">Link the packages using connection groups.</span></span> <span data-ttu-id="2021b-122">請參閱 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 管理連線群組 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-122">See <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2021b-123">在轉換期間偵測到環境變數衝突。</span><span class="sxs-lookup"><span data-stu-id="2021b-123">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-124">解決相關的 .osd 檔案中的任何衝突 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-124">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-125">在轉換期間檢測到硬編碼路徑。</span><span class="sxs-lookup"><span data-stu-id="2021b-125">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-126">硬編碼路徑難以正確轉換。</span><span class="sxs-lookup"><span data-stu-id="2021b-126">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="2021b-127">套件轉換器會檢測並傳回內含硬編碼路徑之檔案的套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-127">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="2021b-128">使用硬編碼路徑來查看檔案，並判斷套件是否需要該檔案。</span><span class="sxs-lookup"><span data-stu-id="2021b-128">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="2021b-129">如果是，建議您重新排列套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-129">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2021b-130">轉換套件時，請檢查是否有失敗的檔案或快速鍵。</span><span class="sxs-lookup"><span data-stu-id="2021b-130">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="2021b-131">在 App-v 4.6 套件中找出該專案。</span><span class="sxs-lookup"><span data-stu-id="2021b-131">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="2021b-132">可能是硬式編碼路徑。</span><span class="sxs-lookup"><span data-stu-id="2021b-132">It could possibly be hard-coded path.</span></span> <span data-ttu-id="2021b-133">轉換路徑。</span><span class="sxs-lookup"><span data-stu-id="2021b-133">Convert the path.</span></span>

<span data-ttu-id="2021b-134">**記事** 建議您使用 App-v 5.0 sequencer 來轉換需要利用功能的重要應用程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="2021b-134">**Note** It is recommended that you use the App-V 5.0 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="2021b-135">請參閱[如何使用 app-v 5.0 來排序新的應用程式](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="2021b-135">See, [How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md).</span></span>

<span data-ttu-id="2021b-136">如果轉換後的套件未在轉換後開啟，建議您使用 App-v 5.0 排序器重新排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="2021b-136">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.0 sequencer.</span></span>

 

[<span data-ttu-id="2021b-137">如何轉換在舊版 App-V 中建立的套件</span><span class="sxs-lookup"><span data-stu-id="2021b-137">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

## <span data-ttu-id="2021b-138">遷移用戶端</span><span class="sxs-lookup"><span data-stu-id="2021b-138">Migrating Clients</span></span>


<span data-ttu-id="2021b-139">下表顯示升級用戶端的建議方法。</span><span class="sxs-lookup"><span data-stu-id="2021b-139">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2021b-140">工作</span><span class="sxs-lookup"><span data-stu-id="2021b-140">Task</span></span></th>
<th align="left"><span data-ttu-id="2021b-141">其他資訊</span><span class="sxs-lookup"><span data-stu-id="2021b-141">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-142">將您的環境升級至 App-V 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="2021b-142">Upgrade your environment to App-V4.6SP2</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="2021b-143">應用程式虛擬化部署和升級考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-143">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2021b-144">安裝 App-V 5.0 用戶端（含共存功能）。</span><span class="sxs-lookup"><span data-stu-id="2021b-144">Install the App-V 5.0 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)"><span data-ttu-id="2021b-145">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-145">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-146">順序及推出 app-v 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-146">Sequence and roll out App-V 5.0 packages.</span></span> <span data-ttu-id="2021b-147">視需要，取消發佈 App-v 4.6 套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-147">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)"><span data-ttu-id="2021b-148">如何使用 App-v 5.0 來排序新的應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-148">How to Sequence a New Application with App-V 5.0</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2021b-149">**重要** 您必須執行 App-V 4.6 SP3，才能使用共存模式。</span><span class="sxs-lookup"><span data-stu-id="2021b-149">**Important** You must be running App-V4.6SP3 to use coexistence mode.</span></span> <span data-ttu-id="2021b-150">此外，當您排列套件時，您必須設定 [管理機構] 設定（位於 **[使用者設定**] 中的 [**使用者**設定] 區段中）。</span><span class="sxs-lookup"><span data-stu-id="2021b-150">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="2021b-151">遷移 app-v 5.0 Server 的完整基礎結構</span><span class="sxs-lookup"><span data-stu-id="2021b-151">Migrating the App-V 5.0 Server Full Infrastructure</span></span>


<span data-ttu-id="2021b-152">沒有直接的方法可升級至完整的 App-v 5.0 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="2021b-152">There is no direct method to upgrade to a full App-V 5.0 infrastructure.</span></span> <span data-ttu-id="2021b-153">請使用下一節中的資訊，以取得有關升級 App-v 伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="2021b-153">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2021b-154">工作</span><span class="sxs-lookup"><span data-stu-id="2021b-154">Task</span></span></th>
<th align="left"><span data-ttu-id="2021b-155">其他資訊</span><span class="sxs-lookup"><span data-stu-id="2021b-155">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-156">將您的環境升級到 App V 4.6 SP3。</span><span class="sxs-lookup"><span data-stu-id="2021b-156">Upgrade your environment to App-V4.6SP3.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="2021b-157">應用程式虛擬化部署和升級考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-157">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2021b-158">部署 app-v 5.0 版本的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2021b-158">Deploy App-V 5.0 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"><span data-ttu-id="2021b-159">如何部署 App-v 用戶端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-159">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2021b-160">安裝 App-V 5.0 server。</span><span class="sxs-lookup"><span data-stu-id="2021b-160">Install App-V 5.0 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"><span data-ttu-id="2021b-161">如何部署 app-v 5.0 伺服器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="2021b-161">How to Deploy the App-V 5.0 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2021b-162">[遷移現有的套件]。</span><span class="sxs-lookup"><span data-stu-id="2021b-162">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2021b-163">請參閱本文中的 [ <strong> 使用先前版本的 app-v 建立的套件] </strong> 區段。</span><span class="sxs-lookup"><span data-stu-id="2021b-163">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2021b-164">其他遷移任務</span><span class="sxs-lookup"><span data-stu-id="2021b-164">Additional Migration tasks</span></span>


<span data-ttu-id="2021b-165">您也可以執行額外的遷移工作，例如重新配置端點，以及開啟在執行 App-v 5.0 用戶端的電腦上使用先前版本建立的套件。</span><span class="sxs-lookup"><span data-stu-id="2021b-165">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.0 client.</span></span> <span data-ttu-id="2021b-166">下列連結提供執行這些工作的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2021b-166">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="2021b-167">如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="2021b-167">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="2021b-168">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="2021b-168">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[<span data-ttu-id="2021b-169">如何為特定電腦上的所有使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="2021b-169">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="2021b-170">如何為特定使用者，將擴充點從 App-V 5.0 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="2021b-170">How to Revert Extension Points From an App-V 5.0 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="2021b-171">執行 App-v 遷移任務的其他資源</span><span class="sxs-lookup"><span data-stu-id="2021b-171">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="2021b-172">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="2021b-172">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="2021b-173">簡化的 Microsoft App-v 5.1 管理伺服器升級程式</span><span class="sxs-lookup"><span data-stu-id="2021b-173">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





