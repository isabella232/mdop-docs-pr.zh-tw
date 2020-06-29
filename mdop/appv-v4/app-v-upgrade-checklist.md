---
title: App-V 升級檢查清單
description: App-V 升級檢查清單
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802337"
---
# <span data-ttu-id="a2540-103">App-V 升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="a2540-103">App-V Upgrade Checklist</span></span>


<span data-ttu-id="a2540-104">嘗試升級至 Microsoft Application Virtualization （App-v）4.5 或更新版本之前，您必須先將 App-v 4.1 之前的任何版本升級至 App-v 4.1。</span><span class="sxs-lookup"><span data-stu-id="a2540-104">Before trying to upgrade to Microsoft Application Virtualization (App-V) 4.5 or later versions, any version earlier than App-V 4.1 must be upgraded to App-V 4.1.</span></span> <span data-ttu-id="a2540-105">您應該先規劃升級用戶端，然後再升級伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="a2540-105">You should plan to upgrade clients first, and then upgrade the server components.</span></span> <span data-ttu-id="a2540-106">已升級至 app-v 4.5 的 app V 用戶端會繼續搭配尚未升級的 App-v 伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="a2540-106">App-V clients that have been upgraded to App-V 4.5 continue to work with App-V servers that have not yet been upgraded.</span></span> <span data-ttu-id="a2540-107">已升級至 App-v 4.5 的伺服器不支援舊版用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2540-107">Earlier versions of the client are not supported on servers that have been upgraded to App-V 4.5.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2540-108">步驟</span><span class="sxs-lookup"><span data-stu-id="a2540-108">Step</span></span></th>
<th align="left"><span data-ttu-id="a2540-109">參考</span><span class="sxs-lookup"><span data-stu-id="a2540-109">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-110">升級 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2540-110">Upgrade the App-V clients.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)"><span data-ttu-id="a2540-111">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="a2540-111">How to Upgrade the Application Virtualization Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-112">升級 app-v 伺服器和資料庫。</span><span class="sxs-lookup"><span data-stu-id="a2540-112">Upgrade the App-V servers and database.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a2540-113">重要</span><span class="sxs-lookup"><span data-stu-id="a2540-113">Important</span></span></strong><br/><p><span data-ttu-id="a2540-114">如果您有多個伺服器共用存取 App V 資料庫，所有這些伺服器都必須在資料庫升級時離線。</span><span class="sxs-lookup"><span data-stu-id="a2540-114">If you have more than one server sharing access to the App-V database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="a2540-115">您應該遵循資料庫升級的一般業務做法，但我們建議您先使用資料庫的備份複本來測試資料庫升級。</span><span class="sxs-lookup"><span data-stu-id="a2540-115">You should follow your regular business practices for the database upgrade, but we recommend that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="a2540-116">接著，您應該選取其中一個伺服器進行第一次升級，這會升級資料庫架構。</span><span class="sxs-lookup"><span data-stu-id="a2540-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="a2540-117">成功升級生產資料庫之後，您就可以在其他伺服器上升級 App-v 軟體。</span><span class="sxs-lookup"><span data-stu-id="a2540-117">After the production database has been successfully upgraded, you can upgrade the App-V software on the other servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="a2540-118">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="a2540-118">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-119">升級 app-v Management Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a2540-119">Upgrade the App-V Management Web Service.</span></span></p>
<p><span data-ttu-id="a2540-120">此步驟僅適用于管理 Web 服務位於個別伺服器上，這會要求您在該個別伺服器上執行伺服器安裝程式，以升級管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a2540-120">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Management Web service.</span></span> <span data-ttu-id="a2540-121">否則，先前的伺服器升級步驟會自動升級管理 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a2540-121">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="a2540-122">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="a2540-122">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-123">升級 app-v 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="a2540-123">Upgrade the App-V Management Console.</span></span></p>
<p><span data-ttu-id="a2540-124">此步驟僅適用于管理主控台位於不同的電腦上，這會要求您在該個別電腦上執行伺服器安裝程式，以升級主機。</span><span class="sxs-lookup"><span data-stu-id="a2540-124">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="a2540-125">否則，先前的伺服器升級步驟將會升級管理主控台。</span><span class="sxs-lookup"><span data-stu-id="a2540-125">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)"><span data-ttu-id="a2540-126">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="a2540-126">How to Upgrade the Servers and System Components</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-127">升級 App-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="a2540-127">Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)"><span data-ttu-id="a2540-128">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="a2540-128">How to Upgrade the Application Virtualization Sequencer</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="a2540-129">其他升級考慮事項</span><span class="sxs-lookup"><span data-stu-id="a2540-129">Additional Upgrade Considerations</span></span>


-   <span data-ttu-id="a2540-130">在版本4.2 中排序的任何虛擬應用程式套件，都不需再次排序，就能與版本4.5 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="a2540-130">Any virtual application packages sequenced in version 4.2 will not have to be sequenced again for use with version 4.5.</span></span> <span data-ttu-id="a2540-131">不過，如果您想要套用預設的存取控制清單（Acl）或產生 Windows 安裝程式檔案，您應該考慮將虛擬套件升級為 Microsoft Application Virtualization 4.5 格式。</span><span class="sxs-lookup"><span data-stu-id="a2540-131">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization 4.5 format if you want to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="a2540-132">這是一個簡單的程式，只需要使用 App-v 4.5 排序器開啟並儲存現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="a2540-132">This is a simple process and requires only that the existing virtual application package be opened and saved with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="a2540-133">您可以使用應用程式 VSequencer 命令列介面自動化這種做法。</span><span class="sxs-lookup"><span data-stu-id="a2540-133">This can be automated by using the App-VSequencer command-line interface.</span></span> <span data-ttu-id="a2540-134">如需詳細資訊，請參閱[如何使用 App-v 排序器建立或升級虛擬應用程式](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)</span><span class="sxs-lookup"><span data-stu-id="a2540-134">For more information, see [How to Create or Upgrade Virtual Applications Using the App-V Sequencer](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)</span></span>

-   <span data-ttu-id="a2540-135">4.5 排序器的其中一個功能是，可以建立 Windows 安裝程式（.msi）檔案，做為虛擬應用程式套件與電子軟體發佈（ESD）系統（例如 Microsoft 端點設定管理員）的互通性的控點。</span><span class="sxs-lookup"><span data-stu-id="a2540-135">One of the features of the 4.5 Sequencer is the ability to create Windows Installer (.msi) files as control points for virtual application package interoperability with electronic software distribution (ESD) systems, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a2540-136">使用 MSI 工具所建立的舊版 Windows 安裝程式檔案，這些檔案會在隨後升級至 App-v 4.5 的 4.1 App-v 工具或4.2 用戶端上，繼續運作，不過這些檔案無法在 App-v 4.5 用戶端上安裝。</span><span class="sxs-lookup"><span data-stu-id="a2540-136">Previous Windows Installer files created with the MSI tool for Application Virtualization that were installed on a App-V 4.1 or 4.2 client that is subsequently upgraded to App-V 4.5 will continue to work, although they cannot be installed on the App-V 4.5 client.</span></span> <span data-ttu-id="a2540-137">不過，除非在 App-v 4.5 排序器中升級，否則無法移除或升級它們。</span><span class="sxs-lookup"><span data-stu-id="a2540-137">However, they cannot be removed or upgraded unless they are upgraded in the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="a2540-138">早于4.5 的原始 App-v 套件必須在 App-v 4.5 排序器中開啟，然後另存為 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="a2540-138">The original App-V package earlier than 4.5 has to be opened in the App-V 4.5 Sequencer and then saved as a Windows Installer File.</span></span>

    **<span data-ttu-id="a2540-139">注意</span><span class="sxs-lookup"><span data-stu-id="a2540-139">Note</span></span>**  
    <span data-ttu-id="a2540-140">如果 App-v 4.2 用戶端已升級至 App-v 4.5，則可以使用腳本來在版本4.5 用戶端上保留版本4.2 套件，並允許管理它們。</span><span class="sxs-lookup"><span data-stu-id="a2540-140">If the App-V 4.2 Client has already been upgraded to App-V 4.5, it is possible to script a workaround to preserve the version 4.2 packages on version 4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="a2540-141">此腳本必須將兩個檔案（msvcp71.dll 和 msvcr71.dll）複製到 App V 安裝資料夾，並在登錄機碼底下設定下列登錄機碼值： \ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]：</span><span class="sxs-lookup"><span data-stu-id="a2540-141">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key:\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

    <span data-ttu-id="a2540-142">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="a2540-142">"ClientVersion"="4.2.1.20"</span></span>

    <span data-ttu-id="a2540-143">"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" （全域可寫位置）</span><span class="sxs-lookup"><span data-stu-id="a2540-143">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>



-   <span data-ttu-id="a2540-144">在 app-v 4.6 用戶端上執行 app-v 4.5 Sequencer 所產生的 Windows Installer 檔案會顯示錯誤訊息：「此套件需要 Microsoft Application Virtualization 用戶端4.5 或更新版本」。</span><span class="sxs-lookup"><span data-stu-id="a2540-144">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when trying to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="a2540-145">使用 App-v 4.5 SP1 排序器或 App-v 4.6 排序器開啟舊版套件，並為套件產生新的 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2540-145">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi file for the package.</span></span>

-   <span data-ttu-id="a2540-146">已建立並儲存的任何版本4.2 報告，都會在伺服器升級至版本4.5 時覆寫。</span><span class="sxs-lookup"><span data-stu-id="a2540-146">Any version 4.2 reports that were created and saved will be overwritten when the server is upgraded to version 4.5.</span></span> <span data-ttu-id="a2540-147">如果您必須保留這些報告，您必須儲存位於伺服器的 SoftGrid 管理主控台資料夾中的 SftMMC 檔案備份複本，然後使用該複本來取代升級期間安裝的新 SftMMC。</span><span class="sxs-lookup"><span data-stu-id="a2540-147">If you have to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

-   <span data-ttu-id="a2540-148">如需從舊版升級的其他資訊，請參閱[升級至 Microsoft Application Virtualization 4.5 常見問題](https://go.microsoft.com/fwlink/?LinkId=120358)（ https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="a2540-148">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="a2540-149">App-v 4.6 用戶端套件支援</span><span class="sxs-lookup"><span data-stu-id="a2540-149">App-V 4.6 Client Package Support</span></span>


<span data-ttu-id="a2540-150">您可以將在舊版 App-v 中建立的套件部署到 App-v 4.6 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2540-150">You can deploy packages created in previous versions of App-V to App-V 4.6 clients.</span></span> <span data-ttu-id="a2540-151">不過，您必須修改相關的 .osd 檔案，讓它包含適當的作業系統和晶片架構資訊。</span><span class="sxs-lookup"><span data-stu-id="a2540-151">However, you must modify the associated .osd file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="a2540-152">下列值可以使用：</span><span class="sxs-lookup"><span data-stu-id="a2540-152">The following values can be used:</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a2540-153">OS 值</span><span class="sxs-lookup"><span data-stu-id="a2540-153">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-154">&lt;OS 值 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-154">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-155">&lt;OS 值 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-155">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-156">&lt;OS 值 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-156">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-157">&lt;OS 值 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-157">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-158">&lt;OS 值 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-158">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-159">&lt;OS 值 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-159">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-160">&lt;OS 值 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-160">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-161">&lt;OS 值 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-161">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-162">&lt;OS 值 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-162">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-163">&lt;OS 值 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-163">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-164">&lt;OS 值 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="a2540-164">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="a2540-165">若要執行新建立的32位套件，您必須在執行32位作業系統的電腦上，使用安裝 app-v 4.6 Sequencer 的電腦來排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="a2540-165">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V 4.6 Sequencer installed.</span></span> <span data-ttu-id="a2540-166">當您將應用程式排序之後，請在 Sequencer 主控台中，按一下 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。</span><span class="sxs-lookup"><span data-stu-id="a2540-166">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

**<span data-ttu-id="a2540-167">重要</span><span class="sxs-lookup"><span data-stu-id="a2540-167">Important</span></span>**  
<span data-ttu-id="a2540-168">在執行64位作業系統的電腦上，必須將已排序的應用程式部署到執行64位作業系統的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a2540-168">Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="a2540-169">使用 App-v 4.6 Sequencer 建立的新32位套件不會在執行 App-v 4.5 用戶端的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="a2540-169">New 32-bit packages created by using the App-V 4.6 Sequencer do not run on computers running the App-V 4.5 client.</span></span>



<span data-ttu-id="a2540-170">若要在 App-V 4.6 用戶端上執行新的64位套件，您必須在執行 App-v 4.6 排序器的電腦上，將應用程式排序，且執行的是64位作業系統。</span><span class="sxs-lookup"><span data-stu-id="a2540-170">To run new 64-bit packages on the App-V 4.6 Client, you must sequence the application on a computer running the App-V 4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="a2540-171">當您將應用程式排序之後，請在 Sequencer 主控台中，按一下 [**部署**] 索引標籤，然後根據需要指定適當的作業系統和晶片架構。</span><span class="sxs-lookup"><span data-stu-id="a2540-171">After you have sequenced the application, in the Sequencer console, click the **Deployment** tab, and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="a2540-172">下表列出哪些用戶端版本會使用各種不同版本的排序器來執行建立的套件。</span><span class="sxs-lookup"><span data-stu-id="a2540-172">The following table lists which client versions will run packages created by using the various versions of the sequencer.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="a2540-173">使用 App-v 4.2 Sequencer 排序</span><span class="sxs-lookup"><span data-stu-id="a2540-173">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="a2540-174">使用 App-v 4.5 Sequencer 排序</span><span class="sxs-lookup"><span data-stu-id="a2540-174">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="a2540-175">使用32位 App-v-V 4.6 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="a2540-175">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="a2540-176">使用64位 App-v-V 4.6 排序器進行排序</span><span class="sxs-lookup"><span data-stu-id="a2540-176">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-177">4.2 用戶端</span><span class="sxs-lookup"><span data-stu-id="a2540-177">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-178">是</span><span class="sxs-lookup"><span data-stu-id="a2540-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-179">否</span><span class="sxs-lookup"><span data-stu-id="a2540-179">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-180">否</span><span class="sxs-lookup"><span data-stu-id="a2540-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-181">否</span><span class="sxs-lookup"><span data-stu-id="a2540-181">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-182">4.5 用戶端¹</span><span class="sxs-lookup"><span data-stu-id="a2540-182">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-183">是</span><span class="sxs-lookup"><span data-stu-id="a2540-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-184">是</span><span class="sxs-lookup"><span data-stu-id="a2540-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-185">否</span><span class="sxs-lookup"><span data-stu-id="a2540-185">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-186">否</span><span class="sxs-lookup"><span data-stu-id="a2540-186">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a2540-187">4.6 用戶端（32位）</span><span class="sxs-lookup"><span data-stu-id="a2540-187">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-188">是</span><span class="sxs-lookup"><span data-stu-id="a2540-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-189">是</span><span class="sxs-lookup"><span data-stu-id="a2540-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-190">是</span><span class="sxs-lookup"><span data-stu-id="a2540-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-191">不可以</span><span class="sxs-lookup"><span data-stu-id="a2540-191">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a2540-192">4.6 用戶端（64位）</span><span class="sxs-lookup"><span data-stu-id="a2540-192">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-193">是</span><span class="sxs-lookup"><span data-stu-id="a2540-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-194">是</span><span class="sxs-lookup"><span data-stu-id="a2540-194">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-195">是</span><span class="sxs-lookup"><span data-stu-id="a2540-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="a2540-196">是</span><span class="sxs-lookup"><span data-stu-id="a2540-196">Yes</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="a2540-197">¹適用于 App-V 4.5 用戶端的所有版本，包括 App-v 4.5、App-v 4.5 CU1，以及 App-v 4.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="a2540-197">¹Applies to all versions of the App-V 4.5 client, including App-V 4.5, App-V 4.5 CU1, and App-V 4.5 SP1.</span></span>









