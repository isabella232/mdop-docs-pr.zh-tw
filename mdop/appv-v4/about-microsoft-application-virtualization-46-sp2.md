---
title: 關於 Microsoft Application Virtualization 4.6 SP2
description: 關於 Microsoft Application Virtualization 4.6 SP2
author: dansimp
ms.assetid: 1429e314-9c38-472b-8687-3bed6cf0015c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 16303380782a086cfd750c7a8b2f99bf4f4c8b5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802449"
---
# <span data-ttu-id="ad2fb-103">關於 Microsoft Application Virtualization 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="ad2fb-103">About Microsoft Application Virtualization 4.6 SP2</span></span>


<span data-ttu-id="ad2fb-104">Microsoft Application Virtualization （App-v） 4.6 SP2 提供幾項增強功能及新功能，如本主題所述。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-104">Microsoft Application Virtualization (App-V)4.6 SP2 provides several enhancements and new features, which are described in this topic.</span></span>

<span data-ttu-id="ad2fb-105">**小心** 本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-105">**Caution** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="ad2fb-106">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-106">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="ad2fb-107">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-107">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="ad2fb-108">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-108">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="ad2fb-109">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-109">Change the registry at your own risk.</span></span>

 

**<span data-ttu-id="ad2fb-110">Windows 8 和 Windows Server 2012 的支援</span><span class="sxs-lookup"><span data-stu-id="ad2fb-110">Support for Windows 8 and Windows Server 2012</span></span>**

<span data-ttu-id="ad2fb-111">App-V 4.6 SP2 新增 Windows 8 和 Windows Server 2012 遠端桌面服務的支援。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-111">App-V4.6SP2 adds support for Windows 8 and Windows Server 2012 Remote Desktop Services.</span></span>

**<span data-ttu-id="ad2fb-112">支援 App-V 5.0 用戶端的共存</span><span class="sxs-lookup"><span data-stu-id="ad2fb-112">Support for coexistence with App-V 5.0 client</span></span>**

<span data-ttu-id="ad2fb-113">App-V 4.6 SP2 提供與 Microsoft Application Virtualization 5.0 用戶端共存的支援。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-113">App-V4.6SP2 provides support for coexistence with the Microsoft Application Virtualization 5.0 client.</span></span> <span data-ttu-id="ad2fb-114">請參閱 App-v 5.0 檔，以取得如何設定 App-v 5.0 用戶端與 App-v 4.6 SP2 用戶端共存的相關指示。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-114">Review the App-V 5.0 documentation for instructions on how to configure the App-V 5.0 client for coexistence with the App-V4.6SP2 client.</span></span> <span data-ttu-id="ad2fb-115">如需 App-V 5.0 的詳細資訊，請參閱 TechNet 上的[應用程式虛擬化 5](https://go.microsoft.com/fwlink/?LinkId=267599) 。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-115">For more information about App-V 5.0, see [Application Virtualization 5](https://go.microsoft.com/fwlink/?LinkId=267599) on TechNet.</span></span>

**<span data-ttu-id="ad2fb-116">能夠虛擬化 Adobe Reader X 與受保護的模式</span><span class="sxs-lookup"><span data-stu-id="ad2fb-116">Ability to virtualize Adobe Reader X with Protected Mode</span></span>**

<span data-ttu-id="ad2fb-117">您可以使用下列程式，將 Adobe Reader X 虛擬化，並開啟其受保護的模式功能。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-117">You can virtualize Adobe Reader X with its Protected Mode feature turned on by using the following procedures.</span></span> <span data-ttu-id="ad2fb-118">先前您必須停用受保護的模式，才能虛擬化 Adobe Reader X。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-118">Previously you had to disable Protected Mode in order to virtualize Adobe Reader X.</span></span>

<span data-ttu-id="ad2fb-119">啟動 App-v 排序器之前，請先在 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides 中建立下列登錄值：</span><span class="sxs-lookup"><span data-stu-id="ad2fb-119">Before launching the App-V Sequencer, create the following registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE \\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ad2fb-120">名稱</span><span class="sxs-lookup"><span data-stu-id="ad2fb-120">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-121">類型</span><span class="sxs-lookup"><span data-stu-id="ad2fb-121">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-122">資料</span><span class="sxs-lookup"><span data-stu-id="ad2fb-122">Data</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-123">描述</span><span class="sxs-lookup"><span data-stu-id="ad2fb-123">Description</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ad2fb-124">EnableVFSPassthrough</span><span class="sxs-lookup"><span data-stu-id="ad2fb-124">EnableVFSPassthrough</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-125">DWORD</span><span class="sxs-lookup"><span data-stu-id="ad2fb-125">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-126">sr-1</span><span class="sxs-lookup"><span data-stu-id="ad2fb-126">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ad2fb-127">將此值設定為 <strong> 1， </strong> 即可在啟動階段中，以 [受保護模式] 啟動 Adobe Reader X。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-127">Set this value to <strong>1</strong> in order to start Adobe Reader X in Protected Mode during the launch phase.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ad2fb-128">**記事** 在執行64位作業系統的電腦上，在 [HKEY \] 下建立登錄值 _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-128">**Note** On a computer running a 64-bit operating system, create the registry value under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides.</span></span>

 

<span data-ttu-id="ad2fb-129">針對您 Adobe Reader X 套件中的每個 OSD 檔案，請在 [原則] 元素底下新增下列專案 &lt; &gt; ：</span><span class="sxs-lookup"><span data-stu-id="ad2fb-129">For each OSD-file in your Adobe Reader X package, add the following items under the &lt;POLICIES&gt; element:</span></span>

`<VIRTUAL_FILE_SYSTEM_PASS_THROUGH>TRUE</VIRTUAL_FILE_SYSTEM_PASS_THROUGH>`

`<VIRTUAL_REGISTRY_PASS_THROUGH>TRUE</VIRTUAL_REGISTRY_PASS_THROUGH>`

`<ENFORCE_ACLS_ON_VREG_MODIFY>TRUE</ENFORCE_ACLS_ON_VREG_MODIFY>`

**<span data-ttu-id="ad2fb-130">新的 Sequencer 命令列參數</span><span class="sxs-lookup"><span data-stu-id="ad2fb-130">New Sequencer command-line parameter</span></span>**

<span data-ttu-id="ad2fb-131">當您透過排序器 GUI 建立套件加速器（PA）時，您可以選取 RTF 或 TXT 檔案，為將套用套件加速器的管理員提供封裝與部署指導方針。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-131">When you create a Package Accelerator (PA) through the Sequencer GUI, you can select an RTF or TXT file that provides packaging and deployment guidance to the administrators who will apply the Package Accelerator.</span></span> <span data-ttu-id="ad2fb-132">此功能現在可使用排序器 CLI 使用。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-132">This functionality is now available using the Sequencer CLI.</span></span>

`/ACCELERATORDESCRIPTIONFILE:PathToDescriptionFile`

<span data-ttu-id="ad2fb-133">指定 RTF 或 TXT 檔案的路徑，以便在建立套件加速器時提供封裝與部署指導方針。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-133">Specify a path to an RTF or TXT file that provides packaging and deployment guidance when creating a Package Accelerator.</span></span>

**<span data-ttu-id="ad2fb-134">不再需要安裝 Microsoft 應用程式錯誤報表</span><span class="sxs-lookup"><span data-stu-id="ad2fb-134">Microsoft Application Error Reporting no longer needs to be installed</span></span>**

<span data-ttu-id="ad2fb-135">當您使用 setup.msi 安裝 App V 4.6 SP2 用戶端時，您不再需要安裝 Microsoft 應用程式錯誤報表（dw20shared.msi）。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-135">When you are installing the App-V4.6SP2 client by using setup.msi, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="ad2fb-136">App-v 4.6 SP2 現在使用 Microsoft 錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-136">App-V4.6SP2 now uses Microsoft Error Reporting.</span></span> <span data-ttu-id="ad2fb-137">如需詳細資訊，請參閱[如何使用 Setup.msi安裝 App-V 用戶端](https://go.microsoft.com/fwlink/?LinkId=267237)。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-137">For more information, see [How to Install the App-V Client by Using Setup.msi](https://go.microsoft.com/fwlink/?LinkId=267237).</span></span>

**<span data-ttu-id="ad2fb-138">客戶意見反應與修補程式匯總</span><span class="sxs-lookup"><span data-stu-id="ad2fb-138">Customer feedback and hotfix rollup</span></span>**

<span data-ttu-id="ad2fb-139">App-V 4.6 SP2 包括自 App-v 4.6 SP1 發行以來發現問題的修正程式匯總。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-139">App-V4.6SP2 includes a rollup of fixes to address issues found since the App-V 4.6 SP1 release.</span></span> <span data-ttu-id="ad2fb-140">App-V 4.6 SP2 包含最新的修正程式，包括 Microsoft Application Virtualization 4.6 SP1 修正程式6。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-140">App-V4.6SP2 contains the latest fixes up to and including Microsoft Application Virtualization 4.6 SP1 Hotfix 6.</span></span>

## <span data-ttu-id="ad2fb-141">本節內容</span><span class="sxs-lookup"><span data-stu-id="ad2fb-141">In This Section</span></span>


<a href="" id="app-v-4-6-sp2-release-notes"></a>[<span data-ttu-id="ad2fb-142">App-V 4.6 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ad2fb-142">App-V 4.6 SP2 Release Notes</span></span>](https://go.microsoft.com/fwlink/?LinkId=267600)  
<span data-ttu-id="ad2fb-143">提供 App-V 4.6 SP2 已知問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="ad2fb-143">Provides the most up-to-date information about known issues with App-V4.6SP2.</span></span>

 

 





