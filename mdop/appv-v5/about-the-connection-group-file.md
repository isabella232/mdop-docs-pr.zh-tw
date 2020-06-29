---
title: 關於連線群組檔案
description: 關於連線群組檔案
author: dansimp
ms.assetid: bfeb6013-a7ca-4e36-9fe3-229702e83f0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5e5cb93326ce182d71de0f0f89cc569823d6154e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800717"
---
# <span data-ttu-id="86003-103">關於連線群組檔案</span><span class="sxs-lookup"><span data-stu-id="86003-103">About the Connection Group File</span></span>


**<span data-ttu-id="86003-104">本主題內容如下：</span><span class="sxs-lookup"><span data-stu-id="86003-104">In this topic:</span></span>**

-   [<span data-ttu-id="86003-105">連線群組檔案用途和位置</span><span class="sxs-lookup"><span data-stu-id="86003-105">Connection group file purpose and location</span></span>](#bkmk-cg-purpose-loc)

-   [<span data-ttu-id="86003-106">連線群組 XML 檔案的結構</span><span class="sxs-lookup"><span data-stu-id="86003-106">Structure of the connection group XML file</span></span>](#bkmk-define-cg-5-0sp3)

-   [<span data-ttu-id="86003-107">在連線群組中設定套件的優先順序</span><span class="sxs-lookup"><span data-stu-id="86003-107">Configuring the priority of packages in a connection group</span></span>](#bkmk-config-pkg-priority-incg)

-   [<span data-ttu-id="86003-108">支援的虛擬應用程式連線設定</span><span class="sxs-lookup"><span data-stu-id="86003-108">Supported virtual application connection configurations</span></span>](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a><span data-ttu-id="86003-109">連線群組檔案用途和位置</span><span class="sxs-lookup"><span data-stu-id="86003-109">Connection group file purpose and location</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-110">連線群組用途</span><span class="sxs-lookup"><span data-stu-id="86003-110">Connection group purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-111">連線群組是一個 App-v 功能，可讓您將套件組成群組，以建立虛擬環境，讓這些套件中的應用程式可以彼此互動。</span><span class="sxs-lookup"><span data-stu-id="86003-111">A connection group is an App-V feature that enables you to group packages together to create a virtual environment in which the applications in those packages can interact with each other.</span></span></p>
<p><span data-ttu-id="86003-112">範例：您想要在 Microsoft Office 中使用外掛程式。</span><span class="sxs-lookup"><span data-stu-id="86003-112">Example: You want to use plug-ins with Microsoft Office.</span></span> <span data-ttu-id="86003-113">您可以建立包含外掛程式的套件，並建立包含 Office 的另一個套件，然後將這兩個套件新增到連線群組，以讓 Office 使用這些外掛程式。</span><span class="sxs-lookup"><span data-stu-id="86003-113">You can create a package that contains the plug-ins, and create another package that contains Office, and then add both packages to a connection group to enable Office to use those plug-ins.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-114">連線群組檔案的運作方式</span><span class="sxs-lookup"><span data-stu-id="86003-114">How the connection group file works</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-115">當您套用 Application Virtualization 5.0 連線群組檔案時，會在執行時間將在檔案中列舉的套件合併成單一虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="86003-115">When you apply an Application Virtualization 5.0 connection group file, the packages that are enumerated in the file will be combined at runtime into a single virtual environment.</span></span> <span data-ttu-id="86003-116">使用 Microsoft Application Virtualization （App-v）5.0 連線群組檔案來設定現有的 Application Virtualization 5.0 連線群組。</span><span class="sxs-lookup"><span data-stu-id="86003-116">Use the Microsoft Application Virtualization (App-V) 5.0 connection group file to configure existing Application Virtualization 5.0 connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-117">範例檔路徑</span><span class="sxs-lookup"><span data-stu-id="86003-117">Example file path</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED-92D5-8910A8527F96}。</span><span class="sxs-lookup"><span data-stu-id="86003-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups{6CCC7575-162E-4152-9407-ED411DA138F4}{4D1E16E1-8EF8-41ED-92D5-8910A8527F96}.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a><span data-ttu-id="86003-119">連線群組 XML 檔案的結構</span><span class="sxs-lookup"><span data-stu-id="86003-119">Structure of the connection group XML file</span></span>


**<span data-ttu-id="86003-120">本節內容：</span><span class="sxs-lookup"><span data-stu-id="86003-120">In this section:</span></span>**

-   [<span data-ttu-id="86003-121">定義連接群組的參數</span><span class="sxs-lookup"><span data-stu-id="86003-121">Parameters that define the connection group</span></span>](#bkmk-params-define-cg)

-   [<span data-ttu-id="86003-122">在連線群組中定義套件的參數</span><span class="sxs-lookup"><span data-stu-id="86003-122">Parameters that define the packages in the connection group</span></span>](#bkmk-params-define-pkgs-incg)

-   [<span data-ttu-id="86003-123">App-V 5.0 SP3 範例連線群組 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="86003-123">App-V 5.0 SP3 example connection group XML file</span></span>](#bkmk-50sp3-exp-cg-xml)

-   [<span data-ttu-id="86003-124">App-v 5.0 透過 App-V 5.0 SP2 範例連線群組 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="86003-124">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a><span data-ttu-id="86003-125">定義連接群組的參數</span><span class="sxs-lookup"><span data-stu-id="86003-125">Parameters that define the connection group</span></span>

<span data-ttu-id="86003-126">下表說明 XML 檔案中定義連線群組本身（而非套件）的參數。</span><span class="sxs-lookup"><span data-stu-id="86003-126">The following table describes the parameters in the XML file that define the connection group itself, not the packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86003-127">欄位</span><span class="sxs-lookup"><span data-stu-id="86003-127">Field</span></span></th>
<th align="left"><span data-ttu-id="86003-128">描述</span><span class="sxs-lookup"><span data-stu-id="86003-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-129">架構名稱</span><span class="sxs-lookup"><span data-stu-id="86003-129">Schema name</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-130">架構的名稱。</span><span class="sxs-lookup"><span data-stu-id="86003-130">Name of the schema.</span></span></p>
<p><strong><span data-ttu-id="86003-131">適用于 App-v 5.0 SP3 </strong> ：如果您想要使用此表格中所述的新 [選用套件] 和「使用任何版本」功能，您必須在 XML 檔案中指定下列架構：</span><span class="sxs-lookup"><span data-stu-id="86003-131">Applicable starting in App-V 5.0 SP3</strong>: If you want to use the new “optional packages” and “use any version” features that are described in this table, you must specify the following schema in the XML file:</span></span></p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-132">AppConnectionGroupId</span><span class="sxs-lookup"><span data-stu-id="86003-132">AppConnectionGroupId</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-133">這個連線群組的唯一 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="86003-133">Unique GUID identifier for this connection group.</span></span> <span data-ttu-id="86003-134">連線群組狀態與此識別碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="86003-134">The connection group state is associated with this identifier.</span></span> <span data-ttu-id="86003-135">只有在建立連線群組時，才能指定此識別碼。</span><span class="sxs-lookup"><span data-stu-id="86003-135">Specify this identifier only when you create the connection group.</span></span></p>
<p><span data-ttu-id="86003-136">您可以輸入以下內容來建立新的 GUID： <strong>[Guid]::NewGuid()</strong> 。</span><span class="sxs-lookup"><span data-stu-id="86003-136">You can create a new GUID by typing: <strong>[Guid]::NewGuid()</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-137">VersionId</span><span class="sxs-lookup"><span data-stu-id="86003-137">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-138">此版本的連線群組的版本 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="86003-138">Version GUID identifier for this version of the connection group.</span></span></p>
<p><span data-ttu-id="86003-139">當您更新連線群組時（例如，新增或更新新的套件），您必須更新版本 GUID 以反映新版本。</span><span class="sxs-lookup"><span data-stu-id="86003-139">When you update a connection group (for example, by adding or updating a new package), you must update the version GUID to reflect the new version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-140">DisplayName</span><span class="sxs-lookup"><span data-stu-id="86003-140">DisplayName</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-141">[連線] 群組的 [顯示名稱]。</span><span class="sxs-lookup"><span data-stu-id="86003-141">Display name of the connection group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-142">優先順序</span><span class="sxs-lookup"><span data-stu-id="86003-142">Priority</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-143">[連接] 群組的 [選用優先順序] 欄位。</span><span class="sxs-lookup"><span data-stu-id="86003-143">Optional priority field for the connection group.</span></span></p>
<p><strong><span data-ttu-id="86003-144">"0" </strong> - 表示最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-144">“0”</strong> - indicates the highest priority.</span></span></p>
<p><span data-ttu-id="86003-145">如果需要優先順序，但尚未進行設定，則由於無法決定要使用的正確連線群組，套件將會失敗。</span><span class="sxs-lookup"><span data-stu-id="86003-145">If a priority is required, but has not been configured, the package will fail because the correct connection group to use cannot be determined.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a><span data-ttu-id="86003-146">在連線群組中定義套件的參數</span><span class="sxs-lookup"><span data-stu-id="86003-146">Parameters that define the packages in the connection group</span></span>

<span data-ttu-id="86003-147">在連線 &lt; 群組 XML 檔案的 [套件] &gt; 區段中，您可以指定每個套件的唯一套件識別碼與版本識別碼，以列出連接群組中的成員套件，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="86003-147">In the &lt;Packages&gt; section of the connection group XML file, you list the member packages in the connection group by specifying each package’s unique package identifier and version identifier, as described in the following table.</span></span> <span data-ttu-id="86003-148">清單中的第一個套件具有最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-148">The first package in the list has the highest precedence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86003-149">欄位</span><span class="sxs-lookup"><span data-stu-id="86003-149">Field</span></span></th>
<th align="left"><span data-ttu-id="86003-150">描述</span><span class="sxs-lookup"><span data-stu-id="86003-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-151">PackageId</span><span class="sxs-lookup"><span data-stu-id="86003-151">PackageId</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-152">此套件的唯一 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="86003-152">Unique GUID identifier for this package.</span></span> <span data-ttu-id="86003-153">發佈更新版本的套件時，此 GUID 不會變更。</span><span class="sxs-lookup"><span data-stu-id="86003-153">This GUID doesn’t change when newer versions of the package are published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-154">VersionId</span><span class="sxs-lookup"><span data-stu-id="86003-154">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-155">套件版本的唯一 GUID 識別碼。</span><span class="sxs-lookup"><span data-stu-id="86003-155">Unique GUID identifier for the version of the package.</span></span></p>
<p><strong><span data-ttu-id="86003-156">適用于 App-v 5.0 SP3 </strong> ：如果您指定 [ <strong> \*] </strong> 做為套件版本，則會動態插入最新可用套件版本的 GUID。</span><span class="sxs-lookup"><span data-stu-id="86003-156">Applicable starting in App-V 5.0 SP3</strong>: If you specify <strong>“\*”</strong> for the package version, the GUID of the latest available package version is dynamically inserted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-157">IsOptional</span><span class="sxs-lookup"><span data-stu-id="86003-157">IsOptional</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="86003-158">適用于 App-V 5.0 SP3 </strong> ：參數，可讓您在連線群組中將套件設為選用。</span><span class="sxs-lookup"><span data-stu-id="86003-158">Applicable starting in App-V 5.0 SP3</strong>: Parameter that enables you to make a package optional within the connection group.</span></span> <span data-ttu-id="86003-159">有效的專案為：</span><span class="sxs-lookup"><span data-stu-id="86003-159">Valid entries are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="86003-160">"true" </strong> – [連線] 群組中的 [套件] 是選擇性的</span><span class="sxs-lookup"><span data-stu-id="86003-160">“true”</strong> – package is optional in the connection group</span></span></p></li>
<li><p><strong><span data-ttu-id="86003-161">"false" </strong> –在連線群組中需要套件</span><span class="sxs-lookup"><span data-stu-id="86003-161">“false”</strong> – package is required in the connection group</span></span></p></li>
</ul>
<p><span data-ttu-id="86003-162">瞭解 <a href="how-to-use-optional-packages-in-connection-groups.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md)"> 如何在連線群組中使用選用套件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="86003-162">See <a href="how-to-use-optional-packages-in-connection-groups.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md)">How to Use Optional Packages in Connection Groups</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a><span data-ttu-id="86003-163">App-V 5.0 SP3 範例連線群組 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="86003-163">App-V 5.0 SP3 example connection group XML file</span></span>

<span data-ttu-id="86003-164">下列範例連線群組 XML 檔案會顯示先前表格中的欄位範例，並醒目提示 App-V 5.0 SP3 的新專案。</span><span class="sxs-lookup"><span data-stu-id="86003-164">The following example connection group XML file shows examples of the fields in the previous tables and highlights the items that are new for App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16"?>
<appv:AppConnectionGroup 
   xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
   xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
   AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
   VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"  
   Priority="0"  
   DisplayName="Sample Connection Group">
   <appv:Packages>
      <appv:Package      
         PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
         VersionId="*"
         IsOptional=”true”
      />    
     <appv:Package
        PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
        VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
        IsOptional="false"
     />  
   </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a><span data-ttu-id="86003-165">App-v 5.0 透過 App-V 5.0 SP2 範例連線群組 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="86003-165">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>

<span data-ttu-id="86003-166">下列範例連線群組 XML 檔案是透過 App-V 5.0 SP2 套用至 App-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="86003-166">The following example connection group XML file applies to App-V 5.0 through App-V 5.0 SP2.</span></span> <span data-ttu-id="86003-167">它會顯示上表中的欄位範例，但不會排除上述 App-v 5.0 SP3 所述的變更。</span><span class="sxs-lookup"><span data-stu-id="86003-167">It shows examples of the fields in the previous table, but it excludes the changes described above for App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16"?>
<appv:AppConnectionGroup
   xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
   xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
   AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
   VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
   Priority="0"
   DisplayName="Sample Connection Group">
   <appv:Packages>
      <appv:Package``      
         PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
         VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
      />
      <appv:Package
         PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
         VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      />
   </appv:Packages>
</appv:AppConnectionGroup
 ```

## <a href="" id="bkmk-config-pkg-priority-incg"></a><span data-ttu-id="86003-168">在連線群組中設定套件的優先順序</span><span class="sxs-lookup"><span data-stu-id="86003-168">Configuring the priority of packages in a connection group</span></span>


<span data-ttu-id="86003-169">封裝優先順序是使用套件清單順序設定。</span><span class="sxs-lookup"><span data-stu-id="86003-169">Package precedence is configured using the package list order.</span></span> <span data-ttu-id="86003-170">檔中的第一個套件具有最高優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-170">The first package in the document has the highest precedence.</span></span> <span data-ttu-id="86003-171">清單中的後續套件具有遞減優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-171">Subsequent packages in the list have descending priority.</span></span>

<span data-ttu-id="86003-172">封裝優先順序是在虛擬環境初始化期間因應避免的資源碰撞問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="86003-172">Package precedence is the resolution for otherwise inevitable resource collisions during virtual environment initialization.</span></span> <span data-ttu-id="86003-173">例如，如果在同一個虛擬環境中開啟的兩個套件定義相同的登錄 DWORD 值，則具有最高優先順序的套件會決定所設定的值。</span><span class="sxs-lookup"><span data-stu-id="86003-173">For example, if two packages that are opening in the same virtual environment define the same registry DWORD value, the package with the highest precedence determines the value that is set.</span></span>

<span data-ttu-id="86003-174">您可以使用下列方法，使用連線群組檔案來設定每個連接群組：</span><span class="sxs-lookup"><span data-stu-id="86003-174">You can use the connection group file to configure each connection group by using the following methods:</span></span>

-   <span data-ttu-id="86003-175">指定連線群組的執行時間優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-175">Specify runtime priorities for connection groups.</span></span>

    <span data-ttu-id="86003-176">**記事** 只有當套件與一個以上的連線群組相關聯時，才需要優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-176">**Note** Priority is required only if the package is associated with more than one connection group.</span></span>

     

-   <span data-ttu-id="86003-177">在連線群組中指定套件優先順序。</span><span class="sxs-lookup"><span data-stu-id="86003-177">Specify package precedence within the connection group.</span></span>

<span data-ttu-id="86003-178">如果正在執行的虛擬應用程式是從原生應用程式要求（例如，Microsoft Windows Explorer）啟動時，[優先順序] 欄位是必要的。</span><span class="sxs-lookup"><span data-stu-id="86003-178">The priority field is required when a running virtual application initiates from a native application request, for example, Microsoft Windows Explorer.</span></span> <span data-ttu-id="86003-179">App-v 用戶端會使用優先順序來判斷應用程式應該在哪個連線群組虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="86003-179">The App-V client uses the priority to determine which connection group virtual environment the application should run in.</span></span> <span data-ttu-id="86003-180">如果虛擬應用程式是多個連線群組的一部分，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="86003-180">This situation occurs if a virtual application is part of multiple connection groups.</span></span>

<span data-ttu-id="86003-181">如果虛擬應用程式是使用另一個虛擬應用程式開啟，則會使用原始虛擬應用程式的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="86003-181">If a virtual application is opened using another virtual application the virtual environment of the original virtual application will be used.</span></span> <span data-ttu-id="86003-182">在這種情況下，不會使用 [優先順序] 欄位。</span><span class="sxs-lookup"><span data-stu-id="86003-182">The priority field is not used in this case.</span></span>

**<span data-ttu-id="86003-183">範例：</span><span class="sxs-lookup"><span data-stu-id="86003-183">Example:</span></span>**

<span data-ttu-id="86003-184">Microsoft Outlook 正在虛擬環境**XYZ**中執行的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="86003-184">The virtual application Microsoft Outlook is running in virtual environment **XYZ**.</span></span> <span data-ttu-id="86003-185">當您開啟附加的 Microsoft Word 檔時，無論虛擬化 Microsoft Word 的關聯連線群組或執行時間優先順序為何，在虛擬環境**XYZ**中都會開啟虛擬化版本 microsoft word。</span><span class="sxs-lookup"><span data-stu-id="86003-185">When you open an attached Microsoft Word document, a virtualized version Microsoft Word opens in the virtual environment **XYZ**, regardless of the virtualized Microsoft Word’s associated connection groups or runtime priorities.</span></span>

## <a href="" id="bkmk-va-conn-configs"></a><span data-ttu-id="86003-186">支援的虛擬應用程式連線設定</span><span class="sxs-lookup"><span data-stu-id="86003-186">Supported virtual application connection configurations</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86003-187">設定</span><span class="sxs-lookup"><span data-stu-id="86003-187">Configuration</span></span></th>
<th align="left"><span data-ttu-id="86003-188">範例案例</span><span class="sxs-lookup"><span data-stu-id="86003-188">Example scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-189">將.</span><span class="sxs-lookup"><span data-stu-id="86003-189">An.</span></span> <span data-ttu-id="86003-190">exe 檔案和外掛程式（.dll）</span><span class="sxs-lookup"><span data-stu-id="86003-190">exe file and plug-in (.dll)</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="86003-191">您想要將 Microsoft Office 發佈給所有使用者，但只將 Microsoft Excel 外掛程式發佈至使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="86003-191">You want to distribute Microsoft Office to all users, but distribute a Microsoft Excel plug-in to only a subset of users.</span></span></p></li>
<li><p><span data-ttu-id="86003-192">針對適當的使用者啟用 [連接] 群組。</span><span class="sxs-lookup"><span data-stu-id="86003-192">Enable the connection group for the appropriate users.</span></span></p></li>
<li><p><span data-ttu-id="86003-193">根據需要逐一更新每個套件。</span><span class="sxs-lookup"><span data-stu-id="86003-193">Update each package individually as required.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-194">將.</span><span class="sxs-lookup"><span data-stu-id="86003-194">An.</span></span> <span data-ttu-id="86003-195">exe 檔案和中介軟體應用程式</span><span class="sxs-lookup"><span data-stu-id="86003-195">exe file and a middleware application</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="86003-196">您的應用程式需要一個中介軟體應用程式，或多個應用程式，它們都依賴同一個中介軟體執行時間版本。</span><span class="sxs-lookup"><span data-stu-id="86003-196">You have an application requires a middleware application, or several applications that all depend on the same middleware runtime version.</span></span></p></li>
<li><p><span data-ttu-id="86003-197">所有需要一或多個應用程式的電腦會透過應用程式和中介軟體應用程式執行時間來接收連接群組。</span><span class="sxs-lookup"><span data-stu-id="86003-197">All computers that require one or more of the applications receive the connection groups with the application and middleware application runtime.</span></span></p></li>
<li><p><span data-ttu-id="86003-198">您可以選擇性地將多個中介軟體應用程式合併成單一連線群組。</span><span class="sxs-lookup"><span data-stu-id="86003-198">You can optionally combine multiple middleware applications into a single connection group.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86003-199">範例</span><span class="sxs-lookup"><span data-stu-id="86003-199">Example</span></span></th>
<th align="left"><span data-ttu-id="86003-200">範例描述</span><span class="sxs-lookup"><span data-stu-id="86003-200">Example description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-201">財務部門的虛擬應用程式連線群組</span><span class="sxs-lookup"><span data-stu-id="86003-201">Virtual application connection group for the financial division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="86003-202">中介軟體應用程式1</span><span class="sxs-lookup"><span data-stu-id="86003-202">Middleware application 1</span></span></p></li>
<li><p><span data-ttu-id="86003-203">中介軟體應用程式2</span><span class="sxs-lookup"><span data-stu-id="86003-203">Middleware application 2</span></span></p></li>
<li><p><span data-ttu-id="86003-204">中介軟體應用程式3</span><span class="sxs-lookup"><span data-stu-id="86003-204">Middleware application 3</span></span></p></li>
<li><p><span data-ttu-id="86003-205">中介軟體應用程式執行時間</span><span class="sxs-lookup"><span data-stu-id="86003-205">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86003-206">人力資源部門的虛擬應用程式連線群組</span><span class="sxs-lookup"><span data-stu-id="86003-206">Virtual application connection group for HR division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="86003-207">中介軟體應用程式5</span><span class="sxs-lookup"><span data-stu-id="86003-207">Middleware application 5</span></span></p></li>
<li><p><span data-ttu-id="86003-208">中介軟體應用程式6</span><span class="sxs-lookup"><span data-stu-id="86003-208">Middleware application 6</span></span></p></li>
<li><p><span data-ttu-id="86003-209">中介軟體應用程式執行時間</span><span class="sxs-lookup"><span data-stu-id="86003-209">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86003-210">將.</span><span class="sxs-lookup"><span data-stu-id="86003-210">An.</span></span> <span data-ttu-id="86003-211">exe 檔和 .exe 檔案</span><span class="sxs-lookup"><span data-stu-id="86003-211">exe file and an .exe file</span></span></p></td>
<td align="left"><p><span data-ttu-id="86003-212">您有一個依賴另一個應用程式的應用程式，而您想要將套件保持在運作效率、授許可權制或推出時間範圍之外。</span><span class="sxs-lookup"><span data-stu-id="86003-212">You have an application that relies on another application, and you want to keep the packages separate for operational efficiencies, licensing restrictions, or rollout timelines.</span></span></p>
<p><strong><span data-ttu-id="86003-213">範例：</span><span class="sxs-lookup"><span data-stu-id="86003-213">Example:</span></span></strong></p>
<p><span data-ttu-id="86003-214">如果您要部署 Microsoft Lync 2010，您可以使用三個套件：</span><span class="sxs-lookup"><span data-stu-id="86003-214">If you are deploying Microsoft Lync 2010, you can use three packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="86003-215">Microsoft Office2010</span><span class="sxs-lookup"><span data-stu-id="86003-215">Microsoft Office2010</span></span></p></li>
<li><p><span data-ttu-id="86003-216">Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="86003-216">Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="86003-217">Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="86003-217">Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="86003-218">您可以使用下列連線群組來管理部署：</span><span class="sxs-lookup"><span data-stu-id="86003-218">You can manage the deployment using the following connection groups:</span></span></p>
<ul>
<li><p><span data-ttu-id="86003-219">Microsoft Office2010 和 Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="86003-219">Microsoft Office2010 and Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="86003-220">Microsoft Office2010 和 Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="86003-220">Microsoft Office2010 and Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="86003-221">部署完成後，您可以建立單一的 Microsoft Office2010 + Microsoft Lync2010 套件，或保留並維護它們為個別套件，然後使用連線群組進行部署。</span><span class="sxs-lookup"><span data-stu-id="86003-221">When the deployment has completed, you can either create a single new Microsoft Office2010 + Microsoft Lync2010 package, or keep and maintain them as separate packages and deploy them by using a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="86003-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="86003-222">Related topics</span></span>


[<span data-ttu-id="86003-223">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="86003-223">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





