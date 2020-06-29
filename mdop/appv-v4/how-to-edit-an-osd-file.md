---
title: 如何編輯 OSD 檔案
description: 如何編輯 OSD 檔案
author: dansimp
ms.assetid: 0d126ba7-72fb-42ce-982e-90ed01a852c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4a0ff4a8efe1fa177f6847c344add94bca3648cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801417"
---
# <span data-ttu-id="d8381-103">如何編輯 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="d8381-103">How to Edit an OSD File</span></span>


<span data-ttu-id="d8381-104">您可以使用下列程式，透過新增或刪除元素或屬性來修改已排序的應用程式套件開啟的軟體描述項（OSD）檔案。</span><span class="sxs-lookup"><span data-stu-id="d8381-104">Use the following procedures to modify a sequenced application package's Open Software Descriptor (OSD) file by adding or deleting an element or an attribute.</span></span>

<span data-ttu-id="d8381-105">**記事** 有些元素沒有屬性，因此無法將屬性新增到每個元素。</span><span class="sxs-lookup"><span data-stu-id="d8381-105">**Note** Some elements do not have an attribute, so it is not possible to add an attribute to every element.</span></span>

 

<span data-ttu-id="d8381-106">**重要** 如果您使用 OSD 編輯器來變更 sft 檔案名，即 OSD 檔案中 CODEBASE 元素的 HREF 屬性，您必須使用 [**另存**新檔] 命令來儲存專案檔案的變更。</span><span class="sxs-lookup"><span data-stu-id="d8381-106">**Important** If you use the OSD editor to change the .sft file name, the HREF attribute of the CODEBASE element in the OSD file, you must use the **Save As** command to save the change to the project files.</span></span>

 

**<span data-ttu-id="d8381-107">新增元素</span><span class="sxs-lookup"><span data-stu-id="d8381-107">To add an element</span></span>**

1.  <span data-ttu-id="d8381-108">按一下 [ **OSD**檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d8381-108">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="d8381-109">在 [功能窗格] 中，選取您要修改的順序式應用程式套件的 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8381-109">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="d8381-110">在 [功能窗格] 中，以滑鼠右鍵按一下您要修改的元素。</span><span class="sxs-lookup"><span data-stu-id="d8381-110">In the navigation pane, right-click the element that you want to modify.</span></span> <span data-ttu-id="d8381-111">在功能表上，選取 [**元素**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-111">On the menu, select **Element** and select **Add**.</span></span>

4.  <span data-ttu-id="d8381-112">從功能表中，選取您要新增的元素，例如 [**基本代碼**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-112">From the menu, select the element you want to add—for example, **Codebase**.</span></span>

5.  <span data-ttu-id="d8381-113">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-113">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="d8381-114">刪除元素</span><span class="sxs-lookup"><span data-stu-id="d8381-114">To delete an element</span></span>**

1.  <span data-ttu-id="d8381-115">按一下 [ **OSD**檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d8381-115">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="d8381-116">在 [功能窗格] 中，選取您要修改的順序式應用程式套件的 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8381-116">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="d8381-117">在 [功能窗格] 中，以滑鼠右鍵按一下您要刪除的元素。</span><span class="sxs-lookup"><span data-stu-id="d8381-117">In the navigation pane, right-click the element that you want to delete.</span></span> <span data-ttu-id="d8381-118">在功能表上，選取 [**元素**]，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-118">On the menu, select **Element** and select **Delete**.</span></span>

4.  <span data-ttu-id="d8381-119">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-119">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="d8381-120">新增屬性</span><span class="sxs-lookup"><span data-stu-id="d8381-120">To add an attribute</span></span>**

1.  <span data-ttu-id="d8381-121">按一下 [ **OSD**檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d8381-121">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="d8381-122">在 [功能窗格] 中，選取您要修改的順序式應用程式套件的 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8381-122">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="d8381-123">在左窗格中，以滑鼠右鍵按一下您要新增屬性的元素。</span><span class="sxs-lookup"><span data-stu-id="d8381-123">In the left pane, right-click the element to which you want to add an attribute.</span></span> <span data-ttu-id="d8381-124">在功能表上，選取 [**屬性**]，然後選取 [**新增**]，並從清單中選擇可用的屬性。</span><span class="sxs-lookup"><span data-stu-id="d8381-124">On the menu, select **Attribute** and select **Add**, choosing from the listed available attributes.</span></span>

4.  <span data-ttu-id="d8381-125">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-125">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="d8381-126">刪除屬性</span><span class="sxs-lookup"><span data-stu-id="d8381-126">To delete an attribute</span></span>**

1.  <span data-ttu-id="d8381-127">按一下 [ **OSD**檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d8381-127">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="d8381-128">在 [功能窗格] 中，選取您要修改的順序式應用程式套件的 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="d8381-128">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="d8381-129">在 [功能窗格] 中，以滑鼠右鍵按一下您要從中刪除屬性的元素。</span><span class="sxs-lookup"><span data-stu-id="d8381-129">In the navigation pane, right-click the element from which you want to delete an attribute.</span></span> <span data-ttu-id="d8381-130">在功能表上，選取 [**屬性**]，然後選取 [**刪除**]，選擇您要刪除的屬性。</span><span class="sxs-lookup"><span data-stu-id="d8381-130">On the menu, select **Attribute** and then select **Delete**, choosing the attribute you wish to delete.</span></span>

4.  <span data-ttu-id="d8381-131">從 [**檔案**] 功能表中，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d8381-131">From the **File** menu, select **Save**.</span></span>

## <span data-ttu-id="d8381-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="d8381-132">Related topics</span></span>


[<span data-ttu-id="d8381-133">關於 OSD 索引標籤</span><span class="sxs-lookup"><span data-stu-id="d8381-133">About the OSD Tab</span></span>](about-the-osd-tab.md)

[<span data-ttu-id="d8381-134">如何使用文字編輯器編輯 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="d8381-134">How to Edit an OSD File Using a Text Editor</span></span>](how-to-edit-an-osd-file-using-a-text-editor.md)

[<span data-ttu-id="d8381-135">OSD 檔案元素</span><span class="sxs-lookup"><span data-stu-id="d8381-135">OSD File Elements</span></span>](osd-file-elements.md)

[<span data-ttu-id="d8381-136">排序器主控台</span><span class="sxs-lookup"><span data-stu-id="d8381-136">Sequencer Console</span></span>](sequencer-console.md)

 

 





