---
title: OSD 檔案元素
description: OSD 檔案元素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800953"
---
# <span data-ttu-id="7f8ee-103">OSD 檔案元素</span><span class="sxs-lookup"><span data-stu-id="7f8ee-103">OSD File Elements</span></span>


<span data-ttu-id="7f8ee-104">Sequencer 安裝目錄包含 XML 架構檔案**Softricity （xsd**），該檔案定義開放式軟體描述項（OSD）檔案的有效結構。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-104">The Sequencer installation directory contains an XML schema file, **Softricity.xsd**, which defines the valid structure of an Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="7f8ee-105">以下是一些較頻繁使用的 OSD 元素。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-105">Following are some of the more frequently used OSD elements.</span></span>

<a href="" id="softpkg"></a><span data-ttu-id="7f8ee-106">SOFTPKG</span><span class="sxs-lookup"><span data-stu-id="7f8ee-106">SOFTPKG</span></span>  
<span data-ttu-id="7f8ee-107">OSD 檔案的根項目，內含定義軟體套件的所有元素。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-107">The root element of the OSD file containing all elements defining the software package.</span></span>

<a href="" id="codebase"></a><span data-ttu-id="7f8ee-108">基</span><span class="sxs-lookup"><span data-stu-id="7f8ee-108">CODEBASE</span></span>  
<span data-ttu-id="7f8ee-109">此套件的 sft 檔案相關資訊，包括 HREF、FILENAME 及 GUID 屬性。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-109">Information about the .sft file for this package, including the HREF, FILENAME, and GUID attributes.</span></span> <span data-ttu-id="7f8ee-110">如果您變更這個特定套件的發佈點，就可以編輯 HREF 屬性。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-110">You can edit the HREF attribute if you change the distribution point of this particular package.</span></span>

<a href="" id="os"></a><span data-ttu-id="7f8ee-111">作業系統</span><span class="sxs-lookup"><span data-stu-id="7f8ee-111">OS</span></span>  
<span data-ttu-id="7f8ee-112">根據最初在順序嚮導中設定的值，定義此應用程式可以執行的作業系統。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-112">Defines on what operating systems this application can run based on values that are initially set in the Sequencing Wizard.</span></span> <span data-ttu-id="7f8ee-113">這個值只能包含**Softricity**中定義的值。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-113">This value can contain only the values defined in **Softricity.xsd**.</span></span>

<a href="" id="local-interaction-allowed"></a><span data-ttu-id="7f8ee-114">本機 \ _INTERACTION \ _ALLOWED</span><span class="sxs-lookup"><span data-stu-id="7f8ee-114">LOCAL\_INTERACTION\_ALLOWED</span></span>  
<span data-ttu-id="7f8ee-115">如果設定為 TRUE，則可在全域命名空間中建立命名物件（事件、mutex、信號燈、檔案對應及 mailslots）和 COM 物件，而不是隔離在特定的虛擬環境中，這可讓虛擬應用程式與主機作業系統的應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-115">Set to TRUE, this enables creation of named objects (events, mutexes, semaphores, file mappings, and mailslots) and COM objects in the global namespace rather than isolated inside a particular virtual environment, which allows virtual applications to interact with the host operating system's applications.</span></span>

<span data-ttu-id="7f8ee-116">範例： &lt; SOFTPKG &gt; &lt; 實現&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-116">Example:&lt;SOFTPKG&gt;&lt;IMPLEMENTATION&gt;</span></span>

<span data-ttu-id="7f8ee-117">&lt;VIRTUALENV &gt; &lt; 原則&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-117">&lt;VIRTUALENV&gt;&lt;POLICIES&gt;</span></span>

<span data-ttu-id="7f8ee-118">&lt;本機 \ _INTERACTION \ _ALLOWED &gt; TRUE</span><span class="sxs-lookup"><span data-stu-id="7f8ee-118">&lt;LOCAL\_INTERACTION\_ALLOWED&gt;TRUE</span></span>

<span data-ttu-id="7f8ee-119">&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-119">&lt;/LOCAL\_INTERACTION\_ALLOWED&gt;</span></span>

<span data-ttu-id="7f8ee-120">&lt;/POLICIES &gt; &lt; /VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-120">&lt;/POLICIES&gt;&lt;/VIRTUALENV&gt;</span></span>

<span data-ttu-id="7f8ee-121">&lt;/IMPLEMENTATION &gt; &lt; /SOFTPKG&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-121">&lt;/IMPLEMENTATION&gt;&lt;/SOFTPKG&gt;</span></span>

<a href="" id="dependencies"></a><span data-ttu-id="7f8ee-122">因素</span><span class="sxs-lookup"><span data-stu-id="7f8ee-122">DEPENDENCIES</span></span>  
<span data-ttu-id="7f8ee-123">使用來自另一個套件的 CODEBASE 標記，定義動態套件組合（其他套件的相依性）。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-123">Defines Dynamic Suite Composition (dependencies on other packages) by using a CODEBASE tag from another package.</span></span>

<span data-ttu-id="7f8ee-124">範例：相依性 &lt; &gt; &lt; CODEBASE] HREF = "rtsps：//server/package.sft" GUID = "7579F4DF-2461-4219-BD43-494E1FDC69E3" SYSGUARDFILE = "installer.pkg. 1 \\ osguard. cp" SIZE = "6572748" 強制性 = "FALSE"/ &gt; &lt; /DEPENDENCIES&gt;</span><span class="sxs-lookup"><span data-stu-id="7f8ee-124">Example:&lt;DEPENDENCIES&gt;&lt;CODEBASE HREF="rtsps://server/package.sft" GUID="7579F4DF-2461-4219-BD43-494E1FDC69E3" SYSGUARDFILE="pkg.1\\osguard.cp" SIZE="6572748" MANDATORY="FALSE"/&gt;&lt;/DEPENDENCIES&gt;</span></span>

<a href="" id="package-name"></a><span data-ttu-id="7f8ee-125">套件名稱</span><span class="sxs-lookup"><span data-stu-id="7f8ee-125">PACKAGE NAME</span></span>  
<span data-ttu-id="7f8ee-126">在 [排序] 嚮導的 [**資訊**] 頁面中輸入之套件的通用名稱，可讓您指定單一名稱，以用於包含多個應用程式的順序化應用程式。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-126">A common name for the package entered into the Sequencing Wizard **Package Information** page, which enables you to specify a single name used for a sequenced application containing multiple applications.</span></span>

<a href="" id="title"></a><span data-ttu-id="7f8ee-127">職稱</span><span class="sxs-lookup"><span data-stu-id="7f8ee-127">TITLE</span></span>  
<span data-ttu-id="7f8ee-128">您正在排序之應用程式的選用描述名稱。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-128">Optional descriptive name of the application you are sequencing.</span></span>

<a href="" id="abstract"></a><span data-ttu-id="7f8ee-129">概要</span><span class="sxs-lookup"><span data-stu-id="7f8ee-129">ABSTRACT</span></span>  
<span data-ttu-id="7f8ee-130">在排序嚮導**封裝資訊**頁面的 [**批註**] 欄位中輸入之軟體套件的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-130">Short description of the software package entered in the **Comments** field in the Sequencing Wizard **Package Information** page.</span></span> <span data-ttu-id="7f8ee-131">最佳做法是指定諸如作業系統與服務套件層級、Sequencer 版本及排序工程工程名稱等資訊。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-131">A best practice is to specify information such as the operating system and service-pack level of the Sequencer workstation, Sequencer version, and the sequencing engineer’s name.</span></span>

<a href="" id="script"></a><span data-ttu-id="7f8ee-132">腳本</span><span class="sxs-lookup"><span data-stu-id="7f8ee-132">SCRIPT</span></span>  
<span data-ttu-id="7f8ee-133">定義啟動、關閉或資料流程期間發生的特定腳本事件。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-133">Defines specific scripted events to occur during startup, shutdown, or streaming.</span></span>

<a href="" id="mgmt-shortcutlist"></a><span data-ttu-id="7f8ee-134">管理 \ _SHORTCUTLIST</span><span class="sxs-lookup"><span data-stu-id="7f8ee-134">MGMT\_SHORTCUTLIST</span></span>  
<span data-ttu-id="7f8ee-135">在嚮導中定義的所有快速鍵清單。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-135">List of all shortcuts defined in the wizard.</span></span>

<a href="" id="mgmt-fileassociations"></a><span data-ttu-id="7f8ee-136">管理 \ _FILEASSOCIATIONS</span><span class="sxs-lookup"><span data-stu-id="7f8ee-136">MGMT\_FILEASSOCIATIONS</span></span>  
<span data-ttu-id="7f8ee-137">在嚮導中指定的檔案類型清單。</span><span class="sxs-lookup"><span data-stu-id="7f8ee-137">List of the file types specified in the wizard.</span></span>

## <span data-ttu-id="7f8ee-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f8ee-138">Related topics</span></span>


[<span data-ttu-id="7f8ee-139">關於 OSD 索引標籤</span><span class="sxs-lookup"><span data-stu-id="7f8ee-139">About the OSD Tab</span></span>](about-the-osd-tab.md)

 

 





