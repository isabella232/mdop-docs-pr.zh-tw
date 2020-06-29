---
title: 驗證 MED-V 終端使用者
description: 驗證 MED-V 終端使用者
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810826"
---
# <span data-ttu-id="1fb41-103">驗證 MED-V 終端使用者</span><span class="sxs-lookup"><span data-stu-id="1fb41-103">Authentication of MED-V End Users</span></span>


<span data-ttu-id="1fb41-104">驗證 Microsoft 企業桌面虛擬化（MED-V）2.0 使用者是一個非常重要的安全性問題。</span><span class="sxs-lookup"><span data-stu-id="1fb41-104">The authentication of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 end users is a very important security issue.</span></span> <span data-ttu-id="1fb41-105">在這種情況下，驗證是指驗證 MED-V 端使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="1fb41-105">In this context, authentication refers to verifying the identity of the MED-V end user.</span></span>

<span data-ttu-id="1fb41-106">下列章節提供有關 MED-V 中的使用者驗證的資訊與指導方針。</span><span class="sxs-lookup"><span data-stu-id="1fb41-106">The following section provides information and guidance about end-user authentication in MED-V.</span></span>

## <span data-ttu-id="1fb41-107">MED-V 中的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="1fb41-107">User Authentication in MED-V</span></span>


<span data-ttu-id="1fb41-108">MED-V 中的驗證通常會發生在兩個層面：使用者第一次存取 MED-V，以及每次變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="1fb41-108">Authentication in MED-V generally occurs at two levels: when a user first accesses MED-V and every time that they change their password.</span></span>

<span data-ttu-id="1fb41-109">根據您設定的 MED-V 設定進行驗證的方式，通常會在您第一次啟動 MED-V 或第一次嘗試開啟已發佈的應用程式時，在某些時候提示使用者輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="1fb41-109">Depending on how you have configured MED-V settings for authentication, the end user is typically prompted at some point to enter their password, either the first time MED-V is started or the first time that they try to open a published application.</span></span>

<span data-ttu-id="1fb41-110">最終使用者驗證的幾個層面可供您控制，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="1fb41-110">There are several aspects of end-user authentication that you can control, including the following:</span></span>

<span data-ttu-id="1fb41-111">使用者輸入的認證是否儲存在認證管理員中</span><span class="sxs-lookup"><span data-stu-id="1fb41-111">Whether the credentials the end user enters are stored in Credential Manager</span></span>

<span data-ttu-id="1fb41-112">最終使用者呈現的方式，提供輸入並儲存密碼的選項</span><span class="sxs-lookup"><span data-stu-id="1fb41-112">In what manner the end user is presented with the option of entering and saving their password</span></span>

<span data-ttu-id="1fb41-113">根據貴公司管理使用者驗證的首選程式，您可以指定是否要針對特定的 MED-V 工作區進行認證快取。</span><span class="sxs-lookup"><span data-stu-id="1fb41-113">Depending on your company’s preferred process for managing end-user authentication, you can specify whether credential caching occurs for a particular MED-V workspace.</span></span> <span data-ttu-id="1fb41-114">因為使用者只會收到一次密碼的提示，所以快取使用者的認證很有説明。</span><span class="sxs-lookup"><span data-stu-id="1fb41-114">Caching the credentials of an end user is helpful because they are only prompted one time for their password.</span></span> <span data-ttu-id="1fb41-115">如果使用者每次啟動新的 MED-V 會話時，都不能儲存其密碼或決定不要，必須再次輸入。</span><span class="sxs-lookup"><span data-stu-id="1fb41-115">If the end user is not allowed to save their password or they decide not to, every time that they start a new MED-V session, they must enter it again.</span></span> <span data-ttu-id="1fb41-116">例如，如果 MED-V 設定為在使用者登入主機時開始，但已停用驗證，則在登入時只會提示使用者一次。</span><span class="sxs-lookup"><span data-stu-id="1fb41-116">For example, if MED-V is configured to start when the end user logs on to the host but Authentication is disabled, the end user is only prompted one time during logon.</span></span> <span data-ttu-id="1fb41-117">在這種情況下，認證會一直有效，直到最終使用者從主機登出為止。</span><span class="sxs-lookup"><span data-stu-id="1fb41-117">In this case, credentials are valid until the end user logs off from the host.</span></span>

<span data-ttu-id="1fb41-118">如有需要，您可以使用認證管理員來移除任何已儲存的最終使用者認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-118">If it is necessary, you can use Credential Manager to remove any stored end-user credentials.</span></span>

<span data-ttu-id="1fb41-119">根據預設，認證儲存已停用，但您可以透過下列其中一種方法變更此設定：</span><span class="sxs-lookup"><span data-stu-id="1fb41-119">By default, credential storing is disabled, but you can change this setting through one of the following methods:</span></span>

<span data-ttu-id="1fb41-120">**當您建立 med-v 工作區套件時**。</span><span class="sxs-lookup"><span data-stu-id="1fb41-120">**While you are creating the MED-V workspace package**.</span></span> <span data-ttu-id="1fb41-121">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="1fb41-121">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="1fb41-122">**部署 med-v 工作區後**。</span><span class="sxs-lookup"><span data-stu-id="1fb41-122">**After you have deployed the MED-V workspace**.</span></span> <span data-ttu-id="1fb41-123">編輯 MED-V Cmdlet 參數 UxCredentialCacheEnabled，以設定終端服務登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="1fb41-123">Edit the MED-V cmdlet parameter UxCredentialCacheEnabled to set the Terminal Services registry key.</span></span> <span data-ttu-id="1fb41-124">如需詳細資訊，請參閱 Windows PowerShell 說明。</span><span class="sxs-lookup"><span data-stu-id="1fb41-124">For more information, see Windows PowerShell Help.</span></span>

<span data-ttu-id="1fb41-125">在 MED-V 工作區部署之後，您可以修改名為 DisablePasswordSaving 的終端服務原則，以設定使用者對使用者驗證的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="1fb41-125">After MED-V workspace deployment, you can set your preference for end-user authentication by modifying the Terminal Services policy named DisablePasswordSaving.</span></span> <span data-ttu-id="1fb41-126">DisablePasswordSaving 控制 [RDP 用戶端] 對話方塊視窗是否出現 [密碼儲存] 核取方塊，以及是否顯示 MED-V 認證提示。</span><span class="sxs-lookup"><span data-stu-id="1fb41-126">DisablePasswordSaving controls whether the password saving check box appears on the RDP client dialog window and whether the MED-V credential prompt is displayed.</span></span>

<span data-ttu-id="1fb41-127">下列是名為 DisablePasswordSaving 的終端服務原則的原則路徑。</span><span class="sxs-lookup"><span data-stu-id="1fb41-127">Following is the policy path for the Terminal Services policy named DisablePasswordSaving.</span></span>

**<span data-ttu-id="1fb41-128">註冊表</span><span class="sxs-lookup"><span data-stu-id="1fb41-128">Regedit:</span></span>**

<span data-ttu-id="1fb41-129">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="1fb41-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving</span></span>

**<span data-ttu-id="1fb41-130">注意</span><span class="sxs-lookup"><span data-stu-id="1fb41-130">Note</span></span>**  
<span data-ttu-id="1fb41-131">您對 DisablePasswordSaving 所做的變更只會影響 RDP 提示至虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="1fb41-131">The changes that you make to DisablePasswordSaving only affect the RDP prompt to a virtual machine.</span></span>



<span data-ttu-id="1fb41-132">下表列出您可以用來設定認證儲存空間與不同設定效果的不同方式：</span><span class="sxs-lookup"><span data-stu-id="1fb41-132">The following table lists the different ways you can configure your settings for credential storing and the effects of the different configurations:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1fb41-133">值</span><span class="sxs-lookup"><span data-stu-id="1fb41-133">Value</span></span></th>
<th align="left"><span data-ttu-id="1fb41-134">設定</span><span class="sxs-lookup"><span data-stu-id="1fb41-134">Configuration</span></span></th>
<th align="left"><span data-ttu-id="1fb41-135">結果</span><span class="sxs-lookup"><span data-stu-id="1fb41-135">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1fb41-136">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="1fb41-136">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1fb41-137">停用</span><span class="sxs-lookup"><span data-stu-id="1fb41-137">Disabled</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1fb41-138">隨後便會出現 MED-V 提示，且可使用並清除 [接受] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1fb41-138">The MED-V prompt is presented and a check box to accept is available and cleared.</span></span> <span data-ttu-id="1fb41-139">如果使用者選取核取方塊，就會針對後續使用來緩存認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-139">If the end user selects the check box, credentials are cached for subsequent use.</span></span> <span data-ttu-id="1fb41-140">當密碼到期時，最終使用者也有只會出現提示的好處。</span><span class="sxs-lookup"><span data-stu-id="1fb41-140">The end user also has the benefit of only being prompted when the password expires.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="1fb41-141">如果使用者沒有選取核取方塊，則會出現 [遠端桌面連線（RDC）] 用戶端提示，而不是 MED-V 提示，且已清除 [接受] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1fb41-141">If the end user does not select the check box, the Remote Desktop Connection (RDC) Client prompt is presented instead of the MED-V prompt, and the check box to accept is cleared.</span></span> <span data-ttu-id="1fb41-142">如果使用者選取核取方塊，則會儲存 RDC 用戶端認證以備日後使用。</span><span class="sxs-lookup"><span data-stu-id="1fb41-142">If the end user selects the check box, the RDC Client credential is stored for later use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="1fb41-143">重要</span><span class="sxs-lookup"><span data-stu-id="1fb41-143">Important</span></span></strong><br/><p><span data-ttu-id="1fb41-144">當使用者輸入時，RDC 不會驗證認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-144">RDC does not validate credentials when the end user enters them.</span></span> <span data-ttu-id="1fb41-145">如果使用者透過 RDC 提示來緩存認證，可能會有儲存無法正確認證的風險。</span><span class="sxs-lookup"><span data-stu-id="1fb41-145">If the end user caches the credentials through the RDC prompt, there is a risk that incorrect credentials might be stored.</span></span> <span data-ttu-id="1fb41-146">在這種情況下，必須在 Windows 認證管理器中刪除不正確的認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-146">In this case, the incorrect credentials must be deleted in the Windows Credential Manager.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1fb41-147">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="1fb41-147">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1fb41-148">啟用</span><span class="sxs-lookup"><span data-stu-id="1fb41-148">Enabled</span></span></strong></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="1fb41-149">注意</span><span class="sxs-lookup"><span data-stu-id="1fb41-149">Note</span></span></strong><br/><p><span data-ttu-id="1fb41-150">這種設定較安全，因為它不允許快取使用者認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-150">This configuration is more secure because it does not allow end user credentials to be cached.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="1fb41-151">根據預設，MED-V 安裝會將來賓中的登錄機碼設為抑制「要過期的密碼」提示。</span><span class="sxs-lookup"><span data-stu-id="1fb41-151">By default, the MED-V installation sets a registry key in the guest to suppress the "password about to expire" prompt.</span></span> <span data-ttu-id="1fb41-152">系統只會提示使用者在主機上變更密碼。</span><span class="sxs-lookup"><span data-stu-id="1fb41-152">The end user is only prompted for a password change on the host.</span></span> <span data-ttu-id="1fb41-153">主機上更新的認證會傳遞到來賓。</span><span class="sxs-lookup"><span data-stu-id="1fb41-153">Credentials that are updated on the host are passed to the guest.</span></span>

**<span data-ttu-id="1fb41-154">警告</span><span class="sxs-lookup"><span data-stu-id="1fb41-154">Caution</span></span>**  
<span data-ttu-id="1fb41-155">如果您在您的環境中使用群組原則，請知道它可以覆寫登錄機碼，導致來自來賓的密碼提示再次出現。</span><span class="sxs-lookup"><span data-stu-id="1fb41-155">If you use Group Policy in your environment, know that it can override the registry key causing the password prompts from the guest to reappear.</span></span>



### <span data-ttu-id="1fb41-156">驗證的安全性問題</span><span class="sxs-lookup"><span data-stu-id="1fb41-156">Security Concerns with Authentication</span></span>

<span data-ttu-id="1fb41-157">雖然快取最終使用者的認證能提供最佳的使用者體驗，您必須知道所涉及的風險。</span><span class="sxs-lookup"><span data-stu-id="1fb41-157">Even though caching the end user’s credentials provides the best user experience, you must be aware of the risks involved.</span></span>

<span data-ttu-id="1fb41-158">啟用認證快取時，使用者的網域認證會以可還原的格式儲存在 Windows 認證管理員中。</span><span class="sxs-lookup"><span data-stu-id="1fb41-158">When credential caching is enabled, the end user’s domain credential is stored in a reversible format within the Windows Credential Manager.</span></span> <span data-ttu-id="1fb41-159">因此，攻擊者可以撰寫以系統層級程式或使用者程式來執行的工具，並會檢索最終使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="1fb41-159">As a result, an attacker could write a tool that runs as either a system level process or an end user process and that retrieves the end user's credentials.</span></span> <span data-ttu-id="1fb41-160">您只需要將 DisablePasswordSaving 設定為 [**啟用**]，就能減輕此風險。</span><span class="sxs-lookup"><span data-stu-id="1fb41-160">You can only lessen this risk by setting DisablePasswordSaving to **Enabled**.</span></span>

<span data-ttu-id="1fb41-161">當 MED-V 驗證已停用，但已啟用 [終端服務原則] 設定時，也會有這個問題。</span><span class="sxs-lookup"><span data-stu-id="1fb41-161">This same concern exists when MED-V authentication is disabled but the Terminal Services policy setting is enabled.</span></span>

## <span data-ttu-id="1fb41-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="1fb41-162">Related topics</span></span>


[<span data-ttu-id="1fb41-163">MED-V 作業的安全性最佳做法</span><span class="sxs-lookup"><span data-stu-id="1fb41-163">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)









