---
title: 如何將封裝分支
description: 如何將封裝分支
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801693"
---
# 如何將封裝分支


使用此程式來修改現有的已排序應用程式套件，讓您可以與原始的已排序應用程式套件並存執行。 這個處理常式稱為 [分支]。 當您分支虛擬應用程式套件時，您可以執行同一個套件的兩個版本。 例如，您可以將 service pack 套用至現有的套件，並與原始已排序的虛擬應用程式套件並存執行。

使用下列程式來分支已排序的虛擬應用程式套件。

**分支已排序的虛擬應用程式套件**

1.  開啟 Microsoft Application Virtualization （App-v）排序器。 若要指定包含您想要分支的套件（sprj）的目的地目錄，請**選取 [** 檔案]，然後按一下 [**開啟**]。

2.  流覽至包含您要分支之已排序之應用程式的目錄，然後按一下 [**開啟**]。

3.  若要儲存套件複本 **，請在**應用程式 V 排序器中選取 [檔案]、[**另存**新檔]。 指定新的唯一名稱，並為套件複本指定新的唯一套件根目錄。 按一下 **[儲存]**。

    **重要**  
    您必須指定新的套件名稱，否則您會覆寫現有的套件版本。



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. 在您儲存新版本之後，您可以套用所需的設定變更，並將相關聯的 .ICO、OSD、SFT 及 SPRJ 檔案儲存在應用程式虛擬化（App-v）伺服器上的正確位置。

## 相關主題


[Application Virtualization Sequencer 的工作](tasks-for-the-application-virtualization-sequencer.md)









