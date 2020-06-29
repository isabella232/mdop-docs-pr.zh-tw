---
title: 如何使用動態套件組合
description: 如何使用動態套件組合
author: dansimp
ms.assetid: 24147feb-a0a8-4791-a8e5-cbe5fe13c762
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bff4c9721352785cf6db5c497234ceaa3c5e448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801015"
---
# <span data-ttu-id="489d3-103">如何使用動態套件組合</span><span class="sxs-lookup"><span data-stu-id="489d3-103">How To Use Dynamic Suite Composition</span></span>


<span data-ttu-id="489d3-104">應用程式虛擬化中的動態套件組合可讓您將應用程式定義為依存于其他應用程式，例如中介軟體或外掛程式。</span><span class="sxs-lookup"><span data-stu-id="489d3-104">Dynamic Suite Composition in Application Virtualization enables you to define an application as being dependent on another application, such as middleware or a plug-in.</span></span> <span data-ttu-id="489d3-105">這可讓應用程式與虛擬環境中的中介軟體或外掛程式互動，通常是這種情況。</span><span class="sxs-lookup"><span data-stu-id="489d3-105">This enables the application to interact with the middleware or plug-in in the virtual environment, where typically this is prevented.</span></span> <span data-ttu-id="489d3-106">這個功能非常實用，因為次應用程式套件可以與數個其他應用程式搭配使用，稱為*主要應用*程式，讓每個主要應用程式都能參考同一個輔助套件。</span><span class="sxs-lookup"><span data-stu-id="489d3-106">This is useful because a secondary application package can be used with several other applications, referred to as the *primary applications*, which enables each primary application to reference the same secondary package.</span></span>

<span data-ttu-id="489d3-107">當您順序依賴外掛程式（例如 ActiveX 控制項）或依賴于中介軟體（JRE）等中介軟體的應用程式時，您可以使用動態套件組合。</span><span class="sxs-lookup"><span data-stu-id="489d3-107">You can use Dynamic Suite Composition when you sequence applications that depend on plug-ins such as ActiveX controls or for applications that depend on middleware such as OLE DB or the Java Runtime Environment (JRE).</span></span> <span data-ttu-id="489d3-108">如果使用這些相依元件的每個應用程式都需要排序（包括元件），那麼對這些元件所做的更新將需要重新排序所有主要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="489d3-108">If each application that used these dependent components required sequencing, including the components, updates to those components would require re-sequencing all the primary applications.</span></span> <span data-ttu-id="489d3-109">如果您將沒有元件的主要應用程式排序，然後將中介軟體或外掛程式順序排列為次要套件，則只有副套件必須更新。</span><span class="sxs-lookup"><span data-stu-id="489d3-109">If you sequence the primary applications without the components and then sequence the middleware or plug-in as a secondary package, then only the secondary package must be updated.</span></span>

<span data-ttu-id="489d3-110">這種方法的優點之一是它會縮小主要套件的大小。</span><span class="sxs-lookup"><span data-stu-id="489d3-110">One advantage of this approach is that it reduces the size of the primary packages.</span></span> <span data-ttu-id="489d3-111">另一個優點是，它可讓您更好地控制次要應用程式的存取權限。</span><span class="sxs-lookup"><span data-stu-id="489d3-111">Another advantage is that it provides you with better control of access permissions on the secondary applications.</span></span> <span data-ttu-id="489d3-112">請注意，次要應用程式可以使用正常的方式來流式處理，而且不需要完全緩存即可執行。</span><span class="sxs-lookup"><span data-stu-id="489d3-112">Note that the secondary application can be streamed in the regular way and does not have to be fully cached to run.</span></span>

<span data-ttu-id="489d3-113">主要套件可以有一個以上的次要套件。</span><span class="sxs-lookup"><span data-stu-id="489d3-113">A primary package can have more than one secondary package.</span></span> <span data-ttu-id="489d3-114">不過，只支援一個相依性層面，所以您無法將次要套件定義為相依于另一個次要套件。</span><span class="sxs-lookup"><span data-stu-id="489d3-114">However, only one level of dependency is supported, so you cannot define a secondary package as dependent on another secondary package.</span></span> <span data-ttu-id="489d3-115">此外，次要應用程式只能是中介軟體或外掛程式，不能是其他完整軟體產品。</span><span class="sxs-lookup"><span data-stu-id="489d3-115">Also the secondary application can only be middleware or a plug-in and cannot be another full software product.</span></span>

<span data-ttu-id="489d3-116">如果您想要讓幾個主要的應用程式依賴單一的中介軟體產品，請務必測試此設定，以判斷在部署前，可能會對系統效能造成的影響。</span><span class="sxs-lookup"><span data-stu-id="489d3-116">If you plan to make several primary applications dependent on a single middleware product, make sure that you test this configuration to determine the potential effect on system performance before you deploy it.</span></span>

<span data-ttu-id="489d3-117">**重要** 封裝相依性可以指定為主要應用程式的強制性。</span><span class="sxs-lookup"><span data-stu-id="489d3-117">**Important** Package dependencies can be specified as mandatory for a primary application.</span></span> <span data-ttu-id="489d3-118">如果副套件已標示為強制性，且在載入期間由於某些原因無法存取，則次要套件的載入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="489d3-118">If a secondary package is flagged as mandatory and it cannot be accessed for some reason during loading, the load of the secondary package will fail.</span></span> <span data-ttu-id="489d3-119">此外，主要的應用程式也會在使用者嘗試啟動時失敗。</span><span class="sxs-lookup"><span data-stu-id="489d3-119">Also, the primary application will fail when the user tries to start it.</span></span>

 

<span data-ttu-id="489d3-120">您可以使用下列程式來建立附屬套件（適用于外掛程式或中介軟體元件），然後您就可以使用最後一個程式，在次要套件的 OSD 檔案中定義相依性。</span><span class="sxs-lookup"><span data-stu-id="489d3-120">You can use the following procedures to create a secondary package, for either a plug-in or a middleware component, and then you can use the final procedure to define the dependency in the OSD file of the secondary package.</span></span>

**<span data-ttu-id="489d3-121">使用動態套件組合建立外掛程式的副套件</span><span class="sxs-lookup"><span data-stu-id="489d3-121">To create a secondary package for a plug-in by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="489d3-122">在使用乾淨影像設定的先後順序電腦上，安裝 Application Virtualization 排序器並儲存電腦狀態。</span><span class="sxs-lookup"><span data-stu-id="489d3-122">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="489d3-123">將主要應用程式排序，並將套件儲存到伺服器上的內容資料夾中。</span><span class="sxs-lookup"><span data-stu-id="489d3-123">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

3.  <span data-ttu-id="489d3-124">從步驟1將先後順序電腦還原為已儲存的狀態。</span><span class="sxs-lookup"><span data-stu-id="489d3-124">Restore the sequencing computer to its saved state from step 1.</span></span>

4.  <span data-ttu-id="489d3-125">在先後順序的電腦上安裝並設定主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="489d3-125">Install and configure the primary application locally on the sequencing computer.</span></span>

    <span data-ttu-id="489d3-126">**重要** 您必須指定副套件的新套件根。</span><span class="sxs-lookup"><span data-stu-id="489d3-126">**Important** You must specify a new package root for the secondary package.</span></span>

     

5.  <span data-ttu-id="489d3-127">啟動 sequencer 監視階段。</span><span class="sxs-lookup"><span data-stu-id="489d3-127">Start the sequencer monitoring phase.</span></span>

6.  <span data-ttu-id="489d3-128">在先後順序的電腦上安裝外掛程式，並視需要進行設定。</span><span class="sxs-lookup"><span data-stu-id="489d3-128">Install the plug-in on the sequencing computer and configure it as needed.</span></span>

7.  <span data-ttu-id="489d3-129">開啟主要的應用程式，並確認該外掛程式正常運作。</span><span class="sxs-lookup"><span data-stu-id="489d3-129">Open the primary application, and confirm that the plug-in is working correctly.</span></span>

8.  <span data-ttu-id="489d3-130">在 sequencer 主機中，建立一個虛擬的應用程式來代表將包含該外掛程式的副套件，然後選取一個圖示。</span><span class="sxs-lookup"><span data-stu-id="489d3-130">In the sequencer console, create a dummy application to represent the secondary package that will contain the plug-in and select an icon.</span></span>

9.  <span data-ttu-id="489d3-131">將套件儲存到伺服器上的內容資料夾中。</span><span class="sxs-lookup"><span data-stu-id="489d3-131">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="489d3-132">**記事** 為了協助管理次要套件，建議套件名稱必須包含「次要套件」一詞，以強調這是不能作為獨立應用程式的套件，例如**\ [外掛程式 name \] 輔助套件**。</span><span class="sxs-lookup"><span data-stu-id="489d3-132">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Plug In Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="489d3-133">使用動態套件組合建立中介軟體的副套件</span><span class="sxs-lookup"><span data-stu-id="489d3-133">To create a secondary package for middleware by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="489d3-134">在使用乾淨影像設定的先後順序電腦上，安裝 Application Virtualization 排序器並儲存電腦狀態。</span><span class="sxs-lookup"><span data-stu-id="489d3-134">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="489d3-135">在先後順序電腦上將中介軟體安裝在本機，然後加以設定。</span><span class="sxs-lookup"><span data-stu-id="489d3-135">Install the middleware locally on the sequencing computer, and configure it.</span></span>

3.  <span data-ttu-id="489d3-136">將主要應用程式排序，並將套件儲存到伺服器上的內容資料夾中。</span><span class="sxs-lookup"><span data-stu-id="489d3-136">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

4.  <span data-ttu-id="489d3-137">從步驟1將先後順序電腦還原為已儲存的狀態。</span><span class="sxs-lookup"><span data-stu-id="489d3-137">Restore the sequencing computer to its saved state from step 1.</span></span>

5.  <span data-ttu-id="489d3-138">啟動 sequencer 以建立新的套件。</span><span class="sxs-lookup"><span data-stu-id="489d3-138">Start the sequencer to create a new package.</span></span>

6.  <span data-ttu-id="489d3-139">啟動 sequencer 監視階段。</span><span class="sxs-lookup"><span data-stu-id="489d3-139">Start the sequencer monitoring phase.</span></span>

7.  <span data-ttu-id="489d3-140">在先後順序的電腦上安裝中介軟體應用程式，並將它設定為在一般安裝中。</span><span class="sxs-lookup"><span data-stu-id="489d3-140">Install the middleware application on the sequencing computer, and configure it as in a typical installation.</span></span>

8.  <span data-ttu-id="489d3-141">完成先後順序程式。</span><span class="sxs-lookup"><span data-stu-id="489d3-141">Complete the sequencing process.</span></span>

9.  <span data-ttu-id="489d3-142">將套件儲存到伺服器上的內容資料夾中。</span><span class="sxs-lookup"><span data-stu-id="489d3-142">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="489d3-143">**記事** 為了協助管理次要套件，建議套件名稱必須包含「次要套件」一詞，以強調這是不能做為獨立應用程式的套件，例如**\ [中介軟體名稱 \] 次套件**。</span><span class="sxs-lookup"><span data-stu-id="489d3-143">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Middleware Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="489d3-144">在主要套件中定義相依性</span><span class="sxs-lookup"><span data-stu-id="489d3-144">To define the dependency in the primary package</span></span>**

1. <span data-ttu-id="489d3-145">在伺服器上，開啟副封裝的 OSD 檔案以進行編輯。</span><span class="sxs-lookup"><span data-stu-id="489d3-145">On the server, open the OSD file of the secondary package for editing.</span></span> <span data-ttu-id="489d3-146">（最好是使用 XML 編輯器來變更 OSD 檔案; 不過，您也可以使用 [記事本] 做為替代）。</span><span class="sxs-lookup"><span data-stu-id="489d3-146">(It is a good idea to use an XML editor to make changes to the OSD file; however, you can use Notepad as an alternative.)</span></span>

2. <span data-ttu-id="489d3-147">從該檔案複製**基本代碼 HREF**線。</span><span class="sxs-lookup"><span data-stu-id="489d3-147">Copy the **CODEBASE HREF** line from that file.</span></span>

3. <span data-ttu-id="489d3-148">開啟主要套件的 OSD 檔案以進行編輯。</span><span class="sxs-lookup"><span data-stu-id="489d3-148">Open the OSD file of the primary package for editing.</span></span>

4. <span data-ttu-id="489d3-149">在 <strong> &lt; &gt; </strong> \*\* &lt; VIRTUALENV &gt; **節結尾的 [ \*\* &lt; /ENVLIST &gt; \*\* ] 標籤末尾，在** &lt; /VIRTUALENV &gt; \*\*標記之前插入相依性標記。</span><span class="sxs-lookup"><span data-stu-id="489d3-149">Insert the <strong>&lt;DEPENDENCIES&gt;</strong>tag after the close of **&lt;/ENVLIST&gt;** tag at the end of the **&lt;VIRTUALENV&gt;** section just before the **&lt;/VIRTUALENV&gt;** tag.</span></span>

5. <span data-ttu-id="489d3-150">在您剛建立的相依性標記之後，在次要套件中貼上 [**基本代碼 HREF** \*\* &lt; ] &gt; \*\*行。</span><span class="sxs-lookup"><span data-stu-id="489d3-150">Paste the **CODEBASE HREF** line from the secondary package after the **&lt;DEPENDENCIES&gt;** tag you just created.</span></span>

6. <span data-ttu-id="489d3-151">如果次要套件是強制性套件，即必須在開始主要套件之前啟動，請在**CODEBASE**標記內新增**強制 = "TRUE"** 屬性。</span><span class="sxs-lookup"><span data-stu-id="489d3-151">If the secondary package is a mandatory package, which means that it must be started before the primary package is started, add the **MANDATORY=”TRUE”** property inside the **CODEBASE** tag.</span></span> <span data-ttu-id="489d3-152">如果不是強制性的，則可以省略屬性。</span><span class="sxs-lookup"><span data-stu-id="489d3-152">If it is not mandatory, the property can be omitted.</span></span>

7. <span data-ttu-id="489d3-153">插入下列專案以關閉 [相依性\*\* &lt; ] &gt; \*\*標記：</span><span class="sxs-lookup"><span data-stu-id="489d3-153">Close the **&lt;DEPENDENCIES&gt;** tag by inserting the following:</span></span>

   **<span data-ttu-id="489d3-154">&lt;/DEPENDENCIES&gt;</span><span class="sxs-lookup"><span data-stu-id="489d3-154">&lt;/DEPENDENCIES&gt;</span></span>**

8. <span data-ttu-id="489d3-155">查看您對 OSD 檔案所做的變更，然後儲存並關閉檔案。</span><span class="sxs-lookup"><span data-stu-id="489d3-155">Review the changes that you made to the OSD file, and then save and close the file.</span></span> <span data-ttu-id="489d3-156">下列範例顯示已新增的區段應該如何顯示。</span><span class="sxs-lookup"><span data-stu-id="489d3-156">The following example shows how the added section should appear.</span></span> <span data-ttu-id="489d3-157">此處顯示的標記值僅限範例。</span><span class="sxs-lookup"><span data-stu-id="489d3-157">The tag values shown here are for example only.</span></span>

   **<span data-ttu-id="489d3-158">&lt;VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="489d3-158">&lt;VIRTUALENV&gt;</span></span>**

        **&lt;ENVLIST&gt;**

   **<span data-ttu-id="489d3-159">…</span><span class="sxs-lookup"><span data-stu-id="489d3-159">…</span></span>**

        **&lt;/ENVLIST&gt;**

        **&lt;DEPENDENCIES&gt;**

             **&lt;CODEBASE HREF="rtsp://virt\_apps/package.1/package.1.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.1\\osguard.cp"/&gt;**

             **&lt;CODEBASE HREF="rtsp://sample\_apps/package.2/sample.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.2\\osguard.cp" MANDATORY="TRUE" /&gt;**

        **&lt;/DEPENDENCIES&gt;**

   **<span data-ttu-id="489d3-160">&lt;/VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="489d3-160">&lt;/VIRTUALENV&gt;</span></span>**

9. <span data-ttu-id="489d3-161">如果副封裝在 OSD 檔案的\*\* &lt; ENVLIST &gt; \*\*區段中有任何專案，您必須將這些專案複製到主要套件中的相同區段。</span><span class="sxs-lookup"><span data-stu-id="489d3-161">If the secondary package has any entries in the **&lt;ENVLIST&gt;** section of the OSD file, you must copy those entries to the same section in the primary package.</span></span>

## <span data-ttu-id="489d3-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="489d3-162">Related topics</span></span>


[<span data-ttu-id="489d3-163">如何使用 App-v 排序器建立或升級虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="489d3-163">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





