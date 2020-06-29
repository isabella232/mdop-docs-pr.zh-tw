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
# 如何使用文字編輯器編輯 OSD 檔案


使用下列程式，使用文字編輯器編輯開放式軟體描述項（OSD）檔案。

**使用文字編輯器編輯 OSD 檔案**

1.  使用任何 XML 或 ASCII 文字編輯器開啟 OSD 檔案，例如 Microsoft Notepad。

    **記事** 修改 OSD 檔案之前，請先閱讀安裝目錄中由 XSD 檔案所指定的架構。 無法追蹤這個架構，可能會導致錯誤，讓順序應用程式無法順利啟動。

     

2.  使用您的 XML 或 ASCII 文字編輯器編輯 OSD 檔案，遵循指定的架構與下列準則：

    1.  確定命名元素嵌套在 &lt; SOFTPKG &gt; 根項目中。

    2.  確定元素名稱全部是大寫。

    3.  請注意，屬性值會區分大小寫。

    4.  請謹慎地輸入，並觀察 XML 規格。

## 相關主題


[關於 OSD 索引標籤](about-the-osd-tab.md)

[如何編輯 OSD 檔案](how-to-edit-an-osd-file.md)

[OSD 檔案元素](osd-file-elements.md)

 

 





