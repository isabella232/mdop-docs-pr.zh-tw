---
title: AGPM 技術概觀
description: AGPM 技術概觀
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801761"
---
# <span data-ttu-id="e51a1-103">AGPM 技術概觀</span><span class="sxs-lookup"><span data-stu-id="e51a1-103">Technical Overview of AGPM</span></span>


<span data-ttu-id="e51a1-104">Microsoft 高級群組原則管理（AGPM）是用戶端/伺服器應用程式。</span><span class="sxs-lookup"><span data-stu-id="e51a1-104">Microsoft Advanced Group Policy Management (AGPM) is a client/server application.</span></span> <span data-ttu-id="e51a1-105">AGPM 服務器會將 [封存] 中的 [群組原則物件] （Gpo）離線，在伺服器的檔案系統上建立。</span><span class="sxs-lookup"><span data-stu-id="e51a1-105">The AGPM Server stores Group Policy Objects (GPOs) offline in the archive that AGPM creates on the server's file system.</span></span> <span data-ttu-id="e51a1-106">群組原則管理員使用群組原則管理主控台（GPMC）的 AGPM 管理單元來處理託管封存的伺服器上的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-106">Group Policy administrators use the AGPM snap-in for the Group Policy Management Console (GPMC) to work with GPOs on the server that hosts the archive.</span></span> <span data-ttu-id="e51a1-107">瞭解 AGPM 與相關專案的各個部分、如何將 Gpo 儲存在檔案系統中，以及許可權如何控制每個使用者角色的可用動作，以使用 AGPM 改善群組原則管理員的效能。</span><span class="sxs-lookup"><span data-stu-id="e51a1-107">Understanding the parts of AGPM and related items, how they store GPOs in the file system, and how permissions control the actions available to each user role can improve Group Policy administrators' effectiveness with AGPM.</span></span>

## <span data-ttu-id="e51a1-108">詞彙</span><span class="sxs-lookup"><span data-stu-id="e51a1-108">Terminology</span></span>


<span data-ttu-id="e51a1-109">下列說明基本的 AGPM 詞彙。</span><span class="sxs-lookup"><span data-stu-id="e51a1-109">The following explains the basic AGPM terms.</span></span>

-   <span data-ttu-id="e51a1-110">**AGPM 用戶端：** 針對群組原則管理主控台（GPMC）及從哪個群組原則管理員管理 Gpo 的 [AGPM] 管理單元執行的電腦。</span><span class="sxs-lookup"><span data-stu-id="e51a1-110">**AGPM Client:** A computer that runs the AGPM snap-in for the Group Policy Management Console (GPMC) and from which Group Policy administrators manage GPOs.</span></span>

-   <span data-ttu-id="e51a1-111">**AGPM 管理單元：** 在 AGPM 用戶端上安裝的 AGPM 軟體元件，讓他們可以管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-111">**AGPM snap-in:** The software component of AGPM installed on AGPM Clients so that they can manage GPOs.</span></span>

-   <span data-ttu-id="e51a1-112">**AGPM 服務器：** 執行 AGPM 服務並管理封存的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e51a1-112">**AGPM Server:** A server that runs the AGPM Service and manages an archive.</span></span> <span data-ttu-id="e51a1-113">每個 AGPM 服務器只能管理一個封存，但一個 AGPM 服務器可以在一個封存中管理多個網域的封存資料。</span><span class="sxs-lookup"><span data-stu-id="e51a1-113">Each AGPM Server can manage only one archive, but one AGPM Server can manage archive data for multiple domains in one archive.</span></span> <span data-ttu-id="e51a1-114">封存可以存放在 AGPM 服務器以外的電腦上。</span><span class="sxs-lookup"><span data-stu-id="e51a1-114">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="e51a1-115">**AGPM 服務：** 在 AGPM 服務器上執行的 AGPM 軟體元件（作為服務）。</span><span class="sxs-lookup"><span data-stu-id="e51a1-115">**AGPM Service:** The software component of AGPM that runs on an AGPM Server as a service.</span></span> <span data-ttu-id="e51a1-116">此服務會管理封存中以及該目錄林中生產環境中的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-116">The service manages GPOs in the archive and in the production environment in that forest.</span></span>

-   <span data-ttu-id="e51a1-117">封存 **：** 在 AGPM 中，包含相關聯的 AGPM 服務器所管理之受管理 Gpo 的中央存放區，除了每個 Gpo 的歷史記錄以外。</span><span class="sxs-lookup"><span data-stu-id="e51a1-117">**Archive:** In AGPM, a central store that contains the controlled GPOs that the associated AGPM Server manages, in addition to the history for each of those GPOs.</span></span> <span data-ttu-id="e51a1-118">這包括每個 GPO 以前的所有受控制版本。</span><span class="sxs-lookup"><span data-stu-id="e51a1-118">This includes all previous controlled versions of each GPO.</span></span> <span data-ttu-id="e51a1-119">封存包含封存索引檔案和相關的封存資料，可能會在多個網域中包含 Gpo 的資料。</span><span class="sxs-lookup"><span data-stu-id="e51a1-119">An archive consists of an archive index file and associated archive data that may include data for GPOs in multiple domains.</span></span> <span data-ttu-id="e51a1-120">封存可以存放在 AGPM 服務器以外的電腦上。</span><span class="sxs-lookup"><span data-stu-id="e51a1-120">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="e51a1-121">**受控制的 GPO：** 由 AGPM 管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="e51a1-121">**Controlled GPO:** A GPO that is being managed by AGPM.</span></span> <span data-ttu-id="e51a1-122">AGPM 會管理受管理 Gpo 的記錄和許可權，並將其儲存在封存中。</span><span class="sxs-lookup"><span data-stu-id="e51a1-122">AGPM manages the history and permissions of controlled GPOs, which it stores in the archive.</span></span>

-   <span data-ttu-id="e51a1-123">無法**控制的 GPO：** 網域的生產環境中的 GPO，且不由 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="e51a1-123">**Uncontrolled GPO:** A GPO in the production environment for a domain and not managed by AGPM.</span></span>

## <span data-ttu-id="e51a1-124">要安裝、建立及影響的 AGPM</span><span class="sxs-lookup"><span data-stu-id="e51a1-124">What AGPM installs, creates, and affects</span></span>


<span data-ttu-id="e51a1-125">在 AGPM 服務器上，AGPM 安裝程式會安裝 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="e51a1-125">On an AGPM Server, the AGPM Setup program installs the AGPM Service.</span></span> <span data-ttu-id="e51a1-126">AGPM 不會變更 Active Directory®目錄服務或架構。</span><span class="sxs-lookup"><span data-stu-id="e51a1-126">AGPM does not alter the Active Directory® directory service or the schema.</span></span> <span data-ttu-id="e51a1-127">根據預設，AGPM Server 程式檔案會安裝在%ProgramFiles%\\Microsoft\\AGPM\\Server。</span><span class="sxs-lookup"><span data-stu-id="e51a1-127">By default, the AGPM Server program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Server.</span></span> <span data-ttu-id="e51a1-128">如果您需要的話，您可以在網網域控制站上安裝 AGPM 服務;不過，我們建議您在成員伺服器上安裝 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="e51a1-128">You can install the AGPM Service on a domain controller if you have to; however, we recommend that you install the AGPM Service on a member server.</span></span>

<span data-ttu-id="e51a1-129">在 AGPM 用戶端上，AGPM 安裝程式會安裝 AGPM 管理單元，將**變更控制**資料夾新增至 GPMC 中出現的每個網域。</span><span class="sxs-lookup"><span data-stu-id="e51a1-129">On an AGPM Client, the AGPM Setup program installs the AGPM snap-in, adding a **Change Control** folder to each domain that appears in the GPMC.</span></span> <span data-ttu-id="e51a1-130">根據預設，AGPM 用戶端程式檔案會安裝在%ProgramFiles%\\Microsoft\\AGPM\\Client。</span><span class="sxs-lookup"><span data-stu-id="e51a1-130">By default, the AGPM Client program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Client.</span></span>

<span data-ttu-id="e51a1-131">表格1說明 AGPM 所安裝或建立的專案，以及影響 AGPM 操作的作業系統部分。</span><span class="sxs-lookup"><span data-stu-id="e51a1-131">Table 1 describes both the items that AGPM installs or creates and the parts of the operating system that affect AGPM operation.</span></span>

**<span data-ttu-id="e51a1-132">表格1：由 AGPM 安裝、建立或影響的專案</span><span class="sxs-lookup"><span data-stu-id="e51a1-132">Table 1: Items installed, created, or affected by AGPM</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e51a1-133">項目</span><span class="sxs-lookup"><span data-stu-id="e51a1-133">Item</span></span></th>
<th align="left"><span data-ttu-id="e51a1-134">描述</span><span class="sxs-lookup"><span data-stu-id="e51a1-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e51a1-135">AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="e51a1-135">AGPM Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-136">AGPM 服務會在 AGPM 服務器上執行。</span><span class="sxs-lookup"><span data-stu-id="e51a1-136">The AGPM Service runs on the AGPM Server.</span></span> <span data-ttu-id="e51a1-137">此服務會管理包含在生產環境中的離線 Gpo 和受控 Gpo 的封存。</span><span class="sxs-lookup"><span data-stu-id="e51a1-137">The service manages the archive, which contains offline GPOs, and controlled GPOs in the production environment.</span></span> <span data-ttu-id="e51a1-138">AGPM 服務的預設設定如下所示：</span><span class="sxs-lookup"><span data-stu-id="e51a1-138">The default configuration of the AGPM Service is as follows:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e51a1-139">服務名稱： </strong> AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="e51a1-139">Service name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-140">顯示名稱： </strong> AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="e51a1-140">Display name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-141">可執行檔的路徑： </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</span><span class="sxs-lookup"><span data-stu-id="e51a1-141">Path to executable:</strong> %ProgramFiles%\Microsoft\AGPM\Server\Agpm.exe</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-142">啟動： </strong> 自動</span><span class="sxs-lookup"><span data-stu-id="e51a1-142">Startup:</strong> Automatic</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-143">在 </strong> 安裝 Agpm Server 期間指定的 Agpm 服務帳戶（可使用 <strong> </strong> [控制台] 中的 [程式和功能] 變更）來登入 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e51a1-143">Log on as:</strong> AGPM Service Account specified during installation of AGPM Server, which can be changed using <strong>Programs and Features</strong> in the <strong>Control Panel</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e51a1-144">AGPM 封存</span><span class="sxs-lookup"><span data-stu-id="e51a1-144">AGPM archive</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-145">根據預設，AGPM 會在 AGPM 服務器的%ProgramData%\Microsoft\AGPM 中建立封存。</span><span class="sxs-lookup"><span data-stu-id="e51a1-145">By default, AGPM creates the archive in %ProgramData%\Microsoft\AGPM on the AGPM Server.</span></span> <span data-ttu-id="e51a1-146">封存可提供離線 Gpo 的儲存空間，而且可以儲存每個 GPO 的多個版本。</span><span class="sxs-lookup"><span data-stu-id="e51a1-146">The archive provides storage for offline GPOs, and it can store multiple versions of each GPO.</span></span> <span data-ttu-id="e51a1-147">AGPM 對封存中的 Gpo 所做的變更不會影響生產環境，除非 AGPM 管理員或核准者將 GPO 部署到生產環境，並將 gpo 連結至組織單位（OU）。</span><span class="sxs-lookup"><span data-stu-id="e51a1-147">Changes that AGPM makes to GPOs in the archive do not affect the production environment until an AGPM Administrator or Approver deploys the GPO to the production environment and links the GPO to an organizational unit (OU).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e51a1-148">Windows 防火牆</span><span class="sxs-lookup"><span data-stu-id="e51a1-148">Windows Firewall</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-149">在安裝期間，AGPM 會啟用入站 Windows 防火牆規則，讓 AGPM 用戶端可以與 AGPM 服務器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e51a1-149">During installation, AGPM enables an inbound Windows Firewall rule that allows the AGPM Client to communicate with the AGPM Server.</span></span> <span data-ttu-id="e51a1-150">預設的 Windows 防火牆規則如下所示：</span><span class="sxs-lookup"><span data-stu-id="e51a1-150">The default Windows Firewall rule is the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e51a1-151">名稱： </strong> AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="e51a1-151">Name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-152">動作： </strong> 允許連線</span><span class="sxs-lookup"><span data-stu-id="e51a1-152">Action:</strong> Allow the connection</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-153">程式： </strong> 符合指定條件的所有程式</span><span class="sxs-lookup"><span data-stu-id="e51a1-153">Programs:</strong> All programs that meet the specified conditions</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-154">通訊協定類型： </strong> TCP</span><span class="sxs-lookup"><span data-stu-id="e51a1-154">Protocol type:</strong> TCP</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-155">本機埠： </strong> 4600</span><span class="sxs-lookup"><span data-stu-id="e51a1-155">Local port:</strong> 4600</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-156">遠端埠： </strong> 所有埠</span><span class="sxs-lookup"><span data-stu-id="e51a1-156">Remote port:</strong> All ports</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-157">本機 IP 位址： </strong> 任何</span><span class="sxs-lookup"><span data-stu-id="e51a1-157">Local IP address:</strong> Any</span></span></p></li>
<li><p><strong><span data-ttu-id="e51a1-158">遠端 IP 位址： </strong> 任何</span><span class="sxs-lookup"><span data-stu-id="e51a1-158">Remote IP address:</strong> Any</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e51a1-159">電子郵件伺服器</span><span class="sxs-lookup"><span data-stu-id="e51a1-159">E-mail server</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-160">AGPM 使用簡易郵件傳輸通訊協定（SMTP），將電子郵件要求傳送到 [ <strong> 網域委派] 索引標籤上設定的位址 </strong> 。例如，當編輯者要求建立新的 GPO 時，AGPM 會通知您在 [網域委派] 索引標籤上指定的每個電子郵件地址 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e51a1-160">AGPM uses Simple Mail Transfer Protocol (SMTP) to send e-mail requests to the addresses configured on the <strong>Domain Delegation</strong> tab. For example, when an Editor requests that a new GPO be created, AGPM notifies each e-mail address specified on the <strong>Domain Delegation</strong> tab.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e51a1-161">AGPM 管理單元</span><span class="sxs-lookup"><span data-stu-id="e51a1-161">AGPM snap-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-162">GPMC 的 AGPM 管理單元是在 AGPM 用戶端上執行，由群組原則管理員用來管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-162">The AGPM snap-in for the GPMC runs on AGPM Clients and is used by Group Policy administrators to manage GPOs.</span></span> <span data-ttu-id="e51a1-163">管理單元會出現在 GPMC 中，成為 <strong> 每個網域中的 [變更控制] </strong> 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e51a1-163">The snap-in appears in the GPMC as a <strong>Change Control</strong> folder in each domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e51a1-164">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e51a1-164">Additional references</span></span>

<span data-ttu-id="e51a1-165">如需有關 AGPM 所安裝之檔案的詳細資訊，請參閱[適用于 agpm 的規劃指南](https://go.microsoft.com/fwlink/?LinkId=160060)。</span><span class="sxs-lookup"><span data-stu-id="e51a1-165">For more information about the files installed by AGPM, see the [Planning Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160060).</span></span>

## <span data-ttu-id="e51a1-166">Archive</span><span class="sxs-lookup"><span data-stu-id="e51a1-166">Archive</span></span>


<span data-ttu-id="e51a1-167">根據預設，AGPM 服務器安裝程式會在%ProgramData%\\Microsoft\\AGPM. 中的 [AGPM 服務器] 本機硬碟上建立封存</span><span class="sxs-lookup"><span data-stu-id="e51a1-167">By default, the AGPM Server installation process creates the archive on the local hard disk of the AGPM Server at %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="e51a1-168">不過，您可以在安裝期間變更路徑，甚至在 AGPM 服務器以外的伺服器上建立封存。</span><span class="sxs-lookup"><span data-stu-id="e51a1-168">However, you can change the path during installation and even create the archive on a server other than the AGPM Server.</span></span>

<span data-ttu-id="e51a1-169">封存包含封存所包含每個版本之 GPO 的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="e51a1-169">The archive contains a subfolder for each version of each GPO the archive contains.</span></span> <span data-ttu-id="e51a1-170">每個子資料夾的名稱是可識別 GPO 版本的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e51a1-170">The name of each subfolder is a GUID that identifies a version of the GPO.</span></span>

<span data-ttu-id="e51a1-171">gpostate.xml 檔案會記錄封存中每個 GPO 的狀態。</span><span class="sxs-lookup"><span data-stu-id="e51a1-171">The gpostate.xml file records the state of each GPO in the archive.</span></span> <span data-ttu-id="e51a1-172">檔案是描述封存內容的資訊清單。</span><span class="sxs-lookup"><span data-stu-id="e51a1-172">The file is a manifest that describes the contents of the archive.</span></span> <span data-ttu-id="e51a1-173">例如，GPO 可以有許多版本，而每個版本都位於封存中自己的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="e51a1-173">For example, a GPO can have many versions, and each version is in its own subfolder in the archive.</span></span> <span data-ttu-id="e51a1-174">gpostate.xml 檔案會指出哪些子資料夾包含不同版本的單一 GPO。</span><span class="sxs-lookup"><span data-stu-id="e51a1-174">The gpostate.xml file indicates which subfolders contain different versions of a single GPO.</span></span> <span data-ttu-id="e51a1-175">此外，GPO 範本在封存中有子資料夾，但 gpostate.xml 指出這些是範本，而不是受控制的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-175">Additionally, GPO templates have subfolders in the archive, but gpostate.xml indicates that these are templates and not controlled GPOs.</span></span> <span data-ttu-id="e51a1-176">同樣地，當群組原則管理員刪除 Gpo 時，AGPM 會在 gpostate.xml 中變更其狀態，以指出它們位於 [**回收站**] 中，但實際上並不會從封存中移除 gpo 的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="e51a1-176">Similarly, when Group Policy administrators delete GPOs, AGPM changes their states in gpostate.xml to indicate that they are in the **Recycle Bin** but does not actually remove the GPOs' subfolders from the archive.</span></span>

<span data-ttu-id="e51a1-177">**小心** 請勿手動編輯 gpostate.xml 或封存所包含的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-177">**Caution** Do not manually edit gpostate.xml or the GPOs the archive contains.</span></span> <span data-ttu-id="e51a1-178">提供這項資訊只是為了加強對 AGPM 封存的瞭解。</span><span class="sxs-lookup"><span data-stu-id="e51a1-178">This information is provided only to enhance understanding of the AGPM archive.</span></span> <span data-ttu-id="e51a1-179">您可以改為使用 AGPM 管理單元來變更 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-179">Instead, use the AGPM snap-in to change GPOs.</span></span>

 

<span data-ttu-id="e51a1-180">當 AGPM 建立封存時，它會將 [完全控制] 提供給系統、系統管理員和 AGPM 服務帳戶（在 AGPM 服務器的設定中指定）。</span><span class="sxs-lookup"><span data-stu-id="e51a1-180">When AGPM creates the archive, it gives Full Control to SYSTEM, Administrators, and the AGPM Service Account (specified in the setup of AGPM Server).</span></span> <span data-ttu-id="e51a1-181">使用 AGPM 管理單元的 AGPM 使用者介面變更許可權，不會改變封存的許可權，因為 AGPM 服務帳戶代表登入的使用者執行所有操作。</span><span class="sxs-lookup"><span data-stu-id="e51a1-181">Changing permissions by using the AGPM user interface on the AGPM snap-in does not alter permissions on the archive, because the AGPM Service Account performs all operations on behalf of the logged-on user.</span></span>

### <span data-ttu-id="e51a1-182">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e51a1-182">Additional references</span></span>

<span data-ttu-id="e51a1-183">如需有關如何備份封存、從備份還原封存，或移動 AGPM 服務器與封存的相關資訊，請參閱[適用于 agpm 的操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)中的「執行 Agpm 系統管理員工作」一節。</span><span class="sxs-lookup"><span data-stu-id="e51a1-183">For information about how to back up the archive, restore the archive from a backup, or move both the AGPM Server and the archive, see the "Performing AGPM Administrator Tasks" section in the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

## <span data-ttu-id="e51a1-184">角色和權限</span><span class="sxs-lookup"><span data-stu-id="e51a1-184">Roles and permissions</span></span>


<span data-ttu-id="e51a1-185">角色簡化委派。</span><span class="sxs-lookup"><span data-stu-id="e51a1-185">Roles simplify delegation.</span></span> <span data-ttu-id="e51a1-186">您可以將四個角色的其中一個角色指派給群組原則管理員，而不是指派詳細的許可權給群組原則系統管理員，以讓他們執行與該角色相關的工作：</span><span class="sxs-lookup"><span data-stu-id="e51a1-186">Instead of assigning detailed permissions to Group Policy administrators, AGPM Administrators can assign one of four roles to Group Policy administrators to let them perform work related to that role:</span></span>

-   <span data-ttu-id="e51a1-187">**AGPM 系統管理員：** 指派給 AGPM 系統管理員（完全控制）角色的群組原則管理員，可以在 AGPM 中執行任何工作。</span><span class="sxs-lookup"><span data-stu-id="e51a1-187">**AGPM Administrator:** Group Policy administrators assigned the AGPM Administrator (Full Control) role can perform any task in AGPM.</span></span> <span data-ttu-id="e51a1-188">AGPM 系統管理員可以設定全域性選項，並委派其他群組原則管理員的許可權。</span><span class="sxs-lookup"><span data-stu-id="e51a1-188">AGPM Administrators can configure domain-wide options and delegate permissions to other Group Policy administrators.</span></span>

-   <span data-ttu-id="e51a1-189">**核准者：** 指派核准者角色的群組原則系統管理員可以將 Gpo 部署到網域的生產環境。</span><span class="sxs-lookup"><span data-stu-id="e51a1-189">**Approver:** Group Policy administrators assigned the Approver role can deploy GPOs to the production environment for a domain.</span></span> <span data-ttu-id="e51a1-190">核准者也可以建立和刪除 Gpo，以及核准或拒絕來自編輯者的要求。</span><span class="sxs-lookup"><span data-stu-id="e51a1-190">Approvers can also create and delete GPOs and approve or reject requests from Editors.</span></span> <span data-ttu-id="e51a1-191">核准者可以在網域中查看 Gpo 的清單、查看 Gpo 中的原則設定，以及建立及查看 GPO 中原則設定的報告。</span><span class="sxs-lookup"><span data-stu-id="e51a1-191">Approvers can view the list of GPOs in a domain, view the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="e51a1-192">他們無法編輯 Gpo 中的原則設定，除非它們也獲指派了 [編輯者] 角色。</span><span class="sxs-lookup"><span data-stu-id="e51a1-192">They cannot edit the policy settings in GPOs unless they are also assigned the Editor role.</span></span>

-   <span data-ttu-id="e51a1-193">**編輯器：** 指派「編輯者角色」的群組原則管理員可以在網域中查看 Gpo 的清單、查看 Gpo 中的原則設定、編輯 Gpo 中的原則設定，以及建立及查看 GPO 中原則設定的報告。</span><span class="sxs-lookup"><span data-stu-id="e51a1-193">**Editor:** Group Policy administrators assigned the Editor role can view the list of GPOs in a domain, view the policy settings in GPOs, edit the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="e51a1-194">除非他們也指派給核准者角色，否則編輯者就無法建立、部署或刪除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-194">Unless they are also assigned the Approver role, Editors cannot create, deploy, or delete GPOs.</span></span> <span data-ttu-id="e51a1-195">不過，他們可以要求建立、部署或刪除 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-195">However, they can request that GPOs be created, deployed, or deleted.</span></span>

-   <span data-ttu-id="e51a1-196">**檢閱者：** 指派檢閱者角色的群組原則管理員可以在網域中查看 Gpo 的清單，並在 GPO 中建立及查看原則設定的報告。</span><span class="sxs-lookup"><span data-stu-id="e51a1-196">**Reviewer:** Group Policy administrators assigned the Reviewer role can view the list of GPOs in a domain and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="e51a1-197">除非它們也獲指派編輯器角色，否則他們無法在 GPO 中編輯策略設定。</span><span class="sxs-lookup"><span data-stu-id="e51a1-197">Unless they are also assigned the Editor role, they cannot edit policy settings in a GPO.</span></span>

<span data-ttu-id="e51a1-198">AGPM 可讓 AGPM 系統管理員利用 AGPM 管理單元，以比角色更詳細的層級來設定許可權。</span><span class="sxs-lookup"><span data-stu-id="e51a1-198">AGPM gives AGPM Administrators the flexibility to configure permissions at a more detailed level than roles by using the AGPM snap-in.</span></span> <span data-ttu-id="e51a1-199">Table 2 說明這些許可權，並指出預設情況下授予每個角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="e51a1-199">Table 2 describes these permissions and indicates the permissions granted to each role by default.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e51a1-200">使用權限</span><span class="sxs-lookup"><span data-stu-id="e51a1-200">Permission</span></span></th>
<th align="left"><span data-ttu-id="e51a1-201">描述</span><span class="sxs-lookup"><span data-stu-id="e51a1-201">Description</span></span></th>
<th align="left"><span data-ttu-id="e51a1-202">AGPM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="e51a1-202">AGPM Administrator</span></span></th>
<th align="left"><span data-ttu-id="e51a1-203">核准者</span><span class="sxs-lookup"><span data-stu-id="e51a1-203">Approver</span></span></th>
<th align="left"><span data-ttu-id="e51a1-204">編輯器</span><span class="sxs-lookup"><span data-stu-id="e51a1-204">Editor</span></span></th>
<th align="left"><span data-ttu-id="e51a1-205">審校</span><span class="sxs-lookup"><span data-stu-id="e51a1-205">Reviewer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-206">完全控制</span><span class="sxs-lookup"><span data-stu-id="e51a1-206">Full Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-207">擁有擁有權限。</span><span class="sxs-lookup"><span data-stu-id="e51a1-207">Have all permissions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-208">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-208">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-209">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="e51a1-209">Create GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-210">在網域中建立 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-210">Create GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-211">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-211">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-212">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-212">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-213">清單內容</span><span class="sxs-lookup"><span data-stu-id="e51a1-213">List Contents</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-214">列出網域中的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="e51a1-214">List the GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-215">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-215">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-216">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-216">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-217">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-217">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-218">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-218">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-219">讀取設定</span><span class="sxs-lookup"><span data-stu-id="e51a1-219">Read Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-220">讀取 GPO 中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="e51a1-220">Read the policy settings within a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-221">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-221">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-222">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-222">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-223">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-223">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-224">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-224">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-225">編輯設定</span><span class="sxs-lookup"><span data-stu-id="e51a1-225">Edit Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-226">變更 GPO 中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="e51a1-226">Change the policy settings in a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-227">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-227">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e51a1-228">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-228">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-229">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="e51a1-229">Delete GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-230">刪除 GPO。</span><span class="sxs-lookup"><span data-stu-id="e51a1-230">Delete a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-231">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-231">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-232">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-232">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-233">修改安全性</span><span class="sxs-lookup"><span data-stu-id="e51a1-233">Modify Security</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-234">委派網域層級存取、委派單一 GPO 的存取權，以及委派對生產環境的存取權。</span><span class="sxs-lookup"><span data-stu-id="e51a1-234">Delegate domain-level access, delegate access to a single GPO, and delegate access to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-235">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-235">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-236">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="e51a1-236">Deploy GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-237">將 GPO 從封存部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="e51a1-237">Deploy a GPO from the archive to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-238">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-238">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-239">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-239">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-240">建立範本</span><span class="sxs-lookup"><span data-stu-id="e51a1-240">Create Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-241">在 AGPM 中建立 GPO 範本。</span><span class="sxs-lookup"><span data-stu-id="e51a1-241">Create a GPO template in AGPM.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-242">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-242">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e51a1-243">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-243">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-244">修改選項</span><span class="sxs-lookup"><span data-stu-id="e51a1-244">Modify Options</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-245">設定 AGPM 電子郵件通知，並限制儲存在封存中的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="e51a1-245">Configure AGPM e-mail notification and limit the GPO versions stored in the archive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-246">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-246">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e51a1-247">匯出 GPO</span><span class="sxs-lookup"><span data-stu-id="e51a1-247">Export GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-248">將 GPO 匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="e51a1-248">Export a GPO to a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-249">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-249">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e51a1-250">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-250">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e51a1-251">匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="e51a1-251">Import GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e51a1-252">從檔案匯入 GPO。</span><span class="sxs-lookup"><span data-stu-id="e51a1-252">Import a GPO from a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e51a1-253">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-253">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="e51a1-254">是</span><span class="sxs-lookup"><span data-stu-id="e51a1-254">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e51a1-255">**記事** 
在 AGPM 3.0 或2.5 中無法使用**匯出 gpo**和匯**入 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="e51a1-255">**Note**
**Export GPO** and **Import GPO** permissions are not available in AGPM 3.0 or 2.5.</span></span>

<span data-ttu-id="e51a1-256">在 AGPM 2.5 中，您無法委派對網域生產環境中 Gpo 的存取權，以及限制儲存之 GPO 版本數的能力。</span><span class="sxs-lookup"><span data-stu-id="e51a1-256">The ability to delegate access to GPOs in the production environment for a domain and the ability to limit the number of GPO versions stored are not available in AGPM 2.5.</span></span>

 

### <span data-ttu-id="e51a1-257">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e51a1-257">Additional references</span></span>

<span data-ttu-id="e51a1-258">如需有關指派特定角色的群群組原則系統管理員或關於執行特定工作所需的許可權的相關資訊，請參閱適用于 AGPM 的[操作指南](https://go.microsoft.com/fwlink/?LinkId=160061)。</span><span class="sxs-lookup"><span data-stu-id="e51a1-258">For information about what tasks can be performed by Group Policy administrators assigned a particular role or about which permissions are required to perform a specific task, see the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

 

 





