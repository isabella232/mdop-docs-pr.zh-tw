---
title: 如何使用文字編輯器編輯 OSD 檔案
description: 如何使用文字編輯器編輯 OSD 檔案
author: dansimp
ms.assetid: f4263a1b-824f-49b9-8060-b8229c9d9960
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c83547b38cee7e91e8348689583e0542a88dab83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801418"
---
# <span data-ttu-id="f7d7c-103">如何使用文字編輯器編輯 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="f7d7c-103">How to Edit an OSD File Using a Text Editor</span></span>


<span data-ttu-id="f7d7c-104">使用下列程式，使用文字編輯器編輯開放式軟體描述項（OSD）檔案。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-104">Use the following procedure to edit an Open Software Descriptor (OSD) file by using a text editor.</span></span>

**<span data-ttu-id="f7d7c-105">使用文字編輯器編輯 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="f7d7c-105">To edit an OSD file by using a text editor</span></span>**

1.  <span data-ttu-id="f7d7c-106">使用任何 XML 或 ASCII 文字編輯器開啟 OSD 檔案，例如 Microsoft Notepad。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-106">Open the OSD file using any XML or ASCII text editor—for example, Microsoft Notepad.</span></span>

    <span data-ttu-id="f7d7c-107">**記事** 修改 OSD 檔案之前，請先閱讀安裝目錄中由 XSD 檔案所指定的架構。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-107">**Note** Before modifying the OSD file, read the schema prescribed by the XSD file in the install directory.</span></span> <span data-ttu-id="f7d7c-108">無法追蹤這個架構，可能會導致錯誤，讓順序應用程式無法順利啟動。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-108">Failing to follow this schema might introduce errors that prevent a sequenced application from starting successfully.</span></span>

     

2.  <span data-ttu-id="f7d7c-109">使用您的 XML 或 ASCII 文字編輯器編輯 OSD 檔案，遵循指定的架構與下列準則：</span><span class="sxs-lookup"><span data-stu-id="f7d7c-109">Edit the OSD file using your XML or ASCII text editor of choice, adhering to the prescribed schema and the following guidelines:</span></span>

    1.  <span data-ttu-id="f7d7c-110">確定命名元素嵌套在 &lt; SOFTPKG &gt; 根項目中。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-110">Ensure that named elements are nested within the &lt;SOFTPKG&gt; root element.</span></span>

    2.  <span data-ttu-id="f7d7c-111">確定元素名稱全部是大寫。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-111">Ensure that element names are in all uppercase letters.</span></span>

    3.  <span data-ttu-id="f7d7c-112">請注意，屬性值會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-112">Be aware that attribute values are case sensitive.</span></span>

    4.  <span data-ttu-id="f7d7c-113">請謹慎地輸入，並觀察 XML 規格。</span><span class="sxs-lookup"><span data-stu-id="f7d7c-113">Type carefully, and observe the XML specifications.</span></span>

## <span data-ttu-id="f7d7c-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="f7d7c-114">Related topics</span></span>


[<span data-ttu-id="f7d7c-115">關於 OSD 索引標籤</span><span class="sxs-lookup"><span data-stu-id="f7d7c-115">About the OSD Tab</span></span>](about-the-osd-tab.md)

[<span data-ttu-id="f7d7c-116">如何編輯 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="f7d7c-116">How to Edit an OSD File</span></span>](how-to-edit-an-osd-file.md)

[<span data-ttu-id="f7d7c-117">OSD 檔案元素</span><span class="sxs-lookup"><span data-stu-id="f7d7c-117">OSD File Elements</span></span>](osd-file-elements.md)

 

 





