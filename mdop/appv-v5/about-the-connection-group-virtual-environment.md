---
title: 關於連線群組虛擬環境
description: 關於連線群組虛擬環境
author: dansimp
ms.assetid: 535fa640-cbd9-425e-8437-94650a70c264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bd93c9e7acbf7bbf3f9da506d5d95b8df09e1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800711"
---
# <span data-ttu-id="f3ffa-103">關於連線群組虛擬環境</span><span class="sxs-lookup"><span data-stu-id="f3ffa-103">About the Connection Group Virtual Environment</span></span>


**<span data-ttu-id="f3ffa-104">本主題內容如下：</span><span class="sxs-lookup"><span data-stu-id="f3ffa-104">In this topic:</span></span>**

-   [<span data-ttu-id="f3ffa-105">如何決定封裝優先順序</span><span class="sxs-lookup"><span data-stu-id="f3ffa-105">How package priority is determined</span></span>](#bkmk-pkg-priority-deter)

-   [<span data-ttu-id="f3ffa-106">將相同的套件路徑合併成連接群組中的一個虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="f3ffa-106">Merging identical package paths into one virtual directory in connection groups</span></span>](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a><span data-ttu-id="f3ffa-107">如何決定封裝優先順序</span><span class="sxs-lookup"><span data-stu-id="f3ffa-107">How package priority is determined</span></span>


<span data-ttu-id="f3ffa-108">虛擬環境及其目前狀態會與連線群組相關聯，而不會與個別套件建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-108">The virtual environment and its current state are associated with the connection group, not with the individual packages.</span></span> <span data-ttu-id="f3ffa-109">如果從連線群組中移除 App-v 套件，則在連線群組中存在的狀態將不會與套件一起遷移。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-109">If an App-V package is removed from the connection group, the state that existed as part of the connection group will not migrate with the package.</span></span>

<span data-ttu-id="f3ffa-110">如果同一個套件是兩個不同連線群組的一部分，您必須指出應該使用哪個連線群組 App。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-110">If the same package is a part of two different connection groups, you have to indicate which connection group App-V should use.</span></span> <span data-ttu-id="f3ffa-111">例如，您可能會在連線群組中有兩個套件，每個套件都定義相同的登錄 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-111">For example, you might have two packages in a connection group that each define the same registry DWORD value.</span></span>

<span data-ttu-id="f3ffa-112">所使用的連線群組是依據套件在**AppConnectionGroup** XML 檔中出現的順序所決定：</span><span class="sxs-lookup"><span data-stu-id="f3ffa-112">The connection group that is used is based on the order in which a package appears inside the **AppConnectionGroup** XML document:</span></span>

-   <span data-ttu-id="f3ffa-113">第一個套件的優先順序最高。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-113">The first package has the highest precedence.</span></span>

-   <span data-ttu-id="f3ffa-114">第二個套件的優先順序最高。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-114">The second package has the second highest precedence.</span></span>

<span data-ttu-id="f3ffa-115">請考慮下列範例區段：</span><span class="sxs-lookup"><span data-stu-id="f3ffa-115">Consider the following example section:</span></span>

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

<span data-ttu-id="f3ffa-116">假設在第一個和第三個套件中定義了相同的 DWORD 值 ABC （HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region），例如：</span><span class="sxs-lookup"><span data-stu-id="f3ffa-116">Assume that same DWORD value ABC (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region) is defined in the first and third package, such as:</span></span>

-   <span data-ttu-id="f3ffa-117">套件1（A8731008-4523-4713-83A4-CD1363907160）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5</span><span class="sxs-lookup"><span data-stu-id="f3ffa-117">Package 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5</span></span>

-   <span data-ttu-id="f3ffa-118">套件3（04220DCA-EE77-42BE-A9F5-96FD8E8593F2）： HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10</span><span class="sxs-lookup"><span data-stu-id="f3ffa-118">Package 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=10</span></span>

<span data-ttu-id="f3ffa-119">由於套件1會先出現，所以 AppConnectionGroup 的虛擬環境會將單一 DWORD 值為5（HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5）。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-119">Since Package 1 appears first, the AppConnectionGroup's virtual environment will have the single DWORD value of 5 (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5).</span></span> <span data-ttu-id="f3ffa-120">這表示套件1、套件2和套件3中的虛擬應用程式在查詢 HKEY \ _LOCAL 時，會看到值 5 _MACHINE \\software\\contoso\\finapp\\region。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-120">This means that the virtual applications in Package 1, Package 2, and Package 3 will all see the value 5 when they query for HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region.</span></span>

<span data-ttu-id="f3ffa-121">其他虛擬環境資源的解決方式類似，但一般情況下，會發生衝突。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-121">Other virtual environment resources are resolved similarly, but the usual case is that the collisions occur in the registry.</span></span>

## <a href="" id="bkmk-merged-root-ve-exp"></a><span data-ttu-id="f3ffa-122">將相同的套件路徑合併成連接群組中的一個虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="f3ffa-122">Merging identical package paths into one virtual directory in connection groups</span></span>


<span data-ttu-id="f3ffa-123">如果連線群組中有兩個以上的套件包含完全相同的目錄路徑，則會將這些路徑合併到連線群組虛擬環境內的單一虛擬目錄中。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-123">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span> <span data-ttu-id="f3ffa-124">這種路徑合併可讓一個套件中的應用程式存取不同套件中的檔案。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-124">This merging of paths allows an application in one package to access files that are in a different package.</span></span>

<span data-ttu-id="f3ffa-125">當您從連線群組中移除套件時，已移除套件中的應用程式將無法再存取連線群組中其餘套件中的檔案。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-125">When you remove a package from a connection group, the applications in that removed package are no longer able to access files in the remaining packages in the connection group.</span></span>

<span data-ttu-id="f3ffa-126">App V 在連線群組中尋找檔案名稱的順序，是由在連線群組資訊清單檔案中所列的 app-v 套件順序來指定。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-126">The order in which App-V looks up a file’s name in the connection group is specified by the order in which the App-V packages are listed in the connection group manifest file.</span></span>

<span data-ttu-id="f3ffa-127">下列範例顯示 [**封裝 a** ] 與 [**封裝 B**] 的 [連線] 群組中的檔案名查閱順序與關聯性。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-127">The following example shows the order and relationship of a file name lookup in a connection group for **Package A** and **Package B**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f3ffa-128">封裝 A</span><span class="sxs-lookup"><span data-stu-id="f3ffa-128">Package A</span></span></th>
<th align="left"><span data-ttu-id="f3ffa-129">套件 B</span><span class="sxs-lookup"><span data-stu-id="f3ffa-129">Package B</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f3ffa-130">C:\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="f3ffa-130">C:\Windows\System32</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3ffa-131">C:\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="f3ffa-131">C:\Windows\System32</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f3ffa-132">C:\AppTest</span><span class="sxs-lookup"><span data-stu-id="f3ffa-132">C:\AppTest</span></span></p></td>
<td align="left"><p><span data-ttu-id="f3ffa-133">C:\AppTest</span><span class="sxs-lookup"><span data-stu-id="f3ffa-133">C:\AppTest</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f3ffa-134">在上述範例中，當虛擬化的應用程式嘗試尋找特定檔案時，會先搜尋封裝 A，以取得相符的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-134">In the example above, when a virtualized application tries to find a specific file, Package A is searched first for a matching file path.</span></span> <span data-ttu-id="f3ffa-135">如果找不到相符路徑，則會使用下列對應規則搜尋封裝 B：</span><span class="sxs-lookup"><span data-stu-id="f3ffa-135">If a matching path is not found, Package B is searched, using the following mapping rules:</span></span>

-   <span data-ttu-id="f3ffa-136">如果在兩個應用程式套件的同一個虛擬資料夾階層中都存在名為**test.txt**的檔案，則會使用第一個相符的檔案。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-136">If a file named **test.txt** exists in the same virtual folder hierarchy in both application packages, the first matching file is used.</span></span>

-   <span data-ttu-id="f3ffa-137">如果一個名為**bar.txt**的檔案存在於一個應用程式套件的虛擬資料夾階層中，而不在另一個，則會使用第一個相符的檔案。</span><span class="sxs-lookup"><span data-stu-id="f3ffa-137">If a file named **bar.txt** exists in the virtual folder hierarchy of one application package, but not in the other, the first matching file is used.</span></span>






## <span data-ttu-id="f3ffa-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="f3ffa-138">Related topics</span></span>


[<span data-ttu-id="f3ffa-139">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="f3ffa-139">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





