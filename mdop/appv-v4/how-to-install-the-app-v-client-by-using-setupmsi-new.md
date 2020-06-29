---
title: 如何使用 Setup.msi 安裝 App-V Client
description: 如何使用 Setup.msi 安裝 App-V Client
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801374"
---
# <span data-ttu-id="dcf2e-103">如何使用 Setup.msi 安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="dcf2e-103">How to Install the App-V Client by Using Setup.msi</span></span>


<span data-ttu-id="dcf2e-104">本主題描述如何使用 setup.msi 程式來安裝 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-104">This topic describes how to install the App-V client by using the setup.msi program.</span></span> <span data-ttu-id="dcf2e-105">在您使用 setup.msi 程式安裝 App-V 用戶端之前，您必須先判斷是否必須安裝任何必要的軟體，然後才能安裝它。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-105">Before you install the App-V client using the setup.msi program, you must first determine if any prerequisite software must be installed, and then you must install it.</span></span> <span data-ttu-id="dcf2e-106">若要安裝必備軟體，請參閱本主題的[安裝必備軟體](#prereq-sw)一節。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-106">To install the prerequisite software, see the [Installing Prerequisite Software](#prereq-sw) section of this topic.</span></span> <span data-ttu-id="dcf2e-107">若要安裝用戶端軟體，請參閱本主題的[使用 Setup.msi 程式區段來安裝 App-V 用戶端](#msi-setup)。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-107">To install the client software, see the [Installing the App-V Client Using the Setup.msi Program](#msi-setup) section of this topic.</span></span>

## <a href="" id="prereq-sw"></a><span data-ttu-id="dcf2e-108">安裝必備軟體</span><span class="sxs-lookup"><span data-stu-id="dcf2e-108">Installing Prerequisite Software</span></span>


<span data-ttu-id="dcf2e-109">您可以使用下列程式來安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-109">You can use the following procedures to install the prerequisite software.</span></span> <span data-ttu-id="dcf2e-110">您可以建立命令檔並從命令提示字元執行命令，或者您可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-110">You can create a command file and run the commands from the command prompt, or you can use a scripting language such as VBScript or Windows PowerShell to run the commands.</span></span>

<span data-ttu-id="dcf2e-111">**記事** 在應用程式 V 用戶端的 x86 和 x64 版本中，都需要下列軟體的 x86 版本。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-111">**Note** The x86 versions of the following software are required for both x86 and x64 versions of the App-V client.</span></span>

 

**<span data-ttu-id="dcf2e-112">若要安裝 Microsoft VisualC + + 2005SP1 可再發行套件（x86）</span><span class="sxs-lookup"><span data-stu-id="dcf2e-112">To install Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>**

1. <span data-ttu-id="dcf2e-113">從 Microsoft 下載中心下載[Microsoft Visual c + + 2005 SP1 可再發行套件（x86）](https://go.microsoft.com/fwlink/?LinkId=119961)軟體套件 <https://go.microsoft.com/fwlink/?LinkId=119961> 。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-113">Download the [Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961) software package from the Microsoft Download Center (<https://go.microsoft.com/fwlink/?LinkId=119961>).</span></span> <span data-ttu-id="dcf2e-114">\ [範本權杖值 \] 針對版本 4.5 SP2 及更新版本的 App-V 用戶端，從[Microsoft Visual c + + 2005 Service Pack 1 的可再發行套件](https://go.microsoft.com/fwlink/?LinkId=169360)（ https://go.microsoft.com/fwlink/?LinkId=169360).\ [Template Token 值 \]）下載 vcredist\_x86.exe</span><span class="sxs-lookup"><span data-stu-id="dcf2e-114">\[Template Token Value\] For version 4.5 SP2 and later of the App-V client, download vcredist\_x86.exe from [Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360) (https://go.microsoft.com/fwlink/?LinkId=169360).\[Template Token Value\]</span></span>

2. <span data-ttu-id="dcf2e-115">若要自行安裝，請在命令列選項 "/Q" 中使用 vcredist\_x86.exe，例如**vcredist\_x86.exe/q**。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-115">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

3. <span data-ttu-id="dcf2e-116">若要使用 vcredist\_x86.msi 檔案來安裝軟體，請使用命令列選項 "/C/T： &lt; fullpathtofolder &gt; " 將檔案 vcredist.msi，然後 vcredis1.cab 從 vcredist\_x86.exe 到暫存檔案夾。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-116">To install the software by using the vcredist\_x86.msi file, use the command-line option “/C /T:&lt;fullpathtofolder&gt;” to extract the files vcredist.msi and vcredis1.cab from vcredist\_x86.exe to a temporary folder.</span></span> <span data-ttu-id="dcf2e-117">若要自行安裝，請使用命令列選項/quiet，例如， **msiexec/i vcredist.msi** /quiet。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-117">To install silently, use the command-line option /quiet—for example, **msiexec /i vcredist.msi** /quiet.</span></span>

### <span data-ttu-id="dcf2e-118">若要安裝 Microsoft VisualC + + 2008SP1 可再發行套件（x86）</span><span class="sxs-lookup"><span data-stu-id="dcf2e-118">To install Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

<span data-ttu-id="dcf2e-119">**重要** 針對應用程式-V 用戶端的4.6 及更新版本，您也必須安裝 Microsoft Visual c + + 2008 Service Pack 1 可重新發佈的套件 ATL 安全性更新。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-119">**Important** For version4.6 and later of the App-V client, you must also install the Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update.</span></span>

 

****

1.  <span data-ttu-id="dcf2e-120">從 Microsoft 下載中心下載[Microsoft Visual c + + 2008 Service Pack 1 可再發行套件 [ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=150700)軟體套件] https://go.microsoft.com/fwlink/?LinkId=150700) 。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-120">Download the [Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=150700) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=150700).</span></span>

2.  <span data-ttu-id="dcf2e-121">若要自行安裝，請在命令列選項 "/Q" 中使用 vcredist\_x86.exe，例如**vcredist\_x86.exe/q**。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-121">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

### <span data-ttu-id="dcf2e-122">安裝 Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）</span><span class="sxs-lookup"><span data-stu-id="dcf2e-122">To install Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

****

1.  <span data-ttu-id="dcf2e-123">從 Microsoft 下載中心下載[Microsoft CORE XML Services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266)軟體套件（ https://go.microsoft.com/fwlink/?LinkId=63266) 。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-123">Download the [Microsoft Core XML Services (MSXML)6.0SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=63266).</span></span>

2.  <span data-ttu-id="dcf2e-124">若要自行安裝，請使用命令列選項/quiet，例如， **msiexec/i msxml6\_x86.msi/quiet**。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-124">To install silently, use the command-line option /quiet—for example, **msiexec /i msxml6\_x86.msi /quiet**.</span></span>

### <span data-ttu-id="dcf2e-125">若要安裝 Microsoft 應用程式錯誤報表</span><span class="sxs-lookup"><span data-stu-id="dcf2e-125">To install Microsoft Application Error Reporting</span></span>

<span data-ttu-id="dcf2e-126">安裝 Microsoft 應用程式錯誤報表時，您必須使用*APPGUID*參數來指定 app-v 產品代碼。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-126">When installing Microsoft Application Error Reporting, you must use the *APPGUID* parameter to specify the App-V product code.</span></span> <span data-ttu-id="dcf2e-127">產品代碼對於每個 App-v 用戶端類型和版本都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-127">The product code is unique for each App-V client type and version.</span></span> <span data-ttu-id="dcf2e-128">從下表中選取正確的產品代碼。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-128">Select the correct product code from the following table.</span></span>

<span data-ttu-id="dcf2e-129">**重要** 在 App-v 4.6 SP2 及更新版本中，您不再需要安裝 Microsoft 應用程式錯誤報表（dw20shared.msi）。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-129">**Important** For App-V4.6SP2 and later, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="dcf2e-130">App-v 現在使用 Microsoft 錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-130">App-V now uses Microsoft Error Reporting.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dcf2e-131">版本</span><span class="sxs-lookup"><span data-stu-id="dcf2e-131">Version</span></span></th>
<th align="left"><span data-ttu-id="dcf2e-132">桌面用戶端的產品代碼</span><span class="sxs-lookup"><span data-stu-id="dcf2e-132">Product Code for Desktop Client</span></span></th>
<th align="left"><span data-ttu-id="dcf2e-133">適用于遠端桌面服務之用戶端的產品代碼</span><span class="sxs-lookup"><span data-stu-id="dcf2e-133">Product Code for Client for Remote Desktop Services</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf2e-134">App-V 4.5 CU1</span><span class="sxs-lookup"><span data-stu-id="dcf2e-134">App-V 4.5 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span><span class="sxs-lookup"><span data-stu-id="dcf2e-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span><span class="sxs-lookup"><span data-stu-id="dcf2e-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf2e-137">App-V 4.5 SP1</span><span class="sxs-lookup"><span data-stu-id="dcf2e-137">App-V 4.5 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-138">93468B43-C19D-44F9-8BCC-114076DB0443</span><span class="sxs-lookup"><span data-stu-id="dcf2e-138">93468B43-C19D-44F9-8BCC-114076DB0443</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span><span class="sxs-lookup"><span data-stu-id="dcf2e-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf2e-140">App-v 4.5 SP2</span><span class="sxs-lookup"><span data-stu-id="dcf2e-140">App-V 4.5 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span><span class="sxs-lookup"><span data-stu-id="dcf2e-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span><span class="sxs-lookup"><span data-stu-id="dcf2e-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf2e-143">應用程式-V 4.6 x86</span><span class="sxs-lookup"><span data-stu-id="dcf2e-143">App-V 4.6 x86</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span><span class="sxs-lookup"><span data-stu-id="dcf2e-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-145">439FAC21-B423-41D4-8126-54F9FCB70039</span><span class="sxs-lookup"><span data-stu-id="dcf2e-145">439FAC21-B423-41D4-8126-54F9FCB70039</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf2e-146">App-V 4.6 x64</span><span class="sxs-lookup"><span data-stu-id="dcf2e-146">App-V 4.6 x64</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span><span class="sxs-lookup"><span data-stu-id="dcf2e-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span><span class="sxs-lookup"><span data-stu-id="dcf2e-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf2e-149">App-V 4.6 x86 ¹</span><span class="sxs-lookup"><span data-stu-id="dcf2e-149">App-V 4.6 x86 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span><span class="sxs-lookup"><span data-stu-id="dcf2e-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-151">9915D911-CC73-4122-AF4F-564F89454655</span><span class="sxs-lookup"><span data-stu-id="dcf2e-151">9915D911-CC73-4122-AF4F-564F89454655</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf2e-152">App-V 4.6 x64 ¹</span><span class="sxs-lookup"><span data-stu-id="dcf2e-152">App-V 4.6 x64 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-153">1650E31F-23B8-40B5-A60A-C5934F557E3B</span><span class="sxs-lookup"><span data-stu-id="dcf2e-153">1650E31F-23B8-40B5-A60A-C5934F557E3B</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span><span class="sxs-lookup"><span data-stu-id="dcf2e-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf2e-155">App-V 4.6 x86 SP1</span><span class="sxs-lookup"><span data-stu-id="dcf2e-155">App-V 4.6 x86 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span><span class="sxs-lookup"><span data-stu-id="dcf2e-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-157">1354855A-2298-4C73-9022-EF0686C65991</span><span class="sxs-lookup"><span data-stu-id="dcf2e-157">1354855A-2298-4C73-9022-EF0686C65991</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf2e-158">App-V 4.6 x64 SP1</span><span class="sxs-lookup"><span data-stu-id="dcf2e-158">App-V 4.6 x64 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span><span class="sxs-lookup"><span data-stu-id="dcf2e-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf2e-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span><span class="sxs-lookup"><span data-stu-id="dcf2e-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="dcf2e-161">¹ App-V "語言" 版本。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-161">¹App-V “Languages” release.</span></span>

<span data-ttu-id="dcf2e-162">**記事** 如果您需要尋找產品代碼，您可以使用 Orca.exe 資料庫編輯器或類似的工具來檢查 Windows 安裝程式檔案，以找出*ProductCode*屬性的值。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-162">**Note** If you need to find the product code, you can use the Orca.exe database editor or a similar tool to examine Windows Installer files to find the value of the *ProductCode* property.</span></span> <span data-ttu-id="dcf2e-163">如需使用 Orca.exe 的詳細資訊，請參閱[Windows 安裝程式開發工具](https://go.microsoft.com/fwlink/?LinkId=150008)（ https://go.microsoft.com/fwlink/?LinkId=150008) 。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-163">For more information about using Orca.exe, see [Windows Installer Development Tools](https://go.microsoft.com/fwlink/?LinkId=150008) (https://go.microsoft.com/fwlink/?LinkId=150008).</span></span>

 

****

1.  <span data-ttu-id="dcf2e-164">找出 Microsoft 應用程式錯誤報表安裝程式，dw20shared.msi，可以在發行媒體的**Support\\Watson**資料夾中找到。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-164">Locate the Microsoft Application Error Reporting install program, dw20shared.msi, which can be found in the **Support\\Watson** folder on the release media.</span></span>

2.  <span data-ttu-id="dcf2e-165">若要安裝軟體，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dcf2e-165">To install the software, run the following command:</span></span>

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a><span data-ttu-id="dcf2e-166">使用 Setup.msi 程式安裝 App V 用戶端</span><span class="sxs-lookup"><span data-stu-id="dcf2e-166">Installing the App-V Client by Using the Setup.msi Program</span></span>


<span data-ttu-id="dcf2e-167">使用下列程式來安裝 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-167">Use the following procedure to install the App-V client.</span></span> <span data-ttu-id="dcf2e-168">確認已安裝任何必要的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-168">Ensure that any necessary prerequisite software has been installed.</span></span> <span data-ttu-id="dcf2e-169">\ [Template 標記值 \] 在應用程式 V 用戶端的版本4.6 及更新版本中，setup.msi 程式會檢查系統，如果未安裝必備軟體，則會產生錯誤訊息，指出安裝無法繼續執行。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-169">\[Template Token Value\] For version4.6 and later of the App-V client, the setup.msi program checks the system and if prerequisite software is not installed, it generates an error message indicating that installation cannot continue.</span></span> <span data-ttu-id="dcf2e-170">\ [範本標記值 \]</span><span class="sxs-lookup"><span data-stu-id="dcf2e-170">\[Template Token Value\]</span></span>

**<span data-ttu-id="dcf2e-171">使用 Setup.msi 安裝應用程式虛擬化用戶端</span><span class="sxs-lookup"><span data-stu-id="dcf2e-171">To install the Application Virtualization Client by Using Setup.msi</span></span>**

1.  <span data-ttu-id="dcf2e-172">確認您是以在電腦上擁有系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-172">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="dcf2e-173">使用較高的權限開啟命令提示字元視窗，然後將目錄變更為內含安裝程式檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-173">Open a Command Prompt window by using elevated rights, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="dcf2e-174">在安裝版本4.6 或更新版本的 App-v 用戶端時，您必須針對電腦的作業系統、32位或64位使用正確的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-174">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="dcf2e-175">如果您使用的是錯誤的安裝程式，安裝將會失敗，並會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-175">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="dcf2e-176">在命令提示字元中輸入安裝命令字串。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-176">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="dcf2e-177">或者，您可以建立命令檔，然後從命令提示字元執行它。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-177">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="dcf2e-178">您也可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-178">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="dcf2e-179">下列命令列範例會說明如何將 setup.msi 用於許多選用的參數。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-179">The following command-line example shows how setup.msi can be used with a number of optional parameters.</span></span> <span data-ttu-id="dcf2e-180">如需這些參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-180">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="dcf2e-181">msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "生產系統" SWIPUBSVRTYPE = ""/secure "SWIPUBSVRHOST =" PRODSYS "SWIPUBSVRPORT =" 443 "SWIPUBSVRPATH ="/AppVirt/appsntype.xml "SWIPUBSVRREFRESH =" @ "SWIGLOBALDATA ^ D:\\AppVirt\\Global Virtualization 用戶端" SWIUSERDATA = "S"</span><span class="sxs-lookup"><span data-stu-id="dcf2e-181">msiexec.exe /i "setup.msi" SWICACHESIZE="10240" SWIPUBSVRDISPLAY="Production System" SWIPUBSVRTYPE="HTTP /secure" SWIPUBSVRHOST="PRODSYS" SWIPUBSVRPORT="443" SWIPUBSVRPATH="/AppVirt/appsntype.xml" SWIPUBSVRREFRESH="on" SWIGLOBALDATA="D:\\AppVirt\\Global" SWIUSERDATA="^% LOCALAPPDATA^%\\Windows\\Application Virtualization Client" SWIFSDRIVE="S" /q</span></span>**

    **<span data-ttu-id="dcf2e-182">重要</span><span class="sxs-lookup"><span data-stu-id="dcf2e-182">Important</span></span>**  
    -   <span data-ttu-id="dcf2e-183">Windows Installer 開關 "**/q**" 是用來將它設為無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-183">The Windows Installer switch "**/q**" is used to make this a silent installation.</span></span>

    -   <span data-ttu-id="dcf2e-184">" **%** **% HomeDrive%**" 中的 "" 字元前面必須是 " **^** " 逸出字元。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-184">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="dcf2e-185">否則，Windows 命令 shell 會將值設定為執行安裝的使用者。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-185">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="dcf2e-186">若要開啟安裝記錄，請使用 msiexec 開關 **/l\ \* v filename. 記錄**。</span><span class="sxs-lookup"><span data-stu-id="dcf2e-186">To turn on installation logging, use the msiexec switch **/l\*v filename.log**.</span></span>

     

## <span data-ttu-id="dcf2e-187">相關主題</span><span class="sxs-lookup"><span data-stu-id="dcf2e-187">Related topics</span></span>


[<span data-ttu-id="dcf2e-188">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="dcf2e-188">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





