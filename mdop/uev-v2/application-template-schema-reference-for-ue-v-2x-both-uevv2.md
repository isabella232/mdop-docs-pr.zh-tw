---
title: UE-V 2. x 的應用程式範本架構參考
description: UE-V 2. x 的應用程式範本架構參考
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812338"
---
# <span data-ttu-id="0e963-103">UE-V 2. x 的應用程式範本架構參考</span><span class="sxs-lookup"><span data-stu-id="0e963-103">Application Template Schema Reference for UE-V 2.x</span></span>


<span data-ttu-id="0e963-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 設定位置範本來定義由 UE-V 捕獲並套用的桌面應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the desktop application settings and Windows settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="0e963-105">UE-V 包含一組預設的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-105">UE-V includes a set of default settings location templates.</span></span> <span data-ttu-id="0e963-106">您也可以使用 UE-V 發生器建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-106">You can also create custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="0e963-107">[高級使用者] 可自訂 [設定位置] 範本的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e963-107">An advanced user can customize the XML file for a settings location template.</span></span> <span data-ttu-id="0e963-108">本主題詳細說明 UE-V 2.1 （SP1）和2.0 設定位置範本的 XML 結構，並提供編輯這些檔案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0e963-108">This topic details the XML structure of the UE-V 2.1 (SP1) and 2.0 settings location templates and provides guidance for editing these files.</span></span>

## <span data-ttu-id="0e963-109">UE-V 2.1 和 2.1 SP1 應用程式範本架構參考</span><span class="sxs-lookup"><span data-stu-id="0e963-109">UE-V 2.1 and 2.1 SP1 Application Template Schema Reference</span></span>


<span data-ttu-id="0e963-110">本節詳細說明 UE-V 2.1 和 2.1 SP1 設定位置範本的 XML 結構，並提供編輯此檔案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0e963-110">This section details the XML structure of the UE-V 2.1 and 2.1 SP1 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="0e963-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="0e963-111">In This Section</span></span>

-   [<span data-ttu-id="0e963-112">XML 宣告與編碼屬性</span><span class="sxs-lookup"><span data-stu-id="0e963-112">XML Declaration and Encoding Attribute</span></span>](#xml21)

-   [<span data-ttu-id="0e963-113">命名空間與根項目</span><span class="sxs-lookup"><span data-stu-id="0e963-113">Namespace and Root Element</span></span>](#namespace21)

-   [<span data-ttu-id="0e963-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-114">Data types</span></span>](#data21)

-   [<span data-ttu-id="0e963-115">Name 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-115">Name Element</span></span>](#name21)

-   [<span data-ttu-id="0e963-116">識別碼元素</span><span class="sxs-lookup"><span data-stu-id="0e963-116">ID Element</span></span>](#id21)

-   [<span data-ttu-id="0e963-117">Version 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-117">Version Element</span></span>](#version21)

-   [<span data-ttu-id="0e963-118">Author 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-118">Author Element</span></span>](#author21)

-   [<span data-ttu-id="0e963-119">進程與程式元素</span><span class="sxs-lookup"><span data-stu-id="0e963-119">Processes and Process Element</span></span>](#processes21)

-   [<span data-ttu-id="0e963-120">Application 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-120">Application Element</span></span>](#application21)

-   [<span data-ttu-id="0e963-121">常見元素</span><span class="sxs-lookup"><span data-stu-id="0e963-121">Common Element</span></span>](#common21)

-   [<span data-ttu-id="0e963-122">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-122">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate21)

-   [<span data-ttu-id="0e963-123">附錄： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="0e963-123">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix21)

### <a href="" id="xml21"></a><span data-ttu-id="0e963-124">XML 宣告與編碼屬性</span><span class="sxs-lookup"><span data-stu-id="0e963-124">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="0e963-125">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-125">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-126">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-126">Type: String</span></span>**

<span data-ttu-id="0e963-127">XML 聲明必須指定 XML 版本1.0 屬性（ &lt; ？ XML 版本 = "1.0" &gt; ）。</span><span class="sxs-lookup"><span data-stu-id="0e963-127">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="0e963-128">由 UE-V 發生器建立的設定位置範本會儲存為 UTF-8 編碼，但不明確指定編碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-128">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="0e963-129">我們建議您在這個元素中包含 encoding = "UTF-8" 屬性來做為最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0e963-129">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="0e963-130">產品隨附的所有範本也會指定此標記（請參閱%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\Templates 中的檔以瞭解參考）。</span><span class="sxs-lookup"><span data-stu-id="0e963-130">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="0e963-131">例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-131">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a><span data-ttu-id="0e963-132">命名空間與根項目</span><span class="sxs-lookup"><span data-stu-id="0e963-132">Namespace and Root Element</span></span>

**<span data-ttu-id="0e963-133">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-133">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-134">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-134">Type: String</span></span>**

<span data-ttu-id="0e963-135">UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有應用程式的命名空間。</span><span class="sxs-lookup"><span data-stu-id="0e963-135">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="0e963-136">SettingsLocationTemplate 是根項目，且包含所有其他元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-136">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="0e963-137">使用此標記的所有範本中的參照 SettingsLocationTemplate：</span><span class="sxs-lookup"><span data-stu-id="0e963-137">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a><span data-ttu-id="0e963-138">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-138">Data types</span></span>

<span data-ttu-id="0e963-139">以下是 UE-V 應用程式範本架構的資料類型。</span><span class="sxs-lookup"><span data-stu-id="0e963-139">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="0e963-140">**GUID**GUID 描述標準的全域唯一識別碼正則運算式，形式為 "\\ {\ [a-fA-F0-9 \] {8} -\ [a-fa-F0-9 \]- {4} \] [a-FA-F0-9 \] {4} -\ [a-fa-F0-9 \] {4} -\ [a-fa-F0-9 \] {12} \}"。</span><span class="sxs-lookup"><span data-stu-id="0e963-140">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="0e963-141">這會在 Filesetting\\Root\\KnownFolder 元素中使用，以驗證已知資料夾的格式設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-141">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="0e963-142">**FilenameString**FilenameString 是指要監視之程式的檔案名。</span><span class="sxs-lookup"><span data-stu-id="0e963-142">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="0e963-143">它的值會受到 RegEx \ [^ \\ \\ \* \ \ | &lt; &gt;/： \] +，（也就是說，它們可能不包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號字元）。</span><span class="sxs-lookup"><span data-stu-id="0e963-143">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="0e963-144">**IDString**IDString 指的是應用程式元素、SettingsLocationTemplate 及常見元素的識別碼值（用來描述共用一般設定的應用程式套件）。</span><span class="sxs-lookup"><span data-stu-id="0e963-144">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="0e963-145">它受到與 FilenameString 相同的 RegEx （\ [^ \\ \\ \\？ \\ \* \\ | &lt; &gt;/:\]+).</span><span class="sxs-lookup"><span data-stu-id="0e963-145">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="0e963-146">**TemplateVersion**TemplateVersion 是一個整數值，用於描述設定位置範本的修訂。</span><span class="sxs-lookup"><span data-stu-id="0e963-146">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="0e963-147">其值的範圍可以是0到2147483647。</span><span class="sxs-lookup"><span data-stu-id="0e963-147">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="0e963-148">**空白**空白代表 null 值。</span><span class="sxs-lookup"><span data-stu-id="0e963-148">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="0e963-149">這會在 Process\\ShellProcess 中使用，表示沒有任何程式可供監視。</span><span class="sxs-lookup"><span data-stu-id="0e963-149">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="0e963-150">您不應該在任何應用程式範本中使用這個值。</span><span class="sxs-lookup"><span data-stu-id="0e963-150">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="0e963-151">**作者**[作者] 資料類型是一種複雜類型，可用於識別範本的作者。</span><span class="sxs-lookup"><span data-stu-id="0e963-151">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="0e963-152">它包含兩個子項目： [**名稱**] 和 [**電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-152">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="0e963-153">在 Author 資料類型中，Name 元素是必要的，而 Email 元素是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-153">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="0e963-154">此類型會在 SettingsLocationTemplate 元素下更詳細的說明。</span><span class="sxs-lookup"><span data-stu-id="0e963-154">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="0e963-155">**範圍**範圍定義由兩個子項目組成的整數類別： [**最小值**] 和 [**最大值**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-155">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="0e963-156">此資料類型是在 ProcessVersion 資料類型中實現。</span><span class="sxs-lookup"><span data-stu-id="0e963-156">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="0e963-157">如果已指定，則必須包含最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="0e963-157">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="0e963-158">**ProcessVersion**ProcessVersion 會定義含有四個子項目的類型：**主要**、**次要**、**組建**及**修補程式**。</span><span class="sxs-lookup"><span data-stu-id="0e963-158">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="0e963-159">此資料類型是由 Process 元素用來填入其 ProductVersion 和 FileVersion 值。</span><span class="sxs-lookup"><span data-stu-id="0e963-159">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="0e963-160">此類型的資料是範圍值。</span><span class="sxs-lookup"><span data-stu-id="0e963-160">The data for this type is a Range value.</span></span> <span data-ttu-id="0e963-161">主要子項目是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-161">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="0e963-162">**架構**結構列舉了兩個可能的值： **Win32**和**Win64**。</span><span class="sxs-lookup"><span data-stu-id="0e963-162">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="0e963-163">這些值是用來指定處理常式體系結構。</span><span class="sxs-lookup"><span data-stu-id="0e963-163">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="0e963-164">**處理**程式[流程] 資料類型是用來描述要由 UE-V 監視之進程的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-164">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="0e963-165">它包含六個子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="0e963-165">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="0e963-166">下表詳細說明每個元素各自的資料類型：</span><span class="sxs-lookup"><span data-stu-id="0e963-166">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e963-167">元素</span><span class="sxs-lookup"><span data-stu-id="0e963-167">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-168">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-168">Data Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-169">Mandatory</span><span class="sxs-lookup"><span data-stu-id="0e963-169">Mandatory</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-170">副檔名</span><span class="sxs-lookup"><span data-stu-id="0e963-170">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-171">FilenameString</span><span class="sxs-lookup"><span data-stu-id="0e963-171">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-172">True</span><span class="sxs-lookup"><span data-stu-id="0e963-172">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-173">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-173">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-174">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-174">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-175">False</span><span class="sxs-lookup"><span data-stu-id="0e963-175">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-176">ProductName</span><span class="sxs-lookup"><span data-stu-id="0e963-176">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-177">字串</span><span class="sxs-lookup"><span data-stu-id="0e963-177">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-178">False</span><span class="sxs-lookup"><span data-stu-id="0e963-178">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-179">FileDescription</span><span class="sxs-lookup"><span data-stu-id="0e963-179">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-180">字串</span><span class="sxs-lookup"><span data-stu-id="0e963-180">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-181">False</span><span class="sxs-lookup"><span data-stu-id="0e963-181">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-182">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-182">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-183">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-183">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-184">False</span><span class="sxs-lookup"><span data-stu-id="0e963-184">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-185">FileVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-185">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-186">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-186">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-187">False</span><span class="sxs-lookup"><span data-stu-id="0e963-187">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="0e963-188">**處理**程式[進程] 資料類型代表一或多個處理元素集合的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-188">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="0e963-189">進程式列類型支援兩個子項目： **Process**與**ShellProcess**。</span><span class="sxs-lookup"><span data-stu-id="0e963-189">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="0e963-190">Process 是 Process 類型的元素，且 ShellProcess 的資料類型為空白。</span><span class="sxs-lookup"><span data-stu-id="0e963-190">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="0e963-191">在順序中至少必須辨識一個專案。</span><span class="sxs-lookup"><span data-stu-id="0e963-191">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="0e963-192">**路徑**RegistrySetting 和 FileSetting 會使用 Path 來參照登錄和檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="0e963-192">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="0e963-193">這個元素支援兩個選用的屬性： **Recursive**與**DeleteIfNotFound**。</span><span class="sxs-lookup"><span data-stu-id="0e963-193">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="0e963-194">這兩個值都設定為 default = "False"。</span><span class="sxs-lookup"><span data-stu-id="0e963-194">Both values are set to default=”False”.</span></span>

<span data-ttu-id="0e963-195">Recursive：表示檔案設定中包含路徑和所有子資料夾，或是所有的子登錄機碼都包含在註冊設定中。</span><span class="sxs-lookup"><span data-stu-id="0e963-195">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="0e963-196">在這兩種情況下，目前層級的所有專案都會包含在捕獲的資料中。</span><span class="sxs-lookup"><span data-stu-id="0e963-196">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="0e963-197">針對 FileSettings 物件，指定資料夾中的所有檔案都包含在 UE-V 捕獲的資料中，但不包含資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e963-197">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="0e963-198">針對登錄路徑，會捕獲目前路徑中的所有值，但不會捕獲子登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-198">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="0e963-199">在這兩種情況下，請小心考慮避免捕獲大型資料集或大量專案。</span><span class="sxs-lookup"><span data-stu-id="0e963-199">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="0e963-200">DeleteIfNotFound 屬性會從使用者的設定儲存路徑資料中移除設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-200">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="0e963-201">在從套件中移除這些設定時，可能需要這麼做，將大量磁碟空間儲存在設定儲存路徑檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0e963-201">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="0e963-202">**FileMask**FileMask 僅指定由 Path 所定義之資料夾的特定檔案類型。</span><span class="sxs-lookup"><span data-stu-id="0e963-202">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="0e963-203">例如，Path 可能是， `C:\users\username\files` 且 FileMask `*.txt` 只能包含文字檔。</span><span class="sxs-lookup"><span data-stu-id="0e963-203">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="0e963-204">**RegistrySetting**RegistrySetting 代表登錄機碼和值的容器，以及 UE-V Agent 元件上相關聯的所需行為。</span><span class="sxs-lookup"><span data-stu-id="0e963-204">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="0e963-205">此類型中定義了四個子項目： **path**、 **Name**、 **Exclude**以及值**Path**和**Name**的順序。</span><span class="sxs-lookup"><span data-stu-id="0e963-205">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="0e963-206">**FileSetting**FileSetting 包含與檔案和檔案路徑相關聯的參數。</span><span class="sxs-lookup"><span data-stu-id="0e963-206">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="0e963-207">定義了四個子項目： **Root**、 **Path**、 **FileMask**及**Exclude**。</span><span class="sxs-lookup"><span data-stu-id="0e963-207">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="0e963-208">Root 是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-208">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="0e963-209">**設定**[設定] 是適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-209">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-210">它包含前面所述的登錄、檔案、SystemParameter 及 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-210">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="0e963-211">此外，它也可以包含下列含有行為的子項目：</span><span class="sxs-lookup"><span data-stu-id="0e963-211">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e963-212">元素</span><span class="sxs-lookup"><span data-stu-id="0e963-212">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-213">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-213">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-214">非同步</span><span class="sxs-lookup"><span data-stu-id="0e963-214">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-215">在不封鎖應用程式啟動的情況下，會套用非同步設定套件，讓應用程式在設定仍在套用時開始進行。</span><span class="sxs-lookup"><span data-stu-id="0e963-215">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="0e963-216">這對於可以非同步套用的設定（例如 <code>get/set</code> ，透過 API （例如 SystemParameterSetting）而言很有用。</span><span class="sxs-lookup"><span data-stu-id="0e963-216">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-217">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="0e963-217">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-218">根據預設，UE-V 只會在使用範本的最後一個應用程式實例關閉時，儲存應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-218">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="0e963-219">當這個元素設定為 ' false」時，UE-V 會匯出設定，即使有應用程式的其他實例正在執行也一樣。</span><span class="sxs-lookup"><span data-stu-id="0e963-219">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="0e963-220">適合使用由 UE-V 隨附的常見元素區段的範本（包含通用元素區段）使用此標誌來啟用共用設定，以避免在應用程式關閉時匯出應用程式特定的設定，但在最後一個實例關閉之後，才會進行匯出。</span><span class="sxs-lookup"><span data-stu-id="0e963-220">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-221">AlwaysApplySettings</span><span class="sxs-lookup"><span data-stu-id="0e963-221">AlwaysApplySettings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-222">（2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="0e963-222">(introduced in 2.1)</span></span></p>
<p><span data-ttu-id="0e963-223">此參數會強制會套用匯入的設定套件，即使套件與應用程式的目前狀態之間沒有任何差異也一樣。</span><span class="sxs-lookup"><span data-stu-id="0e963-223">This parameter forces an imported settings package to be applied even if there are no differences between the package and the current state of the application.</span></span> <span data-ttu-id="0e963-224">這個參數只能在特殊的情況中使用，因為它會減緩設定匯入的速度。</span><span class="sxs-lookup"><span data-stu-id="0e963-224">This parameter should be used only in special cases since it can slow down settings import.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a><span data-ttu-id="0e963-225">Name 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-225">Name Element</span></span>

**<span data-ttu-id="0e963-226">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-226">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-227">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-227">Type: String</span></span>**

<span data-ttu-id="0e963-228">名稱指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-228">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-229">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-229">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-230">一般來說，請避免參照版本資訊，因為這可以從 ProductVersion 元素中 objected。</span><span class="sxs-lookup"><span data-stu-id="0e963-230">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="0e963-231">例如，請指定 `<Name>My Application</Name>` （而非） `<Name>My Application 1.1</Name>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-231">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="0e963-232">**記事** UE-V 不會參照外部 Dtd，所以無法在設定位置範本中使用命名實體。</span><span class="sxs-lookup"><span data-stu-id="0e963-232">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="0e963-233">例如，請勿用 &reg; 來參照已註冊的商業標誌簽署®。</span><span class="sxs-lookup"><span data-stu-id="0e963-233">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="0e963-234">相反地，請改用規範編號參照來包含這些類型的特殊字元，例如，®字元 & \ #174。</span><span class="sxs-lookup"><span data-stu-id="0e963-234">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="0e963-235">此規則適用于此檔中的所有字串值。</span><span class="sxs-lookup"><span data-stu-id="0e963-235">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="0e963-236"><http://www.w3.org/TR/xhtml1/dtds.html>如需字元實體的完整清單，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0e963-236">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="0e963-237">UTF-8 編碼的檔可能會直接包含 Unicode 字元。</span><span class="sxs-lookup"><span data-stu-id="0e963-237">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="0e963-238">透過 UE-V 發生器儲存範本時會自動將字元實體轉換成其 Unicode 代表。</span><span class="sxs-lookup"><span data-stu-id="0e963-238">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id21"></a><span data-ttu-id="0e963-239">識別碼元素</span><span class="sxs-lookup"><span data-stu-id="0e963-239">ID Element</span></span>

**<span data-ttu-id="0e963-240">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-240">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-241">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-241">Type: String</span></span>**

<span data-ttu-id="0e963-242">[識別碼] 會填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-242">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-243">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼（例如，請參閱 UevTemplate 和 UevTemplateProgram PowerShell Cmdlet 的輸出）。</span><span class="sxs-lookup"><span data-stu-id="0e963-243">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="0e963-244">根據慣例，此標記不應包含任何空格，以簡化腳本撰寫。</span><span class="sxs-lookup"><span data-stu-id="0e963-244">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="0e963-245">應用程式的版本號碼應該在這個元素中指定，以便更輕鬆地識別範本，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-245">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version21"></a><span data-ttu-id="0e963-246">Version 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-246">Version Element</span></span>

**<span data-ttu-id="0e963-247">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-247">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-248">類型： Integer</span><span class="sxs-lookup"><span data-stu-id="0e963-248">Type: Integer</span></span>**

**<span data-ttu-id="0e963-249">最小值：0</span><span class="sxs-lookup"><span data-stu-id="0e963-249">Minimum Value: 0</span></span>**

**<span data-ttu-id="0e963-250">最大值：2147483647</span><span class="sxs-lookup"><span data-stu-id="0e963-250">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="0e963-251">[版本] 可識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-251">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-252">每次儲存範本時，UE-V 發生器都會自動將這個數位遞增1。</span><span class="sxs-lookup"><span data-stu-id="0e963-252">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="0e963-253">請注意，這個欄位必須是整數整數;分數值，例如 `<Version>2.5</Version>` 不允許。</span><span class="sxs-lookup"><span data-stu-id="0e963-253">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="0e963-254">**提示：** 您可以使用 XML comment 標記儲存有關版本變更 `<!-- -->` 的筆記，例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-254">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

<span data-ttu-id="0e963-255">**重要** 系統會詢問此值，以判斷是否應該在這些範例中將範本的新版本套用至現有的範本：</span><span class="sxs-lookup"><span data-stu-id="0e963-255">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="0e963-256">排程範本自動更新工作執行時</span><span class="sxs-lookup"><span data-stu-id="0e963-256">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="0e963-257">在執行更新 UevTemplate PowerShell Cmdlet 時</span><span class="sxs-lookup"><span data-stu-id="0e963-257">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="0e963-258">透過 WMI 呼叫 microsoft\\uev： SettingsLocationTemplate Update 方法時</span><span class="sxs-lookup"><span data-stu-id="0e963-258">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author21"></a><span data-ttu-id="0e963-259">Author 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-259">Author Element</span></span>

**<span data-ttu-id="0e963-260">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-260">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-261">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-261">Type: String</span></span>**

<span data-ttu-id="0e963-262">[作者] 會識別 [設定位置] 範本的建立者。</span><span class="sxs-lookup"><span data-stu-id="0e963-262">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="0e963-263">支援兩個選用的子項目： [**名稱**] 和 [**電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-263">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="0e963-264">這兩個屬性都是選擇性的，但如果指定了電子郵件子項目，則它必須伴隨 Name 元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-264">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="0e963-265">[作者] 是指 [設定位置] 範本的連絡人完整名稱，而電子郵件應該是代表作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0e963-265">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="0e963-266">我們建議您在發佈的範本中包含這項資訊，例如，在[Ue-v 範本圖庫](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。</span><span class="sxs-lookup"><span data-stu-id="0e963-266">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes21"></a><span data-ttu-id="0e963-267">進程與程式元素</span><span class="sxs-lookup"><span data-stu-id="0e963-267">Processes and Process Element</span></span>

**<span data-ttu-id="0e963-268">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-268">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-269">Type：元素</span><span class="sxs-lookup"><span data-stu-id="0e963-269">Type: Element</span></span>**

<span data-ttu-id="0e963-270">進程至少包含一個 `<Process>` 元素，而該元素又包含下列子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="0e963-270">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="0e963-271">Filename 子項目是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-271">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="0e963-272">完全填入的元素包含與此範例類似的標記：</span><span class="sxs-lookup"><span data-stu-id="0e963-272">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="0e963-273">副檔名</span><span class="sxs-lookup"><span data-stu-id="0e963-273">Filename</span></span>

**<span data-ttu-id="0e963-274">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-274">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-275">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-275">Type: String</span></span>**

<span data-ttu-id="0e963-276">Filename 指的是可執行檔在檔案系統中出現的實際檔案名。</span><span class="sxs-lookup"><span data-stu-id="0e963-276">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="0e963-277">這個元素指定 UE-V 用來評估範本是否適用于流程的主要準則。</span><span class="sxs-lookup"><span data-stu-id="0e963-277">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="0e963-278">這個元素必須在 [設定位置] 範本 XML 中指定。</span><span class="sxs-lookup"><span data-stu-id="0e963-278">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="0e963-279">有效的檔案名必須與正則運算式 \ [^ \\ \\ \ \？ \\ \* \ | &lt; &gt;/： \] +，也就是不能包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號（\\？</span><span class="sxs-lookup"><span data-stu-id="0e963-279">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="0e963-280">\* |&lt; &gt; /或：個字元）。</span><span class="sxs-lookup"><span data-stu-id="0e963-280">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="0e963-281">**提示：** 若要對照此 RegEx 測試字串，請使用 PowerShell 命令視窗，並將您的可執行檔名稱取代為**YourFileName**：</span><span class="sxs-lookup"><span data-stu-id="0e963-281">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="0e963-282">**True**值表示字串包含非法字元。</span><span class="sxs-lookup"><span data-stu-id="0e963-282">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="0e963-283">以下是非法值的一些範例：</span><span class="sxs-lookup"><span data-stu-id="0e963-283">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="0e963-284">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="0e963-284">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="0e963-285">Program \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="0e963-285">Program\*.exe</span></span>

-   <span data-ttu-id="0e963-286">Pro？ ram.exe</span><span class="sxs-lookup"><span data-stu-id="0e963-286">Pro?ram.exe</span></span>

-   <span data-ttu-id="0e963-287">程式 &lt; 1 &gt; .exe</span><span class="sxs-lookup"><span data-stu-id="0e963-287">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="0e963-288">**記事** UE-V 發生器分別對大於和小於字元進行編碼 &gt; &lt; 。</span><span class="sxs-lookup"><span data-stu-id="0e963-288">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="0e963-289">在極少數情況下，FileName 值不一定包括 .exe 副檔名，但應該將它指定為值的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e963-289">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="0e963-290">例如， `<Filename>MyApplictication.exe</Filename>` 應指定而不是 `<Filename>MyApplictication</Filename>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-290">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="0e963-291">如果可執行檔的實際名稱是「MyApplication.exe」，則第二個範例不會將範本套用至程式。</span><span class="sxs-lookup"><span data-stu-id="0e963-291">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="0e963-292">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-292">Architecture</span></span>

**<span data-ttu-id="0e963-293">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-293">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-294">類型：結構（字串）</span><span class="sxs-lookup"><span data-stu-id="0e963-294">Type: Architecture (String)</span></span>**

<span data-ttu-id="0e963-295">結構指的是編譯目標可執行檔的處理器架構。</span><span class="sxs-lookup"><span data-stu-id="0e963-295">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="0e963-296">有效值為32位應用程式的 Win32，或64位應用程式的 Win64。</span><span class="sxs-lookup"><span data-stu-id="0e963-296">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="0e963-297">如果有，此標記會將 [設定位置] 範本的適用性限制為特定的應用程式結構。</span><span class="sxs-lookup"><span data-stu-id="0e963-297">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="0e963-298">如需這種情況的範例，請比較%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 與 UE-V 隨附的 MicrosoftOffice2010Win64.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e963-298">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="0e963-299">當相對路徑在不同版本的可執行檔之間變更，或在從一個處理器架構移到另一個時，如果已新增或移除設定，這就很有用。</span><span class="sxs-lookup"><span data-stu-id="0e963-299">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="0e963-300">如果此元素不存在，則設定位置範本會忽略進程的體系結構，並同時適用于32和64位程式（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="0e963-300">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="0e963-301">**記事** UE-V 在這個版本中不支援 ARM 處理器。</span><span class="sxs-lookup"><span data-stu-id="0e963-301">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="0e963-302">ProductName</span><span class="sxs-lookup"><span data-stu-id="0e963-302">ProductName</span></span>

**<span data-ttu-id="0e963-303">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-303">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-304">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-304">Type: String</span></span>**

<span data-ttu-id="0e963-305">ProductName 是一個可供您用來識別管理用途或報告之產品的選用元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-305">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="0e963-306">ProductName 與 Filename 不同，因為它的值沒有正則運算式限制。</span><span class="sxs-lookup"><span data-stu-id="0e963-306">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="0e963-307">這可讓您更輕鬆地瞭解可執行檔名稱可能不明顯的程式說明。</span><span class="sxs-lookup"><span data-stu-id="0e963-307">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="0e963-308">例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-308">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="0e963-309">FileDescription</span><span class="sxs-lookup"><span data-stu-id="0e963-309">FileDescription</span></span>

**<span data-ttu-id="0e963-310">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-310">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-311">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-311">Type: String</span></span>**

<span data-ttu-id="0e963-312">FileDescription 是一個可執行檔的系統管理描述的選擇性標記。</span><span class="sxs-lookup"><span data-stu-id="0e963-312">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="0e963-313">這是自由文字欄位，在您需要識別可執行檔之功能的軟體套件中，可能會有説明。</span><span class="sxs-lookup"><span data-stu-id="0e963-313">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="0e963-314">例如，在適用的應用程式中，提供兩個可執行檔（MyApplication.exe 和 MyApplicationHelper.exe）功能的提醒可能會很有用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e963-314">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="0e963-315">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-315">ProductVersion</span></span>

**<span data-ttu-id="0e963-316">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-316">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-317">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-317">Type: String</span></span>**

<span data-ttu-id="0e963-318">ProductVersion 指的是檔案的主要及次要產品版本，以及組建與修補程式層級。</span><span class="sxs-lookup"><span data-stu-id="0e963-318">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="0e963-319">ProductVersion 是一個選用的元素，但如果有指定，它必須包含至少主要的子項目。</span><span class="sxs-lookup"><span data-stu-id="0e963-319">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="0e963-320">此值必須以最小值為 "X" 的範圍來表示最大值 = "X" 上限 = "Y"，其中 X 和 Y 為整數。</span><span class="sxs-lookup"><span data-stu-id="0e963-320">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="0e963-321">[最小值] 和 [最大值] 可以完全相同。</span><span class="sxs-lookup"><span data-stu-id="0e963-321">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="0e963-322">產品和檔案版本元素可能是未指定的。</span><span class="sxs-lookup"><span data-stu-id="0e963-322">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="0e963-323">如此一來，就會將範本設為「不限版本」，這表示該範本會套用至指定的可執行檔的所有版本。</span><span class="sxs-lookup"><span data-stu-id="0e963-323">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="0e963-324">範例 1：</span><span class="sxs-lookup"><span data-stu-id="0e963-324">Example 1:</span></span>**

<span data-ttu-id="0e963-325">UE-V 發生器中指定的產品版本：1.0 會產生下列 XML：</span><span class="sxs-lookup"><span data-stu-id="0e963-325">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="0e963-326">範例 2：</span><span class="sxs-lookup"><span data-stu-id="0e963-326">Example 2:</span></span>**

<span data-ttu-id="0e963-327">檔版本： UE-V 發生器中指定的5.0.2.1000 會產生下列 XML：</span><span class="sxs-lookup"><span data-stu-id="0e963-327">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="0e963-328">不正確的範例1–不完整範圍：</span><span class="sxs-lookup"><span data-stu-id="0e963-328">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="0e963-329">只有最小屬性出現。</span><span class="sxs-lookup"><span data-stu-id="0e963-329">Only the Minimum attribute is present.</span></span> <span data-ttu-id="0e963-330">範圍中也必須包含最大值。</span><span class="sxs-lookup"><span data-stu-id="0e963-330">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="0e963-331">不正確的範例2–指定的次要元素沒有主要元素：</span><span class="sxs-lookup"><span data-stu-id="0e963-331">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="0e963-332">只有次要元素存在。</span><span class="sxs-lookup"><span data-stu-id="0e963-332">Only the Minor element is present.</span></span> <span data-ttu-id="0e963-333">還必須包含主要版本。</span><span class="sxs-lookup"><span data-stu-id="0e963-333">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="0e963-334">FileVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-334">FileVersion</span></span>

**<span data-ttu-id="0e963-335">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-335">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-336">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-336">Type: String</span></span>**

<span data-ttu-id="0e963-337">FileVersion 會區分已發佈應用程式的發行版本本，以及元件可執行檔的內部組建詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0e963-337">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="0e963-338">對於大多數商業應用程式而言，這些號碼是完全相同的。</span><span class="sxs-lookup"><span data-stu-id="0e963-338">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="0e963-339">在其他情況下，檔案的產品版本會指示檔案的一般版本識別，而檔案版本則表示檔案的特定組建（例如，修補程式或更新的情況）。</span><span class="sxs-lookup"><span data-stu-id="0e963-339">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="0e963-340">這會唯一識別檔案，而不會中斷偵測邏輯。</span><span class="sxs-lookup"><span data-stu-id="0e963-340">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="0e963-341">若要判斷特定可執行檔的產品版本和檔案版本，請以滑鼠右鍵按一下 Windows 資源管理器中的檔案，選取 [屬性]，然後按一下 [詳細資料] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0e963-341">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="0e963-342">包含應用程式的 FileVersion 元素可讓您更精確地微調偵測邏輯，但對於大部分的應用程式來說，不是必要的。</span><span class="sxs-lookup"><span data-stu-id="0e963-342">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="0e963-343">首先會選取 [ProductVersion] 元素設定，然後 FileVersion [已核取]。</span><span class="sxs-lookup"><span data-stu-id="0e963-343">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="0e963-344">您將會套用限制性較強的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-344">The more restrictive setting will apply.</span></span>

<span data-ttu-id="0e963-345">FileVersion 的子項目和語法規則與 ProductVersion 相同。</span><span class="sxs-lookup"><span data-stu-id="0e963-345">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a><span data-ttu-id="0e963-346">Application 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-346">Application Element</span></span>

<span data-ttu-id="0e963-347">應用程式是適用于特定應用程式的設定容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-347">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="0e963-348">它是下欄欄位/類型的集合。</span><span class="sxs-lookup"><span data-stu-id="0e963-348">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e963-349">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-349">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-350">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-350">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-351">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-351">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-352">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-352">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-353">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-353">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-354">如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-354">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-355">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-355">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-356">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-356">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-357">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-357">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-358">如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-358">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-359">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-359">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-360">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-360">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-361">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-361">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-362">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-362">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-363">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-363">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-364">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-364">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-365">版本</span><span class="sxs-lookup"><span data-stu-id="0e963-365">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-366">識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-366">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-367">如需詳細資訊，請參閱 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-367">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-368">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="0e963-368">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-369">控制是否將此範本與 Microsoft 帳戶搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0e963-369">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="0e963-370">如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-370">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-371">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="0e963-371">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-372">與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-372">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="0e963-373">如果您使用 Office 365 來同步處理設定，此範本會自動停用。</span><span class="sxs-lookup"><span data-stu-id="0e963-373">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-374">FixedProfile （2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="0e963-374">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-375">指定這個範本只能與此元素中指定的設定檔相關聯，而且無法透過 WMI 或 PowerShell 進行變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-375">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-376">處理程序</span><span class="sxs-lookup"><span data-stu-id="0e963-376">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-377">一個或多個處理元素集合的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-377">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="0e963-378">如需詳細資訊，請參閱 <a href="#processes21" data-raw-source="[Processes](#processes21)"> 進程 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-378">For more information, see <a href="#processes21" data-raw-source="[Processes](#processes21)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-379">設定</span><span class="sxs-lookup"><span data-stu-id="0e963-379">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-380">適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-380">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-381">它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-381">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="0e963-382">如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-382">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a><span data-ttu-id="0e963-383">常見元素</span><span class="sxs-lookup"><span data-stu-id="0e963-383">Common Element</span></span>

<span data-ttu-id="0e963-384">[常用] 與應用程式元素類似，但它永遠與兩個或更多個應用程式元素相關聯。</span><span class="sxs-lookup"><span data-stu-id="0e963-384">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="0e963-385">[常見] 區段代表在這些應用程式實例之間共用的一組設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-385">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="0e963-386">它是下欄欄位/類型的集合。</span><span class="sxs-lookup"><span data-stu-id="0e963-386">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e963-387">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-387">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-388">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-388">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-389">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-389">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-390">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-390">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-391">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-391">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-392">如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-392">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-393">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-393">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-394">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-394">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-395">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-395">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-396">如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-396">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-397">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-397">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-398">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-398">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-399">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-399">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-400">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-400">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-401">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-401">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-402">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-402">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-403">版本</span><span class="sxs-lookup"><span data-stu-id="0e963-403">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-404">識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-404">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-405">如需詳細資訊，請參閱 <a href="#version21" data-raw-source="[Version](#version21)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-405">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-406">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="0e963-406">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-407">控制是否將此範本與 Microsoft 帳戶搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0e963-407">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="0e963-408">如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-408">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-409">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="0e963-409">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-410">與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-410">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="0e963-411">如果您使用 Office 365 來同步處理設定，此範本會自動停用。</span><span class="sxs-lookup"><span data-stu-id="0e963-411">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-412">FixedProfile （2.1 中引入）</span><span class="sxs-lookup"><span data-stu-id="0e963-412">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-413">指定這個範本只能與此元素中指定的設定檔相關聯，而且無法透過 WMI 或 PowerShell 進行變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-413">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-414">設定</span><span class="sxs-lookup"><span data-stu-id="0e963-414">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-415">適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-415">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-416">它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-416">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="0e963-417">如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-417">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a><span data-ttu-id="0e963-418">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-418">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="0e963-419">這個元素定義單一應用程式或一套應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-419">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0e963-420">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-420">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="0e963-421">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-421">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-422">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-422">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-423">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-423">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-424">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-424">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-425">如需詳細資訊，請參閱 <a href="#name21" data-raw-source="[Name](#name21)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-425">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-426">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-426">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-427">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-427">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-428">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-428">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-429">如需詳細資訊，請參閱 <a href="#id21" data-raw-source="[ID](#id21)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-429">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-430">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-430">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-431">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-431">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-432">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-432">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-433">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-433">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-434">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-434">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-435">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-435">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a><span data-ttu-id="0e963-436">附錄： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="0e963-436">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="0e963-437">以下是 SettingsLocationTemplate 檔案，其中顯示其元素、子項目、屬性和參數：</span><span class="sxs-lookup"><span data-stu-id="0e963-437">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## <span data-ttu-id="0e963-438">UE-V 2.0 應用程式範本架構參考</span><span class="sxs-lookup"><span data-stu-id="0e963-438">UE-V 2.0 Application Template Schema Reference</span></span>


<span data-ttu-id="0e963-439">本節詳細說明 UE-V 2.0 設定位置範本的 XML 結構，並提供編輯此檔案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="0e963-439">This section details the XML structure of the UE-V 2.0 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="0e963-440">本節內容</span><span class="sxs-lookup"><span data-stu-id="0e963-440">In This Section</span></span>

-   [<span data-ttu-id="0e963-441">XML 宣告與編碼屬性</span><span class="sxs-lookup"><span data-stu-id="0e963-441">XML Declaration and Encoding Attribute</span></span>](#xml)

-   [<span data-ttu-id="0e963-442">命名空間與根項目</span><span class="sxs-lookup"><span data-stu-id="0e963-442">Namespace and Root Element</span></span>](#namespace)

-   [<span data-ttu-id="0e963-443">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-443">Data types</span></span>](#data)

-   [<span data-ttu-id="0e963-444">Name 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-444">Name Element</span></span>](#name)

-   [<span data-ttu-id="0e963-445">識別碼元素</span><span class="sxs-lookup"><span data-stu-id="0e963-445">ID Element</span></span>](#id)

-   [<span data-ttu-id="0e963-446">Version 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-446">Version Element</span></span>](#version)

-   [<span data-ttu-id="0e963-447">Author 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-447">Author Element</span></span>](#author)

-   [<span data-ttu-id="0e963-448">進程與程式元素</span><span class="sxs-lookup"><span data-stu-id="0e963-448">Processes and Process Element</span></span>](#processes)

-   [<span data-ttu-id="0e963-449">Application 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-449">Application Element</span></span>](#application)

-   [<span data-ttu-id="0e963-450">常見元素</span><span class="sxs-lookup"><span data-stu-id="0e963-450">Common Element</span></span>](#common)

-   [<span data-ttu-id="0e963-451">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-451">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate)

-   [<span data-ttu-id="0e963-452">附錄： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="0e963-452">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix)

### <a href="" id="xml"></a><span data-ttu-id="0e963-453">XML 宣告與編碼屬性</span><span class="sxs-lookup"><span data-stu-id="0e963-453">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="0e963-454">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-454">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-455">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-455">Type: String</span></span>**

<span data-ttu-id="0e963-456">XML 聲明必須指定 XML 版本1.0 屬性（ &lt; ？ XML 版本 = "1.0" &gt; ）。</span><span class="sxs-lookup"><span data-stu-id="0e963-456">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="0e963-457">由 UE-V 發生器建立的設定位置範本會儲存為 UTF-8 編碼，但不明確指定編碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-457">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="0e963-458">我們建議您在這個元素中包含 encoding = "UTF-8" 屬性來做為最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0e963-458">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="0e963-459">產品隨附的所有範本也會指定此標記（請參閱%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\Templates 中的檔以瞭解參考）。</span><span class="sxs-lookup"><span data-stu-id="0e963-459">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="0e963-460">例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-460">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a><span data-ttu-id="0e963-461">命名空間與根項目</span><span class="sxs-lookup"><span data-stu-id="0e963-461">Namespace and Root Element</span></span>

**<span data-ttu-id="0e963-462">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-462">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-463">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-463">Type: String</span></span>**

<span data-ttu-id="0e963-464">UE-V 使用 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate 所有應用程式的命名空間。</span><span class="sxs-lookup"><span data-stu-id="0e963-464">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="0e963-465">SettingsLocationTemplate 是根項目，且包含所有其他元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-465">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="0e963-466">使用此標記的所有範本中的參照 SettingsLocationTemplate：</span><span class="sxs-lookup"><span data-stu-id="0e963-466">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a><span data-ttu-id="0e963-467">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-467">Data types</span></span>

<span data-ttu-id="0e963-468">以下是 UE-V 應用程式範本架構的資料類型。</span><span class="sxs-lookup"><span data-stu-id="0e963-468">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="0e963-469">**GUID**GUID 描述標準的全域唯一識別碼正則運算式，形式為 "\\ {\ [a-fA-F0-9 \] {8} -\ [a-fa-F0-9 \]- {4} \] [a-FA-F0-9 \] {4} -\ [a-fa-F0-9 \] {4} -\ [a-fa-F0-9 \] {12} \}"。</span><span class="sxs-lookup"><span data-stu-id="0e963-469">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="0e963-470">這會在 Filesetting\\Root\\KnownFolder 元素中使用，以驗證已知資料夾的格式設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-470">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="0e963-471">**FilenameString**FilenameString 是指要監視之程式的檔案名。</span><span class="sxs-lookup"><span data-stu-id="0e963-471">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="0e963-472">它的值會受到 RegEx \ [^ \\ \\ \* \ \ | &lt; &gt;/： \] +，（也就是說，它們可能不包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號字元）。</span><span class="sxs-lookup"><span data-stu-id="0e963-472">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="0e963-473">**IDString**IDString 指的是應用程式元素、SettingsLocationTemplate 及常見元素的識別碼值（用來描述共用一般設定的應用程式套件）。</span><span class="sxs-lookup"><span data-stu-id="0e963-473">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="0e963-474">它受到與 FilenameString 相同的 RegEx （\ [^ \\ \\ \\？ \\ \* \\ | &lt; &gt;/:\]+).</span><span class="sxs-lookup"><span data-stu-id="0e963-474">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="0e963-475">**TemplateVersion**TemplateVersion 是一個整數值，用於描述設定位置範本的修訂。</span><span class="sxs-lookup"><span data-stu-id="0e963-475">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="0e963-476">其值的範圍可以是0到2147483647。</span><span class="sxs-lookup"><span data-stu-id="0e963-476">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="0e963-477">**空白**空白代表 null 值。</span><span class="sxs-lookup"><span data-stu-id="0e963-477">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="0e963-478">這會在 Process\\ShellProcess 中使用，表示沒有任何程式可供監視。</span><span class="sxs-lookup"><span data-stu-id="0e963-478">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="0e963-479">您不應該在任何應用程式範本中使用這個值。</span><span class="sxs-lookup"><span data-stu-id="0e963-479">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="0e963-480">**作者**[作者] 資料類型是一種複雜類型，可用於識別範本的作者。</span><span class="sxs-lookup"><span data-stu-id="0e963-480">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="0e963-481">它包含兩個子項目： [**名稱**] 和 [**電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-481">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="0e963-482">在 Author 資料類型中，Name 元素是必要的，而 Email 元素是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-482">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="0e963-483">此類型會在 SettingsLocationTemplate 元素下更詳細的說明。</span><span class="sxs-lookup"><span data-stu-id="0e963-483">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="0e963-484">**範圍**範圍定義由兩個子項目組成的整數類別： [**最小值**] 和 [**最大值**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-484">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="0e963-485">此資料類型是在 ProcessVersion 資料類型中實現。</span><span class="sxs-lookup"><span data-stu-id="0e963-485">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="0e963-486">如果已指定，則必須包含最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="0e963-486">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="0e963-487">**ProcessVersion**ProcessVersion 會定義含有四個子項目的類型：**主要**、**次要**、**組建**及**修補程式**。</span><span class="sxs-lookup"><span data-stu-id="0e963-487">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="0e963-488">此資料類型是由 Process 元素用來填入其 ProductVersion 和 FileVersion 值。</span><span class="sxs-lookup"><span data-stu-id="0e963-488">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="0e963-489">此類型的資料是範圍值。</span><span class="sxs-lookup"><span data-stu-id="0e963-489">The data for this type is a Range value.</span></span> <span data-ttu-id="0e963-490">主要子項目是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-490">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="0e963-491">**架構**結構列舉了兩個可能的值： **Win32**和**Win64**。</span><span class="sxs-lookup"><span data-stu-id="0e963-491">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="0e963-492">這些值是用來指定處理常式體系結構。</span><span class="sxs-lookup"><span data-stu-id="0e963-492">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="0e963-493">**處理**程式[流程] 資料類型是用來描述要由 UE-V 監視之進程的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-493">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="0e963-494">它包含六個子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="0e963-494">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="0e963-495">下表詳細說明每個元素各自的資料類型：</span><span class="sxs-lookup"><span data-stu-id="0e963-495">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e963-496">元素</span><span class="sxs-lookup"><span data-stu-id="0e963-496">Element</span></span></th>
<th align="left"><span data-ttu-id="0e963-497">資料類型</span><span class="sxs-lookup"><span data-stu-id="0e963-497">Data Type</span></span></th>
<th align="left"><span data-ttu-id="0e963-498">Mandatory</span><span class="sxs-lookup"><span data-stu-id="0e963-498">Mandatory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-499">副檔名</span><span class="sxs-lookup"><span data-stu-id="0e963-499">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-500">FilenameString</span><span class="sxs-lookup"><span data-stu-id="0e963-500">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-501">True</span><span class="sxs-lookup"><span data-stu-id="0e963-501">True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-502">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-502">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-503">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-503">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-504">False</span><span class="sxs-lookup"><span data-stu-id="0e963-504">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-505">ProductName</span><span class="sxs-lookup"><span data-stu-id="0e963-505">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-506">字串</span><span class="sxs-lookup"><span data-stu-id="0e963-506">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-507">False</span><span class="sxs-lookup"><span data-stu-id="0e963-507">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-508">FileDescription</span><span class="sxs-lookup"><span data-stu-id="0e963-508">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-509">字串</span><span class="sxs-lookup"><span data-stu-id="0e963-509">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-510">False</span><span class="sxs-lookup"><span data-stu-id="0e963-510">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-511">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-511">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-512">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-512">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-513">False</span><span class="sxs-lookup"><span data-stu-id="0e963-513">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-514">FileVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-514">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-515">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-515">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-516">False</span><span class="sxs-lookup"><span data-stu-id="0e963-516">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="0e963-517">**處理**程式[進程] 資料類型代表一或多個處理元素集合的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-517">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="0e963-518">進程式列類型支援兩個子項目： **Process**與**ShellProcess**。</span><span class="sxs-lookup"><span data-stu-id="0e963-518">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="0e963-519">Process 是 Process 類型的元素，且 ShellProcess 的資料類型為空白。</span><span class="sxs-lookup"><span data-stu-id="0e963-519">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="0e963-520">在順序中至少必須辨識一個專案。</span><span class="sxs-lookup"><span data-stu-id="0e963-520">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="0e963-521">**路徑**RegistrySetting 和 FileSetting 會使用 Path 來參照登錄和檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="0e963-521">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="0e963-522">這個元素支援兩個選用的屬性： **Recursive**與**DeleteIfNotFound**。</span><span class="sxs-lookup"><span data-stu-id="0e963-522">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="0e963-523">這兩個值都設定為 default = "False"。</span><span class="sxs-lookup"><span data-stu-id="0e963-523">Both values are set to default=”False”.</span></span>

<span data-ttu-id="0e963-524">Recursive：表示檔案設定中包含路徑和所有子資料夾，或是所有的子登錄機碼都包含在註冊設定中。</span><span class="sxs-lookup"><span data-stu-id="0e963-524">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="0e963-525">在這兩種情況下，目前層級的所有專案都會包含在捕獲的資料中。</span><span class="sxs-lookup"><span data-stu-id="0e963-525">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="0e963-526">針對 FileSettings 物件，指定資料夾中的所有檔案都包含在 UE-V 捕獲的資料中，但不包含資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e963-526">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="0e963-527">針對登錄路徑，會捕獲目前路徑中的所有值，但不會捕獲子登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-527">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="0e963-528">在這兩種情況下，請小心考慮避免捕獲大型資料集或大量專案。</span><span class="sxs-lookup"><span data-stu-id="0e963-528">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="0e963-529">DeleteIfNotFound 屬性會從使用者的設定儲存路徑資料中移除設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-529">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="0e963-530">在從套件中移除這些設定時，可能需要這麼做，將大量磁碟空間儲存在設定儲存路徑檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0e963-530">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="0e963-531">**FileMask**FileMask 僅指定由 Path 所定義之資料夾的特定檔案類型。</span><span class="sxs-lookup"><span data-stu-id="0e963-531">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="0e963-532">例如，Path 可能是， `C:\users\username\files` 且 FileMask `*.txt` 只能包含文字檔。</span><span class="sxs-lookup"><span data-stu-id="0e963-532">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="0e963-533">**RegistrySetting**RegistrySetting 代表登錄機碼和值的容器，以及 UE-V Agent 元件上相關聯的所需行為。</span><span class="sxs-lookup"><span data-stu-id="0e963-533">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="0e963-534">此類型中定義了四個子項目： **path**、 **Name**、 **Exclude**以及值**Path**和**Name**的順序。</span><span class="sxs-lookup"><span data-stu-id="0e963-534">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="0e963-535">**FileSetting**FileSetting 包含與檔案和檔案路徑相關聯的參數。</span><span class="sxs-lookup"><span data-stu-id="0e963-535">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="0e963-536">定義了四個子項目： **Root**、 **Path**、 **FileMask**及**Exclude**。</span><span class="sxs-lookup"><span data-stu-id="0e963-536">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="0e963-537">Root 是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-537">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="0e963-538">**設定**[設定] 是適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-538">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-539">它包含前面所述的登錄、檔案、SystemParameter 及 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-539">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="0e963-540">此外，它也可以包含下列含有行為的子項目：</span><span class="sxs-lookup"><span data-stu-id="0e963-540">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e963-541">元素</span><span class="sxs-lookup"><span data-stu-id="0e963-541">Element</span></span></th>
<th align="left"><span data-ttu-id="0e963-542">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-542">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-543">非同步</span><span class="sxs-lookup"><span data-stu-id="0e963-543">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-544">在不封鎖應用程式啟動的情況下，會套用非同步設定套件，讓應用程式在設定仍在套用時開始進行。</span><span class="sxs-lookup"><span data-stu-id="0e963-544">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="0e963-545">這對於可以非同步套用的設定（例如 <code>get/set</code> ，透過 API （例如 SystemParameterSetting）而言很有用。</span><span class="sxs-lookup"><span data-stu-id="0e963-545">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-546">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="0e963-546">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-547">根據預設，UE-V 只會在使用範本的最後一個應用程式實例關閉時，儲存應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-547">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="0e963-548">當這個元素設定為 ' false」時，UE-V 會匯出設定，即使有應用程式的其他實例正在執行也一樣。</span><span class="sxs-lookup"><span data-stu-id="0e963-548">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="0e963-549">適合使用由 UE-V 隨附的常見元素區段的範本（包含通用元素區段）使用此標誌來啟用共用設定，以避免在應用程式關閉時匯出應用程式特定的設定，但在最後一個實例關閉之後，才會進行匯出。</span><span class="sxs-lookup"><span data-stu-id="0e963-549">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a><span data-ttu-id="0e963-550">Name 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-550">Name Element</span></span>

**<span data-ttu-id="0e963-551">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-551">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-552">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-552">Type: String</span></span>**

<span data-ttu-id="0e963-553">名稱指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-553">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-554">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-554">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-555">一般來說，請避免參照版本資訊，因為這可以從 ProductVersion 元素中 objected。</span><span class="sxs-lookup"><span data-stu-id="0e963-555">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="0e963-556">例如，請指定 `<Name>My Application</Name>` （而非） `<Name>My Application 1.1</Name>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-556">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="0e963-557">**記事** UE-V 不會參照外部 Dtd，所以無法在設定位置範本中使用命名實體。</span><span class="sxs-lookup"><span data-stu-id="0e963-557">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="0e963-558">例如，請勿用 &reg; 來參照已註冊的商業標誌簽署®。</span><span class="sxs-lookup"><span data-stu-id="0e963-558">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="0e963-559">相反地，請改用規範編號參照來包含這些類型的特殊字元，例如，®字元 & \ #174。</span><span class="sxs-lookup"><span data-stu-id="0e963-559">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="0e963-560">此規則適用于此檔中的所有字串值。</span><span class="sxs-lookup"><span data-stu-id="0e963-560">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="0e963-561"><http://www.w3.org/TR/xhtml1/dtds.html>如需字元實體的完整清單，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0e963-561">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="0e963-562">UTF-8 編碼的檔可能會直接包含 Unicode 字元。</span><span class="sxs-lookup"><span data-stu-id="0e963-562">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="0e963-563">透過 UE-V 發生器儲存範本時會自動將字元實體轉換成其 Unicode 代表。</span><span class="sxs-lookup"><span data-stu-id="0e963-563">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id"></a><span data-ttu-id="0e963-564">識別碼元素</span><span class="sxs-lookup"><span data-stu-id="0e963-564">ID Element</span></span>

**<span data-ttu-id="0e963-565">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-565">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-566">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-566">Type: String</span></span>**

<span data-ttu-id="0e963-567">[識別碼] 會填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-567">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-568">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼（例如，請參閱 UevTemplate 和 UevTemplateProgram PowerShell Cmdlet 的輸出）。</span><span class="sxs-lookup"><span data-stu-id="0e963-568">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="0e963-569">根據慣例，此標記不應包含任何空格，以簡化腳本撰寫。</span><span class="sxs-lookup"><span data-stu-id="0e963-569">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="0e963-570">應用程式的版本號碼應該在這個元素中指定，以便更輕鬆地識別範本，例如 `<ID>MicrosoftCalculator6</ID>` 或 `<ID>MicrosoftOffice2010Win64</ID>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-570">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version"></a><span data-ttu-id="0e963-571">Version 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-571">Version Element</span></span>

**<span data-ttu-id="0e963-572">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-572">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-573">類型： Integer</span><span class="sxs-lookup"><span data-stu-id="0e963-573">Type: Integer</span></span>**

**<span data-ttu-id="0e963-574">最小值：0</span><span class="sxs-lookup"><span data-stu-id="0e963-574">Minimum Value: 0</span></span>**

**<span data-ttu-id="0e963-575">最大值：2147483647</span><span class="sxs-lookup"><span data-stu-id="0e963-575">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="0e963-576">[版本] 可識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-576">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-577">每次儲存範本時，UE-V 發生器都會自動將這個數位遞增1。</span><span class="sxs-lookup"><span data-stu-id="0e963-577">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="0e963-578">請注意，這個欄位必須是整數整數;分數值，例如 `<Version>2.5</Version>` 不允許。</span><span class="sxs-lookup"><span data-stu-id="0e963-578">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="0e963-579">**提示：** 您可以使用 XML comment 標記儲存有關版本變更 `<!-- -->` 的筆記，例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-579">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

<span data-ttu-id="0e963-580">**重要** 系統會詢問此值，以判斷是否應該在這些範例中將範本的新版本套用至現有的範本：</span><span class="sxs-lookup"><span data-stu-id="0e963-580">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="0e963-581">排程範本自動更新工作執行時</span><span class="sxs-lookup"><span data-stu-id="0e963-581">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="0e963-582">在執行更新 UevTemplate PowerShell Cmdlet 時</span><span class="sxs-lookup"><span data-stu-id="0e963-582">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="0e963-583">透過 WMI 呼叫 microsoft\\uev： SettingsLocationTemplate Update 方法時</span><span class="sxs-lookup"><span data-stu-id="0e963-583">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author"></a><span data-ttu-id="0e963-584">Author 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-584">Author Element</span></span>

**<span data-ttu-id="0e963-585">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-585">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-586">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-586">Type: String</span></span>**

<span data-ttu-id="0e963-587">[作者] 會識別 [設定位置] 範本的建立者。</span><span class="sxs-lookup"><span data-stu-id="0e963-587">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="0e963-588">支援兩個選用的子項目： [**名稱**] 和 [**電子郵件**]。</span><span class="sxs-lookup"><span data-stu-id="0e963-588">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="0e963-589">這兩個屬性都是選擇性的，但如果指定了電子郵件子項目，則它必須伴隨 Name 元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-589">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="0e963-590">[作者] 是指 [設定位置] 範本的連絡人完整名稱，而電子郵件應該是代表作者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0e963-590">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="0e963-591">我們建議您在發佈的範本中包含這項資訊，例如，在[Ue-v 範本圖庫](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)中。</span><span class="sxs-lookup"><span data-stu-id="0e963-591">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes"></a><span data-ttu-id="0e963-592">進程與程式元素</span><span class="sxs-lookup"><span data-stu-id="0e963-592">Processes and Process Element</span></span>

**<span data-ttu-id="0e963-593">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-593">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-594">Type：元素</span><span class="sxs-lookup"><span data-stu-id="0e963-594">Type: Element</span></span>**

<span data-ttu-id="0e963-595">進程至少包含一個 `<Process>` 元素，而該元素又包含下列子項目： **Filename**、**結構**、 **ProductName**、 **FileDescription**、 **ProductVersion**和**FileVersion**。</span><span class="sxs-lookup"><span data-stu-id="0e963-595">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="0e963-596">Filename 子項目是強制性的，而其他則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="0e963-596">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="0e963-597">完全填入的元素包含與此範例類似的標記：</span><span class="sxs-lookup"><span data-stu-id="0e963-597">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="0e963-598">副檔名</span><span class="sxs-lookup"><span data-stu-id="0e963-598">Filename</span></span>

**<span data-ttu-id="0e963-599">強制： True</span><span class="sxs-lookup"><span data-stu-id="0e963-599">Mandatory: True</span></span>**

**<span data-ttu-id="0e963-600">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-600">Type: String</span></span>**

<span data-ttu-id="0e963-601">Filename 指的是可執行檔在檔案系統中出現的實際檔案名。</span><span class="sxs-lookup"><span data-stu-id="0e963-601">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="0e963-602">這個元素指定 UE-V 用來評估範本是否適用于流程的主要準則。</span><span class="sxs-lookup"><span data-stu-id="0e963-602">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="0e963-603">這個元素必須在 [設定位置] 範本 XML 中指定。</span><span class="sxs-lookup"><span data-stu-id="0e963-603">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="0e963-604">有效的檔案名必須與正則運算式 \ [^ \\ \\ \ \？ \\ \* \ | &lt; &gt;/： \] +，也就是不能包含反斜線字元、星號或問號萬用字元、管道字元、大於或小於符號、轉寄斜線或冒號（\\？</span><span class="sxs-lookup"><span data-stu-id="0e963-604">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="0e963-605">\* |&lt; &gt; /或：個字元）。</span><span class="sxs-lookup"><span data-stu-id="0e963-605">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="0e963-606">**提示：** 若要對照此 RegEx 測試字串，請使用 PowerShell 命令視窗，並將您的可執行檔名稱取代為**YourFileName**：</span><span class="sxs-lookup"><span data-stu-id="0e963-606">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="0e963-607">**True**值表示字串包含非法字元。</span><span class="sxs-lookup"><span data-stu-id="0e963-607">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="0e963-608">以下是非法值的一些範例：</span><span class="sxs-lookup"><span data-stu-id="0e963-608">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="0e963-609">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="0e963-609">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="0e963-610">Program \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="0e963-610">Program\*.exe</span></span>

-   <span data-ttu-id="0e963-611">Pro？ ram.exe</span><span class="sxs-lookup"><span data-stu-id="0e963-611">Pro?ram.exe</span></span>

-   <span data-ttu-id="0e963-612">程式 &lt; 1 &gt; .exe</span><span class="sxs-lookup"><span data-stu-id="0e963-612">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="0e963-613">**記事** UE-V 發生器分別對大於和小於字元進行編碼 &gt; &lt; 。</span><span class="sxs-lookup"><span data-stu-id="0e963-613">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="0e963-614">在極少數情況下，FileName 值不一定包括 .exe 副檔名，但應該將它指定為值的一部分。</span><span class="sxs-lookup"><span data-stu-id="0e963-614">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="0e963-615">例如， `<Filename>MyApplictication.exe</Filename>` 應指定而不是 `<Filename>MyApplictication</Filename>` 。</span><span class="sxs-lookup"><span data-stu-id="0e963-615">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="0e963-616">如果可執行檔的實際名稱是「MyApplication.exe」，則第二個範例不會將範本套用至程式。</span><span class="sxs-lookup"><span data-stu-id="0e963-616">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="0e963-617">架構</span><span class="sxs-lookup"><span data-stu-id="0e963-617">Architecture</span></span>

**<span data-ttu-id="0e963-618">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-618">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-619">類型：結構（字串）</span><span class="sxs-lookup"><span data-stu-id="0e963-619">Type: Architecture (String)</span></span>**

<span data-ttu-id="0e963-620">結構指的是編譯目標可執行檔的處理器架構。</span><span class="sxs-lookup"><span data-stu-id="0e963-620">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="0e963-621">有效值為32位應用程式的 Win32，或64位應用程式的 Win64。</span><span class="sxs-lookup"><span data-stu-id="0e963-621">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="0e963-622">如果有，此標記會將 [設定位置] 範本的適用性限制為特定的應用程式結構。</span><span class="sxs-lookup"><span data-stu-id="0e963-622">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="0e963-623">如需這種情況的範例，請比較%ProgramFiles%\\Microsoft 使用者體驗 Virtualization\\templates\\ MicrosoftOffice2010Win32.xml 與 UE-V 隨附的 MicrosoftOffice2010Win64.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e963-623">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="0e963-624">當相對路徑在不同版本的可執行檔之間變更，或在從一個處理器架構移到另一個時，如果已新增或移除設定，這就很有用。</span><span class="sxs-lookup"><span data-stu-id="0e963-624">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="0e963-625">如果此元素不存在，則設定位置範本會忽略進程的體系結構，並同時適用于32和64位程式（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="0e963-625">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="0e963-626">**記事** UE-V 在這個版本中不支援 ARM 處理器。</span><span class="sxs-lookup"><span data-stu-id="0e963-626">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="0e963-627">ProductName</span><span class="sxs-lookup"><span data-stu-id="0e963-627">ProductName</span></span>

**<span data-ttu-id="0e963-628">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-628">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-629">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-629">Type: String</span></span>**

<span data-ttu-id="0e963-630">ProductName 是一個可供您用來識別管理用途或報告之產品的選用元素。</span><span class="sxs-lookup"><span data-stu-id="0e963-630">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="0e963-631">ProductName 與 Filename 不同，因為它的值沒有正則運算式限制。</span><span class="sxs-lookup"><span data-stu-id="0e963-631">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="0e963-632">這可讓您更輕鬆地瞭解可執行檔名稱可能不明顯的程式說明。</span><span class="sxs-lookup"><span data-stu-id="0e963-632">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="0e963-633">例如：</span><span class="sxs-lookup"><span data-stu-id="0e963-633">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="0e963-634">FileDescription</span><span class="sxs-lookup"><span data-stu-id="0e963-634">FileDescription</span></span>

**<span data-ttu-id="0e963-635">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-635">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-636">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-636">Type: String</span></span>**

<span data-ttu-id="0e963-637">FileDescription 是一個可執行檔的系統管理描述的選擇性標記。</span><span class="sxs-lookup"><span data-stu-id="0e963-637">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="0e963-638">這是自由文字欄位，在您需要識別可執行檔之功能的軟體套件中，可能會有説明。</span><span class="sxs-lookup"><span data-stu-id="0e963-638">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="0e963-639">例如，在適用的應用程式中，提供兩個可執行檔（MyApplication.exe 和 MyApplicationHelper.exe）功能的提醒可能會很有用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e963-639">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="0e963-640">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-640">ProductVersion</span></span>

**<span data-ttu-id="0e963-641">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-641">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-642">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-642">Type: String</span></span>**

<span data-ttu-id="0e963-643">ProductVersion 指的是檔案的主要及次要產品版本，以及組建與修補程式層級。</span><span class="sxs-lookup"><span data-stu-id="0e963-643">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="0e963-644">ProductVersion 是一個選用的元素，但如果有指定，它必須包含至少主要的子項目。</span><span class="sxs-lookup"><span data-stu-id="0e963-644">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="0e963-645">此值必須以最小值為 "X" 的範圍來表示最大值 = "X" 上限 = "Y"，其中 X 和 Y 為整數。</span><span class="sxs-lookup"><span data-stu-id="0e963-645">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="0e963-646">[最小值] 和 [最大值] 可以完全相同。</span><span class="sxs-lookup"><span data-stu-id="0e963-646">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="0e963-647">產品和檔案版本元素可能是未指定的。</span><span class="sxs-lookup"><span data-stu-id="0e963-647">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="0e963-648">如此一來，就會將範本設為「不限版本」，這表示該範本會套用至指定的可執行檔的所有版本。</span><span class="sxs-lookup"><span data-stu-id="0e963-648">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="0e963-649">範例 1：</span><span class="sxs-lookup"><span data-stu-id="0e963-649">Example 1:</span></span>**

<span data-ttu-id="0e963-650">UE-V 發生器中指定的產品版本：1.0 會產生下列 XML：</span><span class="sxs-lookup"><span data-stu-id="0e963-650">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="0e963-651">範例 2：</span><span class="sxs-lookup"><span data-stu-id="0e963-651">Example 2:</span></span>**

<span data-ttu-id="0e963-652">檔版本： UE-V 發生器中指定的5.0.2.1000 會產生下列 XML：</span><span class="sxs-lookup"><span data-stu-id="0e963-652">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="0e963-653">不正確的範例1–不完整範圍：</span><span class="sxs-lookup"><span data-stu-id="0e963-653">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="0e963-654">只有最小屬性出現。</span><span class="sxs-lookup"><span data-stu-id="0e963-654">Only the Minimum attribute is present.</span></span> <span data-ttu-id="0e963-655">範圍中也必須包含最大值。</span><span class="sxs-lookup"><span data-stu-id="0e963-655">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="0e963-656">不正確的範例2–指定的次要元素沒有主要元素：</span><span class="sxs-lookup"><span data-stu-id="0e963-656">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="0e963-657">只有次要元素存在。</span><span class="sxs-lookup"><span data-stu-id="0e963-657">Only the Minor element is present.</span></span> <span data-ttu-id="0e963-658">還必須包含主要版本。</span><span class="sxs-lookup"><span data-stu-id="0e963-658">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="0e963-659">FileVersion</span><span class="sxs-lookup"><span data-stu-id="0e963-659">FileVersion</span></span>

**<span data-ttu-id="0e963-660">強制： False</span><span class="sxs-lookup"><span data-stu-id="0e963-660">Mandatory: False</span></span>**

**<span data-ttu-id="0e963-661">類型： String</span><span class="sxs-lookup"><span data-stu-id="0e963-661">Type: String</span></span>**

<span data-ttu-id="0e963-662">FileVersion 會區分已發佈應用程式的發行版本本，以及元件可執行檔的內部組建詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0e963-662">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="0e963-663">對於大多數商業應用程式而言，這些號碼是完全相同的。</span><span class="sxs-lookup"><span data-stu-id="0e963-663">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="0e963-664">在其他情況下，檔案的產品版本會指示檔案的一般版本識別，而檔案版本則表示檔案的特定組建（例如，修補程式或更新的情況）。</span><span class="sxs-lookup"><span data-stu-id="0e963-664">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="0e963-665">這會唯一識別檔案，而不會中斷偵測邏輯。</span><span class="sxs-lookup"><span data-stu-id="0e963-665">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="0e963-666">若要判斷特定可執行檔的產品版本和檔案版本，請以滑鼠右鍵按一下 Windows 資源管理器中的檔案，選取 [屬性]，然後按一下 [詳細資料] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0e963-666">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="0e963-667">包含應用程式的 FileVersion 元素可讓您更精確地微調偵測邏輯，但對於大部分的應用程式來說，不是必要的。</span><span class="sxs-lookup"><span data-stu-id="0e963-667">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="0e963-668">首先會選取 [ProductVersion] 元素設定，然後 FileVersion [已核取]。</span><span class="sxs-lookup"><span data-stu-id="0e963-668">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="0e963-669">您將會套用限制性較強的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-669">The more restrictive setting will apply.</span></span>

<span data-ttu-id="0e963-670">FileVersion 的子項目和語法規則與 ProductVersion 相同。</span><span class="sxs-lookup"><span data-stu-id="0e963-670">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a><span data-ttu-id="0e963-671">Application 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-671">Application Element</span></span>

<span data-ttu-id="0e963-672">應用程式是適用于特定應用程式的設定容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-672">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="0e963-673">它是下欄欄位/類型的集合。</span><span class="sxs-lookup"><span data-stu-id="0e963-673">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e963-674">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-674">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="0e963-675">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-675">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-676">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-676">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-677">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-677">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-678">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-678">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-679">如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-679">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-680">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-680">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-681">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-681">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-682">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-682">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-683">如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-683">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-684">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-684">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-685">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-685">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-686">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-686">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-687">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-687">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-688">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-688">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-689">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-689">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-690">版本</span><span class="sxs-lookup"><span data-stu-id="0e963-690">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-691">識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-691">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-692">如需詳細資訊，請參閱 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-692">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-693">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="0e963-693">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-694">控制是否將此範本與 Microsoft 帳戶搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0e963-694">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="0e963-695">如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-695">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-696">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="0e963-696">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-697">與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-697">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="0e963-698">如果您使用 Office 365 來同步處理設定，此範本會自動停用。</span><span class="sxs-lookup"><span data-stu-id="0e963-698">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-699">處理程序</span><span class="sxs-lookup"><span data-stu-id="0e963-699">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-700">一個或多個處理元素集合的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-700">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="0e963-701">如需詳細資訊，請參閱 <a href="#processes" data-raw-source="[Processes](#processes)"> 進程 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-701">For more information, see <a href="#processes" data-raw-source="[Processes](#processes)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-702">設定</span><span class="sxs-lookup"><span data-stu-id="0e963-702">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-703">適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-703">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-704">它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-704">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="0e963-705">如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-705">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a><span data-ttu-id="0e963-706">常見元素</span><span class="sxs-lookup"><span data-stu-id="0e963-706">Common Element</span></span>

<span data-ttu-id="0e963-707">[常用] 與應用程式元素類似，但它永遠與兩個或更多個應用程式元素相關聯。</span><span class="sxs-lookup"><span data-stu-id="0e963-707">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="0e963-708">[常見] 區段代表在這些應用程式實例之間共用的一組設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-708">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="0e963-709">它是下欄欄位/類型的集合。</span><span class="sxs-lookup"><span data-stu-id="0e963-709">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e963-710">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-710">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="0e963-711">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-711">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-712">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-712">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-713">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-713">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-714">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-714">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-715">如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-715">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-716">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-716">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-717">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-717">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-718">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-718">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-719">如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-719">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-720">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-720">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-721">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-721">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-722">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-722">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-723">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-723">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-724">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-724">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-725">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-725">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-726">版本</span><span class="sxs-lookup"><span data-stu-id="0e963-726">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-727">識別 [設定位置] 範本的版本，以進行系統管理追蹤變更。</span><span class="sxs-lookup"><span data-stu-id="0e963-727">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="0e963-728">如需詳細資訊，請參閱 <a href="#version" data-raw-source="[Version](#version)"> 版本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-728">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-729">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="0e963-729">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-730">控制是否將此範本與 Microsoft 帳戶搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0e963-730">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="0e963-731">如果已針對電腦上的使用者啟用 MSA 同步處理，則會自動停用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-731">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-732">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="0e963-732">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-733">與 MSA 類似，這會控制是否與 Office365 搭配使用此範本。</span><span class="sxs-lookup"><span data-stu-id="0e963-733">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="0e963-734">如果您使用 Office 365 來同步處理設定，此範本會自動停用。</span><span class="sxs-lookup"><span data-stu-id="0e963-734">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-735">設定</span><span class="sxs-lookup"><span data-stu-id="0e963-735">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-736">適用于特定範本之所有設定的容器。</span><span class="sxs-lookup"><span data-stu-id="0e963-736">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="0e963-737">它包含 Registry、File、SystemParameter 和 CustomAction 設定的實例。</span><span class="sxs-lookup"><span data-stu-id="0e963-737">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="0e963-738">如需詳細資訊，請參閱 <strong> </strong> 資料類型中的設定 <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-738">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a><span data-ttu-id="0e963-739">SettingsLocationTemplate 元素</span><span class="sxs-lookup"><span data-stu-id="0e963-739">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="0e963-740">這個元素定義單一應用程式或一套應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="0e963-740">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0e963-741">欄位/類型</span><span class="sxs-lookup"><span data-stu-id="0e963-741">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="0e963-742">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-742">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-743">Name</span><span class="sxs-lookup"><span data-stu-id="0e963-743">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-744">指定 [設定位置] 範本的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="0e963-744">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="0e963-745">這用於在 WMI、PowerShell、事件檢視器和調試記錄中參照範本時的顯示用途。</span><span class="sxs-lookup"><span data-stu-id="0e963-745">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="0e963-746">如需詳細資訊，請參閱 <a href="#name" data-raw-source="[Name](#name)"> Name </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-746">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-747">識別碼</span><span class="sxs-lookup"><span data-stu-id="0e963-747">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-748">填入特定範本的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-748">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="0e963-749">此標記會成為 UE-V Agent 在執行時間參考範本時所用的主要識別碼。</span><span class="sxs-lookup"><span data-stu-id="0e963-749">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="0e963-750">如需詳細資訊，請參閱 <a href="#id" data-raw-source="[ID](#id)"> 識別碼 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0e963-750">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-751">描述</span><span class="sxs-lookup"><span data-stu-id="0e963-751">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-752">範本的選用描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-752">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0e963-753">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="0e963-753">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-754">UI 中顯示的選擇性名稱，由語言地區設定當地語系化。</span><span class="sxs-lookup"><span data-stu-id="0e963-754">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0e963-755">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="0e963-755">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="0e963-756">依語言地區設定當地語系化的選用範本描述。</span><span class="sxs-lookup"><span data-stu-id="0e963-756">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a><span data-ttu-id="0e963-757">附錄： SettingsLocationTemplate</span><span class="sxs-lookup"><span data-stu-id="0e963-757">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="0e963-758">以下是 SettingsLocationTemplate 檔案，其中顯示其元素、子項目、屬性和參數：</span><span class="sxs-lookup"><span data-stu-id="0e963-758">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## <span data-ttu-id="0e963-759">相關主題</span><span class="sxs-lookup"><span data-stu-id="0e963-759">Related topics</span></span>


[<span data-ttu-id="0e963-760">使用自訂的 UE-V 2. x 範本和 UE-V 2. x 發電機</span><span class="sxs-lookup"><span data-stu-id="0e963-760">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[<span data-ttu-id="0e963-761">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="0e963-761">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





