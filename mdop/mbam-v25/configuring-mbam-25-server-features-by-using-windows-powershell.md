---
title: 使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能
description: 使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809596"
---
# <span data-ttu-id="33ee6-103">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="33ee6-103">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>


<span data-ttu-id="33ee6-104">在您安裝 MBAM 2.5 Server 軟體之後，您可以使用 Windows PowerShell Cmdlet 或 [MBAM 伺服器設定] 嚮導，使用 [設定 MBAM 2.5 伺服器功能]。</span><span class="sxs-lookup"><span data-stu-id="33ee6-104">After you install the MBAM 2.5 Server software, you can use configure MBAM 2.5 Server features by using Windows PowerShell cmdlets or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="33ee6-105">本主題描述如何使用 Windows PowerShell Cmdlet 來設定 MBAM 2.5。</span><span class="sxs-lookup"><span data-stu-id="33ee6-105">This topic describes how to configure MBAM 2.5 by using the Windows PowerShell cmdlets.</span></span> <span data-ttu-id="33ee6-106">若要改為使用嚮導，請參閱設定[MBAM 2.5 伺服器功能](configuring-the-mbam-25-server-features.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee6-106">To use the wizard instead, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md).</span></span>

## <span data-ttu-id="33ee6-107">本主題內容</span><span class="sxs-lookup"><span data-stu-id="33ee6-107">In this topic</span></span>


<span data-ttu-id="33ee6-108">本主題包含下列關於使用 Windows PowerShell 來設定 MBAM 的資訊：</span><span class="sxs-lookup"><span data-stu-id="33ee6-108">This topic includes the following information about using Windows PowerShell to configure MBAM:</span></span>

-   [<span data-ttu-id="33ee6-109">如何載入 MBAM 2.5 的 Windows PowerShell 說明</span><span class="sxs-lookup"><span data-stu-id="33ee6-109">How to load Windows PowerShell Help for MBAM 2.5</span></span>](#bkmk-load-posh-help)

-   [<span data-ttu-id="33ee6-110">如何取得有關 MBAM Windows PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="33ee6-110">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>](#bkmk-help-specific-cmdlet)

-   [<span data-ttu-id="33ee6-111">您只能在 Windows PowerShell 中執行的設定，而不能使用 MBAM Server 設定精靈進行</span><span class="sxs-lookup"><span data-stu-id="33ee6-111">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>](#bkmk-config-only-posh)

-   [<span data-ttu-id="33ee6-112">使用 Windows PowerShell 設定 MBAM Server 功能的先決條件及需求</span><span class="sxs-lookup"><span data-stu-id="33ee6-112">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>](#bkmk-prereqs-posh-mbamsvr)

-   [<span data-ttu-id="33ee6-113">使用 Windows PowerShell 來設定遠端電腦上的 MBAM</span><span class="sxs-lookup"><span data-stu-id="33ee6-113">Using Windows PowerShell to configure MBAM on a remote computer</span></span>](#bkmk-remote-config)

-   [<span data-ttu-id="33ee6-114">必要的帳戶和對應的 Windows PowerShell Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="33ee6-114">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>](#bkmk-reqd-posh-accts)

<span data-ttu-id="33ee6-115">如需可用於管理 MBAM 之**MbamBitLockerRecoveryKey**和**MbamTPMOwnerPassword** Windows powershell Cmdlet 的詳細資訊，請參閱[使用 Windows PowerShell 管理 MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee6-115">For information about the **Get-MbamBitLockerRecoveryKey** and **Get-MbamTPMOwnerPassword** Windows PowerShell cmdlets, which are used to administer MBAM, see [Using Windows PowerShell to Administer MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md).</span></span>

## <a href="" id="bkmk-load-posh-help"></a><span data-ttu-id="33ee6-116">如何載入 MBAM 2.5 的 Windows PowerShell 說明</span><span class="sxs-lookup"><span data-stu-id="33ee6-116">How to load Windows PowerShell Help for MBAM 2.5</span></span>


<span data-ttu-id="33ee6-117">如需 TechNet 上的 Windows PowerShell Cmdlet 清單，請參閱適用[于 Windows powershell 的 Microsoft 桌面優化套件自動化](https://go.microsoft.com/fwlink/?LinkId=392816)。</span><span class="sxs-lookup"><span data-stu-id="33ee6-117">For a list of the Windows PowerShell cmdlets on TechNet, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=392816).</span></span>

**<span data-ttu-id="33ee6-118">若要在安裝 MBAM 伺服器軟體後載入 Windows PowerShell Cmdlet 的 MBAM 2.5 說明</span><span class="sxs-lookup"><span data-stu-id="33ee6-118">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="33ee6-119">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="33ee6-119">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="33ee6-120">類型**更新-說明-MODULE MBAM**。</span><span class="sxs-lookup"><span data-stu-id="33ee6-120">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

## <a href="" id="bkmk-help-specific-cmdlet"></a><span data-ttu-id="33ee6-121">如何取得有關 MBAM Windows PowerShell Cmdlet 的說明</span><span class="sxs-lookup"><span data-stu-id="33ee6-121">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>


<span data-ttu-id="33ee6-122">MBAM 的 Windows PowerShell 說明提供下列格式：</span><span class="sxs-lookup"><span data-stu-id="33ee6-122">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33ee6-123">Windows PowerShell 說明格式</span><span class="sxs-lookup"><span data-stu-id="33ee6-123">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="33ee6-124">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="33ee6-124">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-125">在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="33ee6-125">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-126">若要上傳最新的 Windows PowerShell Cmdlet，請按照上一節中如何載入 MBAM 的 Windows PowerShell 說明一節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="33ee6-126">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-127">在 TechNet 上做為網頁</span><span class="sxs-lookup"><span data-stu-id="33ee6-127">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-128">以單字 .docx 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="33ee6-128">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-129">以 .pdf 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="33ee6-129">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a><span data-ttu-id="33ee6-130">您只能在 Windows PowerShell 中執行的設定，而不能使用 MBAM Server 設定精靈進行</span><span class="sxs-lookup"><span data-stu-id="33ee6-130">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33ee6-131">只能使用 Windows PowerShell 執行的設定</span><span class="sxs-lookup"><span data-stu-id="33ee6-131">Configurations that you can do only by using Windows PowerShell</span></span></th>
<th align="left"><span data-ttu-id="33ee6-132">詳細資料</span><span class="sxs-lookup"><span data-stu-id="33ee6-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-133">從 web 應用程式在不同的電腦上安裝 web 服務。</span><span class="sxs-lookup"><span data-stu-id="33ee6-133">Install the web services on a separate computer from the web applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-134">您必須在同一部電腦上安裝 web 服務和 web 應用程式，才能使用此嚮導。</span><span class="sxs-lookup"><span data-stu-id="33ee6-134">Using the wizard, you must install the web services and web applications on the same computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-135">在個別的報表服務點啟用報表，而不安裝所有 Configuration Manager 物件。</span><span class="sxs-lookup"><span data-stu-id="33ee6-135">Enable reports on a separate reporting services point without installing all of the Configuration Manager objects.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-136">從 Configuration Manager 刪除所有物件。</span><span class="sxs-lookup"><span data-stu-id="33ee6-136">Delete all of the objects from Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-137">刪除物件時，會從 Configuration Manager 刪除所有合規性資料。</span><span class="sxs-lookup"><span data-stu-id="33ee6-137">Deleting the objects in turn deletes all of the compliance data from Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-138">為資料庫輸入自訂的連線字串。</span><span class="sxs-lookup"><span data-stu-id="33ee6-138">Enter a custom connection string for the databases.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-139">範例：若要將 web 應用程式設定為搭配鏡像使用，您必須使用 <strong> Enable-MbamWebApplication </strong> Cmdlet，在連線字串中指定適當的容錯移轉合作夥伴語法。</span><span class="sxs-lookup"><span data-stu-id="33ee6-139">Example: To configure the web applications to work with mirroring, you must use the <strong>Enable-MbamWebApplication</strong> cmdlet to specify the appropriate failover partner syntax in the connection string.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-140">[略過驗證] 和 [設定功能]，即使必備項檢查失敗也一樣。</span><span class="sxs-lookup"><span data-stu-id="33ee6-140">Skip validation and configure a feature even though the prerequisite check failed.</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="33ee6-141">**記事** 您無法使用 Windows PowerShell Cmdlet 或 MBAM 伺服器設定向導停用 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="33ee6-141">**Note** You cannot disable the MBAM databases with a Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="33ee6-142">若要防止意外移除您的合規性和審核資料，資料庫管理員必須手動移除資料庫。</span><span class="sxs-lookup"><span data-stu-id="33ee6-142">To prevent the accidental removal of your compliance and audit data, database administrators must remove databases manually.</span></span>

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a><span data-ttu-id="33ee6-143">使用 Windows PowerShell 設定 MBAM Server 功能的先決條件及需求</span><span class="sxs-lookup"><span data-stu-id="33ee6-143">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>


<span data-ttu-id="33ee6-144">開始設定之前，請先完成下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="33ee6-144">Before starting the configuration, complete the following prerequisites.</span></span>

**<span data-ttu-id="33ee6-145">與客戶相關的先決條件</span><span class="sxs-lookup"><span data-stu-id="33ee6-145">Account-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33ee6-146">必備</span><span class="sxs-lookup"><span data-stu-id="33ee6-146">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="33ee6-147">詳細資料或其他資訊</span><span class="sxs-lookup"><span data-stu-id="33ee6-147">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-148">建立必要的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-148">Create the required accounts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-149">請參閱 <strong> 本主題稍後的所需帳戶和對應的 Windows PowerShell Cmdlet 參數一節 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="33ee6-149">See section <strong>Required accounts and corresponding Windows PowerShell cmdlet parameters</strong> later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-150">您傳遞為 Windows PowerShell Cmdlet 之參數的使用者帳戶和群組，在網域中必須是有效的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-150">User accounts and groups that you pass as parameters to the Windows PowerShell cmdlets must be valid accounts in the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-151">您無法使用本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-151">You cannot use local accounts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-152">指定底層格式的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-152">Specify accounts in the down-level format.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-153">範例：</span><span class="sxs-lookup"><span data-stu-id="33ee6-153">Examples:</span></span></p>
<p><span data-ttu-id="33ee6-154">domainNetBiosName\userdomainNetBiosName\group</span><span class="sxs-lookup"><span data-stu-id="33ee6-154">domainNetBiosName\userdomainNetBiosName\group</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="33ee6-155">許可權相關的先決條件</span><span class="sxs-lookup"><span data-stu-id="33ee6-155">Permission-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33ee6-156">必備</span><span class="sxs-lookup"><span data-stu-id="33ee6-156">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="33ee6-157">詳細資料或其他資訊</span><span class="sxs-lookup"><span data-stu-id="33ee6-157">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-158">您必須是本機電腦的系統管理員，才能設定 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="33ee6-158">You must be an administrator on the local computer where you are configuring the MBAM feature.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-159">使用提升許可權的 Windows PowerShell 命令提示字元來執行所有的 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33ee6-159">Use an elevated Windows PowerShell command prompt to run all Windows PowerShell cmdlets.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-160">僅適用于 <strong> Enable-MbamDatabase </strong> Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="33ee6-160">For the <strong>Enable-MbamDatabase</strong> cmdlet only:</span></span></p>
<p><span data-ttu-id="33ee6-161">您必須 &quot; &quot; 在目標 Microsoft SQL Server 資料庫的實例上擁有 [建立任何資料庫] 許可權。</span><span class="sxs-lookup"><span data-stu-id="33ee6-161">You must have &quot;create any database&quot; permissions on the instance of the target Microsoft SQL Server database.</span></span></p>
<p><span data-ttu-id="33ee6-162">這個使用者帳戶必須是本機管理員群組的一部分，或 [備份操作員] 群組，才能註冊 MBAM Volume Shadow 複製服務（VSS）寫入程式。</span><span class="sxs-lookup"><span data-stu-id="33ee6-162">This user account must be a part of the local administrators group or the Backup Operators group to register the MBAM Volume Shadow Copy Service (VSS) Writer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="33ee6-163">根據預設，資料庫系統管理員或系統管理員必須 &quot; 建立任何資料庫 &quot; 許可權。</span><span class="sxs-lookup"><span data-stu-id="33ee6-163">By default, the database administrator or system administrator has the required &quot;create any database&quot; permissions.</span></span></p>
<p></p>
<p><span data-ttu-id="33ee6-164">如需 VSS 寫入程式的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> Volume Shadow 複製服務 </a> 。</span><span class="sxs-lookup"><span data-stu-id="33ee6-164">For more information about VSS Writer, see <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)">Volume Shadow Copy Service</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-165"><strong>僅限 System Center Configuration Manager 整合 </strong> 功能：</span><span class="sxs-lookup"><span data-stu-id="33ee6-165">For the <strong>System Center Configuration Manager Integration</strong> feature only:</span></span></p>
<p><span data-ttu-id="33ee6-166">啟用此功能的使用者必須在 Configuration Manager 中擁有下列許可權：</span><span class="sxs-lookup"><span data-stu-id="33ee6-166">The user who enables this feature must have these rights in Configuration Manager:</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="33ee6-167">Configuration Manager 中的許可權類型</span><span class="sxs-lookup"><span data-stu-id="33ee6-167">Type of rights in Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="33ee6-168">所需的許可權</span><span class="sxs-lookup"><span data-stu-id="33ee6-168">Required rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-169">Configuration Manager 網站許可權：</span><span class="sxs-lookup"><span data-stu-id="33ee6-169">Configuration Manager Site rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="33ee6-170">讀取</span><span class="sxs-lookup"><span data-stu-id="33ee6-170">Read</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="33ee6-171">Configuration Manager 集合許可權：</span><span class="sxs-lookup"><span data-stu-id="33ee6-171">Configuration Manager Collection rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="33ee6-172">建立-刪除-已讀-修改-部署設定項目</span><span class="sxs-lookup"><span data-stu-id="33ee6-172">Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="33ee6-173">Configuration Manager 設定項目許可權：</span><span class="sxs-lookup"><span data-stu-id="33ee6-173">Configuration Manager Configuration item rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="33ee6-174">建立-刪除-已讀取</span><span class="sxs-lookup"><span data-stu-id="33ee6-174">Create- Delete- Read</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a><span data-ttu-id="33ee6-175">使用 Windows PowerShell 來設定遠端電腦上的 MBAM</span><span class="sxs-lookup"><span data-stu-id="33ee6-175">Using Windows PowerShell to configure MBAM on a remote computer</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="33ee6-176">使用此功能的時機</span><span class="sxs-lookup"><span data-stu-id="33ee6-176">When to use this capability</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33ee6-177">當您想要設定遠端電腦上的 MBAM 2.5 伺服器功能時。</span><span class="sxs-lookup"><span data-stu-id="33ee6-177">When you want to configure the MBAM 2.5 Server features on a remote computer.</span></span> <span data-ttu-id="33ee6-178">Windows PowerShell Cmdlet 是在一部電腦上執行，您是在不同的遠端電腦上設定功能。</span><span class="sxs-lookup"><span data-stu-id="33ee6-178">The Windows PowerShell cmdlets are running on one computer, and you are configuring the features on a different, remote computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="33ee6-179">您必須執行的動作</span><span class="sxs-lookup"><span data-stu-id="33ee6-179">What you have to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33ee6-180">若要使用 Windows PowerShell 來設定遠端電腦上的 MBAM 2.5 伺服器功能，您必須：</span><span class="sxs-lookup"><span data-stu-id="33ee6-180">To use Windows PowerShell to configure MBAM 2.5 Server features on a remote computer, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="33ee6-181">確認已在遠端電腦上安裝 MBAM 2.5 Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="33ee6-181">Ensure that the MBAM 2.5 Server software has been installed on the remote computer.</span></span></p></li>
<li><p><span data-ttu-id="33ee6-182">使用認證安全支援提供者（CredSSP）通訊協定來開啟 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="33ee6-182">Use the Credential Security Support Provider (CredSSP) Protocol to open the Windows PowerShell session.</span></span></p></li>
<li><p><span data-ttu-id="33ee6-183">啟用 Windows 遠端系統管理（WinRM）。</span><span class="sxs-lookup"><span data-stu-id="33ee6-183">Enable Windows Remote Management (WinRM).</span></span> <span data-ttu-id="33ee6-184">如果您無法啟用 WinRM 並正確設定， <strong> </strong> 此表格中所述的新 PSSession Cmdlet 會顯示錯誤，並說明如何修正問題。</span><span class="sxs-lookup"><span data-stu-id="33ee6-184">If you fail to enable WinRM and to configure it correctly, the <strong>New-PSSession</strong> cmdlet that is described in this table displays an error and describes how to fix the issue.</span></span> <span data-ttu-id="33ee6-185">如需有關 WinRM 的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> 使用 Windows 遠端系統管理 </a> 。</span><span class="sxs-lookup"><span data-stu-id="33ee6-185">For more information about WinRM, see <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)">Using Windows Remote Management</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="33ee6-186">為什麼要這麼做</span><span class="sxs-lookup"><span data-stu-id="33ee6-186">Why you have to do it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33ee6-187">這個通訊協定可讓 Windows PowerShell Cmdlet 使用使用者的管理認證來連線至 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="33ee6-187">This protocol enables the Windows PowerShell cmdlets to connect to Active Directory Domain Services by using the user’s administrative credentials.</span></span> <span data-ttu-id="33ee6-188">如果您在沒有這個通訊協定的情況下啟動 Windows PowerShell 會話，您可能會收到驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="33ee6-188">You might get a validation error if you start the Windows PowerShell session without this protocol.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="33ee6-189">如何使用 CredSSP 通訊協定啟動 Windows PowerShell 會話</span><span class="sxs-lookup"><span data-stu-id="33ee6-189">How to start a Windows PowerShell session with the CredSSP protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="33ee6-190">在 Windows PowerShell 提示中輸入下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="33ee6-190">Type the following code at the Windows PowerShell prompt:</span></span></p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p><span data-ttu-id="33ee6-191">下列程式碼顯示一個範例。</span><span class="sxs-lookup"><span data-stu-id="33ee6-191">The following code shows an example.</span></span></p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a><span data-ttu-id="33ee6-192">必要的帳戶和對應的 Windows PowerShell Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="33ee6-192">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>


<span data-ttu-id="33ee6-193">下表說明設定 MBAM 2.5 伺服器功能所需的帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-193">The following table describes the accounts that are required to configure MBAM 2.5 Server features.</span></span> <span data-ttu-id="33ee6-194">它也會列出對應的 Windows PowerShell Cmdlet 和參數，您必須在設定期間指定該帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-194">It also lists the corresponding Windows PowerShell cmdlet and parameter for which you have to specify the account during configuration.</span></span>

<span data-ttu-id="33ee6-195">Cmdlet 參數類型（使用者或群組） Description Enable-MBAMDatabase</span><span class="sxs-lookup"><span data-stu-id="33ee6-195">Cmdlet Parameter Type (User or Group) Description Enable-MBAMDatabase</span></span>

<span data-ttu-id="33ee6-196">AccessAccount</span><span class="sxs-lookup"><span data-stu-id="33ee6-196">AccessAccount</span></span>

<span data-ttu-id="33ee6-197">使用者或群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-197">User or Group</span></span>

<span data-ttu-id="33ee6-198">指定擁有此資料庫讀/寫許可權的網域使用者或群組，以讓 web 應用程式存取此資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="33ee6-198">Specify a domain user or group that has read/write permission to this database to give the web applications access to data and reports in this database.</span></span> <span data-ttu-id="33ee6-199">如果該值是網域使用者，則執行**Enable MbamWebApplication** Cmdlet 時所使用的**WebServiceApplicationPoolCredential**參數必須使用相同的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-199">If the value is a domain user, then the **WebServiceApplicationPoolCredential** parameter that is used when running the **Enable-MbamWebApplication** cmdlet must use the same user account.</span></span> <span data-ttu-id="33ee6-200">如果該值是 [網域使用者] 群組，則**WebServiceApplicationPoolCredential**參數所使用的網域帳戶必須是此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="33ee6-200">If the value is a domain Users group, then the domain account that is used by the **WebServiceApplicationPoolCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="33ee6-201">ReportAccount</span><span class="sxs-lookup"><span data-stu-id="33ee6-201">ReportAccount</span></span>

<span data-ttu-id="33ee6-202">使用者或群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-202">User or Group</span></span>

<span data-ttu-id="33ee6-203">指定擁有此資料庫唯讀許可權的網域使用者或使用者群組，以提供 MBAM 報告對合規性和審核資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="33ee6-203">Specify a domain user or Users group that has read-only permission to this database to provide the MBAM reports access to the compliance and audit data.</span></span> <span data-ttu-id="33ee6-204">如果該值是網域使用者， **Enable-MbamReport** Cmdlet 的**ComplianceAndAuditDBCredential**參數必須使用相同的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-204">If the value is a domain user, then the **ComplianceAndAuditDBCredential** parameter of the **Enable-MbamReport** cmdlet must use the same user account.</span></span> <span data-ttu-id="33ee6-205">如果該值是 [網域使用者] 群組，則**ComplianceAndAuditDBCredential**參數所使用的網域帳戶必須是此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="33ee6-205">If the value is a domain Users group, then the domain account that is used by the **ComplianceAndAuditDBCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="33ee6-206">Enable-MbamReport</span><span class="sxs-lookup"><span data-stu-id="33ee6-206">Enable-MbamReport</span></span>

<span data-ttu-id="33ee6-207">ComplianceAndAuditDBCredential</span><span class="sxs-lookup"><span data-stu-id="33ee6-207">ComplianceAndAuditDBCredential</span></span>

<span data-ttu-id="33ee6-208">使用者</span><span class="sxs-lookup"><span data-stu-id="33ee6-208">User</span></span>

<span data-ttu-id="33ee6-209">指定本機 SSRS 實例用來連線到 MBAM 合規性和審核資料庫的管理認證。</span><span class="sxs-lookup"><span data-stu-id="33ee6-209">Specifies the administrative credential that the local SSRS instance uses to connect to the MBAM Compliance and Audit Database.</span></span> <span data-ttu-id="33ee6-210">系統管理認證中的網域使用者必須與執行**ReportAccount**參數時所使用的使用者帳戶相同，這會在執行**Enable-MbamDatabase** Cmdlet 時使用。</span><span class="sxs-lookup"><span data-stu-id="33ee6-210">The domain user in the administrative credential must be the same as the user account that is used for the **ReportAccount** parameter, which is used while running the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="33ee6-211">如果網域使用者群組是與**ReportAccount**參數搭配使用，這個帳戶應該是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="33ee6-211">If a domain Users group was used with the **ReportAccount** parameter, this account should be a member of that group.</span></span>

<span data-ttu-id="33ee6-212">**重要** 系統管理認證中指定的帳號應該擁有有限的使用者許可權，以提高安全性。</span><span class="sxs-lookup"><span data-stu-id="33ee6-212">**Important** The account specified in the administrative credentials should have limited user rights for improved security.</span></span> <span data-ttu-id="33ee6-213">此外，帳戶的密碼應該設定為 [未過期]。</span><span class="sxs-lookup"><span data-stu-id="33ee6-213">Also, the password of the account should be set to not expire.</span></span>

 

<span data-ttu-id="33ee6-214">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="33ee6-214">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="33ee6-215">群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-215">Group</span></span>

<span data-ttu-id="33ee6-216">指定擁有報告 [讀取] 許可權的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="33ee6-216">Specifies the domain user group that has read permissions to the reports.</span></span> <span data-ttu-id="33ee6-217">指定的群組必須是在**Enable-MbamWebApplication** Cmdlet 中用於**ReportsReadOnlyAccessGroup**參數的同一個群組。</span><span class="sxs-lookup"><span data-stu-id="33ee6-217">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamWebApplication** cmdlet.</span></span>

<span data-ttu-id="33ee6-218">Enable-MBAMWebApplication</span><span class="sxs-lookup"><span data-stu-id="33ee6-218">Enable-MBAMWebApplication</span></span>

<span data-ttu-id="33ee6-219">AdvancedHelpdeskAccessGroup</span><span class="sxs-lookup"><span data-stu-id="33ee6-219">AdvancedHelpdeskAccessGroup</span></span>

<span data-ttu-id="33ee6-220">群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-220">Group</span></span>

<span data-ttu-id="33ee6-221">指定 [網域使用者] 群組，該群組有權存取管理和監控網站的所有區域（[報告] 區域除外）。</span><span class="sxs-lookup"><span data-stu-id="33ee6-221">Specifies the domain Users group that has access to all areas of the Administration and Monitoring Website except the Reports area.</span></span>

<span data-ttu-id="33ee6-222">HelpdeskAccessGroup</span><span class="sxs-lookup"><span data-stu-id="33ee6-222">HelpdeskAccessGroup</span></span>

<span data-ttu-id="33ee6-223">群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-223">Group</span></span>

<span data-ttu-id="33ee6-224">指定可存取管理和監控網站之 [**管理 TPM** ] 和 [**磁片磁碟機**] 區域的 [網域使用者] 群組。</span><span class="sxs-lookup"><span data-stu-id="33ee6-224">Specifies the domain Users group that has access to the **Manage TPM** and **Drive Recovery** areas of the Administration and Monitoring Website.</span></span>

<span data-ttu-id="33ee6-225">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="33ee6-225">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="33ee6-226">群組</span><span class="sxs-lookup"><span data-stu-id="33ee6-226">Group</span></span>

<span data-ttu-id="33ee6-227">指定擁有 [管理] 和 [監視] 網站 [**報告**] 區域之 [讀取] 許可權的 [網域使用者] 群組。</span><span class="sxs-lookup"><span data-stu-id="33ee6-227">Specifies the domain Users group that has read permission to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="33ee6-228">指定的群組必須是在**Enable-MbamReport** Cmdlet 中用於**ReportsReadOnlyAccessGroup**參數的同一個群組。</span><span class="sxs-lookup"><span data-stu-id="33ee6-228">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamReport** cmdlet.</span></span>

<span data-ttu-id="33ee6-229">WebServiceApplicationPoolCredential</span><span class="sxs-lookup"><span data-stu-id="33ee6-229">WebServiceApplicationPoolCredential</span></span>

<span data-ttu-id="33ee6-230">使用者</span><span class="sxs-lookup"><span data-stu-id="33ee6-230">User</span></span>

<span data-ttu-id="33ee6-231">指定要供 MBAM web 應用程式的應用程式池使用的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="33ee6-231">Specifies the domain user to be used by the application pool for the MBAM web applications.</span></span> <span data-ttu-id="33ee6-232">它必須是在**Enable-MbamDatabase** Cmdlet 的**AccessAccount**參數中所指定的相同網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="33ee6-232">It must be the same domain user account that is specified in the **AccessAccount** parameter of the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="33ee6-233">如果**AccessAccount**參數是在執行**Enable MbamDatabase** Cmdlet 時使用網域使用者群組，則此處指定的網域使用者必須是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="33ee6-233">If a domain Users group was used by the **AccessAccount** parameter when running the **Enable-MbamDatabase** cmdlet, the domain user that is specified here must be a member of that group.</span></span> <span data-ttu-id="33ee6-234">如果您沒有指定管理認證，則會使用任何先前啟用的 web 應用程式所指定的管理認證。</span><span class="sxs-lookup"><span data-stu-id="33ee6-234">If you do not specify the administrative credentials, the administrative credentials that were specified by any previously enabled web application are used.</span></span> <span data-ttu-id="33ee6-235">所有的 web 應用程式都使用相同的應用程式池身分識別。</span><span class="sxs-lookup"><span data-stu-id="33ee6-235">All of the web applications use the same application pool identity.</span></span> <span data-ttu-id="33ee6-236">如果多次指定，則會使用最近指定的值。</span><span class="sxs-lookup"><span data-stu-id="33ee6-236">If it is specified multiple times, the most recently specified value is used.</span></span>

<span data-ttu-id="33ee6-237">**重要** 若要提高安全性，請將管理認證中指定的帳號設定為受限制的使用者權利。</span><span class="sxs-lookup"><span data-stu-id="33ee6-237">**Important** For improved security, set the account that is specified in the administrative credentials to limited user rights.</span></span> <span data-ttu-id="33ee6-238">此外，將帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="33ee6-238">Also, set the password of the account to never expire.</span></span> <span data-ttu-id="33ee6-239">請確定已將內建的 IIS \ _IUSRS 帳戶或用於**WebServiceApplicationPoolCredential**參數的帳戶新增至 [在驗證本機安全性**之後類比用戶端**] 設定。</span><span class="sxs-lookup"><span data-stu-id="33ee6-239">Ensure that either the built-in IIS\_IUSRS account or the account that is used for the **WebServiceApplicationPoolCredential** parameter has been added to the **Impersonate a client after authentication** local security setting.</span></span>

<span data-ttu-id="33ee6-240">若要查看 [本機安全性] 設定，請開啟 [**本機安全性原則編輯器**]，然後展開 [**本機原則**] 節點，選取 [**使用者權利指派**] 節點，然後按兩下 [在**驗證之後類比用戶端**]，然後在詳細資料窗格中以**批次工作**群組原則設定登入。</span><span class="sxs-lookup"><span data-stu-id="33ee6-240">To view the local security setting, open the **Local Security Policy editor**, expand the **Local Policies** node, select the **User Rights Assignment** node, and then double-click the **Impersonate a client after authentication** and **Log on as a batch job** Group Policy settings in the details pane.</span></span>

 

 




## <span data-ttu-id="33ee6-241">相關主題</span><span class="sxs-lookup"><span data-stu-id="33ee6-241">Related topics</span></span>


[<span data-ttu-id="33ee6-242">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="33ee6-242">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="33ee6-243">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="33ee6-243">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)

[<span data-ttu-id="33ee6-244">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="33ee6-244">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)

 
## <span data-ttu-id="33ee6-245">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="33ee6-245">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="33ee6-246">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="33ee6-246">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="33ee6-247">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="33ee6-247">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





